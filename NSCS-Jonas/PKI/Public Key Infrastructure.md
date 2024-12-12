![[Pasted image 20241212124748.png]]

### Funktionsweise
Verwendet Verschlüsselung, [[Digitale Signatur|Digitale Signaturen]], [[Zertifikat|Zertifikate]], [[Certificate Authority|Certificate Authorities]], [[Registration Authorities|Registration Authorities]] usw für eine sichere Kommunikation im Internet.

Um zu sehen, ob man einem [[Zertifikat|Zertifikat]] vertrauen kann, muss man die gesamte [[Zertifikat|Zertifikats]]kette durchgehen und überprüfen, ob diese valide sind. Dem letzten Zertifikat muss vertraut werden.

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

### Vertrauensmodelle
[[Zertifikat|Zertifikate]] stellen die digitale Beglaubigung dar. Das Vertrauen zwischen Prüfer und Aussteller ist hier essentiell, wofür [[Zertifikat|Zertifikate]] benötigt werden.

**Streng hierarchische PKI**
Geht von der Existenz einer Root-[[Certificate Authority|Certificate Authority]] aus, welcher alle Parteien vertrauen. Jedoch gibt es in der Welt keine einheitliche Root-[[Certificate Authority|Certificate Authority]]. So betreiben Länder und große Unternehmen eigene hierarchische PKIs mit Root-[[Certificate Authority|Certificate Authorities]]. Der Grund dafür ist fehlendes Vertrauen und dem Wunsch nach Kontrolle.

![[Pasted image 20241212141035.png]]

Diese Root-[[Certificate Authority|Certificate Authorities]] werden oft bei Software mitgeliefert (Browser usw).

**Cross-Zertifizierung**
Ein Cross-[[Zertifikat|Zertifikat]] ermöglicht es, [[Zertifikat|Zertifikate]] einer anderen PKI in die eigene PKI aufzunehmen. Hier steht jedoch die eigene Root-[[Certificate Authority|Certificate Authorities]] immer noch über allen anderen.

![[Pasted image 20241212141650.png]]

Ein Beispiel hierfür ist LetsEncrypt, welches früher nicht vertraulich war, bis von TrustID ein Cross-[[Zertifikat|Zertifikat]] erstellt wurde.

**Web of Trust**
Anderes Vertrauensmodell, ermöglicht durch PGP und GNU Privacy Guard.
Jeder kann ein [[Zertifikat|Zertifikat]] für einen anderen [[Public Key|öffentlichen Schlüssel]] erstellen. Andere können anhand der Menge an [[Zertifikat|Zertifikate]] für einen [[Public Key|öffentlichen Schlüssel]] entscheiden, ob dieser vertraulich ist.

![[Pasted image 20241212143538.png]]

Es kann nie die 100%ige Gültigkeit nachgewiesen werden. Die [[Digitale Signatur|Signatur]] der [[Zertifikat|Zertifikate]] können nur schwer geprüft werden.
Jedoch gibt es keine Zentrale Autorität, was ein Vorteil ist.
Für kleine Projekte eventuell denkbar.
### Implementierungen
- [[Windows Server|Windows Server]]
- OpenSSL (EasyRSA, OpenCA)
- Dogtag Certificate System

---

