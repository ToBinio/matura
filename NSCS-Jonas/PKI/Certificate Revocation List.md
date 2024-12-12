Zertifikate die vor Ablauf der Gültigkeit zurückgezogen wurden. Meist aus Sicherheit oder Ungültigkeit. Wird periodisch neu generiert und aktualisiert. Diese kann auch durch eine Positiv-Liste (White-List) ersetzt werden. Diese beiden Varianten sind offline Statusüberprüfungen.

Für online Statusüberprüfungen gibt es z.B. die Protokolle [[Online Certificate Status Protocol|OCSP]] oder [[Server-Based Certificate Validation Protocol|SCVP]]. Diese werden eingesetzt wenn die Überprüfung zeitgenau erfolgen muss.

---

> [!cite]-
> ## Originale Quelle
> Eine Liste mit Zertifikaten, die vor Ablauf der Gültigkeit zurückgezogen wurden. Gründe sind die Kompromittierung des Schlüsselmaterials, aber auch Ungültigkeit der Zertifikatsdaten (z.B. E-Mail) oder Verlassen der Organisation. Eine Zertifikatssperrliste hat eine definierte Laufzeit, nach deren Ablauf sie erneut aktualisiert erzeugt wird. Anstatt der CRL kann auch eine Positivliste, die sogenannte White-List verwendet werden, in die nur alle zum aktuellen Zeitpunkt gültigen Zertifikate eingetragen werden. Prinzipiell muss eine PKI immer eine Zertifikatsstatusprüfung anbieten. Hierbei können jedoch neben der CRL (oder der WhiteList) als Offline Statusprüfung auch so genannte Online-Statusprüfungen wie OCSP (Online Certificate Status Protocol) oder SCVP (Server-based Certificate Validation Protocol) zum Einsatz kommen. OnlineStatusprüfungen werden üblicherweise dort eingesetzt, wo die zeitgenaue Prüfung des Zertifikates wichtig ist z. B. bei finanziellen Transfers etc.