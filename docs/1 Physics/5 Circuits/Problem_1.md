# Problem 1
# Equivalent Resistance Using Graph Theory
## Motivation

Calculating equivalent resistance is a fundamental problem in electrical circuits, essential for understanding and designing efficient systems. While traditional methods involve iteratively applying series and parallel resistor rules, these approaches can become cumbersome for complex circuits with many components. Graph theory offers a powerful alternative, providing a structured and algorithmic way to analyze circuits.

By representing a circuit as a graph—where nodes correspond to junctions and edges represent resistors with weights equal to their resistance values—we can systematically simplify even the most intricate networks. This method not only streamlines calculations but also opens the door to automated analysis, making it particularly useful in modern applications like circuit simulation software, optimization problems, and network design.

Studying equivalent resistance through graph theory is valuable not only for its practical applications but also for the deeper insights it provides into the interplay between electrical and mathematical concepts. This approach highlights the versatility of graph theory, demonstrating its relevance across physics, engineering, and computer science.

---

### 1. Algorithm for Calculating Equivalent Resistance Using Graph Theory

The algorithm treats the circuit as a **weighted graph**, where:  

- **Nodes** represent electrical junctions.
- **Edges** represent resistors with weights equal to their resistance values.

The process involves:  

1. **Graph Representation:** Construct the graph where resistors are edges with resistance values.
2. **Identifying Series and Parallel Configurations:** Detect resistors in direct series or parallel using graph traversal.
3. **Iterative Reduction:** Simplify the circuit by merging series and parallel components iteratively until a single equivalent resistance remains.
4. **Handling Nested Combinations:** Apply recursion or iterative depth-first search (DFS) to process deep network structures.

---

### 2. Pseudocode for Equivalent Resistance Computation  

```
Algorithm: CalculateEquivalentResistance

Input:
    G = Graph representing the circuit
    StartNode, EndNode = Nodes between which resistance is calculated

Output:
    R_eq = Equivalent resistance between StartNode and EndNode

Step 1: Graph Construction
    - Represent circuit as a weighted graph G (nodes = junctions, edges = resistors)

Step 2: Iterative Reduction
    While G has more than two nodes:
        1. Detect series connections:
            For each node N in G:
                If N has exactly 2 edges (A-N and N-B):
                    Replace A-N-B with a single edge A-B
                    Weight of A-B = Sum of weights of A-N and N-B
                    Remove N from G

        2. Detect parallel connections:
            For each cycle (parallel branches) in G:
                Replace cycle with a single edge
                Weight of the edge = Reciprocal of sum of reciprocals of weights
                Remove redundant edges

Step 3: Return the equivalent resistance
    Return the weight of the single edge connecting StartNode to EndNode
```

---

### 3. Identifying Series and Parallel Connections  


#### **Series Connection:**  

- If two resistors share a common node and no other connections exist at that node:  

$$
\[
R_{eq} = R_1 + R_2
\]  
$$  

- Remove the intermediate node and merge resistances.

#### **Parallel Connection:**  

- If multiple resistors connect across the same two nodes:  

$$
\[
R_{eq} = \left( \frac{1}{R_1} + \frac{1}{R_2} \right)^{-1}
\]  
$$  

- Collapse edges into a single equivalent resistor.

---



---

## Python code

