---
title: How to restore IP traffic over optical
date: '2024-09-17 17:14 +0300'
author: Ori Gerstel
excerpt: Solutions for restoring IP traffic over an optical system
tags:
  - iosxr
  - Optical
  - RON
published: false
---

{% include toc %}

<br>

# Protection IP Traffic Against Fiber Cuts

![image](https://github.com/user-attachments/assets/c4a7b5d5-d62b-4b59-8779-848ecd47d5b9)

## 1. Scope

Fiber cuts are a common cause of network outages. If you consider the huge amount of traffic that can be carried on a single fiber using modern optical line systems – in the order of 25-50Tb/s – these failures can cause significant service impact. Therefore, the design of the network must take these outages into account – despite the significant cost this adds to the network. While in some parts of the world fiber cuts are rare enough to justify designing the network against a single fiber cut, in densely populated developing countries, with a high amount of construction projects, fiber cuts are quite common, forcing the network designer to design the network against 2 or even 3 simultaneous fiber cuts.

In this document we focus on different solutions to protect IP traffic from fiber cuts. Some of these solutions use optical switching technology and restore traffic in the optical domain. Other solutions use the built-in protection capability of the IP layer to restore the traffic. Finally, some solutions leverage both the optical layer and IP layer to optimally restore the traffic.

## 2. Traffic protection technologies

The following options for protecting IP traffic against fiber cuts are the most common ones in SP networks. 

### 2.1 IP protection/restoration

The IP network has inherent traffic protection capabilities thanks to fast convergence of its routing protocol. For high priority services, additional mechanisms exist – even fast end-to-end 1:1 protection for some segments routing tunnels. In addition to mechanisms that apply to all traffic types, the IP layer can distinguish between high priority traffic and best-effort traffic and favor the former, in case there is not enough capacity to protect everything. 

This is, by far, the simplest and most flexible solution from an operational perspective since it only involves functionality that is needed anyway, while all other schemes below involve the optical layer, implying additional provisioning and more complex multilayer behavior.

### 2.2 Dedicated optical protection (1+1)

This is an optical mechanism for protecting an optical connection by duplicating the data carried over it at the source of the wavelength, sending the second copy over a different path, and selecting the best copy of the data at the destination, before the receiver. This is a very fast mechanism, but it requires dedicated hardware per wavelength (called Photonic Switch Module) and is therefore complex and costly. Both working and protection paths and wavelength are static and cannot change if failure conditions require it. 

From the IP layer perspective, when such protection kicks in, IP links between routers go down and up – in some cases without triggering any IP reconvergence.
This scheme is often coupled with optical restoration, and then it is referred to as “1+1+R”. For purposes of the analysis below, both schemes can be treated independently – each one with its distinct advantages and disadvantages.

### 2.3 Optical restoration

A mechanism that utilizes the wavelength switching mechanism that exists in modern high-end DWDM networks. Upon failure of a fiber, the control plane of the optical layer kicks in (typically, such solutions have been implemented before the days of SDN control) to figure out all impacted optical connections and to dynamically find alternate paths for them around the failure. In some cases, this implies changing the wavelength of the connection, which can take tens of seconds. Therefore, this is not considered a fast mechanism. Indeed, there is no need for it to be fast – all it needs to do is to get the IP layer back to its full capacity after a fiber cut, but before the next fiber cut occurs.
Optical restoration is typically based on the vendor control plane (e.g. GMPLS) and has never evolved to support multivendor use cases. Therefore the solution is limited to a closed single vendor line system.

From the IP layer perspective, IP links between routers go down and up, but the process takes a long time and therefore the IP layer will typically reconverge before the optical connection is restored, and then reconverge again once the optical connection is restored.

### 2.4 Multilayer restoration (MLR)

A more advanced restoration mechanism that considers both the IP layer and the optical layer. Since it involves both routers and optical gear – often from different vendors – the solution is based on the modern hierarchical SDN control architecture, which involves optical and IP controllers to control the gear and a hierarchical controller (HCO) to coordinate between the IP and optical controllers.

The solution works in a similar way to optical restoration – dynamically finding alternative paths for failed optical connections leveraging optical switching – but it has an important additional flexibility lacking in optical restoration: it can change the capacity of optical connections and trigger a change in the IP layer to take into account the reduced capacity and avoid traffic loss. This flexibility is important because the restored optical path is often much longer than the working path and the modulation format of the signal must be changed to a more robust one to allow the connection to work – trading off reach for capacity.

MLR has another advantage, which comes into play when reverting back to normal, after the fiber cut has been fixed: it can reroute the connection without any traffic loss. This is impossible with optical restoration, since any change of the optical path means that an IP link goes down and traffic is lost. The way MLR achieves this is by coordinating the process with the IP layer, first moving traffic away from the IP links, and only then switching the optical path. 

## 3. Which solution should be used for my network?

The optimal choice of a traffic protection solution highly depends on your network: is it an optical mesh network or a bunch disparate point-to-point links and rings? Is it using traditional closed DWDM systems or transponders integrated into routers? (IPoDWDM or RON – click here for details.) The choice of solution also depends on your service availability considerations: are you worried about a single fiber cut, or are you prepared to invest to protect your network against multiple simultaneous cuts (or maintenance activities)?

In this section we analyze the different options in light of the different network architecture and failure profile you are trying to protect against.

### 3.1 IP protection/restoration

IP protection is always needed to deal with IP layer failures or maintenance activities. Such failures cannot be protected against by the optical layer. When the IP layer is sized to have sufficient spare capacity to deal with IP failures (most notably a router outage), it can already deal with a single fiber cut quite well (a central router carries more capacity than each of the fibers connecting it to the rest of the network). Therefore, most network planners tend to be satisfied with IP protection if they are not concerned with multiple simultaneous failures. In fact, even if a couple of simultaneous failures are plausible, a careful simulation of the likely failure scenarios and the resulting behavior of the IP layer may reveal that the network is still protected without extra capacity or with just a little extra capacity.

It should be noted that IP protection is very efficient, since it protects that actual traffic carried over the link and not the entire capacity of the link. In most networks, most of the time, the actual traffic is much lower than the link capacity and can easily find room on other IP links (which are mostly equally empty).

In addition, the IP layer can be configured to prefer certain types of traffic should congestion occur. This allows planners to size the network for full protection of all traffic under one failure, but selectively protect only premium traffic under multiple failures. Since most traffic in IP networks is typically best-effort traffic, there is a lot of room for premium traffic to be protected while preempting best-effort traffic – allowing such traffic to survive many simultaneous fiber cuts.

### 3.2 Dedicated optical protection (1+1)

Dedicated optical protection is useful for protecting pure optical services that do not enjoy the protection that the IP layer provides – such as high-speed ELINE. This is indeed its main use case. But for IP services this mechanism adds no value – it only adds cost and complexity. While dedicated protection may work well for single fiber cuts, it can’t deal well with all dual failure scenarios since the second failure may affect the static protection path. The speed of protection that this scheme provides, is not an advantage for IP traffic since some of the protection mechanisms in the IP layer are just as fast. 

We do see very limited use cases that justify using this scheme for protecting IP links. 

### 3.3 Optical restoration

Optical restoration is useful for optical mesh networks, where multiple paths exist to deal with multiple failures. Such deployments are typical in the core but sometimes in large metro networks as well.
To allow the control plane to pick any path without many constraints, a highly functional optical switch is required at router locations: directionless switching at a minimum, but full colorless + directionless + contentionless switching provides much better support. Such systems are called CDC-ROADMs – see here for an excellent series of tutorials on the topic). While CDC-ROADMs are deployed in high-end networks, they are expensive and complex, limiting the applicability of optical restoration.

