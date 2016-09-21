# Network Visualization
To visualize the network with both positive and negative weighted edges.

#### Here are 3 types of network data:
1. "p&n" : Network with both positive and negative weighted edges.
2. "positive" : Network with only positive weighted edges.
3. "bipartite" : Bipartite (2-mode) network. (maybe not useful currently)

### What we want
Our problem is to develop a force-based layout algorithm to print out the "p&n" network. First, please get familiar with Gephi software and the layout algorithms it uses. In Gephi, import the graph format files ("positive.gml" and "p&n.graphml"), use ForceAtlas 2 to print out the networks and observe their difference (just like the two png pictures). We hope finally we could neatly print out the "p&n" network similar to the "positive" one.

### Some notes
1. The file format (gml/graphml) essentially doesn’t influence the graph content. I was just trying different file formats when I build the network.
2. Those gephi files are the results I already edited in Gephi. You can play with them to help you get familiar with the software.
3. One possible idea is to increase "gravity" to grip the nodes in the "p&n" network, but be careful --- this may cause the central nodes huddle together which makes it difficult to get useful information from the graph (bad visualization). Maybe you can try weighted gravity like {*k* * gravity}: long distance between two nodes with large *k*.
4. When you test your algorithm and code, it is better to test on some small dataset; otherwise iterative computations may take a long time. You can manually build small networks with different weights by python networkx or igraph package. 
5. *(Optional)* The original data which the network is constructed from actually is a bipartite (2-mode) graph. The link in the 2-mode graph is *reviewer* <---> *book* <---> *reviewer* <---> *book* <---> *reviewer* <---> …. Gephi can visualize the bipartite graph and also project it into one-mode graph (follow the Section 4 in this [tutorial]( http://www.martingrandjean.ch/gephi-introduction/)), but we will face the similar problem mentioned in note 3: the nodes distribute closely and uniformly in plane that loses a lot of useful information. Hence, if and only if it is too difficult to develop an algorithm to deal with negative weighted edges, we could try to visualize the network from this aspect. However, that would be **a totally new problem**!
