# Opdrachtbeschrijving Model/Repository

## Inleiding

Je bent net begonnen als developer bij een bedrijf genaamd Tech It Easy, dat TV's verkoopt. Tijdens de cursus Spring Boot ga jij een backend applicatie voor hen programmeren. De winkel heeft een inventaris van televisies die moet worden bijgehouden. Na iedere les gaan we deze applicatie een stukje verder uitbouwen in de vorm van huiswerk. Zo krijgen we stap-voor-stap meer ervaring in het bouwen van een backend applicatie. Aan het einde van de cursus zullen we een werkende Tech It Easy backend hebben!

## Recap van vorige opdracht

Je hebt de [vorige les](https://github.com/hogeschoolnovi/backend-spring-boot-tech-it-easy-controller-uitwerkingen) een begin gemaakt voor de applicatie voor je werkgever TechItEasy. Je hebt een controller aangemaakt met verschillende endpoints. Deze kunnen aangeroepen worden via een frontend. Jij maakt hiervoor gebruik van Postman. Omdat we niet weten of alles bestaat wat de gebruiker opvraagt heb je ook een exception controller gemaakt en een RecordNotFound exception. Na een nieuwe les Spring boot ben je klaar voor de volgende stap van het bouwen van je applicatie. 

## Randvoorwaarden

- Het project bevat, op de juiste plaats in de map-structuur, een map genaamd `models`;
- Het project bevat, op de juiste plaats in de map-structuur, een map genaamd `repositories`;
- Het project bevat een `Television` in de map `models`;
- Het project bevat een `TelevisionRepository`;
- Het project bevat de volgende dependencies: 
  - `Spring Web`
  - `Spring Data Jpa`
  - `PostgreSQL Driver`
- De **Application.properties** bevat de properties uit hoofdstuk 5.3 van de cursus Spring Boot(met aangepaste namen)
- De **TelevisionRepository** extends JpaRepository met de juiste parameters
- De **Television** bevat:
  -de attributen:
    - Long id (incl. annotaties id en generatedValue)
    - String type
    - String brand
    - String name
    - Double price
    - Double availableSize
    - Int refreshRate
    - String screenType
    - String screenQuality
    - Boolean smartTv
    - Boolean wifi
    - Boolean voiceControl
    - Boolean hdr
    - Boolean bluetooth
    - Boolean ambiLight
    - Integer originalStock
    - Integer sold
  - default constructor
  - constructor
  - alle getters en setters
  
### Belangrijk
- Laat de _application.properties_ overeenkomen met de gegevens van `PgAdmin`
- Je mag de volgende ResponseEntiteiten als return waardes gebruiken:
  - `ResponseEntiteit.ok(television)`
  - `ResponseEntiteit.created(null).body(television)`
  - `ResponseEntiteit.noContent().build()`
- Let er op dat je database-password niet hetzelfde password is dat je gebruikt voor je email, facebook of andere applicatie. Aangezien deze applicatie niet gedeployed hoeft te worden, kun je een makkelijk password kiezen als "password" of "banaan".

## Stappenplan
_Let op_: het is uitdagender om jouw eigen stappenplan te maken. Mocht je niet zo goed weten waar je moet beginnen, kun je onderstaand stappenplan volgen:

1. Voeg de benodigde dependencies toe aan je _POM.xml_ en laat `Maven` deze installeren
2. Voeg aan de _application.properties_ de benodigde properties toe
3. Maak een nieuwe database aan in `PgAdmin` (zorg dat je _application.properties_ overeenkomt met de naam, password en user van de database)
4. Maak een nieuwe map aan in je project voor `models`
5. Maak een nieuwe klasse genaamd `Television`
6. Voeg de annotatie **@Entity** toe aan de klasse
7. Voeg de juiste _attributen_ toe aan de klasse
8. Voeg de beide _constructors_ toe aan de klasse
9. Voeg alle _getters & setters_ toe aan de klasse
10. Maak een nieuwe map aan in je project voor `repositories`
11. Voeg aan deze map een nieuwe Interface toe genaamd `TelevisionRepository`
12. Extend de _repository_ met de `JpaRepository` en geef de juiste attributen mee. (het type van het model en het type van het ID)
13. Pas de methodes in je controller aan zodat deze gebruik maken van de Television klasse en de repository.
14. Test je applicatie met postman en pgadmin. Kijk of je echt televisies kunt opslaan, ophalen, aanpassen en verwijderen.

## Bonus
Een television heeft best veel variabelen, maar er zit nog weinig variatie in de types. Het zijn enkel Strings, Booleans of nummers. Probeer andere datatypes te gebruiken zoals:
- een Datum voor sold (verkoopDatum) of originalStock (inkoopDatum) (er zijn in Java verschillende opties om een datum te maken)
- Een enumeratie voor een of meerdere van availableSize, refreshRate, screenType en screenQuality
- Zoek zelf op Baeldung, W3, GeeksForGeeks, etc op hoe je zulke datatypes maakt.
- Let er ook op hoe dit in je database komt te staan, is dit anders dan andere datatypes?
- Let er ook op dat je deze datatypes goed in postman invoert. Ook dit kun je op internet vinden, maar kun je ook met de ouderwetse gis-en-mis-methode vinden.

 _Let op: je mag ook andere types proberen, maar je kunt (nog) geen lijsten of andere soorten collecties gebruiken. Elke variabele wordt een kolom in de databasetabel. In zo'n kolom kan maar 1 waarde staan, niet een hele lijst van waardes._
