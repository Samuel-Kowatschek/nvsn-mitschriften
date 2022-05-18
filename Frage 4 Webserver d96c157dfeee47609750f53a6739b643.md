# Frage 4: Webserver

## Framework

### Vorteile

- Kosten
- Zeit
- Modular

### Nachteile

- Updates
- Abhängigkeit

### Selbst entwickeln

### Vorteile

- Eigene Gestaltung
- Spezialisierung auf gewollte Features
    - Weniger Angriffsfläche

### Nachteile

- Risiko für Sicherheitslücken

## Proxy

- Client im LAN verbindet sich zu Proxy
- Proxy schickt ins Internet
- vgl Gateway, NAT (Proxy kann mehr)

## Reverse Proxy

- Eine Domain → viele Server
- Clients verbinden sich zum Reverse Proxy → Verteilung auf unterschiedliche Server (z.B. Load-Balancing, Verschleierung der internen Server)

## Beispiel

- Reverse Proxy wird bei einem Server nicht benötigt
    - erst bei mehreren Servern (optional)
- Virtual Host konfiguration beim Webserver
    - Host Header im HTTP-Paket
- Ein Zertifikat für jede Domain → 7
    - Certificate Authority (CA)
        - Verifikation des Benutzers
        - Eigentümer der Domain
    - Kunden prüfen Signatur der CA
- Schnittstellen
    - REST
    - Websocket
    - gRPC

## HTTP-Versionen

- HTTP 1.1
    - Plaintextprotokoll
    - wird fast überall verwendet
    - ineffizient
    - Request — Response
    - zustandslos
        - JWT müssen immer mitgeschickt werden
- HTTP 2
    - Binärprotokoll
    - Unterstützt Data-Streams
        - ein TCP-Datenstrom
        - mehrere HTTP 2 Verbindungen
        - bei Fehler von einer HTTP2 Verbindungen werden alle anderen aufgehalten
            - hohe Latenzen
            - nicht brauchbar
- HTTP 3
    - QUIC
    - UDP statt TCP