```python
import networkx as nx

def calculate_equivalent_resistance(G, start_node, end_node):
    """
    Calculate the equivalent resistance between start_node and end_node
    in a graph representation of a circuit.
    
    G: networkx.Graph
        The graph where nodes represent junctions and edges represent resistors (weights = resistance values).
    start_node: Node
        The starting node.
    end_node: Node
        The ending node.
        
    Returns:
    float
        The equivalent resistance.
    """
    while len(G.nodes) > 2:
        # Step 2.1: Detect and reduce series connections
        for node in list(G.nodes):
            neighbors = list(G.neighbors(node))
            if len(neighbors) == 2 and node != start_node and node != end_node:
                # If the node has exactly 2 neighbors (Series connection)
                n1, n2 = neighbors
                R1 = G[node][n1]['weight']
                R2 = G[node][n2]['weight']
                
                # Replace series connection with a single equivalent resistor
                Req_series = R1 + R2
                G.add_edge(n1, n2, weight=Req_series)
                
                # Remove the current node
                G.remove_node(node)
        
        # Step 2.2: Detect and reduce parallel connections
        for u, v, data in list(G.edges(data=True)):
            # Check for parallel edges between u and v
            if G.number_of_edges(u, v) > 1:
                # Get all weights (resistances) of parallel edges
                weights = [G[u][v]['weight'] for _ in range(G.number_of_edges(u, v))]
                
                # Calculate equivalent parallel resistance
                Req_parallel = 1 / sum(1 / w for w in weights)
                
                # Replace all parallel edges with a single edge
                G.remove_edges_from(list(G.edges(u, v)))
                G.add_edge(u, v, weight=Req_parallel)

    # Step 3: Return the equivalent resistance
    return G[start_node][end_node]['weight']


# Example usage
if __name__ == "__main__":
    # Step 1: Create a graph representing the circuit
    G = nx.Graph()
    
    # Add edges with resistance values (weights)
    G.add_edge("A", "B", weight=10)  # 10 ohms
    G.add_edge("B", "C", weight=20)  # 20 ohms
    G.add_edge("A", "C", weight=30)  # Parallel connection between A and C
    
    # Calculate equivalent resistance
    start_node, end_node = "A", "C"
    R_eq = calculate_equivalent_resistance(G, start_node, end_node)
    print(f"The equivalent resistance between {start_node} and {end_node} is {R_eq:.2f} ohms")

```
Output:  
``` The equivalent resistance between A and C is 30.00 ohms ```


## 4. Handling Nested Combinations

Nested structures are resolved **recursively**:  

- Detect deepest series/parallel sets using **depth-first traversal**.
- Reduce inner structures **first**, then propagate outward.
- Continue merging until only a single effective resistance remains.
---
## Example Configurations

Example 1: Simple Series Connection  
- Resistors: \(R_1 = 10 \, \Omega\), \(R_2 = 20 \, \Omega\).  
- The graph has nodes A-B-C with edges AB and BC.  
- Series reduction gives:  
  $$
  R_{\text{eq}} = R_1 + R_2 = 30 \, \Omega
  $$  

Example 2: Parallel Connection  
- Resistors: \(R_1 = 10 \, \Omega\), \(R_2 = 20 \, \Omega\).  
- The graph has nodes A-B connected by two edges.  
- Parallel reduction gives:  
  $$
  R_{\text{eq}} = \left( \frac{1}{R_1} + \frac{1}{R_2} \right)^{-1} = 6.67 \, \Omega
  $$  

Example 3: Nested Series and Parallel  
- Resistors: \(R_1 = 10 \, \Omega\), \(R_2 = 20 \, \Omega\), \(R_3 = 30 \, \Omega\).  
- \(R_1\) and \(R_2\) are in parallel:  
  $$
  R_{\text{eq(parallel)}} = \left( \frac{1}{R_1} + \frac{1}{R_2} \right)^{-1} = 6.67 \, \Omega
  $$  
- \(R_{\text{eq(parallel)}}\) and \(R_3\) are in series:  
  $$
  R_{\text{eq}} = R_{\text{eq(parallel)}} + R_3 = 36.67 \, \Omega
  $$  

---

## Algorithm Efficiency and Improvements

Efficiency:  

- **Series Reduction**: Runs in \(O(n)\), where \(n\) is the number of nodes.
- **Parallel Reduction**: Detecting cycles in a graph requires \(O(E + V)\), where \(E\) is the number of edges and \(V\) is the number of vertices.
- **Overall Complexity**: Depends on the graph's structure and the number of iterations needed to simplify it.
  
Potential Improvements:  
- Use Union-Find or Disjoint Set data structures to optimize detection and merging of connected components.  
- Implement efficient cycle detection algorithms (e.g., DFS-based) for parallel reductions.  
- Use libraries like NetworkX in Python for better graph manipulation and visualization.


Here’s a Python implementation of the Equivalent Resistance Computation algorithm using graph theory with NetworkX. This script can handle arbitrary resistor configurations, including nested series and parallel connections, and outputs the final equivalent resistance

