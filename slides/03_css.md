!SLIDE

# Cascading Style Sheets

!SLIDE

## Früher: Formatierung in HTML

~~~~
<table border="0">
  <tr>
    <td>
      <font color="red">Hallo</font>
    </td>
  </tr>
</table>
~~~~

!SLIDE

## Heute: Formatierung in CSS

* Dokumentenstruktur und Layout/Formatierung sauber getrennt
* Layout/Formatierung austauschbar
* Leichtere Wiederwendbarkeit von Formatierungen
* Integration inline oder durch separate Dateien

!SLIDE

## Geschichte

| Version | Jahr             |
|---------|------------------|
| CSS1    | 1996             |
| CSS2    | 1998             |
| CSS2.1  | 2011             |
| CSS3    | 2011 - ?         |

!SLIDE

## CSS3

* Im Gegensatz zu den Vorgängern nicht _eine_ Spezifikation
* Zeitweise über 50 Module
* 4 Module sind fertig, einige weitere so gut wie

!SLIDE

## Syntax

~~~~
/* Kommentar */

<selektor> {
  <attribut>: <wert>;
}
~~~~

!SLIDE

## Einbetten in HTML

Pro Element:

~~~~
<p style="<css>">
~~~~

Externe Datei:

~~~~
<link rel="stylesheet" href="my.css" />
~~~~

Außerdem style-Tags.

!SLIDE

# Selektoren

!SLIDE

## HTML-Elemente

\* fängt alle Elemente. Konkretete Elemente können anhand ihres Namens selektiert werden.

~~~~
* { color: red; }

p { color: red; }
~~~~
 
!SLIDE

## Anhand der ID

Mit dem #-Symbol kann ein Element anhand des id-Attributs selektiert werden:

~~~~
#headline {
  ...
}

p#abstract {
  ...
}
~~~

__Achtung__: id eindeutig vergeben, im Zweifel validieren.

!SLIDE

## Für die ganze Klasse

Mit dem . kann eine Klasse selektiert werden:

~~~~
.green-text {
  color: green;
}

p.conclusion {
  ...
}
~~~~

!SLIDE

## Nach Attributen selektieren

~~~~
input[checked] {
  ...
}

input[type=text] {
  ...
}
~~~~

!SLIDE

## Mehrere Elemente selektieren

Mehrfachselektionen können einfach mit Komma getrennt werden.

~~~~
h1, h2, p, .blue-text {
   color: blue;
}
~~~~

!SLIDE

## Kontext zählt

~~~~
/* p irgendwo in einem div */
div p { ... }

/* p der direktes Kindelement eines divs ist */
div > p { ... }

/* p unmittelbar nach einer Überschift h1 */
h1 + p { ... }
~~~~

!SLIDE

## Eigenschaften überladen

Die spezifischte Regel gewinnt:

~~~~
p { color: red; }

div p { color: blue; }

div > p { color: green; }
~~~~

!SLIDE

## Pseudoklassen

Pseudoklassen können an Selektoren mit : angefügt werden:

~~~~
p:<klasse> { ... }
~~~~

Beispiele für einfache Pseudoklassen:

link, visited, hover, active, focus, enabled, disabled, checked, first-child, last-child

!SLIDE

## Parametrisierbare Pseudoklassen

Manche Pseudoklassen können mit einem Parameter versehen werden, z.B.:

* nth-child()
* nth-last-child()
* nth-of-type()
* nth-last-of-type()

!SLIDE

## Pseudoelemente

* ::first-line und ::first-letter eines Absatzes
* ::before und ::after

~~~~
p:after {
  content: "hallo";
}
~~~~

!SLIDE

# Dokumente formatieren

!SLIDE

## Größenangaben

* Absolut: px, pt, pc
* Maßeinheiten: cm, mm, in
* Relativ zur Schriftgröße: em, ex
* Relativ in Prozent: %

!SLIDE

## Farben

* 17 vordefinierte Werte, z.B. black, white, green, red, blue...
* Zusätzlich X11/SVG-Farben
* RGB hexadezimal als #rgb oder #rrggbb
* RGB dezimal als rgb(255,10,30), RGBA als rgba(255,0,50,1)
* HSL als hsl(120, 50%, 10%), HSLA als hsla(240, 60%, 100%, 1)

!SLIDE

## Schriftarten

~~~~
body { 
  font-family: "Lucida Grande", Arial, sans-serif; 
}
~~~~

Generische Schriftarten: serif, sans-serif, cursive, fantasy, monospace

!SLIDE

## Schriftgröße

~~~~
body { font-size: 12px; }
~~~~

* Eingebaute Größen: xx-small, x-small, small, medium, large, x-large, xx-large
* Relative Angaben: larger, smaller

!SLIDE

## Schriftstärke

~~~~
p { font-weight: bold; }
~~~~

Erlaubte Werte: normal, bold, bolder, lighter oder numerische Werte

!SLIDE

## Schriftstil

~~~~
p { font-style: italic; }
~~~~

Mögliche Werte: normal, italic, oblique

!SLIDE

## Schriftdekoration

~~~~
p { text-decoration: underline; }
~~~~

Mögliche Werte: underline, overline, line-through, blink

!SLIDE

## Ausrichtung

~~~~
p { text-align: center; }
~~~~

Mögliche Werte: left, right, center, justify

!SLIDE

## Weitere Texteigenschaften

~~~~
/* Shortcut */
p { font: bold 14px FreeSans, sans-serif; }

/* Transformieren */
p { text-transform: uppercase; }

/* Small-caps variante */
p { font-variant: small-caps; }
~~~~

!SLIDE

# Praxis

!SLIDE

## Textformatierung

* Wählt jeweils eine andere Schriftart für Überschriften und sonstigen Text
* Formatiert Eure Formular-Labels fett
* Zentriert Eure Überschriften
* Wertet Eure Seite durch zusätzliche Textformatierungen auf

!SLIDE

## Das Box-Model

* Jedes Element nimmt eine rechteckige Fläche in Anspruch
* Tatsächliche Breite ergibt sich aus Breite + Innenabstand + Rahmen + Außenabstand

![image](images/box_model.png)

!SLIDE

## Breite und Höhe

~~~~
div.square {
  width: 150px;
  height: 150px;
}
~~~~

Außerdem min-, max-width und -height

!SLIDE

## Overflow

Was passiert, wenn Inhalt nicht passt?

~~~~
div.square {
  overflow: hidden;
}
~~~~

Mögliche Werte: visible, hidden, scroll, auto

!SLIDE

## Innen- und Außenabstand

~~~~
/* Einzeln angeben */
p { margin-top: 10px; }

/* Mehrere Seiten auf einmal */
p { margin: 10px; } /* Alle */
p { margin: 10px 5px; } /* oben/unten, links/rechts */
p { margin: 1px 2px 4px 1px; } /* oben, rechts, unten, links */
~~~~

Analog: padding

!SLIDE

## Rahmen

~~~~
p {
  border-width: 1px;
  border-color: red;
  border-style: dashed;
}

p { border: 1px solid black; }
~~~~

!SLIDE

## Runde Ecken

~~~~
/* Für einzelne Ecke */
p { border-top-left-radius: 5px;}

/* Für alle Ecken gleich */
p { border-radius: 6px; }

/* Für alle Ecken einzeln */
p { border-radius: 1px 2px 4px 2px; }
~~~~

!SLIDE

## Hintergrund

~~~~
body { background-color: green; }

body { 
  background-image: url('back.png');
  background-repeat: repeat-y;
  background-position: center;
}

body { background: white; }
body { background: url('back.png') repeat-y center }
~~~~

!SLIDE

## Farbverlauf

~~~~
body { background: linear-gradient(white, black); }

body {
  background: linear-gradient(45deg, white, black);
}

body { background: radial-gradient(yellow, green); }
~~~~

!SLIDE

## Schlagschatten

~~~~

p { box-shadow: 3px 3px black; }

p { box-shadow: inset 4px 4px white; }

p {
  box-shadow: 5px 5px 3px 10px rgba(0,0,0,0.3);
}
~~~~

!SLIDE

# Praxis

!SLIDE

## Hintergrund und Info-Boxen

* Wählt eine andere Hintergrundfarbe als weiß
* Erstellt eine Klasse für Infoboxen
* Infoboxen sollen einen Rahmen und eine andere Hintergrundfarbe haben
* Legt ein paar Infoboxen, z.B. auf der Startseite an

!SLIDE

# Layouts

!SLIDE

## Arten von Layouts

* Problem: verschiedene Bildschirmgrößen und -auflösungen
* Lösungsansätze:
  * Feste Breite
  * Fließende Breite (liquid)
  * Responsive

!SLIDE

## Anzeigeeigenschaften

* Unterscheidung block-level und inline Elemente
* Bsp: p, div = block-level - em, span = inline
* inline-block als Sonderfall
* none unterdrückt Anzeige komplett
* Außerdem: Listen und Tabellen

~~~~
.block { display: block; }
~~~~

!SLIDE

## Positionierung 1

* Positionierung kann absolut oder relativ erfolgen
* _Absolut_ bedeutet genaue Positionierung innerhalb der Seite
* _Relativ_ bedeutet innerhalb des umgebenden Elements
* Vorsichtig einsetzen 

~~~~
#logo { position: absolute; }
~~~~

!SLIDE

## Positionierung 2

Positionierung in Abhängigkeit einer der vier Kanten top, right, bottom, left.

~~~~
#logo {
  position: absolute;
  top: 10px;
  left: 30px;
}
~~~~

!SLIDE

## z-index

* Durch genaue Positionierung können Elemente überlappen
* Welches dann vorne dargstellt wird, regelt z-index
* Je höher der z-index, desto weiter vorne
* Default: 0

~~~~
#logo { z-index: 100; }
~~~~

!SLIDE

## Floating elements

* "Floating elements" dürfen von anderen Elementen "umflossen" werden
* Beispiel: Bild im Text
* Mehrere Elemente mit float werden so lange hintereinander dargestellt, wie Platz auf der Seite ist
* Daher gut geeignet für Layouts, insbesondere "liquid layouts"
* Flußrichtung muss angegeben werden:

~~~~
.left { float: left; }
~~~~

!SLIDE

## Clearing floats

Aneinanderreihung unterbrechen - Umbruch erzwingen:

~~~~
.test { clear: left; }
.clear { clear: both; }
~~~~

!SLIDE

## Spaltenbasierte Layouts

* Standardlayouts sind häufig spaltenbasiert
* Breite Inhaltsspalte mit einer oder zwei Seitenspalten
* Relativ einfach mit float umsetzbar


!SLIDE

## Gitter/Grid-basierte Layouts

* Seitenbreite wird in x-Teile geteilt
* CSS-Klassen von 1 bis x mit passender Breite
* Zeilen enthalten Floats und sorgen für "clear"
* Summe der Breite aller Floats einer Zeile sollte = Seitenbreite sein

HAML-Beispiel mit Twitter's Bootstrap:

~~~~
.row
  .span3
  .span9
~~~~

!SLIDE

## Float gotchas

* Footer, der nicht neben Spalten rutschen soll
  * clear: both
* Floats ragen aus Container heraus
  * Spezielles clear-Element
  * Container floaten
  * overflow: hidden;
  * ::after Pseudo-Element
* Spalten gleicher Höhe
  * Hintergrundbild
* Float drops (Box-Model beachten!)

!SLIDE

# Praxis

!SLIDE

## Layout

* Infoboxen sollen von Fließtext umflossen werden
* Setzt eine feste Breite für Eure Seite
* Navigation formatieren, vom Inhalt optisch absetzen
* Erstellt Footer-Bereich, der ebenfalls optisch deutlich abgegrenzt ist

!SLIDE

