WAN ist ein Netzwerk, dass sich über große Bereiche streckt. 
Unterschiede zwischen LAN und WAN:

| LAN                                         | WAN                                             |
|---------------------------------------------|-------------------------------------------------|
| Kleine Gebiete                              | Große Gebiete                                   |
| Verbindet Geräte                            | Verbindet Netzwerke                             |
| Verwaltet von einer Person oder Unternehmen | Verwaltet von Providern (Internet, Telefon usw) |
| Keine Gebühren                              | Gebühren                                        |
| Hohe Bandbreite                             | Mittlere bis hohe Bandbreite                    |

Ein privates WAN ist eine Verbindung, die einer einzelnen Person gehört.
Zu den Vorteilen davon gehören:
- Garantierter Service
- Konsistente Bandbreite
- Sicherheit
Was bei einem öffentlichen WAN nicht zutreffen muss.

**WAN Topologien**
- [[WAN Point To Point|Point to Point]]
- [[WAN Hub And Spoke|Hub and Spoke]]
- [[WAN Dual Homed|Dual Homed]]
- [[WAN Mesh|Mesh]]

**Carrier Connections**
Hierbei geht es darum, wie das WAN mit dem Internet verbunden ist. Carrier muss nicht der Service Provider sein. 

***Single Carrier***
Nur mit einem ISP verbunden:

![[Pasted image 20241212182223.png]]

***Dual Carrier***
Mit zwei ISP verbunden. Bessere Redundanz und Netzwerkverfügbarkeit.

![[Pasted image 20241212182305.png]]

Mögliche Entwicklung eines Unternehmensnetzwerks:
Siehe PPP Folie 14

**WAN Operation**

***Standards***
- TIA/EIA
- ISO
- IEEE

Im Bereich des WANs gibt es viele Protokolle auf Layer 1 & 2:

![[Pasted image 20241212182938.png]]

**WAN Begriffe**

| WAN Begriff                         | Beschreibung                           |
|-------------------------------------|----------------------------------------|
| Data Terminal Equipment (DTE)       | Verbindet LAN mit WAN                  |
| Data Communications Equipment (DCE) | Kommunikation mit dem Provider         |
| Customer Premises Equipment (CPE)   | DTE und DCE                            |
| Point Of Presence (POP)             | Subscriber connect to Provider Network |
| Demarcation Point                   | Trennpunkt CPE und Provider Netzwerk   |
| Local Loop                          | Kable das CPE mit CO verbindet         |
| Central Office (CO)                 | Service Provider Gebäude               |
| Toll network                        | siehe ppp 22                           |
| Backhaul network                    | siehe ppp 22                           |
| Backbone network                    | siehe ppp 22                           |

![[Pasted image 20241212183807.png]]

**WAN Geräte**

| WAN Gerät                      | Beschreibung                                              |
|--------------------------------|-----------------------------------------------------------|
| Voiceband Modem                | Verwendet Telefonkabel                                    |
| DSL Modem / Cable Modem        | Verbunden mit DTE unter verwendung von Ethernet           |
| CSU/DSU                        | Verbindet ein digitales Gerät mit einer digitalen Leitung |
| Optical Converter              | Verbindet Glasfaser mit Kupferkabel                       |
| Wireless Router / Access Point | Kabelose Verbindung mit einem WAN-netzwerk                |
| WAN core devices               | Highspeed-Router und Layer 3 Switches                     |

**Serielle Kommunikation**

***Einzelnes Kabel***
Byte für Byte wird hintereinander geschickt.

***Parallel - Mehrere Kabel***
Bytes werden auf die Kabel aufgeteilt. Nur für kurze Distanzen nützlich, da sonst der Syncronisierungsaufwand zu hoch ist.

![[Pasted image 20241212184838.png]]

**Circuit Switched Communication**
Es wird zuerst ein Kanal zum Ziel im WAN aufgebaut, bevor kommuniziert wird. Immer der gleiche Pfad wird verwendet.
- Public Switched Telephone Network (Niedrige Geschwindigkeit)
- Integrated Services Digital Network

