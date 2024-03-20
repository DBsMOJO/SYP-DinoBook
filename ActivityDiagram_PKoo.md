#### Projekte koordinieren

Auf der Projektpinwand, die den Projektteilnehmern für allgemeine Kommunikation untereinander dient, bekommt der CCC einen exkusiven Platz. Auch kann der CCC "Allgemeine Nachrichten" aushängen, wie etwa Termine, Kodex, Adressen, etc.

```mermaid
---
title: Projekte koordinieren
---
stateDiagram

state fork_d1 <<fork>>
state fork_d2 <<fork>>

[*] --> fork_d1

fork_d1 --> prioritärer_Aushang
fork_d1 --> regulärer_Aushang

prioritärer_Aushang --> fork_d2
regulärer_Aushang --> fork_d2

fork_d2 -->[*]
```
