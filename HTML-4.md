Events in HTML
==================

�Wenn das passiert, dann reagiere folgenderma�en darauf ...�

Events sind Status-�nderungen oder Aktionen, die bei Ihrem Eintreten einen JavaScript-Funktions-Aufruf ausl�sen.

Die m�glichen Events  h�ngen an DOM-Elementen oder Eingabeger�ten (Maus / Tastatur). 

HTML selbst verarbeitet keine Events. Die belegbaren Events m�ssen alle mit JavaScript abgearbeitet werden. Hier wird vorgestellt, wie JavaScript-Events in HTML eingebettet werden.

Event-Schl�sselw�rter beginnen mit �on�, wie in �onclick�, �onmouseover� oder �onsubmit�.

An jedes HTML-Tag k�nnen Events notiert werden.

```html
<a href="http://heise.de/" 
   onclick="alert(this.href + 'geklickt');">Heise</a>
```
Das Schl�sselwort �this� ist das DOM-Objekt des betroffenen Elements. Hier das <a>-Tag.

`<body>` Events
==================

Event-Attribut | Wann?
--- | ---
onload | Wenn das HTML-Dokument fertig geladen ist
onunload | Wenn die Seite verlassen wird
ontouchstart | Wenn ein Touch-Event beginnt (nur auf Smartphones und Tablets verf�gbar)
onresize | Wenn sich die Gr��e des Fensters �ndert

`<form>` Events
==================

Event-Attribut | Wann?
--- | ---
onsubmit | Bevor das Formular abgeschickt wird
onfocus | Bevor ein Element den Fokus erh�lt
onblur | Wenn ein Element den Fokus verliert
onchange | Bevor ein Element ge�ndert wird

Keyboard-Events
==================

Keyboard-Events k�nnen an Eingabefeldern angegeben werden.

Event-Attribut | Wann?
--- | ---
onkeyup | Wenn eine gedr�ckte Taste losgelassen wird
onkeydown | Wenn eine Taste gedr�ckt wird (ohne loslassen)
onkeypress | Wenn eine Taste gedr�ckt wurde

`<img>` Events
==================

Event-Attribut | Wann?
--- | ---
onload | W�hrend das Bild l�dt
onabort | Wenn der Bild-Download abgebrochen wurd

Mouse-Events
==================

Event-Attribut | Wann?
--- | ---
onclick | Bei Maus-Klick
ondlbclick | Bei Doppelklick
onmouseover | W�hrend man sich mit der Maus �ber dem Element befindet
onmouseout | Wenn man mit der Maus ein Element verl�sst
onmousedown | Wenn man eine Maus-Taste dr�ckt (ohne los zu lassen)
onmouseenter | Wenn man mit der Maus ein Element betritt
onmousemove | Wenn man die Maus �ber dem Element bewegt
onmouseup | Wenn man eine gedr�ckte Maustaste losgelassen wird

data-Attribute
==================

data-Attribute sind (nicht definierte) HTML-Attribute, die mit �data-� beginnen. Im Gegensatz zu falsch geschriebenen oder nicht definierten HTML-Attributen k�nnen data-* Attribute beliebig eingesetzt werden (keine W3C-Validator-Meldung). Beispiel:

```html
<img src="small-image.jpg" 
     title="Klick zum Zoom" 
     data-image="big-image.jpg" />
```

Die Zeichenfolge hinter �data-� kann frei gew�hlt werden aus Buchstaben und Zahlen.

data-Attribute k�nnen unter anderem Informationen f�r Events bereithalten, so dass eine individuelle Funktionalit�t erreicht werden kann. Die Auswertung des data-Attributes muss �ber JavaScript erfolgen und kann bedingt mit CSS-Selektoren zur optischen Gestaltung verwendet werden.