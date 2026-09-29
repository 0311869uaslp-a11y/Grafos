# Graph Theory & Algorithms

Repository containing exercises, implementations, and practical work developed during my academic training in **Graph Theory** as part of the **Data Science & Artificial Intelligence program at Universidad Autónoma de San Luis Potosí (UASLP)**.

The coursework explores the mathematical and computational representation of problems using graphs, including **shortest-path algorithms, minimum spanning trees, graph coloring, planar graphs, and Eulerian and Hamiltonian paths and cycles**.

The repository includes work with classical algorithms such as **Dijkstra, Floyd-Warshall, Prim, and Kruskal**, providing foundations for optimization, network analysis, routing, resource allocation, and graph-based computational problems.

---

## Course Overview

Graph Theory provides a mathematical framework for representing systems composed of entities and relationships.

A graph can be represented as:

```text
G = (V, E)
```

where:

```text
V = set of vertices
E = set of edges
```

Conceptually:

```text
        A
       / \
      /   \
     B-----C
      \   /
       \ /
        D
```

The vertices represent entities, while the edges describe relationships or connections between them.

This simple abstraction can represent many real-world systems, including:

- Communication networks
- Transportation systems
- Social networks
- Computer networks
- Electrical networks
- Dependency networks
- Resource-allocation problems

---

# Topics Covered

The repository includes practical work related to:

- Graph fundamentals
- Vertices and edges
- Directed and undirected graphs
- Weighted graphs
- Graph representation
- Paths and cycles
- Connectivity
- Vertex degree
- Shortest paths
- Dijkstra's algorithm
- Floyd-Warshall algorithm
- Minimum spanning trees
- Prim's algorithm
- Kruskal's algorithm
- Eulerian paths and circuits
- Hamiltonian paths and cycles
- Planar graphs
- Graph coloring
- Graph-based optimization

---

# Graph Fundamentals

A graph consists of a set of vertices connected by edges.

```text
Vertices:

A   B   C   D

Edges:

A --- B
|     |
|     |
C --- D
```

The structure of a graph depends on the problem being represented.

Graphs can differ according to properties such as:

```text
Graph
 |
 +---- Directed / Undirected
 |
 +---- Weighted / Unweighted
 |
 +---- Connected / Disconnected
 |
 +---- Cyclic / Acyclic
```

Understanding these properties is essential before selecting an algorithm to analyze the graph.

---

# Weighted Graphs

In a weighted graph, each edge contains an associated numerical value.

For example:

```text
        5
   A -------- B
   |          |
  2|          |3
   |          |
   C -------- D
        4
```

The weights can represent quantities such as:

- Distance
- Cost
- Time
- Latency
- Energy consumption
- Network capacity

Weighted graphs are particularly important in optimization problems.

---

# Paths and Cycles

A **path** is a sequence of vertices connected through edges.

```text
A -> B -> C -> D
```

A **cycle** occurs when a path eventually returns to its starting vertex.

```text
A -> B -> C -> D
^              |
|______________|
```

Paths and cycles are fundamental concepts behind routing, connectivity, Eulerian problems, Hamiltonian problems, and shortest-path algorithms.

---

# Connectivity

Connectivity describes whether vertices can be reached from one another.

```text
Connected Graph

A ----- B
|       |
C ----- D
```

Compared with:

```text
Disconnected Graph

A ----- B

C ----- D
```

Connectivity analysis is relevant when determining whether information, resources, or routes can propagate through a network.

---

# Shortest-Path Problems

One of the main problems studied in Graph Theory is finding the minimum-cost path between vertices.

Given a weighted graph:

```text
        4
   A -------- B
   |          |
  2|          |1
   |          |
   C -------- D
        3
```

the objective is to determine which sequence of edges minimizes the total accumulated cost.

Two classical algorithms studied in the coursework are:

- Dijkstra
- Floyd-Warshall

---

# Dijkstra's Algorithm

**Dijkstra's algorithm** finds shortest paths from a source vertex to the other reachable vertices in a weighted graph with non-negative edge weights.

The basic process can be represented as:

```text
Select Source
     |
     v
Initialize Distances
     |
     v
Select Closest Unvisited Vertex
     |
     v
Evaluate Neighbors
     |
     v
Update Distances
     |
     v
Mark Vertex as Visited
     |
     v
Repeat
```

