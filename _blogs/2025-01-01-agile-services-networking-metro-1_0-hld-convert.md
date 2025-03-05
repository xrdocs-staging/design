---
published: true 
date: '2025-01-01 11:00-0400'
title: Agile Services Networking - Agile Metro 1.0 High-Level Design 
excerpt: Cisco Agile Services Networking enables network operators to build flexible converged networks to handle any type of service at any place in the network. Networks built using ASN provide the scale, efficiency, and resiliency required while maintaining a simplier and easier to operate network.  
author: Phil Bedard 
permalink: /blogs/latest-asn-metro-hld
tags:
  - iosxr
  - Metro
  - Design
  - 5G 
  - Cable
  - CIN
position: hidden 
---

{% include toc %}

# Revision History

| Version          |Date                    |Comments| 
| ---------------- | ---------------------- |-----|
| 1.0       | 2/1/2024 |Initial Agile Services Networking - Metro HLD| 

# Minimum supported IOS-XR Release 

| Agile Metro Version          | XR version |  
| ---------------- | ---------------------- |
| 1.0       | 24.4.1 |  

# Minimum supported IOS-XE Release 

| Agile Metro Version          | XE version |  
| ---------------- | ---------------------- |
| 1.0        | 17.15.21 on NCS 520, ASR920; 17.15 on Catalyst 8500 |


# Agile Metro 1.0 component versions 

| Component          | Version |  
| ---------------- | ---------------------- |
| Crosswork Planning | 24.1.1 | 
| Crosswork Network Controller      | 7.0.1 |  
| Crosswork Hierarchical Controller      | 9.0 |  
| Crosswork Workflow Manager | 1.2 |  
| Cisco Routed PON manager | 5.0 |  
| Cisco Cloud Native BNG | 24.4.1 |  
| Cisco Edge Protect DDoS | 24.4.1 |  
| Cisco CX Edge Fabric NSO services | 1.0 |  

# Service Provider challenges 

Service providers continue to face challenges building networks to satisfy the
evolving demands of network services. The traditional "service edge" of the
network was built using typically larger modular chassis in a centralized
location, resulting in inefficient traffic distribution 

# Cisco Agile Services Networking 

Networks must be built to handle the advanced services and increased traffic
associated with modern network services. Networks must evolve so the
infrastructure layer can keep up with the service layer. The result of these
shifts is driving traffic away from centralized delivery to a more distributed
network. New network architectures must be considered as design options moving
forward that include these key aspects: Distributed and fixed routing systems to
deliver services at any place in the network Fabric models delivering scale-out
networks that can be built on-demand Flexible deployment options matching
provider requirements Network simplification at all layers of the network

Cisco's Agile Services Networking introduces an end-to-end architecture which
evolves traditional network design towards a simplified, efficient network
capable of delivering all network services (AI, Residential, Business, 4G/5G
mobile transport, video, IoT) while adding enhanced ability to assure SLAs and
provide security across all layers of the network. These capabilities will be
delivered at all parts of the network without compromise.   

## Agile Services Networking - Agile Metro overview 

The Agile Metro is one component of the overall solution architecture providing 
a scalable any to any network fabric for Metro networks.   

### Agile Services Networking - Agile Metro 

The Agile Metro is a key component of the overall solution as it helps providers build 