# Transforms, Transitions und Animationen

!SLIDE

## Elemente transformieren

* Neuer Mechanismus für interessantere Effekte
* Mögliche Tansformationen: rotate, scale, translate, skew
* _Achtung_: Platz auf der Seite wird vor der Transformation reserviert

~~~~
nav a:hover {
  transform: rotate(10deg) scale(1.5);
}
~~~~

!SLIDE

## Einfache Animationen mit Transitions

* Mit Transitions kann man den (animierten) Übergang zwischen zwei Styles notieren
* Übergang wird getriggert durch Pseudoklasse oder JavaScript

~~~~
nav a { 
  transition-property: all;
  transition-duration: 3s;
}
~~~~

!SLIDE

## Animierbare Eigenschaften

* Animierbar sind nicht alle, aber einige Eigenschaften
* Insbesondere transform
* Außerdem: Farben, Breite/Höhe, Abstände, Schriftgröße, Position und einiges mehr

!SLIDE

## Timing

* transition-duration legt nur fest, wie lange der Übergang dauern soll
* Der Übergang selber kann in der Geschwindigkeit variiert werden
* Dafür gibt es verschiedene Funktionen: linear, ease, ease-in, ease-out, ease-in-out

~~~~
a { transition-timing-function: ease; }
~~~~

!SLIDE

## Kurzform

~~~~
nav a {
  transition: all 2s ease-in;
}
~~~~

!SLIDE

## Animationen

* Transitions ermöglichen nur Übergang A =&gt; B
* Animations ermöglichen komplexere, flexiblere Übergange wie A =&gt; B =&gt; C
* Keyframes legen Ausgangs-, Endzustand und alle Zwischenstationen fest

!SLIDE

## Keyframes

~~~~
@keyframes colorChange {
  from { background-color: red; }
  50%  { background-color: blue; }
  to   { background-color: green; }
}
~~~~

!SLIDE

## Animation starten

~~~~
div#mydiv {
  animation-name: colorChange;
  animation-duration: 5s;
  animation-timing-function: linear;
  animation-iteration-count: 3; /* oder: infinite */
  animation-direction: alternate;
}
~~~~

!SLIDE

## Kurzform

~~~~
div#other {
  animation: colorChange 2s ease 2 alternate;
}
~~~~

!SLIDE

# Praxis

!SLIDE

## Effekte

* Erstellt einen Hover-Effekt für Eure Navigation

!SLIDE

# Alternative Ausgabe-formate

!SLIDE

## Media types

* Jedes Stylesheet kann einem oder allen Media Types zugeordnet werden
* Neben Bildschirmausgabe auch Print
* Typische Aufgaben eines Print-Stylesheets:
  * Navigation ausblenden
  * Hintergrundfarben überschreiben

!SLIDE

## Responsive design

* Feste Breite immer suboptimal für bestimmte Nutzer
* "Liquid"-Layouts schwer umzusetzen
* Kompromiss: Styles in Abhängigkeit der Bildschirmgröße
* Flexibles Gittersystem und Media Queries

!SLIDE

## Media Queries

In HTML:

~~~~
<link href="mobile.css" rel="stylesheet" media="(max-width:480px)" />
~~~~

In CSS:

~~~~
@import url(mobile.css) (max-width: 480px);

@media (min-width: 481px) and (max-width: 768px) {
  body { background: white; }
}
~~~~

!SLIDE

# Browser-unterschiede

!SLIDE

## Das Leid mit den Versionen 2

* CSS2 bis heute nicht vollständig unterstützt
* CSS3-Unterstützung sehr unterschiedlich
* Darstellungsunterschiede in allen Browsern
* Pixelgenaue, identische Darstellung in allen Browsern praktisch unmöglich

!SLIDE

## Vendor prefixes

* Neue Features, die noch nicht stabil sind
* Nutzung früh möglich, aber in jedem Browser anders
* Präfixe entfallen erst kurz vor finalem Standard

Beispiel runde Ecken:

