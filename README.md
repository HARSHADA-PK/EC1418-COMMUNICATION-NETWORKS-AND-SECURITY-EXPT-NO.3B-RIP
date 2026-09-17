# EXPT.NO-3 B-IMPLEMENTATION-OF-DISTANCE-VECTOR-ROUTING-PROTOCOL-RIP
# AIM:

To connect computers in multiple networks using Distance Vector Routing Protocol and to verify the connectivity between computers.
# EQUIPMENTS REQUIRED:

<img width="442" height="342" alt="image" src="https://github.com/user-attachments/assets/7a1d1ebd-d7f3-4f63-9178-fdeb530d426e" />


# IP ASSIGNMENT:

<img width="978" height="447" alt="image" src="https://github.com/user-attachments/assets/f2b3a0af-746e-4927-934f-640a08cb7ed3" />




# NETWORK DIAGRAM:

<img width="943" height="465" alt="image" src="https://github.com/user-attachments/assets/bc0940de-3553-4661-bcaf-bf1bc7cee0de" />

# PROCEDURE:

STEP 1: Open a Packet Tracer Software.
STEP 2: Drag two 2900 Switches, two Cisco 1800 Routers, four PC Terminals from tool barand drop it in work area.
STEP 3: Connect all the PC Terminals and Routers through Switches as shown in the networkdiagram using CAT 6 Patch cables.
STEP 4: Configure IP address and Gateway in all PC Terminals.
STEP 5: Configure ROUTER0 and restart ROUTER0.
STEP 6: Configure ROUTER1 and restart ROUTER1.
STEP 7: Verify the connectivity between PC Terminals in different networks using Pingcommand.
After This follow the given procedure
1. Assign IP Addresses to PCs
•	For each PC, go to Desktop > IP Configuration and assign:
o PC0: 192.168.1.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1
o PC1: 192.168.1.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.1.1
o PC2: 192.168.2.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.2.1
o PC3: 192.168.3.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.3.1
o PC4: 192.168.4.2, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1
o PC5: 192.168.4.3, Subnet Mask: 255.255.255.0, Gateway: 192.168.4.1
 
# PROGRAM

Router0 Configuration Steps
Click Router 0 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.1.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.2.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.1.0
Router(config-router)# network 192.168.2.0 Router(config-router)# exit

Router1 Configuration Steps
Click Router 1 and in CLI TYPE THIS Router> enable
Router# configure terminal Router(config)# interface FastEthernet0/0
Router(config-if)# ip address 192.168.3.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit
Router(config)# interface FastEthernet0/1
Router(config-if)# ip address 192.168.4.1 255.255.255.0 Router(config-if)# no shutdown
Router(config-if)# exit Router(config)# router rip Router(config-router)# version 2
Router(config-router)# network 192.168.3.0
Router(config-router)# network 192.168.4.0 Router(config-router)# exit
Steps to Check the Output:
1.	Verify RIP Routing Table on Routers
To check if RIP is working and the routes are learned from the other router, you need to inspect the routing table on each router.
Click Router 0
In the same CLI window type this
Router# show ip route
You should see routes for the networks connected to Router1 (192.168.3.0 and 192.168.4.0) via RIP. The output might look something like this:
 
R 192.168.3.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
R 192.168.4.0 [120/1] via 192.168.2.2, 00:00:00, FastEthernet0/1
For Router1, enter the same command:
Router# show ip route
You should see routes for the networks connected to Router0 (192.168.1.0 and 192.168.2.0) via RIP:
R 192.168.1.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0
R 192.168.2.0 [120/1] via 192.168.2.1, 00:00:00, FastEthernet0/0

2.	Ping from PC to PC
You can also check connectivity between the PCs on different networks to ensure that RIP is correctly routing packets across the routers.
•	Example: Ping from PC0 (192.168.1.2) to PC3 (192.168.3.2):
1.	Click on PC0, go to the Desktop tab.
2.	Open the Command Prompt.
3.	Use the ping command: ping 192.168.3.2
4.	If everything is configured correctly, you should receive replies from PC3.
•	Similarly, you can ping between other PCs (e.g., from PC2 to PC5) to verify network connective
 
# OUTPUT

<img width="987" height="681" alt="image" src="https://github.com/user-attachments/assets/3a794f8c-72a4-4017-be23-c1c2388ab03a" />

<img width="952" height="551" alt="image" src="https://github.com/user-attachments/assets/1daaac16-8002-47f9-9e62-5d7d2a08ad3e" />

# RESULT:

Thus the computers in multiple networks using Distance Vector Routing have been implemented.
