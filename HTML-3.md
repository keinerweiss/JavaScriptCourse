Formulare
==================

Formulare sind eine Gruppe von Eingabefeldern. Formulare werden mit dem `<form>` Tag umschlossen. Ein Formular enthält die entsprechenden Eingabefelder und Schaltflächen und wird als „Ganzes“ abgeschickt. Andere Formulare auf der selben Webseite werden selbstverständlich nicht ebenfalls abgeschickt.

Das `<form>` Tag hat folgende wichtige Attribute:

Attribut |  Beschreibung | Beispiele Inhalt
--- | --- | ---
method | Sende-Art | "POST" / "GET"
action | Ziel URL | "formular.html"
Enctype | |
onsubmit | Aktion vor dem Versenden | "return false;" (stoppt Versand)

Jedes Eingabefeld in einem Formular muss in einem Blocklevel-Element eingeschlossen sein, bspw in `<p>`, `<div>` oder `<fieldset>`
Drückt der Benutzer in einem Eingabefeld die Eingabetaste (Enter) wird das Formular bereits abgeschickt.

Der Unterschied zwischen den Sende-Arten GET und POST ist, dass GET die Formularwerte sichtbar an die URL anhängt  wohingegen POST die Formularwerte unsichtbar im Hintergrund überträgt.

Wichtig: `<form>` Tags können nicht verschachtelt werden.

Eingabefelder generell
==================

Jedes Eingabefeld kann deaktiviert werden. Das Attribut „disabled“ verhindert das Bearbeiten, das Eingabefeld ist jedoch weiterhin sichtbar.

```html
<input type="text" name="email" value="hans@web.de" disabled="disabled" />
```
Um ein deaktiviertes Feld zu reaktivieren, muss das Attribut entfernt werden. Ein leerer Wert genügt nicht.

Ein Eingabelement mit Texteingabe kann mit einem Platzhalter vorbelegt werden. Für E-Mail Felder bspw. „example@example.com“ o.ä.. Das Attribut „placeholder“ sorgt für diese Anzeige.

```html
<input type="text" name="email" placeholder="example@example.com" />
```

Fieldset
==================

Mit einem `<fieldset>` Tag lassen sich Bereiche innerhalb eines Formulars thematisch zusammenfassen. Das `<legend>` Tag enthält hierbei eine Art Überschrift für das Fieldset.

```html
<form method="GET">
  <fieldset><legend>Persönliche Angaben</legend>
    <!-- Formularfelder -->
  </fieldset>
  <fieldset><legend>Zahlungsinformationen</legend>
    <!-- Formularfelder -->
  </fieldset>
  <fieldset><legend>Interessen</legend>
    <!-- Formularfelder -->
  </fieldset>
</form>
```

Fieldsets haben für das Formular an sich keine weitere technische Bedeutung. 

Fieldsets sind Blocklevel-Elemente.

Label
==================

Mit einem `<label>` Tag werden Formularfelder beschriftet. Das Attribut „for“ bezeichnet das Eingabefeld (dessen „id“) für dieses Label.

Klickt man auf das Label, wird das entsprechende Eingabefeld aktiviert.

```html
<p>
  <label for="vorname">Vorname: </label>
  <input type="text" value="Angezeigter Wert" name="vorname"
         id="vorname" class="input-text" />
</p>
```

Label sind Inline-Elemente. 

Einzeiliges Eingabefeld
==================

Einzeilige Eingabefelder werden zur Eingabe kurzer Texte verwendet. Bspw. E-Mail Adresse, Vorname/Nachname, PLZ, Titel, Stichwörter, etc ...

```html
<input type="text" value="Angezeigter Wert" name="vorname" id="vorname" />
```

Den Inhalt einzeiliger Eingabefelder merkt sich der Browser anhand des Feldnamens. So kommt es, dass auf gänzlich fremden Seite im E-Mail Feld bereits E-Mail Adressen während des Tippens vorgeschlagen werden, die man in E-Mail Felder anderer Webseiten verwendet hat. Möchte man dies nicht, lässt sich die „autocomplete“-Funktion abschalten durch das Attribut „autocomplete“.

