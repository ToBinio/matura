![[Pasted image 20241212124748.png]]

### Funktionsweise
Verwendet Verschlüsselung, [[Digitale Signatur|Digitale Signaturen]], [[Zertifikat|Zertifikate]], [[Certificate Authority|Certificate Authorities]], [[Registration Authorities|Registration Authorities]] usw für eine sichere Kommunikation im Internet.

Um zu sehen, ob man einem [[Zertifikat|Zertifikat]] vertrauen kann, muss man die gesamte Zertifikatskette durchgehen und überprüfen, ob diese valide sind. Dem letzten Zertifikat muss vertraut werden.

Die [[Zertifikat|Zertifikats]]kette wird gebildet, in dem das [[Zertifikat|Zertifikat]] für den [[Public Key|öffentlichen Schlüssel]], der das [[Zertifikat|Zertifikat]] ausgestellt hat, überprüft. Und das solange bis es keines mehr gibt.

### Bestandteile
- [[Zertifikat|Zertifikate]]
- [[Certificate Authority|Certificate Authorities]]
- [[Registration Authorities|Registration Authorities]]
- [[Certificate Revocation List|Certificate Revocation List]]
- [[Directory Service|Directory Service]]
- [[Certificate Policy|Certificate Policy]]
- [[Certification Practice Statement|Certification Practice Statement]]
- Dokumentation
	- Dokumentation über die Handhabung des [[Private Key|privaten Schlüssels]], Schlüsselerzeugung usw. Beinhaltet teilweise die [[Certificate Policy|Certificate Policy]] und das [[Certification Practice Statement|Certification Practice Statement]]

---

>[!cite]-
> ## Originale Quellen
> Mit Hilfe eines asymmetrischen Kryptosystems können Nachrichten in einem Netzwerk digital signiert und verschlüsselt werden. Sichere Kryptosysteme können bei geeigneter Wahl der Parameter (z. B. der Schlüssellänge) auch bei Kenntnis des Verfahrens zumindest nach heutigem Kenntnisstand nicht in überschaubarer Zeit gebrochen werden. In asymmetrischen Kryptosystemen benötigt der Sender für eine verschlüsselte Übermittlung den öffentlichen Schlüssel (Public Key) des Empfängers. Dieser könnte z. B. per E-Mail versendet oder von einer Web- 4 Seite heruntergeladen werden. Dabei muss sichergestellt sein, dass es sich tatsächlich um den Schlüssel des Empfängers handelt und nicht um eine Fälschung eines Betrügers. Hierzu dienen nun digitale Zertifikate, die die Authentizität eines öffentlichen Schlüssels und seinen zulässigen Anwendungs- und Geltungsbereich bestätigen. Das digitale Zertifikat ist selbst durch eine digitale Signatur geschützt, deren Echtheit mit dem öffentlichen Schlüssel des Ausstellers des Zertifikates geprüft werden kann. Um die Authentizität des Ausstellerschlüssels zu prüfen, wird wiederum ein digitales Zertifikat benötigt. Auf diese Weise lässt sich eine Kette von digitalen Zertifikaten aufbauen, die jeweils die Authentizität des öffentlichen Schlüssels bestätigen, mit dem das vorhergehende Zertifikat geprüft werden kann. Eine solche Kette von Zertifikaten wird Validierungspfad oder Zertifizierungspfad genannt. Auf die Echtheit des letzten Zertifikates (und des durch diesen zertifiziert