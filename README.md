# Peintures de Claude Monet - Wikidata & Requêtes SPARQL

### Requête 1

SELECT *

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296.
  ?peinture wdt:P18 ?image. }

### Requête 2

SELECT ?peinture ?image

WHERE {
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296.
  OPTIONAL { ?peinture wdt:P18 ?image. }
}

### Requête 3

SELECT ?peinture ?image ?collection ?collectionLabel ?lieu ?lieuLabel

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296;
    wdt:P18 ?image.
  OPTIONAL { ?peinture wdt:P195 ?collection. }
  OPTIONAL { ?peinture wdt:P276 ?lieu. }
}

### Requête 4

SELECT ?peinture ?image ?collection ?collectionLabel ?lieu ?lieuLabel

WHERE {
  ?peinture wdt:P31 wd:Q3305213;
    wdt:P170 wd:Q296;
    wdt:P18 ?image.
  OPTIONAL { ?peinture wdt:P195 ?collection. }
  OPTIONAL { ?peinture wdt:P276 ?lieu. }
}

ORDER BY DESC (?count)
