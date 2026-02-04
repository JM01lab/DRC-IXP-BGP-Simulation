# DRC-IXP-BGP-Simulation

## Project Overview

This project simulates a powerful national-scale network infrastructure for the Democratic Republic of Congo (DRC) using Cisco Packet Tracer. The core objective was to design and implement an Internet Exchange Point (IXP) to localize domestic traffic and provide a structured gateway to the Global Internet.

## Network Architecture

The topology is divided into three functional layers:

   •	Peering Hub (AS 65000): The central IXP_DRC router interconnecting all local Internet Service Providers (ISPs).

   •	Upstream & Global Connectivity: 

     o	AS 37000 (ARPTC): National regulator acting as the primary gateway.

     o	AS 6000 (Global Internet): Simulation of the worldwide web (reaching 8.8.8.8).

   •	Local ISPs (Tier 3): Four major providers (Orange, Vodacom, Airtel, Africell) managing their own client subnets (192.168.x.0/24).
Technical Implementation Details

   •	Dynamic Routing: Full BGP peering established between all 6 Autonomous Systems.

   •	Route Propagation: Implemented default-originate and static route redistribution to ensure global reachability for all internal PCs.

   •	Loop Prevention: Resolved BGP routing loops between the national gateway and global transit points using static route optimization and next-hop-self attributes.

   •	Network Services: Integrated shared services including:

     o	Public DNS: 72.163.4.10

     o	Web Hosting: www.odc.cd (72.163.4.185)

Verification & Proof of Concept

   •	End-to-End Connectivity: Successfully pinged 8.8.8.8 from all ISP client PCs.
	 
   •	Web Access: Verified HTTP access to www.odc.cd across different Autonomous Systems.
	 
   •	BGP Stability: show ip bgp summary confirms all neighbors are in the Established state with active prefix exchange.
