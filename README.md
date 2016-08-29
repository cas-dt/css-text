# Repetition Textformatierung mit CSS

Zur Vorbereitung des Themas Webfonts frischen wir unsere Kenntnisse über CSS bezüglich Schrift auf.

## Terminologie

Eine unvollständige Liste von Begriffen, die im Zusammenhang mit dem Thema Schrift am Screen verstanden werden müssen.

* Font ≠ Schrift (-familie) /  Schnitt
* Schriftgrösse, Geviert
* Grundlinie, Oberlänge, Unterlänge, x-Höhe, Versalhöhe
* line-height, Zeilenhöhe, Durchschuss
* px, em, Vererbung von em
* Kerning, spationieren, ausgleichen, sperren
* Webfonts / Websafe Fonts
* Zeichen ≠ Glyphe

## Übung 1: Vermassung von Schrift am Bildschirm

Es geht darum, gute Schriftgrössen für verschiedene Screens zu bestimmen. Gleichzeitig möchte ich die Aufmerksamkeit auf einige Punkte lenken, die wir im alltäglichen Gebrauch nicht bewusst wahrnehmen.

Wir vergleichen in Zweiergruppen Text auf dem Smartphone und auf dem Laptop: Was ist eine angenehm zu lesende Schriftgrösse, wie lange ist die Zeile?

Wichtig zu wissen: In welcher Grösse Schrift und Bild am Screen ausgegeben wird, ist (noch) nicht standardisiert. Durch verschieden aufgelöste Screens, durch Umrechnung der Auflösug durch Treiber/Betriebssystem etc. gibt es starke Abweichungen. Das heisst: alles muss immer ausprobiert werden.

### Vorbereiten

* Datei font-size/index.html auf ZHdK-People-Account laden.
* URL in Laptop- und Smartphone-Browser öffnen.

*Vorsicht: URL mit `http` schreiben, nicht mit `https`. Und: `admin` hat im URL-Pfad nichts zu suchen.*

### Einstellen

Schriftgrösse und Durchschuss einstellen und Text prüfen (jeweils durch Neuladen der Seite im Browser `cmd r`), bis ihr den Text als angenehm zu lesen empfindet.

Ich habe die breite der Spalte auf 30em limitiert – ihr könnt diesen Wert nach Belieben einstellen. Am Smartphone ergibt sich die Spalte von alleine. Wir betrachten nur die **vertikale Ausrichtung**.

Wir interessieren uns nur für Text innerhlab von `<p>` Tags. Ihr könnt natürlich gerne auch `H1` und `h2` formatieren.

```
p {
    font-size: 16px;  /* Für die Übung nehmen wir Pixelwerte. */
    line-height: 1.2; /* Dieser Wert wird mit der Schriftgrösse multipliziert. */
}
```

### Messen

In Zweiergruppen: LeserIn versucht, entspannt einige Abschnitte der Menschenrechtskonvention zu lesen. PartnerIn misst Distanz zum Screen.

* Grösse in Punkt am Screen (mit Typometer)
* Abstand zum Laptop beim Lesen
* Abstand zum Smartphone beim Lesen

