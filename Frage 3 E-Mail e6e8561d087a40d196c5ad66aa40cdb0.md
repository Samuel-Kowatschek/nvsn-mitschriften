# Frage 3: E-Mail

## ****POP3 – Post Office Protocol, Version 3****

Übertragung eingehender Mails

## ****IMAP – Internet Message Access Protocol****

Synchronisation zwischen Postfach und Endgeräten

## ****SMTP – Simple Mail Transfer Protocol****

Postausgang → hauptsächlich für das Senden und Weiterleiten der E-Mails

Auch zwischen den Mailservern

### Ablauf

- SMTP Paket wird zum eigenen Mailserver gesendet
    - FROM, TO, (CC), BODY
    - Authentisierung
- IP-Adresse des Ziels → MX Record der Domain
- Email wird beim Ziel-Mailserver gespeichert
- Server = Mail Transfer Agent
- Client = Mail User Agent

### Verschlüsselung

SMTPS → SMTP mit TLS

STARTTLS → Verbindung mit Plaintext → Keyword “STARTTLS” → Wechsel zu Verschlüsselung

ähnlich bei IMAP und POP3

Email werden beim Server entschlüsselt → hilft nur bei Man in the middle

### PGP

Standardisiertes Format der Schlüssel

Email wird asymmetrisch verschlüsselt

Kann nur vom Empfänger entschlüsselt werden

Header muss Plaintext bleiben → Empfänger etc sonst nicht lesbar

Integrität der Mail kann ohne Verschlüsselung nicht sichergestellt werden

### Signierung

Ebenfalls mit Keys, aber wird mit private Key verschlüsselt

### Anhänge

Bilder können mit Base64 kodiert werden

## Zentral

Ein logisches Servernetzwerk

Besitzer hat volle Autorität

## Dezentral

Mehrere Server kommunizieren miteinander

Jeder kann einen Mail-Server erstellen

Bei Ausfall keine Konsequenz für andere

## Verteilt

Jeder Server ist gleich