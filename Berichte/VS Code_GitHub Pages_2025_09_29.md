 # ITSE VS Code, Github Pages
 ### Petra Bernroitner, 4AHITS, 29.09.2025

 ---

## VM auf Bridged Modus stellen
 Bridged:
 1. sich zum Admin machen
 2. VM Einstellungen:
 Network Adapters -> Bridged -> Configure Adapters -> nur das Realtek PCIe GbE Family Controller wählen (Labornetz)
 das Intel(R) Ethernet Connection weg, das ist das HTL Netz.

---

## Visual Studios auf Kali installieren

in der Kommandozeile alle folgenden Befehle eingeben:

```sh
$ wget -O ~/Downloads/code.deb "https://update.code.visualstudio.com/latest/linux-deb-x64/stable"
$ sudo dpkg -i ~/Downloads/code.deb
$ sudo apt -f install
```
um VS Code auszuführen:

Im Terminal ```Code``` eingeben

vs code:

preferences -> settings -> Auto Save ->  "after Delay"



Klonen:
```sh
git clone https://github.com/bernroitnerp4AHITS_ITSE_Bernroitner.Petra
```

Weiter:
Im VS Code das Terminal öffnen und im Git prüfen, ob das richtige Repository offen ist ```ls``` oder ```git status```, dann folgendes eingeben:
```sh
git add .
```


Test ob es im Kali nagezeigt wird:

