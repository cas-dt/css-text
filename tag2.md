# Tag 2 – ergänzende Themen

## OpenType features in CSS

OpenType-Features lassen sich aus Stylesheets ansprechen. Es gibt zwei Möglichkeiten (‘high-’ und ‘klow-level’ dafür, wer es genau wissen will, sei auf den unten angegebenen Artikel von Typotheque verwiesen.

### Beispiel Medievalziffern

```
p { /* high-level */
    font-variant-numeric: oldstyle-nums;
}

p { /* low-level */
    font-feature-settings: 'onum';
}
```

### Beispiel Kapitälchen

```
p { /* high-level */
    font-variant: small-caps;
}

/* low-level */
   font-feature-settings: 'smcp'; 
}
```

* [Typotheque – OpenType features in CSS](https://www.typotheque.com/articles/opentype_features_in_css)

## Faux bold

Dies ist der häufigste Fehler, der im Zusammenhang mit Webfonts gemacht wird.

Überschriften (HTML-Tags h1–h6) werden vom Browser automatisch fett gezeichnet. Gibt es nur einen Schnitt und wird im Stylesheet keine Definition des Schriftgewichtes, so zeichnen Browser auch ad. 2016 eine Umrisslinie um die Zeichen.

## Links

### Technisches

* [Linotype – Webfont Tutorial](https://www.linotype.com/de/7027/webfonts-tutorial.html)
* [MDN – CSS Fonts](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Fonts)
* [FontFont – OpenType User Guide](https://www.fontfont.com/staticcontent/downloads/FF_OT_User_Guide.pdf)
* [Microsoft – OpenType Feature List](https://www.microsoft.com/typography/otspec/featurelist.htm)
* [MSDN – Using the Whole Font](https://blogs.msdn.microsoft.com/ie/2012/01/09/css-corner-using-the-whole-font/)

### Nicht so technisches

* [Gerry Leonidas – Typefaces for Screens](https://vimeo.com/108336615)
* [Typewolf](http://typewolf.com)

## Webfonts die Herr Renner im Oktober 2016 interessant fand

* [Fira sans](https://mozilla.github.io/Fira/)
* [Input](http://input.fontbureau.com/info/) <— und es ist nicht einmal ein Webfont
