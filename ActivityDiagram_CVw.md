#### Verwaltung von Inhalten

Als Sittenwächter hat der CCC die Befugnis, Gastkommentare zu löschen oder Benutzer außerhalb des Projektteams zu sperren, sodass sie das Projekt nicht mehr verfolgen können. Der CCC kann auch bei Bedarf die Kommentarfunktion von Projektteilnehmern einfrieren, sodass sie keine weiteren Projektbeiträge mehr veröffentlichen können. Darüber hinaus kann der CCC auch Projektpostings anderer Projektteilnehmer von der Projektseite entfernen.

```plantuml
@startuml
start
:CCC entscheidet über die Inhalte;
if (Kommentar löschen?) then (ja)
    if(Teammitglied?) then (ja)
        :Kommentarfunktion einfrieren;
    else
        :Gastkommentar löschen;
    endif
elseif (Beitrag/Posting entfernen?) then (ja)
    :Projektposting entfernen;
elseif (User sperren?) then (ja)
    :User sperren;
endif
stop
@enduml
```

