Einleitung
==========
HTML steht für HyperText Markup Language.

Ein Hypertext-Dokument ist eine Webseite mit Links zu anderen Webseiten im Internet.

HTML gibt es seit etwa 1992.

HTML ist eine Text-Beschreibungs-Sprache, keine Programmiersprache.

Die aktuelle HTML-Version ist 4.01.

HTML5 befindet sich von Seiten des World-Wide-Web-Consortiums (W3C) noch in der Entwicklung, erfreut sich jedoch schon regem Einsatz im Internet.

Ein HTML-Dokument wird mit sog. Tags [tæg] (Auszeichnern) aufgebaut, wie man sie durch XML kennt.

Grundgerüst einer Webseite
==========================

Ein HTML-Dokument ist quasi ein XML-Dokument, dessen Tags durch die HTML-Spezifikation bestimmt sind.

```html
<!DOCTYPE HTML>
<html>
<head>
  <title>Der Titel der Webseite</title>
</head>
<body>
  Hier steht der Inhalt den man auf der Webseite sehen kann.
</body>
</html>
```
Der Doctype kennzeichnet das HTML-Dokument als HTML5-Dokument.

Das gesamte Dokument ist in das <html>-Tag eingeschlossen.

Darin befindet sich ein Kopf-Bereich (für Angaben, die man in der Webseite nicht sehen kann) und der eigentliche Inhaltsbereich (body).
In head und body können wiederum Tags stehen.

Aufbau von Tags
===============
Tag
---
Tags sind eingeschlossen in spitze Klammern.

Jedes Tag hat ein Anfangs-Tag und ein Ende-Tag (oder es beendet sich selbst).

Tag  | Bedeutung
--- | ---
`<strong>`  | Anfangs-Tag 
`</strong>` | Ende-Tag 
`<br />`    | Tag beendet sich selbst (Zeilenumbruch) 

Ein Tag wird zwischen Anfangs-und Ende-Tag angewendet.

```html
<strong>Fetter Text</strong>
```

Tag-Name hier: strong

Auszeichner für den Inhalt: „Fetter Text“

Tags können beliebig verschachtelt werden. Regel: das zuletzt geöffnete Tag muss als erstes wieder geschlossen werden.
```html
<div><strong>Fetter <em>Text</em></strong></div>
```

Tag  | Bedeutung
--- | ---
`<div>`   | gilt für den gesamten Inhalt. 
`<strong>` | gilt für den gesamten Text. 
`<em>` |	gilt für den Text „Text“.

Tag-Attribute
-------------
Anfangs-Tags können Attribute beinhalten, die näher beschreiben, wie sich dieses Tag auswirken soll.

```html
<h1 id="WichtigeEigenschaften">Thema: Wichtige Eigenschaften</h1>
<a href="http://www.golem.de" target="_blank">Link zu Golem</a>
```

Attribute stehen mit einem Leerzeichen vom Tag-Namen abgesetzt und bestehen aus einem Bezeichner, dessen Eigenschaft/Wert mit einem Gleichheitszeichen verbunden wird. Der Wert wird in Gänsefüßchen eingeschlossen.

Es können mehrere unterschiedliche Attribute innerhalb eines Tags verwendet werden.

Welche Attribute bei welchem Tag funktionieren definiert die HTML-Spezifikation.

```html
<h1 id="WichtigeEigenschaften">...</h1>
```

id |	Bezeichner für das id-Attribut 
WichtigeEigenschaften|	Wert des id-Attributs 

Einfache Textformatierung mit HTML
----------------------------------
Nachfolgend die am häufigsten verwendeten Textformatierungen.

Tag  | Bedeutung
--- | ---
`<strong>` | Fetter Text
`<em>` |Kusiver Text
`<u>` | Unterstrichener Text
`<strike>` | Durchgestrichener Text
`<sup>` | Hochgestellter Text

Weiterführende Informationen finden Sie unter http://www.w3schools.com/html5/html5_reference.asp 

Einfache Text-Strukturierung mit HTML
-------------------------------------
Bei Textstrukturierung ist es empfehlenswert eine einheitliche, blockweise Einrückung zu verwenden. So bleiben die Zusammenhänge der Tags leicht erfassbar.

