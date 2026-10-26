Aufgabe 1 Einführung in die VSCode-IDE LED-Programm in Assembler
Im Originalprogramm führt der code folgendes aus:

Anweisung	Maske	Ergebnis
STRB R2, [R6]	0x40	D14 an
STRB R3, [R6]	0x80	D15 an
STRB R0, [R6]	0x01	D08 an
STRB R0, [R7]	0x01	D08 aus
STRB R0, [R6]	0x01	D08 wieder an
STRB R1, [R6]	0x02	D09 an
STRB R2, [R7]	0x40	D14 aus
STRB R3, [R7]	0x80	D15 aus
Endzustand
D08: an
D09: an
D14: aus
D15: aus

Optimierung
Die Masken für D08 und D09 wurden zu 0x03 zusammengefasst.
Die Masken für D14 und D15 wurden zu 0xC0 zusammengefasst.

Der optimierte Programmabschnitt lautet:

MOV     R0, #0x03
MOV     R1, #0xC0
STRB    R0, [R6]
STRB    R1, [R7]
b       .
Damit wird der gleiche Endzustand mit weniger Assembleranweisungen erreicht.