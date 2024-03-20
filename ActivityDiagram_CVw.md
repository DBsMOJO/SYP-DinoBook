#### Verwaltung von Inhalten

Als Sittenwächter hat der CCC die Befugnis, Gastkommentare zu löschen oder Benutzer außerhalb des Projektteams zu sperren, sodass sie das Projekt nicht mehr verfolgen können. Der CCC kann auch bei Bedarf die Kommentarfunktion von Projektteilnehmern einfrieren, sodass sie keine weiteren Projektbeiträge mehr veröffentlichen können. Darüber hinaus kann der CCC auch Projektpostings anderer Projektteilnehmer von der Projektseite entfernen.

```mermaid
---
title: Contant verwalten
---
stateDiagram

state fork_c1 <<fork>>
state fork_c2 <<fork>>
state fork_c3 <<fork>>
state fork_c4 <<fork>>

[*] --> fork_c1

fork_c1 --> Teammitglied
fork_c1 --> User

Teammitglied --> fork_c2
fork_c2 --> Beitrag_löschen
fork_c2 --> Kommentare_freezen

User --> fork_c3
fork_c3 --> Kommentare_löschen
fork_c3 --> User_sperren

Beitrag_löschen --> fork_c4
Kommentare_freezen --> fork_c4
Kommentare_löschen --> fork_c4
User_sperren --> fork_c4

fork_c4 --> [*]
```
