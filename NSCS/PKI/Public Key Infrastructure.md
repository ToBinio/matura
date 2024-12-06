## Digitale Signatur
Die digitale Signatur (=elektronische Signatur) dient der Sicherstellung von Authentizität und Integrität. Sie dient **nicht** der Geheimhaltung von Daten.
![[Digitale-Signatur.png]]Um die Gültigkeit der Signatur zu Überprüfen muss der Public Key des Absenders (Unterschreibenden) verwendet werden. Um die Gültigkeit dieses Keys zu überprüfen wird er meist in Form eines Zertifikates weitergegeben.

<small>
In Österreich ist die Verwendung von digitalen Signaturen im Signaturgesetz geregelt. Hier wird beispielsweise auch festgelegt, was passiert, wenn ein Zertifikat abläuft. Das jedes Zertifikat nur eine begrenzte Gültigkeitsdauer hat, wird das zwangsläufig passieren. In diesem Fall bleibt die dig. Signatur weiterhin gültig.
</small>

---
## Zertifikate
Auch moderne Verschlüsselungsverfahren garantieren nicht automatisch, dass eine Nachricht wirklich von der angegebenen Person stammt. Damit eine sichere Kommunikation möglich ist, muss der öffentliche Schlüssel als „vertrauenswürdig“ gelten.

Deshalb gibt es [[Certificate Authorities]] diese überprüfen die Identität des Absenders und unterschreiben als Nachweis den Public-Key des Besitzers mit ihrem eigenen Private-Key und garantieren so die Identität. Zur weiteren Sicherheit sind alle Zertifizierungen zeitlich befristet und müssen regelmäßig wiederholt werden. Zusätzlich werden alle unterschriebenen Zertifikate von der CA veröffentlicht. Die Vertrauenswürdigkeit einer CA wird anhand von gesetzlichen Grundlagen und stichprobenartigen Überprüfungen gesichert.

CA’s können sowohl staatsnahe sein (z.B. a-trust in Österreich) als auch private Unternehmen sein (z.B. Verisign).

Der wichtigste Standard für digitale Zertifikate ist der X.509 Standard. Ein X.509 Zertifikat muss folgende Informationen enthalten:

• Den Namen des Eigentümers des Zertifikats
• Den öffentlichen Schlüssel des Eigentümers (public key)
• Den Namen der CA
• Eine digitale Signatur der CA
• Gültigkeitszeitraum
• Verwendungszweck

Nachdem verschiedene Algorithmen für digitale Signaturen verwendet werden können, muss der benutzte Algorithmus ebenfalls angegeben werden. Zudem haben Zertifikate oft eine begrenzte Gültigkeit. Zertifikate können bei Missbrauch von der ausgestellten CA widerrufen werden. Sie veröffentlichen dazu eine sogenannte Certificate Revocation List (CRL), die periodisch aktualisiert wird. Jeder Teilnehmer einer Kommunikation, der ein Zertifikat erhält kann anhand dieser Liste überprüfen, ob es noch gültig ist.