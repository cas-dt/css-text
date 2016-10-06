# Tag 2 – ergänzende Themen

## OpenType features in CSS

OpenType-Features lassen sich aus Stylesheets ansprechen. Es gibt zwei Möglichkeiten (‘high-’ und ‘low-level’) dafür, wer es genau wissen will, sei auf [diesen Artikel](https://www.typotheque.com/articles/opentype_features_in_css)), erschienen bei Typotheque verwiesen.

### Beispiel Kapitälchen

```
p { /* high-level */
    font-variant: small-caps;
}

/* low-level */
   font-feature-settings: 'smcp'; 
}
```

### Beispiel Medievalziffern

```
p { /* high-level */
    font-variant-numeric: oldstyle-nums;
}

p { /* low-level */
    font-feature-settings: 'onum';
}
```

## Faux bold

Dies ist wahrscheinlich der häufigste Fehler, der im Zusammenhang mit Webfonts gemacht wird.

Überschriften (HTML-Tags h1–h6) werden vom Browser automatisch fett gezeichnet. Gibt es nur einen Schnitt und keine Definition des Schriftgewichtes im Stylesheet, so zeichnen Browser auch im Jahre 2016 noch eine Umrisslinie um die Zeichen. Dies ist ein Punkt, den Front End Entwickler selten von sich aus bemerken, darum immer prüfen.

```
h2 { font-weight: normal; }
```

Es gibt dieses Problem natürlich auch im Zusammenhang mit falschen Kursiven. Technische Details gibt es in diesem [A-List-Apart-Artikel](http://alistapart.com/article/say-no-to-faux-bold).

## Links

### Technisches

* [Linotype – Webfont Tutorial](https://www.linotype.com/de/7027/webfonts-tutorial.html)
* [MDN – CSS Fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts)
* [FontFont – OpenType User Guide](https://www.fontfont.com/staticcontent/downloads/FF_OT_User_Guide.pdf)
* [Microsoft – OpenType Feature List](https://www.microsoft.com/typography/otspec/featurelist.htm)
* [MSDN – Using the Whole Font](https://blogs.msdn.microsoft.com/ie/2012/01/09/css-corner-using-the-whole-font/)
* [Prevent hotlinking with a .htaccess file](https://mediatemple.net/community/products/dv/204644230/prevent-hotlinking-with-a-htaccess-file)

### Nicht so Technisches

* [Gerry Leonidas – Typefaces for Screens](https://vimeo.com/108336615)
* [Typewolf](http://typewolf.com)

## Webfonts die Herr Renner im Oktober 2016 interessant fand

* [Fira sans](https://mozilla.github.io/Fira/)
* [Nitti Mostro](http://nittimostro.webtype.com/)
* [Action](http://action.commercialtype.com/)
* [Input](http://input.fontbureau.com/info/) <— nicht primär ein Webfont
