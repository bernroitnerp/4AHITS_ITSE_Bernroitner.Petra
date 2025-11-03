Petra Bernroitner, 4AHITS, 03.11.2025

# Host Discovery

``nmap`` ist ein Tool zum network scanning. 

In einer ersten Phase (host discovery, ping scan oder ping sweep) ermittelt nmap alle aktiven Hosts.

**Aufgaben:**

## Recherchiere zur grundlegenden Anwendung von nmap für einen sogenannten ping scan.

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
<img width="633" height="309" alt="image" src="https://github.com/user-attachments/assets/ca6a3db4-f87c-4596-ae38-90af8bd93a76" />

das ``` GET /HTTP/1.0``` ist hier die Header-Request-Line. Die sagt, welche HTTP-Protokoll Version verwendet wird.
  
- Verwende nc (netcat)
   - Hinweis: der notwendige http request header kann am besten mit Hilfe eines Shell here-documents beschrieben werden.
 <img width="629" height="264" alt="image" src="https://github.com/user-attachments/assets/53792d6b-3cfd-4b5a-aa4b-34aa6a970ea3" />

- Verwende curl
<img width="310" height="124" alt="image" src="https://github.com/user-attachments/assets/b15e6323-0d40-4648-a914-ceb1d5499cea" />

das ``` -I ``` zeigt den  HTTP HEAD-Request

```Curl -I``` ist der einfachste Weg, um Webserver Informationen anzuzeigen.


3. Erstelle ein port probing cheat sheet für alle 3 Tools

   ### Cheat Sheet

**Telnet**
```
telnet METASPLOITABLE_IP 80
```

Dann:
```
GET / HTTP/1.0
```
-> Server-Header ist sichtbar


**Netcat (nc)**
```
nc METASPLOITABLE_IP 80
```

Dann manuell:
```
GET / HTTP/1.0
```
-> Server-Header erscheint 

**Curl**
```
curl -I http://METASPLOITABLE_IP
```

Zeigt wegen ```-I ``` direkt die Header, z. B.:
```
Server: Apache/2.2.8 (Ubuntu)
```
-> Einfachste & "zuverlässigste" Methode (laut ChatGPT)

--- 


## Übung (netcat port scan)
Ermittle mit Hilfe von netcat welche Ports zwischen 1 und 30 in der Metasploitable VM geöffnet sind 
– Hinweis: dies geht in einer einzigen Kommandozeile. Recherchiere welche Dienste sich dort befinden.

Randnotitz: netcat wird auch gerne als das swiss army knife of network tools bezeichnet.
