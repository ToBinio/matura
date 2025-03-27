Bei Raid 1 werden die Daten auf alle angeschlossenen Festplatten dupliziert. 

Durch das duplizieren der Daten wird die Fehlertoleranz erhöht. Mindestens eine der angeschlossenen Festplatten muss funktionieren, damit die Daten bestehen bleiben.

Die Lesegeschwindigkeit kann erhöht sein, da gleichzeitig von mehreren Festplatten gelesen werden kann. Die Schreibgeschwindigkeit bleibt jedoch gleich, da immer alles auf alle Festplatten geschrieben werden muss. Eventuell einwenig langsamer als bei einer Festplatte.

![[raid-level-1.jpg]]

---

> [!cite]-
> ### Originale Quelle
> In RAID 1 with two drives, the configuration is centered around mirroring, where data is written identically
to two separate drives. Here’s a breakdown of the key points:
Mirroring
 Exact Copy: In RAID 1, each piece of data written to one
drive is simultaneously written to the other. This creates an
exact duplicate, or mirror, on the second drive.
 Data Redundancy: Because the data exists on both drives,
it offers an immediate backup in case one of the drives fails.
Fault Tolerance
 Operational Integrity: The RAID 1 array continues to function as long as at least one of the drives
remains operational. If one drive fails, the data is still accessible from the remaining functional drive.
 Automatic Failover: In the event of a drive failure, the system can automatically switch to the
surviving drive, ensuring continued access to data without immediate downtime.
Datenbanken und Informationssysteme Seite 45
HÖHERE TECHNISCHE BUNDESLEHRANSTALT ST. PÖLTEN
Höhere Abteilung für Informatik
Data Access
 Read Performance: In some RAID 1 implementations, read performance can improve because data
can be read from both drives. This allows the system to balance read requests across the two drives,
potentially speeding up access times for high-read workloads.
 Write Performance: For every write request, both drives need to be updated to maintain the mirror.
This means the system performs N parallel operations (in this case, two parallel writes) for each write
request, as each drive has to be synchronized.
However, write speeds generally do not see
improvement and may be slower than single-drive
writes because the data needs to be written to both
drives.
Summary
RAID 1 with two drives provides strong fault tolerance through mirroring, maintaining data integrity as
long as one drive is functional. While it doesn’t improve write speed, it can enhance read performance in
specific scenarios by allowing read operations from either drive.