The main drawback of optical restoration is the design complexity it creates in long-haul networks, where a long restoration path cannot have the high capacity that the working path can have. The network designer can cope with this limitation in one of three ways:

1. Run the working path at its highest capacity and accept that not all paths will be restored under all failure combinations. In such cases, let the IP layer protect the traffic. This hybrid solution is operationally complex: when only some paths get restored, the optical team is unsure what to make of paths that fail to restore: is the current network state OK for the IP layer or not?
2. Derate working paths based on the feasible capacity of their restoration path. This solution solves the problem of partial restoration of paths, but is very inefficient and costly, since even during normal conditions you pay the price of all possible failures, while in practice each failure combination only affects a subset of these paths. In this case, relative operational simplicity is achieved at a high cost per bit.
3. A way to keep working paths running at high capacity but ensure all of them can be restored is based on inserting regenerators into the network. These are used by the restoration path to extend its reach when needed. This solution has its own drawbacks: first, regens are not cheap, so there’s still an economical penalty to be paid, but worse is the planning nightmare that the solution creates since one needs to place regens in strategic locations so that they can be shared by multiple restoration paths under different failure scenarios. This also has operational repercussions, since the team must make sure on an ongoing basis that the regens placed are still sufficient in light of changes in traffic patterns and traffic growth.

### 3.4 Multilayer restoration

This scheme is applicable in the same network topologies and requires the same optical switching that optical restoration uses, but for RON networks instead of closed DWDM systems. Optical restoration cannot be used in such networks because of the need to coordinate the configuration of the WDM interface in the router and the optical line system – a task that is impractical for the optical control plane due to the inability to achieve multivendor interoperability as I explained above.

The big difference between these two schemes, from a network planning perspective, is that for MLR you don’t need to worry about matching the capacity of the working path to that of the restoration path. You can run the working path at the highest capacity and let the restoration path use the maximum capacity it can under various failure conditions. This avoids the operational or planning nightmare that the first and third design options for optical restoration suffered from. It also avoids the significant cost increase that the second design option suffered from, but it may require some extra IP layer cost to ensure there is sufficient capacity to protect all traffic should the restoration path have reduced capacity.

Finally, MLR lays the foundation many other novel capabilities, such as hitless coordinated maintenance between the layers and adaptive use of capacity in the face of optical degradations. Those will be covered in more detail in a subsequent post. 

## 4. Conclusions 

In this paper we surveyed different options network planners can use to protect IP services over an optical network. The right solution depends on the specific network architecture and conditions. If fiber cuts are rare or there is no requirement to protect all traffic under simultaneous failure conditions (especially best-effort traffic), the lowest cost and simplest solution to operate is to let the IP layer protect the traffic and keep the optical layer simple.

If multiple simultaneous fiber cuts are a big concern, the optical system is a closed one, and the vendor supports optical restoration, then this is a good solution, potentially justifying the cost of CDC-ROADMs and the additional planning and operational complexity. Under the same conditions, if the optical line system is open and WDM interfaces are integrated into routers, then multilayer restoration is the best solution, with some clear advantages over optical restoration. Finally dedicated optical protection is rarely a good solution for protecting IP traffic – it adds cost and complexity and provides no value compared to IP layer traffic protection: protecting whole wavelengths is a lot less efficient than protecting the actual traffic that requires protection, since most of the wavelength capacity is typically unused.
