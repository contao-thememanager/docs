# Module

Im Abschnitt Module können derzeit einige von Contao mitgelieferten Navigationen modifiziert werden.

!!! info

    Da sich einige der nachfolgenden Einstellungen erst ab einem bestimmten Anzeigebereich auswirken, empfehlen sich die
    Navigations-Einstellungen grundsätzlich nur für die Hauptnavigation.

## Navigation

Die nachfolgenden Einstellungen beeinflussen die durch den StyleManager eingestellten Navigations-Einstellungen und
wirken sich nur aus, wenn eine der Optionen `Horizontal`, `Vertical` oder `Vertical (static)` ausgewählt wurde.

!!! info "Die Variable $navigation-behaviour-min-width"

    Aufgrund von mobilen Navigationen wirken sich alle Einstellungen erst ab dem eingestellten Wert der
    `$navigation-behaviour-min-width` aus.

### Layout-Verhalten

`$navigation-behaviour-min-width`

Über diese Einstellung kann das responsive Navigations-Verhalten gesteuert werden, ab wann die eingestellten Optionen
greifen sollen.

!!! info

    Zum Styling der Haupt-Navigation empfiehlt sich die Verwendung dieser Variable, da hiermit der korrekte Media-Query 
    genutzt werden kann:

    **Minimale Breite**
    ```scss
    @media (min-width: $navigation-behaviour-min-width)
    ```

    **Maximale Breite**
    ```scss
    @media (max-width: #{sub($navigation-behaviour-min-width, .02px)})
    ```

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $navigation-behaviour-min-width
    ```
    ```css title="CSS"
    var(--nav-bhr)
    ```
    </div>

### Navigations-Link / Navigations-Item

`$navigation-item-font-size` `$navigation-item-font-weight` `$navigation-item-padding`

Folgende Einstellungen sind für die Navigationslinks verfügbar:

| Option                         | Beschreibung                                                                                                                             |
|--------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| `$navigation-item-font-size`   | Schriftgröße ab dem [Media-Query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries) `$navigation-behaviour-width`      |
| `$navigation-item-font-weight` | Schriftstärke ab dem [Media-Query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries) `$navigation-behaviour-width`     |
| `$navigation-item-padding`     | Padding / Polster ab dem [Media-Query](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries) `$navigation-behaviour-width` |

## Breadcrumb

Dieser Reiter befasst sich mit der Einstellung des Trennzeichens (z. B. `›`) einer Brotkrümel-Navigation, sodass diese
wie folgt aussehen kann:

```Home › Unterseite › Blog```

### Trennzeichen

`$breadcrumb-separator` `$breadcrumb-separator-color` `$breadcrumb-separator-font-family`

Folgende Einstellungen sind für Trennzeichen verfügbar:

| Option                              | Beschreibung                                                                                                         |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| `$breadcrumb-separator`             | Trennzeichen, welches als `content` eingefügt wird. Wichtig ist, dass diese in Anführungszeichen stehen ('' oder "") |
| `$breadcrumb-separator-color`       | Farbe des Trennzeichens                                                                                              |
| `$breadcrumb-separator-font-family` | Schriftart des Trennzeichens                                                                                         |

!!! warning "$breadcrumb-separator-font-family"

    Diese Einstellung sollte **nur überschrieben werden**, falls eine weitere Icon-Schriftart als die im
    [Theme eingestellte](../icon-set.md) verwendet wird.
