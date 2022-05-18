# Reverse Engineering

### Statisch

- Programm wird NICHT ausgeführt
- Analyse beschränkt
- Source Code vohanden?
- 

### Dynmisch

- Programm wird ausgeführt
- Verhalten, Code-Pfade
- Debugger
- Unterschiedliche Inputs
    - Dateien
    - User-Eingaben
    - Mausbewegungen
- Keine Garantie, dass alle Code Teile geprüft werden
- Tools
    - LTrace
        - Verfolgt Funktionsaufrufe von Bibliotheken
    - STrace
        - Verfolgt System Calls
        - Zeitpunkt vom Zugriff auf Datein oder Sockets
    - LSOF (List of open files)

### Reverse Engineering

- Decompiler
    - Versucht Code in Programmiersprache zu erzeugen
    - Code Qualität oft nicht gut
    - Code kann nicht richtig sein
    - Komplexe Programme funktionieren nicht
- Disassembler
    - Assembler Code aus kompiliertem Programm
    - Maschinen Code : Assembly = 1:1
    - Assembler lesen kann schwierig sein
    - Tools:
        - AIDA Pro
        - Radar 2
    - Nativ vs Byte Code
        - Byte Code wird von Runtime / Virtueller Maschine (JVM) zu Maschinen Code übersetzt
        

### Android

Android verwendet Java-ähnliche VM → Android Runtime

Byte Code = Smali