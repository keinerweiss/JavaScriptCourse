Formulare
==================

Formulare sind eine Gruppe von Eingabefeldern. Formulare werden mit dem `<form>` Tag umschlossen. Ein Formular enth�lt die entsprechenden Eingabefelder und Schaltfl�chen und wird als �Ganzes� abgeschickt. Andere Formulare auf der selben Webseite werden selbstverst�ndlich nicht ebenfalls abgeschickt.

Das `<form>` Tag hat folgende wichtige Attribute:

Attribut |  Beschreibung | Beispiele Inhalt
--- | --- | ---
method | Sende-Art | "POST" / "GET"
action | Ziel URL | "formular.html"
Enctype | |
onsubmit | Aktion vor dem Versenden | "return false;" (stoppt Versand)

Jedes Eingabefeld in einem Formular muss in einem Blocklevel-Element eingeschlossen sein, bspw in `<p>`, `<div>` oder `<fieldset>`
Dr�ckt der Benutzer in einem Eingabefeld die Eingabetaste (Enter) wird das Formular bereits abgeschickt.

Der Unterschied zwischen den Sende-Arten GET und POST ist, dass GET die Formularwerte sichtbar an die URL anh�ngt  wohingegen POST die Formularwerte unsichtbar im Hintergrund �bertr�gt.

Wichtig: `<form>` Tags k�nnen nicht verschachtelt werden.

Eingabefelder generell
==================

Jedes Eingabefeld kann deaktiviert werden. Das Attribut �disabled� verhindert das Bearbeiten, das Eingabefeld ist jedoch weiterhin sichtbar.

```html
<input type="text" name="email" value="hans@web.de" disabled="disabled" />
```
Um ein deaktiviertes Feld zu reaktivieren, muss das Attribut entfernt werden. Ein leerer Wert gen�gt nicht.

Ein Eingabelement mit Texteingabe kann mit einem Platzhalter vorbelegt werden. F�r E-Mail Felder bspw. �example@example.com� o.�.. Das Attribut �placeholder� sorgt f�r diese Anzeige.

```html
<input type="text" name="email" placeholder="example@example.com" />
```

Fieldset
==================

Mit einem `<fieldset>` Tag lassen sich Bereiche innerhalb eines Formulars thematisch zusammenfassen. Das `<legend>` Tag enth�lt hierbei eine Art �berschrift f�r das Fieldset.

```html
<form method="GET">
  <fieldset><legend>Pers�nliche Angaben</legend>
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

Fieldsets haben f�r das Formular an sich keine weitere technische Bedeutung. 

Fieldsets sind Blocklevel-Elemente.

Label
==================

Mit einem `<label>` Tag werden Formularfelder beschriftet. Das Attribut �for� bezeichnet das Eingabefeld (dessen �id�) f�r dieses Label.

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

Einzeilige Eingabefelder werden zur Eingabe kurzer Texte verwendet. Bspw. E-Mail Adresse, Vorname/Nachname, PLZ, Titel, Stichw�rter, etc ...

```html
<input type="text" value="Angezeigter Wert" name="vorname" id="vorname" />
```

Den Inhalt einzeiliger Eingabefelder merkt sich der Browser anhand des Feldnamens. So kommt es, dass auf g�nzlich fremden Seite im E-Mail Feld bereits E-Mail Adressen w�hrend des Tippens vorgeschlagen werden, die man in E-Mail Felder anderer Webseiten verwendet hat. M�chte man dies nicht, l�sst sich die �autocomplete�-Funktion abschalten durch das Attribut �autocomplete�.

```html
<input type="text" name="email" id="email" autocomplete="off" />
```

Einzeilige Eingabefelder kennen das Attribut �size�, welches die Breite der Box in �Zeichen� beschreibt. Hierf�r sollten aus Pr�zisionsgr�nden aber besser Stylesheet-Angaben verwendet werden.

Das Attribut �maxlength� gibt die maximale Anzahl eingebbarer Zeichen an. Ist die maximale Zeichenanzahl erreicht, k�nnen keine weiteren Zeichen mehr angegeben werden.

```html
<input type="text" name="vorname" maxlength="125" />
```

Mehrzeiliges Eingabefeld
==================

Um tendenziell l�ngeren, mehrzeiligen Text (bspw einen Mail-Text oder eine Rezept-Beschreibung) eingeben zu lassen, werden sog. Textareas verwendet.

```html
<textarea name="vorname" id="vorname">Angezeigter Inhalt</textarea>
```

Wichtig bei der Textarea ist, dass direkt nach dem �ffnenden Text � ohne Zeilenumbruch oder Leerzeichen - mit dem Inhalt begonnen werden muss, da alles innerhalb der `<textarea>` Tags der Textinhalt des Feldes ist.

Die `<textarea>` kennt die Attribute �cols� (Anzahl Zeichen in der Breite) und �rows� (H�he des Feldes in Zeilen). Aus Pr�zisionsgr�nden sollten aber besser  Stylesheet-Angaben verwendet werden.

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

Dieses Feld erm�glicht es dem Benutzer, eine Datei von der Festplatte auszuw�hlen und beim Absenden des Formulars hochzuladen.

```html
<input type="file" name="passwort" id="passwort" />
```

Es kann lediglich eine Datei auf einmal hochgeladen werden. 
Der Text f�r den Button �Ausw�hlen� kann nicht beeinflusst werden. Er wird je Sprache und Betriebsystem anders dargestellt.
Das Feld kann aus Sicherheitsaspekten nicht mit einem Wert vorbelegt werden.
Damit ein Datei-Upload auch wirklich funktioniert, muss dem <form> Tag ein weiteres Attribut enctype="multipart-formdata" gegeben werden.

Checkbox
==================

Checkboxen sind f�r Mehrfachauswahl gedacht, wobei es sich jedes Checkbox-Element durch eine viereckige Box darstellt.

```html
<input type="checkbox" value="Sport" name="hobby-sport"
   id="hobby-sport" checked="checked" />
<label for="hobby-sport">Sport-Interesse</label>
<input type="checkbox" value="TV" name="hobby-tv" 
   id="hobby-tv" />
<label for="hobby-tv">TV-Interesse</label>
```

Das �name� Attribut muss je einen unterschiedlichen Namen haben.

Auch f�r die �id� m�ssen eindeutige Werte vergeben werden, um eine Label-Zuordnung zu erm�glichen.

Durch das Label wird erst die Bedeutung der Checkbox ersichtlich.

Durch das Attribut �checked� kann ein Eintrag vorausgew�hlt werden (Haken gesetzt).

Beim Absenden des Formulars werden nur die aktivierten Checkboxen mitgesendet.

Das Label ist rechts von der Checkbox am intuitivsten.

Radioboxen
==================

Checkboxen sind f�r Einfachauswahl aus einer Menge Optionen gedacht, wobei sich jedes Radio-Element durch eine runde Box darstellt.

```html
<input type="radio" value="Herr" name="anrede" 
   id="anrede-herr" />
<label for="anrede-herr">Herr</label>
<input type="radio" value="Frau" name="anrede" 
   id="anrede-frau" />
<label for="anrede-frau">Frau</label>
```

Wichtig ist, dass das �name� Attribut bei allen zusammengeh�rigen Radio-Buttons den selben Namen haben muss.

F�r die �id� m�ssen eindeutige Werte vergeben werden, um eine Label-Zuordnung je Feld zu erm�glichen.

Selectbox allgemein
==================

Das `<select>` Tag kann f�r Dropdowns und mehrzeilige Auswahlfelder mit einfacher und mehrfacher Auswahl verwendet werden.

Das `<select>` Tag umgibt eine Reihe `<option>` Tags (die zur Verf�gung stehenden Auswahlfelder).

Das `<select>` Tag tr�gt den Namen und die `<option>` Tags die m�glichen Werte.

```html
<label for="auswahlfeld">Auswahl</label>
<select name="auswahlfeld" id="auswahlfeld">
  <option value="wert1">Anzeige Wert 1</option>
  <option value="wert2" selected="selected">Anzeige Wert 2</option>
  �
</select>
```

Um eine Element vorauszuw�hlen, wird das Attribut �selected� an einer Option gesetzt.

Durch Dr�cken von Buchstaben kann man innerhalb eines select-Feldes Eintr�ge schnell auffinden.

Durch das Bilden von Options-Gruppen k�nnen lange Listen �bersichtlicher gestaltet werden.

```html
<select name="auswahlfeld">
  <optgroup label="Sofas">
    <option value="wert1">Sofa 1</option>
    <option value="wert2" selected="selected">Sofa 2</option>
  </optgroup>
  <optgroup label="St�hle">
    <option value="wert3">Stuhl 1</option>
    <option value="wert4"> Stuhl 2</option>
  </optgroup>
  �
</select>
```

Einzeilige einfache Auswahl (Dropdown)
-------------------------------------------

Mit dem `<select>` Tag lassen sich Dropdowns (Einfach-Auswahl-Felder) realisieren. Die Darstellung entspricht je der Betriebsystem-Vorgabe.

Das `<select>` Tag umgibt eine Reihe `<option>` Tags (die zur Verf�gung stehenden Dropdown-Eintr�ge).

Das `<select>` Tag tr�gt den Namen und die `<option>` Tags die m�glichen Werte.

```html
<select name="anrede" id="anrede">
  <option value="m">Herr</option>
  <option value="f">Frau</option>
