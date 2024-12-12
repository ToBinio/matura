- Virtual private networks (VPNs) to create end-to-end private network connections.
- A VPN is virtual in that it carries information within a private network, but that information is actually transported over a public network.
- A VPN is private in that the traffic is encrypted to keep the data confidential while it is transported across the public network.

![[vpn.png]]

## Benefits

| **Benefit**       | **Description**                                                                                                                                                                                          |
| ----------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Encryption        | Modern VPNs now support encryption features, such as Internet Protocol Security ([[NSCS/VPN/IPsec]]) and Secure Sockets Layer (SSL) VPNs to secure network traffic between sites.                                 |
| **Cost Savings**  | Organizations can use VPNs to reduce their connectivity costs while simultaneously increasing remote connection bandwidth.                                                                               |
| **Security**      | Encryption and authentication protocols protect data from unauthorized access.                                                                                                                           |
| **Scalability**   | VPNs allow organizations to use the internet, making it easy to add new users without adding significant infrastructure.                                                                                 |
| **Compatibility** | VPNs can be implemented across a wide variety of [[WAN]] link options including broadband technologies. Remote workers can use these high-speed connections to gain secure access to corporate networks. |


## managed and deployed
### Enterprise VPNs
common solution for securing enterprise traffic across the internet. [[#Site to Site]] and [[#Remote-Access]] are created and managed by the enterprise using [[NSCS/VPN/IPsec]] and SSL VPNs.
![[Enterprise Managed.png]]
### Service Provider VPNs
created and managed by the provider network. The provider uses Multiprotocol Label Switching (MPLS) at Layer 2 or Layer 3 to create secure channels between an enterprise’s sites, effectively segregating the traffic from other customer traffic.

![[service provider.png]]
# Types of VPN

## SSL vs IPSEC

SSL uses the public key infrastructure and digital certificates to authenticate peers. The type of VPN method implemented is based on the access requirements of the users and the organization’s IT processes. The table compares IPsec and SSL remote access deployments.


| **Feature**                 | **IPsec**                                                                    | **SSL**                                                    |
| --------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------- |
| **Applications supported**  | **Extensive** – All IP-based applications                                    | **Limited** – Only web-based applications and file sharing |
| **Authentication strength** | **Strong** – Two-way authentication with shared keys or digital certificates | **Moderate** – one-way or two-way authentication           |
| **Encryption strength**     | **Strong** – Key lengths 56 – 256 bits                                       | **Moderate to strong** - Key lengths 40 – 256 bits         |
| **Connection complexity**   | **Medium** – Requires VPN client installed on a host                         | **Low** – Requires web browser on a host                   |
| **Connection option**       | **Limited** – Only specific devices with specific configurations can connect | **Extensive** – Any device with a web browser can connect  |

## Remote-Access
Remote-access VPNs let remote and mobile users securely connect to the enterprise.    
Remote-access VPNs are typically enabled dynamically by the user when required and  can be created using either IPsec or SSL.    

- **Clientless VPN connection** -The connection is secured using a web browser SSL connection.
- **Client-based VPN connection** - VPN client software such as Cisco AnyConnect Secure Mobility Client must be installed on the remote user’s end device.
![[remote acess.png]]

## Site to Site
- Site-to-site VPNs connect networks across an untrusted network such as the internet.
- End hosts send and receive normal unencrypted TCP/IP traffic through a VPN gateway.
- The VPN gateway encapsulates and encrypts outbound traffic from a site and sends the traffic through the VPN tunnel to the VPN gateway at the target site. The receiving VPN gateway strips the headers, decrypts the content, and relays the packet toward the target host inside its private network.
![[Site to site.png]]
### GRE
- Generic Routing Encapsulation (GRE) is a non-secure site-to-site VPN tunneling protocol.
- A GRE tunnel can encapsulate various network layer protocols as well as multicast and broadcast traffic.
- GRE does not by default support encryption; and therefore, it does not provide a secure VPN tunnel.
- A GRE packet can be encapsulated into an IPsec packet to forward it securely to the destination VPN gateway.
- Standard IPsec VPNs (non-GRE) can only create secure tunnels for unicast traffic. 
- Encapsulating GRE into IPsec allows multicast routing protocol updates to be secured through a VPN.

The terms used to describe the encapsulation of GRE over IPsec tunnel are passenger protocol, carrier protocol, and transport protocol.
- **Passenger protocol** – This is the original packet that is to be encapsulated by GRE. It could be an IPv4 or IPv6 packet, a routing update, and more.
- **Carrier protocol** – GRE is the carrier protocol that encapsulates the original passenger packet.
- **Transport protocol** – This is the protocol that will actually be used to forward the packet. This could be IPv4 or IPv6.
![[GRE.png]]

For example, Branch and HQ need to exchange OSPF routing information over an IPsec VPN. GRE over IPsec is used to support the routing protocol traffic over the IPsec VPN. Specifically, the OSPF packets (i.e., passenger protocol) would be encapsulated by GRE (i.e., carrier protocol) and subsequently encapsulated in an IPsec VPN tunnel.

![[GRE tunnel.png]]

## Dynamic Multipoint
Site-to-site IPsec VPNs and GRE over IPsec are not sufficient when the enterprise adds many more sites. Dynamic Multipoint VPN (DMVPN) is a Cisco software solution for building multiple VPNs in an easy, dynamic, and scalable manner.
- DMVPN simplifies the VPN tunnel configuration and provides a flexible option to connect a central site with branch sites.
- It uses a hub-and-spoke configuration to establish a full mesh topology.
- Spoke sites establish secure VPN tunnels with the hub site.
- Each site is configure using Multipoint Generic Routing Encapsulation (mGRE). The mGRE tunnel interface allows a single GRE interface to dynamically support multiple IPsec tunnels.
- Spoke sites can also obtain information about each other, and alternatively build direct tunnels between themselves (spoke-to-spoke tunnels).

### Virtual Tunnel Interface
IPsec Virtual Tunnel Interface (VTI) simplifies the configuration process required to support multiple sites and remote access.
- IPsec VTI configurations are applied to a virtual interface instead of static mapping the IPsec sessions to a physical interface.
- IPsec VTI is capable of sending and receiving both IP unicast and multicast encrypted traffic. Therefore, routing protocols are automatically supported without having to configure GRE tunnels.
- IPsec VTI can be configured between sites or in a hub-and-spoke topology.
![[IpSec Virtual Tunnel Interface.png]]

### [[Modern WAN#Multiprotocol Label Switching (MPLS)|MPLS]] VPNS
Today, service providers use [[Modern WAN#Multiprotocol Label Switching (MPLS)|MPLS]] in their core network. Traffic is forwarded through the MPLS backbone using labels. Traffic is secure because service provider customers cannot see each other’s traffic.
- MPLS can provide clients with managed VPN solutions; therefore, securing traffic between client sites is the responsibility of the service provider.
- There are two types of MPLS VPN solutions supported by service providers:
	- **[[OSI Model|Layer 3 MPLS VPN]]** - The service provider participates in customer routing by establishing a peering between the customer’s routers and the provider’s routers.
	- **[[OSI Model|Layer 2 MPLS VPN]]** - The service provider is not involved in the customer routing. Instead, the provider deploys a Virtual Private LAN Service (VPLS) to emulate an Ethernet multiaccess LAN segment over the MPLS network. No routing is involved. The customer’s routers effectively belong to the same multiaccess network.

---
## [[NSCS/VPN/IPsec]]