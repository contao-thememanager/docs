---
icon: material/button-cursor
---

# Buttons

Bekannt seit Anfangszeiten des Internets definiert das
<button type="button" onclick="alert('Reminder to hydrate :)')" style="all: revert">Button-Element</button> eine
anklickbare Schaltfläche. Das Aussehen ist of definiert durch einen prägnanten größeren Hintergrund und/oder einem
Rahmen.

Im Rahmen des Website-Designs werden einige Hyperlinks so verändert, dass sie wie ein `<button>` aussehen. Die
nachfolgenden Einstellungen belaufen sich hierbei auf alle `<button>`-Elemente und jeden Hyperlink innerhalb einer mit
einem *Button-Design* eingestellte Komponente.

## Allgemein

Die allgemeinen Einstellungen für Buttons dienen dazu, dass die Zeilenhöhe, Schriftgrößen und Polster (Paddings) für
die nachfolgenden Designs eingestellt werden können.

### Zeilenhöhe

`$button-line-height`

Dient der Einstellung der vertikalen Zeilenhöhe aller Buttons und Button-Designs (`Standard = 1`).

??? example "Verfügbare SCSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $button-line-height
    ```
    </div>

### Schriftgrößen und Paddings

`$button-font-size-*` `$button-padding-*`

Für jedes Button-Design werden 4 Großen bereitgestellt, welche auf die StyleManager Option `Size` hören.

- Small (Size: Small)
- Medium (Standard)
- Large (Size: Large)
- Super (Size: Super)

Sowohl Schriftgröße als auch Padding werden über die `Size`-Option gesetzt.

!!! info "Button-Padding und Rahmenbreite"

    Damit zwei verschiedene Button-Designs die selbe Größe behalten, wird die Rahmenbreite vom Padding abgezogen.
    Hierfür wird der Rahmen vom Padding abgezogen und die danach verfügbare Kurzschreibweise verwendet.

??? example "Verfügbare SCSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    /** Padding */
    #{subList($button-padding-small,  $button-border-width-primary, 'rem', true)};
    #{subList($button-padding-medium, $button-border-width-primary, 'rem', true)};
    #{subList($button-padding-large,  $button-border-width-primary, 'rem', true)};
    #{subList($button-padding-super,  $button-border-width-primary, 'rem', true)};

    /** Schriftgröße */
    $button-font-size-small
    $button-font-size-medium
    $button-font-size-large
    $button-font-size-super
    ```
    ```css title="CSS"
    /** Padding */
    var(--btn-p-1)
    var(--btn-p-2)
    var(--btn-p-3)
    var(--btn-p-4)
    ```
    </div>

---

## Button-Design

`$button-font-weight-*` `$button-transform-*` `$button-decoration-*` `$button-bg-*` `$button-color-*` `$button-border-*`

Der ThemeManager stellt derzeit drei Designs bereit, welche im Standard auf die Primär-, die Sekundär- und die dunkle
Farbe hören.

| Design        | Beschreibung                                                                                                                                                   |
|---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `Primary`     | Primäres Design und Standard-Styles für `<button>`-Elemente.<br>Im Contao Core enthaltene `<button>`-Elemente können mit einem anderen Design versehen werden. |  
| `Secondary`   | Sekundäres Design, welches zur Auswahl in Buttons und Links steht.                                                                                             |  
| `Alternative` | Alternatives Design, welches zur Auswahl in Buttons und Links steht.                                                                                           |

!!! info "Designs anpassen"

    Jeder Button kann den eigenen Bedürfnissen angepasst werden, sodass die Defaults nicht notwendig sind.

Zusätzlich stehen weitere Einstellungen zur Verfügung, welche das Design eines Buttons bestimmen:

**Text**

- Schriftstärke[^1] (*font-weight*)
- Text-Darstellung[^2] (*text-transform*)
- Text-Verzierung[^3] (*text-decoration*)

**Farben**

- Hintergrundfarbe (*background-color*)
- Farbe (*color*)

**Rahmen**

- <a style="display: block; text-align: center; padding: 5px 10px; border: solid 1px var(--md-primary-fg-color)" title="Rahmenfarbe" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-color">
  Rahmenfarbe</a>
- <a style="display: block; text-align: center; padding: 5px 10px; border: solid 1px var(--md-primary-fg-color); border-radius: 50px" title="Rahmenradius" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius">
  Rahmenradius</a>
- <a style="display: block; text-align: center; padding: 5px 10px; border: solid 5px var(--md-primary-fg-color); border-radius: 50px" title="Rahmenbreite" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-width">
  Rahmenbreite</a>
- <a style="display: block; text-align: center; padding: 5px 10px; border: double 5px var(--md-primary-fg-color)" title="Rahmenstil" href="https://developer.mozilla.org/en-US/docs/Web/CSS/border-style">
  Rahmenstil</a>

!!! info "Farben eines Buttons"

    Primary, Secondary und Alternative haben invertierte Farben, sodass bei Aktivierung der Option "invert" in Text oder
    Link die Hintergrundfarbe, Farbe und die Rahmenfarbe geändert werden können.

[^1]: Schriftstärken wurden in den Themen [Text](fonts.md#Schriftstärken) und [Überschriften](headings.md#Schriftstärke)
erklärt.
[^2]: Textdarstellungen wurden bereits im Thema [Überschriften](headings.md#textdarstellung) erklärt.
[^3]: Textverzierungen wurden im Thema [Link-Verzierungen](fonts.md#link-verzierung) behandelt.
