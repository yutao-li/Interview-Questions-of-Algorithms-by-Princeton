## Minimum Spanning Trees
1. Bottleneck minimum spanning tree. Given a connected edge-weighted graph, design an efficient algorithm to find a minimum bottleneck spanning tree. The bottleneck capacity of a spanning tree is the weights of its largest edge. A minimum bottleneck spanning tree is a spanning tree of minimum bottleneck capacity.

   mst is mbst(O(E) algorithm:Camerini's algorithm)
   
2. Is an edge in a MST. Given an edge-weighted graph G and an edge e, design a linear-time algorithm to determine whether e appears in some MST of G.  
   Note: Since your algorithm must take linear time in the worst case, you cannot afford to compute the MST itself.   

   consider the subgraph G' of G containing only those edges whose weight is strictly less than that of e,if it's connected, then yes, else no.
   
3. Minimum-weight feedback edge set. A feedback edge set of a graph is a subset of edges that contains at least one edge from every cycle in the graph. If the edges of a feedback edge set are removed, the resulting graph is acyclic. Given an edge-weighted graph, design an efficient algorithm to find a feedback edge set of minimum weight. Assume the edge weights are positive.

https://cstheory.stackexchange.com/questions/36222/minimum-weight-feedback-edge-set-in-undirected-graph-how-to-find-it-is-it-np

## Shortest Paths
1. Monotonic shortest path. Given an edge-weighted digraph G, design an ElogE algorithm to find a monotonic shortest path from s to every other vertex. A path is monotonic if the sequence of edge weights along the path are either strictly increasing or strictly decreasing.

   https://stackoverflow.com/questions/22876105/find-a-monotonic-shortest-path-in-a-graph-in-oe-logv

2. Second shortest path. Given an edge-weighted digraph and let P be a shortest path from vertex s to vertex t. Design an ElogV algorithm to find a path other than P from s to t that is as short as possible. Assume all of the edge weights are strictly positive.

   compute the shortest path distances from s to every vertex and the shortest path distances from every vertex to t.
   
3. Shortest path with one skippable edge. Given an edge-weighted digraph, design an ElogV algorithm to find a shortest path from s to t where you can change the weight of any one edge to zero. Assume the edge weights are nonnegative.   
   
   use a modified version of Dijkstra's algorithm, maintain an array of max weight of path from s to every vertex, each time we select a new edge and its end node, we choose the one with the shortest path given that we could delete the max weight from path.
   
 
