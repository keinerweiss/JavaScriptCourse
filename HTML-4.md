Events in HTML
==================

„Wenn das passiert, dann reagiere folgendermaßen darauf ...“

Events sind Status-Änderungen oder Aktionen, die bei Ihrem Eintreten einen JavaScript-Funktions-Aufruf auslösen.

Die möglichen Events  hängen an DOM-Elementen oder Eingabegeräten (Maus / Tastatur). 

HTML selbst verarbeitet keine Events. Die belegbaren Events müssen alle mit JavaScript abgearbeitet werden. Hier wird vorgestellt, wie JavaScript-Events in HTML eingebettet werden.

Event-Schlüsselwörter beginnen mit „on“, wie in „onclick“, „onmouseover“ oder „onsubmit“.

An jedes HTML-Tag können Events notiert werden.

```html
<a href="http://heise.de/" 
   onclick="alert(this.href + 'geklickt');">Heise</a>
```
Das Schlüsselwort „this“ ist das DOM-Objekt des betroffenen Elements. Hier das <a>-Tag.

`<body>` Events
==================

Event-Attribut | Wann?
--- | ---
onload | Wenn das HTML-Dokument fertig geladen ist
onunload | Wenn die Seite verlassen wird
ontouchstart | Wenn ein Touch-Event beginnt (nur auf Smartphones und Tablets verfügbar)
onresize | Wenn sich die Größe des Fensters ändert

`<form>` Events
==================

Event-Attribut | Wann?
--- | ---
onsubmit | Bevor das Formular abgeschickt wird
onfocus | Bevor ein Element den Fokus erhält
onblur | Wenn ein Element den Fokus verliert
onchange | Bevor ein Element geändert wird

Keyboard-Events
==================

Keyboard-Events können an Eingabefeldern angegeben werden.

Event-Attribut | Wann?
--- | ---
onkeyup | Wenn eine gedrückte Taste losgelassen wird
onkeydown | Wenn eine Taste gedrückt wird (ohne loslassen)
onkeypress | Wenn eine Taste gedrückt wurde

`<img>` Events
==================

Event-Attribut | Wann?
--- | ---
onload | Während das Bild lädt
onabort | Wenn der Bild-Download abgebrochen wurd

Mouse-Events
==================

Event-Attribut | Wann?
--- | ---
onclick | Bei Maus-Klick
ondlbclick | Bei Doppelklick
onmouseover | Während man sich mit der Maus über dem Element befindet
onmouseout | Wenn man mit der Maus ein Element verlässt
onmousedown | Wenn man eine Maus-Taste drückt (ohne los zu lassen)
onmouseenter | Wenn man mit der Maus ein Element betritt
onmousemove | Wenn man die Maus über dem Element bewegt
onmouseup | Wenn man eine gedrückte Maustaste losgelassen wird

data-Attribute
==================

data-Attribute sind (nicht definierte) HTML-Attribute, die mit „data-“ beginnen. Im Gegensatz zu falsch geschriebenen oder nicht definierten HTML-Attributen können data-* Attribute beliebig eingesetzt werden (keine W3C-Validator-Meldung). Beispiel:

```html
<img src="small-image.jpg" 
     title="Klick zum Zoom" 
     data-image="big-image.jpg" />
```

Die Zeichenfolge hinter „data-“ kann frei gewählt werden aus Buchstaben und Zahlen.

data-Attribute können unter anderem Informationen für Events bereithalten, so dass eine individuelle Funktionalität erreicht werden kann. Die Auswertung des data-Attributes muss über JavaScript erfolgen und kann bedingt mit CSS-Selektoren zur optischen Gestaltung verwendet werden.