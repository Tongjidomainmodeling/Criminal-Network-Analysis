# Criminal-Network-Analysis
This repository is to support our paper titled
["Research Notes: A Proof of Concept Study for Criminal Network Analysis with Interactive Strategies(116)"](https://tongjidomainmodeling.github.io/Criminal-Network-analysis/papers/ijseke_zhou.pdf)
revised at IJSEKE 2016.

> This paper was submitted to IJSEKE Special Issue on Selected papers from SEKE2016 as research notes.
> Due to that reseach notes are limited to ten pages including figures, references
and appendices, so we here provide some details that can't be fully shown in the paper.
> We hope this can make our readers more easy to understand the process proposed in our paper and the case study
with a real world criminal dataset.

### IJSEKE revision: changes list
    1. change1
    2. change2
    3. change3
    4. change4


### Dataset Introduction and Network Construction
    1. change1
    2. change2
    3. change3
    4. change4

### Experiment Results Interpretation
    1. change1
    2. change2
    3. change3
    4. change4

### Metric Design
In order to exactly capture the influence of core members and its roles playing in the criminal organizations, we introduce a series of measures from the domain of Social Network Analysis and interpret them in the context of our certain CN. After calculating these metrics, we render the network view with different color intensity and size based upon the metric value of each entity and spotlight certain nodes.

***A.Network Measures Reinterpretation in CNs***
**Degree centrality** measures the activity and influence by calculating the number of direct relations a node has. It is convinced that a call number with a high degree could be regarded as a hub which act as an import information channel in the communication network and a node with high activity. It is defined as:
\begin{equation*}
{Dgr}_i = \frac{{d}_i} {S-1} = \frac{\sum\limits_{i\in M}m_{ij}} {S-1}
\end{equation*}
where $d_i$ is the directly links to other call numbers of a call number $i$, and $m_{ij}$ is the $ij_{th}$ element of the adjacency matrix $M$ and $S$ is the sum of the whole call numbers. $S-1$ is the normalization factor.

**Betweenness centrality** is another indicator to measure node’s centrality which equals the number of the shortest paths from all nodes to all other nodes which pass through that node. In the context of CN, a call number with high betweenness can be regarded as broker of messages, indicating the great importance of this call number in the information transfer. Most importantly, this kind of call numbers usually connects two or more densely call number clusters, removal of them might lead to the destabilization, abruption and even destroy of the CNs.
The betweenness centrality of a call number $(i)$ is redefined as:
\begin{equation*}
{Btw}_i = \frac{\sum\limits_{ j<k\in N}\frac{p_{jk}(i)}{p_{jk}}}    {(S-1)(S-2)}
\end{equation*}
where $p_{jk}$ is the total number of the shortest paths from call number $j$ to call number $k$ and the $p_{jk}(i)$ is the number of those paths that pass through call number $i$, the $(S-1)(S-2)$ is the normalization factor.

**Closeness centrality** is the reciprocal of the sum of the shortest paths between that node and all other nodes in the network. In the analysis of our CN, a high closeness indicates this call number can reach majority of the other nodes easier and faster. The closeness centrality of a call number $(i)$ is redefined by the expression:
\begin{equation*}
{Clsn}_i = (H_i)^{-1} = \frac {S-1} {\sum\limits_{j\in N}d_(i,j)}
\end{equation*}
where $d_(i,j) $ is the distance between node $i$ with node $j$, $H_i$ is the normalized distance.

**Eigenvector centrality** defines another centrality with the consideration of the importance of their neighbours. In the framework of our CN, a call number with high eigenvector centrality means that this call number can reach a group of other call numbers easily and quickly. The eigenvector centrality of a node $(i)$ is redefined as:
\begin{equation*}
{Eign}_i = \frac{1}{\alpha  } \sum\limits_{j\in L(i)}m_j = \frac{1}{\alpha} \sum\limits_{j\in N} a_{ij}x_j
\end{equation*}
where $L(i)$ is the direct link set of call number $i$, $\alpha$ is a constant, and $a_{ij}$ is the $ij_{th}$ element of the adjacency matrix $M$.

**Clustering coefficient** is a measure of the degree to the aggregation of nodes in a graph. In the context of our CN, a call number with high clustering coefficient means a high likelihood of that the direct links of the given call number can reach each other. It is redefined as:
\begin{equation*}
{Clst}_i = \frac{ |{e_{jk}}|  }   {l_i(l_i-1)}
\end{equation*}
where $e_{jk}$ is the link existing in the neighbours of call number $i$ and $l_i$ is the number of direct links of the call number $i$.

**PageRank** is a variant of the eigenvector centrality measure in some degree. Our work employ this measure to the importance of a certain call number globally.
It is redefined as:
\begin{equation*}
Page(i) = (1-f) + f * \sum\limits_{j \in H(i)}\frac{P_i(j)}{L_j}
\end{equation*}
where $H(i)$ are the set of call numbers directly linking to the call number $i$ , $L_j$ is the number of outgoing links in $j$ and $f$ is the damping factor.


