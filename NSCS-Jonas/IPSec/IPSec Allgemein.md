IPSec ist ein IETF Standard, welcher definiert, wie [[VPN Allgemein|VPNs]] innerhalb IP-Netzwerken sicher ein können. IPSec sichert und authentifiziert Pakete zwischen Quelle und Ziel.

| Bereich                                    | Beschreibung                                                            |
| ------------------------------------------ | ----------------------------------------------------------------------- |
| [[IPSec Protocol\|IPSec Protokol]]         | Das verwendete IPSec Protokol                                           |
| [[IPSec Vertraulichkeit\|Vertraulichkeit]] | Verwendet Verschlüsselung                                               |
| [[IPSec Integrität\|Integrität]]           | Verwendet Hashing um nach Veränderungen zu überprüfen                   |
| [[IPSec Authentizität\|Authentizität]]     | Verwendet Internet Key Exchange und Quelle und Ziel zu authentifizieren |
| [[IPSec Diffie-Hellman\|Diffe-Hellman]]    | Wird verwendet für den Schlüsselaustausch                               |

IPSec ist an keine Regeln gebunden und kann sich somit gut an neue Technologien anpassen:

![[Pasted image 20241212172253.png]]

---

> [!cite]-
> ## Originale Quelle
> IPsec is an IETF standard that defines how a VPN can be secured across IP networks. IPsec protects and authenticates IP packets between source and destination and provides these essential security functions:
>
> •Confidentiality - Uses encryption algorithms to prevent cybercriminals from reading the packet contents.
>
> •Integrity - Uses hashing algorithms to ensure that packets have not been altered between source and destination.
>
> •Origin authentication - Uses the Internet Key Exchange (IKE) protocol to authenticate source and destination.
>
> •Diffie-Hellman – Used to secure key exchange.
>
> •IPsec is not bound to any specific rules for secure communications.
>
> •IPsec can easily integrate new security technologies without updating existing IPsec standards.
>
> •The open slots in the IPsec framework shown in the figure can be filled with any of the choices that are available for that IPsec function to create a unique security association (SA).