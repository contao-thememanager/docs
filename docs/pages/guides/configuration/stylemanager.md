---
title: StyleManager
---

# Einleitung


## StyleManager-Auswahl für Layout-Bereiche

Mit Version [`2.2.17`](https://github.com/contao-thememanager/core/releases/tag/2.2.17) wurde das `fe_page` Template
überarbeitet, sodass Klassen innerhalb der Bereiche `<header>`, `<main>` und `<footer>` vergeben werden können.
Folgende xml kann im `/templates` Ordner abgelegt und entsprechend modifiziert werden, sodass Optionen für Header, Main
und Footer im Layout hinzugefügt werden können: 

```xml title="templates/stylemanager-foo.xml"
<?xml version="1.0" encoding="UTF-8"?>
<archives>
  <archive identifier="gHeader">
    <field title="identifier">gHeader</field>
    <children>
      <child alias="foo">
        <field title="pid">60</field>
        <field title="sorting">100</field>
        <field title="alias">foo</field>
        <field title="title">Foo</field>
        <field title="description">Foo</field>
        <field title="cssClasses">a:1:{i:0;a:2:{s:3:"key";s:3:"foo";s:5:"value";s:3:"Foo";}}</field>
        <field title="chosen">1</field>
        <field title="blankOption">1</field>
        <field title="passToTemplate">1</field>
        <field title="extendLayout">1</field>
      </child>
    </children>
  </archive>
  <archive identifier="gMain">
    <field title="identifier">gMain</field>
    <children>
      <child alias="foo">
        <field title="pid">70</field>
        <field title="sorting">100</field>
        <field title="alias">foo</field>
        <field title="title">Foo</field>
        <field title="description">Foo</field>
        <field title="cssClasses">a:1:{i:0;a:2:{s:3:"key";s:3:"foo";s:5:"value";s:3:"Foo";}}</field>
        <field title="chosen">1</field>
        <field title="blankOption">1</field>
        <field title="passToTemplate">1</field>
        <field title="extendLayout">1</field>
      </child>
    </children>
  </archive>
  <archive identifier="gFooter">
    <field title="identifier">gFooter</field>
    <children>
      <child alias="foo">
        <field title="pid">80</field>
        <field title="sorting">100</field>
        <field title="alias">foo</field>
        <field title="title">Foo</field>
        <field title="description">Foo</field>
        <field title="cssClasses">a:1:{i:0;a:2:{s:3:"key";s:3:"foo";s:5:"value";s:3:"Foo";}}</field>
        <field title="chosen">1</field>
        <field title="blankOption">1</field>
        <field title="passToTemplate">1</field>
        <field title="extendLayout">1</field>
      </child>
    </children>
  </archive>
</archives>
```
