---
icon: octicons/typography-24
---

# Schriften

## Typografie

Die Typografie-Einstellungen erlauben die Einstellung der Schriftart ($font-family), der Schriftgröße des `<body>`, der
Schriftstärken und der Schriftfarben (regulär und invertiert). Die invertierte Schriftfarbe lässt sich in Artikeln und
Inhaltselementen über den Reiter Text einstellen und überschreibt die normale Farbe.

Schriftgröße, Art, Zeilenhöhe etc. haben immer auch Einfluss auf alle weiteren Elemente. Lediglich Überschriften und
Formulare können individuell eingestellt werden.

### Schriftart

`$font-family-base`

Die Einstellung überschreibt die Schriftart der Webseite.

!!! warning

    Sofern es sich nicht um eine [Standard-Schriftart](https://developer.mozilla.org/en-US/docs/Web/CSS/generic-family)
    handelt, muss die Schrift in Anführungszeichen `"Meine Schriftart"` gesetzt und zusätzlich im Seitenlayout
    eingebunden werden. Zwecks Ladezeiten-Optimierung empfiehlt sich immer eine lokale Einbindung der Schriftarten.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $font-family
    ```
    ```css title="CSS"
    var(--font-family)
    ```
    </div>

### Schriftgröße

`$font-size-base`

Beeinflusst die Schriftgröße für normale Texte einer Webseite und kann in `px` und `rem` angegeben werden.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $font-size-base
    ```
    ```css title="CSS"
    var(--fs-base)
    ```
    </div>

### Zeilenhöhe

`$line-height-base`

Dient der Einstellung der vertikalen Zeilenhöhe von Schriften.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $line-height-base
    ```
    ```css title="CSS"
    var(--leading-base)
    ```
    </div>

### Schriftstärken

`$font-weight-base` `$font-weight-*` `$strong-font-weight`

Die Standard-Schriftstärke kann über **$font-weight-base** festgelegt werden. Restliche Schriftstärken werden lediglich
in der Konfiguration verwendet.

!!! info

    Sofern keine Standard-Schriftart eingestellt wurde, müssen die Schriftstärken der Schriftart eingebunden werden,
    damit der Effekt sichtbar wird.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $font-weight-base
    $font-weight-light
    $font-weight-regular
    $font-weight-medium
    $font-weight-semibold
    $font-weight-bold
    ```
    ```css title="CSS"
    var(--fw-base)
    var(--fw-light)
    var(--fw-regular)
    var(--fw-medium)
    var(--fw-semibold)
    var(--fw-bold)
    ```
    </div>

### Schriftfarben

`$text-color-regular` `$text-color-invert`

Der ThemeManager liefert grundsätzlich zwei Farben für normalen Text, welche über die StyleManager-Einstellungen
ausgewählt werden können.
Sowohl die reguläre, als auch die invertierte Farbe, sind in den Standard-Einstellungen der Konfiguration in den meisten
Komponenten mit diesen Farben vorbelegt.

!!! info

    Die StyleManager-Einstellung der Text-Farbe hat zusätzlichen Einfluss auf andere Farben wie Überschriften, Buttons,
    Formularen etc. und kontrolliert nicht nur die Text-Farbe.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $text-color-regular
    $text-color-invert
    ```
    ```css title="CSS"
    var(--text-clr-base)
    var(--text-clr-invert)
    ```
    </div>

---

## Strong / Bold

### Strong-Schriftstärke

`$strong-font-weight`

Dient der Einstellung der Schriftstärke von allen `<strong>`-Elementen.

### Strong-Farben

`$strong-color-*`

Hiermit können die Strong-Farben angepasst werden, welche über die Textfarbe (regulär, invertiert) über den
Style-Manager eingestellt werden können.

!!! info

    Eine über den Style-Manager eingestellte Strong-Farbe überschreibt immer auch die Text-Farbe und setzt die Invertierung
    durch die eingestellte Text-Farbe außer Kraft.

---

## Links

Zusätzlich zur Typografie werden Link-Einstellungen für die Schriftstärke, Farben und die Verzierung bereitgestellt.
Da Verlinkungen auch immer mit einer Aktion verbunden sind, gibt es **zusätzliche Einstellungen für das Hovern**.

!!! info

    Das CSS-Framework sieht derzeit 3 Designs vor, wobei sich diese nur in den Farben unterscheiden. Sofern eine
    invertierte oder reguläre Textfarbe eingestellt ist, werden Links, welche nicht explizit mit einer Link-Farbe über
    den StyleManager eingestellt wurden, in der jeweils passenden Version angezeigt.

### Link-Schriftstärke

`$link-font-weight`

Dient der Einstellung der Schriftstärke von allen `<a>`-Elementen.

### Link-Farben

`$link-color-*` `$link-hover-color-*`

Hiermit können die Link-Farben angepasst werden, welche über die Textfarbe (regulär, invertiert) und / oder über die
Link-Farbe (regulär, invertiert, extra) über den Style-Manager eingestellt werden können.

!!! info

    Eine über den Style-Manager eingestellte Link-Farbe überschreibt immer auch die Text-Farbe und setzt die Invertierung
    durch die eingestellte Text-Farbe außer Kraft.

### Link-Verzierung

`$link-decoration-*` `$link-hover-decoration-*`

Verzierungen (*text-decorations*) können verwendet werden, um Links optisch hervorzuheben. Derzeit stehen folgende
Verzierungen zur Auswahl:

- none
- <span style="text-decoration: underline">underline</span>
- <span style="text-decoration: overline">overline</span>
- <span style="text-decoration: line-through">line-through</span>
- <span style="text-decoration: wavy underline">wavy</span>
- <span style="text-decoration: dotted underline">dotted</span>
- <span style="text-decoration: dashed underline">dashed</span>

### Link-Typen

| Typ       | Beschreibung      |
|-----------|-------------------|
| `regular` | Regulärer Link    |  
| `invert`  | Invertierter Link |  
| `extra`   | Extra Link        |

???+ example "Verfügbare (S)CSS-Variablen"

    Da sich Link-Eigenschaften abhängig der Text-Farbe verhalten, gibt es nur eine CSS-Custom-Property für alle Link-Farben.
    Hierdurch lassen sich Link-Farben im eigenen Skin hinzufügen.

    Die Typen lassen sich dem Abschnitt [Link-Typen](#link-typen) entnehmen

    <div class="grid" markdown>
    ```scss title="SCSS"
    $link-font-weight
    $link-color-[typ]          
    $link-hover-color-[typ]   
    $link-decoration-[typ]  
    $link-hover-decoration-[typ]
    ```
    ```css title="CSS"
    var(--a-fw)
    var(--a-clr)
    var(--a-clr-hvr)
    var(--a-td)
    var(--a-td-hvr)
    ```
    </div>
