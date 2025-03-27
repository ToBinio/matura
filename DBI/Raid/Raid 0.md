Raid 0 verwendet das Prinzip des Stripings. Hier werden Daten in Blöcke aufgeteilt und getrennt auf mehreren Festplatten gespeichert.

Raid 0 liefert keine Fehlertoleranz. Die Fehlertoleranz wird sogar schlechter, da jede zusätzliche Festplatte ein neues Risiko darstellt. Jedoch wird die Performance verbessert, da gleichzeitig auf mehrere Festplattem geschrieben oder gelesen werden kann.

![RAID 0](https://www.easeus.de/images/en/screenshot/partition-manager/raid-0.png)

---

> [!cite]-
> ### Originale Quelle
> RAID 0 is a disk array configuration that utilizes striping to distribute data across multiple drives. Here's a
breakdown of how it works and its implications on performance, fault tolerance, and data access:
Striping
In RAID 0, data is split and distributed block-by-block across
all the drives in the array. This means that instead of writing a
whole file to a single drive, the file is broken into smaller blocks
and spread sequentially across the drives. When you have two
drives in RAID 0, each drive receives alternating blocks of data.
For instance, block A might go to Drive 1, block B to Drive 2,
block C to Drive 1, and so on.
Fault Tolerance
RAID 0 offers no fault tolerance. In fact, the fault tolerance decreases as you add more drives to the array.
With RAID 0, if any one drive fails, all data in the array is lost, as there’s no redundancy or parity to recover
lost data. So, while adding drives improves performance, it also increases the risk of data loss.
Datenbanken und Informationssysteme Seite 44
HÖHERE TECHNISCHE BUNDESLEHRANSTALT ST. PÖLTEN
Höhere Abteilung für Informatik
Data Access Performance
 Improved Access for Consecutive Blocks: Since the data is spread across multiple drives, the array
can read and write multiple blocks in parallel. This improves performance, especially for sequential
data access, as the drives work together, effectively multiplying the throughput (*N, where N is the
number of drives in the array).
 Random Access for Single Blocks: For random access to a single block of data, there’s no significant
performance improvement over a single drive. Each block is still stored on a specific drive, so if only
one block is needed, RAID 0 doesn’t enhance access speed for that single operation.
Summary
 Pros: RAID 0 improves data throughput for sequential operations by leveraging multiple drives
simultaneously.
 Cons: RAID 0 lacks fault tolerance, and if one drive fails, all data is lost. Additionally, it doesn’t enhance
performance for random single-block access.