!SLIDE

# HTML

!SLIDE

# Geschichte

!SLIDE

## Entstehung des Webs

* 1989 - 1991 erfindet Sir Tim Berners-Lee das WWW während seiner Arbeit am CERN
* Ziel: Wissenschaftliche Quellen im Internet leichter auffindbar machen
* Konzept: HyperText
* Komponenten:
  * URLs zur Adressierung
  * HTTP als Protokoll
  * HTML als Auszeichnungssprache nach Vorbild SGML
* 1994 wird das W3C gegründet

!SLIDE

## Standardisierung

| Version  | Jahr der Veröffentlichung|
|----------|--------------------------|
| HTML+    | 1993                     |
| HTML2.0  | 1995                     |
| HTML3.2  | 1997                     |
| HTML4.01 | 1999                     |
| HTML5    | 2014?                    |

!SLIDE

## HTML5

* Sammelbegriff, der wahlweise steht für
  * Den nächsten W3C-Standard
  * Den "lebendigen" Standard der WHATWG
  * Eine Sammlung moderner Browsertechnologien
* Erstmals weite Verbreitung _vor_ der Standardisierung

!SLIDE

# Grundlagen

!SLIDE

## Hypertext

* Texte verknüpft mit Verweisen
* Verweise = Hyperlinks
* Hypermedia als Erweiterung

!SLIDE

## URLs

* Uniform Resource Locator
* Beschreibt Ort einer Ressource in einem Netzwerk
* Aufbau von HTTP-URLs:

~~~~
http://<domain>/<pfad>?<query>#<fragment>
~~~~

!SLIDE

## Tags

~~~~
<!-- Einfacher Tag -->
<tag>Inhalt</tag>

<!-- Tag ohne Inhalt (void tag) -->
<tag />

<!-- Verschachtelte Tags -->
<tageins>
  <tagzwei />
</tageins>
~~~~

!SLIDE

## Attribute

~~~~
<tag name="wert" marker />
~~~~

Basisattribute: id, class, title, lang, dir, tabindex, contenteditable, style, u.a.

Beliebige data-Attribute erlaubt.

!SLIDE

## Basis-Dokumentenstruktur

~~~~
<!DOCTYPE html>
<html>
  <head>
    <title>Test</title>
  </head>
  <body></body>
</html>
~~~~

!SLIDE

## Doctypes

* Teilt dem Client mit, welche Version verwendet wird
* Früher komplex, HTML5 macht es simpel
* Zukunftssicher und abwärtskompatibel
* Wird gerne vergessen, ist aber wichtig für korrekte Darstellung

!SLIDE

## Dokumente validieren

* Browser sind _sehr_ tolerant, was invalides HTML angeht
* Problem: Unerwartetes Verhalten
* Problem: Darstellungsfehler
* Problem: Barrierefreiheit
* Daher besser validieren
* http://validator.w3.org

!SLIDE

# Dokumente auszeichnen

!SLIDE

## Metadaten

~~~~
<meta charset="UTF-8" />
~~~~

_Attribute_: name, http-equiv, charset, content

Beispiele für name: author, description, keywords

!SLIDE

# Dokumente gliedern

!SLIDE

## Header und Footer

~~~~
<header>Kopfbereich</header>
...
<footer>Fußbereich</footer>
~~~~

!SLIDE

## Überschriften

~~~~
<h1>Überschrift</h1>

<!-- h2, h3 usw. bis -->

<h6>Unterüberschrift</h6>
~~~~

!SLIDE

## Artikel und Sektionen

~~~~
<article>
  <section>...</section>
</article>
<div>...</div>
~~~~

!SLIDE

## Navigation und Nebenbemerkungen

~~~~
<nav>(Liste von Links)</nav>

<aside>Zusatzinfo</aside>
~~~~

!SLIDE

## Absätze

~~~~
<p>Text...</p>
~~~~

_Achtung_: Whitespace wird ignoriert. Daher Zeilen explizit umbrechen:

~~~~
Zeile 1
<br />
Zeile 2
~~~~

!SLIDE

## Spezielle Absätze

~~~~
<pre> 
 wird 
   ungefiltert 
     übernommen
</pre>

