## Proxy
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