# Frage 8: TCP/IP Schichtenmodell

![Untitled](Frage%208%20TCP%20IP%20Schichtenmodell%2039b2c539619e48699ef1f78806104f43/Untitled.png)

## OSI-Schichtenmodell

- **Schicht 1 – Bitübertragungsschicht (Physical Layer)**
    
    Diese Schicht stellt mechanische, elektrische und weitere funktionale Hilfsmittel zur Verfügung, um physische Verbindungen zu aktivieren bzw. zu deaktivieren, sie aufrechtzuerhalten und Bits darüber zu übertragen.
    
    Repeater, Hub
    
- **Schicht 2 – Sicherungsschicht (Data Link Layer)**
    
    Aufgabe der Sicherungsschicht ist es, eine zuverlässige, das heißt weitgehend fehlerfreie Übertragung zu gewährleisten und den Zugriff auf das Übertragungsmedium zu regeln. 
    Dazu dient das Aufteilen des Bitdatenstromes in Blöcke – auch als *[Frames](https://de.wikipedia.org/wiki/Datenframe)* oder *Rahmen*
    bezeichnet – und das Hinzufügen von [Prüfsummen](https://de.wikipedia.org/wiki/Pr%C3%BCfsumme) im Rahmen der [Kanalkodierung](https://de.wikipedia.org/wiki/Kanalkodierung).
    
    Das [Ethernet](https://de.wikipedia.org/wiki/Ethernet)-Protokoll beschreibt sowohl Schicht 1 als auch Schicht 2, wobei auf dieser als Zugriffskontrolle [CSMA/CD](https://de.wikipedia.org/wiki/Carrier_Sense_Multiple_Access/Collision_Detection) zum Einsatz kommt.
    
    Bridge, Switch
    
    ARP
    
    WLAN
    
- **Schicht 3 – Vermittlungsschicht (Network Layer)**
    
    Router, Layer-3-Switch
    
    IP, ICMP
    
- **Schicht 4 – Transportschicht (Transport Layer)**
    
    Zu den Aufgaben der Transportschicht zählt die Segmentierung des Datenstroms, die Stauvermeidung und die Sicherstellung einer fehlerfreien Übertragung.
    
    TCP, UDP
    
- **Schicht 5 – Sitzungsschicht (Session Layer)**
    
    Die Schicht 5 sorgt für die Prozesskommunikation zwischen zwei Systemen.
    
    TLS
    
- **Schicht 6 – Darstellungsschicht (Presentation Layer)**
- **Schicht 7 – Anwendungsschicht (Application Layer)**
    
    Funktionen für Anwendungen sowie die Dateneingabe und -ausgabe.
    
    HTTP/S, S/FTP, SSH, DHCP, POP, SMTP, IMAP
    

## TCP/IP - Modell

- Netzzugangsschicht
    - keine Protokolle der TCP/IP-Familie
    - Ethernet / WLAN
- Internetschicht
    - Die Internetschicht ist für die Weitervermittlung von Paketen und das (Routing) zuständig.
- Transportschicht
    - TCP
    - UDP
- Anwendungsschicht
    - Alle Protokolle, die mit Anwendungsprogrammen zusammenarbeiten