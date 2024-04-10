# Verwaltung der Projektteilnehmer

Der CCC hat die Möglichkeit, andere Benutzer (Projektteilnehmer) zur Teilnahme an diesem Projekt einzuladen oder erhält Anfragen von Freiwilligen, die am Projekt teilnehmen möchten. Der CCC kann auch einzelne Personen vom Projekt ausschließen, wenn sie sich disqualifizieren.

```plantuml
@startuml
start
:CCC entscheidet über
Projektteilnahmer;
if (bestehendes Mitglied?) then (ja)
    :Projektteilnehmer
    disqualifizieren;
else
:neuen Projektteilnehmer
inizialisieren;
    if (Initiative vom Projektleiter) then (ja)
    else
        :Anfrage vom User;
    endif;
    if (Anfrage bestätigt) then (ja)
        :Neues Teammitglied
        hinzufügen;
    else
        fork
            :Absage
            bekanntgegeben;
        fork again
            :⏳ Warteschleife
            (2 Wochen);
            note left: bei fehlender\nBenachrichtigung
        end fork
        :Anfrage löschen;
        :Kein neues Teammitglied;
    endif;
endif;
stop
@enduml
```