---
title: config.yaml
---

# ThemeManager Optionen konfigurieren

Über die `config/config.yaml` können bestimmte Bereiche des ThemeManagers modifiziert werden, sodass beispielsweise
Headline Styles ergänzt oder sogar entfernt werden können

### Headline Styles ergänzen / entfernen

Das nachfolgende Beispiel ergänzt `Foobar` mit den Klassen `foo` und `bar` innerhalb der Headline Styles.
Bitte beachten Sie, dass mit dem Präfix `+` Optionen ergänzt werden, mit `-` werden Optionen entfernt.

```yaml title="config/config.yaml"
contao_theme_manager_core:
    headline:
        styles:
            +foo bar: Foobar
```

!!! info "CSS wird nicht hinzugefügt"

    Für die neu hinzugefügten Headline-Styles muss das CSS selber ergänzt werden.

### Headline Einheiten ergänzen / entfernen

Die zur Auswahl stehenden Headline-Einheiten sind derzeit `h1` - `h6`, `p`, `div`, `span` und `strong`. Im nachfolgenden
Beispiel wird die Einheit `h6` entfernt, zusätzlich `abbr` hinzugefügt:

```yaml title="config/config.yaml"
contao_theme_manager_core:
    headline:
        units:
            -h6
            +abbr
```

### CSS-Einheiten in der Theme-Konfiguration

Ähnlich der Einheiten und Styles können mit dem Präfix `+` Optionen hinzugefügt werden, mit `-` entfernt werden.
Diese Einheiten stehen nachfolgend in der Theme-Konfiguration zur Verfügung.

```yaml title="config/config.yaml"
contao_theme_manager_core:
    config:
        css_units:
            +%
            +em
```

!!! danger "px oder rem sollten nicht entfernt werden"

    Es wird nicht empfohlen Optionen zu entfernen, da `px` und `rem` im Framework genutzt werden.

