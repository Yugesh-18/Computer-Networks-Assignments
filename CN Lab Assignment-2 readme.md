Name: N.Yugesh
Roll Number: 2301010199
Section - C (BTech CSE Core)


Packet Flow Visualization Using Simulation Mode
Overview

This experiment uses Cisco Packet Tracer’s Simulation Mode to visualize how packets travel in a network. It demonstrates ARP resolution, ICMP communication (ping), and how a switch learns MAC addresses dynamically.

Requirements
Software
Cisco Packet Tracer (any recent version)
Network Components
1 × Switch
3 × PCs
Copper Straight-Through Cables
IP Configuration

Assign IP addresses in the same subnet:

Device	IP Address	Subnet Mask
PC1	192.168.20.1	255.255.255.0
PC2	192.168.20.2	255.255.255.0
PC3	192.168.20.3	255.255.255.0
Procedure
Step 1: Build the Network
Open Packet Tracer
Add:
1 switch
3 PCs
Connect each PC to the switch using straight-through cables
Configure IP addresses on all PCs via:
Desktop → IP Configuration
Step 2: Enable Simulation Mode
Switch from Real-Time Mode → Simulation Mode
Keep only relevant protocols visible:
ARP
ICMP
Step 3: First Ping (PC1 → PC2)
Open PC1 → Command Prompt

Run:

ping 192.168.20.2
Observe the Event List and packet movement step-by-step
What to Observe
ARP Request (broadcast)
ARP Reply (unicast)
ICMP Echo Request
ICMP Echo Reply
Step 4: Second Ping (PC1 → PC2)

Run the same ping command again:

ping 192.168.20.2
Observe the packet flow
What to Observe
No ARP request this time
Only ICMP packets
Step 5: MAC Address Table Observation
Click on the switch

Check MAC table via CLI (if supported):

show mac address-table
Alternatively, infer learning from simulation events
Expected Output

1. Event List Behavior
First ping:
ARP Request → ARP Reply → ICMP Request → ICMP Reply
Second ping:
Only ICMP Request and Reply
2. Packet Flow Observations
ARP Request is broadcast to all devices
ARP Reply is unicast back to sender
ICMP packets follow resolved MAC addresses
3. Switch Behavior
Switch learns MAC addresses dynamically
Stores:
Source MAC address
Associated port
4. First vs Second Ping
Feature	First Ping	Second Ping
ARP Involved	Yes	No
ICMP Packets	Yes	Yes
Speed	Slower	Faster
Reason	MAC unknown	MAC cached

