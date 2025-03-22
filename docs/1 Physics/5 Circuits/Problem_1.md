# Problem 1
# Equivalent Resistance Using Graph Theory
## Motivation

Calculating equivalent resistance is a fundamental problem in electrical circuits, essential for understanding and designing efficient systems. While traditional methods involve iteratively applying series and parallel resistor rules, these approaches can become cumbersome for complex circuits with many components. Graph theory offers a powerful alternative, providing a structured and algorithmic way to analyze circuits.

By representing a circuit as a graph—where nodes correspond to junctions and edges represent resistors with weights equal to their resistance values—we can systematically simplify even the most intricate networks. This method not only streamlines calculations but also opens the door to automated analysis, making it particularly useful in modern applications like circuit simulation software, optimization problems, and network design.

Studying equivalent resistance through graph theory is valuable not only for its practical applications but also for the deeper insights it provides into the interplay between electrical and mathematical concepts. This approach highlights the versatility of graph theory, demonstrating its relevance across physics, engineering, and computer science.

---

## Algorithm Description
The algorithm uses graph theory to model a circuit as a graph:

Steps:  
1. Graph Construction:  
- Build a graph where edges have weights corresponding to resistor values.  
2. Detect Series Connections:  
- Identify linear chains of resistors (nodes with only two connections) and replace them with a single equivalent resistor: [ R_{\text{eq (series)}} = R_1 + R_2 + \dots + R_n ]  
3. Detect Parallel Connections:  
- Find cycles or parallel branches and replace them with a single equivalent resistor: [ \frac{1}{R_{\text{eq (parallel)}}} = \frac{1}{R_1} + \frac{1}{R_2} + \dots + \frac{1}{R_n} ]  
4. Iterative Reduction:  
- Repeat steps 2 and 3 until the entire graph is reduced to a single edge representing the equivalent resistance.  
5. Handle Nested Combinations:  
- Nested series and parallel combinations are automatically handled by recursive application of steps 2 and 3.  

---
## Pseudocode

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
- The equivalent resistance between A and C is 30.00 ohms


## Handling Nested Combinations

The algorithm automatically handles nested combinations through iterative graph simplification. For example:  
    - If a series reduction creates a new branch, the parallel reduction step will automatically simplify it.  
    - If a parallel reduction creates a new linear chain, the series reduction step will handle it in the next iteration.

This recursive simplification ensures that even deeply nested configurations are reduced correctly.

---
## Example Configurations

Example 1: Simple Series Connection  
- Resistors: (R_1 = 10 , \Omega), (R_2 = 20 , \Omega).
- The graph has nodes A-B-C with edges AB and BC.
- Series reduction gives (R_{\text{eq}} = R_1 + R_2 = 30 , \Omega).
  
Example 2: Parallel Connection
- Resistors: (R_1 = 10 , \Omega), (R_2 = 20 , \Omega).
- The graph has nodes A-B connected by two edges.
- Parallel reduction gives: [ R_{\text{eq}} = \left( \frac{1}{R_1} + \frac{1}{R_2} \right)^{-1} = 6.67 , \Omega ]

Example 3: Nested Series and Parallel  
- Resistors: (R_1 = 10 , \Omega), (R_2 = 20 , \Omega), (R_3 = 30 , \Omega).
- (R_1) and (R_2) are in parallel: [ R_{\text{eq(parallel)}} = \left( \frac{1}{R_1} + \frac{1}{R_2} \right)^{-1} = 6.67 , \Omega ]
- (R_{\text{eq(parallel)}}) and (R_3) are in series: [ R_{\text{eq}} = R_{\text{eq(parallel)}} + R_3 = 36.67 , \Omega ]

---

## Algorithm Efficiency and Improvements

Efficiency:  
- Series Reduction: Runs in (O(n)), where (n) is the number of nodes.
- Parallel Reduction: Detecting cycles in a graph requires (O(E + V)), where (E) is the number of edges and (V) is the number of vertices.
- Overall complexity depends on the graph's structure and the number of iterations needed to simplify it.
  
Potential Improvements:
- Use Union-Find or Disjoint Set data structures to optimize detection and merging of connected components.
- Implement efficient cycle detection algorithms (e.g., DFS-based) for parallel reductions.
- Use libraries like NetworkX in Python for better graph manipulation and visualization.