<blockquote>Sein oder nicht sein</blockquote>
~~~~

!SLIDE

## Trennzeile

~~~~
<hr />
~~~~

!SLIDE

## Sortierte Listen

~~~~
<ol>
  <li>Erster Punkt</li>
  <li>Zweiter Punkt</li>
  <li>...</li>
</ol>
~~~~

!SLIDE

## Unsortierte Listen

~~~~
<ul>
  <li>Punkt eins</li>
  <li>Punkt zwei</li>
  <li>...</li>
</ul>
~~~~

!SLIDE

## Beschreibungslisten

~~~~
<dl>
  <dt>Begriff</dt>
  <dd>Definition des Begriffs</dd>   
</dl>
~~~~

!SLIDE

# Praxis

!SLIDE

## Online Shop

* Legt ein neues Projekt für einen Online Shop an
* Legt eine eigene Datei index.html an
* Füllt die Datei mit dem notwendigen Rahmenwerk und
  * Einer großen Überschrift mit dem Namen Eures Shops
  * Unterüberschriften und Blindtext für die Shop-Beschreibung, Artikelliste und Versandbedingungen
  * Einer Liste mit Artikeln
* Validiert Eure Datei

!SLIDE

# Textaus- zeichnung

!SLIDE

## Einfache Textauszeichnung

~~~~
HTML kann <em>viel</em>.

<strong>Achtung:</strong> Man kann auch viel falsch machen.

<small>Auch kleine Fehler, können große Auswirkungen haben.</small>

<s>HTML5 wird niemals fertig</s>

~~~~

!SLIDE

## Einfache Textauszeichnung 2

~~~~
Texte können vielfältig <i>ausgezeichnet</i> werden.

Wörter können auch ohne besondere Bedeutung <b>hervorgehoben</b> werden.

Und auch <u>das hier</u> geht, sollte aber mit Vorsicht genossen werden.
~~~~

!SLIDE

## Hyperlinks

~~~~
<a href="http://my.site/">Home</a>
~~~~

_Attribute_: href, target u.a.

!SLIDE

## Wo zeigt der Link hin?

Das href-Attribut darf folgendes enthalten:

* komplette URI, z.B.
  * HTTP-URL
  * mailto
  * javascript
* Relativer oder absoluter Pfad
* Fragment

!SLIDE

## Wo wird der Link geöffnet?

Das target-Attribut kann folgende Werte annehmen:

* \_self = selbes Fenster
* \_blank = neues Fenster
* \_parent und \_top bei Verschachtelten Dokumenten
* Beliebiger neuer Name = neues Fenster
* Bestehender Name = Fenster mit diesem Namen

!SLIDE

## Spezielle Texte

~~~~
<abbr title="HyperText Markup Language">HTML</abbr>

<code>alert('welcome');</code>

<span>...</span>
~~~~

!SLIDE

## Semantisches Markup

* HTML zeichnet die Dokumentenstruktur aus
* div und span bieten maximale Flexibilität
* ...aber auch wenig Info über die tatsächliche Struktur
* Gefahr, Zuständigkeiten durcheinander zu bringen
* Wo möglich, passendere Tags verwenden
* Erhöht Wartbarkeit, kann besser weiterverarbeitet werden, ist barrierefreier

!SLIDE

# Praxis

!SLIDE

## Textauszeichnung und Links

* Wertet Texte durch Auszeichnungen auf
* Legt (mindestens) eine Artikelseite an
* Überlegt Euch mindestens 2 Kategorien für Artikel und legt Übersichtsseiten dafür an
* Verlinkt alle Seiten sinnvoll untereinander
* Ergänzt am Fuße der Startseite einen Link, um nach oben zu gelangen

!SLIDE

## Tabellen

~~~~
<table>
  <thead>...</thead>
  <tbody>...</tbody>
  <tfoot>...</tfoot>
</table>
~~~~

!SLIDE

## Kopfzeile

~~~~
<thead>
  <tr>
    <th>Spalte1</th>
    <th>Spalte2</th>
  </tr>
</thead>
~~~~

!SLIDE

## Inhaltsbereich

~~~~
<tbody>
  <tr>
    <td>Wert1</td>
    <td>Wert2</td>
  <tr>
