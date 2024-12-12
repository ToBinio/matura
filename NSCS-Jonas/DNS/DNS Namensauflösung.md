[[DNS Resolver|DNS Resolver]] können [[DNS Struktur|Domains]] auf [[IP-Adress|IPs]] auflösen. Aufgrund von Geschwindigkeit und Lastverringerung werden Ergebnisse mit einer [[TTL|TTL]] (Time To Live) gecached.  

### Ablauf
1. Anfrage an [[DNS Allgemein|DNS Server]]
2. [[IP-Adress|IP]] falls im cache. Sonst wird die Domain hierarchisch abgefragt bis IP gefunden.
3. Warten bis gefunden
4. [[IP-Adress|IP]] der [[DNS Struktur|Domain]]
5. [[DNS Allgemein|DNS Server]] speichert [[IP-Adress|IP]] im Cache

### Reserve DNS
Möglichkeit [[DNS Struktur|Domain]] zu [[IP-Adress|IP]] zu finden. "x3.x2.x1.x0.in.addr.arpa" lieftert den PRT Eintrag der [[DNS Struktur|Domain]] zurück.

### Entwicklung
[[DNS Allgemein|DNS]] wird auch für Mail-Service (MX), TXT-Einträge, etc verwendet.

---

> [!cite]-
> ## Originale Quelle
> Über einen DNS Resolver werden Domains auf die IP Adressen bzw. andere Einträge aufgelöst. Dabei wird bei den meisten Resolvern das Ergebnis aus Performance und Lastgründen zwischen gespeichert. Dazu wird jeder Eintrag vom DNS Server mit einer TTL (Time To Live) versehen, solange ist dann der Eintrag gültig. a. Namensauflösung 1. Der Client sendet eine Anfrage an den lokalen Name Server 2. Wenn der Server die Antwort kennt, antwortet dieser direkt, wenn nicht wird die Top Level Domain bei einem der DNS Root Server abgefragt. Dieser liefert dann die IP des zuständigen DNS Server für die nächste Stufe. 3. Es wird solange die Hierarchie abgearbeitet, bis der für die Domain zuständige DNS Server gefunden wurde. 4. Dieser Server liefert den gewünschten Eintrag zu der Domain an den lokalen DNS Server. (IP Adresse, Telefon Nummer, etc) 5. Der Lokale DNS Server legt die Information im Cache ab und liefert diese an den Client aus.
>
> Es gibt die Möglichkeit eine IP Adresse in einen DNS Namen zurück aufzulösen. Dazu wird der Bereich in-addr.apra verwendet. Z.B. 1.1.1.1.in-addr.arpa Die IP wird dazu in umgekehrter Reihenfolge bei in-addr.arpa angehängt. Dann wird als Antwort der PTR Eintrag geliefert, welcher die dazugehörige Domain liefert. Das Domain System wird mittlerweile auch zum Verteilen von anderen Informationen als IP Adressen genutzt. Es wird zum Beispiel zum auch beim E-Mail Austausch verwendet. Mit dem MX Eintrag, wird der Mail Server für die Domain bekannt gegeben. Über den TXT Eintrag kann bei E-Mail auch der Öffentliche Schlüssel für die Authentifizierung des Mail Server bekannt gegeben werden. Bei der Telefon wird das DNS System auch verwendet, um Telefonnummer auf SIP URIs umzusetzen. Dieses Verfahren wird ENUM genannt und nutzt die E164.arpa Domain. Dieses Verfahren kommt jedoch in Österreich nur selten zum Einsatz.