~~~~
#rounded {
  -webkit-border-radius: 15px;  
  -moz-border-radius: 15px;
  border-radius: 15px;
}
~~~~

!SLIDE

## Quirks mode

* Die meisten Browser unterscheiden "Quirks" und "Standards" Modi
* Darstellungsunterschiede
* Quirks mode wird u.a. durch fehlenden Doctype getriggert
* Simples Beispiel: text-decoration und floats

!SLIDE

## CSS Resets

* Seiten ohne CSS bekommen vom Browser ein Standardaussehen verliehen
* Eigenes CSS erweitert und überschreibt dieses
* Standardaussehen ist je nach Browser anders
* Daher: Unerwartetes Verhalten möglich
* Workaround: CSS Resets

!SLIDE

# CSS generieren mit SCSS

!SLIDE

## SCSS

* Schwester-Projekt von HAML
* SASS eng an HAML angelehnt, SCSS näher an CSS
* SCSS ist eine Obermenge von CSS, d.h. gültiges CSS ist auch gültiges SCSS
* SCSS wird zu CSS kompiliert
* Voll integriert in die Rails Asset Pipeline und default bei neuen Projekten

!SLIDE

## Variablen

Werden mit $ eingeleitet:

~~~~
$background: white;

body { background: $background; }

p { background: $background; }
~~~~

!SLIDE

## Operatoren

~~~~
$base-size = 15px;

h1 { font-size: $base-size + 15px; }
~~~~

!SLIDE

## Bedingungen und Schleifen

~~~~
@if $size < 15px { color: black; }

@for $i from 1 through 12 {
  .span-#{$i} { width: $grid-width / 12 * $i; }
}

@each $class in float1, float2, float3 {
  .#{$class} { float: left; }
}
~~~~

!SLIDE

## Farbfunktionen

~~~~

$color: rgb(1, 2, 3); // #010203

lighten($color, 10%);
darken($color, 40%);
~~~~

!SLIDE

## Selektoren verschachteln

~~~~
p {
  color: black;
  strong {
    color: red;
  }
}
~~~~

wird zu

~~~~
p { color: black; }
p strong { color: red; }
~~~~

!SLIDE

## Attribute verschachteln

~~~~
p {
  font: {
    family: FreeSans, sans-serif;
    size: 14px;
    weight: normal;
  }
}
~~~~

!SLIDE

## Vererbung

~~~~
.message { border: 1px solid black; }
.success {
  @extend .message
  color: green;
}
.error {
  @extend .message
  color: red;
}
~~~~

!SLIDE

## Mixins

~~~~
@mixin red {
  color: red;
}

p {
  @include red;
}
~~~~

!SLIDE

## Mixins parametrisieren

~~~~
@mixin colored-box($color) {
  border: 2px solid $color;
  background: lighten($color, 20%);
  color: $color;
}

.red-box {
  @include colored-box(red);
}
~~~~

!SLIDE

## Vendor prefixes

~~~~
@mixin box-shadow($shadows...) {
  -moz-box-shadow: $shadows;
  -webkit-box-shadow: $shadows;
  box-shadow: $shadows;
}

.box {
  @include box-shadow(3 3 3 black);
}
~~~~

Fertige Sammlungen von Mixins, z.b. Bourbon.

!SLIDE

# Links

!SLIDE

## Links und Literatur

* Standards: http://www.w3.org/TR/#tr_CSS
* Validator: http://jigsaw.w3.org/css-validator/
* CSS Zen Garden: http://csszengarden.com
* Gute Artikel: http://alistapart.com
* CSS3 The Missing Manual, O'Reilly, 3. Auflage
* SCSS: http://sass-lang.com

!SLIDE

# Praxis

!SLIDE

## SCSS einsetzen

* Konvertiert statische Stylesheets zu SCSS-Assets
* Legt ein Farbschema fest, dass aus 3-4 Farben besteht
* Legt Farben als SCSS-Variablen an
* Nutzt SCSS um Eure Styles übersichtlicher zu gestalten

