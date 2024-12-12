Es ist ein Cisco Produkt, welches das Erstellen von mehreren verbundenen [[VPN Allgemein|VPNs]] erleichtert. Hierfür gibt es zentralen Standort und Branch-Standorte. Hier wird eine hub-and-spoke Konfiguration verwendet. Jeder Spoke baut einen sicheren [[VPN Allgemein|VPN]]-Tunnel mit dem Hub auf. Jeder Standort verwendet Multipoint Generic Routing Encapsulation (m[[General Routing Encapsulation|GRE]]), wodurch ein einzelnes [[General Routing Encapsulation|GRE]] Interface mehrere [[IPSec Allgemein|IPSec]] Interfaces unterstützt. Spokes können ebenfalls Daten über andere Spokes herausfinden und direkte Tunnel zwischen sich erstellen (spoke-to-spoke Tunnel)

---

> [!cite]-
> ## Originale Quelle
> Site-to-site IPsec VPNs and GRE over IPsec are not sufficient when the enterprise adds many more sites. Dynamic Multipoint VPN (DMVPN) is a Cisco software solution for building multiple VPNs in an easy, dynamic, and scalable manner.
>
> •DMVPN simplifies the VPN tunnel configuration and provides a flexible option to connect a central site with branch sites.
>
> •It uses a hub-and-spoke configuration to establish a full mesh topology.
>
> •Spoke sites establish secure VPN tunnels with the hub site.
>
> •Each site is configure using Multipoint Generic Routing Encapsulation (mGRE). The mGRE tunnel interface allows a single GRE interface to dynamically support multiple IPsec tunnels.
>
> •Spoke sites can also obtain information about each other, and alternatively build direct tunnels between themselves (spoke-to-spoke tunnels).

