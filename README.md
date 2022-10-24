# ELO-Coding-Guidelines
Die Streit ELO Coding Guidelines dienen als Hilfestellung und als Orientierung zum Programmieren in und um ELO, 
sodass eine einheitliche, unternehmensweite Richtlinie zur Erstellung von Code eingehalten wird.

Dies dient nicht nur des schnelleren Verständnis und der Wiederverwendbarkeit durch andere Kollegen, 
sondern vermittelt den Kunden einen professionellen Eindruck und ist essentiell für das gemeinsame Arbeiten an 
Entwicklungsprojekten.

![Alt text](./assets/streit_logo.jpg?raw=true "Title")

## Inhaltsverzeichnis

1. [ Namenskonvention ](#naming-conventions)

<a name="naming-conventions"></a>
## 1. Namenskonvention
Namenskonventionen sind Festlegungen/Vorschriften/Empfehlungen für Entwickler zur Benennung von Objekten, Dateien etc.
Diese dienen dazu einen einheitlichen Stil in der Programmierung einzuhalten und die Wiederfindbarkeit / Wartbarkeit und Professionalität zu erhöhen.

### 1.1 Business Solutions
Eigene Business Solutions werden wie folgt benannt: 

    - streit.kundenname(optional).komponente(BS)

    - Beispiel 1 Interne Entwicklung: streit.invoice
    - Beispiel 2 Externe Entwicklung: streit.buro.invoice 

Keine Verwendung von Großbuchstaben, Sonderzeichen und Nummerischen Charakteren in der Benennung von Business Solutions.

### 1.2 Entwicklungsdateien
Entwicklungsdateien wie Scripte, Assets usw. werden wie folgt benannt: 

    - streit.kundenname(optional).komponente(BS).servermodul.Kurzbezeichnung

    - Beispiel 1 Internes AS-Script: streit.invoice.as.Mailverarbeitung
    - Beispiel 2 Externes AS-Script: streit.buro.invoice.as.Mailverarbeitung

Zu beachten ist, dass für verschiedene Arten von Entwicklungsdateien noch einmal separate Namenskonventionen einzuhalten sind, die
ebenfalls in dieser Repository erläutert sind.
