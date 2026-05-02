# VLAN-DHCP-Network-Design-
This project demonstrates a computer network design using VLAN and DHCP. VLAN is used to divide the network into smaller groups for better management and security, while DHCP automatically assigns IP addresses to devices. The project is built in Cisco Packet Tracer to understand networking concepts practically.

## Introduction:
## Computer networks are an important part of modern communication systems. Managing a network becomes difficult when many devices are connected. This project focuses on designing a network using VLAN and DHCP. VLAN helps divide a network into smaller groups for better security and management, while DHCP automatically assigns IP addresses to devices. The project is implemented using Cisco Packet Tracer to understand how these technologies work in a real network environment.

## Tool / Software use :
 • Cisco Packet Tracer

 ## Implementation: 
Step 1. Topology Setup
  Connect the following devices in the simulation:
    Layer 2 Switches: Multiple switches (e.g., Cisco 2960) to connect end-user PCs.
    Layer 3 Device: A Layer 3 Switch or Router to act as the gateway and route traffic between VLANs.
    Windows Server: The central DHCP server.
    Connections: Ensure links between switches and the Layer 3 device are configured as Trunks.

Step 2. VLAN Creation & Port Assignment
  Create VLANs on the Layer 2 switches and assign access ports to them.

Step 3. Configure SVIs (Switch Virtual Interfaces) on Layer 3 Device
  On the Layer 3 switch or router, create virtual interfaces for each VLAN. These will serve as the Default Gateway for devices in those VLANs.

Step 4. Configure DHCP Relay (IP Helper Address)
  Since the DHCP server is on a different subnet, the Layer 3 device must forward (relay) DHCP broadcast requests as unicast packets to the server.

Step 5. Windows Server Configuration
  1. On the Windows Server, install and configure the DHCP Role:
  2. Open DHCP Manager.
  Create a Scope for each VLAN:
  Scope 1 (VLAN 10): IP Range 192.168.10.10–192.168.10.100, Subnet 255.255.255.0, Gateway 192.168.10.1.
  Scope 2 (VLAN 20): IP Range 192.168.20.10–192.168.20.100, Subnet 255.255.255.0, Gateway 192.168.20.1.
  Scope 3 (VLAN 30): IP Range 192.168.30.10–192.168.30.100, Subnet 255.255.255.0, Gateway 192.168.30.1.
  3. Activate/Authorize the scopes.

Step 6. Verification
  1. Test connectivity on the client PCs.
  2. Open Command Prompt on a PC in VLAN 10, 20, or 30.
  3. Run:
      ipconfig /release
      ipconfig /renew
      ipconfig /all
  4. Success Criteria: The PC receives an IP address from the correct scope (e.g., a 192.168.10.x address for a PC in VLAN 10) with the correct gateway and DNS.

 ## Output :
 
<img width="1919" height="1010" alt="Image" src="https://github.com/user-attachments/assets/f92dd76f-fc02-40ab-819f-133e7696d144" />
<img width="1919" height="1019" alt="Image" src="https://github.com/user-attachments/assets/d4d8623a-f981-4613-add8-b6b52826da21" />
<img width="1919" height="1018" alt="Image" src="https://github.com/user-attachments/assets/16a4ac7c-1d5d-4acf-b510-b5a410521c64" />
