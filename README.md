Network Sniffer
A simple Python-based network packet sniffer that uses the Scapy library to capture and analyze network traffic. This tool extracts and displays detailed information about packets on the network, including IP layer details, Ethernet layer information, and protocol-specific data (TCP, UDP, ICMP).

Features
Captures network packets in real-time.
Extracts information from the IP layer, including source/destination IP addresses, protocol type, TTL, flags, and fragment offset.
Optionally displays Ethernet layer information such as MAC addresses.
Supports detailed analysis of TCP, UDP, and ICMP packets:
TCP: Source and destination ports, sequence/acknowledgment numbers, flags, and payload.
UDP: Source and destination ports, and payload.
ICMP: Type, code, and payload.
Prints all relevant packet information for each captured packet.
Requirements
Python 3.x
Scapy library
You can install Scapy using pip:

bash
Copy code
pip install scapy
How It Works
The script continuously captures packets on the network and processes each packet. Depending on the protocol, the script prints different details:

IP Layer:

Source and destination IP addresses.
Protocol type (TCP, UDP, ICMP, etc.).
Time to Live (TTL).
Flags and fragment offset.
Packet length.
Ethernet Layer (optional):

Source and destination MAC addresses.
Protocol-Specific Information:

TCP: Source port, destination port, sequence and acknowledgment numbers, flags, and payload.
UDP: Source port, destination port, and payload.
ICMP: Type, code, and payload.
If the packet is of an unrecognized protocol, a generic message will be printed.

How to Use
Clone the repository or download the script.

Install the required dependencies:

bash
Copy code
pip install scapy
Run the script:

bash
Copy code
python networksniffer.py
The script will start capturing packets and print out detailed information about each packet in real-time.

Example Output
bash
Copy code
Time: 1642873821.123456, Source IP: 192.168.1.1, Destination IP: 192.168.1.2, Protocol: 6, Length: 60
    TTL: 64, Flags: 2, Fragment Offset: 0
    Source MAC: 00:14:22:01:23:45, Destination MAC: 00:14:22:67:89:AB
    TCP Source Port: 80, Destination Port: 443
    Sequence Number: 123456, Acknowledgment Number: 654321, Flags: S
    Payload: b'GET / HTTP/1.1\r\nHost: example.com\r\n'
Notes
This script works on Linux, MacOS, and Windows (with proper packet capture drivers installed, such as Npcap on Windows).
Make sure to run the script with the necessary permissions (administrator or root access) to capture packets.
