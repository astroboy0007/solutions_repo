# Problem 1
# Equivalent Resistance Using Graph Theory

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

R_{eq} = R_1 + R_2
  
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
  



Testing Scenarios
- ✅ Series & Parallel networks: Basic components.  
- ✅ Nested resistors: Multi-layer configurations.  
- ✅ Complex circuits with cycles: Advanced graph structures.


```python
import networkx as nx
import numpy as np

def parallel_resistance(resistors):
    """Calculate equivalent resistance for resistors in parallel."""
    return 1 / sum(1 / R for R in resistors) if resistors else float('inf')

def series_resistance(resistors):
    """Calculate equivalent resistance for resistors in series."""
    return sum(resistors)

def simplify_series_parallel(graph, source, target):
    """Detect and reduce series and parallel resistor connections iteratively, keeping source and target intact."""
    while len(graph.nodes) > 2:
        for node in list(graph.nodes):
            if node in [source, target]:  # Ensure source and target remain
                continue
            
            neighbors = list(graph.neighbors(node))

            if len(neighbors) == 1:  # Series case
                parent = neighbors[0]
                resistance = graph[node][parent]["weight"]
                graph.remove_node(node)  

                if parent in graph and len(graph.neighbors(parent)) > 0:
                    for neighbor in graph.neighbors(parent):
                        graph[parent][neighbor]["weight"] += resistance

            elif len(neighbors) == 2:  # Parallel case
                R1 = graph[node][neighbors[0]]["weight"]
                R2 = graph[node][neighbors[1]]["weight"]
                R_eq = parallel_resistance([R1, R2])

                graph.add_edge(neighbors[0], neighbors[1], weight=R_eq)
                graph.remove_node(node)

    return graph

def kirchhoff_resistance_matrix(graph, source, target):
    """Solve equivalent resistance using Kirchhoff's laws and matrix methods."""
    nodes = list(graph.nodes())
    node_index = {node: i for i, node in enumerate(nodes)}

    # Build Kirchhoff Matrix
    size = len(nodes)
    matrix = np.zeros((size, size))
    currents = np.zeros(size)

    for u, v, data in graph.edges(data=True):
        resistance = data["weight"]
        matrix[node_index[u], node_index[u]] += 1 / resistance
        matrix[node_index[v], node_index[v]] += 1 / resistance
        matrix[node_index[u], node_index[v]] -= 1 / resistance
        matrix[node_index[v], node_index[u]] -= 1 / resistance

    # Set source-target voltage difference to 1V
    currents[node_index[source]] = 1
    currents[node_index[target]] = -1

    # Solve circuit equations using linear algebra
    voltages = np.linalg.pinv(matrix).dot(currents)
    equivalent_resistance = voltages[node_index[source]] - voltages[node_index[target]]

    return abs(equivalent_resistance)

def compute_equivalent_resistance(graph, source, target):
    """Compute the final equivalent resistance between two nodes."""
    simplified_graph = simplify_series_parallel(graph, source, target)
    
    if nx.has_path(simplified_graph, source, target):
        return kirchhoff_resistance_matrix(simplified_graph, source, target)
    else:
        return "Could not simplify the circuit using only series and parallel reductions."

# **Test Cases**

# **Example 1: Simple Series & Parallel Combination**
G1 = nx.Graph()
G1.add_edge(0, 1, weight=5)   # 5Ω resistor
G1.add_edge(1, 2, weight=10)  # 10Ω resistor (Series)
G1.add_edge(0, 2, weight=15)  # 15Ω resistor (Parallel)

source, target = 0, 2
equivalent_resistance = compute_equivalent_resistance(G1, source, target)
print(f"Test 1 - Equivalent Resistance: {equivalent_resistance:.2f} Ω")

# **Example 2: Nested Configurations**
G2 = nx.Graph()
G2.add_edge(0, 1, weight=4)
G2.add_edge(1, 2, weight=6)
G2.add_edge(2, 3, weight=8)
G2.add_edge(1, 3, weight=3)  # Parallel
G2.add_edge(0, 3, weight=2)  # Parallel

source, target = 0, 3
equivalent_resistance = compute_equivalent_resistance(G2, source, target)
print(f"Test 2 - Equivalent Resistance: {equivalent_resistance:.2f} Ω")

# **Example 3: Complex Graph with Cycles**
G3 = nx.Graph()
G3.add_edge(0, 1, weight=1)
G3.add_edge(1, 2, weight=2)
G3.add_edge(2, 3, weight=3)
G3.add_edge(3, 0, weight=4)  # Cycle
G3.add_edge(1, 3, weight=5)  # Additional path

source, target = 0, 3
equivalent_resistance = compute_equivalent_resistance(G3, source, target)
print(f"Test 3 - Equivalent Resistance: {equivalent_resistance:.2f} Ω")
```

Output:  

Test 1 - Equivalent Resistance: 3.33 Ω  
Test 2 - Equivalent Resistance: 1.85 Ω  
Test 3 - Equivalent Resistance: 0.55 Ω