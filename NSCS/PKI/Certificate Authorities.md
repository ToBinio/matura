CA's überprüfen die Identität des Absenders und unterschreiben als Nachweis den Public-Key des Besitzers mit ihrem eigenen Private-Key und garantieren so die Identität. Zur weiteren Sicherheit sind alle Zertifizierungen zeitlich befristet und müssen regelmäßig wiederholt werden. Zusätzlich werden alle unterschriebenen Zertifikate von der CA veröffentlicht. Die Vertrauenswürdigkeit einer CA wird anhand von gesetzlichen Grundlagen und stichprobenartigen Überprüfungen gesichert.

CA’s können sowohl staatsnahe sein (z.B. a-trust in Österreich) als auch private Unternehmen sein (z.B.
Verisign).
3
Der wichtigste Standard für digitale Zertifikate ist der X.509 Standard. Ein X.509 Zertifikat muss folgende
Informationen enthalten:
• Den Namen des Eigentümers des Zertifikats
• Den öffentlichen Schlüssel des Eigentümers (public key)
• Den Namen der CA
• Eine digitale Signatur der CA
• Gültigkeitszeitraum
• Verwendungszweck