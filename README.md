# Repetition Textformatierung mit CSS

Zur Vorbereitung des Themas Webfonts frischen wir unsere Kenntnisse über CSS bezüglich Schrift auf.

## Übung 1: Vermassung von Schrift am Bildschirm

Es geht darum, gute Schriftgrössen für verschiedene Screens zu bestimmen. Gleichzeitig möchte ich die Aufmerksamkeit auf einige Punkte lenken, die wir im alltäglichen Gebrauch nicht bewusst wahrnehmen.

Wir vergleichen in Zweiergruppen Text auf dem Smartphone und auf dem Laptop: Was ist eine angenehm zu lesende Schriftgrösse, wie lange ist die Zeile?

Wichtig zu wissen: In welcher Grösse Schrift und Bild am Screen ausgegeben wird, ist nicht standardisiert. Durch verschieden aufgelöste Screens und je nach Browser gibt es starke Abweichungen. Das heisst: alles muss immer ausprobiert werden.

### Vorbereiten

* Datei XXXXX auf ZHdK-People-Account laden.
* URL in Laptop- und Smartphone-Browser öffnen.

*Vorsicht: URL mit `http` schreiben, nicht mit `https`. Und: `admin` hat im URL-Pfad nichts zu suchen.*

### Einstellen

Schriftgrösse ändern und Text prüfen (jeweils durch Neuladen der Seite im Browser `cmd r`), bis ihr den Text als angenehm zu lesen empfindet. Die länge der Zeile interessiert uns im Moment nicht. Am Smartphone ergibt sie sich von alleine, am Laptop ändern wir die Fenstergrösse von Hand.

Es reicht, die Eigenschaften für `<body>` zu bestimmen. Der Werte werden 1:1 auf Paragraphen angewendet, Überschriften werden proportional gröser dargestellt. Sonderregeln für  `H1` und `h2` können für diese Übung vernachlässigt werden.

```
body {
    font-size: 16px; /* Für die Übung nehmen wir Pixelwerte. */
    line-height: 1.2; /* Dieser Wert wird mit der Schriftgrösse multipliziert. */
}
```

### Messen

In Zweiergruppen: LeserIn versucht entspannt einige Abschnitte der Menschenrechtskonvention zu lesen. PartnerIn misst Distanz zum Screen.

* Grösse in Punkt am Screen (mit Typometer)
* Abstand zum Laptop beim Lesen
* Abstand zum Smartphone beim Lesen

