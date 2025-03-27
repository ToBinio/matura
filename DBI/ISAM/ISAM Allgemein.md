Steht für Index Sequential Access Method und wird verwendet um schnell den Speicherort von Daten anhand von Suchkriterien zu finden (Vergleichbar mit Index in einem Buch).

Wird verwendet, da nicht alle Daten im [[Primäre Speichermedien|primären Speicher]] gespeichert werden können, sondern auf den [[Sekundärer Speicher|sekundären Speicher]] ausgelagert werden müssen, welcher langsamer ist.

**Indices**
Indexes gibt es in allen verschiedenen Datenbanksystemen. Meistens mit B-Baum implementiert. 

Es gibt verschieden Arten von Indices:
- [[Primäre Indices|Primäre Indices (z.B. MongoDb)]]
	- clustered
- [[Sekundäre Indices|Sekundäre Indices (z.B. MongoDb)]]
- Clustered Indices
	- Definiert die physische Speicherreihenfolge
- Non-Clustered Indices
	- Pointer auf die realen Daten
- Unique Indices
	- Eine Kombination der Index-Spalten darf nur einmal vorkommen
- Compound Index
	- Mehrere Felder

**ISAM Struktur**

![[ISAM.png]]

In den Index-Pages (Links) werden Paare an Pointer zu Data-Pages (Rechts) und Schlüsselwert gespeichert. Jeder Schlüssel zeigt den kleinsten Wert einer Data-Page. Die Schlüssel sind sortiert.
In der Data-Page (Rechts) werden die Schlüssel in Verbindung mit den echten Daten gespeichert (Pointers). Alle Schlüssel einer Data-Page sind <= als der Index-Schlüssel. Es gibt ebenfalls einen Verweis auf die nächste Data-Page.

**Wie funktioniert ISAM** (+ Vorteile und Nachteile)
Es müssen nicht alle Daten durchgeschaut werden, um einen Eintrag zu finden. Daten sind sortiert und durch die Verlinkung der Data-Pages können Daten sortiert sequentiell gelesen werden. Werden oft Daten hinzugefügt oder entfernt kann dies viel Leistung beanspruchen, da die Struktur permanent geupdated werden muss.

**In ISAM einfügen**

Ist eine Data-Page voll, so kann ein Eintrag in eine andere Data-Page ausgelagert und der Index-Schlüssel geupdated werden oder die Data-Page muss aufgeteilt werden, wobei ein neuer Index-Schlüssel entsteht:

![[ISAM adding.png]]

![[ISAM adding 2.png]]

**ISAM löschen**
Sind weniger als Kapazität/2 Einträge in einer Data-Page, so muss ein Eintrag einer Nachbar Data-Page ausgeborgt werden. Falls das nicht möglich ist, dann müssen Data-Pages verbunden werden.

**ISAM Operationen**
- Suche
	- Schnell durch Index Struktur
- Hinzufügen
	- aufwendig, falls reorganisiert werden muss
- Löschen
	- Lässt leere Data-Pages zurück -> reorganisieren (aufwendig)

---

> [!cite]-
> ### Originale Quelle
 Index
 Sequential
 Access
 Method
An index in ISAM is a data structure that maps keys (or search criteria) to the location of the actual data. It
acts as a "table of contents" for quick data access.
9.1 Why Indexes?
 situation: large data sets must be searched for usually small portions of data
 naive approach: sequential access for all data
o primary storage cannot hold all data; secondary storage is
required.
o access gap factor to secondary storage is 105
o slow, in worst case all data must be read
 better approach: use efficient data structures that are easy to search, and which utilize characteristics
of secondary storage
9.2 Indexes in DBMS
 various concepts (primary, secondary indexes; clustered or non-clustered indexes, …)
 no standard in SQL like for CRUD operations
 implementation depends on concrete DBMS
 basis for many implementations in modern databases are B-Trees
 primary index
o defines the structure (clustered index) of data on the secondary storage.
o usually the primary key of the data records
 secondary index
o additional indexes to speed up searches for other criteria.
 e.g. for names in a register of city names...
