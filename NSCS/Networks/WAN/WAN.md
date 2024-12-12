Wide Area Network
see [[Comparisons]]

---
### Private WAN
A private WAN is a connection that is dedicated to a single customer.

Private WANs provide the following:
- Guaranteed service level
- Consistent bandwidth
- Security

### Public WAN
A public WAN connection is typically provided by an ISP or telecommunications service provider using the internet. In this case, the service levels and bandwidth may vary, and the shared connections do not guarantee security.

---
## Topologies

<small>
Large networks usually deploy a combination of these topologies.
</small>

### Point-to-Point Topology
![[Point to Point.png]]
- Employs a point-to-point circuit between two endpoints.
- Involves a Layer 2 transport service through the service provider network.
- The point-to-point connection is transparent to the customer network.

<small>
It can become expensive if many point-to-point connections are required.
</small>

### Hub-and-Spoke Topology
![[Hub and Spoke.png]]
- Enables a single interface on the hub router to be shared by all spoke circuits.
- Spoke routers can be interconnected through the hub router using virtual circuits and routed subinterfaces.
- Spoke routers can only communicate with each other through the hub router.

<small>
The hub router represents a single point of failure. If it fails, inter-spoke communication also fails.
</small>

### Dual-homed Topology
![[Dual homed.png]]

- Offers enhanced network redundancy, load balancing, distributed computing and processing, and the ability to implement backup service provider connections.
- More expensive to implement than single-homed topologies. This is because they require additional networking hardware, such as additional routers and switches.
- More difficult to implement because they require additional, and more complex, configurations.

### Fully Meshed Topology
![[Fully Meshed.png]]
- Uses multiple virtual circuits to connect all sites
- The most fault-tolerant topology

### Partially Meshed Topology
![[Partally Meshed.png]]
- Connects many but not all sites

---
## Carrier Connections
<small>
Another aspect of WAN design is how an organization connects to the internet. An organization usually signs a service level agreement (SLA) with a service provider. The SLA outlines the expected services relating to the reliability and availability of the connection.    
</small>

<small>
The service provider may or may not be the actual carrier. A carrier owns and maintains the physical connection and equipment between the provider and the customer. Typically, an organization will choose either a single-carrier or dual-carrier WAN connection.
</small>

A **single-carrier connection** is when an organization connects to only one service provider. An SLA is negotiated between the organization and the service provider.
![[single Carrier.png]]

A **dual-carrier connection** provides redundancy and increases network availability. The organization negotiates separate SLAs with two different service providers.
![[dual carrier.png]]

## Evolving Networks
```
see if anybody carse about that (Presentation page 13-17)
``` 

---
## Operations
### WAN Standards
Modern WAN standards are defined and managed by a number of recognized authorities including the following
[[Standart Organasitations|TIA/EIA, ISO, IEEE]]

### OSI Modell
Most WAN standards focus on the physical layer and the data link layer.

[[OSI Model|Layer 1 Protocols]]
- Synchronous Digital Hierarchy (SDH)
- Synchronous Optical Networking (SONET)
- Dense Wavelength Division Multiplexing (DWDM)