Diese Werte und jene für `font-size` und `line-height` tragen wir in [diese Google Tabelle](https://docs.google.com/spreadsheets/d/1TfsKTSyCyqqWqwmckg6X9kW5HE-dZ68coE1edf_MLFQ/pubhtml) ein.

Um vergleichbare Werte zu erhalten, verwenden wir die gleiche Schriftfamilie und den gleichen Schnitt (Georgia, normal).

Tipp zum Einschätzen der Schriftgrösse auf Smartphones: Smartphon auf Taschebuch legen und vergleichen (Quelle: [Interview mit Erik Blokland](https://www.youtube.com/watch?v=EDG14YhYrGw).

## Übung 2: Schriftgrösse nach Viewport, ohne media query

Die länge der Zeile lässt sich der breite des Viewports anpassen, indem im Stylesheet der Eigenschaft *width* ein Prozentwert zugeordnet wird (oder indem gar keine Angabe gemacht wird).

Die Länge der Zeile wird für einen längeren Text in Abhängigkeit der durchschnittlichen Menge an Wörtern gewählt, die darin Platz finden sollen. So können wir davon ausgehen, dass der Text angenehm zu lesen ist. Soweit gibt es kein Problem: Wir können mit *min-width* und *max-width* eine minimale und maximale Spaltenbreite definieren.

Kompliziert wird es, wenn die Schriftgrösse sich der Grösse des Viewports anpassen soll. Solange wir nur zwischen klein (mobile) und gross (alles andere) unterscheiden, geht es noch. Aber diese grobe Einteilung führt wahrscheinlich zu unbefriedigenden Ergebnissen auf Bildschirmen, die nicht klein sind, aber den Mittelwert unter- oder überschreiten.

Das definieren von Zwischenschritten ist aufwendig: Wie viele Breakpoints es gibt und wo diese eingerichtet werden müssen, lässt sich nur durch ausprobieren an verschiednen Geräten ermitteln. Aber wieviele und welche Geräte prüft man? Was ist mit den Gewohnheiten der Benutzer?

Vor diesem Hintergrund probieren wir einen Ansatz aus, der die Schriftgrösse in Verhältnis zur Viewportbreite bringt. Dazu muss gesagt werden, dass es sich um eine experimentelle Methode handelt, deren praktischer Nutzen fraglich ist (siehe Links). Es illustriert aber sowohl die Möglichkeiten als auch die Limitierungen der gegenwärtigen Technologie. Fakt ist, dass die bestehenden Möglichkeiten von CSS nach wie vor unzureichend sind, auch wenn sich in den letzten Jahren viel getan hat. Um über neue Entwicklungen informiert zu werden, lohnt es sich, Leuten wie [Erik Blokland](@letterror), [Just van Rossum](@justvanrossum), [Tim](@nicewebtype) [Brown](@timbrown), [Bram Stein](@bram_stein), [Nina Stössinger](@ninastoessinger) und [Nick Sherman](@NickSherman) per Twitter zu folgen.

```
p {
    font-size: calc(1em + 1vw);
}
```

### Viewport Units: vw, vh, vmax und vim

Die sog. ‘Viewport Units’ sind eine neue Masseinheit in CSS. Sie beziehen sich auf die Grösse des Viewports: *vw* steht für ‘viewport width’ (Fensterbreite), *vh* für ‘viewport height’ (Fensterhöhe), *vmin* wird mit *vw* oder *vh* ersetzt, je nachdem welcher Wert kleiner ist, *vmax* mit dem jeweils grösseren Wert. Dem Wert wird eine ganze Zahl zwischen 1 und 100 vorangestellt, 1*vw* ist 1% der Fensterbreite, 100*vw* ist die ganze Breite des Viewports.

### calc

Seit kurzem gibt es die Möglichkeit, einer CSS-Eigenschaft statt eines numerischen Wertes eine Formel zuzuordnen.

### Links

* [Vasilis van Gemert – Variable line-height](https://vasilis.nl/nerd/variable-line-height/)
* [Nathan Ford – Fluid typography with viewport units](http://artequalswork.com/posts/fluid-type/)
* [Dillon de Voor – Mixing vw and vh in font-size](http://codepen.io/CrocoDillon/pen/fBJxu)
* [Smashing Magazine – Truly Fluid Typography With vh And vw Units](https://www.smashingmagazine.com/2016/05/fluid-typography/)
* [Video: Vasilis van Gemert – Look, no media queries](https://vimeo.com/160593680)
* [Video: Tim Brown – Typesetting Body Text for the Web](https://vimeo.com/156203722)
* [Bram Stein – PostCSS plugin to scale values](https://github.com/bramstein/postcss-scale)
* [Mozilla Developer Network – Calc](https://developer.mozilla.org/en-US/docs/Web/CSS/calc)

Zu sagen, CSS biete zu wenig Möglichkeiten, greift zu kurz. Jenen, die mehr über die technischen Herausforderungen im Zusammenhang mit der Darstellung von Schrift am Screen wissen möchten, empfehle ich Nick Shermans Präsentation [Variable Fonts for Responsive Design](https://vimeo.com/123813231).

* [Size Calculator](https://sizecalc.com/)


## Übung 3: Unser erster Webfont

David Jonathan Ross hat vor kurzem die Schrift Bungee unter einer Open Source Lizenz veröffentlicht (und ausserdem als Google Font). Zur Entspannung versuchen wir, die Schrift herunterzuladen und in eine Website einzubauen.

Es geht nicht darum, zu verstehen, was wie funktioniert, sondern darum, das Ding zum Laufen zu bringen.

Es braucht zwei CSS Eigenschaften, um Text von oben nach unten zu schreiben: Eine für die vertikale Ausrichtung der Zeile, eine für die vertikale Ausrichtung der Buchstaben.

```
p {
    writing-mode: vertical-rl
    text-orientation: upright
}
```

Der Font ist ausführlich dokumentiert (siehe Links).

* [David Jonathan Ross](https://djr.com/)
* [Bungee](https://github.com/djrrb/Bungee)
* [Bungee Dokumentation](https://github.com/djrrb/Bungee/tree/master/documentation)
* [Bungee Dokumentation Web](https://github.com/djrrb/Bungee/blob/master/documentation/3-vertical-text.md#on-the-web)
* [Bungee.js – Script zur Konfiguration der Schnitte etc.](https://github.com/djrrb/Bungee/tree/master/resources/web)
* [Video: Präsentation Bungee](http://typotalks.com/de/videos/hochs-und-tiefs-der-vertikalen-typografie/)
* [Lizenz](http://scripts.sil.org/OFL)

## Hausaufgabe

* CSS-Eigenschaften für Text repetieren.
* Text lesen: Robert Bringhurst, «The 100’000 Character Alphabet» – bis (und mit) 9.3
* Recherchieren: ‘multiple master’, ‘optical size’, ‘open type features’ – Anton Studer wird das kurz streifen. Es schadet aber nicht, das vorzubereiten.

## Hausaufgabe auf den 21. Oktober

Pixate installieren, vertraut machen mit Grundlagen.

### Links

* [Pixate](http://pixate.com)
* [Introduction](http://help.pixate.com/knowledgebase/articles/461798-1-introduction)
* [Concepts to understand before using Pixate](http://help.pixate.com/knowledgebase/articles/461806-2-high-level-concepts)
* [Video Tutorials](http://www.pixate.com/education/video-tutorials/)
