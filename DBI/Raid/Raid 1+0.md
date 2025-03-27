Es ist eine Kombination aus [[Raid 1|Raid 1]] und [[Raid 0|Raid 0]]. Zuerst wird aufgeteilt und dann dupliziert:

![[RAID10.png]]

In jedem [[Raid 0|Raid 0]] Array kann maximal eine Festplatte ausfallen, wodurch insgesamt minimal eine und bis zu zwei Festplatten ausfallen können. Die Performance im Bereich Schreiben ist vergleichbar mit [[Raid 1]] und im Bereich Lesen mit [[Raid 0]].

---

> [!cite]-
> ### Originale Quelle
>  combines RAID 1 with RAID 0
o mirroring + striping
 fault tolerance?
o at least one drive per RAID 1 needs to be operational
 data access?
o fast for consecutive blocks (*N)