# Ex. No: 11 – Packet Tracer: Verify IPv4 and IPv6 Addressing
# Date: 25-10-2025
________________________________________<br>
# Objective
To configure, verify, and test dual-stack (IPv4 and IPv6) addressing on a Cisco Packet Tracer network topology.<br>
Tasks:<br>
• Document IPv4 and IPv6 addressing details.<br>
• Test connectivity using ping for both protocols.<br>
• Trace the route of packets to verify end-to-end connectivity.<br>
________________________________________<br>
# Apparatus / Tools Required
• Cisco Packet Tracer<br>
• 3 Routers (R1, R2, R3 – 2911 or equivalent)<br>
• 2 PCs (PC1, PC2)<br>
• Copper straight-through and Serial DCE/DTE cables<br>
________________________________________<br>
# Network Topology Diagram:

<img width="1918" height="1021" alt="image" src="https://github.com/user-attachments/assets/e59baba5-6724-4391-b9f3-4bbe0cfa7060" />

________________________________________<br>
# Addressing Table
Device	Interface	IPv4 Address / Subnet Mask	IPv6 Address / Prefix	Default Gateway<br>
R1	G0/0	10.10.1.97 / 255.255.255.224	2001:db8:1:1::1/64	N/A<br>
R1	S0/0/1	10.10.1.6 / 255.255.255.252	2001:db8:1:2::2/64	N/A<br>
R2	S0/0/0	10.10.1.5 / 255.255.255.252	2001:db8:1:2::1/64	N/A<br>
R2	S0/0/1	10.10.1.9 / 255.255.255.252	2001:db8:1:3::1/64	N/A<br>
R3	G0/0	10.10.1.17 / 255.255.255.240	2001:db8:1:4::1/64	N/A<br>
R3	S0/0/1	10.10.1.10 / 255.255.255.252	2001:db8:1:3::2/64	N/A<br>
PC1	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R1 G0/0<br>
PC2	NIC	(IPv4 auto/DHCP)	(IPv6 auto-config)	R3 G0/0<br>
________________________________________
# Procedure
# Part 1: Verify IPv4 and IPv6 Addressing
1.	On PC1, open Command Prompt → enter:<br>
2.	ipconfig /all<br>
Record IPv4 address, subnet mask, and gateway.<br>
3.	On PC2, repeat the same.<br>
4.	For IPv6 verification:<br>
5.	ipv6config /all<br>
Record IPv6 address, prefix, and default gateway for both PCs.<br>
________________________________________<br>
# Part 2: Test Connectivity Using Ping
1.	From PC1, ping the IPv4 address of PC2.<br>
2.	ping 10.10.1.20<br>
o	Verify success (Reply from 10.10.1.20).<br>
3.	From PC2, ping the IPv6 address of PC1.<br>
4.	ping 2001:db8:1:1::a<br>
o	Verify success for IPv6 reachability.
________________________________________<br>
# Part 3: Discover the Path Using Traceroute
1.	From PC1, trace route to PC2 using IPv4:<br>
2.	tracert 10.10.1.20<br>
Observe the hops across R1 → R2 → R3.<br>
3.	From PC2, trace route to PC1 using IPv6:<br>
4.	tracert 2001:db8:1:4::a<br>
Record IPv6 path hops.<br>
________________________________________<br>
# Commands Used :
Purpose	Command<br>
Check IPv4 details	ipconfig /all<br>
Check IPv6 details	ipv6config /all<br>
Ping test (IPv4/IPv6)	ping <IP><br>
Trace path (IPv4/IPv6)	tracert <IP><br>
________________________________________<br>
# Verification & Testing
• Successful ping replies indicate proper dual-stack connectivity.<br>
• Trace route confirms correct path through routers R1–R2–R3.<br>
________________________________________
# Output:

• ipconfig /all and ipv6config /all output for both PCs.

<img width="1919" height="1079" alt="501538148-901ec34f-8682-45e5-a3f1-2b7909ff1469" src="https://github.com/user-attachments/assets/36288e15-24dd-47ff-8980-ac2501644d63" />
<img width="1895" height="856" alt="501537888-90c00ca1-d559-4390-b6d1-9f821dae9f50" src="https://github.com/user-attachments/assets/d8614dcc-d29f-4e2f-bc7b-553973c36374" />

• Ping results for IPv4 and IPv6.

• Traceroute results showing intermediate hops.

<img width="753" height="420" alt="501536992-c2935432-6708-4b33-bc70-50215ffe3204" src="https://github.com/user-attachments/assets/5e992224-4e22-4822-9b5c-b0f1892a0288" />
<img width="798" height="427" alt="501537108-47f075b5-db00-4d88-91b4-800c1a8c216e" src="https://github.com/user-attachments/assets/9a476be0-19ac-4eef-a3ce-bfa66e2a9756" />

________________________________________
# Result
The dual-stack IPv4 and IPv6 addressing scheme was successfully verified. Both addressing types achieved full connectivity between PC1 and PC2 through multiple routers, confirming correct configuration and routing.

