To understand the WANs of today, it helps to know where they started.    
- When LANs appeared in the 1980s, organizations began to see the need to interconnect with other locations.
- To do so, they needed their networks to connect to the local loop of a service provider.
- This was accomplished by using dedicated lines, or by using switched services from a service provider.

![[Tradional WAN.png]]

### Leased Lines

Point-to-point lines could be leased from a service provider and were called “leased lines”. The term refers to the fact that the organization pays a monthly lease fee to a service provider to use the line.
- Leased lines are available in different fixed capacities and are generally priced based on the bandwidth required and the distance between the two connected points.    
- There are two systems used to define the digital capacity of a copper media serial link:
- **T-carrier** - Used in North America, T-carrier provides T1 links supporting bandwidth up to 1.544 Mbps and T3 links supporting bandwidth up to 43.7 Mbps.
- **E-carrier** – Used in Europe, E-carrier provides E1 links supporting bandwidth up to 2.048 Mbps and E3 links supporting bandwidth up to 34.368 Mbps.

| ***Advantages***        |                                                                                                                                                                                                            |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Simplicity**          | **Point-to-point communication links require minimal expertise to install and maintain.**                                                                                                                  |
| **Quality**             | Point-to-point communication links usually offer high quality service, if they have adequate bandwidth.                                                                                                    |
| **Availability**        | Constant availability is essential for some applications, such as e-commerce. Point-to-point communication links provide permanent, dedicated capacity which is required for VoIP or Video over IP.        |
| ***Disadventages***     |                                                                                                                                                                                                            |
| **Cost**                | **Point-to-point links are generally the most expensive type of WAN access. The cost of leased line solutions can become significant when they are used to connect many sites over increasing distances.** |
| **Limited flexibility** | WAN traffic is often variable, and leased lines have a fixed capacity, so that the bandwidth of the line seldom matches the need exactly.                                                                  |

 [[NSCS/Networks/WAN/WAN#Circuit switching]] connections are provided by Public Service Telephone Network (PSTN) carriers. The local loop connecting the CPE to the CO is copper media.
 
There are two traditional circuit-switched options:

**Public Service Telephone Network (PSTN)**  
- Dialup WAN access uses the PSTN as its WAN connection. Traditional local loops can transport binary computer data through the voice telephone network using a voiceband modem.
- The physical characteristics of the local loop and its connection to the PSTN limit the rate of the signal to less than 56 kbps.
- 
**Integrated Services Digital Network (ISDN)**  
- ISDN is a circuit-switching technology that enables the PSTN local loop to carry digital signals. This provided higher capacity switched connections than dialup access. ISDN provides for data rates from 45 Kbps to 2.048 Mbps.


[[NSCS/Networks/WAN/WAN#Packet Switching]] segments data into packets that are routed over a shared network. It allows many pairs of nodes to communicate over the same channel.
   
There are two traditional (legacy) circuit-switched options:    

**Frame Relay**    
- Frame Relay is a simple Layer 2 non-broadcast multi-access (NBMA) WAN technology that is used to interconnect enterprise LANs.
- Frame Relay creates PVCs which are uniquely identified by a data-link connection identifier (DLCI).

**Asynchronous Transfer Mode (ATM)**    
- Asynchronous Transfer Mode (ATM) technology is capable of transferring voice, video, and data through private and public networks.
- ATM is built on a cell-based architecture rather than on a frame-based architecture. ATM cells are always a fixed length of 53 bytes.