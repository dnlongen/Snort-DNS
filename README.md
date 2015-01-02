Snort-DNS
=========

Snort rules to detect local malware, phishing, and adult content by inspecting DNS responses from OpenDNS

I use OpenDNS Family Shield as my domain name service. It's an effective way of minimizing one popular avenue of infection and phishing attacks. DNS is bit like a phone book: it translates human-friendly website names into computer-friendly network addresses. OpenDNS takes advantage of this to provide a layer of protection: for most websites, it will tell my computer the real network address, but for domains known to host malware, phishing attacks, or adult content, OpenDNS instead gives the network address of a page with a warning message.

This project takes advantage of this fact. The local.rules file contains a set of Snort rules that identify DNS responses (packets from udp port 53 destined for a device on the local network), then inspects the payload. If the payload includes one of OpenDNS' blocked content landing pages, the rule will fire an alert.

For more details on how this works, and suggested improvements, see http://dnlongen.blogspot.com/2015/01/detecting-malware-through-dns-queries.html
