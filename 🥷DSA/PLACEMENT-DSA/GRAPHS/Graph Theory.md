AM
Tree Vs Graph
- Graph With no cycle is tree
- Tree edges = n - 1 Graph edges \> n - 1
- Every Tree is graph

<table>
<colgroup>
<col style="width: 42%" />
<col style="width: 57%" />
</colgroup>
<thead>
<tr class="header">
<th>Tree</th>
<th>Graph</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>exactly n - 1 edges</td>
<td>max edges: n to n*(n-1)/2</td>
</tr>
<tr class="even">
<td>no cycle</td>
<td>cycle present</td>
</tr>
<tr class="odd">
<td>directed -&gt;</td>
<td>undirected, directed</td>
</tr>
<tr class="even">
<td><p>class node {</p>
<p>int data;</p>
<blockquote>
<p>node* left;</p>
<p>node* right;</p>
</blockquote>
<p>}</p></td>
<td><p>vector&lt;vector&lt;int&gt;&gt; adj;<br />
vector&lt;int&gt; adj[];<br />
<br />
unordered_map&lt;int,</p>
<p>vector&lt; pair&lt;int,int&gt; &gt; &gt; um;</p></td>
</tr>
</tbody>
</table>

Example
Tree = Folder stracture
Graph = Facebook Friend

![image1](../../resources/f83a82931d1c4b13a64b9c96618e6990.png)

--------------------------------------------------------------
| Graph        | Undirected          | directed                       |
|--------------|---------------------|--------------------------------|
| max Edge (e) | n\*(n-1)/2          | n\*(n-1)                       |
| sum of edge  | 2\*e                | sum(in) = sum(out) = e         |
| degree       | degree for directed | in & out degree for undirected |

--------------------------------------------------------------
Types of Graph ( Cyclic Acyclic Weighted )

![image2](../../resources/0d671ba14c024330a69f6b075843f6ee.png)
--------------------------------------------------------------
Connected component -
If we can reach to any node from any other node then they are component

--------------------------------------------------------------
Representation of this Graph :
![image3](../../resources/7c424f69c620455f8800c6dfd6e46e6e.png)

<table>
<colgroup>
<col style="width: 51%" />
<col style="width: 48%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Adjecency matrix</p>
<p>graph[n+1][n+1] // n = no. of vertex</p>
<p>![image4](../../resources/3a39664677f243c9b0914a3408d66989.jpeg)</p>
<p></p>
<p>use hastable if vertex name in graph</p>
<p>= abc, bcd</p></th>
<th><p>![image5](../../resources/8341586d450e41ac8518cad5ec830356.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Adjecency List</p>
<p>vector&lt;int&gt; adj[n+1]</p>
<p>vector&lt;vector&lt;int&gt;&gt; adj(n+1);</p>
<p></p>
<p>vector&lt;pair&lt;int,int&gt;&gt; graph[n+1]</p>
<p>vertex,weight</p>
<p>![image6](../../resources/0d7328ac2d28434abd037ed7c6164e6e.png)</p>
<p></p></td>
<td><p>Weight wt</p>
<p>![image7](../../resources/69c17c6daae24206acd6490b7d227681.png)</p>
<p></p>
<p></p>
<p></p></td>
</tr>
</tbody>
</table>

<table>
<colgroup>
<col style="width: 27%" />
<col style="width: 19%" />
<col style="width: 52%" />
</colgroup>
<thead>
<tr class="header">
<th>Time Complexity</th>
<th>Matrix</th>
<th><p>List</p>
<p>vector&lt;pair&lt;int,int&gt;&gt; graph[n+1]</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>SC</td>
<td>V*V</td>
<td>V+E</td>
</tr>
<tr class="even">
<td>TC check edge</td>
<td>1</td>
<td>V i.e E more accurate but say V</td>
</tr>
<tr class="odd">
<td>TC check vertex adjecent to u</td>
<td>V</td>
<td>V i.e E<br />
</td>
</tr>
<tr class="even">
<td>Remove</td>
<td>1</td>
<td>V</td>
</tr>
</tbody>
</table>

![image8](../../resources/e8e5259b0aab4bf7bfde36e765a48cd0.png)

\> m = edges = 2\*e (undireced)

![image9](../../resources/b04a887209ee4158bd96a8c423ea1f8b.png)

![image10](../../resources/2b2f504b86ce4a0ab3125bdad516d560.png)

1.  node = u,v
edge = {u,v} = pair of nodes

2.  undirected graph :

![image11](../../resources/b0de192ce60e4f7fa306fa2da30ebfb3.png)

directed graph :

![image12](../../resources/00b30910ac75411fa32bb31edbbfa1b7.png)

3.  connected component : on every vertex we can go to another vertiex

3 connected comp

![image13](../../resources/26355567739241ee8d194303c147cb21.png)

in directed graph there is strongly

strongly connected comp

![image14](../../resources/320c2a6fc8e44e28843953906ab944b8.png)

![image15](../../resources/bc48f8592e5e46af8781ee814594984a.jpeg)

