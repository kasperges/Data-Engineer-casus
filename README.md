# Casus 1 – Data Engineer Macro-economie

Onderwerp: Verwerking en opslag van CBS CPI-data, transformeren naar kwartaal data

Auteur: Kasper Hermanns

## Description

In dit project wordt data over de consumentenprijsindex (CPI) van een groot aantal product categorieen gebruikt. Deze zijn afkomstig van het CBS en zijn te bekijken op Statline: <https://opendata.cbs.nl/#/CBS/nl/dataset/83131NED/table?ts=1713952795072>

Deze dataset bevat al de maandmutaties van de CPI's, maar miste nog de mutaties per kwartaal. In dit project is er een automatische proces opgezet om deze data te transformeren naar kwartaal data voor de CPI en mutaties.

Met de functies hierin kunnen deze statistieken ook makkelijk geproduceerd worden voor specifieke producten en verslagperiodes. Een simpel voorbeeld is al voorgedaan waarin 3 producten vergelijken worden en in een grafiek gezet zijn.

## Benodigdheden

### Packages

```         
cbsodataR, tidyverse
```

Deze packages zijn allebei openbaar beschikbaar, cbsodataR is nodig om de CBS data in te laden en bevat handige functies en informatie over het werken met CBS data.

### Kennis

Daarbovenop is het handig om kennis te hebben van de codes die het CBS hanteert voor de productcategorieen en perioden. Deze kunnen uit de metadata van de tabel gehaald worden en staan ook deels in de Statline tabel.

## Proces

Het project volgt een typische Data Engineering pipeline:

1.  (Extract) de data van OData3
2.  (Transform) de data naar kwartaalcijfers
3.  (Enrich) de data door kwartaalmutaties toe te voegen
4.  (Analyze) de data door deze te plotten en met elkaar te vergelijken
5.  (Store) de data in een lokale SQLite database