[[OSI Model|Layer 2 Protocols]]
- Broadband (i.e., DSL and Cable)
- Wireless
- [[Modern WAN#Ethernet WAN]] (Metro Ethernet)
- Multiprotocol Label Switching (MPLS)
- Point-to-Point Protocol (PPP) (less used)
- High-Level Data Link Control (HDLC) (less used)
- Frame Relay (legacy)
- Asynchronous Transfer Mode (ATM) (legacy)

### Terminology

| WAN Term                                | Description                                                                                                                                         |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Data Terminal Equipment (DTE)**       | Connects the subscriber LANs to the WAN communication device                                                                                        |
| **Data Communications Equipment (DCE)** | Device used to communicate with the provider                                                                                                        |
| **Customer Premises Equipment (CPE)**   | This is the DTE and DCE devices located on the enterprise edge                                                                                      |
| **Point-of-Presence (POP)**             | The point where the subscriber connects to the service provider network                                                                             |
| **Demarcation Point**                   | The physical location in a building or complex that officially separates the CPE from service provider equipment.                                   |
| **Local Loop (last mile)**              | The copper or fiber cable that connects the CPE to the CO of the service provider                                                                   |
| **Central office (CO)**                 | The local service provider facility or building that connects the CPE to the provider network                                                       |
| **Toll network**                        | Includes backhaul, long-haul, all-digital, fiber-optic communications lines, switches, routers, and other equipment inside the WAN provider network |
| **Backhaul network**                    | Connects multiple access nodes of the service provider network                                                                                      |
| **Backbone network**                    | Large, high-capacity networks used to interconnect service provider networks and to create a redundant network.                                     |
![[terminology.png]]

### WAN Devices

| **WAN Device**                     | **Description**                                                                                                   |
| ---------------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| **Voiceband Modem**                | Dial-up modem – uses telephone lines<br>    <br>Legacy device                                                     |
| **DSL Modem / Cable Modem**        | Collectively known as broadband modems, these high-speed digital modems connect to the DTE router using Ethernet. |
| **CSU/DSU**                        | Digital-leased lines require a CSU and a DSU. It connects a digital device to a digital line.                     |
| **Optical Converter**              | Connect fiber-optic media to copper media and convert optical signals to electronic pulses.                       |
| **Wireless Router / Access Point** | Devices are used to wirelessly connect to a WAN provider.                                                         |
| **WAN Core devices**               | WAN backbone consists of multiple high-speed routers and Layer 3 switches.                                        |

![[Devices.png]]

---

## Wan Switching
### Circuit switching
A circuit-switched network establishes a dedicated circuit (or channel) between endpoints before the users can communicate.    

- Establishes a dedicated virtual connection through the service provider network before communication can start.
- All communication uses the same path.
- The two most common types of circuit-switched WAN technologies are the public switched telephone network (PSTN) and the legacy Integrated Services Digital Network (ISDN).

![[Circuit Switching.png]]

### Packet Switching
Network communication is most commonly implemented using packet-switched communication.
- Segments traffic data into packets that are routed over a shared network.
- Much less expensive and more flexible than circuit switching.

Common types of packet-switched WAN technologies are:
- Ethernet WAN (Metro Ethernet),
	- [[Modern WAN#**Multiprotocol Label Switching (MPLS)**]]
	- Frame Relay
	- Asynchronous Transfer Mode (ATM).
![[Packet switching.png]]

---
WANs went though a lot of changes see [[Legacy WAN]] compared to [[Modern WAN]] 

---

## Internet-based
Internet-based broadband connectivity is an alternative to using dedicated WAN options.
Internet-based connectivity can be divided into wired and wireless options.

**Wired Options**
- Wired options use permanent cabling (e.g., copper or fiber) to provide consistent bandwidth, and reduce error rates and latency. Examples: DSL, cable connections, and optical fiber networks.
**Wireless Options**
- Wireless options are less expensive to implement compared to other WAN connectivity options because they use radio waves instead of wired media to transmit data. Examples: cellular 3G/4G/5G or satellite internet services.
- Wireless signals can be negatively affected by factors such as distance from radio towers, interference from other sources and weather.
![[internet based wan.png]]

### DSL
Digital Subscriber Line (DSL) is a high-speed, always-on, connection technology that uses existing twisted-pair telephone lines to provide IP services to users.    

DSL are categorized as either Asymmetric DSL (ADSL) or Symmetric DSL (SDSL).    
- ADSL and ADSL2+ provide higher downstream bandwidth to the user than upload bandwidth.
- SDSL provides the same capacity in both directions.

DSL transfer rates are dependent on the actual length of the local loop, and the type and condition of the cabling.

![[DSL.png]]

Service providers deploy DSL connections in the local loop. The connection is set up between the DSL modem and the DSL access multiplexer (DSLAM).    
- The DSL modem converts the Ethernet signals from the teleworker device to a DSL signal, which is transmitted to a DSL access multiplexer (DSLAM) at the provider location.
- A DSLAM is located at the Central Office (CO) of the provider and concentrates connections from multiple DSL subscribers.
- DSL is not a shared medium. Each user has a separate direct connection to the DSLAM. Adding users does not impede performance.
![[DSL connections.png]]

#### PPP
ISPs use [[PPP]] as the [[OSI Model|Layer 2 protocol]] for broadband DSL connections.    
- PPP can be used to authenticate the subscriber.
- PPP can assign a public [[IP-v4|IPv4]] address to the subscriber.
- PPP provides link-quality management features.

 There are two ways PPP over Ethernet (PPPoE) can be deployed:    
- **Host with** **PPoE** **Client** - The PPPoE client software communicates with the DSL modem using PPPoE and the modem communicates with the ISP using PPP.
- **Router** **PPPoE** **Client -** The router is the PPPoE client and obtains its configuration from the provider.
![[DSL and ppp.png]]

### Cable
Cable technology is a high-speed always-on connection technology that uses a coaxial cable from the cable company to provide IP services to users.    
The Data over Cable Service Interface Specification (DOCSIS) is the international standard for adding high-bandwidth data to an existing cable system.

- The optical node converts RF signals to light pulses over [[Fiber Optic]] cable.   
- The fiber media enables the signals to travel over long distances to the provider headend where a Cable Modem Termination System (CMTS) is located.
- The headend contains the databases needed to provide internet access while the CMTS is responsible for communicating with the cable modems.
![[Cable WAN.png]]

### Fiber
Many municipalities, cities, and providers install [[Fiber Optic]] cable to the user location. This is commonly referred to as Fiber to the x (FTTx) and includes the following:
- **Fiber to the Home (FTTH)** - Fiber reaches the boundary of the residence.
- **Fiber to the Building (FTTB)** - Fiber reaches the boundary of the building with the final connection to the individual living space being made via alternative means.
- **Fiber to the Node/Neighborhood (FTTN)** – Optical cabling reaches an optical node that converts optical signals to a format acceptable for twisted pair or coaxial cable to the premise.

### Wireless
Wireless technology uses the unlicensed radio spectrum to send and receive data.

- **Municipal Wi-Fi** -  Municipal wireless networks are available in many cities providing high-speed internet access for free, or for substantially less than the price of other broadband services.
- **Cellular** – Increasingly used to connect devices to the internet using radio waves to communicate through a nearby mobile phone tower. 3G/4G/5G and Long-Term Evolution (LTE) are cellular technologies.
- **Satellite Internet** - Typically used by rural users or in remote locations where cable and DSL are not available. A router connects to a satellite dish which is pointed to a service provider satellite in Geosynchronous orbit. Trees and heavy rains can impact the satellite signal.
- **WiMAX** - Worldwide Interoperability for Microwave Access (WiMAX) is described in the [[Standart Organasitations|IEEE]] standard 802.16 Provides high-speed broadband service with wireless access and provides broad coverage like a cell phone network rather than through small Wi-Fi hotspots.

### VPN
[[VPN Allgemein|VPNs]] can be used to address security concerns incurred when a remote office worker uses broadband services to access the corporate WAN over the internet.
A VPN is an encrypted connection between private networks over a public network. VPN tunnels are routed through the internet from the private network of the company to the remote site or employee host.

There are several [[VPN Allgemein#VPN Vorteile|benefits to using VPN]]

VPNs are commonly implemented as the following:
- **Site-to-site VPN** - VPN settings are configured on routers. Clients are unaware that their data is being encrypted.
- **Remote Access** - The user is aware and initiates remote access connection. For example, using HTTPS in a browser to connect to your bank. Alternatively, the user can run VPN client software on their host to connect to and authenticate with the destination device.

## Connectivity Options
There are different ways an organization can connect to an ISP. The choice depends on the needs and budget of the organization.

- **Single-homed** –Single connection to the ISP using one link. Provides no redundancy and is the least expensive solution.
- **Dual-homed** - Connects to the same ISP using two links. Provides both redundancy and load balancing. However, the organization loses internet connectivity if the ISP experiences an outage.
- **Multihomed** -The client connects to two different ISPs. This design provides increased redundancy and enables load-balancing, but it can be expensive.
- **Dual-multihomed** - Dual-multihomed is the most resilient topology of the four shown. The client connects with redundant links to multiple ISPs. This topology provides the most redundancy possible. It is the most expensive option of the four.

![[WAN Connectivity.png]]

---

## Broadband Solution Comparison
Each broadband solution has advantages and disadvantages. If there are multiple broadband solutions available, a cost-versus-benefit analysis should be performed to determine the best solution.    
Some factors to consider include the following:    
- [[#Cable]] - Bandwidth is shared by many users. Therefore, upstream data rates are often slow during high-usage hours in areas with over-subscription.
- [[#DSL]] - Limited bandwidth that is distance sensitive (in relation to the ISP central office). Upload rate is proportionally lower compared to download rate.
- [[#Fiber|Fiber-to-the-Home]] - This option requires fiber installation directly to the home.
- [[#Wireless|Cellular/Mobile]] - With this option, coverage is often an issue, even within a small office or home office where bandwidth is relatively limited.
- [[#Wireless|Municipal Wi-Fi]] - Most municipalities do not have a mesh Wi-Fi network deployed. If is available and in range, then it is a viable option.
- [[#Wireless|Satellite]] - This option is expensive and provides limited capacity per subscriber. Typically used when no other option is available.