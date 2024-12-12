Ist ein nicht sicheres Site-To-Site [[VPN Allgemein|VPN]] Protokoll, da keine Verschlüsselung verwendet wird. 

[[General Routing Encapsulation|GRE]] umfasst verschiedenste Network Layer Protokolle, sowie Broad-/Multicast. Standart [[IPSec Allgemein|IPSec]] [[VPN Allgemein|VPNs]] können nur [[Unicast|Unicast]] verwenden. 

[[General Routing Encapsulation|GRE]] kann zusammen mit [[IPSec Allgemein|IPSec]] verwendet werden, um sicher zwischen [[VPN Allgemein|VPN]]-Gatways zu routen.
Wie genau [[General Routing Encapsulation|GRE]] eingesetzt wird kann durch folgendes beschrieben werden:

**Passanger Protocol**
Hierbei handelt es sich um das originale Datenpaket, welches gesendet wird. Dieses kann [[IP-v4|IPv4]] oder [[IP-v6|IPv6]] sein.

**Carrier Protocol**
[[General Routing Encapsulation|GRE]] ist hier das Carrier Protocol

**Transport Protocol**
Das Protocol, worüber das Datenpaket in Wirklichkeit gesendet wird. Dieses kann [[IP-v4|IPv4]] oder [[IP-v6|IPv6]] sein.

![[GRE.png]]

Beispielsweiser Verwendungszweck:

![[GRE tunnel.png]]

---

> [!cite]-
> ## Originale Quelle
> •Generic Routing Encapsulation (GRE) is a non-secure site-to-site VPN tunneling protocol.
>
> •A GRE tunnel can encapsulate various network layer protocols as well as multicast and broadcast traffic.
>
> •GRE does not by default support encryption; and therefore, it does not provide a secure VPN tunnel.
>
> •A GRE packet can be encapsulated into an IPsec packet to forward it securely to the destination VPN gateway.
>
> •Standard IPsec VPNs (non-GRE) can only create secure tunnels for unicast traffic.
>
> •Encapsulating GRE into IPsec allows multicast routing protocol updates to be secured through a VPN.
>
> The terms used to describe the encapsulation of GRE over IPsec tunnel are passenger protocol, carrier protocol, and transport protocol.
>
> •Passenger protocol – This is the original packet that is to be encapsulated by GRE. It could be an IPv4 or IPv6 packet, a routing update, and more.
>
> •Carrier protocol – GRE is the carrier protocol that encapsulates the original passenger packet.
>
> •Transport protocol – This is the protocol that will actually be used to forward the packet. This could be IPv4 or IPv6.
>
> For example, Branch and HQ need to exchange OSPF routing information over an IPsec VPN. GRE over IPsec is used to support the routing protocol traffic over the IPsec VPN. Specifically, the OSPF packets (i.e., passenger protocol) would be encapsulated by GRE (i.e., carrier protocol) and subsequently encapsulated in an IPsec VPN tunnel.