# Useful Algorithms & Techniques for Coding Interviews in Java & Python

By [Andry Rakotonjanabelo](https://www.linkedin.com/in/andryart10/)

## *Arrays:*

**Converting Integer ArrayList to Array of integer:**

```java
int[] arr = list.stream().mapToInt(i -> i).toArray();
```



## *Graphs:*

**Turning an input array of edges into an adjacency list:**

Java:

```java
//edges is an array of int[2] where [a, b] means (node a) <-> (node b) 
//if it is a directional graph then [a, b] means (node a) -> (node b)
int nEdges = edges.length;
List<List<Integer>> adjList = new ArrayList<>(); //initializing the list for each node

for (int i = 0; i < n; ++i) {
    adjList.add(new ArrayList<>());
} 

//populating the adj list per node
for (int[] edge : edges) {
    adjList.get(edge[0]).add(edge[1]);
    adjList.get(edge[1]).add(edge[0]); //comment out list if DAG
}
```

Python:

```python
# edges is an array of int[2] where [a, b] means (node a) <-> (node b)
# if it is a directional graph then [a, b] means (node a) -> (node b)
nEdge = len(edges)
adjList = [[] for _ in range(n)]  # form adj list with edges

for edge in edges:
    adjList[edge[0]].append(edge[1])
    adjList[edge[1]].append(edge[0])
```

**Depth-First Search (in-progress...)**
