Verwaltung der Projektteilnehmer

Der CCC hat die Möglichkeit, andere Benutzer (Projektteilnehmer) zur Teilnahme an diesem Projekt einzuladen oder erhält Anfragen von Freiwilligen, die am Projekt teilnehmen möchten. Der CCC kann auch einzelne Personen vom Projekt ausschließen, wenn sie sich disqualifizieren.

```mermaid
---
title: Projektteilnehmer verwalten
---
stateDiagram
state fork_b1 <<fork>>
state fork_b2 <<fork>>
classDef time stroke:black,fill:white,color:black
[*] --> fork_b1
fork_b1 --> einladen
fork_b1 --> Anfrage_erhalten
Anfrage_erhalten --> geben
state Annahme {
geben
nicht_annehmen
}
nicht_annehmen:::time --> Anfrage_löschen: nach 2 Wochen
Anfrage_löschen --> fork_b2
einladen --> bekommen
geben --> neues_Teammitglied
state Zusage {
ausständig
bekommen
}
bekommen --> neues_Teammitglied
ausständig:::time --> Einladung_löschen: nach 2 Wochen
neues_Teammitglied --> fork_b2
Einladung_löschen --> fork_b2
fork_b2 --> [*]
```
