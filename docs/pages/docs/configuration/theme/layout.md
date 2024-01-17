---
icon: material/view-grid-plus-outline
---

# Layout

Die nachfolgenden Kapitel beschreiben Einstellungen, welche Auswirkungen auf das visuelle Verhalten der Website haben.

___

## Breakpoints

`$breakpoints`

Breakpoints werden verwendet, um das Layout einer Website auf verschiedene Bildschirmbreiten anzupassen. Dies ermöglicht
das [responsive Websdesign](https://de.wikipedia.org/wiki/Responsive_Webdesign), bei der das Erscheinungsbild je nach
Gerät oder Fenstergröße optimiert wird.

Typische Breakpoints sind beispielsweise für

- Smartphones (kleine Bildschirme)
- Tablets (mittelgroße Bildschirme)
- Desktops (große Bildschirme)

definiert, um ein konsistentes und benutzerfreundliches Erlebnis auf unterschiedlichen Geräten zu gewährleisten.
Ungleich anderer CSS-Frameworks liegt der Fokus des ThemeManagers auch auf Bildschirme, welche über Full HD
(1920 x 1080) gehen.
![Breakpoints des ThemeManagers](../../../../assets/configuration/layout/grid-breakpoints.png){loading=lazy}

Der ThemeManager ergänzt sechs Breakpoints, welche sich in den StyleManager Einstellungen als Suffix der Einstellungen
wieder finden (z.B. `(xs)`).

![Breakpoints im StyleManager](../../../../assets/configuration/layout/stylemanager-breakpoints.png){loading=lazy}

| Breakpoint | Bildschirmgröße |                    Geräte |
|------------|----------------:|--------------------------:|
| -          |          <600px |    Smartphones (portrait) |
| xs         |          ≥600px |   Smartphones (landscape) |
| s          |          ≥768px | kleine Tablets (portrait) |
| m          |         ≥1024px |        Tablets (portrait) |
| l          |         ≥1264px |           Desktop (1080p) |
| xl         |         ≥1921px |       Desktop (1440p, 4k) |

Jeder Breakpoint kann individuell angepasst werden, der Name kann aber nicht geändert werden.

???+ example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $breakpoints: (
      xs: 600px,  // 37.5rem
      s:  768px,  // 48rem
      m:  1024px, // 64rem
      l:  1264px, // 79rem
      xl: 1921px  // 120rem
    )
    ```
    ```css title="CSS"
    /* Zu erwähnen ist, dass Custom properties
    nicht in Media queries funktionieren */
    var(--bp-xs)
    var(--bp-s)
    var(--bp-m)
    var(--bp-l)
    var(--bp-xl)
    ```

    </div>

### Media queries

Sofern der Skin mit [SCSS](https://sass-lang.com/guide/) geschrieben und im Theme eingebunden wird, kann mit den
folgenden Mixins auf die Breakpoints zugegriffen werden:

???+ example "Verfügbare SCSS-Mixins"

    ```scss title="Min width"
    @include media-breakpoint('xs') { ... } // @media (min-width: 600px)  { ... }
    @include media-breakpoint('s')  { ... } // @media (min-width: 768px)  { ... }
    @include media-breakpoint('m')  { ... } // @media (min-width: 1024px) { ... }
    @include media-breakpoint('l')  { ... } // @media (min-width: 1264px) { ... }
    @include media-breakpoint('xl') { ... } // @media (min-width: 1921px) { ... }
    ```
    ```scss title="Max width"
    @include max-breakpoint('xs') { ... } // @media (max-width: 599.98px)  { ... }
    @include max-breakpoint('s')  { ... } // @media (max-width: 767.98px)  { ... }
    @include max-breakpoint('m')  { ... } // @media (max-width: 1023.98px) { ... }
    @include max-breakpoint('l')  { ... } // @media (max-width: 1263.98px) { ... }
    @include max-breakpoint('xl') { ... } // @media (max-width: 1920.98px) { ... }
    ```

    !!! info
    
        Mehr zu der Subtraktion von 0.02px kann hier gefunden werden: https://www.w3.org/TR/mediaqueries-4/#mq-min-max

___

## Verhalten

Die Einstellungen dieser Kategorie beeinflussen das Verhalten des
[Inhaltslayouts](../../installation/setup.md#inhaltslayout) und ermöglichen hierbei drei einstellbare Breiten
(small, medium, large) für die linke und/oder rechte Spalte.

### Verhaltensänderung

`$layout-column-[small|medium|large]-break` `$layout-column-width-*` `$layout-column-gutter-*`

Diese Optionen erlauben die Auswahl eines [Breakpoints](#breakpoints) für die Verhaltensänderung, bei welcher die linke
und/oder rechte Spalte in der gleichen Reihe der Hauptspalte angezeigt werden.

![Verhalten des Layouts](../../../../assets/configuration/layout/layout-behavior.png){loading=lazy}

Über `$layout-column-width-` lassen sich die Breiten für die linke und rechte Spalte einstellen. Mit
`$layout-column-gutter` wird der Abstand zur Hauptspalte eingestellt.

!!! tip

    Sofern nur eine oder zwei Breakpoints gewünscht sind, kann das kleinere `$layout-column-[]-break` auf die gleiche
    Einstellung wie die des nachfolgenden eingestellt werden.

___

## Artikel

### Horizontale Breite

`$x-spacing-large-m` `$x-spacing-large-l` `$x-spacing-small`

### Horizontaler Abstand zum Bildschirmrand

`$article-outer-padding`

### Vertikaler Abstand

`$article-spacing-*` `$article-main-spacing-bottom`

### Höhen

`$article-min-vheight` `$article-options-vheight`

___

## Grid

`$grid-columns` `$grid-gutter-width` `$grid-gutter-bottom`

Das CSS-Framework des Contao ThemeManager nutzt ein Flexbox-basiertes 12-Spalten Grid-System, in welches sich die
Inhaltselemente in Artikeln einordnen lassen.

Ein Artikel dient hierbei immer als Grid-Container, welches die Ausrichtung der Kinds-Elemente (Inhaltselemente)
steuern kann. Inhaltselemente lassen sich in dem 12-Spalten Raster einordnen.

![12er Grid](../../../../assets/configuration/layout/grid-columns-12.png){loading=lazy}
!!! danger "Spaltenanzahl von 12 ($grid-columns)"

    Es wird nicht empfohlen die Spaltenanzahl von 12 zu ändern, da die Optionen des StyleManagers nicht angepasst
    werden!

___

## Abstände (Innen)

### Paragraphen

`$paragraph-spacing`

### Element-Spacing

`$element-spacing-*`

### Vertikales Padding

`$top-bottom-padding-small`

### Horizontales Padding

`$left-right-padding-small`

___

## Abstände (Außen)

### Vertikales Margin

`$top-bottom-margin-*`

### Horizontales Margin 

`$left-right-margin-*`

___

## Bild-Text

`$image-text-behaviour-min-width` `$image-text-ratio-options`