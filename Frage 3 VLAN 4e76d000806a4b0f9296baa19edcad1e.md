# Frage 3: VLAN

VLAN fähiger Switch oder Router

**Statisch / Portbasiert**: Je nach Port unterschiedliches VLAN

**Dynamisch / Tagged**: Tag im Ethernet-Frame

Trunk: bestimmter Port, an dem Tag-Verkehr statt findet

Layer 3 Switch: Switch, der auch als Router funktioniert

[https://nvs.htl-leonding.ac.at/script/n_vlan.html](https://nvs.htl-leonding.ac.at/script/n_vlan.html)

IEEE 802.1Q

ICMP: Internet Control Message Protocol

- Ping
- Basiert auf IP-Adressen (Layer-3)
- Fehleranalyse
- Statuscode

ARP: Auflösung von IP-Adresse zu MAC-Adresse

- Ping auf Layer 2 als Broadcast
- definiert Broadcast-Domäne
    - nur innerhalb eines VLANs möglich

Vorteile

- Flexibilität: Zuordnung von Endgeräten zu Netzwerksegmenten, unabhängig vom Standort der Basisstation.
- Performance: Priorisierung
- Sicherheit: Trennung des Datenverkehrs → Angriff nicht auf gesamtes Netzwerk