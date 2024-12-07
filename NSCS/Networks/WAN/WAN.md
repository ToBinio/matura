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

