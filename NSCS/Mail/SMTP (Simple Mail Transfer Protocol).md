Protokoll zum Austausch von Daten zwischen MTAs (Mail Transfer Agent) über den Port 25.

SMTP ist ein textbasiertes Protokoll ohne Authentifizierung und Verschlüsselung, weshalb es die erweiterte Version ESMTP. 

#### Verbindungsaufbau in SMTP
1. Abfrage des Mail-Servers mit telnet
	- 220 service ready: Mail-Server bestätigt
2. HELO _NAME_ an Mail-Server
	- Client nennt seinen Namen
	- 250 OK: Mail-Server bestätigt
3. MAIL FROM: _ABSENDER_
	- 250 OK: Mail-Server bestätigt
4. RCPT TO: _EMPFÄNGER_
	- 250 OK: Mail-Server bestätigt
5. DATA
	- Client kündigt Email-Inhalt an
	- 354 start mail input: Mail-Server bestätigt und ist bereit für Input
6. _DATEN_
	- 250 OK: Server bestätigt
7. QUIT
	- 221 BYTE: Server beendet die Verbindung

#### Statuscodes von Mail-Server
- 1XX
	- Server hat akzeptiert aber noch nicht tätig
- 2XX
	- Server hat erfolgreich ohne Fehler durchgeführt
- 3XX
	- Server hat Anforderungen verstanden, braucht aber mehr Informationen
- 4XX
	- Server hat temporären Fehler erkannt. Kann möglicherweise durch Wiederholung erfolgreich ausgeführt werden.
- 5XX
	- Server hat fatalen Fehler festgestellt. Kann nicht verarbeitet werden.
#### ESMTP
Diese Erweiterung kann Authentifizierung, sowie Verschlüsselung mittels TLS zur Verfügung. 

Es muss aber nicht am ganzen weg sichergestellt werden, weshalb für End-To-End Verschlüsselung PGP verwendet werden soll.

Für ESMTP muss der Client die Kommunikation mit EHELO und nicht HELO beginnen. Danach Teilt der Server mit, welche Erweiterungen er unterstützt:
##### STARTTLS (Secure SMTP over TLS)
Er nach dem STARTTLS Befehl ist die Kommunikation Verschlüsselt, es wird keine neue Verbindung aufgebaut. Server verwenden aber "TLS, wenn möglich verwenden" und Nutzer weiß nicht, ob die Kommunikation noch verschlüsselt ist.
##### DSN (Delivery Status Notification)
Mail-Server sendet eine Mail, um den Absender über den Zustellstatus zu informieren. Meistens werden nur Mails geschickt, falls die Mail nicht zugestellt werden konnte. Nutzer kann anfordern, dass er eine Mail bekommt, wenn die Mail zugestellt wurde.
##### AUTH (SMTP-Auth)
Ermöglicht Authentifizierung des Clients:
- PLAIN
	- Unverschlüsselter Benutzername und Passwort in Base64
- LOGIN
	- Unverschlüsselter Benutzername und Passwort in Base64
	- Jedoch in 2 Schritten übertragen
- CRAM-MD5
	1. Server sendet Challenge (Zeichenkette) an Client
	2. Client antwortet mit "_BENUTZERNAME_ _DIGEST_". DIGEST ist ein MD5-Hash vom Passwort und der Challenge
	3. Server rechnet nach und überprüft
- NTLM
	1. Client sendet Benutzername an den Server
	2. Server schickt als Challenge eine Zahl
	3. Client verschlüsselt Challenge mit dem Hash des Passwort
	4. Server rechnet nach und überprüft
	- Passwort wird nicht übertragen

### SMTPS