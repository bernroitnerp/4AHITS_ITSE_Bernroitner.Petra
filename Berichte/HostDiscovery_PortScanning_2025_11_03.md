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


## Ermittle alle aktiven Hosts im Subnetz des Labor-Netzwerks mit nmap.

![Bild.jpg](/img/HostDiscovery.png)

--- 

# Port Scanning

## Übung (port probing)

Beim port probing möchte man herausfinden ob auf einem gewissen port ein Dienst läuft, welcher Dienst dies ist und (wenn möglich) mehr Details wie z.B. Versionsnummern. 

```telnet```, ```nc``` (netcat) und ```curl``` sind einfache Tools die zum port probing verwendet werden können.


1. Verwende telnet um festzustellen ob ein ssh Server auf Metasploitable läuft

   <img width="335" height="164" alt="image" src="https://github.com/user-attachments/assets/37408c72-58f6-486f-8947-d45929205fed" />

   Die Fehlermeldung ```Protocol mismatch``` ist kein wirkliches Problem. Der Port ist offen!
   Der Server läuft, jedoch versteht das Protokol Telnet ssh nicht.

2. Finde Bezeichnung und die Versionsnummer des Web Servers auf Metasploitable heraus. Auf 3 Arten:
- Verwende telnet
- Verwende nc (netcat)
- Hinweis: der notwendige http request header kann am besten mit Hilfe eines Shell here-documents beschrieben werden.
- Verwende curl
3. Erstelle ein port probing cheat sheet für alle 3 Tools

  