![](http://xrdocs.io/design/images/asn-metro/end-to-end.png)

The ASN Metro design brings tremendous value to Service
Providers:

  - **Fast service deployment** and **rapid time to market** through
    fully automated service provisioning and end-to-end network
    programmability

  - **Operational simplicity** with less protocols to operate and manage

  - **Enhanced and optimized operations** using telemetry/analytics in
    conjunction with advanced model-driven automation tools   

**The Agile Metro design is targeted at network operators who:**

  - Want to deploy a simpler and easier to operate network that does not sacrifice functionality 

  - Need a simple, scalable design that can support future growth

  - Want a future proof architecture built using industry-leading technology


## Agile Metro high-level building blocks 

### Cisco routers covering all operator use cases  
### Advanced Network Operating Systems (NOS) 
### Network Automation 
### Architectural principles providing the basic building block for building agile, efficient, and scalable networks 

## Key Agile Metro features  

- **Efficient transport using Routed Optical Networking** Cisco's Routed Optical Network solution simplifies router interconnections across optical fiber, replacing inefficient external transponders with pluggable digital coherent transceivers. Private Line Emulation allows providers to use standard routers to transparently carry Ethernet, OTN/SONET, and Fiber Channel services across an IP network without sacrificing transport layer functionality and resilience.    

- **Simplified network control plane** Based on Segment Routing SRv6 or SR-MPLS, the network control plane is simplified scalable to meet even the largest service provider networks.  

- **Built-in network assurance** Utilizing advanced functions like Segment Routing Performance Measurement (SR-PM), and Integrated Performance Measurement (IPM), the network itself provides advanced assurance and telemetry functionality. When coupled with Cisco Provider Connectivity Assurance sensors, reporting, and advanced correlation it provides end to end assurance from underlay network to overlay services.  

- **Network device convergence** Cisco Routed PON enables providers to provide XGS-PON OLT functionality using a pluggable transceiver. This allows the termination of residential and business PON endpoints on the same routers providing fiber based service termination. 

- **Network infrastructure convergence**  Carrying multiple services across a single unified network is easier to operate than distinct parallel networks. Agile Metro allows operators to converge residential, business, DCI, and future service types onto a single converged metro network with any to any connectivity.   

- **CUPS based distributed subscriber termination** Cisco Cloud Native Broadband Network Gateway (cnBNG) is a CUPS-based solution combining a high-availability cloud native control plane with user-plane elements distributed closer to end users. Distributing the user-plane closer to end users allows for efficient traffic offload vs. traditional BNG deployments where traffic is backhauled to a centralized BNG.    

- **Enhanced security and DDoS protection** Security begins with trust and verification of trust. Cisco's leading NOS security features ensure device authenticity and integrity. Cisco Trust Insights allows providers to monitor and report on the overall trust posture of network devices at all times, alerting on anomalies. Cisco's Edge Protect DDoS solution distributes DDoS detection and mitigation to every device in the network. The distribution of these function is more efficient and scales higher than traditional centralized DDoS detection and mitigation deployments.   

- **Advanced network automation** Simplifying operations requires not only infrastructure simplification but also changes in how networks are operated. The Cisco Crosswork family of network automation software covers the end to end lifecycle of the network. See the section on Network Automation for more detail on how the Agile Metro incorporates these components to help simplify the planning and operation of the network.  

- **Integration across layers** Integration across layers includes both underlay/overlay integrations to enable carrying differentiated service traffic across specific engineered paths as well as the ability to correlate higher layer service to underlay infrastructure down to the physical fiber.  SD-WAN is one use case covered by Agile Metro where SD-WAN overlay services can be monitored along with the underlay paths carrying the traffic. 


# Infrastructure network technical overview

The infrastructure portion of the network refers to the building blocks of any high scale service provider network. The hardware, interconnection, and low level control plane protocols are utilized together to build a modern agile scalable 
network. 

The following highlights the key technology building blocks used to build the Agile Metro network. 

![](http://xrdocs.io/design/images/asn-metro/asn-metro-hw.png)

## Hardware Components 

### Cisco 8000 
 The Cisco 8000 family is one of the primary hardware components of the Agile Metro  
 Metro design. Cisco 8000 routers provide the lowest power consumption in the
 industry, all while supporting systems over 200 Tbps and features service
 providers require. The expanded Silicon One family of ASICs in Agile Metro 1.0 includes the P100 and K100 family of products fulfilling specific roles in the solution.  

![](http://xrdocs.io/design/images/asn-metro/cst-hw-8000.png)

### New Agile Services Networking hardware 
Agile Services Networking introduces new Silicon One based hardware, simplifying provider deployments with a unified silicon strategy across all parts of the network.   

![](http://xrdocs.io/design/images/asn-metro/metro-hw-8000.png)

#### P100 routers and line cards 
The P100 Silicon One ASIC provides up to 19.2Tbps of bandwidth. The 8212-48FH-M
and 8711-32FH-M single-ASIC fixed routers are validated for edge services,
peering, and aggregation roles in the Agile Metro design. P100 line cards are
also available for modular systems including the Edge enhanced 88-LC1-12TH24FH-E
and 88-LC1-52Y8H-EM.  The 88-LC1-52Y8H-EM is the first Silicon One line card
offering a high density low speed aggregation with 52 SFP28 ports for 10G and
25G native support. All line cards support MACSEC and Class C timing.   

#### K100 routers and line cards 
The K100 Silicon One ASIC provides higher scale edge services. The 6.4T ASIC
will support advanced Edge service functionality for mobile, business services,
Internet, peering, and enterprise use cases. The K100 natively supports MACSEC 
has an embedded IPSec encryption engine (supported in a future release).

The 8712-MOD-M released with XR 24.4.1 is a modular 4-slot router using a single ASIC providing 1.6T per slot. The following MPAs will be initially supported ont he 8712-MOD-M.  

| MPA | Port layout |   
| ----------|---------|
| 8K-MPA-4D | 4 400G QSFP56-DD  | 
| 8K-MPA-16H | 16 QSFP28| 
| 8K-MPA-16Z2D | 16 SFP56 + 4 QSFP56-DD (2x400G or 4x100G/200G)| 
| 8K-MPA-18Z1 | 18 SFP56 + 1 QSFP56-DD  |


## ASR 9000 
The ASR 9000 is the router of choice for high scale edge services.  Agile Metro utilizes the ASR 9000 in a PE function role, performing high scale L2VPN, L3VPN, peering, and Pseudowire headend termination. The ASR 9000 is also utilized as a user plane in the distributed CUPS architecture for subscriber termination. 

![](http://xrdocs.io/design/images/asn-metro/cst-hw-asr9000.png)

## NCS 5504, 5508, 5516 Modular Chassis 
The modular chassis version of the NCS 5500 is available in 4, 8, and 16 slot versions for flexible interfaces at high scale with dual RP modules. A variety of line cards are available with 10G, 40G, 100G, and 400G interface support. The NCS 5500 fully supports timing distribution for applications needing high accuracy clocks like mobile backhaul.  

![](http://xrdocs.io/design/images/asn-metro/cst-hw-ncs5500.png)

## NCS 5500 / 5700 Fixed Chassis 
The NCS 5500 / 5700 fixed series devices are validated in access, aggregation,
and core role in the Agile Metro design. All platforms listed below
support at least PTP class B timing and the full set of IOS-XR xVPN and Segment
Routing features.   

These family of devices provide a flexible way to both aggregate downstream connections 
as well terminate user services at different places in the network.  

More information on the NCS 5500 fixed routers can be found at: 

<https://www.cisco.com/c/en/us/products/routers/network-convergence-system-5500-series/index.html>

## NCS 540 Small, Medium, and Large density routers
The NCS 540 family of routers supports mobile and business services across a wide
variety of service provier and enterprise applications, including support for
Routed Optical Networking in the QSFP-DD enabled NCS-540 Large Density router.

More information on the NCS 540 router line can be found at: 

<https://www.cisco.com/c/en/us/products/routers/network-convergence-system-540-series-routers/index.html>

![](http://xrdocs.io/design/images/asn-metro/cst-hw-ncs540.png)


# Transport – Design Components  

## Agile service placement 

In an Agile Metro network services can be located at any point within the network, blurring the traditional 
network boundaries of access, aggregation, edge, and core. These segments in the network may still exist based 
on geographical boundaries and interconnection, but the "edge" terminating user services can be placed throughout the metro network. The distribution of services enhances overall network scale and resilience.  

![](http://xrdocs.io/design/images/asn-metro/agile-metro-end-state.png) 


## Network domains and IGP structure 

Network domains are defined by different criteria. Scale is the primary driver
for creating separate network domains but it could be for other reasons such as
administrative boundaries or geographic regions. In the case of the Agile
network design we will utilize distinct IGP instances at network domain
boundary routers (ABRs). Boundary nodes will contain two or more IGP instances. Traffic paths
crossing domain boundaries can utilize redistribution, SR-TE using SR-PCE, and
traditional overlay options like BGP-LU. SRv6 using aggregation and
redistribution is the preferred approach for greenfield networks and networks
migrating from legacy MPLS (LDP, RSVP-TE) to Segment Routing.   

The Agile Metro achieves network scale by IGP domain separation. 

## Topology options and PE placement - Inline and non-inline PE
The design is flexible to support edge service placement at different places in the network.  

![](http://xrdocs.io/design/images/asn-metro/metro-deployment-options.png) 

### Edge services on a stick 
This model can be utilized for scenarios where the Edge service termination is relatively 
low bandwidth compared to transit traffic and requires utilizing a more sophisticated edge device. In the Agile Metro 
design this includes cases where Carrier Grade NAT is being used or exception handling for MAP-T traffic.   

### Fully distributed edge
This model full distributes edge functions so any router within the metro can provide edge user services. A provider may use a fully distributed edge is if the bandwidth, port, or service scale does not exceed that of a single node or pair of nodes. Another scenario may be if   

### Edge Fabric 
This design creates a scale out fabric which can be placed within a single provider location or 
utilize WAN connections to create a larger fabric spanning multiple locations. An Edge Fabric is used 
when providers want the ultimate scale in terminating user services, have a necessity for using specific leaf
devices for different services types, or need to create a multi-vendor fabric. See the "Edge Fabric" section of 
the document for more information on building and managing Edge Fabrics.   


## Cisco Routed Optical Networking 
Routed Optical Networking is a foundational component of the Agile Metro for network operators with their own fiber assets 
utilizing point to point dark fiber connections or multiplexed DWDM connections. At its basis Routed Optical Networking 
eliminates redundant hardware and simplifies management through advanced automation. Routed Optical Networking works 
with all types of optical networks; P2P dark fiber, simplified P2P DWDM using Cisco's Pluggable OLS with 
passive multiplexers, and traditional multi-degree ROADMs.


![](http://xrdocs.io/design/images/asn-metro/metro-routed-optical-networking.png) 

For more information on Cisco's Routed Optical Networking design please see the 
following high-level design document:  

<https://xrdocs.io/design/blogs/latest-routed-optical-networking-hld> 


## Segment Routing 

Segment Routing is another foundational component of Agile Services Networking. The Segment Routing architecture is available with 
two forwarding planes, IPv6 and MPLS. SRv6 presents a highly scalable and simplified data plane for modern networks. SRv6 is simply IP routing, using IPv6 addresses to represent end nodes as well as end services. The Agile Services Networking solution uses SRv6 with uSID as the primary dataplane, but also utilizes SR-MPLS which is fully supported across all hardware, software, and automation products. 

### SRv6 Benefits 

#### Scale 
One of the main benefits of SRv6 is the ability to build networks at huge scale
through address summarization. MPLS networks require a unique label per node be
distributed to all nodes requiring mutual reachability. In most cases there is
also the requirement of distributing a /32 IP prefix as well. In the MPLS CST
design we have the option to eliminate the IP and MPLS label distribution by
utilizing a PCE to compute end to end paths. While this method works well and is
also available for SRv6 it can lead to a large number of SR-TE or SRv6-TE
policies.  

SRv6 allows us to summarize domain loopback addresses at IGP or BGP boundaries.
This means a domain of 1000 nodes no longer requires advertising 1000 IP
prefixes and associated labels, but can be summarized into a single IP
advertisement reachable via a simple longest prefix match (LPM) lookup. Networks
of tens of thousands of nodes can now provide full reachability with very few
IPv6 routes. 

![](http://xrdocs.io/design/images/cst-srv6/cst-srv6-igp-layout.png)

![](http://xrdocs.io/design/images/cst-srv6/cst-srv6-isis-redist.png)

#### Simplified Forwarding 
In SRv6, if a node is not a terminating node it simply forwards the traffic
using IPv6 IP forwarding.  This means nodes which are not SRv6 aware can also
participate in a SRv6 network.  

Forwarding in SRv6 follows the semantics of simple IPv6 routing. The destination 
is always identified as an IPv6 address. In the case of an SRv6 packet without an 
additional SRH, traffic is routed to the endpoint destination node hop by hop 
based on normal destination based prefix lookups. In the case of a SRH, the SRH 
is only processed by a node if it is the destination address in the outer IPv6 
header. If the node is the last SID in the SID list it will pop the SRH and process
the packet further.  If the node is not the last SID in the SID list it will replace
the outer IPv6 destination address with the next IPv6 address in the SID list. 

#### Forwarding and Service Congruency 
As you will see in the services section, the destination IPv6 address in SRv6 is
the service endpoint. Coupled with the simple forwarding this aids in
troubleshooting and is much easier to understand than the MPLS layered service
and data plane.   


### Segment Routing Flexible Algorithms (Flex-Algo) 

A powerful tool used to create traffic engineered Segment Routing paths is SR
Flexible Algorithms, better known as SR Flex-Algo.  Flex-Algo assigns a specific
set of "algorithms" to a Segment. The algorithm identifies a specific
computation constraint the segment supports. There are standards based algorithm
definitions such as least cost IGP path and latency, or providers can define
their own algorithms to satisfy their business needs.  Agile Services Networking supports
computation of Flex-Algo paths in intra-domain and inter-domain deployments. 
Flex-Algo limits the computation of a path to only those nodes participating in
that algorithm. This gives a powerful way to create multiple network domains
within a single larger network, constraining an SR path computation to segments
satisfying the metrics defined by the algorithm. As you will see, we can now use
a single node SID to reach a node via a path satisfying an advanced constraint
such as delay.  

Operators can solve most traffic engineering use cases with Flex-Algo. Capabilities of Flex-Algo are continually being enhanced, supporting additional metrics and constraints for path computation. In XR 24.4.1 the following metrics and constraints are supported.  

#### Flex-Algo Metrics  

Delay 
: Delay utilizes the measured or statically configured delay of each link to compute an end to end lowest latency path. Delay values are computed or defined using SR Performance Measurement.   
Generic 
: The generic metric type is used by operators to build a custom topology based on their own metrics. The generic metric for each link is defined in the IS-IS configuration for each link. The Flex-Algo topology will only include nodes/links with the generic metric defined, and will follow the lowest cost path using those user-defined metrics. 
TE: 
The TE metric is an additional metric which can be assigned to each link. The TE metric is advertised in the standard IS-IS traffic engineering TLVs.  

#### Flex-Algo Constraints 

Affinity: 
Affinity uses standard unidirectional traffic engineering affinities (groups) to include or exclude links from the topology. IOS-XR also supports reverse affinities, meaning if the affinity is being sent from node B to A, A will take that link into account when computing the Flex-Algo. One use case is if an affinity is being applied by the remote node on the link due to packet errors.  

Minimum Bandwidth: 
The minimum bandwidth metric is uses to prune links below a certain bandwidth value. This is useful for networks with a mix of high and low speed links to ensure traffic does not take a low speed path. An example is a network with 10G access rings connected to a higher speed aggregation network. High speed traffic between aggregation locations should never traverse the access rings, and this is easily achievable using the minimum bandwidth constraint. 

Maximum Delay: 
Maximum delay uses the measured or statically set SR-PM delay values to prune high delay links from the network. While the delay metric will calculate the lowest delay path, this will ensure that path never takes high delay links.  


#### Flex-Algo SRv6 locator assignment 

SRv6 locators are defined under the primary SRv6 configuration. Each defined locator for the node can be assigned a specific Flex-Algo, which is used by remote head-end nodes to calculate the specific Flex-Algo topology for end to end path computation.  

<div class="highlighter-rouge">
<pre class="highlight">
segment-routing
 srv6
  encapsulation
   source-address fccc:0:214::1
  !
  locators
   locator LocAlgo0
    micro-segment behavior unode psp-usd
    prefix fccc:0:214::/48
   !
   locator LocAlgo128
    micro-segment behavior unode psp-usd
    prefix fccc:1:214::/48
    algorithm 128
   !
  !
 !
!
</pre>
</div>

#### Flex-Algo MPLS SID Assignment
Nodes participating in a specific algorithm must have a unique node SID prefix assigned to the algorithm. In a typical deployment, the same Loopback address is 
used for multiple algorithms. IGP extensions advertise algorithm membership throughout the network. Below is an example of a node with multiple algorithms and node SID 
assignments. By default, the basic IGP path computation is assigned to algorithm "0".  Algorithm "1" is also reserved. Algorithms 128-255 are user-definable. All Flex-Algo 
SIDs belong to the same global SRGB so providers deploying SR should take this into account. Each algorithm should be assigned its own block of SIDs within 
the SRGB, in the case below the SRGB is 16000-32000, each algorithm is assigned 1000 SIDs.   

<div class="highlighter-rouge">
<pre class="highlight">
 interface Loopback0
  address-family ipv4 unicast
   prefix-sid index 150
   prefix-sid algorithm 128 absolute 18003
   prefix-sid algorithm 129 absolute 19003
   prefix-sid algorithm 130 absolute 20003
</pre>
</div>

#### Flex-Algo IGP Definition 
Flexible algorithms being used within a network must be defined in the IGP domains in the network The configuration is typically 
done on at least one node under the IGP configuration for domain. Under the definition the metric type used for computation is 
defined along with any link affinities. Link affinities are used to constrain the algorithm to not only specific nodes, but 
also specific links. These affinities are the same previously used by RSVP-TE.  

**Note: Inter-domain Flex-Algo path computation requires synchronized Flex-Algo definitions across the end-to-end path** 

<div class="highlighter-rouge">
<pre class="highlight">
 flex-algo 130
  metric-type delay
  advertise-definition
 !
 flex-algo 131
  advertise-definition
  affinity exclude-any red
</pre>
</div>

#### Path Computation across SR Flex-Algo Network 
Flex-Algo works by creating a separate topology for each algorithm. By default,
all links interconnecting nodes participating in the same algorithm can be used
for those paths. If the algorithm is defined to include or exclude specific link
affinities, the topology will reflect it. A SR-TE path computation using a
specific Flex-Algo will use the Algo's topology for end the end path
computation. It will also look at the metric type defined for the Algo and use
it for the path computation. Even with a complex topology, a single SID is used
for the end to end path, as opposed to using a series of node and adjacency SIDs
to steer traffic across a shared topology. Each node participating in the
algorithm has adjacencies to other nodes utilizing the same algorithm, so when an 
incoming SRv6 IP address or MPLS label matching the algo SID enters, it will utilize the path
specific to the algorithm. On-demand SR-TE policies can also use a specific algorithm.   


#### Flex-Algo SR-MPLS dual-plane topology example  
A very simple use case for Flex-Algo is to easily define a dual-plane network
topology where algorithm 129 red and algorithm 130 is green. Nodes A1 and A6
participate in both algorithms. When a path request is made for algorithm 129,
the head-end nodes A1 and A6 will only use paths specific to the algorithm.  The
SR-TE Policy does not need to reference the specific SID, only the Algo being
used as the constraints. The local node or SR-PCE will utilize the Algo to
compute the path dynamically.   

![](http://xrdocs.io/design/images/asn-metro/cst-hld-dual-plane.png)

The following policy configuration is an example of constraining the path to the Algo 129 "Red" path.  

<div class="highlighter-rouge">
<pre class="highlight">
segment-routing
 traffic-eng
  policy GREEN-PE8-128
   color 1128 end-point ipv4 100.0.2.53
   candidate-paths
    preference 1
     dynamic
      pcep
      !
      metric
       type igp
      !
     !
<b>     constraints
      segments
       sid-algorithm 129</b> 
</pre>
</div>


### Traffic Engineering (Tactical Steering) – SR-TE Policy

Segment Routing provides a simple and scalable way of defining an end-to-end
application-aware traffic engineering path known as an SR-TE Policy. The SR-TE
Policy expresses the intent of the applications constraints across the network.
The path computation will minimize the number of segments required to build the
end to end path across the network, simplifying deploying and increasing the
supported path length.   

In the Agile Metro design, SR-TE can be utilized for both IPv6 and MPLS dataplanes for 
more advanced traffic engineering use cases.  

Path computation of the end to end SR-TE path is carried out either on the head-end node 
or by using a PCE (Path Computation Element). SR-TE policies can be persistently configured 
on the head-end node or computed on-demand using Cisco "On-Demand Next Hop" or ODN feature.   


### Circuit Style Segment Routing (SR-MPLS) 

Circuit Style Segment Routing (CS-SR) is another Cisco advancement bringing 
TDM circuit like behavior to SR-TE Policies. These policies use deterministic 
hop by hop routing, co-routed bi-directional paths, hot standby protect paths
with end to end liveness detection, and bandwidth guaranteed services.
Standard Ethernet services not requiring bit transparency can be transported
over a Segment Routing network similar to OTN networks without the additional
cost, complexity, and inefficiency of an OTN network layer.   

### Circuit-Style SR-TE with Bandwidth Admission Control using CNC Circuit Style Manager 

Crosswork Network Controller Circuit Style Manager provides Bandwidth
Admission Controller and guaranteed bandwidth paths for Circuit-Style Policies.
CNC also supports full provisioning, monitoring, and visualization of
Circuit-Style SR-TE Policies. 

![](http://xrdocs.io/design/images/ron-hld/ron-cnc-csm-policy-overview.png){:height="50%" width="50%"}

### Segment Routing Path Computation Element (SR-PCE)

Segment Routing Path Computation Element, or SR-PCE, is a Cisco Path Computation
Engine (PCE) and is implemented as a feature included as part of Cisco IOS-XR
operating system. The function is typically deployed on Cisco's virtual router, the XRv-9000 
as it involves control plane operations only. The SR-PCE
gains network topology awareness from BGP-LS advertisements received from the
underlying IGP network. Such knowledge is leveraged by the embedded multi-domain
computation engine to provide optimal path information to Path Computation
Element Clients (PCCs) using the Path Computation Element Protocol (PCEP).  

The PCC is the device where the service originates (PE) and therefore it
requires end-to-end connectivity over the segment routing enabled
multi-domain network.

## Agile networks using SRv6 or IPv4 unnumbered interfaces  

If building an IPv6/SRv6 based network, IS-IS utilizes link-local addresses for
node adjacencies. It does not require the operator number interfaces in a common
subnet like IPv4. This simplifies the overall deployment of the network and
allows an operator to insert nodes into an existing IS-IS adjacency path without
additional configuration.  If using IS-IS for IPv4, the operator can achieve
similar behavior by using unnumbered support.  

IS-IS and Segment Routing/SR-TE utilized in the Agile Metro design supports
using unnumbered IPv4 interfaces. In the topology database each interface is
uniquely identified by a combination of router ID and SNMP IfIndex value. 

![](http://xrdocs.io/design/images/asn-metro/cst-hld-unnumbered.png)

**Unnumbered interface configuration:**  

<div class="highlighter-rouge">
<pre class="highlight">
interface TenGigE0/0/0/2
 description to-AG2
 mtu 9216
 ptp
  profile My-Slave
  port state slave-only
  local-priority 10
 !
 service-policy input core-ingress-classifier
 service-policy output core-egress-exp-marking
<b> ipv4 point-to-point
 ipv4 unnumbered Loopback0 </b> 
 frequency synchronization
  selection input
  priority 10
  wait-to-restore 1
 !
!
</pre>
</div>

### SR-MPLS Area Border Routers – Anycast-SID

In the case of SR-MPLS and computing end to end paths using SR-TE with SR-PCE,
the use of Anycast SIDs is advisable. SR-PCE is aware of anycast SIDs in the
topology and will compute a path utilizing them at IGP instance boundaries,
creating a resilient end to end path for SR-MPLS SR-TE policies. In the event of
a failure of an ABR node, traffic will quickly reroute to the other node since
the SID being used in the SR-TE path is the same across all ABRs sharing the
same Anycast SID.  

### SRv6 and SR-MPLS black hole avoidance  

#### SR-MPLS Anycast SID 

Inter-domain resilience and load-balancing for SR-MPLS is satisfied by using the same
Anycast SID on each boundary node. Once the SR-PCE knows the location of a set
of Anycast SIDs, it will utilize the SID in the path computation to an egress
node. The SR-PCE will only utilize the Anycast SID if it has a valid path to the
next SID in the computed path, meaning if one ABR loses it's path to the
adjacent domain, the SR-PCE will update the head-end path with one utilizing a
normal node SID to ensure traffic is not dropped.   

It is also possible to withdraw an anycast SID from the topology by using the
conditional route advertisement feature for IS-IS. Once the anycast
SID Loopback has been withdrawn, it will no longer be used in a SR Policy path.
Conditional route advertisement can be used for SR-TE Policies with Anycast SIDs
in either dynamic or static SID candidate paths. Conditional route advertisement
is implemented by supplying the router with a list of remote prefixes to monitor
for reachability in the RIB. If those routes disappear from the RIB, the
interface route will be withdrawn.  

### SRv6 Unreachable Prefix Announcement (UPA) 
Summarization hides the state of longer prefixes within the aggregate
summary, leading to traffic loss or slower failover when an egress PE is
unreachable. UPA is an IGP function to quickly poison a prefix which has become
unreachable to an upstream node. It enables the notification of an individual
prefix becoming unreachable, outside of the local area/domain and across the
network in a manner that does not leave behind any persistent state in the
link-state database. When an ingress PE receives the UPA for an egress PE it can 
trigger fast switchover to an alternate path, such as a BGP PIC pre-programmed 
backup path.    


### SR-MPLS, SRv6, and Unified MPLS (BGP-LU) Co-existence 

In the Agile Metro design validation is performed for the co-existence of
services using BGP Labeled Unicast transport for inter-domain forwarding and
those using SR-MPLS and SRv6. Many networks deployed today have an existing BGP-LU design
which may not be easily migrated to SR, so graceful introduction between the two
transport methods is required.

## Agile Metro Edge Fabric
Agile Services Networking enables providers to build networks in the way that
best fits their business and service needs. One deployment method is build an
Edge Fabric allowing providers to build a flexible scale-out network providing
Edge services. Each leaf node in the fabric can be dedicated to a specific
service type or multiple services can be deployed to the same fabric. One key
property of the fabric is managing nodes by role and not as individual PE
routers. A role is defined by a set of common properties and service termination
needs. A fabric may be contained within a single location or span multiple
geographic locations, interconnected using Cisco's Routed Optical Networking
solution for simplicity and efficiency.    

![](http://xrdocs.io/design/images/asn-metro/metro-edge-fabric-diagram-1.png){:height="50%" width="50%"}

### Additional Edge Fabric properties  

- Topology-driven group of standard routers 
- Uses standard protocols for intra-fabric control-plane and data plane, 
not proprietary interconnect hardware and data plane 
- Service / UNI facing ports are managed on individual leaf devices  
- No requirement for homogenous hardware, different devices or even vendors could be used as leaves 
- Not explicitly a Clos fabric, the spines can be collapsed spine/border nodes 

### Edge Fabric deployment options 
There is also flexibility in how and where the Edge Fabric is deployed in the provider network.  
The diagram shows four potential options, but the deployment is primarily based on the provider requirements. The fully 
distributed edge offers the highest scale and performance, but as interim steps during migration other models may be used.  

![](http://xrdocs.io/design/images/asn-metro/metro-edge-fabric-deployment-options.png){:height="50%" width="50%"}

### Recommended Edge Fabric hardware 
There is no hard and fast rule about specific hardware deployed in a specific role. Spines should be higher bandwidth and higher port count devices with no service termination on those nodes. If fixed devices are used as spines, the Silicon One P100-based 8212-48FH-M and 8711-32FH-M are ideal spines due to their high 400G and 100G density. P100 routers and line cards also have Edge service capabilities if there is a requirement for placing some services on the spine devices. Edge Leaf devices should be chosen based on UNI port speeds, 
UNI port bandwidth, and in some cases specific feature support. The NCS 540, NCS 5500/5700, and 8000 series can be utilized for Internet services (DIA), peering, L2VPN, and L3VPN services. In the case of cnBNG user plane the ASR 9000 series satisfies that role.   

# Quality of Service 

## Overview 
Quality of Service is of utmost importance in today's multi-service converged
networks. The Agile Metro design has the ability to enforce end to end traffic
path SLAs using Segment Routing Traffic Engineering. In addition to satisfying
those path constraints, traditional QoS is used to make sure the PHB (Per-Hop
Behavior) of each packet is enforced at each node across the converged network.  

## NCS 540, 560, 5500, and 5700 QoS Primer 
Full details of the NCS 540 and 5500 QoS capabilities and configuration can be found at: 
<https://www.cisco.com/c/en/us/td/docs/iosxr/ncs5500/qos/24xx/configuration/guide/b-qos-cg-ncs5500-24xx.html>

The NCS platforms utilize the same MQC configuration for QoS as other IOS-XR platforms but based on their hardware architecture use different elements for implementing end to end QoS. On these platforms ingress traffic is: 
1. Matched using flexible criteria via Class Maps
2. Assigned to a specific <b>Traffic Class (TC)</b> and/or <b>QoS Group</b> for further treatment on egress 
3. Has its header marked with a specific IPP, DSCP, or MPLS EXP value

<B>Traffic Classes</b> are used internally for determining fabric priority and as the match condition for egress queuing.  <B>QoS Groups</b> are used internally as the match criteria for egress CoS header re-marking. IPP/DSCP marking and re-marking of ingress MPLS traffic is done using _ingress_ QoS policies.  MPLS EXP for imposed labels can be done on ingress or egress, but if you wish to rewrite both the IPP/DSCP and set an explicit EXP for imposed labels, the MPLS EXP must be set on egress.  

The <code>priority-level</code> command used in an egress QoS policy specifies the egress transmit priority of the traffic vs. other priority traffic. Priority levels can be configured as 1-7 with 1 being the highest priority.  Priority level 0 is reserved for best-effort traffic.  

Please note, multicast traffic does not follow the same constructs as unicast traffic for prioritization. All multicast traffic assigned to Traffic Classes 1-4 are treated as Low Priority and traffic assigned to 5-6 treated as high priority.     

## Cisco 8000 QoS  
The QoS configuration of the Cisco 8000 follows similar configuration guidelines
as the NCS 540, 5500, and NCS 5700 series devices. Detailed documentation of
8000 series QoS including platform dependencies can be found at:  

<https://www.cisco.com/c/en/us/td/docs/iosxr/cisco8000/qos/24xx/configuration/guide/b-qos-cg-8k-24xx.html> 

## Hierarchical Edge QoS 
Hierarchical QoS enables a provider to set an overall traffic rate across all services, and then configure parameters per-service via a child QoS policy where the percentages of guaranteed bandwidth are derived from the parent rate

### H-QoS platform support 
NCS platforms support 2-level and 3-level H-QoS. 3-level H-QoS applies a policer (ingress) or shaper (egress) to a physical interface, with each sub-interface having a 2-level H-QoS policy applied. Hierarchical QoS is not enabled by default on the NCS 540 and 5500 platforms. H-QoS is enabled using the <b>hw-module profile qos hqos-enable</b> command.  Once H-QoS is enabled, the number of priority levels which can be assigned is reduced from 1-7 to 1-4. Additionally, any hierarchical QoS policy assigned to a L3 sub-interface using priority levels must include a "shape" command.   

## Agile Services Core QoS mapping with five classes 
QoS designs are typically tailored for each provider, but we introduce a 5-level QoS design which can fit most provider needs. The design covers transport of both unicast and multicast traffic.  

| Traffic Type |  Core Marking | Core Priority | Comments | 
| ----------|---------|----------|---------------|-------------| 
| Network Control |  EXP 6 | Highest | Underlay network control plane |  
| Low latency | EXP 5 | Highest | Low latency service, consistent delay |  
| High Priority 1 | EXP 3 | Medium-High | High priority service traffic |     
| Medium Priority / Multicast | EXP 2  | Medium priority and multicast | 
| Best Effort | EXP 0 | General user traffic | 

### Example Core QoS Class and Policy Maps 
These are presented for reference only, please see the implementation guide for the full QoS configuration 

#### Class maps for ingress header matching
<div class="highlighter-rouge">
<pre class="highlight">
class-map match-any match-ef-exp5
 description High priority, EF 
 match dscp 46
 end-class-map
!
class-map match-any match-cs5-exp4
 description Second highest priority
 match dscp 40
 end-class-map
</pre>
</div>
<b>Ingress QoS policy</b> 
<div class="highlighter-rouge">
<pre class="highlight">
policy-map ingress-classifier
 class match-ef-exp5
  set traffic-class 2
  set qos-group 2
 !
 class match-cs5-exp4
  set traffic-class 3
  set qos-group 3
 ! 
 class class-default
  set traffic-class 0
  set dscp 0
  set qos-group 0
 !
 end-policy-map
</pre>
</div>

#### Class maps for egress queuing and marking policies
<div class="highlighter-rouge">
<pre class="highlight">
class-map match-any match-traffic-class-2
 description "Match highest priority traffic-class 2"
 match traffic-class 2
 end-class-map
!
class-map match-any match-traffic-class-3
 description "Match high priority traffic-class 3"
 match traffic-class 3
 end-class-map
!
class-map match-any match-qos-group-2
 match qos-group 2
 end-class-map
!
class-map match-any match-qos-group-3
 match qos-group 3
 end-class-map
</pre>
</div>

#### Egress QoS queuing policy 
<div class="highlighter-rouge">
<pre class="highlight">
policy-map egress-queuing
 class match-traffic-class-2
  priority level 2
 !
 class match-traffic-class-3
  priority level 3
 !
 class class-default
 !
 end-policy-map
</pre>
</div>

#### Egress QoS marking policy 
<div class="highlighter-rouge">
<pre class="highlight">
policy-map core-egress-exp-marking
 class match-qos-group-2
  set mpls experimental imposition 5
 !
 class match-qos-group-3
  set mpls experimental imposition 4
 class class-default
  set mpls experimental imposition 0
 !
 end-policy-map
</pre>
</div> 

# Multicast 

## L3 Multicast using SR-MPLS Tree-SID
### Tree SID Diagram 

![](http://xrdocs.io/design/images/asn-metro/cst-treesid.png)

### Tree-SID Overview 
Tree-SID utilizes the programmability of SR-PCE to create and
maintain an optimized multicast tree from source to receiver across an SR-only
IPv4 network.  Each node in the network maintains a session to the same set of SR-PCE
controllers. The SR-PCE creates the tree using PCE-initiated segments. TreeSID
supports advanced functionality such as TI-LFA for fast protection and disjoint
trees.  
### Static Tree-SID 

Multicast traffic is forwarded across the tree using static S,G mappings at the
head-end source nodes and tail-end receiver nodes. Providers needing a solution
where dynamic joins and leaves are not common, such as broadcast video
deployments, can be benefit from the simplicity static Tree-SID brings,
eliminating the need for distributed BGP mVPN signaling. Static Tree-SID is
supported for both default VRF (Global Routing Table) and mVPN.  

Please see the CST 3.5+ Implementation Guide for static Tree-SID configuration
guidelines and examples. 

### Dynamic Tree-SID using BGP mVPN Control-Plane 

IOS-XR supports using fully dynamic signaling to create multicast
distribution trees using Tree-SID. Sources and receivers are discovered using
BGP auto-discovery (BGP-AD) and advertised throughout the mVPN using the IPv4 or
IPv6 mVPN AFI/SAFI. Once the source head-end node learns of receivers, the
head-end will create a PCEP request to the configured primary PCE. The PCE then
computes the optimal multicast distribution tree based on the metric-type and
constraints specified in the request. Once the Tree-SID policy is up, multicast
traffic will be forwarded using the tree by the head-end node. Tree-SID
optionally supports TI-LFA for all segments, and the ability to create disjoint
trees for high available applications.   

All routers across the network needing to participate in the tree, including
core nodes, must be configured as a PCC to the primary PCE being used by the
head-end node.  

Please see the Agile Services Networking Implementation Guide for more information 
on implementing SR-MPLS Tree-SID. 

## L3 IP Multicast and mVPN using mLDP  
The Agile Metro design supports using mLDP for multicast distribution when using 
SR-MPLS or SRv6 for unicast transport.  
Using BGP signaling adds additional scale to the network over in-band
mLDP signaling and fits with the overall design goals of CST. More information
about deployment of profile 14 can be found in the Agile Metro implementation
guide. The Agile Services Networking design supports mLDP-based label switched multicast
within a single doman and across IGP domain boundaries. In the case of the Agile
Metro design multicast has been tested with the source and receivers on both
access and ABR PE devices.   

| Supported Multicast Profiles | Description |  
| ----------------------- | ---------------- | 
| Profile 6 | mLDP VRF using in-band signaling | 
| Profile 7 | mLDP global routing table using in-band signaling | 
| Profile 14 | Partitioned MDT using BGP-AD and BGP c-multicast signaling |  

Profile 14 is recommended for all service use cases and supports both
intra-domain and inter-domain transport use cases.  

### LDP Auto-configuration 
LDP can automatically be enabled on all IS-IS interfaces with the following configuration in the IS-IS configuration 
<div class="highlighter-rouge">
<pre class="highlight">
router isis ACCESS
 address-family ipv4 unicast
  mpls ldp auto-config
</pre> 
</div> 

### LDP mLDP-only Session Capability (RFC 7473)  
IOS-XR has the ability to only advertise mLDP state on each router adjacency, eliminating the need to filter LDP unicast FECs from advertisement into the network. This is done using the SAC (State Advertisement Control) TLV in the LDP initialization messages to advertise which LDP FEC classes to receive from an adjacent peer.  We can restrict the capabilities to mLDP only using the following configuration.  Please see the implementation guide and configurations for the full LDP configuration.   

<div class="highlighter-rouge">
<pre class="highlight">
mpls ldp
 capabilities sac mldp-only
</pre> 
</div> 

# Agile Metro Use Cases

Service Provider networks must adopt a very flexible design that satisfy
any to any connectivity requirements, without compromising in stability
and availability. Moreover, transport programmability is essential to
bring SLA awareness into the network. 

The goal of the Agile Metro is to provide a flexible network
blueprint that can be easily customized to meet customer specific
requirements. This blueprint must adapt to carry any service type, for example  
cable access, mobile, and business services over the same converged network infrastructure. 
The following sections highlight the use cases and the components of the 
design used in building those solutions.  

# Mobile transport 

## Summary and 5G Service Types  
The Agile Metro design introduces support for 5G networks and 5G services. There are a variety of new service use cases being defined by 3GPP for use on 5G networks, illustrated by the figure below. Networks must now be built to support the stringent SLA requirements of Ultra-Reliable Low-Latency services while also being able to cope with the massive bandwidth introduced by Enhanced Mobile Broadband services. The initial support for 5G in the Converged SDN Transport design focuses on the backhaul and midhaul portions of the network utilizing end to end Segment Routing. The design introduces no new service types, the existing scalable L3VPN and EVPN based services using BGP are sufficient for carrying 5G control-plane and user-plane traffic.   

## Key Validated Components 
The following key features have been added to the CST validated design to support 5G deployments

### End to End Timing Validation 
End to end timing using PTP with profiles G.8275.1 and G.8275.2 have been
validated in the CST design. Best practice configurations are available in the
online configurations and CST Implementation Guide. It is recommended to use
G.8257.1 when possible to main the highest level of accuracy across the network.
IOS-XR fully supports G.8275.1 to G.8275.2 interworking,
allowing the use of different profiles across the network. Synchronous Ethernet
(SyncE) is also recommended across the network to maintain stability when timing
to the PRC. 

### Low latency SR-TE path computation
The "latency" constraint type is used either with a configured SR Policy or ODN
SR Policy specifies the computation engine to compute the lowest latency path
across the network. The latency computation algorithm can use different
mechanisms for computing the end to end path. The first and preferred mechanism
is to use the realtime measured per-link one-way delay across the network. This
measured information is distributed via IGP extensions across the IGP domain and
to external PCEs using BGP-LS extensions for use in both intra-domain and
inter-domain calculations. Two other metric types can also be utilized as part
of the "latency" path computation. The TE metric, which can be defined on all SR
IS-IS links and the regular IGP metric can be used in the absence of the
link-delay metric. More information on Performance Measurement for link delay can 
be found at <https://www.cisco.com/c/en/us/td/docs/routers/asr9000/software/asr9k-r7-5/segment-routing/configuration/guide/b-segment-routing-cg-asr9000-75x/configure-performance-measurement.html> 
Performance Measurement is supported on all hardware used in the CST design.  

#### <b>Dynamic Link Performance Measurement</b>  
Starting in version 3.5 of the CST, dynamic measurement of one-way and two-way
latency on logical links is fully supported across all devices. The delay
measurement feature utilizes TWAMP-Lite as the transport mechanism for probes
and responses. PTP is a requirement for accurate measurement of one-way latency
across links and is recommended for all nodes.  In the absence of PTP a
"two-way" delay mode is supported to calculate the one-way link delay. It is
recommended to configure one-way delay on all IS-IS core links within the CST
network. A sample configuration can be found below and detailed configuration
information can be found in the implementation guide. 

One way delay measurement is also available for SR-TE Policy paths to give the
provider an accurate latency measurement for all services utilizing the SR-TE
Policy. This information is available through SR Policy statistics using the CLI
or model-driven telemetry. The latency measurement is done for all active
candidate paths.   

Dynamic one-way link delay measurements using PTP are not currently supported on unnumbered interfaces. In the case of unnumbered interfaces, static link delay values must be used.    

Different metric types can be used in a single path computation, with the following order used:  
1. Unidirectional link delay metric either computed or statically defined  
2. Statically defined TE metric 
3. IGP metric 

#### SR Policy latency constraint configuration on configured policy  
<div class="highlighter-rouge">
<pre class="highlight">
segment-routing
  traffic-eng
    policy LATENCY-POLICY 
      color 20 end-point ipv4 1.1.1.3
      candidate-paths
        preference 100
          dynamic mpls
            metric
              type latency
</pre>
</div>

#### SR Policy latency constraint configuration for ODN policies 
<div class="highlighter-rouge">
<pre class="highlight">
segment-routing
 traffic-eng
  on-demand color 100 
   dynamic
    pcep
    !
    metric
     type latency
</pre>
</div>

#### Dynamic link delay metric configuration 
<div class="highlighter-rouge">
<pre class="highlight">
performance-measurement
 interface TenGigE0/0/0/10
  delay-measurement
 interface TenGigE0/0/0/20
  delay-measurement
  !
 ! 
  protocol twamp-light
  measurement delay
   unauthenticated
    querier-dst-port 12345
   !
  !
 !
 delay-profile interfaces
  advertisement
   accelerated
    threshold 25
   !
   periodic
    interval 120
    threshold 10
   !
  !
  probe
   measurement-mode one-way 
   protocol twamp-light
   computation-interval 60
  !
 !
</pre>
</div>

#### Static defined link delay metric
Static delay is set by configuring the "advertise-delay" value in microseconds under each interface 

<div class="highlighter-rouge">
<pre class="highlight">
performance-measurement
 interface TenGigE0/0/0/10
  delay-measurement
   advertise-delay 15000
 interface TenGigE0/0/0/20
  delay-measurement
   advertise-delay 10000
</pre>
</div>

#### TE metric definition  
<div class="highlighter-rouge">
<pre class="highlight">
segment-routing
 traffic-eng
  interface TenGigE0/0/0/10
   metric 15
  !
  interface TenGigE0/0/0/20
   metric 10
</pre>
</div>

The link-delay metrics are quantified in the unit of microseconds.  On most
networks this can be quite large and may be out of range from normal IGP
metrics, so care must be taken to ensure proper compatibility when mixing metric
types. The largest possible IS-IS metric is 16777214 which is equivalent to
16.77 seconds.    

### SR Policy one-way delay measurement 
In addition to the measurement of delay on physical links, the end to end
one-way delay can also be measured across a SR Policy. This allows a provider to
monitor the traffic path for increases in delay and log/alarm when thresholds
are exceeded. Please note SR Policy latency measurements are not supported for
PCE-computed paths, only those using head-end computation or configured static
segment lists.  The basic configuration for SR Policy measurement follows:  

<div class="highlighter-rouge">
<pre class="highlight">
performance-measurement
 delay-profile sr-policy
  advertisement
   accelerated
    threshold 25
   !
   periodic
    interval 120
    threshold 10
   !
   threshold-check
    average-delay
   !
  !
  probe
   tos
    dscp 46
   !
   measurement-mode one-way
   protocol twamp-light
   computation-interval 60
   burst-interval 60
  !
 !
 protocol twamp-light
  measurement delay
   unauthenticated
    querier-dst-port 12345
   !
  !
 !
!
segment-routing
 traffic-eng
  policy APE7-PM
   color 888 end-point ipv4 100.0.2.52
   candidate-paths
    preference 200
     dynamic
      metric
       type igp
      !
     !
    !
   !
   performance-measurement
    delay-measurement
     logging
      delay-exceeded
</pre>
</div>

### IP Endpoint Delay Measurement 
In CST 5.0+ IOS-XR's Performance Measurement is extended to perform SLA 
measurements between IP endpoints across multi-hop paths. Delay measurements 
as well as liveness detection are supported. Model-driven telemetry as well as 
CLI commands can be used to monitor the path delay.  

#### Global Routing Table IP Endpoint Delay Measurement 
<div class="highlighter-rouge">
<pre class="highlight">
performance-measurement
 endpoint ipv4 1.1.1.5
  source-address ipv4 1.1.1.1
  delay-measurement
  !
 !
 delay-profile endpoint default
  probe
   measurement-mode one-way
</pre>
</div>

#### VRF IP Endpoint Delay Measurement 
<div class="highlighter-rouge">
<pre class="highlight">
performance-measurement
 endpoint ipv4 10.10.10.100 vrf green
  source-address ipv4 1.1.1.1
  delay-measurement
  !
 !
 delay-profile endpoint default
  probe
   measurement-mode one-way
</pre>
</div>

### Segment Routing Flexible Algorithms for 5G Slicing 
SR Flexible Algorithms, outlined earlier in the transport section, give
providers a powerful mechanism to segment networks into topoligies defined by
SLA requirements. The SLA-driven topologies solve the constraints of specific 5G
service types such as Ulta-Reliable Low-Latency Services. Using SR with a packet
dataplane ensures the most efficient network possible, unlike slicing solutions
using optical transport or OTN.  

### End to end network QoS with H-QoS on Access PE 
QoS is of utmost importance for ensuring the mobile control plane and critical
user plane traffic meets SLA requirements. Overall network QoS is covered in the
QoS section in this document, this section will focus on basic Hierarchical QoS
to support 5G services. 

H-QoS enables a provider to set an overall traffic rate across all services, and
then configure parameters per-service via a child QoS policy where the
percentages of guaranteed bandwidth are derived from the parent rate. NCS
platforms support 2-level and 3-level H-QoS. 3-level H-QoS applies a policer
(ingress) or shaper (egress) to a physical interface, with each sub-interface
having a 2-level H-QoS policy applied.  


#### CST QoS mapping with 5 classes 

| Traffic Type | Ingress Marking | Core Marking | Comments | 
| ----------|---------|----------|---------------|-------------| 
| Low latency | IPP 5  | EXP 5 | URLLC, consistent delay, small buffer|  
| 5G Control Plane | IPP 4 | EXP 4 | Mobile control and billing |    
| High Priority Service | IPP 3 (in contract), 1 (out of contract) | EXP 1,3 | Business service | 
| Best Effort | IPP 0 | EXP 0 | General user traffic | 
| Network Control | IPP 6 | EXP 6 | Underlay network control plane |  

# FTTH Design using EVPN E-Tree 

## Summary 
Many providers today are migrating from L2 access networks to more flexible L3 underlay networks using xVPN overlays to support a variety of network services. L3 networks offer more flexibility in terms of topology, resiliency, and support of both L2VPN and L3VPN services. Using a converged aggregation and access network simplifies networks and reduced both capex and opex spend by eliminating duplicate networks. Fiber to the home networks using active Ethernet have typically used L2 designs using proprietary methods like Private VLANs for subscriber isolation. EVPN E-Tree gives us a modern alternative to provide these services across a converged L3 Segment Routing network. This use case highlights one specific use case for E-Tree, however there are a number of other business and subscriber service use cases benefitting from EVPN E-Tree.   

## E-Tree Diagram 
<img src="http://xrdocs.io/design/images/asn-metro/cst-etree.png" width="500"/>

## E-Tree Operation 
One of the strongest features of EVPN is its dynamic signaling of PE state across the entire EVPN virtual instance. E-Tree extends this paradigm by signaling between EVPN PEs which Ethernet Segments are considered root segments and which ones are considered leaf segments. Similar to hub and spoke L3VPN networks, traffic is allowed between root/leaf and root/root interfaces but not between leaf interfaces either on the same node or on different nodes. EVPN signaling creates the forwarding state and entries to restrict traffic forwarding between endpoints connected to the same leaf Ethernet Segment.   

### Split-Horizon Groups 
E-Tree enables split horizon groups on access interfaces within the same Bridge Domain/EVI configured for E-Tree to prohibit direct L2 forwarding between these interfaces. 

### L3 IRB Support  
In a fully distributed FTTH deployment, a provider may choose to put the L3 gateway for downstream access endpoints on the leaf device. The L3 BVI interface defined for the E-Tree 
BD/EVI is always considered a root endpoint. E-Tree operates at L2 so when a L3 interface is present traffic will be forwarded at L3 between leaf endpoints. Note L2 leaf devices using 
a centralized IRB L3 GW on an E-Tree root node is not currently supported. In this type of deployment where the L3 GW is not located on the leaf the upstream L3 GW node must be attached via a L2 interface into the E-Tree root node Bridge Domani/EVI. 
It is recommended to locate the L3 GW on the leaf device if possible.  

### Multicast Traffic 
Multicast traffic across the E-Tree L2/L3 network is performed using ingress replication from the source to the receiver nodes. It is important to use IGMP or MLDv2 snooping in order to minimize the flooding of 
multicast traffic across the entire Ethernet VPN instance. When snooping is utilized, traffic is only sent to EVPN PE nodes with interested receivers instead of all PEs in the EVI.   

### Ease of Configuration
Configuring a node as a leaf in an E-Tree EVI requires only a single command "etree" to be configured under the EVI in the global EVPN configuration. Please see the Implementation Guide for specific configuration examples.  

<div class="highlighter-rouge">
<pre class="highlight">
l2vpn
 bridge group etree
  bridge-domain etree-ftth 
  interface TenGigE0/0/0/23.1098
  routed interface BVI100 
  ! 
  evi 100 
 !
!
evpn
  evi 100
<b>   etree 
   leaf</b> 
   !
  advertise-mac
  !
 ! 
</pre>
</div>

# Cisco Cloud Native Broadband Network Gateway 

cnBNG represents a fundamental shift in how providers build converged access
networks by separating the subscriber BNG control-plane functions from
user-plane functions. CUPS (Control/User-Plane Separation) allows the use of
scale-out x86 compute for subscriber control-plane functions, allowing providers
to place these network functions at an optimal place in the network, and also
allows simplification of user-plane elements. This simplification enables
providers to distribute user-plane elements closer to end users, optimizing
traffic efficiency to and from subscribers. In the CST 5.0 design we include
both traditional physical BNG (pBNG) and the newer cnBNG architecture.  

## Cisco cnBNG Architecture

Cisco's cnBNG supports the BBF TR-459 standards for control and user plane
communication. The State Control Interface (SCi) is used for programming and
management of dynamic subscriber interfaces including accounting information.
The Control Packet Redirect Interface (CPRi) as its name implies redirects user
packets destined for control-plane functions from the user plane to control
plane. These include: DHCP DORA, DHCPv6, PPPoE, and L2TP. More information on 
TR-459 can be found at <https://www.broadband-forum.org/marketing/download/TR-459.pdf> 

### cnBNG Control Plane 
The cloud native BNG control plane is a highly resilient scale out architecture.
Traditional physical BNGs embedded in router software often scale poorly,
require complex HA mechnaisms for resiliency, and are relatively painful to
upgrade. Moving these network functions to a modern Kubernetes based
cloud-native infrastructure reduces operator complexity providing native
scale-out capacity growth, in-service software upgrades, and faster feature
delivery.  

### cnBNG User Plane 
The cnBNG user plane is provided by Cisco ASR 9000 routers. The routers are
responsible for terminating subscriber sessions (IPoE/PPPoE), communicating with
the cnBNG control plane for user authentication and policy, applying
subscriber policy elements such as QoS and security policies, and performs 
subscriber routing. Fixed and modular platforms are supported  



# Business and Infrastructure Services using L3VPN and EVPN 

## EVPN Multicast 
Multicast within a L2VPN EVPN has been supported since Agile Metro 1.0. Multicast traffic within an EVPN is replicated to the endpoints interested in a specific group via EVPN signaling. EVPN utilizes ingress replication for all multicast traffic, meaning multicast is encapsulated with a specific EVPN label and unicast to each PE router with interested listeners for each multicast group. Ingress replication may add additional traffic to the network, but simplifies the core and data plane by eliminating multicast signaling, state, and hardware replication.  EVPN multicast is also not subject to domain boundary restrictions.

### EVPN Centralized Gateway Multicast 
In CGW deployments, EVPN multicast is enhanced with support for EVPN Route Type
6 (RT-6), the Selective Multicast Ethernet Tag Route. RT-6 or SMET routes are
used to distribute a leaf node's interest in a specific multicast S,G. This
allows the sender node to only transmit the multicast traffic to an EVPN router
with an interested receiver instead of sending unwanted traffic dropped on the
remote router. In release 5.0 CGW is supported on ASR 9000 routers only.  CGW
selective multicast is supported for IPv4 and *,G multicast.   

## LDP to Agile Metro Migration  
Very few networks today are built as greenfield networks, most new designs are migrated 
from existing ones and must support some level of interop during migration. In the Agile Metro 
design we tackle one of the most common migration scenarios, LDP to the Agile Metro design. The following 
sections explain the configuration and best practices for performing the migration. The design is 
applicable to transport and services originating and terminating in the same LDP domain.     

### Towards Agile Metro Design  
The Agile Metro design utilizes isolated IGP domains in different parts of the network, with each domain 
separated at a logical boundary by an ASBR router. SR-PCE is used to provide end to end paths across the 
inter-domain network. LDP does not support inter-domain transport, only between LDP FECs in the 
same IGP domain. It is recommended to plan logical boundaries if necessary when doing a flat LDP migration to 
the Agile Metro design, so that when migration is complete the future scale benefits can be realized.  
 
### Segment Routing Enablement 
One must define the global Segment Routing Block (SRGB) to be used across the network on every node 
participating in SR. There is a default block enabled by default but it may not be large enough to support
an entire network, so it's advised to right-size this value for your deployment. The current maximum SRGB size
for SR-MPLS is 256K entries. 

Enabling SR in IS-IS requires only issuing the command "segment-routing mpls" under the IPv4 
address-family and assigning a prefix-sid value to any loopback interfaces you require the node 
be addressed towards as a service destination. Enabling TI-LFA is done on a per-interface basis 
in the IS-IS configuration for each interface. 

Enabling SR-Prefer within IS-IS aids in migration by preferring a SR prefix-sid to a 
prefix over an LDP prefix, allowing a seamless migration to SR without needing to enable 
SR completely within a domain.  
 
### Segment Routing Mapping Server Design
One component introduced with Segment Routing is the SR Mapping Server (SRMS), a control-plane 
element converting unicast LDP FECs to Segment Routing prefix-SIDs for advertisement 
throughout the Segment Routing domain. Each separate IGP domain requires a pair of 
SRMS nodes until full migratino to SR is complete.   

# Network Assurance 

## SR Performance Measurement  
The network itself can perform dynamic performance measurement between any two
endpoints in the network. Performance measurement includes delay and loss
calculations. It is recommended SR-PM be enabled on all logical links across
the network.  

### Dynamic Link Performance Measurement
SR-PM supports dynamic measurement of one-way and two-way
delay and loss on logical links. The delay
measurement feature utilizes TWAMP-Lite as the transport mechanism for probes
and responses. PTP is a requirement for accurate measurement of one-way latency
across links and is recommended for all nodes.  In the absence of PTP a
"two-way" delay mode is supported to calculate the one-way link delay.

Legacy hardware also now supports a software CPU based timestamp method to enable
SR-PM delay measurements for hardware with PTP timing hardware.  

Delay and loss measurement is also available for SR-TE Policy paths to give the
provider an accurate latency and loss measurement for all services utilizing the SR-TE
Policy. This information is available through SR Policy statistics using the CLI
or model-driven telemetry. The latency measurement is done for all active
candidate paths.  

### Delay and Loss anomaly detection  
It is possible to set thresholds for both delay and loss and trigger behaviors
based on the type of resource being monitored using SR-PM. In the case of a
SR-Policy, a candidate path can be deactivated if the delay or loss exceeds the
configured thresholds. In the case of a logical link, the IGP advertising the
link will set the "A" or anomaly bit for the link. When a receiving node
receives the IGP link state data with the A bit set, it can raise the IGP cost
on the link. 

The "anomaly-check" command is used for delay thresholds, and the "anomaly-loss"
command is used for loss thresholds.  

### Sample SR-PM configuration 

<div class="highlighter-rouge">
<pre class="highlight">

performance-measurement
 interface TenGigE0/0/0/5
  delay-measurement
  !
 !
 interface TenGigE0/0/0/23
  delay-measurement
  !
 !
 interface HundredGigE0/0/1/0
  delay-measurement
  !
 !
 interface HundredGigE0/0/1/1
  delay-measurement
  !
 !
 delay-profile interfaces default
  advertisement
   accelerated
    threshold 25
   !
   anomaly-check upper-bound 1000 lower-bound 100
   periodic
    interval 120
    threshold 10
   !
   anomaly-loss upper-bound 20 lower-bound 10
  !
  probe
   measurement-mode two-way
   protocol twamp-light
  !
 !
 protocol twamp-light
  measurement delay
   unauthenticated
    querier-dst-port 12345

</div> 
</pre> 


# Security 

## Security overview 

## Edge DDoS Protect
Cisco's Edge DDoS Protect presents an innovative solution providing fully distributed 
DDoS protection for all places in the network.  Edge DDoS Protect  

# Automation 

## Network Management using Cisco Crosswork Network Controller 

Crosswork Network Controller provides a platform for UI and API based network 
management. CNC supports RSVP-TE, SR-TE Policy, L2VPN, and L3VPN provisioning 
using standards based IETF models.

More information on Crosswork Network Controller can be found at: 
<https://www.cisco.com/c/en/us/products/cloud-systems-management/crosswork-network-controller/index.html>

### L2VPN Service Provisioning and Visualization
Crosswork Network Controller supports UI and API based provisioning of EVPN-VPWS 
services using the IETF L2NM standard model. Once services are provisionined they 
are visualized using the CNC topology UI along with their underlying SR-TE policies, 
if applicable.  

![](http://xrdocs.io/design/images/asn-metro/cst-5-cnc-l2vpn.png)

### L3VPN Service Provisioning and Visualization
Crosswork Network Controller supports UI and API based provisioning of L3VPN  
services using the IETF L3NM standard model. Once services are provisionined they 
are visualized using the CNC service topology UI along with their underlying SR-TE policies, 
if applicable.  

![](http://xrdocs.io/design/images/asn-metro/cst-5-cnc-l3vpn.png)

### Crosswork Automated Assurance 

In addition to provisioning, monitoring of all 
transport infrastructure is also supported including advanced service assurance for 
xVPN services. Service assurance checks all aspects of the network making up the service 
along with realtime Y.1731 measurements to ensure the defined SLA for the service is met.  

![](http://xrdocs.io/design/images/asn-metro/cst-5-cnc-service-assurance-sla.png)

![](http://xrdocs.io/design/images/asn-metro/cst-5-cnc-assurance.png)

The figure below shows an example of a degraded service where the measured
one-way latency on the end to end path of 1680uS has exceeded the SLA of 500uS. 

![](http://xrdocs.io/design/images/asn-metro/cst-5-cnc-l2vpn-degraded.png)

## Zero Touch Provisioning

In addition to model-driven configuration and operation, Agile Metro 1.5 
supports ZTP operation for automated device provisioning. ZTP is useful both in 
production as well as staging environments to automate initial device software 
installation, deploy an initial bootstrap configuration, as well as advanced functionality 
triggered by ZTP scripts. ZTP is supported on both out of band management interfaces as 
well as in-band data interfaces. When a device first boots, the IOS-XR ZTP process
beging on the management interface of the device and if no response is received, or the 
the interface is not active, the ZTP process will begin the process on data ports. IOS-XR
can be part of an ecosystem of automated device and service provisioning via Cisco NSO.  

![](http://xrdocs.io/design/images/asn-metro/ztp-metro-fabric.png)

### Zero Touch Provisioning using Crosswork Network Controller 

Crosswork Network Controller now includes a ZTP application used to onboard network 
devices with the proper IOS-XR software and base configuration. Crosswork ZTP 
supports both traditional unsecure as well as fully secure ZTP operation as outlined 
in RFC 8572. More information on Crosswork ZTP can be found at 
<https://www.cisco.com/c/en/us/products/collateral/cloud-systems-management/crosswork-network-automation/datasheet-c78-743677.html> 

## Transport and Service Management using Crosswork Network Controller
Crosswork Network Controller provides support for provisioning SR-MPLS and SRv6   
traffic engineering policies as well as managing the VPN services utilizing those
paths or standard IGP based Segment Routing paths.   

# Base Services Supporting Advanced Use Cases  
## Overview

The Agile Metro Design aims to enable simplification across all
layers of a Service Provider network. Thus, the  Agile Metro
services layer focuses on a converged Control Plane based on BGP.

BGP based Services include EVPNs and Traditional L3VPNs (VPNv4/VPNv6).

EVPN is a technology initially designed for Ethernet multipoint services
to provide advanced multi-homing capabilities. By using BGP for
distributing MAC address reachability information over the MPLS network,
EVPN brought the same operational and scale characteristics of IP based
VPNs to L2VPNs. Today, beyond DCI and E-LAN applications, the EVPN
solution family provides a common foundation for all Ethernet service
types; including E-LINE, E-TREE, as well as data center routing and
bridging scenarios. EVPN also provides options to combine L2 and L3
services into the same instance.

To simplify service deployment, provisioning of all services is fully
automated using Cisco Network Services Orchestrator (NSO) using (YANG)
models and NETCONF. Refer to Section: "Network Services Orchestrator (NSO)".

There are two types of services: End-To-End and Hierarchical. The next
two sections describe these two types of services in more detail.

## Ethernet VPN (EVPN)

EVPNs solve two long standing limitations for Ethernet Services in
Service Provider Networks:

  - Multi-Homed & All-Active Ethernet Access

  - Service Provider Network - Integration with Central Office or with
    Data Center
    
### Ethernet VPN Hardware Support 

In CST 3.0+ EVPN ELAN, ETREE, and VPWS services are supported on all IOS-XR
devices. The ASR920 running IOS-XE does not support native EVPN services in the
CST design, but can integrate into an overall EVPN service by utilizing service
hierarchy. Please see the tables under End-to-End and Hierarchical Services for
supported service types.  

### Multi-Homed & All-Active Ethernet Access

Figure 21 demonstrates the greatest limitation of traditional L2
Multipoint solutions like
VPLS.

![](http://xrdocs.io/design/images/asn-metro/image22.png)

_Figure 21: EVPN All-Active Access_

When VPLS runs in the core, loop avoidance requires that PE1/PE2 and
PE3/PE4 only provide Single-Active redundancy toward their respective
CEs. Traditionally, techniques such mLACP or Legacy L2 protocols like
MST, REP, G.8032, etc. were used to provide Single-Active access
redundancy.

The same situation occurs with Hierarchical-VPLS (H-VPLS), where the
access node is responsible for providing Single-Active H-VPLS access by
active and backup spoke pseudowire (PW).

All-Active access redundancy models are not deployable as VPLS
technology lacks the capability of preventing L2 loops that derive from
the forwarding mechanisms employed in the Core for certain categories of
traffic. Broadcast, Unknown-Unicast and Multicast (BUM) traffic sourced
from the CE is flooded throughout the VPLS Core and is received by all
PEs, which in turn flood it to all attached CEs. In our example PE1
would flood BUM traffic from CE1 to the Core, and PE2 would sends it
back toward CE1 upon receiving it.

EVPN uses BGP-based Control Plane techniques to address this issue and
enables Active-Active access redundancy models for either Ethernet or
H-EVPN access.

Figure 22 shows another issue related to BUM traffic addressed by
EVPN.

![](http://xrdocs.io/design/images/asn-metro/image23.png)

_Figure 22: EVPN BUM Duplication_

In the previous example, we described how BUM is flooded by PEs over the
VPLS Core causing local L2 loops for traffic returning from the core.

Another issue is related to BUM flooding over VPLS Core on remote PEs.
In our example either PE3 or PE4 receive and send the BUM traffic to
their attached CEs, causing CE2 to receive duplicated BUM traffic.

EVPN also addresses this second issue, since the BGP Control Plane
allows just one PE to send BUM traffic to an All-Active EVPN access.

Figure 23 describes the last important EVPN
enhancement.

![](http://xrdocs.io/design/images/asn-metro/image24.png)

_Figure 23: EVPN MAC Flip-Flopping_

In the case of All-Active access, traffic is load-balanced (per-flow)
over the access PEs (CE uses LACP to bundle multiple physical ethernet
ports and uses hash algorithm to achieve per flow load-balancing).
Remote PEs, PE3 and PE4, receive the same flow from different neighbors.
With a VPLS core, PE3 and PE4 would rewrite the MAC address table
continuously, each time the same mac address is seen from a different
neighbor.

EVPN solves this by mean of “Aliasing”, which is also signaled via the
BGP Control Plane.

### Service Provider Network - Integration with Central Office or with Data Center

Another very important EVPN benefit is the simple integration with
Central Office (CO) or with Data Center (DC). Note that Metro Central
Office design is not covered by this document.

The adoption of EVPNs provides huge benefits on how L2 Multipoint
technologies can be deployed in CO/DC. One such benefit is the converged
Control Plane (BGP) and converged data plane (SR MPLS/SRv6) over SP WAN
and CO/DC network.

Moreover, EVPNs can replace existing proprietary Ethernet
Multi-Homed/All-Active solutions with a standard BGP-based Control
Plane.

## End-To-End (Flat) Services

The End-To-End Services use cases are summarized in the table in Figure
24 and shown in the network diagram in Figure 25.

![](http://xrdocs.io/design/images/asn-metro/cst-services-flat-5.png)

_Figure 24: End-To-End – Services table_

![](http://xrdocs.io/design/images/asn-metro/image26.png)

_Figure 25: End-To-End – Services_

All services use cases are based on BGP Control Plane.

Refer also to Section: "Transport and Services Integration".

## Hierarchical Services

Hierarchical Services Use Cases are summarized in the table of Figure 26
and shown in the network diagram of Figure 27.

![](http://xrdocs.io/design/images/asn-metro/cst-services-hierarchical-5.png)

_Figure 26: Supported Hierarchical Services_ 

![](http://xrdocs.io/design/images/asn-metro/image28.png)

_Figure 27: Hierarchical Services Control Plane_

Hierarchical services designs are critical for Service Providers looking
for limiting requirements on the access platforms and deploying more
centralized provisioning models that leverage very rich features sets on
a limited number of touch points.

Hierarchical Services can also be required by Service Providers who want
to integrate their SP-WAN with the Central Office/Data Center network
using well-established designs based on Data Central Interconnect (DCI).

Figure 27 shows hierarchical services deployed on PE routers, but the
same design applies when services are deployed on AG or DCI routers.

The Agile Metro Design offers scalable hierarchical services with
simplified provisioning. The three most important use cases are
described in the following sections:

  - Hierarchical L2 Multipoint Multi-Homed/All-Active

  - Hierarchical L2/L3 Multi/Single-Home, All/Single-Active Service
    (H-EVPN) and Anycast-IRB

  - Hierarchical L2/L3 Multipoint Multi-Homed/Single-Active (H-EVPN) and
    PWHE
    
### Hierarchical L2 Multipoint Multi-Homed/All-Active

Figure 28 shows a very elegant way to take advantage of the benefits of
Segment-Routing Anycast-SID and EVPN. This use case provides
Hierarchical L2 Multipoint Multi-Homed/All-Active (Single-Homed Ethernet
access) service with traditional access router
integration.

![](http://xrdocs.io/design/images/asn-metro/image29.png)

_Figure 28: Hierarchical Services (Anycast-PW)_

Access Router A1 establishes a Single-Active static pseudowire
(Anycast-Static-PW) to the Anycast IP address of PE1/PE2. PEs anycast IP
address is represented by Anycast-SID.

Access Router A1 doesn’t need to establish active/backup PWs as in a
traditional H-VPLS design and doesn’t need any enhancement on top of the
established spoke pseudowire design.

PE1 and PE2 use BGP EVPN Control Plane to provide Multi-Homed/All-Active
access, protecting from L2 loop, and providing efficient per-flow
load-balancing (with aliasing) toward the remote PEs (PE3/PE4).

A3, PE3 and PE4 do the same, respectively.

### Hierarchical L2/L3 Multi/Single-Home, All/Single-Active Service (H-EVPN) and Anycast-IRB

Figure 29 shows how EVPNs can completely replace the traditional H-VPLS
solution. This use case provides the greatest flexibility as
Hierarchical L2 Multi/Single-Home, All/Single-Active modes are available
at each layer of the service
hierarchy.

![](http://xrdocs.io/design/images/asn-metro/image30.png)

_Figure 29: Hierarchical Services (H-EVPN)_

Optionally, Anycast-IRB can be used to enable Hierarchical L2/L3
Multi/Single-Home, All/Single-Active service and to provide optimal L3
routing.

### Hierarchical L2/L3 Multipoint Multi-Homed/Single-Active (H-EVPN) and PWHE

Figure 30 shows how the previous H-EVPN can be extended by taking
advantage of Pseudowire Headend (PWHE). PWHE with the combination of
Multi-Homed, Single-Active EVPN provides an Hierarchical L2/L3
Multi-Homed/Single-Active (H-EVPN) solution that supports QoS.

It completely replaces traditional H-VPLS based solutions. This use case
provides Hierarchical L2 Multi/Single-Home, All/Single-Active
service.

![](http://xrdocs.io/design/images/asn-metro/image31.png)

_Figure 30: Hierarchical Services (H-EVPN and PWHE)_

Refer also to the section: “Transport and Services Integration”.

### EVPN Centralized Gateway
Similar to the Hierarchical L2/L3 service with Anycast-IRB, EVPN Centralized 
Gateway extends that service type by allowing the use of EVPN-ELAN services between 
the access site and core location. In previous versions the Anycast-IRB L3 gateway needed 
to be part of the access L2 domain and could not be placed elsewhere in the EVPN across
the core network.  EVPN CGW relaxes the constraint and allows the L3 Anycast IRB gateway 
to be located at any point in the EVPN ELAN. The IRB can be placed in either the global 
routing table or within a VRF. 

In CST 5.0 EVPN Centralized GW is supported on the ASR 9000 platform.  

The figure below shows an example EVPN CGW deployment. In this scenario A-PE3,
A-PE4, A-PE5, PE1, and PE2 all belong to the same EVPN-ELAN EVI 100. The CE
nodes connected to A-PE3, A-PE4, and A-PE5 can communicate at Layer 2 or Layer 3
with eachother without having to traverse the core nodes.  This is one
fundamental difference between EVPN-CGW and EVPN-HE. Traffic destined to another
subnet, such as the 10.0.0.2 address is routed through the CGW core gateway. 

Also in this example CE4 is an example of a multi-homed CE node, utilizing a LAG
across A-PE4/A-PE3. This multi-homed connection can be configured in an
all-active, single-active, or port-active configuration.  

![](http://xrdocs.io/design/images/asn-metro/cst-5-evpn-cgw.png)

_Figure 31: Hierarchical Services EVPN Centralized GW_ 

### EVPN Head-End for L3 Services 
CST 5.0 also introduces Cisco's EVPN Head-End solution for hierarchical
services. EVPN Head-End is similar to the existing Hierarchical PWHE services,
but allows the use of native EVPN-VPWS between the access PE node and
centralized PE node. This simplifies deployments by allowing providers to use
the fully dynamic EVPN control plane for signaling, including the ability to
signal active/backup signaling between access PE and core PE nodes. In CST 5.0
EVPN-HE is supported for L3 service termination, with the L3 gateway residing on
either a PWHE P2P interface or BVI interface. The L3 GW can reside in the global 
routing table or within a VRF.    

In CST 5.0 EVPN-HE for L3 services is supported on the ASR 9000 platform.  

The figure below shows a typical EVPN Head-End deployment. A-PE3 is configured
as an EVPN-VPWS endpoint, with PE1 and PE2 configured with the same EVPN-VPWS
EVI, acting as All-Active or Single-Active gateways. PE1 and PE2 are configured
with the same 10.1.0.1/24 address on the terminating L3 interface, providing a
redundant gateway for the CE device with address 10.1.0.2/24. While not shown in
this figure, the CE device could also be multi-homed to two separate A-PE nodes in 
a all-active, single-active, or port-active configuration.       

![](http://xrdocs.io/design/images/asn-metro/cst-5-evpn-he.png)

_Figure 32: Hierarchical Services EVPN Centralized GW_ 

    
# The Agile Metro Design - Summary

The Agile Metro brings huge simplification at the Transport as
well as at the Services layers of a Service Provider network.
Simplification is a key factor for real Software Defined Networking
(SDN). Cisco continuously improves Service Provider network designs to
satisfy market needs for scalability and flexibility.

From a very well established and robust Unified MPLS design, Cisco has
embarked on a journey toward transport simplification and
programmability, which started with the Transport Control Plane
unification in Evolved Programmable Network 5.0 (EPN5.0). The Cisco
Agile Metro provides another huge leap forward in simplification and
programmability adding Services Control Plane unification and
centralized path computation.

![](http://xrdocs.io/design/images/asn-metro/cst-overview.png)

_Figure 51: Agile Metro – Evolution_

The transport layer requires only IGP protocols with Segment Routing
extensions for Intra and Inter Domain forwarding. Fast recovery for node
and link failures leverages Fast Re-Route (FRR) by Topology Independent
Loop Free Alternate (TI-LFA), which is a built-in function of Segment
Routing. End to End LSPs are built using Traffic Engineering by Segment
Routing, which does not require additional signaling protocols. Instead
it solely relies on SDN controllers, thus increasing overall network
scalability. The controller layer is based on standard industry
protocols like BGP-LS, PCEP, BGP-SR-TE, etc., for path computation and
NETCONF/YANG for service provisioning, thus providing a on open
standards based solution.

For all those reasons, the Cisco Agile Metro design really brings an
exciting evolution in Service Provider Networking.

