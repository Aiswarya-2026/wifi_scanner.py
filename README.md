Wi-Fi Network Scanner & Signal Logger

A Python tool that scans nearby Wi-Fi networks and logs SSID, signal strength, channel, and security type over time — useful for spotting channel congestion and comparing signal quality across networks.

Why I built this

I'm interested in wireless networking (access points, controllers, and how Wi-Fi networks are managed and optimized), so I built a small tool to get hands-on with the core concepts: SSIDs, BSSIDs, channels, RSSI/signal strength, and 802.11 security types.

Features
Scans nearby Wi-Fi networks (Windows via netsh, Linux via iwlist)
Logs SSID, BSSID, signal strength, channel, and security type
Appends results with a timestamp to wifi_scan_log.csv for tracking changes over time
Prints a quick readable summary to the console
How to run
bash
python wifi_scanner.py

On Linux, iwlist requires sudo, so you may need:

bash
sudo python wifi_scanner.py
Sample output

Replace this section with a real scan result once you've run the script on your machine. Easiest way: run it, copy 3-5 lines from the console output or from wifi_scan_log.csv, and paste them here inside a code block.

Scanning Wi-Fi networks on Windows...

Found 6 network(s):

SSID                     Signal    Channel   Security
------------------------------------------------------------
[paste your real scan results here]
What I learned

Building this helped me understand, hands-on, how Wi-Fi networks are actually identified and compared in practice — SSIDs vs BSSIDs, how signal strength (RSSI) relates to connection quality, how channels can overlap and cause congestion, and how security/encryption type shows up at the network-discovery level before any connection is made. It also gave me practice parsing unstructured command-line output into clean, structured data.

Known limitations
Tested on Windows (netsh) and Linux (iwlist); no macOS support yet
Signal strength format differs slightly between OS scan tools, so values may not be directly comparable across platforms
Requires the Wi-Fi adapter to support scanning while connected (most modern adapters do)
Roadmap / next steps
 Plot signal strength over time with matplotlib
 Flag channel congestion (multiple strong networks on the same channel)
 Export a simple HTML report
 Add a --interval flag to scan repeatedly and track signal drift
