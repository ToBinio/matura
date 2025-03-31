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
Sind eine Bestimmte implementation zu Paketfiltern im Linux kernel
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

Weg eines Paketes im Kernel
![[Weg im Kernel.png]]