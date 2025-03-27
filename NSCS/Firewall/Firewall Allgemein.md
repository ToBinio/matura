Firewalls verhindern ungewollten Zugriff auf Netzwerkdienste.
Hier kann unterschieden werden zwischen:
- Persönliche Firewall
- Externe Firewall
- Paketfilter
- Proxy
- Proxy Server
- Transparenter Proxy
- Reverse Proxy
- Application Gateway
### Persönliche Firewall
Diese befindet sich direkt auf dem Gerät das geschützt werden soll. So haben alle Windows-Geräte eine, welche den Netzwerkverkehr des PCs kontrollieren. Diese sollten aber nur für einen zusätzlichen Schutz sorgen.

### Externe Firewall
Diese befinden sich nicht auf dem Gerät, sondern separater Hardware, welche sich zwischen 2 Netzwerksegmenten befindet. Diese ist von den Endgeräten unabhängig.
### Paketfilter
![[paketfilter.png]]
Stellt einen modifizierten Router dar, welcher Paketheader überprüft und entscheidet, ob er es weiterleitet oder nicht. Arbeiten auf Layer 3 und 4 der [[OSI Model]]

Diese können folgende Informationen überprüfen:
- Protokoll (ICMP, UDP, TCP)
- Source-Adresse
- Ziel-Adresse
- Flags (Hauptsächlich TCP Verbindungsaufbau)
- Zusätzliche Regeln, wie stateful packet tracing (ESTABLISHED)
#### Vorteile
- Einfach erweiterungsfähig für neue Protokolle & Dienste
- Transparente Firewall: Clients & Server müssen nicht angepasst werden
- Geringe Verzögerung der Pakete
#### Nachteile
- Stateful packet tracing ist sehr aufwendig
- Programme können nicht geschützt werden, die eine falsche Konfiguration aufweisen und damit einen direkten Zugriff auf das Rechnersystem zulassen
#### IP-Tables
Es werden Regeln definiert, welche aus einem Muster und einer Aktion bestehen. Ein Muster definiert auf welche Pakete die Regel angewendet werden soll, die Aktion was mit dem Paket passieren soll.

 Policies (glaube das sind Aktionen) können einer der folgenden zwei sein:
 - ACCEPT: Paket wird angenommen
 - DROP: Paket wird verworfen. Sollte default sein.
#### Chains
Regeln werden als Chain dargestellt. Chains werden Tables zugewiesen. Hier gibt es 3 Tables:
1. filter
	- Standardtabelle, beinhaltet INPUT, FORWARD und OUTPUT Chain
2. nat
	- Für Port-Forwarding und Address-Umsetzung. Beinhaltet die PREROUTING, OUTPUT und POSTROUTING Chain
3. mangle
	- Beinhaltet die PREROUTING und OUTPUT Chain

### Proxy
![[proxy.png]]
Grundsätzlich kann ein Proxy mehrere Funktionen haben:
- Vermittler
- Sicherheitsmaßnahme
- Cache
### Proxy Server (Dedicated Proxy)
Dieser steht als Vermittler zwischen der Client-Server Verbindung. Der Proxy kann die Kommunikation analysieren und sogar dessen Inhalt ändern. Der Zielserver sieht daher nicht die Identität des Clients, sondern des Proxy-Servers. Es können auch Daten auf dem Proxy gespeichert werden, um die Bearbeitungsdauer zu verkürzen.
### Transparenter Proxy
Da ein normaler Proxy Einstellungen am Client benötigt, ist dieser im Netzwerk nicht transparent (z.B. Anmeldung beim Proxy). Befindet sich der Proxy direkt am Gateway entfallen die Einstellungen am Client.
### Reverse Proxy
![[reverse_proxy.png]]
Läuft auf der Server-Seite und kann zum cachen verwendet werden. Ebenfalls versteckt der reverse Proxy die Identität der Services hinter ihm.
### Applikationsfilter (Application Level Filter) (Application Gateway)
Diese arbeiten auf Layer 7 (Application) [[OSI Model]] als anwendungsbezogener Filter. Für jeden Dienst (FTP, HTTP, usw) meist einen eigenen. 
#### Vorteile
- differenzierte Authentifikation und Überprüfung
- Nutzung von Diensten lässt sich einschränken
#### Nachteile
- rechenintensiv
- Neue Dienste problematisch da es keinen Proxy dafür gibt

### Kombination von Paketfilter und Proxy
![[combination_paketfilter_proxy.png]]
Aufgaben des Proxy:
- Vermitteln der Pakete des LANs ins Internet

Aufgaben des Paketfilter:
- sichere (gewollten) Protokolle reinlassen
- Verbindungen nur mit dem Proxy erlauben
- bestimmte Protokolle nur vom Proxy aus rauslassen
- nur bestimmte Protokolle aus LAN rauslassen

Probleme:
- Hoches Sicherheitsrisiko beim Proxy (Kontrolle durch Hacker)
- Gehostete Dienste großes Risiko da (Kontrolle durch Hacker) 