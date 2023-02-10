# ELO-Coding-Guidelines
Die Streit ELO Coding Guidelines dienen als Hilfestellung und als Orientierung zum Programmieren in und um ELO, 
sodass eine einheitliche, unternehmensweite Richtlinie zur Erstellung von Code eingehalten wird.

Dies dient nicht nur des schnelleren Verständnis und der Wiederverwendbarkeit durch andere Kollegen, 
sondern vermittelt den Kunden einen professionellen Eindruck und ist essentiell für das gemeinsame Arbeiten an 
Entwicklungsprojekten.

![Alt text](./assets/streit_logo.jpg?raw=true "Title")

## Inhaltsverzeichnis

1. [ Namenskonvention ](#naming-conventions)
2. [ Datentypen ](#types)
3. [ Referenzen ](#references)

<a name="naming-conventions"></a>
## 1. Namenskonvention
Namenskonventionen sind Festlegungen/Vorschriften/Empfehlungen für Entwickler zur Benennung von Objekten, Dateien etc.
Diese dienen dazu einen einheitlichen Stil in der Programmierung einzuhalten und die Wiederfindbarkeit / Wartbarkeit und Professionalität zu erhöhen.
Dieselben Namenskonventionen sollten für jeden Teil von Code beibehalten werden.

### 1.1 Business Solutions
Eigene Business Solutions werden wie folgt benannt: 

    - streit.kundenname(optional).komponente(BS)

    - Beispiel 1 Interne Entwicklung: streit.invoice
    - Beispiel 2 Externe Entwicklung: streit.kunde.invoice 

Keine Verwendung von Großbuchstaben, Sonderzeichen und Nummerischen Charakteren in der Benennung von Business Solutions.

### 1.2 Entwicklungsdateien
Entwicklungsdateien wie Scripte, Assets usw. werden wie folgt benannt: 

    - streit.kundenname(optional).komponente(BS).servermodul.Kurzbezeichnung

    - Beispiel 1 Internes AS-Script: streit.invoice.as.Mailverarbeitung
    - Beispiel 2 Externes AS-Script: streit.kunde.invoice.as.Mailverarbeitung

Übersetzungsdateien werden wie folgt benannt: 

    - Beispiel 1 Übersetzungsdatei Deutsch: streit.invoice_de
    - Beispiel 2 Übersetzungsdatei Default: streit.invoice
    
    - Beispiel 3 JavaClient Übersetzungsdatei Deutsch: text_streit.invoice.client_DE
    - Beispiel 4 JavaClient Übersetzungsdatei Default: text_streit.invoice.client

Zu beachten ist, dass für verschiedene Arten von Entwicklungsdateien noch einmal separate Namenskonventionen einzuhalten sind, die
ebenfalls in diesem Repository erläutert sind.


### 1.3 Variablen
Die Deklaration von Variablen erfolgt nach folgendem Schema. Es wird jeder Variable ein Prefix vorangestellt, der deutlich macht, 
um welchen Typ es sich handelt. Für Variablen vom Typ Objekt wird ein "o" vorangestellt, für Variablen vom Typ String ein "s" etc.
Das erhöht die Lesbarkeit und macht direkt deutlich um welchen Variablentyp es sich handelt. Der Typ einer Variable sollte nicht überschrieben werden, 
sondern es sollte eine neue Variable angelegt werden.


```JavaScript
    var oVariableOfTypeObject = {}          // Variable vom Typ Objekt
    var sVariableOfTypeString = "Test"      // Variable vom Typ String
    var iVariableOfTypeInteger = 1234       // Variable vom Typ Integer
    var dVariableOfTypeDouble  = 12,34      // Variable vom Typ Double
    var bVariableOfTypeBoolean = true       // Variable vom Typ Boolean
```

Variablen werden auch stets so benannt, dass klar ist wofür diese stehen, sodass schon am Namen erkennbar ist, 
wofür sie genutzt wird bzw. welchen Inhalt sie zugewiesen bekommt. 

```JavaScript
    var sT = "I am an Test String" // schlecht
    var sTestString = "I am an Test String" // gut
```

Variablen in JavaScript werden ebenfalls im camelCase angelegt. 

```JavaScript
    var IsimPleInteger = 123 // schlecht
    var iSimpleInteger = 123 // gut
```

Variablen namen werden niemals mit Sonderzeichen vergeben und auf gar keinen Fall wird ein $ Zeichen vergeben, das würde Konflikte mit
bestehenden JavaScript Bibliotheken und jQuery auslösen.

### 1.4 Funktionen


<a name="types"></a>
## 2. Typen

### 2.1 Primitive Typen
Beim Arbeiten mit primitiven Typen wird direkt mit deren Wert gearbeitet. 

---
> In JavaScript, a primitive (primitive value, primitive data type) is data that is not an object and has no methods or properties.
---

<a href="https://developer.mozilla.org/en-US/docs/Glossary/Primitive">Primitive Datentypen</a>

Zu den primitiven Typen gehören: 

    * String
    * Number
    * Boolean
    * Null
    * Undefined
    * Symbol 
    * Bigint

```JavaScript
    const iFoo = 1
    let iBar = foo

    iBar = 9

    console.log(iFoo, iBar)   // Ausgabe: 1, 9
```

### 2.2 Komplexe Typen
Beim Arbeiten mit komplexen Typen wird mit Referenzen zu deren Wert gearbeitet.

Zu den komplexen Typen gehören: 

    * Object
    * Array
    * Function 

```JavaScript
    const aFoo = [1, 2]
    const aBar = aFoo
    
    aBar[0] = 9

    console.log(aFoo[0], aBar[0])   // Ausgabe: 9, 9
```


<a name="references"></a>
## 3. Referenzen

3.1 Für Referenzen wird immer const verwendet und nicht var oder let. Diese Entscheidung basiert auf den Richtlinien von eslint ( prefer-const ), ( no-const-assign )
Konstanten können nicht neu zugewiesen werden, so kann verhindert werden, dass es fälschlicherweise zu erneuten Zuweisungen der Variablen kommt, was zu Bugs führen kann.


