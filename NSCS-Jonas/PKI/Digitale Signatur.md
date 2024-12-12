Stellt Authentizität und Integrität sicher, nicht aber Geheimhaltung der Daten.

![[Pasted image 20241212115357.png]]

Zur Überprüfung muss der [[Public Key|Öffentliche Schlüssel]] des Absenders bekannt sein, meist über ein [[Zertifikat|Zertifikat]].
In Österreich ist geregelt, das [[Digitale Signatur|digitale Signaturen]] trotz Ablauf des [[Zertifikat|Zertifikats]] gültig wären.

Der für die [[Digitale Signatur|Signature]] verwendete Algorithmus muss ebenfalls angegeben werden.

---

> [!cite]-
> ## Originale Quelle
> Die digitale Signatur (=elektronische Signatur) dient der Sicherstellung von Authentizität und Integrität. Sie dient nicht der Geheimhaltung von Daten. Um die Gültigkeit der Signatur zu Überprüfen muss der Public Key des Absenders (Unterschreibenden) verwendet werden. Um die Gültigkeit dieses Keys zu überprüfen wird er meist in Form eines Zertifikates weitergegeben. In weiterer Folge geht es um die Verwaltung und Prüfung von solchen Zertifikaten. In Österreich ist die Verwendung von digitalen Signaturen im Signaturgesetz geregelt. Hier wird beispielsweise auch festgelegt, was passiert, wenn ein Zertifikat abläuft. Das jedes Zertifikat nur eine begrenzte Gültigkeitsdauer hat, wird das zwangsläufig passieren. In diesem Fall bleibt die dig. Signatur weiterhin gültig.
> 
> Nachdem verschiedene Algorithmen für digitale Signaturen verwendet werden können, muss der benutzte Algorithmus ebenfalls angegeben werden. Zudem haben Zertifikate oft eine begrenzte Gültigkeit. Zertifikate können bei Missbrauch von der ausgestellten CA widerrufen werden. Sie veröffentlichen dazu eine sogenannte Certificate Revocation List (CRL), die periodisch aktualisiert wird. Jeder Teilnehmer einer Kommunikation, der ein Zertifikat erhält kann anhand dieser Liste überprüfen, ob es noch gültig ist.