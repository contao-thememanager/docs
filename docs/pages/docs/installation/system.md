# Systemanforderungen

Um den Contao ThemeManager zu nutzen, muss der Webserver die für Contao erforderlichen
[Systemvoraussetzungen](https://docs.contao.org/manual/de/installation/systemvoraussetzungen/) ab **Contao 4.13**
erfüllen, zusätzlich müssen auch folgende Anforderungen erfüllt sein.

## Software

Folgende Software muss auf dem Webserver installiert sein, damit der ThemeManager eingesetzt werden kann.

- **PHP**: Version 8.1+

Da der Contao ThemeManager das Contao CMS erweitert, muss Contao zunächst komplett installiert und aufgesetzt sein.
Empfohlen wird bei der Nutzung die [Managed Edition](https://contao.org/de/download).

## Unterstützte Contao-Versionen

Unterstützte Contao-Versionen werden nachfolgend aufgelistet.
Grundsätzlich wird immer die aktuelle [Long-Term-Support-Version](https://contao.org/de/release-plan) von Contao
supportet.

| Version    |               Support |
|------------|----------------------:|
| 4.13 (LTS) |                     ✅ |
| 5.0        |                     ❌ |
| 5.1        | (Support eingestellt) |
| 5.2        |                     ✅ |
| 5.3 (LTS)  |        (Februar 2024) |

## Benötigte PHP-Erweiterungen

| Name der Erweiterung                                                                                                        |                                              |
|-----------------------------------------------------------------------------------------------------------------------------|----------------------------------------------|
| <a href="https://www.php.net/manual/de/book.simplexml.php" class="highlight">SimpleXML</a><br/>(<code>ext-simplexml</code>) | **erforderlich**                             |
| <a href="https://www.php.net/manual/de/book.image.php" class="highlight">GD</a><br/>(<code>ext-gd</code>)                   | **erforderlich**                             |
| <a href="https://www.php.net/manual/de/book.imagick.php" class="highlight">Imagick</a><br/>(<code>ext-imagick</code>)       | erfordert GD, <br/>Imagick oder <br/>Gmagick |
| <a href="https://www.php.net/manual/de/book.gmagick.php" class="highlight">Gmagick</a><br/>(<code>ext-gmagick</code>)       | erfordert GD, <br/>Imagick oder <br/>Gmagick |

## Symfony und Contao-Erweiterungen

| Name der Erweiterung                                                                                                        |        Version |
|-----------------------------------------------------------------------------------------------------------------------------|---------------:|
| [oveleon/contao-component-style-manager](https://packagist.org/packages/oveleon/contao-component-style-manager)             |         ^3.4.1 |
| [oveleon/contao-theme-compiler-bundle](https://packagist.org/packages/oveleon/contao-theme-compiler-bundle)                 |           ^1.7 |
| [oveleon/contao-config-driver-bundle](https://packagist.org/packages/oveleon/contao-config-driver-bundle)                   |         ^1.3.1 |
| [madeyourday/contao-rocksolid-custom-elements](https://packagist.org/packages/madeyourday/contao-rocksolid-custom-elements) |           ^2.4 |
| [madeyourday/contao-rocksolid-icon-picker](https://packagist.org/packages/madeyourday/contao-rocksolid-icon-picker)         |         ^2.1.2 |
| [symfony/filesystem](https://packagist.org/packages/symfony/filesystem)                                                     | ^5.4 oder ^6.0 |
