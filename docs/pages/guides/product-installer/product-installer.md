---
title: Product Installer
---

# Demo über den Product Installer installieren

## 1. Product Installer installieren

!!! info

    Für die Installation über die Kommandozeile muss [Composer](https://getcomposer.org/) auf dem System installiert sein.

=== "Composer"

    ```shell
    composer require oveleon/contao-theme-manager-bridge 1.0
    ```

=== "Contao Manager"

    Im Contao Manager steht der _Product Installer_ für den Contao ThemeManager unter dem Namen `ThemeManager: Product Installer` zur Verfügung.
    !!! tip
        Hier findest Du [eine Anleitung, wie Erweiterungen über den Contao Manager installiert](https://docs.contao.org/manual/de/installation/erweiterungen-installieren/) werden können

## 2. Produkte erwerben

Produkte können über [contao-thememanager.com](https://www.contao-thememanager.com/) erworben werden. Nach Mapping der
Lizenzschlüssel können diese im Product-Installer eingetragen werden.

## 3. Produkt installieren und einrichten

Sofern der _Product Installer_ installiert, können wir mit der Einrichtung beginnen. Nach erfolgreicher Installation
erscheint ein neuer Menüpunkt "Produktverwaltung" im Contao-Backend, welcher bei Klick den _Product Installer_
öffnet.

![product-installer.png](../../../assets/product-installer/product-installer.png)

#### Produkt registrieren

Im nächsten Schritt möchten wir das Produkt registrieren, damit die Einrichtung über den _Product Installer_
zur Verfügung gestellt wird.

Mit Klick auf **Produkt registrieren** gelangen wir in die nächste Maske, in der ein bis mehrere Schnittstellen
(abhängig der installierten Abhängigkeiten) zur Verfügung gestellt werden.

![product-installer.png](../../../assets/product-installer/product-upload.png)

#### Produktprüfung

Hat alles funktioniert bekommen wir im nächsten Schritt eine Übersicht des Produktes.

!!! note

    Es könnte sein, dass Du eine Fehlermeldung bekommst, mit dem Hinweis, dass Deine Contao-Version nicht für das
    Produkt geeignet ist. Bitte überprüfe in diesem Fall Deine Contao-Version.

![product-installer.png](../../../assets/product-installer/product-preview.png)

#### Contao Manager Authentifizierung

In der nächsten Maske wird geprüft, ob eine Verbindung zum Contao Manager hergestellt werden kann. Diese
wird benötigt, um das Produkt ordnungsgemäß mit allen Abhängigkeiten zu installieren.
In diesem Schritt könnten drei Szenarien auftreten. Bitte folge den Hinweisen des _Product Installers_, um Dein Projekt
im Contao Manager zu authentifizieren.

|    |   Installiert    | Authentifiziert  | Beschreibung                                       |
|----|:----------------:|:----------------:|:---------------------------------------------------|
| 🟢 | :material-check: | :material-check: | Der Contao-Manager ist einsatzbereit und verbunden |
| 🟡 | :material-check: | :octicons-x-24:  | Die Authentifizierung ist ausstehend               |
| 🔴 | :octicons-x-24:  | :octicons-x-24:  | Der Contao-Manager ist nicht installiert           |

!!! warning

    Ab Version `1.7.0` des Contao Managers muss das Projekt eine SSL-Verbindung aufweisen, um die
    Authentifizierungen durchzuführen.

!!! question "Ich habe den Contao-Manager installiert, der Product-Installer erkennt es aber nicht?"

    Prüfe zunächst, ob der Contao Manager installiert ist, aufgerufen werden kann und funktioniert.

    Stelle zudem sicher, dass in der composer.json das `contao/manager-bundle` als Abhängigkeit hinterlegt und installiert ist.

    Möglicherweise wurde der Dateiname der `contao-manager.phar.php` abgeändert, ohne diese Änderung in einer
    `config/config.yaml` der Contao-Installation einzutragen:

    ```yaml
    contao_manager:
      manager_path: neuerDateiName.phar.php
    ```
    
    Lösche außerdem anschließend den Cache und versuche es erneut.

Sofern die Verbindung hergestellt wurde, siehst Du folgende Maske:

![product-installer.png](../../../assets/product-installer/product-manager.png)

#### Produktvorbereitung und -registrierung

Nach Klick auf **Weiter** kommen wir in die eigentliche Produktregistrierung und Installation der Abhängigkeiten. Hier
erhältst du eine Übersicht der Prozesse, welche durchgeführt werden müssen, um dein Produkt zu registrieren und
anschließend einrichten zu können.
Mit einem weiteren Klick auf **Starten** wird dieser Prozess gestartet.

!!! tip

    Über die drei Punkte ( **⋮** ) neben einem Prozess können Details zu diesem aufgerufen oder Aktionen angewendet
    werden.

![product-installer.png](../../../assets/product-installer/product-process-console.png)

Sofern die Notwendigkeit besteht, eine Datenbankmigrierung durchzuführen, muss diese manuell über das Menü ( **⋮** )
gestartet werden.

!!! note

    Sollten Probleme während der Datenbankmigration auftreten, kann dieser Schritt übersprungen werden. Bitte führe die
    Migration der Datenbank anschließend über den Contao Manager oder auf der Kommandozeile durch.

#### Produkteinrichtung

Sofern alle Prozesse erfolgreich durchgelaufen sind, steht das Produkt in der
Produktübersicht des _Product Installers_ bereit und kann somit eingerichtet werden.
Über das Menü ( **⋮** ) kannst Du Informationen des Produktes einsehen, sowie die Einrichtung dessen starten.

!!! info

    Ein registriertes Produkt kann mehrfach in Deiner Contao Instanz eingerichtet werden.

![product-installer.png](../../../assets/product-installer/product-products.png)

In der Einrichtungsmaske eines Produktes wird zunächst geprüft, ob alle Abhängigkeiten installiert und auf
dem neusten Stand sind. Ein Produkt kann mehrere sog. Inhaltspakete beinhalten, welche sich einzeln einrichten lassen.
Die Einrichtung kann über das Menü ( **⋮** ) des jeweiligen
Inhaltspaketes gestartet werden.

!!! warning

    Wir empfehlen vorerst stets die **schnelle Einrichtung** zu verwenden!

![product-installer.png](../../../assets/product-installer/product-setup.png)

Sobald die Einrichtung abgeschlossen ist, ist das Produkt installiert. Schließen Sie den _Product Installer_ und öffnen
Sie
die Live-Vorschau über das Contao Backend.
