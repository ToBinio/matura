Benutzer weiß nicht, dass ein [[VPN Allgemein|VPN]] existiert. [[VPN Allgemein|VPN]] wird nur zwischen [[VPN Allgemein|VPN]]-Gatways verwendet.

![[Site to site.png]]

**Site-To-Site IPSec VPN**
Wird verwendet für eine Kommunikation über ein nicht vertrauliches Netzwerk. Hosts bekommen unverschlüsselte Daten von einem [[VPN Allgemein|VPN]]-Gateway. Ver/Entschlüsselung wird von den [[VPN Allgemein|VPN]]-Gateways durchgeführt.

---

> [!cite]-
> ## Originale Quelle
> A site-to-site VPN is terminated on VPN gateways. VPN traffic is only encrypted between the gateways. Internal hosts have no knowledge that a VPN is being used.
>
> •Site-to-site VPNs connect networks across an untrusted network such as the internet.
>
> •End hosts send and receive normal unencrypted TCP/IP traffic through a VPN gateway.
>
> •The VPN gateway encapsulates and encrypts outbound traffic from a site and sends the traffic through the VPN tunnel to the VPN gateway at the target site. The receiving VPN gateway strips the headers, decrypts the content, and relays the packet toward the target host inside its private network.