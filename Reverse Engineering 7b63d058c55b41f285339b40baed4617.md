# Reverse Engineering

### Statisch

- Programm wird NICHT ausgeführt
- Analyse beschränkt
- Source Code vohanden?
- 

### Dynmisch

- Programm wird ausgeführt
- Verhalten, Code-Pfade
- Debugger wird am Programm angehängt
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
    - Versucht Code in einer höheren Programmiersprache zu erzeugen (Bsp. C bei native x86 oder x64 oder Java bei Smali ByteCode)
    - Code Qualität oft nicht gut
    - Code meist nicht *vollständig* richtig, da viele Informationen durch den Compiler entfernt wurden
    - Symbole, z.B. Funktions- oder Variablennamen, sind nicht wiederherstellbar, da durch Compiler entfernt
- Disassembler
    - Versucht aus einer (großen) Reihe von Bytes (z.B. aus einer .exe) einzelne Anweisungen zu interpretieren
    - Ausgabe des Disassemblers ist meist immer Assembly einer bestimmten Architektur (z.B. x86 Assembly bei Intel oder AMD)
    - Assembler lesen ist schwierig, da Control-Flow (if, else, switch, Schleifen, ...) nicht leicht interpretierbar
    - Output des Disassemblers wird meist nochmal durch einen Decompiler gejagt (z.b. HexRays bei IDA Pro oder ret-dec bei Radare2)
    - Tools:
        - IDA Pro (Teuer, 2000€ aufwärts, Closed-Source) (Profi-Features, z.B. Debugger, deobfuscator, Python scripting, ...)
        - Radare 2 (OpenSource, gratis (na geh), jedoch für weniger Architekturen geeignet)
    - Nativ vs Byte Code
        - Byte Code wird von Runtime (z.B. CLR bei .NET) / Virtueller Maschine (JVM) interpretiert, wodurch Architekturelle und Betriebssystemunabhängige Ausführung ermöglicht wird.
        - Nativer Code ist immer speziell für eine Architektur (z.B. x86 Intel) kompiliert und hängt ggf. von bestimmten OS-APIs ab.
        - Nativer Code ist meist immer ein bisschen schneller in der Ausführung als interpretierte sprachen, da diese direkt auf der CPU ausgeführt werden können.
        

### Android

Android verwendet Java-ähnliche VM → Android Runtime

Byte Code = Smali