</select>
```

Ohne weitere Angaben wird die Erste `<option>` vorausgew�hlt. 

Beim Absenden des Formulars wird nur der Wert (value) der ausgew�hlten Option gesendet.

Mehrzeilige Einfachauswahl
-------------------------------------------

In mehrzeiligen Eingabefelder werden die verf�gbaren Eintr�ge als Liste angeboten. Sind mehr Eintr�ge verf�gbar als die H�he des Elements zul�sst, erscheinen Scrollbalken.

```
<select name="anrede" id="anrede" size="3">
  <option value="Herr">Herr</option>
  <option value="Frau">Frau</option>
</select>
```

Das Attribut �size� gibt an, wie hoch das Auswahlfeld sein soll (in Zeilen). 

Hier wird ohne Angabe keine Vorauswahl getroffen.

Mehrzeilige Mehrfachauswahl
-------------------------------------------

In mehrzeiligen Eingabefelder mit Mehrfachauswahl werden die verf�gbaren Eintr�ge als Liste angeboten. Sind mehr Eintr�ge verf�gbar als die H�he des Elements zul�sst, erscheinen Scrollbalken.

```html
<select name="hobby" id="hobby" size="3" multiple="multiple">
  <option value="Sport">Sport</option>
  <option value="TV">TV</option>
</select>
```

Das Attribut �size� gibt an, wie hoch das Auswahlfeld sein soll (in Zeilen). 

Das Attribut �multiple� gibt an, dass Mehrfachauswahl aktiviert sein soll.

H�lt man die Strg-Taste gedr�ckt, lassen sich mehrere Elemente einzeln anklicken (Mehrfachauswahl). 

H�lt man die Shift/Gro�schreib-Taste gedr�ckt, lassen sich ganze Bereiche markieren. Erster Klick=Start, letzter Klick=Ende. 

Hier wird ohne Angabe keine Vorauswahl getroffen.

Button
==================

Buttons sind Schaltfl�chen, mit denen sich Aktionen ausl�sen lassen. Klassisch wird ein Formular durch einen �Submit-Button� abgesendet.
```html
<input type="submit" name="send" value="Absenden" />
```

Ein solcher Submit-Button kann auch ein Bild sein.
<input type="image" name="send" src="images/button.jpg" width="" height="" />
```

Bei Bild-Submit-Buttons ist zu beachten, dass der Name des Formularfelds beim Absenden erweitert wird durch die X/Y-Position auf die innerhalb des Bildes geklickt wurde. In diesem Fall z.B. `send_x=12&send_y=33`
Ein Button, der das Formular auf seine Ursprungswerte zur�cksetzt, wird mit dem �type="reset"� realisiert.

```html
 <input type="reset" name="reset" value="Zur�cksetzen" />
```

Buttons k�nnen auch mit dem `<button>` Tag realisiert werden. Das `<button>` Tag hat Anfang und Ende, dazwischen kann beliebiges HTML stehen, also auch Bilder.
Es gibt 3 verschiedene Button-Arten, die �ber das type-Attribut realisiert werden.

Submit-Button (Standard):

```html
<button type="submit" id="send" value="1">Absenden</button>
```

Beim Absenden des Formulars durch Button-Klick wird das �value� des Submit-Buttons als Wert �bertragen.
Reset-Button:

```html
<button type="reset" id="send">Zur�cksetzen</button>
```

Button ohne Funktion:

```html
<button type="button" name="send">Absenden</button>
```

Buttons ohne Funktion erhalten Ihre Funktion �ber JavaScript.
`<button>`  Tags k�nnen HTML-Inhalt haben, der dann auf dem Button angezeigt wird.

```html
<button name="delete" value="L�schen">
  <p>
    <img src="images/loeschen.jpg" /><br />
    L�schen
  </p>
</button>
```

Auch Links k�nnen sich wie Buttons verhalten. Die Funktion muss wie beim funktionslosen Button mit JavaScript nachger�stet werden.

```html
<a onclick="anmeldungAbschicken();return false;"
  href="#">Absenden</a>
```

Speziell HTML5
==================

HTML5 spezifiert weitere Eingabefelder, diese werden jedoch noch nicht fl�chendeckend unterst�tzt, so dass ein Einsatz noch keinen Sinn macht. Ausnahme bilden Produktionen f�r mobile Endger�te wie Android oder Apple Tablets bzw Smartphones, wo von einem Safari- oder Chrome-Derivat als Browser ausgegangen werden kann.

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

Beschreibungen und Test der Funktionalit�t k�nnen auf w3Schools vertieft werden:
http://www.w3schools.com/html5/html5_form_input_types.asp
http://www.w3schools.com/html5/html5_form_elements.asp
