Raid steht für Redundant Array of Independent Disks. Dieser Array an Festplatten wird als eine einzige Festplatte dargestellt. 

![[raid-diagram.png]]

**Verschiedene Arten von Raid**
- [[Raid 0|Raid 0]]
- [[Raid 1|Raid 1]]
- [[Raid 1+0|Raid 10]]
- [[Raid 0+1|Raid 01]]
- [[Raid 5|Raid 5]]
- Raid 6
	- 2 Parities

**Hot Spare**
Eine weitere Festplatte, welche erst in Betrieb kommt, sobald in einem Raid System eine Festplatte ausfällt.

---

> [!cite]-
> ### Originale Quelle
> Redundant
Array (of)
Independent (or Inexpensive)
Discs
 appears as one logical drive
 different RAID levels for different purposes
Video:
8.4 Final Considerations
 further RAID levels
 RAID 01 (RAID 0+1)
 RAID 2
 RAID 3
 RAID 4
 RAID 6
 ...
 proprietary and hybrid levels
 hot spare
o additional drive
o used for automatic recovery of RAID system
 choice of RAID level
o #read operations
o #write operations
o need for reliability
o need for availability
o need for speed
o cost reduction
 act of god
o fire, water ...
o drives usually in one rack -> data loss!