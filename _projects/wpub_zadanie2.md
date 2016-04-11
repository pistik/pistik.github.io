---
layout: project
title: WPUB - 2. zadanie
year: 2016
languages: "DocBook, xml, xsl, XEP"
categories: wpub docbook
tags: [bachelor, docbook, xml]
---
<h2>Zadanie 2: Vytvorenie dokumentu vo formáte docbook</h2>
<br>
Predmetom 2. zadania bolo spracovanie vybraného dokumentu (v mojom prípade to bola bakalárska práca) z pôvodného OpenOffice formátu do formátu DocBook a vygenerovanie cieľového tvaru v PDF. Výsledný dokument má rozsah celkovo 17 strán, z toho polovicu tvorí generovaný obsah (Obsah, zoznamy obrázkov, tabuliek, Použítá literatúra a Register pojmov).

Pri písaní textu a jeho formátovaní som použil nasledovné časti kódu:

Pre zvýraznenie textu v odrážkach som použil tag emphasis:

```xml
<emphasis role="bold">
```
Vzhľadom k tomu, že bolo potrebné pripodobniť sa výsledným pdf dokumentom tomu pôvodnému, snažil som sa to docieliť aj samotným riadkovaním, toto som docielil len čiastočne na globálnej úrovni doplnením kódu do súboru thesis.xsl

```xml
<xsl:param name="line-height">1.5</xsl:param>
```
Pri spomenutí obrázkov v texte som v jednom prípade potreboval docieliť to, aby sa daný odkaz zobrazoval v súlade s kontextom, a teda nebolo pre mňa prípustné, aby daný obrázok pri samotnom vložení obsahoval nejaký popisok, ktorý by sa rovnako rozbrazoval všade, kde sa bude naň odkazovať. Tento problém som vyriešil tak, že pri odkazovaní sa na obrázok som hneď zadal aj popisok.

```xml
<xref linkend="pic.airdroid_web" xrefstyle="template:obrázku číslo %n"/>
```
V bakalárskej práci som využil aj tabuľku na porovnanie určitých parametrov a keďže táto tabuľka mala trinásť riadkov, potreboval som docieliť, aby sa zobrazila na iba jednej strane a nie aby presahovala cez dve strany. Pre tento prípad bolo potrebné nastaviť hodnotu atribútu v súbore thesis.xsl na allways.

```xml
<xsl:attribute name="keep-together.within-column">always</xsl:attribute>
```
