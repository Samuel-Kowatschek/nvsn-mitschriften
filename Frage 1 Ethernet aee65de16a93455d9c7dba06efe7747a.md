# Frage 1: Ethernet

### Begriff Ethernet

Ethernet ist eine Technologie, die verkabelte lokale Netzwerke (LANs) verbindet und es den Geräten ermöglicht miteinander zu kommunizieren.

Darüber hinaus ist Ethernet ein Protokoll(familie), dass die Prozesse steuert, wie die Daten über LAN übertragen werden.

Standard: IEEE 802.3

**Ethernet-Frame:**

- OSI-Schicht 2
- Sender und Empfänger als MAC-Adresse (6 Byte - 3 für Hersteller und 3 eindeutig für Hersteller,  sollten eindeutig sein)

### Kabeltypen und Topologien

**Twisted-Pair-Kabel (Standard, RJ45):** 

- vier Adernpaare, senden/empfangen
- Shielded / Unshielded, S/STP(Screen Shielded Twiested Pair)
- schlecht für lange Distanzen
- billig
- einfach zu verlegen
- robust
- relativ einfach abhörbar (schwerer bei shielded) wegen Magnetfeld
- Störung

**Koaxkabel (BMC Stecker):** 

- Assymmetrisches Kabel
- leitende Schichten (Hülle)
- lange Strecken
- geringere Bandbreite
- wird nicht mehr verwendet

**Glasfaser:** 

- Sehr lange Strecken
- Extrem hohe Bandbreite
- Abhörsicher
- Wenig robust
- Teurer
- Spezielle Gerät um Kabel zu verbinden oder Stecker anzuschließen

(**Crossoverkabel:** Es können zwei Computer direkt miteinander verbunden werden)

(**Patchkabel/LAN-Kabel**: Verbindet einen Computer mit dem Netzwerkverteiler (Hub, Switch oder Router))

Kein CAT-Varianten

**Punkt-zu-Punkt-Topologie:** Zwei Geräte werden direkt miteinander verbunden

**Stern-Topologie:** Alle Geräte sind direkt mit einem zentralen Gerät(z.B. Switch) verbunden

**Ring:** Jeweils zwei Geräte sind miteinander direkt verbunden

**Bus:** Alle Geräte sind mit dem selben Bus(Übertragungsmedium) verbunden

 

### CSMA/CD vs CSMA/CA + Anwendung

**Carrier Sense Multiple Access/Collision Detection** (**CSMA/CD**)

Ist ein asynchrones Medienzugriffsverfahren das den Zugriff mehrerer Stationen auf ein gemeinsames Übertragungsmedium regelt. Es muss gleichzeitig gesendet und empfangen werden können. 

Anwendung: **ETHERNET**, PowerLAN → Netzwerk über Stromleitung

- Leitung frei → schicken
- Kollision: JAM-Signal → nicht mehr senden → Medium wieder frei
- Zufällige Zeit in ms warten, dann wieder senden

**Carrier Sense Multiple Access/Collision Avoidance** (**CSMA/CA**)

Bezeichnet ein Prinzip für die Kollisionsvermeidung bei Zugriff mehrerer Netzwerkstationen auf denselben Übertragungskanal

Anwendung: **WLAN**

- Überprüft ob gerade was gesendet wird, sendet Anfrage
- Plan, wann wer senden darf
- Kollision werden im Vorraus verhindert

### Kollisions- und Broadcastdomäne

Die Kollisionsdomäne umfasst alle Geräte, die sich in Schicht 1 des OSI-Modells ein Übertragungsmedium teilen. Wenn mehrere Geräte gleichzeitig auf dem selben Medium sendet, kommt es zu Kollisionen und die Nachrichten gehen verloren. Es sollten alle Geräte, die gleiche Chance haben, das Medium zu verwenden

Wo können Kollision stattfinden → bis zum nächsten Switch (Hub nicht)

Eine Broadcastdomäne ist ein logischer Verbund verschiedener Geräte in einem lokalen Netzwerk, die alle von einem Broadcast erreicht werden. Geräte in Schicht 2 des OSI-Modells können mit Hubs oder Bridges verbunden sein, sind aber alle noch Teil der gleichen Broadcastdomäne. Eine Unterteilung in VLANs trennt die Broadcastdomäne

Endet beim nächsten Router

### Endgeräte im Ethernet-Frame

Im Header eines Ethernet-Frame werden die MAC-Adressen des  Senders und des Empfängers eingetragen

### ARP

- MAC-Adresse im LAN unbekannt
- Broadcast, welche MAC-Adresse hat diese IP-Adresse
- ARP Poisoning / Spoofing