# Segmentation-of-Medical-Image
Use Graph-Cut and Min-Cut/Max-Flow Algorithms for Energy Minimization to segment medical image

#### About the algorithm:
The max-flow min-cut problem is represented in a directed acyclic graph(DAG). Each edge has a maximum capacity, which the flow cannot exceed. There are source node s and sink node t. The node s has no incoming edges, and the node t has no outgoing edges. All other nodes are internal nodes, where the incoming flow must equal to the outgoing flow. The goal of the algorithm is to find the maximum possible flow value from s to t.

#### The algorithm:
```
For each edge e in G
  f(e) ⟸ 0
While ∃ s-t path in the residual graph G'
  P ⟸ s-t path in G'
  For each e in P
    If e=(u,v) is a forward edge
      Increase f(e) by the min residual capacity on P
    Else
      e ⟸ (v,u)
      Decrease f(e) by the min residual capacity on P
  f ⟸ updated f'
  G' ⟸ updated G''
End While
Return f
```
