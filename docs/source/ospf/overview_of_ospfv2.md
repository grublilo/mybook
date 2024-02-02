# Overview of OSPFv2


```{admonition} OSPFv2 Review
OSPF is a link-state interior gateway protocol(IGP) used within an autonomous system(AS)
```
:::{figure-md}
![ospf](img/01.png){.bg-primary .mb-1 width=200px}

This is a caption in **Markdown**
:::


OSPF is an interior gateway protocol (IGP) based on the concept of a link-state database (LSDB). As such, each OSPF-speaking router in the network attempts to form an adjacency with each neighboring OSPF router. When these adjacencies are in place, each router generates and floods link-state advertisements (LSAs) into the network in a reliable manner.
The LSAs are placed into the LSDB on each router where the shortest-path-first (SPF) algorithm is run to find the best path to each end node in the network.
OSPF routers send out Hello packets to form and maintain adjacencies with their neighbors.
OSPF uses IP protocol number 89 and the All OSPF Routers multicast address of **224.0.0.5** to flood LSAs. OSPF routers forward all LSAs through all OSPFconfigured interfaces except the one on which an LSA was received.
The LSAs are then installed into the OSPF database, which forms the topology map of the network. Finally, the SPF algorithm is calculated to determine the shortest path to each destination subnet.