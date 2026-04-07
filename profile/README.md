# Firestation-Gateway

Achtung: Sowohl das Gateway als auch das Webfrontend sind noch in der Entwicklungsphase!


# Installation auf RaspberryPi

## Voraussetzungen

 - RaspberryPi Version 2 oder neuer
 - SD-Karte (für das Betriebssystem)
 - Internetverbindung
 - PC/Laptop zum Einloggen auf dem System

Auf dem RaspberryPi (SD-Karte) muss bereits ein Betriebssystem installiert sein. Siehe z.B.: [Raspberry Pi Imager](https://www.raspberrypi.com/software/).

Es wird empfohlen eine minimale Version ohne Desktop zu installieren.

(Betriebssystem auswählen -> Raspberry Pi OS (other) -> Raspberry Pi OS Lite)

## Installation Firestation-Gateway

Für die einfache Installation steht eine Skript zur Verfügung. Dieses installiert das Firestation-Gateway auf dem System und wahlweise ein Webfrontend. Das Webfrontend kann unter https://IP-Adresse-RaspberryPi:8080 erreicht werden (**Achtung**: es wird ein selbst signiertes Zertifikat genutzt, welches auf den meisten Browsern eine Warnung hervorruft)


Zugriff über SSH (Terminal/PowerShell):

 - `ssh benutzername@hostname.local` (benutzername und hostname durch die gewählten Namen ersetzen, z.B. pi und raspberrypi)
 - Alternativ die IP-Adresse des Pi nutzen, falls `hostname.local` nicht funktioniert.

Nach erfolgreichem Login, muss lediglich das folgende Kommando ausgeführt werden.

    sudo -E bash -c "$(curl -fsSL https://raw.githubusercontent.com/firestation-gateway/scripts/main/installFSG.sh)"

Das Skript installiert unter /opt/firestation-gateway eine Python-venv und darin das Firestation-Gateway. Das optionale Webfrontend wird ebenfalls unterhalb dieses Verzeichnisses installiert (/opt/firestation-gateway/web).

*Dieses Skript kann auch genutzt werden, um eine bestehende Installation zu aktualisieren.*