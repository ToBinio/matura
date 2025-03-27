### Weg einer E-Mail
![[mail_path.png]]

Erklärung der Begriffe:
- MUA (Mail User Agent)
- MTA (Mail Transfer Agent)
- [[DNS Allgemein|DNS Server]]
- MDA (Mail Delivery Agent)
- [[SMTP (Simple Mail Transfer Protocol)|SMTP (Simple Mail Transfer Protocol)]] (Simple Mail Transfer Protocol)
- [[POP3 (Post Office Protocol)|POP3 (Post Office Protocol)]] (Post Office Protocol)
- [[IMAP4 (Internet Message Access Protocol)|IMAP4]] (Internet Message Access Protocol)
- [[MX Eintrag|MX]] (Mail Exchange)

Ablauf für das Senden einer E-Mail:
1. MUA schickt Mail an MTA mittels SMTP
2. MTA findet fremden Mail-Server über MX DNS-Eintrag
3. MTA schickt Mail weiter. Kommt final beim MDA an.
4. MUA des Empfängers kann nun auf die E-Mails mittels POP3 oder IMAP4 zugreifen.

### Verschlüsselung
Es gibt 2 Möglichkeiten.
#### Möglichkeit 1
Verschlüsseltes senden der Mail an den MTA. Dieser entschlüsselt sie und schickt sie weiter. Nicht wirklich sicher.
#### Möglichkeit 2
Mail zur Gänze verschlüsselt mittels PGP (End-To-End) schicken. 

### Authentisierung
Stellt den Beweis seiner Identität dar. Kann durch folgende Möglichkeiten bewiesen werden:
- geheime Informationen (z.B. Passwörter)
- Identifizierungsgegenstand (z.B. Personalausweis)
- Biometrische Merkmale (z.B. Fingerabdruck)
### Authentifizierung
Prüfung der behaupteten Authentisierung
### Authorisierung
Prüfung der Rechte

### Security Maßnahmen
#### [[PGP (Pretty Good Privacy)]]
#### DKIM (DomainKeys Identified Mail)
Mail werden vom Mail-Server signiert. Der [[Public Key|öffentliche Schlüssel]] wird im DNS Eintrag des Mail-Servers hinterlegt.
#### SPF (Sender Policy Framework)
Definition von vertrauenswürdigen Mail-Servern im DNS. Wird verwendet, um Spam- oder Phishingmails herauszufiltern.
#### Weitere Methoden
- Blacklist
- Whitelist
- Graylist
	- Erste einkommende Mail ignorieren (Spam schickt nicht 2 mal)
- Textanalyse
	- Mail bekommt Score und daraus entschieden, ob Spam oder nicht.