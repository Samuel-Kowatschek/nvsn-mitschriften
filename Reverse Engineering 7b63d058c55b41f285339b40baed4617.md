# Reverse Engineering

Um zu verstehen, wie ein bestimmtes Programm unter der Haube funktioniert, werden meist 2 verschieden Ansätze gewählt, um Informationen zu bekommen:

### Statische Analyse
- Programm wird NICHT ausgeführt (deswegen statische Analyse)
- Unterstützt durch Disassemblers + Decompilers (IDA Pro, Radare2, Cutter, ...)
- Analyse beschränkt, da die Binary durch Packer oder Obfuscator "unleserlich" gemacht werden können. (Kann durch dynamische Analyse umgangen werden, da spätestens da die Binary wieder entpackt werden muss, um Ausführbarkeit zu gewährleisten)
- Meist ist keine Debugging-Information in der Binary vorhanden (e.g. Symbole, exception guard information, Variablennamen, etc ...) weshalb die statische Analyse ohne Source-Code sehr anstrengend und Zeitaufwändig ist, da das Verhalten des Programms nur schwer eingeschätzt werden kann)

### Dynmische Analyse
- Programm wird ausgeführt, Debugger ist dem Programm angehängt
- Verhalten und Code-Pfade sind viel ersichtlicher unter bestimmten Umständen
- Programm kann anhand von Unterschiedlichen Inputs "inspiziert" werden
    - Dateien
    - stdin / stdout (Eingabe und Ausgabe im Terminal)
    - Mausbewegungen
    - Netzwerk Traffic
- Keine Garantie, dass alle Code Teile geprüft werden
- Tools
    - LTrace
        - Verfolgt Aufrufe des Programms zu bestimmten Bibliotheken (e.g. stdlib bei C oder OS-spezifische APIs)
    - STrace
        - Verfolgt System Calls (Aufrufe zu Schnittstellen, welche nur im Kernel ausgeführt werden können, da dem Programm meist Privilegien fehlen https://de.wikipedia.org/wiki/Systemaufruf)
        - Loggt Zeitpunkt vom Zugriff auf Datein oder Sockets (da beides nur über syscalls verwaltet wird)
    - LSOF (List of open files)
        - Listet alle Datein, die ein Programm gerade geladen oder Zugriff hat bzw. gerade verwendet.
    - gdb 
        - GNU Debugger welcher unter Linux verwendet werden kann, um die dynamische Analyse eines Programms vorzunehmen. (Breakpoints, Register- und Memoryzugriff, ...)
        - 
### Disassembler vs Decompiler
Um den Code eines **kompilierten** Programms zu analysieren, werden Disassembler (meist in Kombination mit einem Decompiler) verwendet.
Diese versuchen das Kompilat wieder in einzelne Anweisungen bzw. Befehle zu zerlegen.

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
- Decompiler
    - Versucht Code in einer höheren Programmiersprache zu erzeugen (Bsp. C bei native x86 oder x64 oder Java bei Smali ByteCode)
    - Code Qualität oft nicht gut
    - Code meist nicht *vollständig* richtig, da viele Informationen durch den Compiler entfernt wurden
    - Symbole, z.B. Funktions- oder Variablennamen, sind nicht wiederherstellbar, da durch Compiler entfernt

### Android

Android verwendet Java-ähnliche VM (Dalvik) → Android Runtime
Verwendete ByteCode von Dalvik = Smali genannt

Bei Smali handelt es sich wiederrum um interpretierte Anweisungen, weshalb meist wichtige Symbole (Funktions- und Variablennamen) noch zum Großteil vorhanden sind.
- Disassembling / Decompiling
  Android Apps sind immer als .apk Datei gespeichert. Diese sind eigentlich nur ein komprimiertes Archiv, welches einzelne Ressourcen der App sowie den Dalvik Byte-Code in Form von .dex Datein beeinhaltet. Diese .dex Datein können mithilfe von dex2jar in ein Java-Archiv (.jar) umgewandelt werden. Im Anschluss ist es mit einem Decompiler wie Luyten (https://github.com/deathmarine/Luyten) möglich, den Quellcode in einer Höheren Programmiersprache, wie Java oder Kotlin, einzusehen.

