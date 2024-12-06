
## Zusammenfassung
DNSSEC (Domain Name System Security Extensions) verbessert die Sicherheit von DNS, indem es die Authentizität und Integrität von DNS-Antworten durch digitale Signaturen garantiert. Dies schützt vor unbemerkten Umleitungen und sorgt für mehr Vertrauen im Internet.

**Vorteile:**

- Bietet mehr Sicherheit für Internetnutzer.
- Hilft Domain-Inhabern, ihre Domains vor Angriffen zu schützen.
- Unterstützt sensible Datenübertragungen, z. B. bei Online-Zahlungen.

**Einschränkungen:**

- Schützt nur Nameserver-Abfragen, nicht die gesamte Kommunikation (z. B. Routing-Angriffe).
- Kombiniert mit TLS bleiben Schwachstellen wie gefälschte Zertifikate möglich.

**Schwachstellen:**

- Erhöht die Gefahr von DoS-Angriffen durch mehr Serverlast.
- Vergrößert die Angriffsfläche für Amplification Attacks.
- Vertrauensketten können durch Angriffe auf die Verteilung öffentlicher Schlüssel gefährdet werden.
- Zonen können durch DNSSEC Walking ausgelesen werden (NSEC3 erschwert dies).
- Stubresolver sind anfällig für Angriffe auf die Kommunikation oder kompromittierte Nameserver.

DNSSEC ist nützlich, entfaltet sein volles Potenzial jedoch erst in Kombination mit weiteren Schutzmaßnahmen wie DANE.

---
## Langform
DNSSec (Domain Name System Security Extensions) ist eine Sicherheitserweiterung für das Domain Name System (DNS). Sie garantiert mit Hilfe von digitalen Signaturen die Echtheit (Authentizität) und Vollständigkeit (Integrität) von DNS-Antworten. Anders gesagt: DNSSec gewährleistet, dass Sie im Internet zu der Domain gelangen, zu der Sie wollen und nicht unbemerkt umgeleitet werden. Obwohl DNSSec in technischen Fachkreisen schon seit 1995 bekannt ist, dauerte es weitere zehn Jahre, bis alle technischen Standards definiert und Implementierungsprobleme gelöst waren – und weitere fünf Jahre, bis die Voraussetzungen zur weltweiten Einführung durch ICANN geschaffen wurden.

Das Prinzip von DNSSec basiert auf der lückenlosen Signierung auf allen Ebenen des DNS, sprich von den 13 Root-Servern (ICANN) über die Zonen der jeweiligen Top-Level Domain Registries (wie .at) bis hin zu den einzelnen Domains, die der Registrar oder Internetdienstanbieter (ISP) verwaltet. Die
Signierung der Root-Zone durch ICANN erfolgte im Jahr 2010 – seither führen mehr und mehr Registries DNSSec für ihre Top-Level Domain ein. Je nach Kontinent ergibt sich ein anderes Bild der DNSSec-Durchdringung: In Regionen wie Nordamerika, wo es wenige country code Top-Level Domains (ccTLDs) gibt, ist die prozentuelle DNSSec-Durchdringung höher, als auf Kontinenten, wie Asien, mit einer hohen ccTLD-dichte.

#### Wem nützt DNSSec?
- Die Internet-Community profitiert von mehr Sicherheit im Internet
- Registrare können ihren Kunden neue Dienstleistungen anbieten
- Zugangsprovider ermöglichen ihren Kunden unverfälschte Domain-Abfragen
- Domain-Inhaber schützen ihre Domain vor ungewollten DNS-Attacken
- Institutionen mit Online-Zahlungsverkehr (z.B. Banken, Webshops etc.) oder sensiblen Daten-Transaktionen können ihre Kunden vor Missbrauch schützen – und Vertrauen im Netz gewinnen

Durch DNSSEC werden lediglich die Nameserverabfragen gesichert. Dies ist hauptsächlich in Verbindung mit verschlüsselnden Übertragungsprotokollen wie TLS sinnvoll. Die Kombination aus DNSSEC mit TLS hat aber noch Schwachstellen. Korruptes Routing könnte beispielsweise Pakete, die an eine mit DNSSEC korrekt ermittelte Ziel-IP-Adresse gesendet werden, an einen falschen Rechner zustellen. Kann sich dieser Rechner durch ein kompromittiertes oder versehentlich ausgestelltes Zertifikat ausweisen, fällt dies nicht auf. An dieser Stelle setzt zum Beispiel DANE an, um das
Zusammenspiel zwischen DNSSEC und TLS zu sichern.

#### Sicherheitsrelevante Schwachstellen von DNSSEC
- Denial-of-Service-Angriffe auf Nameserver werden durch DNSSEC nicht verhindert, sondern auf Grund der höheren Last auf den Servern sogar erleichtert.
- DNS Amplification Attacks unter Ausnutzung der öffentlichen DNS-Infrastruktur werden effektiver, da DNS-Antworten mit DNSSEC deutlich länger sind.
- Die öffentlichen Schlüssel zur Verifizierung werden ebenfalls über das DNS-System verteilt. Damit ergeben sich Angriffsmöglichkeiten auf die Vertrauensketten. Dies kann verhindert werden, wenn der öffentliche Schlüssel des Vertrauensursprungs (engl.: Trust Anchor) auf anderem Wege als der DNS-Infrastruktur (zum Beispiel mit dem Betriebssystem oder der Server- bzw. Clientsoftware) verteilt wird.
- Mittels DNSSEC Walking kann der Inhalt von Zonen vollständig ausgelesen werden (erschwert durch NSEC3).
- Da Stubresolver oft nicht selbst die DNS-Antworten validieren, kann ein Angriff auf der Kommunikationsstrecke zu ihrem rekursiven Nameserver erfolgen. Auch kann der rekursive Nameserver selbst kompromittiert sein