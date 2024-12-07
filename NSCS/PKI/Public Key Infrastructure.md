
![[PKI.png]]
Mit Hilfe eines [[asymmetrischen Kryptosystems]] können Nachrichten in einem Netzwerk digital signiert und verschlüsselt werden. Sichere Kryptosysteme können bei geeigneter Wahl der Parameter (z. B. der Schlüssellänge) auch bei Kenntnis des Verfahrens zumindest nach heutigem Kenntnisstand nicht in überschaubarer Zeit gebrochen werden.

Um die Authentizität des Ausstellerschlüssels zu prüfen, wird wiederum ein [[Zertifikate|digitales Zertifikat]] benötigt. Auf diese Weise lässt sich eine Kette von digitalen Zertifikaten aufbauen, die jeweils die Authentizität des öffentlichen Schlüssels bestätigen, mit dem das vorhergehende Zertifikat geprüft werden kann. Eine solche Kette von Zertifikaten wird Validierungspfad oder Zertifizierungspfad genannt. Auf die Echtheit des letzten Zertifikates (und des durch diesen zertifizierten Schlüssel) müssen sich die Kommunikationspartner ohne ein weiteres Zertifikat verlassen können.

---

### Bestandteile
- [[Zertifikate|Digitale Zertifikate]]
- [[Certificate Authorities|Zertifizierungsstelle (Certificate Authority, CA)]]
- **Registrierungsstelle (Registration Authority, RA)**
  Organisation, bei der Personen, Maschinen oder auch untergeordnete Zertifizierungsstellen Zertifikate beantragen können. Diese prüft die Richtigkeit der Daten im gewünschten Zertifikat und genehmigt den Zertifikatsantrag, der dann durch die Zertifizierungsstelle signiert wird. Bei einer manuellen Prüfung wird diese durch den Registration Authority Officer durchgeführt
  
- **Zertifikatsperrliste (Certificate Revocation List, CRL)**
  Eine Liste mit Zertifikaten, die vor Ablauf der Gültigkeit zurückgezogen wurden. Gründe sind die Kompromittierung des Schlüsselmaterials, aber auch Ungültigkeit der Zertifikatsdaten (z.B. E-Mail) oder Verlassen der Organisation. Eine Zertifikatssperrliste hat eine definierte Laufzeit, nach deren Ablauf sie erneut aktualisiert erzeugt wird. Anstatt der CRL kann auch eine Positivliste, die sogenannte White-List verwendet werden, in die nur alle zum aktuellen Zeitpunkt gültigen Zertifikate eingetragen werden. Prinzipiell muss eine PKI immer eine Zertifikatsstatusprüfung anbieten. Hierbei können jedoch neben der CRL (oder der WhiteList) als Offline Statusprüfung auch so genannte Online-Statusprüfungen wie OCSP (Online Certificate Status Protocol) oder SCVP (Server-based Certificate Validation Protocol) zum Einsatz kommen. Online Statusprüfungen werden üblicherweise dort eingesetzt, wo die zeitgenaue Prüfung des Zertifikates wichtig ist z. B. bei finanziellen Transfers etc.
  
- **Verzeichnisdienst (Directory Service)**
  ein durchsuchbares Verzeichnis, das ausgestellte Zertifikate zusätzlich zu den Usern/Maschinen enthält, meist ein LDAP-Server (Active Directory, eDirectory, OpendLDAP), seltener ein X.500-Server.
  
- **Dokumentationen**
  Eine PKI führt eines oder mehrere Dokumente, in denen die Arbeitsprinzipien der PKI beschrieben sind. Kernpunkte sind der Registrierungsprozess, Handhabung des privaten Schlüssels, zentrale oder dezentrale Schlüsselerzeugung, technischer Schutz der PKI-Systeme sowie eventuell rechtliche Zusicherungen. In X.509-Zertifikaten kann das CPS in den Extensions eines Zertifikates verlinkt werden. Die nachfolgend aufgeführten Dokumente sind teilweise üblich:
  
  -  **CP (Certificate Policy)**
    In diesem Dokument beschreibt die PKI ihr Anforderungsprofil an ihre eigene Arbeitsweise. Es dient Dritten zur Analyse der Vertrauenswürdigkeit und damit zur Aufnahme in den Browser.
  - **CPS (Certification Practice Statement)**
	Hier wird die konkrete Umsetzung der Anforderungen in die PKI beschrieben. Dieses Dokument beschreibt die Umsetzung der CP.

---

## Vertrauensmodelle