>[!cite]-
> ## Originale Quellen
> Mit Hilfe eines asymmetrischen Kryptosystems können Nachrichten in einem Netzwerk digital signiert und verschlüsselt werden. Sichere Kryptosysteme können bei geeigneter Wahl der Parameter (z. B. der Schlüssellänge) auch bei Kenntnis des Verfahrens zumindest nach heutigem Kenntnisstand nicht in überschaubarer Zeit gebrochen werden. In asymmetrischen Kryptosystemen benötigt der Sender für eine verschlüsselte Übermittlung den öffentlichen Schlüssel (Public Key) des Empfängers. Dieser könnte z. B. per E-Mail versendet oder von einer Web- 4 Seite heruntergeladen werden. Dabei muss sichergestellt sein, dass es sich tatsächlich um den Schlüssel des Empfängers handelt und nicht um eine Fälschung eines Betrügers. Hierzu dienen nun digitale Zertifikate, die die Authentizität eines öffentlichen Schlüssels und seinen zulässigen Anwendungs- und Geltungsbereich bestätigen. Das digitale Zertifikat ist selbst durch eine digitale Signatur geschützt, deren Echtheit mit dem öffentlichen Schlüssel des Ausstellers des Zertifikates geprüft werden kann. Um die Authentizität des Ausstellerschlüssels zu prüfen, wird wiederum ein digitales Zertifikat benötigt. Auf diese Weise lässt sich eine Kette von digitalen Zertifikaten aufbauen, die jeweils die Authentizität des öffentlichen Schlüssels bestätigen, mit dem das vorhergehende Zertifikat geprüft werden kann. Eine solche Kette von Zertifikaten wird Validierungspfad oder Zertifizierungspfad genannt. Auf die Echtheit des letzten Zertifikates (und des durch diesen zertifiziert Schlüssel) müssen sich die Kommunikationspartner ohne ein weiteres Zertifikat verlassen können.
>
> Bestandteile einer PKI Digitale Zertifikate Digital signierte elektronische Daten, die sich zum Nachweis der Echtheit von Objekten verwenden lassen. Zertifizierungsstelle (Certificate Authority, CA) Organisation, die das CA-Zertifikat bereitstellt und die Signatur von Zertifikatsanträgen übernimmt. Registrierungsstelle (Registration Authority, RA) Organisation, bei der Personen, Maschinen oder auch untergeordnete Zertifizierungsstellen Zertifikate beantragen können. Diese prüft die Richtigkeit der Daten im gewünschten Zertifikat und genehmigt den Zertifikatsantrag, der dann durch die Zertifizierungsstelle signiert wird. Bei einer manuellen Prüfung wird diese durch den Registration Authority Officer durchgeführt. Zertifikatsperrliste (Certificate Revocation List, CRL) Eine Liste mit Zertifikaten, die vor Ablauf der Gültigkeit zurückgezogen wurden. Gründe sind die Kompromittierung des Schlüsselmaterials, aber auch Ungültigkeit der Zertifikatsdaten (z.B. E-Mail) oder Verlassen der Organisation. Eine Zertifikatssperrliste hat eine definierte Laufzeit, nach deren Ablauf sie erneut aktualisiert erzeugt wird. Anstatt der CRL kann auch eine Positivliste, die sogenannte White-List verwendet werden, in die nur alle zum aktuellen Zeitpunkt gültigen Zertifikate eingetragen werden. Prinzipiell muss eine PKI immer eine Zertifikatsstatusprüfung anbieten. Hierbei können jedoch neben der CRL (oder der WhiteList) als Offline Statusprüfung auch so genannte Online-Statusprüfungen wie OCSP (Online Certificate Status Protocol) oder SCVP (Server-based Certificate Validation Protocol) zum Einsatz kommen. OnlineStatusprüfungen werden üblicherweise dort eingesetzt, wo die zeitgenaue Prüfung des Zertifikates wichtig ist z. B. bei finanziellen Transfers etc. Verzeichnisdienst (Directory Service) ein durchsuchbares Verzeichnis, das ausgestellte Zertifikate zusätzlich zu den Usern/Maschinen enthält, meist ein LDAP-Server (Active Directory, eDirectory, OpendLDAP), seltener ein X.500-Server. Dokumentationen Eine PKI führt eines oder mehrere Dokumente, in denen die Arbeitsprinzipien der PKI beschrieben sind. Kernpunkte sind der Registrierungsprozess, Handhabung des privaten Schlüssels, zentrale oder dezentrale Schlüsselerzeugung, technischer Schutz der PKI-Systeme sowie eventuell rechtliche Zusicherungen. In 5 X.509-Zertifikaten kann das CPS in den Extensions eines Zertifikates verlinkt werden. Die nachfolgend aufgeführten Dokumente sind teilweise üblich: CP (Certificate Policy) In diesem Dokument beschreibt die PKI ihr Anforderungsprofil an ihre eigene Arbeitsweise. Es dient Dritten zur Analyse der Vertrauenswürdigkeit und damit zur Aufnahme in den Browser. CPS (Certification Practice Statement) Hier wird die konkrete Umsetzung der Anforderungen in die PKI beschrieben. Dieses Dokument beschreibt die Umsetzung der CP.
> 
> Zertifikate stellen im Wesentlichen digitale Beglaubigungen dar. Somit stellt das Vertrauen zwischen dem Prüfer und dem Aussteller eines Zertifikates sowie die Art und Weise, wie dieses Vertrauen zustande kommt, die wesentliche Basis für die Verwendung digitaler Zertifikate dar. Umgekehrt lassen sich solche Vertrauensmodelle in der Regel erst durch Zertifikate technisch umsetzen
> 
>Oft werden Zertifikate innerhalb einer komplett hierarchischen PKI eingesetzt. Dieses Vertrauensmodell setzt die Existenz einer Wurzelinstanz (Root-CA) voraus: einer obersten Zertifizierungsstelle, der alle teilnehmenden Parteien vertrauen. In der Praxis (zumindest auf globaler Ebene) gibt es jedoch eine solche Instanz nicht. So betreiben etwa verschiedene Länder und multinationale Unternehmen jeweils eigene hierarchische PKIs mit eigenen Wurzelinstanzen. Die Ursache dafür liegt weniger in mangelndem Vertrauen in andere PKIs oder Wurzelinstanzen, als vielmehr im Wunsch nach vollständiger Kontrolle der Regeln innerhalb der eigenen PKI.
>
>Zertifikate von wichtigen Root-CAs sind oft in die verarbeitende Software integriert (z.B. Browser). Problematisch dabei ist jedoch, dass Aussagen über die Anforderungen für die Ausstellung der Zertifikate und damit über ihre Vertrauenswürdigkeit und zulässige Anwendungsbereiche nur über die jeweilige PKI-Dokumentation getroffen werden können.
>
>Eine Möglichkeit, die Anwendung von Zertifikaten über die Grenzen verschiedener hierarchischer PKIs hinweg zu ermöglichen, ist die Cross-Zertifizierung. Dabei stellen sich zwei Zertifizierungsstellen (meist Wurzelinstanzen) gegenseitig ein (Cross-)Zertifikat aus. Im Unterschied zu normalen Zertifikaten in einer hierarchischen PKI drücken Cross-Zertifikate das Vertrauen zweier gleichberechtigter Parteien aus, d. h. die Regelungen der einen Wurzelinstanz sind für die PKI der anderen Wurzelinstanz nicht verbindlich, oder nur insoweit verbindlich, als sie deren eigenen Regelungen nicht widersprechen. Die Interpretation der durch ein 6 Cross-Zertifikat ausgedrückten Vertrauensbeziehung ist daher manchmal nicht einfach und in vielen Fällen nicht einmal eindeutig.
>
>Ein Anwendungsfall war die CA „Let’s Encrypt“. Als diese CA gegründet wurde, war sie in keinem Betriebssystem als vertrauenswürdig eingetragen. Damit die ausgegebenen Zertifikate aber verwendet werden konnten wurde „Lets Encrypt“ Cross zertifiziert (TrustID). Somit konnten in der Übergangszeit die Zertifikate auf Ihre Gültigkeit überprüft werden.
>
>Ein zur Zertifizierungshierarchie komplett konträres Vertrauensmodell wird durch die Verschlüsselungssoftware PGP und die OpenSource-Variante Gnu Privacy Guard genutzt (Beide basieren auf OpenPGP und sind zueinander kompatibel). Ein Zertifikat kann von jedem Benutzer (Web-of-Trust-Mitglied) erzeugt werden. Glaubt ein Benutzer daran, dass ein öffentlicher Schlüssel tatsachlich zu der Person gehört, die ihn veröffentlicht, so erstellt er ein Zertifikat, indem er diesen öffentlichen Schlüssel signiert. Andere Benutzer können aufgrund dieses Zertifikates entscheiden, ob auch sie darauf vertrauen wollen, dass der Schlüssel zum angegebenen Benutzer gehört oder nicht. Je mehr Zertifikate an einem Schlüssel hängen, desto sicherer kann man sein, dass dieser Schlüssel tatsächlich dem angegebenen Eigentümer gehört.
>
>Diese Methode hat ganz offensichtliche Nachteile. Es kann niemals hundertprozentig die Gültigkeit eines Zertifikats nachgewiesen werden. Die Signaturen eines Zertifikats können nur schwer auf Ihre Gültigkeit geprüft werden. Der große Vorteil ist, dass es keine zentrale Autorität geben muss. In vielen lose organisierten Projekten im Internet gibt es nur wenige oder gar keine Strukturen. In einem solchen Fall kann des „Web of Trust“ zu mindestens eine minimale Überprüfbarkeit bringen.


