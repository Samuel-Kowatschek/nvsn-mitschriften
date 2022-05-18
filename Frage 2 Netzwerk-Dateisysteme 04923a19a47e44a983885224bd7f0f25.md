# Frage 2: Netzwerk-Dateisysteme

## SMB (Server Message Block)

Dateien und Drucker

SMB = CIFS (Common Internet File System)

## FTP (File Transfer Protocol)

Klartext

keine Verschlüsselung

schlecht mit Firewalls (Port 21 für Kommunikation, beliebiger Port für Transfer)

Kommunikationsprotokoll (eig. keine Dateien)

**FTPS → FTP mit TLS Layer (Verschlüsselung)**

**SFTP → basiert auf SSH, Port 22 (alles)**

## NFS (Network File System)

SMB nur für Unix

nicht verschlüsselt

keine Authentisierung

## WebDav

Exportieren von Netzwerkdateisystem auf HTTP Basis

PUT,GET → Netzwerkfreigabe

keine zusätzlichen Port bei Firewalls

nicht Pflicht für Systemaccounts

Cloudprovider

## Authentisierung

Username, Passwort

Zertifikate

Systemaccounts, DB, LDAP