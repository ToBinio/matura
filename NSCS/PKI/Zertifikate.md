Digital signierte elektronische Daten, die sich zum Nachweis der Echtheit von Objekten verwenden lassen.

---

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