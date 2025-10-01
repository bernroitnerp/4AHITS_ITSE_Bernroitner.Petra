 # ITSE VS Code, Github Pages
 ### Petra Bernroitner, 4AHITS, 29.09.2025

 ---
# Aufgabenstellungen:
1. Aktiviere GitHub Pages und kontrolliere ob html Files aus den Markdown Files generiert werden.
2. Installiere Kali und Metasploitable (falls noch nicht geschehen)
3. Stelle beide VMs auf Bridged ins Labor-Netz
4. Installiere Visual Studio Code auf Kali Linux
5. Klone das Github Projekt in Kali, nimm mit VS Code eine Änderung im Markdown vor, führe add, commit und push durch und prüfe ob die Änderungen in der generierten html Seite ankommen (kurze Wartezeit)
6. Nimm nun über die GitHub Oberfläche eine Änderung vor und prüfe ob diese per git pull in den Klon auf Kali übernommen werden.


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


in VS code:

preferences -> settings -> Auto Save ->  "after Delay"



### GitHub Projekt klonen:
```sh
git clone https://github.com/bernroitnerp4AHITS_ITSE_Bernroitner.Petra
```

Weiter:
Im VS Code das Terminal öffnen und im Git prüfen, ob das richtige Repository offen ist ```ls``` oder ```git status```, dann folgendes eingeben:
```sh
git add .
git commit -m "[Nachtricht]"
git push
```

### Test: GitHub -> Kali 

Test ob es im Kali angezeigt wird:
```sh
git pull
```
