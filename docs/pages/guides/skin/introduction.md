---
title: Einleitung
---

# Einleitung

Der Contao ThemeManager stellt lediglich das Grundgerüst für eine Webseite bereit und sollte nicht als alleinige Basis
für den Webseitenaufbau betrachtet werden. In den folgenden Abschnitten wird darauf eingegangen, wie du dein eigenes
Theme erstellen kannst und auf mögliche Schwierigkeiten, die dir dabei begegnen könnten.

Zudem erhältst du hier weitere Ratschläge, Tipps und hilfreiche Hinweise, die dir während des gesamten Prozesses der
Theme-Entwicklung nützlich sein können.

## Theme-Compiler

Eines der Tools des Contao ThemeManager ist
das [contao-theme-compiler-bundle](https://github.com/oveleon/contao-theme-compiler-bundle), welches für das
Zusammenfassen der SCSS-Dateien zuständig ist. Er basiert auf [SCSSPHP](https://github.com/scssphp/scssphp), welches
auch Verwendung im Contao-Core findet.

Die Bestandteile des Frameworks und deiner Themes werden immer im Contao-System (auf dem Server) generiert. Dies
ermöglicht Vorteile wie den Zugriff auf die Theme-Konfiguration, sowie den Kompilierprozess.

!!! info "Eigene Filewatcher"

    Niemand ist dazu gezwungen, den internen Compiler zu verwenden. Du kannst deine Theme-Dateien weiterhin lokal
    kompilieren und als CSS einbinden. Du kannst hierbei aber nicht mehr die durch den Theme-Manager bereitgestellten
    SCSS-Variablen nutzen und musst auf die verfügbaren custom properties ausweichen.

## Best-Practice bei der Nutzung von SCSSPHP

SCSSPHP erlaubt derzeit noch kein Dartsass 2.0, sodass neue Funktionen wie `@layer`, `@extend`, `@forward` und andere
Features nicht möglich sind. Grundsätzlich gilt, dass der Compiler mit LibSass und neueren Sachen umgehen kann.

Sollte es zu Fehlern beim Kompilieren kommen, schaue bitte in den [Issues](https://github.com/scssphp/scssphp/issues)
von SCSSPHP nach.

Kennst du SCSS noch nicht, empfehlen wir die offizielle Dokumentation zu lesen: https://sass-lang.com/documentation/.

### Interpolation von SCSS-Variablen

Bei der Verwendung von SCSS-Variablen wie z. B. bei der Deklaration von
[CSS custom properties](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties), 
kann es sein, dass diese nicht vom Compiler erkannt werden und im Klartext ausgegeben werden.
Um dies zu verhindern, musst du diese Variablen immer mit `#{MY_VARIABLE}` interpolieren.

```scss
$foo: #f00;

.bar {
  --baz: #{$foo}
}
```

### Escaping von `quoted` Strings durch Interpolation

Verwendet man die oben erwähnte Interpolation mit SCSS-Variablen, welche Anführungszeichen erhalten, werden diese durch
SASS entfernt: https://sass-lang.com/documentation/interpolation/#quoted-strings. `$font-family: "Custom", Arial` wird
hierbei zu `Custom, Arial`. Dies kann mit der nachfolgenden Anweisung umgangen werden.
```scss
#{inspect($font-family)};
```

### Verwendung von `@at-root`

Die Nutzung von `&` kann in SCSS verwendet werden, damit dein CSS übersichtlicher und strukturierter geschrieben werden
kann. Wichtig ist hierbei, dass SCSS valide geschrieben wird und die Verwendung durch SCSSPHP erlaubt wird.

```scss title="Falsche Verwendung"
body {
  .myClass& {
    content: 'myInvalidCSS'
  }
}
```
```scss title="Valide Verwendung von @at-root"
body {
  @at-root #{selector-append('.myClass', &)} {
    content: 'myValidCss'
  }
}
```
