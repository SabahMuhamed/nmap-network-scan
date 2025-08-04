# nmap-network-scan and packet Capture 
This project document a basic internal network scan using **Nmap** along with packet capture using **Wireshark**. 

## what was done

1.**Identified Local IP Range**
Used system tools (ipconfig) to find the subnet(192.168.1.0/24)<br>
2.**Performed a TCP SYN Scan**
Ran The following Nmap command to discover active hosts and open ports:<br>
'nmap -sS 192.168.1.0/24'<br>
3.**Captured Packets with Wireshark**
Started Wirshark during the scan to analyse traffic patterns.<br>
filters used - 'ip.addr == 192.168.1.X','tcp'<br>
4.**Analysed Open Ports and Services**
Researched which common service run through the discovered ports and evaluated if any open ports could pose a security threat

## FIles Include
-'scan.txt'-Raw Nmap scan results<br>
-'scan-analyse.md'-(optional)-Notes on identified hosts and open ports<br>
-'packet-Captured.pcap'-Wireshark capture file<br>

## Disclaimer
This scan was conducted on a **local/private network** that i have permission to scan.<br>
**Never scan networks you do not own or have authorization to test.**
