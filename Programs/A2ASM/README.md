(Aufgabe 2 Grundlagen der Informatik)

Anw01

ldr R0, =VariableA
R0 = Adresse von VariableA

Die Adresse von VariableA wird in R0 geladen.

Memory:
EF BE

Anw02

ldrb R2, [R0]
R2 = 0xEF

Das erste Byte von VariableA wird nach R2 geladen.

Memory:
EF BE


Anw03

ldrb R3, [R0,#1]
R3 = 0xBE

Das zweite Byte von VariableA wird nach R3 geladen.

Memory:
EF BE

Anw04

lsl R2,#8
R2 = 0xEF00

Der Inhalt von R2 wird um 8 Bit nach links verschoben.

Memory:
EF BE

Anw05

orr R2,R3
R2 = 0xEFBE

Die Werte aus R2 und R3 werden miteinander verknüpft.

Memory:
EF BE

Anw06

strh R2,[R0]
R0 = 0x2000000C
R2 = 0xEFBE
R3 = 0xBE

Der Inhalt von R2 wird zurück in den Speicher geschrieben.

Memory:

BE EF
BEEF

Wert:
0xBEEF

Memory Browser:
BE EF

BEEF ist nach Anw06 in der gewünschten Reihenfolge sichtbar.

AFFE

Neue Variable:
VariableC DCW 0x0000

Memory Browser:
AF FE

Wert:
0xAFFE

Die Bytes wurden wie bei BEEF umgeordnet, sodass AFFE lesbar wird.

1234

Memory Browser:
12 34

Wert:
0x3412

Der Registerwert wurde so gewählt, dass im Speicher 12 34 erscheint.

Ergebnis

VariableA = BE EF
VariableB = 12 34
VariableC = AF FE


Probleme
- Der Memory Browser musste nach Änderungen mit "Go" aktualisiert werden.
- Für die korrekte Darstellung wurde "Bytes Per Group = 1" verwendet.
- Weitere Probleme sind nicht aufgetreten.
- Da dies mir alles noch Neu ist (zumindest so empfunden), musste ich einige Schritte mehrfach nachvollziehen und im Debugger überprüfen, bis die Funktionsweise verständlich wurde.