[[Zertifikate]] stellen im Wesentlichen digitale Beglaubigungen dar. Somit stellt das Vertrauen zwischen dem Prüfer und dem Aussteller eines Zertifikates sowie die Art und Weise, wie dieses Vertrauen zustande kommt, die wesentliche Basis für die Verwendung digitaler Zertifikate dar. Umgekehrt lassen sich solche Vertrauensmodelle in der Regel erst durch Zertifikate technisch umsetzen.

### Streng hierachische PKI
Oft werden Zertifikate innerhalb einer komplett hierarchischen PKI eingesetzt. Dieses Vertrauensmodell setzt die Existenz einer Wurzelinstanz ([[Certificate Authorities|Root-CA]]) voraus: einer obersten Zertifizierungsstelle, der alle teilnehmenden Parteien vertrauen. In der Praxis (zumindest auf globaler Ebene) gibt es jedoch eine solche Instanz nicht. So betreiben etwa verschiedene Länder und multinationale Unternehmen jeweils eigene hierarchische PKIs mit eigenen Wurzelinstanzen. Die Ursache dafür liegt weniger in mangelndem Vertrauen in andere PKIs oder Wurzelinstanzen, als vielmehr im Wunsch nach vollständiger Kontrolle der Regeln innerhalb der eigenen PKI.

![[Hierachische PKI.png]]

[[Zertifikate]] von wichtigen [[Certificate Authorities|Root-CAs]] sind oft in die verarbeitende Software integriert (z.B. Browser). Problematisch dabei ist jedoch, dass Aussagen über die Anforderungen für die Ausstellung der Zertifikate und damit über ihre Vertrauenswürdigkeit und zulässige Anwendungsbereiche nur über die jeweilige PKI-Dokumentation getroffen werden können.

### Cross-Zertifizierung
Eine Möglichkeit, die Anwendung von [[Zertifikate|Zertifikaten]] über die Grenzen verschiedener hierarchischer PKIs hinweg zu ermöglichen, ist die Cross-Zertifizierung. Dabei stellen sich zwei Zertifizierungsstellen (meist Wurzelinstanzen) gegenseitig ein (Cross-)Zertifikat aus. Im Unterschied zu normalen Zertifikaten in einer hierarchischen PKI drücken Cross-Zertifikate das Vertrauen zweier gleichberechtigter Parteien aus, d. h. die Regelungen der einen [[Certificate Authorities|Wurzelinstanz]] sind für die PKI der anderen Wurzelinstanz nicht verbindlich, oder nur insoweit verbindlich, als sie deren eigenen Regelungen nicht widersprechen. Die Interpretation der durch ein Cross-Zertifikat ausgedrückten Vertrauensbeziehung ist daher manchmal nicht einfach und in vielen Fällen nicht einmal eindeutig.

![[Cross Zertifikate.png]]

<small>
Ein Anwendungsfall war die CA „Let’s Encrypt“. Als diese CA gegründet wurde, war sie in keinem Betriebssystem als vertrauenswürdig eingetragen. Damit die ausgegebenen Zertifikate aber verwendet werden konnten wurde „Lets Encrypt“ Cross zertifiziert (TrustID). Somit konnten in der Übergangszeit die Zertifikate auf Ihre Gültigkeit überprüft werden.
</small>

### Web of Trust
Ein zur Zertifizierungshierarchie komplett konträres Vertrauensmodell wird durch die Verschlüsselungssoftware PGP und die OpenSource-Variante Gnu Privacy Guard genutzt (Beide basieren auf OpenPGP und sind zueinander kompatibel).

Ein [[Zertifikate|Zertifikat]] kann von jedem Benutzer (Web-of-Trust-Mitglied) erzeugt werden. Glaubt ein Benutzer daran, dass ein öffentlicher Schlüssel tatsachlich zu der Person gehört, die ihn veröffentlicht, so erstellt er ein Zertifikat, indem er diesen öffentlichen Schlüssel signiert. Andere Benutzer können aufgrund dieses Zertifikates entscheiden, ob auch sie darauf vertrauen wollen, dass der Schlüssel zum angegebenen Benutzer gehört oder nicht. Je mehr Zertifikate an einem Schlüssel hängen, desto sicherer kann man sein, dass dieser Schlüssel tatsächlich dem angegebenen Eigentümer gehört.

![[web of trust.png]]

Diese Methode hat ganz offensichtliche Nachteile. Es kann niemals hundertprozentig die Gültigkeit eines Zertifikats nachgewiesen werden. Die Signaturen eines Zertifikats können nur schwer auf Ihre Gültigkeit geprüft werden.

Der große Vorteil ist, dass es keine zentrale Autorität geben muss. In vielen lose organisierten Projekten im Internet gibt es nur wenige oder gar keine Strukturen. In einem solchen Fall kann des „Web of Trust“ zu mindestens eine minimale Überprüfbarkeit bringen.