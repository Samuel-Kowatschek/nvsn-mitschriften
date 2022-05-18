# Frage 5: IP-Adressbereiche

Klasse A: 255.0.0.0 → ein Oktett Netzteil, drei Oktette Hostbereich

- 10.x.x.x

Klasse B: 255.255.0.0 → zwei Netz/zwei Host

- 172.16.x.x - 172.31.x.x

Klasse C: 255.255.255.0 → drei Netz/ein Host

- 192.168.x.x

**Beispiel:**

255.255.255.0

10.5.3.1 → 10.5.3 Netzbereich

255.255.254.0 → ein Bit mehr für Hostbereich (512)

255.255.0.0 → 1 Byte für Subnetze (256), 2 Bytes für Hosts (256²)

10.5.3.1 → 10.5 Netzbereich

10.5.3.1 / 8 → 8 = Anzahl an Bits für Netzbereich → 255.0.0.0

10.5.3.1 / 23 → 255.255.254.0

- **IP-Adress-Klassen**
    
    Der Netzteil gibt an, in welchem IP-Netz sich ein Rechner befindet und der Hostteil identifiziert einen Rechner innerhalb dieses IP-Netzes.
    
    Ähnlich wie oben aber für öffentliche Adressen
    
- **Classless Inter-Domain Routing (CIDR)**
    
    IPv4-Adressen müssen jetzt mit einer Netzmaske angegeben werden, um den Netzteil der Adresse von dem Hostteil zu trennen.
    
    Mit Subnetzmasken den benötigten Adressraum definieren
    

### NAT (Network Address Translation)

Router schickt Anwort basierendauf Port zum jeweiligen Gerät im internen Netz