Diese Werte und jene für `font-size` und `line-height` in [diese Google Tabelle](https://docs.google.com/spreadsheets/d/1TfsKTSyCyqqWqwmckg6X9kW5HE-dZ68coE1edf_MLFQ/pubhtml) eintragen.

Um vergleichbare Werte zu erhalten, verwenden wir die gleiche Schriftfamilie und den gleichen Schnitt (Georgia normal).

## Übung 2: Schriftgrösse nach Viewport, ohne media query

Die länge der Zeile lässt sich der breite des Viewports anpassen, indem im Stylesheet der Eigenschaft *width* ein Prozentwert zugeordnet wird (oder indem gar keine Angabe gemacht wird).

Wir wissen: Die Länge der Zeile wird für einen längeren Text in Abhängigkeit zur durchschnittlichen Menge an Wörtern/Zeichen gewählt, die darin Platz finden sollen. So können wir davon ausgehen, dass der Text angenehm zu lesen ist. Soweit gibt es kein Problem: Wir können mit *min-width* und *max-width* eine minimale und maximale Spaltenbreite definieren.

Kompliziert wird es, wenn die Schriftgrösse sich der Grösse des Viewports anpassen soll. Solange wir nur zwischen klein (mobile) und gross (alles andere) unterscheiden, geht es noch. Aber diese grobe Einteilung führt wahrscheinlich zu unbefriedigenden Ergebnissen an Bildschirmen, die nicht klein sind, aber den Mittelwert unter- oder überschreiten.

Das definieren von Zwischenschritten ist aufwendig: Wie viele Breakpoints es gibt und wo diese eingerichtet werden müssen, lässt sich nur durch Ausprobieren an verschiednen Geräten ermitteln. Aber wieviele und welche Geräte prüft man? Dieses Thema ist noch längst nicht befriedigend gelöst.

Vor diesem Hintergrund probieren wir einen Ansatz aus, der die Schriftgrösse in Verhältnis zur Breite des Viewport bringt. Dazu muss gesagt werden, dass es sich um eine experimentelle Methode handelt, deren praktischer Nutzen fraglich ist (siehe Links). Es mag dazu dienen, sowohl die Möglichkeiten als auch die Limitierungen der gegenwärtigen Technologie zu illustrieren – vielleicht auch den verzweifelten Eifer, mit dem nach Lösungen gesucht wird, egal wie abwegig. Fakt ist, dass die bestehenden Möglichkeiten von CSS nach wie vor unzureichend sind, auch wenn sich in den letzten Jahren viel getan hat. Um über neue Entwicklungen informiert zu werden, lohnt es sich, Leuten wie [Erik Blokland](@letterror), [Just van Rossum](@justvanrossum), [Tim](@nicewebtype) [Brown](@timbrown), [Bram Stein](@bram_stein), [Nina Stössinger](@ninastoessinger) und [Nick Sherman](@NickSherman) per Twitter zu folgen.

```
p {
    font-size: calc(1em + 1vw);
}
```

### Viewport Units: vw, vh, vmax und vim

Die sogenannten ‘Viewport Units’ sind eine neue Masseinheit in CSS. Sie beziehen sich auf die Grösse des Viewports: *vw* steht für ‘viewport width’ (Fensterbreite), *vh* für ‘viewport height’ (Fensterhöhe), *vmin* wird mit *vw* oder *vh* ersetzt, je nachdem welcher Wert kleiner ist, *vmax* mit dem jeweils grösseren Wert. Dem Wert wird eine ganze Zahl zwischen 1 und 100 vorangestellt, 1*vw* ist 1% der Fensterbreite, 100*vw* ist die ganze Breite des Viewports.

### calc

Seit Kurzem gibt es die Möglichkeit, einer CSS-Eigenschaft statt eines fixen Wertes eine Funktion zuzuordnen, die einen Wert aufgrund von Variablen errechnet.

```
#container {
    width: calc(100% - 5em);
}
```

Für eine detaillierte Dokumentation: [MDN – calc()](https://developer.mozilla.org/de/docs/Web/CSS/calc)

### Links

* [Vasilis van Gemert – Variable line-height](https://vasilis.nl/nerd/variable-line-height/)
* [Nathan Ford – Fluid typography with viewport units](http://artequalswork.com/posts/fluid-type/)
* [Dillon de Voor – Mixing vw and vh in font-size](http://codepen.io/CrocoDillon/pen/fBJxu)
* [Smashing Magazine – Truly Fluid Typography With vh And vw Units](https://www.smashingmagazine.com/2016/05/fluid-typography/)
* [Tim Brown: Flexible typography with CSS locks](http://blog.typekit.com/2016/08/17/flexible-typography-with-css-locks/)
* [Video: Vasilis van Gemert – Look, no media queries](https://vimeo.com/160593680)
* [Video: Tim Brown – Typesetting Body Text for the Web](https://vimeo.com/156203722)
* [Bram Stein – PostCSS plugin to scale values](https://github.com/bramstein/postcss-scale)
* [Mozilla Developer Network – Calc](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)

Zu sagen, CSS biete zu wenig Möglichkeiten, greift etwas kurz. Jenen, die mehr über die technischen Herausforderungen im Zusammenhang mit der Darstellung von Schrift am Screen wissen möchten, empfehle ich Nick Shermans Präsentation [Variable Fonts for Responsive Design](https://vimeo.com/123813231).

* [Size Calculator](https://sizecalc.com/)

## Übung 3: Unser erster Webfont

David Jonathan Ross hat kürzlich die Schrift Bungee unter einer Open Source Lizenz veröffentlicht (und ausserdem als Google Font). Zur Entspannung versuchen wir, die Schrift herunterzuladen und in eine Website einzubauen.

```
@font-face {
    font-family: 'my font';
    src: url('ordner/datei.woff2') format('woff2'),
    src: url('ordner/datei.woff') format('woff');

p { font-family: 'my font', helvetica, sans-serif;
}
```

Mit @font-face wird Name für den zu verwendenden Font definiert. Dieser kann frei gewählt werden.

Dazu kommt der Pfad zur Datei, die den Font enthält und die Angabe des Formats dieser Datei. Wenn ältere Browserversionen unterstützt serden müssen, können verschiedene Quellen mit Dateien in unterschiedlichen Fomraten angegeben werden.

### Vertikal laufender Text

Für den Einsatz der Bungee müssen wir im Stylesheet die Orientierung der Zeile und der Buchstaben definieren.

```
p {
    writing-mode: vertical-rl
    text-orientation: upright
}
```

Der Font ist ausführlich dokumentiert (siehe Links).

## OpenType Features in Keynote

Was ihr schon immer wissen wolltet: In Keynote können OpenType Features eingesetzt werden, sie sind nur [etwas versteckt](https://twitter.com/marksimonson/status/654836119448653824).

Text auswählen, `cmd t`, Zahnrad, «Typographie …» – voilà.

* [David Jonathan Ross](https://djr.com/)
* [Bungee](https://github.com/djrrb/Bungee)
* [Bungee Dokumentation](https://github.com/djrrb/Bungee/tree/master/documentation)
* [Bungee Dokumentation Web](https://github.com/djrrb/Bungee/blob/master/documentation/3-vertical-text.md#on-the-web)
* [Bungee.js – Script zur Konfiguration der Schnitte etc.](https://github.com/djrrb/Bungee/tree/master/resources/web)
* [Video: Präsentation Bungee](http://typotalks.com/de/videos/hochs-und-tiefs-der-vertikalen-typografie/)
* [Lizenz](http://scripts.sil.org/OFL)

## Silbentrennung mit HTML/CSS

Die Technologie zur Silbentrennung ist noch nicht sehr ausgereift: Wenig Browser können es, und die, die es tun, können es nur in wenigen Sprachen.

```
<html lang="de"> oder <p lang="en"> <!-- Sprache definieren -->

p {
    hyphens: auto;             /* schaltet Silbentrennung an */
    -webkit-hyphens: auto;     /* für Safari/Chrome          */
    -ms-hyphens: auto;         /* für Microsoft Browser      */
}
```

### Manuelle Silbentrennung

Durch das Einfügen der «HTML-entities» `&hyphen;` oder `&shy;` lässt sich von Hand einstellen, wo ein Wort getrennt werden soll. Zustätzlich ist in CSS noch die Angabe `hyphen: manual;` (oder auto) notwendig.

### Notlösung

```
    overflow-wrap: break-word; /* bricht überlange Wörter um */
```

# Lings Silbentrennung

* [MDN – CSS Eigenschaft ‘hyphens’](https://developer.mozilla.org/en-US/docs/Web/CSS/hyphens)
* [MDN – Umbruch überlanger Wörter](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow-wrap)
* [HTML Entities](https://dev.w3.org/html5/html-author/charref
)

## Hausaufgabe auf den 23. September

* Generell auf Schriften im Web achten. Mit den *Dev Tools* nachschauen, was es ist.
* CSS-Eigenschaften für Text repetieren, bis es reicht, z.B. in [CodePen](http://codepen.io/).
* Text lesen: Robert Bringhurst, «The State of the Art» – bis (und mit) 9.3 «Size, Color and Scale»
* Den Links auf dieser Seite folgen.

Der Unterschied zwischen ASCII und Unicode sollte verstanden werden, ebenso, was der Unterschide zwischen einem Zeichen und einer Glyphe. 9.2 und 9.3 behandeln unterschiedliche Dateiformate für Fonts. Anton Studer wird diese ebenfalls ansprechen. Es schadet aber sicher nicht, das vorzubereiten.

## Hausaufgabe auf den 8. Oktober

Pixate installieren, vertraut machen mit den Grundlagen.

### Pixate Links

* [Pixate](http://pixate.com)
* [Introduction](http://help.pixate.com/knowledgebase/articles/461798-1-introduction)
* [Concepts to understand before using Pixate](http://help.pixate.com/knowledgebase/articles/461806-2-high-level-concepts)
* [Video Tutorials](http://www.pixate.com/education/video-tutorials/)

## Last but not least (liest?)

Ein Tipp zum Einschätzen der Schriftgrösse auf Smartphones: Smartphone auf Taschebuch legen und vergleichen (Quelle: [Interview mit Erik Blokland](https://www.youtube.com/watch?v=EDG14YhYrGw)).