```html
<input type="text" name="email" id="email" autocomplete="off" />
```

Einzeilige Eingabefelder kennen das Attribut „size“, welches die Breite der Box in „Zeichen“ beschreibt. Hierfür sollten aus Präzisionsgründen aber besser Stylesheet-Angaben verwendet werden.

Das Attribut „maxlength“ gibt die maximale Anzahl eingebbarer Zeichen an. Ist die maximale Zeichenanzahl erreicht, können keine weiteren Zeichen mehr angegeben werden.

```html
<input type="text" name="vorname" maxlength="125" />
```

Mehrzeiliges Eingabefeld
==================

Um tendenziell längeren, mehrzeiligen Text (bspw einen Mail-Text oder eine Rezept-Beschreibung) eingeben zu lassen, werden sog. Textareas verwendet.

```html
<textarea name="vorname" id="vorname">Angezeigter Inhalt</textarea>
```

Wichtig bei der Textarea ist, dass direkt nach dem öffnenden Text – ohne Zeilenumbruch oder Leerzeichen - mit dem Inhalt begonnen werden muss, da alles innerhalb der `<textarea>` Tags der Textinhalt des Feldes ist.

Die `<textarea>` kennt die Attribute „cols“ (Anzahl Zeichen in der Breite) und „rows“ (Höhe des Feldes in Zeilen). Aus Präzisionsgründen sollten aber besser  Stylesheet-Angaben verwendet werden.

Bei mehrzeiligen Eingabefelder kann keine maximale Zeichenanzahl als Attribut vorgegeben werden.

Passwortfeld
==================

In Password-Feldern werden die eingegebenen Zeichen als Sternchen oder Punkte angezeigt.

```html
<input type="password" name="passwort" id="passwort" />
```

Es hat die selben Eigenschaften wie ein normales einzeiliges Eingabefeld.

Datei-Upload
==================

Dieses Feld ermöglicht es dem Benutzer, eine Datei von der Festplatte auszuwählen und beim Absenden des Formulars hochzuladen.

```html
<input type="file" name="passwort" id="passwort" />
```

Es kann lediglich eine Datei auf einmal hochgeladen werden. 
Der Text für den Button „Auswählen“ kann nicht beeinflusst werden. Er wird je Sprache und Betriebsystem anders dargestellt.
Das Feld kann aus Sicherheitsaspekten nicht mit einem Wert vorbelegt werden.
Damit ein Datei-Upload auch wirklich funktioniert, muss dem <form> Tag ein weiteres Attribut enctype="multipart-formdata" gegeben werden.

Checkbox
==================

Checkboxen sind für Mehrfachauswahl gedacht, wobei es sich jedes Checkbox-Element durch eine viereckige Box darstellt.

```html
<input type="checkbox" value="Sport" name="hobby-sport"
   id="hobby-sport" checked="checked" />
<label for="hobby-sport">Sport-Interesse</label>
<input type="checkbox" value="TV" name="hobby-tv" 
   id="hobby-tv" />
<label for="hobby-tv">TV-Interesse</label>
```

Das „name“ Attribut muss je einen unterschiedlichen Namen haben.

Auch für die „id“ müssen eindeutige Werte vergeben werden, um eine Label-Zuordnung zu ermöglichen.

Durch das Label wird erst die Bedeutung der Checkbox ersichtlich.

Durch das Attribut „checked“ kann ein Eintrag vorausgewählt werden (Haken gesetzt).

Beim Absenden des Formulars werden nur die aktivierten Checkboxen mitgesendet.

Das Label ist rechts von der Checkbox am intuitivsten.

Radioboxen
==================

Checkboxen sind für Einfachauswahl aus einer Menge Optionen gedacht, wobei sich jedes Radio-Element durch eine runde Box darstellt.

