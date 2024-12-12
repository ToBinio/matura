Erweiterung für [[DNS Allgemein|DNS]], die die Authentizität und Integrität von [[DNS Struktur|Domain]]-Antworten mithilfe von [[Digitale Signatur|Digitalen Signaturen]] gewährleistet.

Seit 1995 bekannt, möglich erst nach 15 Jahren.

Verbreitung von DNSSec ist eingeschränkt, überhaupt in Gebieten mit vielen [[DNS Struktur|Top Level Domains]], welche signiert werden müssen.
Root Zone 2010 vollständig von ICANN signiert.

**Vorteil**
- Höhere Sicherheit im Internet (Keine falschen [[IP-Adress|IPs]] zu [[DNS Struktur|Domains]] druch [[Digitale Signatur|Signatur]])

**Mogliches Problem**
- Korruptes Routing (Falsche [[IP-Adress|IP]] durch fehlerhaften Eintrag bekommen)

**Schwachstellen**
- [[DDos|DDos]] wegen höherer Last
- [[DNS Amplification Attack|DNS Amplification Attack]] leichter, da die Antwortlänge größer ist (1 Byte geschickt, 7 Bytes an Opfer)
- [[Public Key|Öffentlicher Schlüssel]] für DNSSec über [[DNS Allgemein|DNS]]. Angriffsmöglichkeit auf Vertrauenskette
- [[DNS Walking|DNS Walking]]
- Stubresolver validieren teilweise Antworten nicht

### DOH
DNS over [[HTTPs]]
Dies hat den vorteil des es den [[HTTPs]] Port verwendet und somit leicht durch [[Firewall|Firewalls]] durchkommt.

### DOT
DNS over TLS

---

> [!cite]-
> ## Originale Quelle
> DNSSec (Domain Name System Security Extensions) ist eine Sicherheitserweiterung für das Domain Name System (DNS). Sie garantiert mit Hilfe von digitalen Signaturen die Echtheit (Authentizität) und Vollständigkeit (Integrität) von DNS-Antworten. Anders gesagt: DNSSec gewährleistet, dass Sie im Internet zu der Domain gelangen, zu der Sie wollen und nicht unbemerkt umgeleitet werden. Obwohl DNSSec in technischen Fachkreisen schon seit 1995 bekannt ist, dauerte es weitere zehn Jahre, bis alle technischen Standards definiert und Implementierungsprobleme gelöst waren – und weitere fünf Jahre, bis die Voraussetzungen zur weltweiten Einführung durch ICANN geschaffen wurden. Das Prinzip von DNSSec basiert auf der lückenlosen Signierung auf allen Ebenen des DNS, sprich von den 13 Root-Servern (ICANN) über die Zonen der jeweiligen Top-Level Domain Registries (wie .at) bis hin zu den einzelnen Domains, die der Registrar oder Internetdienstanbieter (ISP) verwaltet. Die Signierung der Root-Zone durch ICANN erfolgte im Jahr 2010 – seither führen mehr und mehr Registries DNSSec für ihre Top-Level Domain ein. Je nach Kontinent ergibt sich ein anderes Bild der DNSSec-Durchdringung: In Regionen wie Nordamerika, wo es wenige country code Top-Level Domains (ccTLDs) gibt, ist die prozentuelle DNSSec-Durchdringung höher, als auf Kontinenten, wie Asien, mit einer hohen ccTLD-dichte.