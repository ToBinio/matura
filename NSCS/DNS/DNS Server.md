### Typen
- Primary Server
- Slave Server

Der Slave Server repliziert den Primary Server und kann diesem Last abnehmen.

### Lokales Setup
Meistens ist der DNS Server auch ein [[DNS Resolver|DNS Resolver]]. Falls er es selber nicht auflösen kann, schickt er es an einen anderen [[DNS Resolver|DNS Resolver]] weiter. 
Wird verwendet um zum Beispiel lokalen dynamisch vergebenen [[IP-Adress|IPs]] [[DNS Struktur|Domains]] zuzuweisen.

### Protokolle
DNS Server können [[TCP|TCP]] als auch [[UDP|UDP]] zum synchronisieren verwenden.

---
> [!cite]-
> ## Originale Quelle
> Es wird dabei in den Primary Server und Slave Server unterschieden. Der Slave Server kann die Aufgabe des Primary Servers übernehmen und synchronisiert sich mit dem Primary Server. Der Slave Server kann zum Lastausgleich und zur Redundanz genutzt werden. Meistens wird im Netzwerk ein DNS Server eingesetzt, welcher gleichzeitig ein DNS Resolver ist oder die Anfragen an einen DNS Resolver weiterleiten kann, wenn die Top Level Domain nicht im Zuständigkeitsbereich des Servers liegt. Dieser Server kann die Anfrage für die interne Domain Lokal auflösen. In vielen Fällen ist dieser mit dem DHCP Dienst gekoppelt, damit den Dynamischen IP Adressen im Netzwerk die passenden DNS und rDNS Einträge verpasst werden können. Dies ist WLAN fähigen Geräten, wie Laptops extrem nützlich.