</tbody>
~~~~

!SLIDE

## Zellen ausdehnen

~~~~
<tr>
  <td colspan="2">Ganze Zeile</td>
</tr>
<tr>
  <td rowspan="2">Über zwei Zeilen</td>
  <td>...</td>
</tr>
<tr>
  <td>...</td>
</tr>
~~~~
!SLIDE

## Formulare

~~~~
<form action="/checkout">
  ...
</form>
~~~~

_Attribute_: action, method, name, target, novalidate, accept-charset, autocomplete, enctype

!SLIDE

## Formulare strukturieren

~~~~
<fieldset>
  <legend>Stammdaten</legend>
</fieldset>
~~~~

!SLIDE

## Eingabefelder

~~~~
<label for="name-input">Name</label>
<input id="name-input" type="text" name="name" />
~~~~

_Attribute_: name, type, value, disabled, u.a. 

!SLIDE

## Einfache Eingabefelder

* hidden - wird nicht angezeigt
* text - einzeiliges Textfeld (size, placeholder)
* checkbox - zum Anhaken (checked)
* radio - Einzelauswahl aus mehreren Werten (checked)
* file - Dateiauswahl
* password - Passworteingabe (size)
* submit, reset - Buttons

!SLIDE

## HTML5 Eingabefelder

* search
* tel, url, email
* (datetime, date, time, month, week)
* number
* range
* (color)

!SLIDE

## Eingabe längerer Texte

~~~~
<textarea name="description" rows="25" cols="80" >
</textarea>
~~~~

!SLIDE

## Einzelauswahl

~~~~
<select name="country">
  <option>Germany</option>
  <option>France</option>
  <option>USA</option>
</select>
~~~~

!SLIDE

## Mehrfachauswahl

~~~~
<select name="countries" multiple>
  <option value="de">Germany</option>
  <option value="fr">France</option>
  <option value="us">USA</option>
</select>
~~~~

!SLIDE

## Optionen gruppieren

~~~~
<select name="country">
  <optgroup label="Europe">
    <option value="de">Germany</option>
    <option value="fr">France</option>
  </optgroup>
  <optgroup label="North America">
    <option value="us">USA</option>
  </optgroup>
</select>
~~~~

!SLIDE

## Buttons

~~~~
<button type="submit">
  Formular <em>jetzt</em> abschicken
</button>
~~~~

Typen: submit, reset, button

!SLIDE

## Validierungen

Client-seitige Validierungen, gesteuert über Attribute:

* required
* pattern
* maxlength
* min, max
* step

Per JavaScript erweiterbar.

!SLIDE

# Praxis

!SLIDE

## Tabelle und Formular

* Ergänzt Eure Versandbedingungen um eine Tabelle mit Versandkosten
* Legt eine neue Seite an mit einem Kontaktformular
* Das Formular soll mindestens enthalten:
  * Eingabefelder für Absendername und E-Mail
  * Dropdown zur Auswahl eines Betreffs
  * Großes Textfeld zur Eingabe einer Nachricht
* Verlinkt das Kontaktformular von der Startseite

!SLIDE

# Externe Inhalte einbetten

!SLIDE

## iframe

~~~~
<iframe src="http://google.de" ></iframe>
~~~~

_Attribute_: src, name, width, height u.a.

!SLIDE

## CSS und JavaScript

~~~~
<link rel="stylesheet" href="test.css" media="all" />

<script type="text/javascript" src="test.js" ></script>
~~~~

Wo platzieren?

!SLIDE

## Bilder

~~~~
<img src="test.png" alt="Testbild" />
~~~~

_Attribute_: src, alt, width, height u.a.

!SLIDE

## Audio

~~~~
<audio src="test.ogg" ></audio>
~~~~

_Attribute_: src, preload, autoplay, loop, muted, controls u.a.

Unterstützte Formate variieren je nach Browser.

!SLIDE

## Video

~~~~
<video src="test.webm" ></video>
~~~~

_Attribute_: src, width, height, poster, preload, autoplay, loop, muted, controls u.a.

Unterstützte Formate variieren je nach Browser.

!SLIDE

# Praxis

!SLIDE

