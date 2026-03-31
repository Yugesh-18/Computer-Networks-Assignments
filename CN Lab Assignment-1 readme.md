Basic Network Topologies – Experiment 1
Files Included
File	Description
exp_1.pkt	Cisco Packet Tracer simulation file containing all four topology experiments
exp_1.txt	Ping results and observations for all tasks
exp_1.pdf	Full report with topology screenshots, ping results, and conclusions
readme.md	Instructions on how to open and test the simulation
Requirements

Cisco Packet Tracer Student version 6.2 or later (recommended)
Download from Cisco NetAcad (free account required)

No additional software or hardware required. The simulation runs entirely within Packet Tracer.

How to Open the Simulation

Install and launch Cisco Packet Tracer

Go to File → Open (or press Ctrl + O)

Navigate to the folder containing the submission files

Select exp_1.pkt and click Open


How to Test Each Topology
Task 1 – Star Topology (Switch)

Devices: 1 Switch with 4 PCs


IP Assignment:

PC0 → 192.168.0.1

PC1 → 192.168.0.2

PC2 → 192.168.0.3

PC3 → 192.168.0.4

To test:

Click on PC0 → Desktop → Command Prompt

Run:
ping 192.168.0.2
ping 192.168.0.3
ping 192.168.0.4

Observe that after the first ping (ARP broadcast), subsequent pings are forwarded directly to the destination.

Task 2 – Star Topology (Hub)

Devices: 1 Hub with 4 PCs


IP Assignment:

PC0 → 192.168.0.1

PC1 → 192.168.0.2

PC2 → 192.168.0.3

PC3 → 192.168.0.4

To test:

Click on PC1 → Desktop → Command Prompt

Run:
ping 192.168.0.2
ping 192.168.0.3
ping 192.168.0.4

Switch to Simulation Mode and observe that the hub broadcasts every frame to all connected devices.

Observation: All frames are sent to every port because hubs do not perform intelligent forwarding.

Task 3 – Ring-like Topology (Switch Loop with STP)

Devices: 3 Switches connected in a loop with PCs distributed across them


IP Assignment:

PC0 → 192.168.0.1

PC1 → 192.168.0.2

PC2 → 192.168.0.3

PC3 → 192.168.0.4

PC4 → 192.168.0.5

PC5 → 192.168.0.6

PC6 → 192.168.0.7

PC7 → 192.168.0.8

To test:

Click on PC0 → Desktop → Command Prompt

Run:
ping 192.168.0.5
ping 192.168.0.8

Observe that one redundant link is blocked by STP to prevent loops.

Traffic flows only through the active path selected by STP.

Task 3 extended – Failure Test (Ring Topology)

Setup: Same ring topology as Task 3

To test:

Confirm connectivity by pinging between PCs on different switches

Delete one active inter-switch link to simulate failure

Wait a few seconds for STP to recalculate the topology

Ping again — communication should resume through the alternate path