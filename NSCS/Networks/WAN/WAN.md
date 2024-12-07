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
[[Standart Organasitations|**TIA/EIA** , **ISO**, **IEEE**]]

### OSI Modell
Most WAN standards focus on the physical layer and the data link layer.

[[OSI Model|**Layer 1 Protocols**]]
- Synchronous Digital Hierarchy (SDH)
- Synchronous Optical Networking (SONET)
- Dense Wavelength Division Multiplexing (DWDM)

[[OSI Model|**Layer 2 Protocols**]]
- Broadband (i.e., DSL and Cable)
- Wireless
- Ethernet WAN (Metro Ethernet)
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