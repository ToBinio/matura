**Principal of Locality**
[[Sekundärer Speicher|RAM]] wird verwendet, um Daten, auf welche häufig zugegriffen wird, temporär zu speichern ([[Sekundärer Speicher|Sekundärer Speicher]] ist 10^5 mal langsamer), um die aufwändigen Disk I/O Operationen zu minimieren. Read, Write und Updates werden alle im [[Primäre Speichermedien|RAM]] durchgeführt.

![[DBMS.png]]

Buffer ([[Primäre Speichermedien|RAM]] ) kann voll werden, weshalb es verschiedene Methoden gibt, platz im Buffer für neuen Daten frei zu machen:
- LRU
	- Die **zugriff**-ältesten Daten werden entfernt
- FIFO
	- Der Wert der als erstes hinzugefügt wurde, wird entfernt

**Mapping of Relations**
Daten werden in Pages gespeichert. Diese haben eine fixe Größe von 4KB, 8KB, ... Hier werden die einzelnen Datensätze gespeichert. 

In Beziehungen wird die PageId und das Offset in der Page gespeichert, wodurch auf den Datensatz zugegriffen werden kann.

Ermöglicht es, Daten innerhalb der Page zu verschieben, ohne die Beziehung zu verändern.

![[Pages.png]]

![[Refactor Record.png]]

Möchte man einen Eintrag auf eine andere Page verschieben, so bleibt der Eintrag in der originalen Page, verweist jedoch auf den neuen Eintrag:

![[Changing page.png]]

Würde dieser verschobene Eintrag wieder auf eine neue Page verschoben werden, so wird nicht noch eine weitere Referenz erstellt, sonder die in der originalen Page geändert.

---

> [!cite]-
> ### Originale Quelle
> The concept of a database buffer refers to a portion of main memory (RAM) used to store frequently
accessed data pages from disk. This helps to improve performance by minimizing the need to perform
costly disk I/O operations.
 data operations are performed in main memory
o data needs to be read into database buffer
 data is kept in buffer due to principle of locality
o the very same data is accessed several times in a row
o avoids access time (factor 105!)
o set of pages is stored in buffer
o once the buffer is filled up, a replacement strategy necessary to allow new pages to be accessed
Data operations (such as reads, writes, or updates) are performed in main memory (RAM) because
operations on RAM are significantly faster than on secondary storage (e.g., hard disks or SSDs).
Before any operation can be performed on data, it must first be read into the database buffer from disk.
This process is called buffering, and it ensures that the data is available in memory for quick access.
The principle of locality refers to the tendency of programs to access the same set of data multiple times
within short intervals. To leverage this principle, the DBMS keeps data that is frequently accessed in the
database buffer. This helps reduce the need to repeatedly fetch the same data from disk, thereby reducing
the expensive disk I/O operations.
The database buffer is organized as a set of pages that are temporarily stored in memory. Pages are
typically the unit of data transfer between disk and main memory (a page could be 4 KB, 8 KB, etc.,
depending on the DBMS). A page contains a block of data, and multiple pages are loaded into the buffer for
operations.
Since memory is a limited resource, the database buffer has finite space. Once the buffer is filled up, there
needs to be a strategy to replace some of the existing pages in the buffer to make space for new ones.
This is where a buffer replacement strategy comes into play. Common strategies include:
 LRU (Least Recently Used): The page that hasn't been used for the longest time is replaced.
 FIFO (First In, First Out): The oldest page is replaced.
 …
These strategies aim to balance the system's performance by determining which pages to evict when new
pages need to be brought into the buffer.
Mapping of Relations onto Pages
 goal
o efficient storage of data (reduce access
time, make use of locality)
 intuitive approach
o relations are mapped to files which span
multiple pages on the secondary storage
o a data record entirely fits on one page
A tuple is essentially a row in a database table, representing a single record. For example, in a table called
Customers, each tuple could represent one customer, with columns for fields such as name, email, and
phone number.
The Tuple ID is a unique reference to a specific tuple within the table, and it provides the DBMS with all the
information it needs to locate the row in physical storage (on disk or in memory). The Tuple ID typically
consists of the following components, though it may vary depending on the database system:
> 1. 2. Page Number: Identifies the page in which the tuple is stored. In a DBMS, data is stored in pages on
> disk (usually 4 KB, 8 KB, etc.), and the page number helps to pinpoint the exact page where the tuple
> resides.
> Slot Number (or Offset): Within a page, multiple tuples can be stored. The slot number indicates > the
> specific position or offset within the page where the tuple is located.
> This two-part structure allows the DBMS to quickly navigate to the correct page and the correct location
> within that page to access the desired tuple.
> Example for Use Case:
> When an index is built on a table, the index typically stores key values and the corresponding Tuple IDs.
> This allows for rapid lookups. For example, if a query searches for a specific value in an indexed column,
> the DBMS can use the index to find the associated Tuple ID, then directly fetch the tuple.