Tag  | Bedeutung
--- | ---
`<h1>` | Überschrift ersten Grades
`<h2> - <h5>` | Überschrift 2. bis 5. Grades
```<p>Absatz 1</p>`<br/>`<p>Absatz 2</p>``` | Paragraph / Absatz<br />Absatz 1<br />Absatz 2
```html
<ul>
  <li>Punkt 1</li>
  <li>Punkt 2</li>
</ul>``` | Unsortierte Liste (mit Punkten)<br />Punkt 1<br />Punkt 2

<ol>
  <li>Punkt 1</li>
  <li>Punkt 2</li>
</ol>
Geordnete Liste (mit Zahlen)
1. Punkt 1
2. Punkt 2
<ul>
  <li>Punkt 1</li>
  <li>Punkt 2
    <ol>
      <li>Punkt 2.1</li>
      <li>Punkt 2.2</li>
    </ol>
  </li>
</ul>
Verschachtelte Listen
Punkt 1
Punkt 2
1. Punkt 2.1
2. Punkt 2.2
<blockquote>
„Phantasie ist wichtiger als Wissen, denn Wissen ist begrenzt.“
</blockquote>
Zitat
„Phantasie ist wichtiger als Wissen, denn Wissen ist begrenzt.“
6. Links und URLs
6.1. Links in HTML
Erst Links machen ein Hypertext-Dokument so richtig „Hyper“.
Das Link-Tag lautet „a“ für Anchor (Anker). Damit das Link-Ziel klar ist, ist das Attribut „href“ (hpyertext-reference) Pflicht.
<a href="http://www.golem.de/index.htm">Link zu Golem</a>
6.2. URL
URL steht für Unique Resource Location.
Es gibt unterschiedliche Ausprägungen von Links innerhalb einer Webseite.
Angenommen, der Link befindet sich in einer Seite "http://example.com/de/infos.html
http://www.golem.de/index.htm
Vollständig

/en/material.html
Absolut
/en/infos.html
impressum.html
Relativ
/de/impressum.html
Der vollständige Link beinhaltet alle Komponenten einer URL:
1. Protokoll	http:// oder https://
2. Domain		bspw. www.golem.de
3. Pfad		bspw. /en/infos.html
Der absolute Link beinhaltet das vollständige Pfadsegment, beginnend mit einem Schrägstrich „/“.
Der relative Link beinhaltet eine Pfadangabe ohne Schrägstrich am Anfang. Das Link-Ziel wird ausgehend voḿ aktuellen Pfad ermittelt. Zwei Punkte „..“ als Pfad-Segment bezeichnen die vorausgehende Pfad-Ebene.
Seite
Link
Ziel
/de/neu/infos.html
material.html
/de/neu/material.html
/de/neu/infos.html
jobs/alle.html
/de/neu/jobs/alle.html
/de/neu/infos.html
../unternehmen.html
/de/unternehmen.html
6.3. URL-Parameter
URLs können Parameter für Scripte auf dem Server beinhalten.
Diese sogenannten GET-Parameter sind wie folgt aufgebaut:
parameter=wert
Mehrere GET-Parameter können mit „&“ verbunden werden.
modul=Seite&aktion=Anzeigen&seite=Jobs
Diese Parameter-Kette (Query String) wird mit einem „?“ an die URL angeheftet.
/index.php?modul=Seite&aktion=Anzeigen&seite=Jobs
Eine URL mit Parametern wird auch als URI (Unique Resource Identifier) bezeichnet. Jede URL ist auch eine URI, aber nicht jede URI ist eine URL.
7. Einbinden von Stylesheets
Stylesheets werden üblicherweise im head-Bereich der Webseite notiert.
Dies kann 2 Ausprägungen haben:
Direkt:
<style>
  body {
    font-family: Arial, Helvetica, Verdana;
    font-size: 0.9em;
  }
</style>
Ausgelagert (zu bevorzugen):
<link rel="stylesheet" type="text/css" href="/styles/standard.css" />
Einbinden von JavaScript
JavaScript kann im head- oder im body-Bereich notiert werden. Die lineare Verarbeitung ist bei der Platzierung zu berücksichtigen.
Direkt:
<script type="text/javascript">
  alert("JavaScript sagt Hallo!");
</script>
Ausgelagert (zu bevorzugen):
<script type="text/javascript" src="/js/myscript.js"></script>
