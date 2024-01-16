---
icon: octicons/table-24
---

# Komponenten

Die derzeitigen Komponenten-Einstellungen des ThemeManagers beschreiben derzeit das Aussehen von Inhaltselementen,
Modulen, Tabellen sowie der visuellen Trennung von zwei Artikeln.

## Box

Im eigentlichen Sinne auch als `Card` oder `Kachel` bekannt, gibt es die `box` Eigenschaft für die in den StyleManager
verfügbaren Gruppen `Components` und `Elements`.

!!! info "Erklärungen zu StyleManager Gruppen"

    Mehr zu den StyleManager-Gruppen `Global`, `Components` und `Elements` kann
    [hier](../backgrounds.md#exkurs-global-component-und-element) nachgelasen werden.

Wird im StyleManager-Reiter `Layout` eine der Optionen unter `Box` aktiviert, werden der Hintergrund un der Rahmen der
Komponente bzw. der sich darin befindlichen Elemente auf die hier konfigurierten CSS-Einstellungen geändert.

### Exkurs: Padding von Components und Elements

Wird die Option `box` gesetzt, so greifen automatisch `$top-bottom-padding-small` und `$left-right-padding-small`, die
in [Abstände (Innen)](layout.md#abstände-innen) eingestellt werden können.

Innerhalb von `Components` und `Elements` kann hierbei das Padding je [Breakpoint](layout.md#breakpoints) eingestellt
werden.

Die Option `Reset` führt dazu, dass das der Innenabstand aufgehoben wird, diese Option empfiehlt sich jedoch nur für
Bilder. Bild-Text-Elemente haben eine weitere Einstellung um das Bild an den Rahmen zu binden, sodass der Text mit dem
Padding versehen wird.

!!! warning

    Abweichend der Einstellungen des [äußeren Abstands (Margin)](layout.md#abstände-außen), gelten für die
    Padding-Einstellung alle Seiten.

### Hintergrundfarbe

`$boxed-background-color`

Diese Einstellung beeinflusst die Hintergrundfarbe (`background-color`) der Kachel für folgende StyleManager-Gruppen:

**Components**

    ```css
    .box > .inside
    ```

**Elements**

    ```css
    .box-list .item > .inside
    ```

Der Standardwert ist hier die Hintergrundfarbe des `<body>` sofern nicht anders konfiguriert.

!!! tip "Weitere Hintergrundfarben in Components und Elements"

    Die hier gesetzte Hintergrundfarbe kann jederzeit durch eine Hintergrundfarbe innerhalb der `Components` und
    `Elements`-Gruppen überschrieben werden. Wie dies passiert kann im Kapitel
    [Hintergründe](../backgrounds.md#weitere-optionen) nachgelesen werden können.

    Wird eine dunkle Hintergrundfarbe ausgewählt, kann die Text-Farbe der Listen-Items über 
    `Components > Text > Text-Color`, die der Überschrift über `Global > Headlines > Text-Color` (oder im Artikel)
    eingestellt werden. 

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $boxed-background-color
    ```
    
    ```css title="CSS"
    // Components (.box)
    var(--b-bg)

    // Elements (.box-list)
    var(--i-bg)
    ```
    </div>

### Rahmen

`$boxed-border-color` `$boxed-border-radius` `$boxed-border-width` `$boxed-border-style`

Bekannt als `border`, stehen uns hierbei die folgenden Einstellungen zur Verfügung, sodass der Rahmen der Kachel
beeinflusst werden kann.

<a style="display: block; background: var(--md-code-bg-color); text-align: center; margin: 1em 0; padding: 25px; border: solid 1px var(--md-primary-fg-color)" title="Rahmenfarbe" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-color">
  Rahmenfarbe</a>
<a style="display: block; background: var(--md-code-bg-color); text-align: center; margin: 1em 0; padding: 25px; border: solid 1px var(--md-primary-fg-color); border-radius: 50px" title="Rahmenradius" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius">
  Rahmenradius</a>
<a style="display: block; background: var(--md-code-bg-color); text-align: center; margin: 1em 0; padding: 25px; border: solid 5px var(--md-primary-fg-color)" title="Rahmenbreite" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-width">
  Rahmenbreite</a>
<a style="display: block; background: var(--md-code-bg-color); text-align: center; margin: 1em 0; padding: 25px; border: dotted 5px var(--md-primary-fg-color)" title="Rahmenstil" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-style">
  Rahmenstil</a>

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $boxed-border-width
    $boxed-border-style
    $boxed-border-color
    $boxed-border-radius
    ```
    
    ```css title="CSS"
    var(--b-bdr-wdth)
    var(--b-bdr-style)
    var(--b-bdr-clr)
    var(--b-bdr-r)
    ```
    </div>

### Die Option box-shadow

Bei Einstellung der Option `box-shadow` wird ein zusätzlicher Schatten/Schlagschatten ergänzt, welcher in den
[sonstigen Einstellungen](miscellaneous.md#schatten--schlagschatten) konfiguriert werden kann.

Ist für alle Box-Komponenten nur der Schlagschatten ohne Rahmen erwünscht, kann der `$boxed-border-width` auf `0`
gestellt werden. Soll der Rahmen bei `box` weiterhin bestehen bleiben, kann eine Option über einen eigenen
[Skin](../skin.md) individuell erweitert werden.

## Linien

`$divider-size` `$divider-style` `$divider-color`

Linien sind Rahmen, welche in Artikeln verwendet werden, sodass diese vom vorherigen, bzw. nachfolgenden Artikel optisch
getrennt werden können.

In den StyleManager-Optionen von Artikeln stehen hierbei sowohl für den oberen (Top) als auch für den unteren (Bottom)
Rahmen folgende Optionen unter `Component > Divider` zur Verfügung:

| Option | Beschreibung                                                                                                                                        |
|--------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Full   | Durch setzen der Option `Full` wird zwischen den Artikeln eine Linie mit gesamter Breite gesetzt, sodass die ganze Bildschirmbreite verwendet wird. |
| Inner  | Die Option `Inner` folgt dem inneren Abstand von Artikeln, sodass sich diese anhand der Breite der Inhaltselemente orientiert.                      |

Folgende Einstellungen können hierbei vorgenommen werden:

- `$divider-size`: Höhe der Linie
- `$divider-style`: [Stil](https://developer.mozilla.org/en-US/docs/Web/CSS/border-style) der Linie
- `$divider-color`: Farbe der Linie

??? example "Verfügbare SCSS-Variablen und Klassen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $divider-size
    $divider-style
    $divider-color
    ```

    ```css title="Klassen"
    .line-top /* Top -> Full */
    .line-btm /* Bottom -> Full */
    .line-inner-top /* Top -> Inner*/
    .line-inner-btm /* Bottom -> Inner*/
    ```
    </div>

## Tabelle

### Tabellenzelle

`$table-cell-spacing` `$table-cell-padding` `$table-cell-border-radius`

### Rahmen

#### Tabelle (Außen)

`$table-border-color` `$table-border-style` `$table-border-width`

#### Tabellenkopf

`$table-head-border-color` `$table-head-border-style` `$table-head-border-width`

#### Tabellenzelle

`$table-cell-border-color` `$table-cell-border-style` `$table-cell-border-width`

## Icon

## Icon-Schriftart

`$icon-font-family`

Die Einstellung überschreibt die Schriftart der im durch den ThemeManager genutzten Icons.

!!! danger "Ändern der $icon-font-family"

    Wird diese Standard-Einstellung `"ctm-icon"` abgeändert, funktioniert die unter [Icons](../icon-set.md) beschriebene
    Generierung und Bereitstellung von Icons nicht mehr.

    Das Abändern der hier eingestellten Schriftart wird nur empfohlen, wenn das Feature nicht gebraucht, und die
    verwendeten Icons über einen eigenen [Skin](../skin.md) gesetzt werden.

## Größe der Icons

`$icon-size-tiny` `$icon-size-small` `$icon-size-medium $icon-size-large`

