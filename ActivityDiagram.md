# Activity Diagram

## Chief-Contant-Creator (CCC)

Für die Veröffentlichung eines Beitrags auf der Website "Dino-Book" ist ein aktives Projekt erforderlich. Innerhalb dieses Projekts können mehrere Benutzer ihre Inhalte mit der Gemeinschaft von "DinoBook" teilen. Jedes Projekt erfordert einen Projektleiter, der folgende Aufgaben übernimmt:

- **das Projekt einrichtet**
	- das Projekt anlegt
	- die Projektseite gestaltet
	- ggf. ein Priviläg einer fakultären Organisation freischaltet
- **das Projekt verwaltet**
	- die Projektteilnehmer verwaltet
	- den Contant verwalten
	- die Projekte zu koordinieren (Pinnwand)
	- die Bibliotheken verwaltet (Mediathek, Funddokumentationen)
- **das Projekt stilllegen**

```mermaid
stateDiagram
state fork_chef <<fork>>
state fork_a1 <<fork>>
state fork_a2 <<fork>>
    [*] --> fork_chef
	  fork_chef --> Projekttitel_auswählen
	  Projekttitel_auswählen --> Layout_auswählen
	  Layout_auswählen --> fork_a1
	  fork_a1 --> fakultäre_Organisation
	  fork_a1 --> fork_a2
	  fakultäre_Organisation --> fork_a2
	  fork_a2 --> [*]
	  state fork_b1 <<fork>>
state fork_b2 <<fork>>
classDef time stroke:black,fill:white,color:black
fork_chef --> fork_b1
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

state fork_c1 <<fork>>
state fork_c2 <<fork>>
state fork_c3 <<fork>>
state fork_c4 <<fork>>

fork_chef --> fork_c1

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

state fork_d1 <<fork>>
state fork_d2 <<fork>>

fork_chef --> fork_d1

fork_d1 --> prioritärer_Aushang
fork_d1 --> regulärer_Aushang

prioritärer_Aushang --> fork_d2
regulärer_Aushang --> fork_d2

fork_d2 -->[*]

fork_chef --> Projekt_stilllegen
Projekt_stilllegen --> [*]
```