![[Pasted image 20241212185248.png]]

**Packet Switched Communication**
Versteh ich nicht. Hilfe bitte.
Billiger und einfacher. 
- Ethernet WAN (Metro Ethernet)
- Multiprotocol Label Switching (MPLS)
- Frame Relay
- Asynchronous Transfer Moder (ATM)

![[Pasted image 20241212185443.png]]

**Glasfaser Standards**
Layer 1 Standards:
***SDH***
Globaler Standart für das transportieren von Daten über Glasfaser

***SONET***
Der nordamerikanische Standart für die selben Services wie SDH

***Dense Wavelength Division Multiplexing***
Neue Technologie, welche die Geschwindigkeit erhöht, indem man mehrere Streams in verschiedenen Frequenzen schickt.

**Traditionelle WAN Verbindungen**
LANs wurden über den ISP verbunden. Entweder wurden Verbindungen gemietet oder switched Services vom ISP verwendet:

![[Pasted image 20241212190416.png]]

**Mietbare Carrier**

***T-Carrier***
Nordamerikanisch, T1 und T3

***E-Carrier***
Europäisch, E1 und E3

**Vor/Nachteile von Mietbaren Point to Point Verbindungen**
Positiv:
- Einfach
- Qualität (Geschwindigkeit)
- Verfügbarkeit
Negativ:
- Kosten
- Limitierte Flexibilität

**Dedizierte Leitung**
Eigenes Glasfaser verlegen und Standorte verbinden.

**Internet Based broadband**
Verwendung des Internets für die Verbindung von Standorten

![[Pasted image 20241212191604.png]]

**Ethernet WAN**
- Metro Ethernet
- Ethernet over MPLS
- Virtual Private LAN Service (VPLS)
Billiger, einfache Integration und bessere Unternehmensproduktivität

![[Pasted image 20241212192247.png]]

**MPLS (Multiprotocol Label Switching)**
WAN Technologie um Benutzer zu verbinden.
Viele Anschlussmöglichkeiten (DLS, Ethernet, usw)
Kann alle Protokolle umfassen

***MPLS Router***
- Customer Edge
- Provider Edge
- Internal Provider (P)

Fügen Labels für das Routen zu den Paketen hinzu.
Services für QoS, VPN, usw

![[Pasted image 20241212192237.png]]

### Internet Based Connectivity

**Optionen**

***Kabelgebunden**
DLS, Glasfaser, ...

***Kabellos***
3G, 4G, 5G
Nicht Stabil

![[Pasted image 20241212192438.png]]

**DLS (Digital Line Subscriber) Technologien**

***ADSL (Asymmetrisch)***
Besseren Downstream als Upstream

***SDSL (Symmetrisch)***
Gleicher Downstream wie Upstream

![[Pasted image 20241212192734.png]]

**DLS Verbindung**
Ein DLS Modem konvertiert ein Ethernet Signal in ein DLS Signal, welchen dann an einen DLS Multiplexer geschickt wird.
Jeder Nutzer hat eine eigene Verbindung zum DLS Multiplexer

![[Pasted image 20241212192941.png]]

**PPP**
Ist ein Layer 2 Protokoll. PPP wird zum authentifizieren von Benutzern verwendet und fügt eine IP Adresse zum Subscriber hinzu. 

Entweder der Host oder der Router ist der PPPoE Client:
![[Pasted image 20241212193258.png]]
![[Pasted image 20241212193303.png]]

**Kabel Technologie**
Daten werden mittels Kupferkabel und Glasfaser transportiert.

![[Pasted image 20241212193443.png]]

**Glasfaser**
- Fiber To the Home (FTTH)
- Fiber To The Building (FTTB)
- Fiber To The Neighborhood (FTTN)

**Wireless Internet Based Broadband**
- Municipal Wi-Fi (In Städten)
- Cellular (3G, 4G, 5G, LTE)
- Satellite Internet (Wenn DLS nicht verfügbar ist)
- WiMAX (Große Abdeckung)

**ISP Connectivity Options**

