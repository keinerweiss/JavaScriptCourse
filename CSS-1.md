Einleitung
==================

CSS steht für Cascading StyleSheets.

Mit CSS werden Webseiten optisch aufbereitet.

Stylesheets werden auf Tags angewendet und verändern deren Eigenschaften.

**Kaskadieren:** 

Stylesheets werden verkettet. Der globale Teil der Kette wirkt sich auf spätere Teile aus.

Beispielsweise wird die Schriftart global festgelegt und alle Elemente in der Struktur-Kette erben diese Eigenschaft automatisch, sie kann dann aber gezielt geändert werden.

Die Referenz-Seite, die zeigen soll, dass CSS ein mächtiges Gestaltungswerkzeug ist, ist der CSS Zen Garden, zu finden unter http://www.csszengarden.com/

Stylesheets in HTML
==================

Stylesheets können in HTML-Dokumenten auf 3 Arten notiert werden.
Als externe Datei eingebunden

```html
<link rel="stylesheet" type="text/css" href="/styles/standard.css" />
```

Direkt in der HTML-Seite als Style-Block

```html
<style>
  body {
    font-family: Arial, Helvetica, Verdana;
    font-size: 0.9em;
  }
</style>
```

An HTML-Tags als Style-Attribut

```html
<div style="background-color:#00ff00;width:200px; height:100px;">Test-Inhalt</div>
```

HTML-Tags stylen
==================

```css
body {
  color: green;
  font-size: 0.9em;
}
strong {
  color: red;
}
```

Für das `<body>` Tag wird festgelegt, dass die Schriftfarbe grün ist und die Schrift etwa 90% der Standard-Größe hat.

Das `<body>` Tag umschließt den gesamten Inhalt. Die Eigenschaften gelten für alle Elemente darin.

Für das `<strong>` Tag wird eine Ausnahme definiert. Seine Schrift-Farbe soll rot sein. Diese Angabe überschreibt somit die globale Vorgabe von `<body>`.

```html
<html>
...
<body>
  <p>
    Dieser Text beinhaltet einen <strong>wichtigen</strong> 
    Aspekt.
  </p>
</body>
</html>
```

Text-Eigenschaften
==================

Zur Textformatierung stehen eine Reihe von Eigenschaften zur Verfügung. Nachfolgend die am häufigsten eingesetzten Eigenschaften.

Eigenschaft | Bedeutung | Mögliche Werte
--- | --- | ---
color | Schrift-Farbe | Hex: #DEADEE<br />	Hex: #FF0088<br />Hex kurz: #F08<br />RGB: rbg(255,0,136)<br />red, blue, gray, magenta, ...
font-family | Schriftart | Schriftnamen, mit Komma getrennt.<br />serif, sans-serif, monospace<br />Beispiel: Arial, Helvetica, Verdana, sans-serif
font-size | Schriftgröße | Pixel: 		12px<br />Punkt: 		12pt<br />Prozent: 	90%<br />EM: 		0.9em<br />
font-weight | Hervorhebung | normal, bold 
text-shadow | Schatten | Schritt rechts, Schritt runter, Unschärfe, Farbe | Beispiele:<br />5px 5px 5px #FF0000;<br />0px 2px 0px #FF0000;<br />Kombinierbar mit Komma:<br />-5px 0px 2px #99FF99, 0px 2px 0px #FF0000;<br />
text-align | Ausrichtung | left, right, center
text-decoration | Deko | underline, overline, line-through, none
text-transform | Transformation | uppercase, lowercase, capitalize

Rahmen-Eigenschaften
==================

Jedes Element kann als Box mit Inhalt betrachtet werden. Um jedes Element lassen sich Rahmen darstellen. Rahmen lassen sich flexibel gestalten.

Eigenschaft | Bedeutung | Mögliche Werte
--- | --- | ---
border | Rahmen<br />Kombination | Linien-Dicke, Linien-Art, Linien-Farbe<br />1px solid red
border-width | Rahmenbreite<br />Kombination | oben, rechts, links, unten<br />1px 1px 2px 3px<br />oben/unten, rechts/links<br />1px 5px<br />oben/unten/rechts/links<br />2px
border-width-top<br />border-width-right<br />border-width-bottom<br />border-width-left | Rahmenbreite<br />einzeln | Pixel, Punkt, Prozent, EM<br />2px
border-color | Linienfarbe<br />Kombination | oben, rechts, links, unten<br />#f00 #0f0 #00f #ff0<br />oben/unten, rechts/links<br />#f00 #00f<br />oben/unten/rechts/links<br />#0ff
border-color-top<br />border-color-right<br />border-color-bottom<br />border-color-left | Linienfarbe<br />einzeln | Farbe<br />#dea
box-shadow | Rahmen-Schatten | Schritt rechts, Schritt runter, Unschärfe, Farbe<br />3px 3px 0 brown<br />Kombinierbar mit Komma:<br />-1px -1px 1px #99FF99, 3px 3px 0 brown;