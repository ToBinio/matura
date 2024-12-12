Vereinfacht die Konfiguration von mehreren Standorten
- Konfigurationen werden auf ein virtuelles, statt physischen Interface angewendet. 
- Ermöglicht Unicast und Multicast ohne [[General Routing Encapsulation|GRE]] manuell zu konfigurieren.
- Kann zwischen Standorten oder mittels hub-and-spoke konfiguriert werden.

![[IpSec Virtual Tunnel Interface.png]]

---

> [!cite]-
> ## Originale Quelle
> IPsec Virtual Tunnel Interface (VTI) simplifies the configuration process required to support multiple sites and remote access.
>
> •IPsec VTI configurations are applied to a virtual interface instead of static mapping the IPsec sessions to a physical interface.
>
> •IPsec VTI is capable of sending and receiving both IP unicast and multicast encrypted traffic. Therefore, routing protocols are automatically supported without having to configure GRE tunnels.
>
> •IPsec VTI can be configured between sites or in a hub-and-spoke topology.