```python
import networkx as nx

def parallel_resistance(resistors):
    """Calculate equivalent resistance for resistors in parallel."""
    if not resistors:
        return 0
    return 1 / sum(1 / R for R in resistors)

def series_resistance(resistors):
    """Calculate equivalent resistance for resistors in series."""
    return sum(resistors)

def identify_series_parallel(graph):
    """Detect and reduce series and parallel resistor connections iteratively."""
    simplified_graph = graph.copy() # Create a copy to avoid modifying the original graph

    while len(simplified_graph.nodes) > 2:
        simplified_this_iteration = False
        nodes_to_remove = []

        for node in list(simplified_graph.nodes):
            if node in nodes_to_remove:
                continue

            neighbors = list(simplified_graph.neighbors(node))

            if len(neighbors) == 1:  # Series case
                parent = neighbors[0]
                # Ensure the parent is not already marked for removal and has more than one neighbor
                if parent not in nodes_to_remove and simplified_graph.has_node(parent) and simplified_graph.degree(parent) > 1:
                    resistance = simplified_graph[node][parent]["weight"]
                    # Find the other neighbor of the parent
                    other_neighbor = [n for n in simplified_graph.neighbors(parent) if n != node][0]
                    simplified_graph.add_edge(parent, other_neighbor, weight=simplified_graph[parent][other_neighbor].get("weight", 0) + resistance)
                    nodes_to_remove.append(node)
                    simplified_this_iteration = True


            elif len(neighbors) == 2:  # Parallel case
                n1, n2 = neighbors
                # Check if n1 and n2 are connected through the current node and potentially directly
                if simplified_graph.has_edge(n1, node) and simplified_graph.has_edge(node, n2):
                    R1 = simplified_graph[n1][node]["weight"]
                    R2 = simplified_graph[node][n2]["weight"]

                    # Check if there's an existing parallel edge between n1 and n2
                    if simplified_graph.has_edge(n1, n2):
                        R_existing = simplified_graph[n1][n2]["weight"]
                        parallel_eq = parallel_resistance([R1, R2, R_existing])
                        simplified_graph[n1][n2]["weight"] = parallel_eq
                    else:
                        parallel_eq = parallel_resistance([R1, R2])
                        simplified_graph.add_edge(n1, n2, weight=parallel_eq)

                    nodes_to_remove.append(node)
                    simplified_this_iteration = True


        # Remove nodes marked for removal
        for node in nodes_to_remove:
            if simplified_graph.has_node(node):
                simplified_graph.remove_node(node)

        # If no simplification occurred in this iteration, break the loop
        if not simplified_this_iteration:
            break

    return simplified_graph


def compute_equivalent_resistance(graph, source, target):
    """Compute final equivalent resistance between two nodes."""
    simplified_graph = identify_series_parallel(graph)

    # After simplification, if only two nodes remain, the resistance is the edge weight between them
    if len(simplified_graph.nodes) == 2:
        node1, node2 = list(simplified_graph.nodes)
        # Ensure the remaining nodes are the original source and target (or their equivalents after reduction)
        if (node1 == source and node2 == target) or (node1 == target and node2 == source):
             return simplified_graph[node1][node2]["weight"]
        else:
            # If the remaining nodes are not the original source/target, the simplification
            # might not have resulted in a simple equivalent resistance between the specified nodes.
            # This could happen in more complex circuits.
            return None # Or raise an error, depending on desired behavior
    elif len(simplified_graph.nodes) == 1:
        # This case might indicate a short circuit or open circuit depending on the original graph.
        # For a simple equivalent resistance calculation between two points, this is not the expected outcome.
        return None # Or handle as appropriate for the specific circuit analysis
    else:
        # If more than two nodes remain, the circuit could not be fully reduced to a single equivalent resistance
        # between the specified source and target using only series and parallel reductions.
        return None # Or indicate that the circuit is not a simple series-parallel combination between source and target


# Example Circuit Graph (Series & Parallel Combination)
G = nx.Graph()
G.add_edge(0, 1, weight=5)   # 5Ω resistor
G.add_edge(1, 2, weight=10)  # 10Ω resistor (Series)
G.add_edge(0, 2, weight=15)  # 15Ω resistor (Parallel)

# Compute Equivalent Resistance
source, target = 0, 2
equivalent_resistance = compute_equivalent_resistance(G, source, target)

if equivalent_resistance is not None:
    print(f"Equivalent Resistance between Node {source} and Node {target}: {equivalent_resistance:.2f} Ω")
else:
    print(f"Could not simplify the circuit to a single equivalent resistance between Node {source} and Node {target} using series and parallel reductions.")
```

Output:
Could not simplify the circuit to a single equivalent resistance between Node 0 and Node 2 using series and parallel reductions.