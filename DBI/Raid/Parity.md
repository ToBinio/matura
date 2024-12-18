Parity verringert die Anzahl der Festplatten, welche für Fehlertoleranz geopfert werden müssen. Bei [[Raid 1|Raid 1]], [[Raid 1+0|Raid 10]] und [[Raid 0+1|Raid 01]] können nur N/2 Festplatten verwendet werden, wenn Parity verwendet wird jedoch N-1.

**Berechnung der Parity**
Hierfür wird der XOR Operator verwendet:

| A | B | XOR |
|---|---|-----|
| 0 | 0 | 0   |
| 0 | 1 | 1   |
| 1 | 0 | 1   |
| 1 | 1 | 0   |
**Vereinfachte Regel**
Ist die Summe ungerade, so ist die Parity 1 sonst 0.

**Beispiel**
Hier ein Beispiel mit 4 Festplatten und 3 Bytes, welche gespeichert werden:

| A   | B   | C   | Parity (A⊕B⊕C) |
| --- | --- | --- | -------------- |
| 0   | 1   | 0   | 1              |
| 1   | 1   | 1   | 1              |
| 1   | 0   | 1   | 0              |
| 0   | 0   | 0   | 0              |
| 0   | 1   | 0   | 1              |
| 0   | 1   | 1   | 0              |
| 0   | 0   | 1   | 1              |
| 1   | 1   | 0   | 0              |
Fällt nun Beispielsweise Festplatte C aus, kann diese wieder mittels XOR hergestellt werden:

| A   | B   | Parity | C (A⊕B⊕P) |
| --- | --- | ------ | --------- |
| 0   | 1   | 1      | 0         |
| 1   | 1   | 1      | 1         |
| 1   | 0   | 0      | 1         |
| 0   | 0   | 0      | 0         |
| 0   | 1   | 1      | 0         |
| 0   | 1   | 0      | 1         |
| 0   | 0   | 1      | 1         |
| 1   | 1   | 0      | 0         |

---

> [!cite]-
> ### Originale Quelle
>  RAID levels 1, 01, 10 reduce capacity for N drives to C=N/2
 error correction
o more efficient, C=N-1
o used to reconstruct data in the event of a defect drive
 parity bit calculation
o based on XOR
o sum of bits is pair  0
o sum of bits is odd  1
graphics from https://en.wikipedia.org/wiki/Exclusive_or
Exercise 1:
 given:
o A1 = 10011001
o A2 = 01100101
o A3 = 11100110
 What is the parity information PA?
Steps
>1. Perform bitwise XOR across all three data blocks.
Bitwise XOR Calculation:
Exercise 2:
Assume that the disc where A2 is stored is corrupted. Show how the information can be restored for a
replacing new disc!
Column 1 (No defect)
Column 2 (Defect in A1)
A1 = PA ⊕ A2 ⊕ A3
Column 3 (Defect in A2)
A2 = PA ⊕ A1 ⊕ A3
Column 4 (Defect in A3)
A2 = PA ⊕ A1 ⊕ A2
Datenbanken und Informationssysteme Seite 51
HÖHERE TECHNISCHE BUNDESLEHRANSTALT ST. PÖLTEN
Höhere Abteilung für Informatik
Execrise 3:
 Disk 1 =1111
 Disk 2 =1110
 Disk 3 =1100
 Disk 4 =1000
PA = ?
