# Repetition Textformatierung mit CSS

Zur Vorbereitung des Themas Webfonts wiederholen frischen wir unsere Kenntnisse von CSS bezüglich Schrift auf.

## Übung 1

Es geht darum, gute Schriftgrössen für verschiedene Screens zu bestimmen. Gleichzeitig möchte ich die Aufmerksamkeit auf einige Punkte lenken, die wir im alltäglichen Gebrauch nicht bewusst wahrnehmen.

Wir vergleichen in Zweiergruppen Text auf dem Smartphone und auf dem Laptop: Was ist eine angenehm zu lesende Schriftgrösse, wie lange ist die Zeile?

Wichtig zu wissen: In welcher Grösse Schrift und Bild am Screen ausgegeben wird, ist nicht standardisiert. Durch verschieden aufgelöste Screens und je nach Browser gibt es starke Abweichungen. Das heisst: alles muss immer ausprobiert werden.

### Vorbereiten

* Datei XXXXX auf ZHdK-People-Account laden.
* URL in Laptop- und Smartphone-Browser öffnen.

*Vorsicht: URL mit `http` schreiben, nicht mit `https`. Und: `admin` hat im URL-Pfad nichts zu suchen.*

### Einstellen

Schriftgrösse ändern und Text prüfen (jeweils durch Neuladen der Seite im Browser `cmd r`), bis ihr den Text als angenehm zu lesen empfindet.
Die länge der Zeile interessiert uns im Moment nicht. Am Smartphone ergibt sie sich von alleine, am Laptop ändern wir die Fenstergrösse von Hand.

Es reicht die Regeln für Body zu bestimmen. Der Wert wird 1:1 auf Paragraphen angewendet, Überschriften werden proportional gröser dargestellt. Sonderregeln für  `H1` und `h2` können für diese Übung vernachlässigt werden.

```
body {
    font-size: 16px; /* Für die Übung nehmen wir Pixelwerte. */
    line-height: 1.2; /* Dieser Wert wird mit der Schriftgrösse multipliziert. */
}
```

### Messen

* Abstand zum Laptop beim Lesen
* Abstand zum Smartphone beim Lesen

Diese Werte und die Werte für `font-size` und `line-height` tragen wir in [diese Google Tabelle](https://docs.google.com/spreadsheets/d/1TfsKTSyCyqqWqwmckg6X9kW5HE-dZ68coE1edf_MLFQ/pubhtml) ein.

Um vergleichbare Werte zu erhalten, verwenden wir die gleiche Schriftfamilie und den gleichen Schnitt (Georgia, normal).

Zur eigenen Referenz: Smartphone auf Taschenbuch legen und Schriftgrössen vergleichen.

Verschiedene Schriftgrössen probieren. Anfangen bei 16px, dann Schrittweise bis 12px / 20px oder was auch immer als gut empfunden wird. Dies für Laptop und Phon separat wiederholen.

Tabelle: Name, Laptop, Smartphone, Distanz zum Screen, Schriftgrösse

Übung 2
https://vasilis.nl/nerd/variable-line-height/
http://artequalswork.com/posts/fluid-type/
http://codepen.io/CrocoDillon/pen/fBJxu
https://www.smashingmagazine.com/2016/05/fluid-typography/
https://vimeo.com/160593680
https://github.com/bramstein/postcss-scale

## Übung 3

David Jonathan Ross hat vor kurzem die Schrift Bungee  veröffentlicht. Zur Entspannung versuchen wir, die Schrift herunterzuladen und in eine Website einzubauen.

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
* [Präsentation Bungee](http://typotalks.com/de/videos/hochs-und-tiefs-der-vertikalen-typografie/)
* [Lizenz](http://scripts.sil.org/OFL)

## Hausaufgabe

* CSS-Eigenschaften für Text repetieren.
* Text lesen: Robert Bringhurst, «The 100’000 Character Alphabet» – bis (und mit) 9.3

## Hausaufgabe auf den 21. Oktober

Pixate installieren, vertraut machen mit Grundlagen.

### Links

* [Pixate](http://pixate.com)
* [Introduction](http://help.pixate.com/knowledgebase/articles/461798-1-introduction)
* [Concepts to understand before using Pixate](http://help.pixate.com/knowledgebase/articles/461806-2-high-level-concepts)
* [Video Tutorials](http://www.pixate.com/education/video-tutorials/)
