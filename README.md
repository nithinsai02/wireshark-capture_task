# wireshark-capture_task

## What I did
- Captured network traffic for 60 seconds using Wireshark on interface wlan0.
- Generated traffic by browsing https://example.com and running `ping 8.8.8.8`.
- Exported the capture as `network_task_capture.pcap`.
- Wrote a short report `report.md` summarizing protocols identified and key packets.

## Files
- `network_task_capture.pcap` — packet capture file.
- `report.md` — short report with protocol summary and packet details.
- `screenshots/` — optional: screenshots of Wireshark views (protocol hierarchy, follow TCP stream).

## How to reproduce
1. Install Wireshark.
2. Start capture on active interface for ~60s.
3. Generate traffic (browse, ping).
4. Stop capture and save as `.pcap`.
