---
title: Hintergründe
---

# Hintergrundbilder

In zahlreichen Situationen besteht der Wunsch der Anwender, Hintergrundbilder zu integrieren. Oftmals erweist sich dies
für sie als nicht eigenständig umsetzbar, wodurch professionelle Unterstützung erforderlich wird.

Der Prozess gestaltet sich wie folgt:

- (Hochladen des Bildes)
- Hinterlegung des Bildpfads in einer CSS-Datei
- Lokale Kompilierung der CSS-Datei
- Hochladen der CSS-Datei
- Setzen der CSS-Klasse

Ein weiteres Problem entsteht, wenn der Anwender dasselbe Hintergrundbild in einem anderen Artikel verwenden möchte. In
solchen Fällen ist es notwendig, dass er die zugehörige CSS-Klasse kennt und manuell setzt. Bei einer Vielzahl von
Hintergrundbildern bedeutet dies, dass jede einzelne CSS-Klasse dem Anwender bekannt sein muss.

## Hinzufügen und entfernen

Der ThemeManager erweitert eine Option im Dateisystem, sodass Bilder als Hintergrundbild definiert werden können.

<figure markdown>
  ![Bild als Hintergrund festlegen](../../../assets/configuration/background/file-set-as-background.png){ loading=lazy }
  <figcaption>Über die Option kann ein Hintergrundbild festgelegt werden</figcaption>
</figure>

Da das `CSS` für Hintergrundbilder erst generiert werden muss, stehen diese erst nach Kompilieren des Themes zur
Verfügung.

<figure markdown>
  ![Compiler preview](../../../assets/configuration/background/background-compiler.png){ loading=lazy }
  <figcaption>Der Asset-Compiler listet alle verfügbaren Hintergründe auf</figcaption>
</figure>

!!! warning "Entfernen von Hintergrundbildern"

    Wird die entfernte Datei bereits als Hintergrundbild eingebunden, bleibt diese Option im Element als 
    "unbekannte Option" bestehen. Die CSS-Klasse existiert weiterhin bis die Auswahl im Inhaltselemt/Artikel etc.
    entfernt wird.

Die Generierung von Hintergrund-Bildern** findet global statt, sodass Backgrounds Theme-übergreifend zur Verfügung
stehen.

## Auswählen und einstellen

Anwender können die Hintergrundbilder unter dem Reiter Background auswählen. Die Beschriftung der Hintergrundbilder
im Backend folgt hierbei dem Schema `BG-[Dateiname]`.

![Hintergrund auswählen](../../../assets/configuration/background/style-manager-background-image.png){ loading=lazy }

### Wo kann ich Hintergrundbilder einstellen?

Die nachfolgende Tabelle zeigt auf, wo Hintergrundbilder eingestellt werden können und wie sie sich auswirken.

| Ort                           | Beschreibung                                                                                                                                                                                                                                                                                               |
|-------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Layout<br>(Global)            | Ist ein Hintergrundbild im Layout eines Themes eingestellt, wird es auf jeder Seite angezeigt in welchem das Layout zum Einsatz kommt. Die CSS-Klasse wird in den `<body>` geschrieben.                                                                                                                    |
| Seiten<br>(Global)            | Ist ein Hintergrundbild in einer Seite eingestellt, wird es auf der Seite angezeigt.<br>Auch hier wird die Klasse in den `<body>` geschrieben. Das hier eingestellte Bild überschreibt nicht die im Layout eingestellte Option.                                                                            |
| Artikel<br>(Global)           | Sofern ein Hintergrundbild in einer Seite mit dem [Layout für volle Breite](../installation/setup.md#layout-für-volle-breite) ausgewählt wird, erstreckt sich das Hintergrundbild auf die komplette Bildschirm-Breite. Es wird nicht empfohlen Hintergründe in Artikeln des Inhaltsbereiches einzustellen. |
| Inhaltselement<br>(Component) | folgt...                                                                                                                                                                                                                                                                                                   |
| Inhaltselement<br>(Element)   | folgt...                                                                                                                                                                                                                                                                                                   | | |

Die Einstellungen für *Component* und *Element* verhalten sich in Modulen gleich.

!!! tip "Bilder und Farben"

    Hintergrundbilder können mit der Hintergrundfarbe kombiniert werden, wenn sie transparent sind oder in der Größe
    eingeschränkt werden (standardmäßig werden Hintergrundbilder immer auf die verfügbare Breite gestreckt). Dadurch ist
    eine Kombination aus Hintergrundfarbe und Hintergrundbild möglich.

### Weitere Optionen

Die im StyleManager verfügbaren Hintergrund-Einstellungen können genutzt werden, um das Verhalten des festgelegten
Hintergrunds zu beeinflussen.

![Hintergrund-Einstellungen im StyleManager](../../../assets/configuration/background/background-settings.png){ loading=lazy }

| Einstellung         | Beschreibung                                                                                                                                 |
|---------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Color               | Hiermit kann eine Hintergrundfarbe ausgewählt werden. Eine Kombination mit transparenten Hintergrundbildern ist möglich.                     |
| Image               | Dient der Auswahl des Hintergrundbildes. Über die Option `none` kann ein über den [Skin](skin.md) gesetztes Hintergrundbild entfernt werden. |
| Attachment          |                                                                                                                                              |
| Repeat              |                                                                                                                                              |
| Size                |                                                                                                                                              |
| Horizontal Position |                                                                                                                                              |
| Vertical Position   |                                                                                                                                              |

!!! example "Hintergrund-Eigenschaften"

    Die in der Tabelle aufgeführten Einstellungen sind die verfügbaren CSS-Eigenschaften für Hintergrundbilder.

    Im Standard werden folgende Optionen nach der Best-Practice gesetzt, sodass keine Einstellungen vorgenommen werden
    müssen:

    ```css
        background-image: ...;
        background-attachment: scroll;
        background-position: 50% 50%;
        background-repeat: no-repeat;
        background-size: cover;
    ```

## Cascading Style Sheet

Für jede als Hintergrund ausgewählte Datei werden zwei CSS-Klassen erstellt. Das CSS einer Datei mit dem Namen
`emblem.svg` sieht wie folgt aus:

```css
.bgi-emblem {
    --bgi: url(/files/theme/backgrounds/emblem.svg);
}

.i-bgi-emblem {
    --i-bgi: url(/files/theme/backgrounds/emblem.svg);
}
```

!!! question "Was bedeutet `.bgi` und `.i-bgi`?"

    Der erste Präfix steht für `background-image` und setzt Hintergrundbilder im selben Container,
    der zweite steht für `item-background-image` und vererbt Hintergrundbilder in Kinds-Elemente innerhalb von 
    Listen, sodass Hintergründe auch für diese erstellt werden können.

## Farben-Vorschau für Backend-Nutzer