***Single Homed***
Eine einzelne Verbindung zum ISP

![[Pasted image 20241212194336.png]]

***Dual-Homed***
Mehrere Verbindungen zu einem ISP

![[Pasted image 20241212194341.png]]

***Multi-Homed***
Einzelne Verbindungen zu mehreren ISPs

![[Pasted image 20241212194346.png]]

***Dual-Multi-Homed***
Mehrere Verbindungen zu mehreren ISPs

![[Pasted image 20241212194351.png]]

**Broadband solution comparison**

***Kabel***
Geteilt, Upstream oft langsam,

***DLS***
Limitierte Geschwindigkeit, welche distanzabhängig ist.

***Fiber-To-The-Home***
Aufwendig + teuer

**Mobilnetz**
Abdeckung ist problematisch. Geschwindigkeit ist sehr limitiert.

***Municipal Wi-Fi****
Wenn verfügbar, eine gute option

***Satellit***
Teuer, beschränkte Geschwindigkeit, Nur wenn nichts anderes geht

---

> [!cite]-
> ## Originale Quelle
> A WAN is a telecommunications network that spans over a relatively large geographical area and is required to connect beyond the boundary of the LAN.
>
> |Local Area Networks (LANs)|Wide Area Networks (WANs)|
> |LANs provide networking services within a small geographic area.|WANs provide networking services over large geographical areas.|
> |LANs are used to interconnect local computers, peripherals, and other devices.|WANs are used to interconnect remote users, networks, and sites.|
> |A LAN is owned and managed by an organization or home user.|WANs are owned and managed by internet service, telephone, cable, and satellite providers.|
> |Other than the network infrastructure costs, there is no fee to use a LAN.|WAN services are provided for a fee.|
> |LANs provide high bandwidth speeds using wired Ethernet and Wi-Fi services.|WANs providers offer low to high bandwidth speeds, over long distances.|
>
> A private WAN is a connection that is dedicated to a single customer.
>
> Private WANs provide the following:
>
> •Guaranteed service level
>
> •Consistent bandwidth
>
> •Security
>
> A public WAN connection is typically provided by an ISP or telecommunications service provider using the internet. In this case, the service levels and bandwidth may vary, and the shared connections do not guarantee security.
>
> WANs are implemented using the following logical topology designs:
>
> •Point-to-Point Topology
>
> •Hub-and-Spoke Topology
>
> •Dual-homed Topology
>
> •Fully Meshed Topology
>
> •Partially Meshed Topology
>
> Another aspect of WAN design is how an organization connects to the internet. An organization usually signs a service level agreement (SLA) with a service provider. The SLA outlines the expected services relating to the reliability and availability of the connection.
>
> The service provider may or may not be the actual carrier. A carrier owns and maintains the physical connection and equipment between the provider and the customer. Typically, an organization will choose either a single-carrier or dual-carrier WAN connection.
>
> A single-carrier connection is when an organization connects to only one service provider. An SLA is negotiated between the organization and the service provider.
>
> A dual-carrier connection provides redundancy and increases network availability. The organization negotiates separate SLAs with two different service providers.
>
>A single-carrier connection is when an organization connects to only one service provider. An SLA is negotiated between the organization and the service provider.
>
>A dual-carrier connection provides redundancy and increases network availability. The organization negotiates separate SLAs with two different service providers.
>
>Most WAN standards focus on the physical layer and the data link layer.
>
>Layer 1 Protocols
>
>•Synchronous Digital Hierarchy (SDH)
>
>•Synchronous Optical Networking (SONET)
>
>•Dense Wavelength Division Multiplexing (DWDM)
>
>Layer 2 Protocols
>
>•Broadband (i.e., DSL and Cable)
>
>•Wireless
>
>•Ethernet WAN (Metro Ethernet)
>
>•Multiprotocol Label Switching (MPLS)
>
>•Point-to-Point Protocol (PPP) (less used)
>
>•High-Level Data Link Control (HDLC) (less used)
>
>•Frame Relay (legacy)
>
>•Asynchronous Transfer Mode (ATM) (legacy)
>
>There are specific terms used to describe WAN connections between the subscriber (i.e., the company / client) and the WAN service provider.
>
>|WAN Term|Description|
>|Data Terminal Equipment (DTE)|Connects the subscriber LANs to the WAN communication device|
>|Data Communications Equipment (DCE)|Device used to communicate with the provider|
>|Customer Premises Equipment (CPE)|This is the DTE and DCE devices located on the enterprise edge|
>|Point-of-Presence (POP)|The point where the subscriber connects to the service provider network|
>|Demarcation Point|The physical location in a building or complex that officially separates the CPE from service provider equipment.|
>|Local Loop (last mile)|The copper or fiber cable that connects the CPE to the CO of the service provider|
>|Central office (CO)|The local service provider facility or building that connects the CPE to the provider network|
>|Toll network|Includes backhaul, long-haul, all-digital, fiber-optic communications lines, switches, routers, and other equipment inside the WAN provider network|
>|Backhaul network|Connects multiple access nodes of the service provider network|
>|Backbone network|Large, high-capacity networks used to interconnect service provider networks and to create a redundant network.|
>
>There are many types of devices that are specific to WAN environments.
>
>|WAN Device|Description|
>|Voiceband Modem|Dial-up modem – uses telephone lines<br><br>Legacy device|
>|DSL Modem / Cable Modem|Collectively known as broadband modems, these high-speed digital modems connect to the DTE router using Ethernet.|
>|CSU/DSU|Digital-leased lines require a CSU and a DSU. It connects a digital device to a digital line.|
>|Optical Converter|Connect fiber-optic media to copper media and convert optical signals to electronic pulses.|
>|Wireless Router / Access Point|Devices are used to wirelessly connect to a WAN provider.|
>|WAN Core devices|WAN backbone consists of multiple high-speed routers and Layer 3 switches.|
>
>•Almost all network communications occur using a serial communication delivery. Serial communication transmits bits sequentially over a single channel.
>
>•In contrast, parallel communications simultaneously transmit several bits using multiple wires.
>
>•As the cable length increases, the synchronization timing between multiple channels becomes more sensitive to distance. For this reason, parallel communication is limited to very short distances
>
>A circuit-switched network establishes a dedicated circuit (or channel) between endpoints before the users can communicate.
>
>•Establishes a dedicated virtual connection through the service provider network before communication can start.
>
>•All communication uses the same path.
>
>•The two most common types of circuit-switched WAN technologies are the public switched telephone network (PSTN) and the legacy Integrated Services Digital Network (ISDN).
>
>Network communication is most commonly implemented using packet-switched communication.
>
>•Segments traffic data into packets that are routed over a shared network.
>
>•Much less expensive and more flexible than circuit switching.
>
>•Common types of packet-switched WAN technologies are:
>
>•Ethernet WAN (Metro Ethernet),
>
>•Multiprotocol Label Switching (MPLS)
>
>•Frame Relay
>
>•Asynchronous Transfer Mode (ATM).
>
>To understand the WANs of today, it helps to know where they started.
>
>•When LANs appeared in the 1980s, organizations began to see the need to interconnect with other locations.
>
>•To do so, they needed their networks to connect to the local loop of a service provider.
>
>•This was accomplished by using dedicated lines, or by using switched services from a service provider.
>
>Point-to-point lines could be leased from a service provider and were called “leased lines”. The term refers to the fact that the organization pays a monthly lease fee to a service provider to use the line.
>
>•Leased lines are available in different fixed capacities and are generally priced based on the bandwidth required and the distance between the two connected points.
>
>•There are two systems used to define the digital capacity of a copper media serial link:
>
>•T-carrier - Used in North America, T-carrier provides T1 links supporting bandwidth up to 1.544 Mbps and T3 links supporting bandwidth up to 43.7 Mbps.
>
>•E-carrier – Used in Europe, E-carrier provides E1 links supporting bandwidth up to 2.048 Mbps and E3 links supporting bandwidth up to 34.368 Mbps.
>
>The table summarizes the advantages and disadvantages of leased lines.
>
>|Advantages|   |
>|Simplicity|Point-to-point communication links require minimal expertise to install and maintain.|
>|Quality|Point-to-point communication links usually offer high quality service, if they have adequate bandwidth.|
>|Availability|Constant availability is essential for some applications, such as e-commerce. Point-to-point communication links provide permanent, dedicated capacity which is required for VoIP or Video over IP.|
>
>|Disadvantages|   |
>|Cost|Point-to-point links are generally the most expensive type of WAN access. The cost of leased line solutions can become significant when they are used to connect many sites over increasing distances.|
>|Limited flexibility|WAN traffic is often variable, and leased lines have a fixed capacity, so that the bandwidth of the line seldom matches the need exactly.|
>
>Circuit-switched connections are provided by Public Service Telephone Network (PSTN) carriers. The local loop connecting the CPE to the CO is copper media.
>
>There are two traditional circuit-switched options:
>
>Public Service Telephone Network (PSTN)
>
>•Dialup WAN access uses the PSTN as its WAN connection. Traditional local loops can transport binary computer data through the voice telephone network using a voiceband modem.
>
> •The physical characteristics of the local loop and its connection to the PSTN limit the rate of the signal to less than 56 kbps.
> 
> Integrated Services Digital Network (ISDN)
> 
> •ISDN is a circuit-switching technology that enables the PSTN local loop to carry digital signals. This provided higher capacity switched connections than dialup access. ISDN provides for data rates from 45 Kbps to 2.048 Mbps.
> 
> Packet switching segments data into packets that are routed over a shared network. It allows many pairs of nodes to communicate over the same channel.
> 
> There are two traditional (legacy) circuit-switched options:
> 
> Frame Relay
> 
> •Frame Relay is a simple Layer 2 non-broadcast multi-access (NBMA) WAN technology that is used to interconnect enterprise LANs.
> 
> •Frame Relay creates PVCs which are uniquely identified by a data-link connection identifier (DLCI).
> 
> Asynchronous Transfer Mode (ATM)
> 
> •Asynchronous Transfer Mode (ATM) technology is capable of transferring voice, video, and data through private and public networks.
> 
> •ATM is built on a cell-based architecture rather than on a frame-based architecture. ATM cells are always a fixed length of 53 bytes.
> 
> Packet switching segments data into packets that are routed over a shared network. It allows many pairs of nodes to communicate over the same channel.
> 
> There are two traditional (legacy) circuit-switched options:
> 
> Frame Relay
> 
> •Frame Relay is a simple Layer 2 non-broadcast multi-access (NBMA) WAN technology that is used to interconnect enterprise LANs.
> 
> •Frame Relay creates PVCs which are uniquely identified by a data-link connection identifier (DLCI).
> 
> Asynchronous Transfer Mode (ATM)
> 
> •Asynchronous Transfer Mode (ATM) technology is capable of transferring voice, video, and data through private and public networks.
> 
> •ATM is built on a cell-based architecture rather than on a frame-based architecture. ATM cells are always a fixed length of 53 bytes.
> 
> Modern WANS have more connectivity options than traditional WANs.
> 
> •Enterprises now require faster and more flexible WAN connectivity options.
> 
> •Traditional WAN connectivity options have rapidly declined in use because they are either no longer available, too expensive, or have limited bandwidth.
> 
> New technologies are continually emerging. The figure summarizes the modern WAN connectivity options.
> 
> Dedicated broadband
> 
> •Fiber can be installed independently by an organization to connect remote locations directly together.
> 
> •Dark fiber can be leased or purchased from a supplier.
> 
> Packet-switched
> 
> •Metro Ethernet – Replacing many traditional WAN options.
> 
> •MPLS – Enables sites to connect to the provider regardless of its access technologies.
> 
> Internet-based broadband
> 
> •Organizations are now commonly using the global internet infrastructure for WAN connectivity.
> 
> Service providers now offer Ethernet WAN service using fiber-optic cabling.
> 
> The Ethernet WAN service can go by many names, including the following:
> 
> •Metropolitan Ethernet (Metro E)
> 
> •Ethernet over MPLS (EoMPLS)
> 
> •Virtual Private LAN Service (VPLS)
> 
> There are several benefits to an Ethernet WAN:
> 
> •Reduced expenses and administration
> 
> •Easy integration with existing networks
> 
> •Enhanced business productivity
> 
> Multiprotocol Label Switching (MPLS) is a high-performance service provider WAN routing technology to interconnect clients without regard to access method or payload.
> 
> •MPLS supports a variety of client access methods (e.g., Ethernet, DSL, Cable, Frame Relay).
> 
> •MPLS can encapsulate all types of protocols including IPv4 and IPv6 traffic.
> 
> •An MPLS router can be a customer edge (CE) router, a provider edge (PE) router, or an internal provider (P) router.
> 
> •MPLS routers are label switched routers (LSRs). They attach labels to packets that are then used by other MPLS routers to forward traffic.
> 
> •MPLS also provides services for QoS support, traffic engineering, redundancy, and VPNs.
> 
> Internet-based broadband connectivity is an alternative to using dedicated WAN options.
> 
> Internet-based connectivity can be divided into wired and wireless options.
> 
> Wired Options
> 
> •Wired options use permanent cabling (e.g., copper or fiber) to provide consistent bandwidth, and reduce error rates and latency. Examples: DSL, cable connections, and optical fiber networks.
> 
> Wireless Options
> 
> •Wireless options are less expensive to implement compared to other WAN connectivity options because they use radio waves instead of wired media to transmit data. Examples: cellular 3G/4G/5G or satellite internet services.
> 
> •Wireless signals can be negatively affected by factors such as distance from radio towers, interference from other sources and weather.
> 
> Digital Subscriber Line (DSL) is a high-speed, always-on, connection technology that uses existing twisted-pair telephone lines to provide IP services to users.
> 
> DSL are categorized as either Asymmetric DSL (ADSL) or Symmetric DSL (SDSL).
> 
> •ADSL and ADSL2+ provide higher downstream bandwidth to the user than upload bandwidth.
> 
> •SDSL provides the same capacity in both directions.
> 
> DSL transfer rates are dependent on the actual length of the local loop, and the type and condition of the cabling.
> 
> Service providers deploy DSL connections in the local loop. The connection is set up between the DSL modem and the DSL access multiplexer (DSLAM).
> 
> •The DSL modem converts the Ethernet signals from the teleworker device to a DSL signal, which is transmitted to a DSL access multiplexer (DSLAM) at the provider location.
> 
> •A DSLAM is located at the Central Office (CO) of the provider and concentrates connections from multiple DSL subscribers.
> 
> •DSL is not a shared medium. Each user has a separate direct connection to the DSLAM. Adding users does not impede performance.
> 
> ISPs use PPP as the Layer 2 protocol for broadband DSL connections.
> 
> •PPP can be used to authenticate the subscriber.
> 
> •PPP can assign a public IPv4 address to the subscriber.
> 
> •PPP provides link-quality management features.
> 
> There are two ways PPP over Ethernet (PPPoE) can be deployed:
> 
> •Host with PPoE Client - The PPPoE client software communicates with the DSL modem using PPPoE and the modem communicates with the ISP using PPP.
> 
> •Router PPPoE Client - The router is the PPPoE client and obtains its configuration from the provider.
> 
> Cable technology is a high-speed always-on connection technology that uses a coaxial cable from the cable company to provide IP services to users.
> 
> The Data over Cable Service Interface Specification (DOCSIS) is the international standard for adding high-bandwidth data to an existing cable system.
> 
> •The optical node converts RF signals to light pulses over fiber-optic cable.
> 
> •The fiber media enables the signals to travel over long distances to the provider headend where a Cable Modem Termination System (CMTS) is located.
> 
> •The headend contains the databases needed to provide internet access while the CMTS is responsible for communicating with the cable modems.
> 
> Many municipalities, cities, and providers install fiber-optic cable to the user location. This is commonly referred to as Fiber to the x (FTTx) and includes the following:
> 
> •Fiber to the Home (FTTH) - Fiber reaches the boundary of the residence.
> 
> •Fiber to the Building (FTTB) - Fiber reaches the boundary of the building with the final connection to the individual living space being made via alternative means.
> 
> •Fiber to the Node/Neighborhood (FTTN) – Optical cabling reaches an optical node that converts optical signals to a format acceptable for twisted pair or coaxial cable to the premise.
> 
> Wireless technology uses the unlicensed radio spectrum to send and receive data.
> 
> •Municipal Wi-Fi -  Municipal wireless networks are available in many cities providing high-speed internet access for free, or for substantially less than the price of other broadband services.
> 
> •Cellular – Increasingly used to connect devices to the internet using radio waves to communicate through a nearby mobile phone tower. 3G/4G/5G and Long-Term Evolution (LTE) are cellular technologies.
> 
> •Satellite Internet - Typically used by rural users or in remote locations where cable and DSL are not available. A router connects to a satellite dish which is pointed to a service provider satellite in Geosynchronous orbit. Trees and heavy rains can impact the satellite signal.
> 
> •WiMAX - Worldwide Interoperability for Microwave Access (WiMAX) is described in the IEEE standard 802.16 Provides high-speed broadband service with wireless access and provides broad coverage like a cell phone network rather than through small Wi-Fi hotspots.
> 
> VPNs can be used to address security concerns incurred when a remote office worker uses broadband services to access the corporate WAN over the internet.
> 
> A VPN is an encrypted connection between private networks over a public network. VPN tunnels are routed through the internet from the private network of the company to the remote site or employee host.
> 
> There are several benefits to using VPN:
> 
> •Cost savings - Eliminates expensive, dedicated WAN links and modem banks.
> 
> •Security - Advanced encryption and authentication protocols protect data from unauthorized access.
> 
> •Scalability - Corporations can add large amounts of capacity without adding significant infrastructure.
> 
> •Compatibility with broadband technology - Supported by broadband service providers such as DSL and cable.
> 
> VPNs are commonly implemented as the following:
> 
> •Site-to-site VPN - VPN settings are configured on routers. Clients are unaware that their data is being encrypted.
> 
> •Remote Access - The user is aware and initiates remote access connection. For example, using HTTPS in a browser to connect to your bank. Alternatively, the user can run VPN client software on their host to connect to and authenticate with the destination device.
> 
> There are different ways an organization can connect to an ISP. The choice depends on the needs and budget of the organization.
> 
> •Single-homed –Single connection to the ISP using one link. Provides no redundancy and is the least expensive solution.
> 
> •Dual-homed - Connects to the same ISP using two links. Provides both redundancy and load balancing. However, the organization loses internet connectivity if the ISP experiences an outage.
> 
> •Multihomed -The client connects to two different ISPs. This design provides increased redundancy and enables load-balancing, but it can be expensive.
> 
> •Dual-multihomed - Dual-multihomed is the most resilient topology of the four shown. The client connects with redundant links to multiple ISPs. This topology provides the most redundancy possible. It is the most expensive option of the four.
> 
> Each broadband solution has advantages and disadvantages. If there are multiple broadband solutions available, a cost-versus-benefit analysis should be performed to determine the best solution.
> 
> Some factors to consider include the following:
> 
> •Cable - Bandwidth is shared by many users. Therefore, upstream data rates are often slow during high-usage hours in areas with over-subscription.
> 
> •DSL - Limited bandwidth that is distance sensitive (in relation to the ISP central office). Upload rate is proportionally lower compared to download rate.
> 
> •Fiber-to-the-Home - This option requires fiber installation directly to the home.
> 
> •Cellular/Mobile - With this option, coverage is often an issue, even within a small office or home office where bandwidth is relatively limited.
> 
> •Municipal Wi-Fi - Most municipalities do not have a mesh Wi-Fi network deployed. If is available and in range, then it is a viable option.
> 
> •Satellite - This option is expensive and provides limited capacity per subscriber. Typically used when no other option is available.