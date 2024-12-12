Zwei Methoden:
**Pre-shared Key (PSK)**
Jeder Benutzer muss diesen Schlüssel eintragen. Einfach zum Aufsätzen, skaliert jedoch schlecht -> Muss bei jedem Benutzer eingegeben werden.

**[[RSA|RSA]]**
Hierfür werden [[Zertifikat|Zertifikate]] verwendet. Jeder Teilnehmer muss den anderen Teilnehmer vor der Kommunikation authentifizieren.

![[Pasted image 20241212173823.png]]

---

> [!cite]-
> ## Originale Quelle
There are two IPsec peer authentication methods:
>
> 1.Pre-shared key (PSK) - (PSK) value is entered into each peer manually.
>
> •Easy to configure manually
>
> •Does not scale well
>
> •Must be configured on every peer
>
> 2.Rivest, Shamir, and Adleman (RSA) - authentication uses digital certificates to authenticate the peers.
>
> •Each peer must authenticate its opposite peer before the tunnel is considered secure.