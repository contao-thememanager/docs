---
icon: octicons/globe-24
---

# Global

## Basis-Einstellungen

In den grundlegenden Einstellungen sind Optionen für die **Schriftgröße des Root-Elements** (`$browser-context`), die
**Hintergrundfarbe des Body-Elements** (`$body-bg`) und den **Border-Radius** (`$border-radius`) vorhanden.

!!! info "$browser-context"

    Diese Variable beeinflusst die Berechnung der im Framework enthaltenen Funktionen zur Größenanpassung, sodass die
    Umwandlung von px zu rem immer im Kontext der Schriftgröße des Root-Elements erfolgt.

!!! info "$border-radius"

    Diese Variable kann in einem Skin verwendet werden und hat derzeit keine weitere Funktion.

    <div class="grid" markdown>
    ```scss title="SCSS"
    $border-radius
    ```
    ```css title="CSS"
    var(--bdr-r)
    ```
    </div>

---

## Farben

Über die Theme-Konfiguration lassen sich die nachfolgenden 4 Farben einstellen, welche innerhalb der Konfiguration für
Buttons, Komponenten, Schriften und Überschriften verwendet werden. Zusätzlich stehen diese Farben als Icon- und
Hintergrundfarbe innerhalb von Seiten, Artikeln, Inhaltselementen, Modulen etc. zur Verfügung.

### Primäre Farbe

`$primary`

Hauptsächlich verwendet für Buttons, Komponenten, Icons oder Hervorhebungs-Backgrounds.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $primary
    ```
    ```css title="CSS"
    var(--clr-primary)
    var(--clr-primary-rgb) /* RGB */
    ```
    </div>

### Sekundäre Farbe

`$secondary`

Hauptsächlich verwendet für alternative Buttons, Icons oder Hervorhebungs-Backgrounds.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $secondary
    ```
    ```css title="CSS"
    var(--clr-secondary)
    var(--clr-secondary-rgb) /* RGB */
    ```
    </div>

### Helle Hintergrundfarbe

`$light`

Hauptsächlich verwendet für Hintergründe, um Artikel optisch zu trennen.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $light
    ```
    ```css title="CSS"
    var(--clr-light)
    var(--clr-light-rgb) /* RGB */
    ```
    </div>

### Dunkle Hintergrundfarbe

`$dark`

Hauptsächlich verwendet für Hintergründe in Artikeln, die mit einer invertierten Textfarbe herausstechen sollen.

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $dark
    ```
    ```css title="CSS"
    var(--clr-dark)
    var(--clr-dark-rgb) /* RGB */
    ```
    </div>
