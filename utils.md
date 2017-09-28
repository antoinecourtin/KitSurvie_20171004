## Atelier Kit de survie - 4 octobre 2017
### Trucs et astuces utiles pour suivre les ateliers


##### Pour wikidata
* URL du SPARLEndpoint de Wikidata pour utiliser Palladio
https://query.wikidata.org/bigdata/namespace/wdq/sparql
* Exemple de requête SPARQL pour Wikidata
https://gist.github.com/antoinecourtin/39b313d4b0cdaa1df3b6f2a3ddbfc3a5
https://gist.github.com/antoinecourtin/149401410f486372ffb1958ead9f0264
* Adresse pour paramétrer l'outil de réalignement avec wikidata dans OpenRefine
https://tools.wmflabs.org/openrefine-wikidata/fr/api


#### Adresses de téléchargement d'OpenRefine et de plugin
https://github.com/fadmaa/grefine-rdf-extension/releases
http://refine.codefork.com/reconcile/viaf
https://www.bits.vib.be/index.php/software-overview/openrefine
https://github.com/RubenVerborgh/Refine-NER-Extension
https://github.com/sparkica/refine-stats


##### Quelques exemples de "formule" utiles dans OpenRefine

* rajouter une valeur fixe à une table : "test" + ", " + cells['UNIQUE_KEY'].value
* exemple pour faire un rechercher/remplacer : value.replace("[MotRecherché]","[MotLeRemplaçant]")
* Enlever tout sauf les chiffres" : replace(value,/[[a-z],[A-Z],(é|è|à|ù),\,\;\:\.\?\/\!\=\+\"\'\-\(\)\[\]]/,"")
* Extraction d'une date de type aaaa : value.match(/.*(\d{4}).*/)[0]
* Calculer des longueurs de chaînes : value.length()
* Compter les mots d'une chaîne : value.split(/\b/).length()
* Supprimer les espaces superflus d'une chaîne : value.trim()
* Transformer des caractères spéciaux HTML (ex: &eacute;) : Edit cells > Common transform > Unescape HTML entities
* extration des parenthèse : value.match(/.*(\(.*\)).*/)[0]
* appeler une API via la fonction Fetching URL: "http://maps.google.com/maps/api/geocode/json?sensor=false&address=" + escape(value, "url")
* Extraitre une info dans un json (lattitude) issue d'une requête à une API : value.parseJson().results[0].geometry.location.lat
* Extraire l'id de wikidata après le réalignement: cell.recon.match.id
* Template pour croiser 2 jeux de données = cell.cross("My Address Book", "friend")[0].cells["address"].value
=> cell.cross("nomduprojet", "nomColonneeCléIntermédiaire")[0].cells["nomColonneArécupérer"].value
