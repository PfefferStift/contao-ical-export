contao-ical-export
==================

Zusammenkopiert aus Forenbeiträgen (daraus bei Gelegenheit eine Mini-Anleitung machen)

## Einfügen im Event-Leser

Die Extension fügt ein Modul namens "iCal Export/Download" hinzu. 
Du musst es auf der Seite des Event Lesers einbinden (oder bspw. per Insert Tag direkt im event_full Template). 


## Einfügen in der Event-Liste

Habe jetzt eine Lösung, um auch im Eventlisten-Template einen ICS-Downloadlink zu platzieren:

1.  Modul iCal-Export anlegen, ID des Moduls merken.
2.  Im Eventlisten-Template das Modul über {{insert_module::123}} platzieren.
3.  Einen Link mit folgendem href erstellen {{link_url::234}}<?= $this->alias ?>/?ics
Wobei 123 der ID des iCal-Moduls entspricht und 234 der ID der Seite, auf die Eventliste zum Einsatz kommt.

Außerdem wird in diesem Beispiel '/' als URL-Suffix vorausgesetzt. Letztlich muss ein Link gebildet werden, der dem Link zur Detailseite des Termins entspricht (auch wenn es die Detailseite gar nicht gibt, wie in meinem Fall), ergänzt um den URL-Parameter ics. 