```html
<input type="radio" value="Herr" name="anrede" 
   id="anrede-herr" />
<label for="anrede-herr">Herr</label>
<input type="radio" value="Frau" name="anrede" 
   id="anrede-frau" />
<label for="anrede-frau">Frau</label>
```

Wichtig ist, dass das „name“ Attribut bei allen zusammengehörigen Radio-Buttons den selben Namen haben muss.

Für die „id“ müssen eindeutige Werte vergeben werden, um eine Label-Zuordnung je Feld zu ermöglichen.

Selectbox allgemein
==================

Das `<select>` Tag kann für Dropdowns und mehrzeilige Auswahlfelder mit einfacher und mehrfacher Auswahl verwendet werden.

Das `<select>` Tag umgibt eine Reihe `<option>` Tags (die zur Verfügung stehenden Auswahlfelder).

Das `<select>` Tag trägt den Namen und die `<option>` Tags die möglichen Werte.

```html
<label for="auswahlfeld">Auswahl</label>
<select name="auswahlfeld" id="auswahlfeld">
  <option value="wert1">Anzeige Wert 1</option>
  <option value="wert2" selected="selected">Anzeige Wert 2</option>
  …
</select>
```

Um eine Element vorauszuwählen, wird das Attribut „selected“ an einer Option gesetzt.

Durch Drücken von Buchstaben kann man innerhalb eines select-Feldes Einträge schnell auffinden.

Durch das Bilden von Options-Gruppen können lange Listen übersichtlicher gestaltet werden.

```html
<select name="auswahlfeld">
  <optgroup label="Sofas">
    <option value="wert1">Sofa 1</option>
    <option value="wert2" selected="selected">Sofa 2</option>
  </optgroup>
  <optgroup label="Stühle">
    <option value="wert3">Stuhl 1</option>
    <option value="wert4"> Stuhl 2</option>
  </optgroup>
  …
</select>
```

Einzeilige einfache Auswahl (Dropdown)
-------------------------------------------

Mit dem `<select>` Tag lassen sich Dropdowns (Einfach-Auswahl-Felder) realisieren. Die Darstellung entspricht je der Betriebsystem-Vorgabe.

Das `<select>` Tag umgibt eine Reihe `<option>` Tags (die zur Verfügung stehenden Dropdown-Einträge).

Das `<select>` Tag trägt den Namen und die `<option>` Tags die möglichen Werte.

```html
<select name="anrede" id="anrede">
  <option value="m">Herr</option>
  <option value="f">Frau</option>
</select>
```

Ohne weitere Angaben wird die Erste `<option>` vorausgewählt. 

Beim Absenden des Formulars wird nur der Wert (value) der ausgewählten Option gesendet.

Mehrzeilige Einfachauswahl
-------------------------------------------

In mehrzeiligen Eingabefelder werden die verfügbaren Einträge als Liste angeboten. Sind mehr Einträge verfügbar als die Höhe des Elements zulässt, erscheinen Scrollbalken.

```
<select name="anrede" id="anrede" size="3">
  <option value="Herr">Herr</option>
  <option value="Frau">Frau</option>
</select>
```

Das Attribut „size“ gibt an, wie hoch das Auswahlfeld sein soll (in Zeilen). 

Hier wird ohne Angabe keine Vorauswahl getroffen.

Mehrzeilige Mehrfachauswahl
-------------------------------------------

In mehrzeiligen Eingabefelder mit Mehrfachauswahl werden die verfügbaren Einträge als Liste angeboten. Sind mehr Einträge verfügbar als die Höhe des Elements zulässt, erscheinen Scrollbalken.

```html
<select name="hobby" id="hobby" size="3" multiple="multiple">
  <option value="Sport">Sport</option>
  <option value="TV">TV</option>
</select>
```

Das Attribut „size“ gibt an, wie hoch das Auswahlfeld sein soll (in Zeilen). 

Das Attribut „multiple“ gibt an, dass Mehrfachauswahl aktiviert sein soll.