Conceptually:

```text
Source
  |
  v
Current Shortest Distance
  |
  v
Explore Adjacent Vertices
  |
  v
Relax Edges
  |
  v
Update Best Known Paths
```

---

## Applications of Dijkstra

Shortest-path algorithms can be applied to problems involving:

- Transportation routes
- Computer-network routing
- Navigation
- Communication networks
- Logistics
- Cost minimization

For an Electronics and Telecommunications context, a graph can represent:

```text
Router ---- Router ---- Router
   |                       |
   |                       |
Router ---------------- Router
```

where edge weights could represent latency, distance, or another routing metric.

---

# Floyd-Warshall Algorithm

The **Floyd-Warshall algorithm** addresses a different shortest-path problem.

Instead of finding paths from a single source, it computes shortest paths between **all pairs of vertices**.

```text
              Graph
                |
                v
         Distance Matrix
                |
                v
       Intermediate Vertices
                |
                v
      Update Shortest Paths
                |
                v
     All-Pairs Shortest Paths
```

The result can be represented as a matrix:

```text
      A    B    C    D

A     0    4    2    5
B     4    0    3    1
C     2    3    0    3
D     5    1    3    0
```

This makes Floyd-Warshall useful when shortest-path information is required for every pair of vertices in a network.

---

# Dijkstra vs. Floyd-Warshall

The coursework provides exposure to two different shortest-path strategies.

| Dijkstra | Floyd-Warshall |
|---|---|
| Single-source shortest paths | All-pairs shortest paths |
| Starts from one vertex | Considers every pair of vertices |
| Explores reachable nodes | Builds a complete distance solution |
| Useful for routing from a source | Useful for global network analysis |

Understanding the problem structure is important when deciding which algorithm is appropriate.

---

# Minimum Spanning Trees

Another major problem studied in the repository is the **Minimum Spanning Tree (MST)**.

Given a connected weighted graph, the objective is to select a subset of edges that:

1. Connects all vertices.
2. Contains no cycles.
3. Minimizes the total edge weight.

```text
Original Weighted Graph
          |
          v
 Select Necessary Connections
          |
          v
    Avoid Cycles
          |
          v
 Minimize Total Weight
          |
          v
 Minimum Spanning Tree
```

Two classical algorithms are explored:

- Prim
- Kruskal

---

# Prim's Algorithm

**Prim's algorithm** constructs a Minimum Spanning Tree by progressively expanding a connected set of vertices.

The process can be represented as:

```text
Select Starting Vertex
        |
        v
Find Minimum Edge
        |
        v
Add New Vertex
        |
        v
Find Minimum Connecting Edge
        |
        v
Expand Tree
        |
        v
Repeat Until All Vertices Are Connected
```

The algorithm maintains a connected structure throughout its execution.

---

## Prim Example

Conceptually:

```text
Step 1

A

Step 2

A ---- B

Step 3

A ---- B
|
C

Step 4

A ---- B
|      |
C      D
```

At each step, the lowest-cost edge that connects the current tree with a new vertex is selected.

---

# Kruskal's Algorithm

**Kruskal's algorithm** solves the same Minimum Spanning Tree problem using a different strategy.

Instead of starting from one vertex, the algorithm considers edges globally.

```text
Weighted Graph
      |
      v
Sort Edges by Weight
      |
      v
Select Lowest-Cost Edge
      |
      v
Check for Cycle
      |
      +------ Cycle ------> Reject
      |
      +------ No Cycle ---> Add
      |
      v
Repeat
      |
      v
Minimum Spanning Tree
```

Edges are added in increasing order of weight as long as they do not create a cycle.

---

# Prim vs. Kruskal

Both algorithms solve the Minimum Spanning Tree problem but follow different strategies.

| Prim | Kruskal |
|---|---|
| Starts from a vertex | Starts from sorted edges |
| Expands one connected tree | Builds components progressively |
| Selects edges connected to the current tree | Selects globally low-cost edges |
| Avoids cycles while expanding | Rejects edges that create cycles |
| Produces an MST | Produces an MST |

Studying both algorithms demonstrates how the same optimization problem can be approached using different algorithmic strategies.

---

# Eulerian Paths and Circuits

An **Eulerian path** traverses every edge of a graph exactly once.

