Raid 5 verwendet wie [[Raid 0|Raid 0]] das Prinzip des Stripings. Die Daten werden in Blöcke aufgeteilt und auf die verschiedenen Festplatten aufgeteilt, wodurch die Performance im Bereich Lesen und Schreiben verbessert wird. Jedoch gibt es beim Schreiben einen kleinen Overhead, da jedes mal eine [[Parity|Parity]] berechnet werden/geupdated muss .

Raid 5 fügt noch einen [[Parity|Parity]] Block hinzu, welcher zur Wiederherstellung der Daten verwendet wird. Diese [[Parity|Parity]] wird auf alle Festplatten aufgeteilt um einen Bottleneck zu verhindern.

Zum Betrieb von Raid 5 werden mindestens 3 Festplatten benötigt, damit eine [[Parity|Parity]] gebildet werden kann, wobei immer eine ganze Festplatte für die Parity Daten benötigt wird (N-1). 

Raid 5 bietet Sicherheit für maximal einen Festplattenausfall. Tritt dieser Fall ein, so können mittels der [[Parity|Parity]] die fehlenden Daten wiederhergestellt werden. 

![[raid-5.webp]]

---

> [!cite]-
> ### Originale Quelle
> Redundant Array of Independent Disks (Level 5), is a popular RAID level known for balancing performance,
redundancy, and storage efficiency.
Key Features of RAID 5
 Block-Level Striping: RAID 5 stripes data at the block level
across all drives in the array. This means that files are split into
smaller blocks, which are then distributed across multiple
disks. Striping enhances read and write performance, as
multiple drives can handle parts of the data in parallel.
 Distributed Parity: RAID 5 distributes parity information
across all drives in the array, rather than storing it on a single
dedicated parity disk. Parity is a form of error-checking code
that helps recover data if a single drive fails. By distributing
parity blocks among the drives, RAID 5 avoids the bottlenecks
associated with having a single dedicated parity drive.
 Different Layouts: Parity and data blocks are arranged in a way that balances data and parity blocks
on each drive. Different vendors may implement specific layouts to optimize performance or
redundancy, but the basic concept of distributing both data and parity across all disks remains the
same.
 Minimum of 3 Disks: RAID 5 requires at least three disks to function. As the number
of drives increases, the usable storage capacity and read performance improve, but
the redundancy (ability to tolerate failures) remains limited to a single drive failure.