Hält man die Strg-Taste gedrückt, lassen sich mehrere Elemente einzeln anklicken (Mehrfachauswahl). 

Hält man die Shift/Großschreib-Taste gedrückt, lassen sich ganze Bereiche markieren. Erster Klick=Start, letzter Klick=Ende. 

Hier wird ohne Angabe keine Vorauswahl getroffen.

Button
==================

Buttons sind Schaltflächen, mit denen sich Aktionen auslösen lassen. Klassisch wird ein Formular durch einen „Submit-Button“ abgesendet.
```html
<input type="submit" name="send" value="Absenden" />
```

Ein solcher Submit-Button kann auch ein Bild sein.
<input type="image" name="send" src="images/button.jpg" width="" height="" />
```

Bei Bild-Submit-Buttons ist zu beachten, dass der Name des Formularfelds beim Absenden erweitert wird durch die X/Y-Position auf die innerhalb des Bildes geklickt wurde. In diesem Fall z.B. `send_x=12&send_y=33`
Ein Button, der das Formular auf seine Ursprungswerte zurücksetzt, wird mit dem „type="reset"“ realisiert.

```html
 <input type="reset" name="reset" value="Zurücksetzen" />
```

Buttons können auch mit dem `<button>` Tag realisiert werden. Das `<button>` Tag hat Anfang und Ende, dazwischen kann beliebiges HTML stehen, also auch Bilder.
Es gibt 3 verschiedene Button-Arten, die über das type-Attribut realisiert werden.

Submit-Button (Standard):

```html
<button type="submit" id="send" value="1">Absenden</button>
```

Beim Absenden des Formulars durch Button-Klick wird das „value“ des Submit-Buttons als Wert übertragen.
Reset-Button:

```html
<button type="reset" id="send">Zurücksetzen</button>
```

Button ohne Funktion:

```html
<button type="button" name="send">Absenden</button>
```

Buttons ohne Funktion erhalten Ihre Funktion über JavaScript.
`<button>`  Tags können HTML-Inhalt haben, der dann auf dem Button angezeigt wird.

```html
<button name="delete" value="Löschen">
  <p>
    <img src="images/loeschen.jpg" /><br />
    Löschen
  </p>
</button>
```

Auch Links können sich wie Buttons verhalten. Die Funktion muss wie beim funktionslosen Button mit JavaScript nachgerüstet werden.

```html
<a onclick="anmeldungAbschicken();return false;"
  href="#">Absenden</a>
```

Speziell HTML5
==================

HTML5 spezifiert weitere Eingabefelder, diese werden jedoch noch nicht flächendeckend unterstützt, so dass ein Einsatz noch keinen Sinn macht. Ausnahme bilden Produktionen für mobile Endgeräte wie Android oder Apple Tablets bzw Smartphones, wo von einem Safari- oder Chrome-Derivat als Browser ausgegangen werden kann.

Stand: 16.5.2012

type-Attribut | IE9 | Firefox | Chrome | Safari | Opera
---     | --- | --- | --- | --- | ---
email |      |  Ja   |  Ja  |      | Ja
url |      |  Ja   |  Ja  |      |  
date |      |     |  Ja  |  Ja  |  Ja
datetime |      |     |  Ja  |  Ja  |  Ja
datetime-local |      |     |  Ja  |  Ja  |  Ja
month |      |     |  Ja  |  Ja  |  Ja
number |      |     |  Ja  |  Ja  |  Ja
range |      |     |  Ja  |  Ja  |  Ja
search |      |     |  Ja  |  Ja  |  
tel |    |    |    |    |    | 
time |      |     |  Ja  |  Ja  |  Ja
week |      |     |  Ja  |  Ja  |  Ja

Beschreibungen und Test der Funktionalität können auf w3Schools vertieft werden:
http://www.w3schools.com/html5/html5_form_input_types.asp
http://www.w3schools.com/html5/html5_form_elements.asp
