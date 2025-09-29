 # ITSE VS Code, Github Pages
 ### Petra Bernroitner, 4AHITS, 29.09.2025

 ---

# VM auf Bridged Modus stellen
 Bridged:
 Admin machen
 VM Einstellungen
 Network Adapters -> Bridged -> Configure Adapters
 -> nur das Realtek PCIe GbE Family Controller wählen (Labornetz)
 das Intel(R) Ethernet Connection ist das HTL Netz

---

# Visual Studios auf Kali installieren

in der Kommandozeile alle folgenden Befehle eingeben:

```sh
$ sudo apt update

$ sudo apt install software-properties-common apt-transport-https

$ wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg

$ sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/

$ sudo sh -c 'echo "deb [arch=amd64 signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode/ stable main" > /etc/apt/sources.list.d/vscode.list'

$ sudo apt update

$ sudo apt install code
```
