Verwaltet vom [[Enterprise VPN|Enterprise]] und verwendet [[Multiprotocol Label Switching|Multiprotocol Label Switching (MPLS)]] um Kunden-Verkehr von anderen Kunden-Verkehr zu trennen.

![[Pasted image 20241212153941.png]]

Service Provider verwenden IPSec VTI:

**Layer 3 MLPS VPN**
Der Service Provider ist beim Routen der Pakete der Kunden involviert.

**Layer 2 MLPS VPN**
Der Service Provider ist nicht beim Routen der Pakete der Kunden involviert. Der Provider erstellt ein Virtual Private Lan Service, wo die Router des Kunden beinhaltet sind.

---

> [!cite]-
> ## Originale Quelle
> •created and managed by the provider network. The provider uses Multiprotocol Label Switching (MPLS) at Layer 2 or Layer 3 to create secure channels between an enterprise’s sites, effectively segregating the traffic from other customer traffic.
>
> Today, service providers use MPLS in their core network. Traffic is forwarded through the MPLS backbone using labels. Traffic is secure because service provider customers cannot see each other’s traffic.
>
> •MPLS can provide clients with managed VPN solutions; therefore, securing traffic between client sites is the responsibility of the service provider.
>
> •There are two types of MPLS VPN solutions supported by service providers:
>
> •Layer 3 MPLS VPN - The service provider participates in customer routing by establishing a peering between the customer’s routers and the provider’s routers.
>
> •Layer 2 MPLS VPN - The service provider is not involved in the customer routing. Instead, the provider deploys a Virtual Private LAN Service (VPLS) to emulate an Ethernet multiaccess LAN segment over the MPLS network. No routing is involved. The customer’s routers effectively belong to the same multiaccess network.