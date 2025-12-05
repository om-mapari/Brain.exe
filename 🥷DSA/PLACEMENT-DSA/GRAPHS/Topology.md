AM

A graph of V vertices represents a ==Ring topology== if it satisfies the following three conditions:
1.  Number of vertices \>= 3.
2.  No of edges = No of Vertices.
3.  All vertices should have degree**2**.

----------------------------------------------------------------

A graph of V vertices represents a ==bus topology== if it satisfies the following two conditions:
1.  Each node except the starting end ending ones has degree 2 while the starting and ending have degree 1.
2.  No of edges = No of Vertices – 1.

-----------------------------------------------------------

A graph of V vertices represents a ==star topology== if it satisfies the following three conditions:
1.  One node (also called the central node) has degree V – 1.
2.  All nodes except the central node have degree 1.
3.  No of edges = No of Vertices – 1.

**bool** checkStarTopologyUtil(vector\<**int**\> adj\[\], **int** V, **int** E)

{

**if** (E != (V - 1)) **return** **false**;

**if** (V == 1) return true;

**int**\* vertexDegree = **new** **int**\[V + 1\];

**memset**(vertexDegree, 0, **sizeof** vertexDegree);

// calculate the degree of each vertex

**for** (**int** i = 1; i \<= V; i++) {

**for** (**auto** v : adj\[i\]) {

vertexDegree\[v\]++;

}

}

**int** countCentralNodes = 0, centralNode = 0;

**for** (**int** i = 1; i \<= V; i++) {

**if** (vertexDegree\[i\] == (V - 1)) {

countCentralNodes++;

// Store the index of the central node

centralNode = i;

}

}

// there should be only one central node

// in the star topology

**if** (countCentralNodes != 1)

**return** **false**;

**for** (**int** i = 1; i \<= V; i++) {

// except for the central node

// check if all other nodes have

// degree 1, if not return false

**if** (i == centralNode)

**continue**;

**if** (vertexDegree\[i\] != 1) {

**return** **false**;

}

}

// if all three necessary

// conditions as discussed,

// satisfy return true

**return** **true**;

}

