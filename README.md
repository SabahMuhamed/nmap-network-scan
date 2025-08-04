# nmap-network-scan and packet Capture 
This project document a basic internal network scan using **Nmap** along with packet capture using **Wireshark**. 

## what was done

1.**Identified Local IP Range**
Used system tools (ipconfig) to find the subnet(192.168.1.0/24)
2.**Performed a TCP SYN Scan**
Ran The following Nmao commandto discover active hosts and open ports:
'nmap -sS 192.168.1.0/24'
3.**Captured Packets with Wireshark**
Started Wirshark during the scan to analyse traffic patterns.
filters used - 'ip.addr == 192.168.1.X','tcp'
4.**Analysed Open Ports and Services**
Researched which common service run through the discovered ports and evaluated if any open ports could pose a security threat

## FIles Include
-'scan.txt'-Raw Nmap scan results
-'scan-analyse.md'-(optional)-Notes on identified hosts and open ports
-'packet-Captured.pcap'-Wireshark capture file

##Disclaimer
This scan was conducted on a **local/private network** that i have permission to scan.
**Never scan networks you do not own or have authorization to test.**
