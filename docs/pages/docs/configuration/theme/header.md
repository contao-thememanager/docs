---
icon: material/page-layout-header
---

# Header

Alle hier definierten Einstellungen beeinflussen
die [Kopfzeile](https://docs.contao.org/manual/de/layout/theme-manager/seitenlayouts-verwalten/#kopf-und-fußzeile) der
Website, sofern diese in den [Layout-Bereichen](../../installation/setup.md#layouts-erstellen) eingestellt wurde.

## Hintergrund

`$header-bg`

Über die Einstellung `$header-bg` kann der Hintergrund der Kopfzeile eingestellt werden

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $header-bg
    ```
    ```css title="CSS"
    var(--header-bg)
    ```
    </div>

## Höhe der Kopfzeile

`$header-height` `$header-height-*`

Über die nachfolgenden Einstellungen lässt sich die Höhe der Kopfzeile über die verschiedenen
**[Breakpoints](layout.md#breakpoints)** einstellen, sodass die Höhe auf verschiedenen Geräten variieren kann.

!!! info "Größe der CSS-Datei"

    Sofern der selbe Wert über zwei Breakpoints eingestellt ist, wird nur der erste Wert als CSS-Variable in den `:root` 
    geschrieben um CSS einzusparen.

Da die Höhe variabel ist, wird diese nur eine Custom property gesteuert, sodass der Zugriff jederzeit über den
nachfolgenden Wert möglich ist:

    var(--hdr-hght)

??? example "Verfügbare (S)CSS-Variablen"

    <div class="grid" markdown>
    ```scss title="SCSS"
    $header-height
    $header-height-xs
    $header-height-s
    $header-height-m
    $header-height-l
    $header-height-xl
    ```
    ```css title="CSS"
    var(--hdr-hght)
    ```
    </div>

### Exkurs: Header behaviour

Sowohl in den Layout- als auch in den Seiten-Einstellungen befindet sich im Abschnitt Layout die Option
**Header behaviour**, welche entscheidet, wie sich die Kopfzeile auf der Seite verhalten soll.

!!! info

    Jede der nachfolgend eingestellten Optionen führt dazu, dass die Kopfzeile jederzeit sichtbar ist. Mithilfe eines
    JavaScript-Snippets lässt sich diese Ein- bzw. Ausblenden. Tutorials für ein solches JavaScript lassen sich im 
    Internet finden.

=== "Fixed"

    Ist diese Option ausgewählt, fixiert sich die Kopfzeile auf der Webseite.
    !!! tip
        Diese Option wird empfohlen, wenn die Kopfzeile **über dem Inhalt** der nachfolgenden Layout-Bereiche *schweben* 
        soll.

=== "Undocked"

    Auch mit dieser Option wird die Kopfzeile auf der Webseite fixiert, der erste Artikel wird jedoch 
    **nicht überlagert**.
    !!! tip
        Diese Option wird empfohlen, wenn die Kopfzeile jederzeit sichtbar sein soll, der **Inhalt** der nachfolgenden 
        Layout-Bereiche aber **nicht verdeckt** werden soll.

### Exkurs: Artikel-Höhe und Kopfzeilen-Höhe

Innerhalb von Artikeln lässt sich über die Option *Article-Height* die Höhe des Artikels auf eine Display-Höhe begrenzen
bzw. vergrößern, sodass der Inhalt im gesamten Bereich sichtbar ist.

Damit die Höhe eines mit `100vh` eingestellten Artikels (*erster Artikel*) die tatsächliche Bildschirmhöhe einnimmt,
kann die Option `Consider header` aktiviert werden.

!!! info

    Ist die Option `Fixed` auf der Seite ausgewählt, muss diese Option nicht eingestellt werden.

## Abstand

`$header-padding`

Über die Option `$header-padding` kann der innere Abstand / Polster (*padding*) des Umschlags für die Kopfzeilen-Module
eingestellt werden.

!!! info

    Der Abstand des [Navigations-Items](modules.md#navigations-link--navigations-item) beeinflusst die Höhe zusätzlich,
    sodass die [Höhe der Kopfzeile](#höhe-der-kopfzeile) eventuell angepasst werden muss. 

## Ausrichtung der Elemente

`$header-alignment-vertical` `$header-alignment-horizontal`

Alle sich in der Kopfzeile befindenden Module können über diese Einstellungen ausgerichtet werden.

Die vertikale Ausrichtung (`$header-alignment-vertical`) erlaubt die folgenden Optionen und folgt der Flexbox-Anweisung
`align-items`[^1] mit den Optionen:

| Option       | Beschreibung |
|--------------|-------------:|
| `flex-start` |         Oben |
| `center`     |       Mittig |
| `flex-end`   |        Unten |
| `baseline`   |        Achse |

Die horizontale Ausrichtung (`$header-alignment-horizontal`) erlaubt die folgenden Optionen und folgt der
Flexbox-Anweisung `justify-content`[^2] mit den Optionen:

| Option          | Beschreibung                                                                                                                                                          |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `flex-start`    | Module werden zum Start ausgerichtet                                                                                                                                  |
| `center`        | Mittige Ausrichtung der Module                                                                                                                                        |
| `flex-end`      | Module werden zum Ende ausgerichtet                                                                                                                                   |
| `space-between` | Abstand zwischen den Modulen                                                                                                                                          |
| `space-around`  | Aufteilung des freien Raums vor, zwischen und hinter den Modulen. Der Abstand des ersten und letzten Moduls ist zusammen so groß wie der Abstand zwischen den Modulen |
| `space-evenly`  | Gleichmäßiger Abstand aller Module                                                                                                                                    |
| `revert`        | Reset                                                                                                                                                                 |

!!! tip

    Das `<header>` Element wird durch das CSS-Framework auf `display: flex` gesetzt. Da sich Anweisungen von CSS-Grid
    teilweise mit denen von CSS-Flexbox überlagern, können die `center` und `space-*` Anweisungen weiterhin verwendet
    werden.

    Der Header kann mit folgendem CSS im [Skin](../../../guides/skin/introduction.md) auf CSS-Grid gestellt werden:
    ```css
    header > .inside {
      display: grid;
    }
    ``` 

[^1]: Align-Items auf [css-tricks](https://css-tricks.com/almanac/properties/a/align-items/)
[^2]: Justify-Content auf [css-tricks](https://css-tricks.com/almanac/properties/j/justify-content/)
