---
icon: octicons/heading-24
---

# Überschriften

!!! info

    Der ThemeManager erweitert die in Contao einstellbaren Überschriften (`<h1>` - `<h6>`) durch weitere Elemente
    (`p`, `span` & `div`) und ergänzt diese um eine Klasse, sodass sich diese Einstellungen auf die Überschrift bzw.die 
    im Element/Modul eingestellte *Überschrift*-Klasse auswirken.

## Typografie der Überschriften

Über die nachfolgenden Reiter lässt sich das Aussehen von Headlines `<h1>` - `<h6>` und CSS-Klassen `.h1` - `.h6`
verändern, wobei die folgenden Einstellungen möglich sind:

- Zeilenhöhe (*line-height*)
- Schriftgröße über verschiedene Breakpoints (*font-size*)
- Reguläre und invertierte Farbe (*color*)
- Schriftstärke (*font-weight*)
- Zeichenabstand (*letter-spacing*)
- Textdarstellung (*text-transform*)

!!! info "Einstellungen für den Inhaltsbereich?"

    Hiermit werden alle Artikel zusammengefasst, welche sich im 
    [Layout-Bereich](../../installation/setup.md#inhaltslayout) *Hauptspalte* befinden.

    Da sich die Einstellungen der Überschriften des `Volle Breite` und `Inhaltsbereich` Layout gleichen, werden diese 
    zusammen aufgefasst.

### Zeilenhöhe

`$line-height-headline` `$h[1-6]-line-height` `$h[1-6]-content-line-height`

Dient der Einstellung der vertikalen Zeilenhöhe der Überschrift und kann individuell für jede Größe eingestellt werden.

Die Variable `$line-height-headline` dient lediglich als globale Einstellung der nachfolgenden Zeilenhöhen, sodass diese
im Standard für alle Überschriften gilt.

### Schriftgrößen

`$h[1-6] - [ |content] - font-size - [ |small|medium]`

Für jede Überschrift(/-Klasse) lässt sich die Schriftgröße für die folgenden [Breakpoints](layout.md#breakpoints)
einstellen:

| Breakpoints           |       Fensterbreite | Größe / Genutzte Variable |
|-----------------------|--------------------:|--------------------------:|
| kleiner **`xs`**      |          ` < 600px` |   **`*-font-size-small`** |
| **`xs`** bis  **`m`** | `600px - 1023.98px` |  **`*-font-size-medium`** |
| ab **`m`**            |         `>= 1024px` |         **`*-font-size`** |

???+ example "Verfügbare (S)CSS-Variablen"

    Da sich die Schriftgrößen abhängig des Breakpoints verhalten, gibt es nur eine CSS-Custom-Property für jeden 
    Headline-Typen. 

    Die Typen (h1 - h6) beziehen sich sowohl auf den normalen als auch auf den Inhaltsbereich und müssen
    beim Kopieren der nachfolgenden CSS mit der gewünschten **Zahl** (1-6) ausgetauscht werden.

    <div class="grid" markdown>
    ```scss title="SCSS"
    $h1-font-size-small          
    $h1-font-size-medium   
    $h1-font-size
    ```
    ```css title="CSS"
    var(--h1-fs)
    ```
    ```scss title="SCSS"
    $h1-content-font-size-small          
    $h1-content-font-size-medium   
    $h1-content-font-size
    ```
    ```css title="CSS"
    var(--h1-c-fs)
    ```
    </div>

### Überschriften-Farben

`$h[1-6] - [ |content] - color [ |invert]`

### Schriftstärke

`$h[1-6] - [ |content] - font-weight`

### Zeichenabstand

`$h[1-6] - [ |content] - letter-spacing`

### Textdarstellung

`$h[1-6] - [ |content] - transform`

## Abstände von Überschriften

`$headline-spacing` `$headline-spacing-*`