o additional maintenance effort for manipulating operations decreases performance.
 clustered and non-clustered Indexes
o A clustered index determines the physical order of data in a table. A table can have only one
clustered index.
o A non-clustered index creates a separate structure from the data, holding pointers to the
actual data rows.
 unique and non-unique Indexes:
o Unique indexes enforce the uniqueness of values in the indexed column(s).
o Non-unique indexes allow duplicate values and are used for optimizing non-primary key
queries.
 Composite indexes
o An index built on multiple columns. Useful for queries that filter, or sort based on multiple
criteria
 key of an index
o search attribute(s)
o not to confuse with the key term in relational model!
When looking something up, you first use the thumb index to select a section where the word you're
searching for should be, if it exists at all, and then search for it there.
Index and Data
Indexes serve as a roadmap for locating data in database systems. They provide a structured mechanism
to quickly identify the storage location of a desired piece of data without having to scan the entire dataset.
 index
o sequence of alternate pointers to data pages (p) and key values (k) in ascending order,
ensuring efficient lookup and traversal.
o index pages follow each other on secondary storage.
 stored sequentially on secondary storage.
o kx ≠ ky ꓯ x ≠ y indicates that each key value (k) in the index is unique for each entry. This
property is essential for allowing fast, deterministic searches within the index.
 data
o data pages contain keys in ascending order and corresponding data. Each data page typically
contains multiple records, and these records are arranged so that the key values within each
page follow this sorted order.
o all keys on a data page of pi are equal or smaller than the index key ki. This ensures that any
records with key values greater than ki are in subsequent data pages.
o data pages are linked sequentially to support sequential read operations.
Summary of the Interaction Between Index and Data Pages
 The index provides an efficient lookup mechanism with pointers (p) to data pages containing the
actual data.
 Index pages are ordered and stored in ascending key order, supporting fast access through unique key
values (kx ≠ ky ꓯ x ≠ y).
 Data pages are also sorted by key values and linked sequentially, allowing for efficient retrieval and
sequential access patterns. This layout optimizes access to ordered data ranges and supports both
direct access via the index and linear traversals through data pages.
Overview of ISAM Structure
ISAM uses a combination of index pages and data pages to organize and access data efficiently. The index
pages contain key values that point to data pages, allowing the database system to find and retrieve data
in a structured, ordered manner.
>1. Index Pages (left side of the diagram):
 These pages are organized in a sequential manner, storing key values (‘ka’, ‘kb’, ..., ‘km’, ..., ‘kn’) that
act as pointers to corresponding data pages.
 Each index entry (‘ka’, ‘kb’, etc.) represents the starting key of a specific data page, allowing for fast
access to data blocks within a certain range.
 The keys in the index pages are in ascending order (ka < kb < ... < kn), which supports efficient
search operations, as the index can quickly narrow down the data page that contains the needed
record.
 The ISAM structure can span multiple index pages (‘pa’, ‘pb’, ..., ‘po’) depending on the size of the
dataset, which is useful when working with large amounts of data on secondary storage.
>2. Data Pages (right side of the diagram):
 Each data page contains actual data records associated with the index key. These records are also
organized in ascending order of keys within each data page.
 The index key ‘ki’ on a data page ‘pi’ represents the highest key in that page, meaning all records in
‘pi’ have keys less than or equal to ‘ki’
How ISAM Supports Efficient Data Access
 Direct Access Using Index Pages: By following the index, the system can directly access a specific data
page without scanning all records. For example, if a search key falls between ‘ka’ and ‘kb’, the index
directs the system to the data page corresponding to ‘kb’.
 Sequential Access via Data Page Links: The data pages are linked sequentially (right side of the
diagram), allowing efficient sequential read operations. This linking is advantageous for range queries,
where consecutive data records need to be accessed in order.
Characteristics and Limitations of ISAM
 Read-Optimized: ISAM is very efficient for read operations, as it provides both direct access (via the
index) and sequential access (via the links between data pages).
 Static Structure: ISAM is a static index structure, meaning that it is not well-suited for frequent
updates, insertions, or deletions. Adding new records or reordering existing records requires
rebalancing or reorganizing the index structure, which is costly.