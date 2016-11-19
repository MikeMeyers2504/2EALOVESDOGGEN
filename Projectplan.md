# Internet of Things - PlateGate
Documentatie voor het project voor het vak Internet of Things.

Groep 4

## Projectplan 

### Inhoudstabel:
* Teamleden
* Project keuze
* Projectbeschrijving
	* Probleemstelling
	* Doel van het project
	* Methodologie
	* Verwachte resultaten
	* Eigen relevante toevoegingen
	* Raspberry Pi
	* Arduino
* Functionele analyse
	* Technologieën
	* Inventarisatie hardware
	* High level diagrammen
	* Project planning
	* Backlog
	* Story
	* In progress
	* Closed
	* Planning 

### Teamleden (Github account):
* Mike Meyers (MikeMeyers2504)
* Kayode Aina (KayAina)
* Bryan Lameir (LameirBryan)

### Project keuze:
PlateGate 

### Projectbeschrijving

#### Probleemstelling
Elk jaar zijn er wel evenementen georganiseerd waar er een menigte naar toe komt. De mensen die toegestaan zijn om het traject te betreden worden de bevoegde personen genoemd. Deze willen gebruik maken van de parking van het evenement, maar dan moeten ze eerst door de eigenaar tijdelijk als zodanig bevoegd worden gedeclareerd. Als hij dat niet doet, gaat de parking niet open en kunnen ze er dus niet op. 

#### Doel van het project
Het doel van dit project is om ervoor te zorgen dat mensen die normaal gezien geen toegang hebben tot een bepaalde parking tijdelijk bevoegd worden om deze parking te kunnen betreden. 

#### Methodologie
We zijn met elk lid van onze groep gaan samenzitten. Hier hebben we alles wat we gaan gebruiken en ook hoe we het gaan aanpakken besproken. We hebben een planning gekregen waar verschillende opdrachten in staan. Deze dienen tegen de voorziene datums in orde gebracht te worden. We hebben de taken wat verdeeld, zodat ieder van ons al verder kan. Aangezien we moeten werken met de Raspberry Pi en niemand van ons hierin al wat ervaring heeft, hebben we onderling afgesproken om hierover wat research te doen. Elk component (raspberry pi met bluetooth dongle en WiFi, raspberry pi met de camera, arduino voor de ledjes, servomotor, sensoren en bluetooth module) gaan we testen zodat we zeker weten dat alles afzonderlijk al werkt. Als dat in orde is, gaan we alle code van de hardware stuk voor stuk samenvoegen. Vervolgens word er een database opgezet en we laten deze verbinding maken met onze website. Zo kunnen we aan de gegevens van de database. Er word een website ontwikkeld waarop de eigenaar van het evenement de bevoegde personen kan contacteren. Hierdoor kunnen die dan gebruik maken van de parking. We werken met scrum. Dit is een softwareontwikkelmethode. Het bestaat uit 4 sprints, elk uit een aantal weken. Binnenin een sprint worden dan taken verdeeld zodat we op het einde aan de volgende sprint kunnen beginnen. Zo weet elk teamlid wat hij moet doen. Zodat op het einde van de laatste sprint we tot een mooi resultaat komen van ons project.                 

#### Verwachte resultaten
Onze verwachte resultaten zijn:
* De contactpersoon/eigenaar van het evenement gaat de bezoekers registreren, om hun zo toegang te verlenen. 
* Als je dan toekomt met je auto, is er een sensor voorzien die gaat detecteren wanneer deze passeerd. Enkele seconden later neemt de camera een foto van de nummerplaat. Deze foto gaat dan verwerkt worden met de openALPR library tot data, en word dan vergeleken met de database. Als blijkt dat deze persoon toegang heeft, dan zal de slagboom open gaan, zoniet blijft deze dicht.
* Het display dient om de gegevens die bij de nummerplaat horen weer te geven.
* Er is ook nog een failsafe (toetsenbord) voorzien, zodat de persoon de nummerrplaat handmatig kan invoeren als de camera niet zou werken. 
* Als de nummerplaat geregistreerd is als bezoeker, gaat de contactpersoon verwittigd worden via de website.

