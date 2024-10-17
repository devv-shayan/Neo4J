Graph Characteristics:
Directed vs. Undirected Graphs:

Undirected: Think of it like marriage: If Ali is married to Ayesha, it's mutual—the relationship goes both ways. So, if you know Ali is married to Ayesha, Ayesha is also married to Ali.
Directed: Now, consider love: Ali might love Ayesha more than she loves him. This creates a one-way relationship, where the direction adds meaning.
Weighted vs. Unweighted Graphs:

Weighted: Imagine traveling between cities like Lahore and Islamabad. Each road might have a distance or time factor. If you care about the fastest route, then the graph is "weighted" by the travel time or distance. You can calculate the shortest path based on these weights—like finding the quickest way from Lahore to Islamabad, or considering cost if sending a package between cities.
Unweighted: All roads are equal, with no extra data like time or cost affecting decisions.
2. Graph Traversal:
Finding Answers through Traversal:

Let’s say you want to find the shortest path between Karachi and Peshawar. The graph needs to be traversed—meaning, follow the roads (relationships) between the cities (nodes).
Different algorithms, such as Dijkstra’s or A*, consider weights (like distance or cost) to help you figure out the best route.
Performance in Traversal:

Cypher (Neo4j’s query language) is optimized to traverse nodes without rechecking the same relationship, making it faster to find answers.
