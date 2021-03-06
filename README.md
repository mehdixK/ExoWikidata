# Wikidata & Requêtes SPARQL

## Peintures de Claude Monet

### Requête 1

````sparql
SELECT *

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296.
  ?peinture wdt:P18 ?image. }
````

### Requête 2

````sparql
SELECT ?peinture ?image

WHERE {
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296.
  OPTIONAL { ?peinture wdt:P18 ?image. }
}
````

### Requête 3

````sparql
SELECT ?peinture ?image ?collection ?collectionLabel ?lieu ?lieuLabel

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296;
    wdt:P18 ?image.
  OPTIONAL { ?peinture wdt:P195 ?collection. }
  OPTIONAL { ?peinture wdt:P276 ?lieu. }
}
````

### Requête 4

````sparql
SELECT ?peinture ?image ?collection ?collectionLabel ?lieu ?lieuLabel

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296;
    wdt:P18 ?image.
  OPTIONAL { ?peinture wdt:P195 ?collection. }
  OPTIONAL { ?peinture wdt:P276 ?lieu. }
}

ORDER BY DESC (?count)
````