#### Eigen relevante toevoegingen:
* Bezoeker aanwezig of afwezig
* Laat het aantal auto's zien op de parking
* Extra sensor voor het sluiten van de slagboom of poort
* Parkeerplaatsen voorzien van infrarood sensors
* Notificatie voor gereserveerde parkingplaatsen
* Leds die laten zien of de parking al bezet is of niet

#### Raspberry Pi:
* Nemen van een foto
* Verwerken van een foto tot bruikbare data met behulp van openALPR library
* Communiceren met de database
* Communiceren met de website
* Communiceren met de arduino via bluetooth

#### Arduino:
* Aansturen van de ledjes
* Lezen van de sensoren
* Aansturen van de servomotor
* Communiceren met de Raspberry Pi via bluetooth

### Functionele analyse:

#### Technologieën
* Hardware: 
	* Raspbian (Raspberry Pi)
		* Operating system
	* Python (Raspberry Pi)
		* Code taal die we gebruiken voor de camera en de verbinding te programmeren 
	* C++ (Arduino Uno)
		* Code taal die we gebruiken om de Arduino Uno te programmeren 

* Software: 
	* HTML
		* HyperText Markup Language die we gebruiken voor de website
	* CSS/Bootstrap
		* Gebruiken we voor de styling van de website	
	* Javascript
		* Gebruiken we voor de functies van de website
	* MySQL database
		* Gebruiken we voor de database
	* AngularJS
		* Gebruiken we om makkelijk te ontwikkelen in javascript 
	* NodeJS
		* Gebruiken we als backend voor de webserver
	* ExpressJS
		* Gebruiken we voor de servers in te stellen van de website

#### Inventarisatie hardware
* Infrarood sensoren voor detectie auto
* Raspberry Pi
* Raspberry Pi camera module
* Raspberry Pi bluetooth dongle
* Raspberry Pi WiFi
* Toetsenbord voor failsafe 
* Display
* Servomotor
* Arduino Uno
* Bluetooth module (HC-05)
* Ledjes

#### High Level Diagrammen
* Registratie
![alt text](https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/blob/Tussentijds1/doc/FlowChards/Flow1.PNG "Flow1")
* Algemene werking
![alt text](https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/blob/Tussentijds1/doc/FlowChards/Flow2.PNG "Flow2")

#### Project planning
* https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/tree/Tussentijds1#boards?repos=68706070
* https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/projects

#### Backlog
* Portfolio bijwerken
* Eindportfolio in orde brengen
* Eindpresentatie maken
* Release printplaat V2
* Demo voorbereiden
* Release code V2
* Code servomotor V2
* Code infrarood sensoren V2
* Code camera module V2
* Database opzetten
* Website stylen
* Website programmeren
* Connectie database met website
* Connectie tussen software en hardware 

#### Story
* Bluetooth (Epic)
* Code bluetooth module arduino
* Code bluetooth module Raspberry Pi
* Mergen
* Portfolio bijwerken

#### In progress
* Camera module (Epic)
* Code camera module

#### Closed
##### Normal issues
* Groep maken en keuze project
* Servomotor onderzoeken
* Infrarood sensor onderzoeken
* Alles converteren naar issues
* Flowcharts maken
* Scrumplan maken
* Code infrarood sensors
* Code servomotor
* Indienen projectplan (afgewerkte versie)
* Projectplan maken in markdown
* Demo voorbereiden examenweek
* Release PCB 1
* Camera module onderzoeken
* Raspberry Pi basics onderzoeken
* Arduino bluetooth onderzoeken
* Design PCB
* Raspberry Pi bluetooth module onderzoeken
* Release code V1

##### Epic issues
* Voorbereiding examenweek 
* PCB sprint 2 
* Scrumplan in orde maken 
* Projectplan in orde maken 
* Infrarood sensoren 
* Servomotor 

#### Planning:
* Sprint 1
![alt text](https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/blob/Tussentijds1/doc/Screenshots/Sprint1.PNG "Sprint 1")
* Sprint 2
![alt text](https://github.com/AP-Elektronica-ICT/iot16-plate-gate-mbk/blob/Tussentijds1/doc/Screenshots/Sprint2.PNG "Sprint 2")