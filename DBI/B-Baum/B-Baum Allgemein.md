Ist eine selbst balancierende Baumstruktur zum speichern von Daten. Wird oft von Datenbanken verwendet.

Eine Node besitzt Paare aus Key, welche sortiert sind, und Data/Pointer auf eine andere Node und kann n+1 Children haben.

Ein B-Baum muss folgende Punkte erfüllen:
1. Jeder Pfad von Root zur untersten Node ist überall gleich lang
2. Einträge pro Node
	1. Root Node: 1 to 2n
	2. Normal Node: n to 2n
3. Alle Einträge einer Node sind sortiert
4. Alle nicht leaf Nodes haben n+1 Children
5.  K1 to Kn as keys of a node with n + 1 children, R0 to Rn refer to children
6. Sub-Nodes beinhalten nur kleinere Schlüssel

**Einfügen von Elementen**
Einträge werden bei Nodes eingefügt. Falls diese überläuft, so wird sie aufgespalten und die Parent Node bekommt einen neuen Eintrag.

![[b-baum add.png]]

**Entfernen von Elementen**
Wenn eine Node unter das minimum fällt, wird ein Eintrag aus einer Child-Node oder Nachbar-Node genommen oder mit einer Nachbar-Node verbunden.

**Suchen im B-Baum**
Schnell durch Baumstruktur

**Einfügen im B-Baum**
Aufwendig wenn reorganisiert werden muss

**Entfernen vom B-Baum**
Aufwendig wenn reorganisiert werden muss

### B+ Baum
Daten werden nur in Leaf-Nodes gespeichert. Die Leaf-Nodes stellen eine Linked List dar.

![[b+-baum.png]]

**Unterschiede**

![[b-baum differences.png]]

---

> [!cite]-
> ### Originale Quelle
A B-Tree is a self-balancing tree data structure that maintains sorted data and allows for efficient
insertion, deletion, and search operations. It is widely used in databases and file systems due to its ability
to minimize disk I/O operations by optimizing node sizes to fit into a single page of secondary storage. The
key features are:
 balanced tree with data sorted by key
 grows from leaves to the root
 multiple children per node (If a node contains n keys, it can have up to n + 1 children)
 node consists of entries, pairs of keys and corresponding data, and references to sub-trees
o references on leave nodes are empty
 node sizes are optimized with respect to secondary storage (reduce number of disk I/O operations)
o 1 node = 1 page
Summary
B-trees are designed for efficient data storage and retrieval in large-scale systems. Their balance, multi-
way branching, and disk I/O optimization make them well-suited for databases, file systems, and other
applications that involve large datasets stored on secondary storage devices.
A B-Tree of order k satisfies the following properties ...
>1. each path from root to any leave has the same length (B-tree is balanced)
>2. entries per node:
a. root node: number of entries is between 1 and 2k
b. any other node: number of entries is between k and 2k
c. all entries within the nodes are sorted
>3. 4. all non-leaf-nodes with n entries have n + 1 children
K1 to Kn as keys of a node with n + 1 children, R0 to Rn refer to children
a. R0 references the sub-tree with keys < K1
b. Ri references the sub-tree with Ki < keys < Ki+1
c. Rn references the sub-tree with keys > Kn
B-Tree and CRUD Operations
SEARCH INSERT DELETE
 number of pages that needs to
be searched is limited by height
of the tree
 split and merge procedure in
case of filled node may be
necessary from leaf to root
 in leaves just delete as long as
each node has enough
elements
 if number of entries is \<k after
> deletion, merging and/or
balancing necessary
Tutorial: B-Tree
> https://studyflix.de/informatik/b-baum-1435