```
@   IN  SOA dns.foxplex.local. mail.foxplex.local. (
        1       ; Serial
        604800  ; Refresh
        86400   ; Retry
        2419200 ; Expire
        86400   ; Negative Cache TTL
    )

; Nameserver
@   IN  NS  dns.foxplex.local.

; Mailserver
@   IN  MX  10 mail.foxplex.local.

; A-Records
dns         IN  A   192.168.1.1
mail        IN  A   192.168.1.2
client1     IN  A   192.168.1.10
client2     IN  A   192.168.1.11

```

- @: Platzhalter für die Domain
- SOA: Start Of Authority
	Enthält grundlegende Informationen über die Zone:
    
    - Zuständiger Server und E-Mail-Adresse des Administrators (erster Punkt durch „@“ ersetzt).
    - **Serial**: Seriennummer des Eintrags.
    - **Refresh**: Gültigkeitsdauer der Informationen.
    - **Retry**: Intervall für Wiederholungsversuche bei Fehlern.
    - **Expire**: Zeit, nach der der Eintrag ungültig wird, wenn der Server ausfällt.
    - **Negative Cache TTL**: Dauer der Gültigkeit einer "keine Domain gefunden"-Meldung.
- A: [[IP-v4|IPv4]]
- AAAA: [[IP-v6|IPv6]] 
- NS: Name Server
- MX: Mail
- CNAME: [[DNS Struktur|Domain]]
- TXT: Texteinträge
- LOC: Positionsangabe
- NAPTR: Adressen von Server und weitere Information wie Dienste und URIs ausgeliefert 
- RP: Verantwortliche Person

---

> [!cite]-
> ## Originale Quelle
> Zonen Eintrag vom Bind:
> 
> @ Platzhalter für die Domain, für welche die Zonendatei zuständig ist. SOA Start Of Authority. Damit wird festgelegt, um welches Server es sich handelt und wie die EMail Adresse des zuständigen Administrators handelt, dabei wird der ersten Punkt durch ein „AT“ Symbol ersetzt. Es wird auch die Serial Nummer des Eintrages festgelegt (Serial) , wie lange die Informationen gültig sind (Refresh), sowie in welchen Abständen es im Fehlerfall wieder versucht werden soll (Retry). Dann gibt es noch den Expire Eintrag, welcher Festlegt, wann der Eintrag ungültig wird, wenn der Server ausfällt. Die Negative Cache TTL gibt an, wie lange die Information, keine Domain gefunden, gültig ist. A Steht für die IPv4 Adresse zu der Domain AAAA Steht für die IPv6 Adresse zu der Domain NS Steht für den Name Server. Dieser muss über die Domain angegeben werden und dazu muss es einen passenden A Eintrag geben MX Steht für den Mail Eingangsserver. Dieser muss über die Domain angegeben werden und dazu muss es einen passenden A Eintrag geben CNAME Steht für einen Alternativnamen für die Domain. „Spitzname“ TXT Texteinträge, werden unteranderem für Mail und ENUM verwendet. (siehe 3.) LOC Positionsangabe NAPTR Adressen von Server und weitere Information wie Dienste und URIs ausgeliefert RP Verantwortliche Person