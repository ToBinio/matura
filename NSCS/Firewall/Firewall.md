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

## Stateful Paket Filtering

Wenn die Erweiterung state geladen wird, kann die state Zustandsliste zur Filterung herangezogen werden. Es gibt vier Zustände:

* NEW: Dieses Paket beginnt eine neue Verbindung.
* ESTABLISHED: Es handelt sich um ein Folgepaket einer bestehenden Verbindung.
* RELATED: Dieses Paket beginnt eine neue Verbindung, diese steht aber in Verbindung mit einer bestehenden Verbindung (z.B. die Datenverbindung bei FTP, ICMP Fehlermeldungen)
* INVALID: Pakete, welche nicht zugeordnet werden können. Diese können generell verworfen werden.

## Kombination von [[Paketfilter]] und [[Proxy]]
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