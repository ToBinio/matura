Überprüfen die Identität des Absenders des [[Public Key|öffentlicher Schlüssel]] und [[Digitale Signatur|signiert]] diesen mit ihrem [[Private Key|privaten Schlüssel]]. Diese Zertifizierung ([[Zertifikat|Zertifikat]]) hat aus Sicherheitsgründen ein Ablaufdatum.

Ungültige [[Zertifikat|Zertifikate]] werden in der [[Certificate Revocation List|Certificate Revocation List]] aufgelistet und können abgefragt werden, um die Gültigkeit eines [[Zertifikat|Zertifikats]] zu verifizieren.

Die Vertraulichkeit einer Certificate Authority wird durch Stichproben ermittelt.

Es gibt staatliche als auch private Certificate Authorities.

---

> [!cite]-
> ## Originale Quelle
> Deshalb gibt es Certificate Authorities (CA), die eine solche “Zertifizierung“ vornehmen. Sie überprüfen die Identität des Absenders und unterschreiben als Nachweis den Public-Key des Besitzers mit ihrem eigenen Private-Key und garantieren so die Identität. Zur weiteren Sicherheit sind alle Zertifizierungen zeitlich befristet und müssen regelmäßig wiederholt werden. Zusätzlich werden alle unterschriebenen Zertifikate von der CA veröffentlicht. Die Vertrauenswürdigkeit einer CA wird anhand von gesetzlichen Grundlagen und stichprobenartigen Überprüfungen gesichert.
> 
> Nachdem verschiedene Algorithmen für digitale Signaturen verwendet werden können, muss der benutzte Algorithmus ebenfalls angegeben werden. Zudem haben Zertifikate oft eine begrenzte Gültigkeit. Zertifikate können bei Missbrauch von der ausgestellten CA widerrufen werden. Sie veröffentlichen dazu eine sogenannte Certificate Revocation List (CRL), die periodisch aktualisiert wird. Jeder Teilnehmer einer Kommunikation, der ein Zertifikat erhält kann anhand dieser Liste überprüfen, ob es noch gültig ist.
