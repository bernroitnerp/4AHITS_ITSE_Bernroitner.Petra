Petra Bernroitner, 4AHITS, 03.11.2025

# Host Discovery

``nmap`` ist ein Tool zum network scanning. 

In einer ersten Phase (host discovery, ping scan oder ping sweep) ermittelt nmap alle aktiven Hosts.

**Aufgaben:**

## Recherchiere zur grundlegenden Anwendung von nmap für einen sogenannten ping scan (host discovery).

Ein Ping-Scan in nmap heißt heutzutage -sn. Er fragt nur ab, welche Hosts online sind (Host Discovery), ohne anschließend Ports zu scannen. 
nmap benutzt diese Methoden: ICMP, TCP, UDP, ARP u. a.

die genaue Kombination hängt von Rechten (root/Administrator oder nicht) und vom Netzwerktyp (lokales Ethernet vs. entferntes Subnetz) ab.

Beispiel:  
```
nmap -sn 192.168.1.0/24
```

**Hinweise:**

- nmap benötigt als Argument den IP Adressbereich des Subnet in Präfix Notation (z.B.: 192.168.178.0/24)
- Mit der Option -sn führt nmap nur den ping scan durch (ansonsten wird automtisch auch die nächste, länger dauernde, Phase des scans ausgeführt)
- 

## Ermittle alle aktiven Hosts im Subnetz des Labor-Netzwerks mit nmap.