```text
Objective:

Visit every EDGE exactly once.
```

An **Eulerian circuit** satisfies the same condition but also returns to the starting vertex.

```text
Start
  |
  v
Traverse Every Edge
  |
  v
Return to Start
```

The key idea is therefore:

```text
Euler -> EDGES
```

Eulerian problems are useful when the objective involves traversing every connection in a network.

---

## Eulerian Analysis

These exercises involve concepts such as:

- Vertex degree
- Graph connectivity
- Edge traversal
- Eulerian paths
- Eulerian circuits

A typical question is:

```text
Can every edge of this graph
be traversed exactly once?
```

This type of problem has direct connections to route-planning scenarios where every link or road must be visited.

---

# Hamiltonian Paths and Cycles

Hamiltonian problems focus on vertices rather than edges.

A **Hamiltonian path** visits every vertex exactly once.

```text
Objective:

Visit every VERTEX exactly once.
```

A **Hamiltonian cycle** additionally returns to the starting vertex.

The key distinction is:

```text
Euler
  |
  v
Every Edge


Hamilton
  |
  v
Every Vertex
```

This distinction is fundamental in Graph Theory.

---

# Euler vs. Hamilton

| Euler | Hamilton |
|---|---|
| Focuses on edges | Focuses on vertices |
| Traverses every edge | Visits every vertex |
| Eulerian path | Hamiltonian path |
| Eulerian circuit | Hamiltonian cycle |

Although the problems may look similar visually, their mathematical objectives are different.

---

# Planar Graphs

The repository also covers **planar graphs**.

A graph is planar when it can be represented on a plane without edges crossing except at their vertices.

Conceptually:

```text
Planar

A ------ B
|        |
|        |
D ------ C
```

The important property is not necessarily whether one particular drawing contains crossings, but whether a crossing-free representation exists.

Planarity introduces relationships between:

- Vertices
- Edges
- Faces or regions
- Geometric representations of graphs

---

# Graph Coloring

The coursework includes **graph-coloring problems**.

The objective of vertex coloring is to assign colors to vertices so that adjacent vertices do not share the same color.

Mathematically, for every edge:

```text
(u, v) ∈ E
```

the coloring should satisfy:

```text
color(u) != color(v)
```

Conceptually:

```text
        [Red]
        /   \
       /     \
   [Blue]---[Green]
       \     /
        \   /
       [Red]
```

The objective is often to minimize the number of colors required while satisfying the adjacency constraints.

---

# Applications of Graph Coloring

Graph coloring can represent several resource-allocation problems.

Examples include:

- Scheduling
- Frequency assignment
- Resource allocation
- Timetable generation
- Conflict resolution

For example, if two tasks cannot use the same resource simultaneously:

```text
Task A ----- Task B

Different colors
=
Different resources / time slots
```

This transforms a scheduling constraint into a graph-coloring problem.

---

# Graph Algorithms Overview

The main algorithms and problems explored in the repository can be organized as:

```text
                    Graph Theory
                         |
       +-----------------+-----------------+
       |                 |                 |
       v                 v                 v
 Shortest Paths      Spanning Trees   Graph Properties
       |                 |                 |
   +---+---+         +---+---+        +----+---------+
   |       |         |       |        |    |         |
   v       v         v       v        v    v         v
Dijkstra Floyd      Prim  Kruskal   Euler Hamilton Coloring
                                                   |
                                                   v
                                               Planarity
```

This provides exposure to several fundamental classes of graph problems.

---

# Graphs and Optimization

Many graph problems can be interpreted as optimization problems.

### Shortest Path

```text
Minimize:
Total path cost
```

### Minimum Spanning Tree

```text
Minimize:
Total connection cost

Subject to:
All vertices connected
No cycles
```

### Graph Coloring

```text
Minimize:
Number of colors

Subject to:
Adjacent vertices must use different colors
```

These problems provide foundations for more advanced optimization and algorithm-design techniques.

---

# Applications in Computer Networks

Graph Theory is particularly relevant to my background in **Electronics, Telecommunications, and Computer Networks**.

A communication network can naturally be modeled as:

```text
                  Router
                 /      \
                /        \
            Router ------ Router
              |             |
              |             |
           Gateway ------- Node
```

where:

