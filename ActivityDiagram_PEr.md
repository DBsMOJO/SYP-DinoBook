### Projekt einrichten

Bei der Erstellung des Projekts wählt der CCC:

- einen Projekttitel
- eines der (drei) vorgeschlagenen Layout-Muster für die Titelseite des Projekts

Falls der CCC nicht als regulärer Benutzer (Einzelperson) handelt, sondern im Auftrag einer fakultären Organisation ein Projekt organisiert, kann er einen Antrag an die fakultäre Organisation stellen. Bei Genehmigung erhält das Projekt einen "blauen Zertifizierungshaken", der die dahinterstehende Organisation ausweist und als "Gütesiegel" von DinoBook anerkannt wird.

```plantuml
@startuml
start
:CCC entscheidet über
das Projekt;
:Projekttitel wählen;
:Layout-Muster für
Projektseite wählen;
if (Ist CCC im Auftrag einer Organisation?) then (ja)
    :Antrag an fakultäre
	Organisation stellen;
    if (Genehmigung erhalten?) then (ja)
        :Fakultäre Kennzeichnung
		auf der Projektseite;
    else (nein)
        :Keine Kennzeichnung;
    endif
else (nein)
    :fakultäre Kennzeichnung
	nicht erforderlich;
endif
stop
@enduml
```