## Bilder einbetten

* Erstellt/Sucht ein Logo und bindet das auf der Startseite ein
* Bindet ein Artikelfoto auf der Artikelseite ein

!SLIDE

# "HTML5" Features

!SLIDE

## Canvas

* Eine Fläche, deren (Pixel-)Inhalt man programmatisch ändern kann
* Ideal für Grafikprogramme, Spiele usw.

!SLIDE

## localStorage

* Eingebaute Datenbank im Browser
* Stand-alone Anwendungen ohne Server
* Offline-Anwendungen mit Synchronisation

!SLIDE

## Geolocation

* Standort des Benutzers ermitteln

!SLIDE

## Websockets

* Server hält Verbindung zu Clients, bzw. kann neue Verbindungen aufbauen
* Push-Modell
* Für Realtime-Anwendungen, wie Chats usw.

!SLIDE

## Webworkers

* Hintergrund-Threads für JavaScript-Programme
* Rechenintensive Operationen, die das UI nicht blockieren

!SLIDE

## WebGL

* 3D im Browser

!SLIDE

# Und, und und...

!SLIDE

# Developer-Tools

!SLIDE

## Beispiel: Firefox und Firebug

* JavaScript-Konsole
* HTML untersuchen
* CSS untersuchen
* HTML und CSS testweise manipulieren
* Netzwerkzugriffe betrachten
* JavaScript debuggen

In anderen Browsern mittlerweile eingebaut.

!SLIDE

# Browser-unterschiede

!SLIDE

## Das Leid mit den Versionen

* Am weitesten verbreitete Browser: Internet Explorer, Firefox, Chrome, Safari, Opera
* Dazu kommen mobile Browser
* IE macht historisch betrachtet die meisten Probleme
* Aber: Es gibt subtile Unterschiede zwischen allen Browsern
* Konservative Versionierung vs. Rolling Releases

!SLIDE

## Was kann sich alles unterscheiden?

* Unterstützte Elemente und Attribute
* Standarddarstellung von Elementen
* Funktionalität von Formulareingabefeldern
* CSS-Styling
* JavaScript-Funktionalität

!SLIDE

## Browserweiche für IE

~~~~
<!--[if IE]-->

<!--[if IE 7]-->

<!--[if lt IE 9] -->
~~~~

!SLIDE

## HTML5-Kompatibilität

* IE Versionen vor 9 ignorieren HTML5 Tags
* Problem: Elemente können nicht per CSS gestyled werden
* JS-Workaround: html5shiv

!SLIDE

# HAML

!SLIDE

## HTML mal anders

* HTML ist recht ausführlich
* Insbesondere Klammern und schließende Tags sind redundant
* Die HAML-Alternative: 
  * CSS-ähnliche Syntax für Tags 
  * Einrückung statt Tags schließen
* Rubygem mit Integration für Rails

!SLIDE

## Basisdokument

~~~~
!!!
%html
  %head
    %title HAML-Dokument
  %body
~~~~

!SLIDE

## DIVs

Besonderer Shortcut für div-Container:

~~~~
%div#container.dark

#container.dark
~~~~

!SLIDE

## Attribute

Sehen aus wie Ruby-Hash:

~~~~
%a{:href => "test.html"} Testlink
~~~~

Benutzung von Ruby-Code möglich.

!SLIDE

## Dynamische Inhalte

~~~~
%p
  = my_helper()
  Eingebetteter Wert: #{4 + 3}
~~~~

!SLIDE

## Filter

~~~~
  :javascript
    alert('test');
~~~~

!SLIDE

# Links

!SLIDE

## Nützliche Links

* HTML5 W3C Standard: http://www.w3.org/TR/html5/
* HTML Validator: http://validator.w3.org
* HTML5-Kompatibilität: http://caniuse.com und http://html5readiness.com
* HAML: http://haml.info

!SLIDE

# Praxis

!SLIDE

## HAML

* Legt ein application-Layout in HAML an
* Legt einen Rails-Controller für die Ausgabe statischer Seiten an
* Überführt Eure statischen Seiten in Rails-Templates
* Konvertiert mindestens eines der Templates in HAML
* Ergänzt eine Navigation im Layout