```text
Vertices -> routers, gateways, devices
Edges    -> communication links
Weights  -> distance, latency, cost, capacity
```

Graph algorithms can then support tasks such as:

- Routing
- Network design
- Connectivity analysis
- Infrastructure optimization
- Resource allocation

---

# Applications in Data Science

Graphs also provide a useful data representation when relationships between entities are as important as the entities themselves.

```text
Traditional Dataset

Rows
 |
 v
Independent Observations


Graph Dataset

Entities
 |
 v
Vertices
 |
 v
Relationships
 |
 v
Edges
```

Graph-based representations appear in areas such as:

- Social-network analysis
- Recommendation systems
- Communication networks
- Transportation networks
- Knowledge graphs
- Fraud and relationship analysis
- Network optimization

The coursework therefore provides mathematical and algorithmic foundations relevant to graph-based Data Science.

---

# Relationship with Artificial Intelligence

Graph algorithms are also fundamental to many Artificial Intelligence problems.

```text
Problem
   |
   v
State Representation
   |
   v
Graph
   |
   v
Search / Optimization
   |
   v
Solution
```

Graph Theory complements other areas of my Artificial Intelligence training, including:

- Machine Learning
- Data Mining
- Deep Learning
- Symbolic AI
- Optimization

---

# Skills Developed

Through the exercises in this repository, the course develops practical knowledge in:

- Graph Theory
- Graph representation
- Weighted graphs
- Connectivity
- Paths and cycles
- Shortest-path algorithms
- Dijkstra's algorithm
- Floyd-Warshall algorithm
- Minimum spanning trees
- Prim's algorithm
- Kruskal's algorithm
- Eulerian paths and circuits
- Hamiltonian paths and cycles
- Planar graphs
- Graph coloring
- Algorithmic problem solving
- Combinatorial optimization
- Network modeling

---

# Academic Context

This repository contains coursework developed as part of my specialized training in:

**Data Science & Artificial Intelligence**  
**Universidad Autónoma de San Luis Potosí (UASLP)**  
San Luis Potosí, Mexico

The complete specialized training comprised **195 hours** and included Machine Learning, Artificial Intelligence, Data Mining, Deep Learning, Graph Theory, and practical computational methods.

---

# Relationship with My Data Science Training

The Graph Theory coursework complements the other areas represented in my academic repositories:

```text
                Data Science & AI
                       |
       +---------------+---------------+
       |               |               |
       v               v               v
Machine Learning   Data Mining     Deep Learning
       |               |               |
       +---------------+---------------+
                       |
                       v
                  Graph Theory
                       |
             +---------+---------+
             |         |         |
             v         v         v
          Paths       MST     Coloring
             |         |         |
             +---------+---------+
                       |
                       v
                Optimization &
                Network Analysis
```

Related coursework includes:

- Artificial Intelligence
- Data Mining
- Deep Learning
- NoSQL Databases
- Statistical analysis
- Python-based scientific computing

---

# Repository Purpose

The purpose of this repository is to preserve and document the practical exercises completed during my academic training in Graph Theory.

The repository demonstrates a progression from fundamental graph representations to classical optimization algorithms:

```text
Graph Fundamentals
       |
       v
Vertices & Edges
       |
       v
Paths & Connectivity
       |
       +----------------------+
       |                      |
       v                      v
Shortest Paths         Spanning Trees
       |                      |
   +---+---+              +---+---+
   |       |              |       |
   v       v              v       v
Dijkstra Floyd          Prim   Kruskal
       |                      |
       +----------+-----------+
                  |
                  v
          Structural Problems
                  |
        +---------+---------+
        |         |         |
        v         v         v
      Euler    Hamilton   Planarity
                            |
                            v
                         Coloring
```

Together, these exercises provide foundations in **graph modeling, classical graph algorithms, network analysis, and combinatorial optimization**.

---

# Author

**José Luis Romero Vázquez**

Electronics Engineer and Data Scientist with international graduate education in Electronic Engineering, Telecommunications, and Computer Networks, with applied experience in Machine Learning, time-series forecasting, IoT analytics, network optimization, research, and software development.

**LinkedIn:**  
https://www.linkedin.com/in/jose-luis-romero-vazquez-486569209

**GitHub:**  
https://github.com/0311869uaslp-a11y
