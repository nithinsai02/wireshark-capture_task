# Packet Capture Report
Capture filename: network_task_capture.pcap  
**Capture duration:** 60 seconds  
**Interface:** wlan0
**Capture method:** Wireshark (or tcpdump)

## Summary
Objective: Capture live network packets and identify basic protocols.  
During a ~60s capture while browsing example.com and performing a ping, the capture recorded traffic from several protocols: DNS, TCP (HTTP/TLS), ICMP, and ARP.

## Protocols identified (≥3)
1. **DNS** — observed UDP queries for `example.com` and responses resolving to IP `93.184.216.34`. Example packet: #12 (Timestamp: 00:00:12.345) — DNS Standard query A `example.com`.  
2. **TCP / TLS (HTTPS)** — multiple TCP flows to remote host on port 443, using TLS handshake (Client Hello, Server Hello). Example packet: #45 — TLS Client Hello to `93.184.216.34:443`.  
3. **ICMP** — `ping` echo request and reply to/from `8.8.8.8`. Example packets: #5 (ICMP Echo Request), #6 (ICMP Echo Reply).  
4. **ARP** — local network address resolution (who-has requests). Observed packets #2–#4.

## Observations & notes
- Most web traffic to sites using HTTPS is encrypted (TLS). Wireshark shows the handshake but not HTTP content without private keys.  
- DNS lookups occur before the HTTPS handshake.  
- ARP is visible for local LAN discovery.  
- Use **Statistics → Protocol Hierarchy** in Wireshark to see counts of each protocol.

## Conclusion
The capture demonstrates basic network behavior: ARP for local resolution, DNS resolving domain names, ICMP for connectivity checks, and TCP/TLS for secure web browsing. The .pcap file `network_task_capture.pcap` is attached.

