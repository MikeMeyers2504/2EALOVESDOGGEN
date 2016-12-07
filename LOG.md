# Logboek **Michael Marivoet**

## Week 1 (15/02/16 - 21/02/16)
### Maandag
* Allereerst verdere kennismaking met stagementor, krijgen van een RFID kaart voor toegang tot het gebouw en login gegevens verkregen voor het WiFi netwerk. Verder kreeg ik een presentatie waarin
uitgelegd staat wat Agentschap Wegen & Verkeer/EMT hun functie is binnen de Vlaamse overheid. Nogmaals bespreken/verduidelijken wat er juist allemaal voor functionaliteit verwacht wordt van het project, bekijken wat de stagair
vorig jaar bereikt heeft. Ook is er besproken welke technologieën er gebruikt zullen worden (zie algemene README).
* Arduino code bekeken van vorig jaar en deze al lichtjes aangepast. 

### Dinsdag
* Verder bekijken van het python script van de Raspberry Pi, bekijken hoe we een deurslot zouden kunnen simileren en wat we hiervoor nodig hebben.
* Verder gewerkt aan het herwerken van Arduino code, deze afgewerkt, commentaar toegevoegd over de werking en deze getest of de commando's wel doorkomen.
* Uitzoeken hoe we best data van de analoge pinnen opslaan, zodat we die later kunnen opvragen en tonen in bijvoorbeeld een grafiek (in de frontend).

### Woensdag
* Instellen van de raspberry pi voor SSH en de bestaande python scripts bekijken. Uittesten bestaande code en zien hoe juist en wat er precies door de eReader wordt ingelezen en hoe
Artur dit verwerkt/oplost.
* Ook zitten uitdenken hoe we eventueel de admin accounts laat aanmaken voor de webapplicatie door het inlezen van de eID, waardoor deze geen formulier zou moeten invullen.
* Bekijken van de tutorials omtrent een video gesprek met een Raspberry Pi en een webbrowser, die Rik heeft doogestuurd gisteren.
* In de namiddag wilt de Raspberry Pi niet meer via SSH verbinden en mits ik geen HDMI kabel bij heb. Nog zitten proberen uit te zoeken hoe dit komt, zal ik morgen rechtstreeks bekijken wat het probleem is.

### Donderdag
* Op de virtuele server alle benodigdheden gëinstalleerd (LAMP stack, nodejs, phpmyadmin, etc.).
* Bekijken hoe we communicatie tussen Raspberry Pi en server best kunnen doen, hiervoor onderzoek gedaan omtrent MQTT, CoAP & AMQP protocol.
* Raspberry Pi probleem omtrent SSH was opgelost bij de volgende boot, voor de zekerheid heb ik deze rechstreeks verbonden met
het internet en alles geupdate.
* Verder gelezen omtrent artikels video gesprek & bekijken van het aansluiten van de webcam.

### Vrijdag
* Les: Professionalisering

## Week 2 (22/02/16 - 28/02/16)
### Maandag
* Aanpassing aan arduino seriële commando met oog op het gebruikt van MQTT.
* Verder onderzoek gedaan omtrent MQTT op Raspberry Pi en nodejs. Onderzocht of Node-Red kan gebruikt worden om makkelijker te ontwikkelen.
* Artikel van Rik gelezen omtrent mogelijk gebruik van HTSQL voor het weergeven van data op de webpage.
* Nagedacht over indeling van de tabellen in de MySQL database (opstellen schema later).
* Node-mysql doorgenomen.

### Dinsdag
* Laatste voorlopige aanpassingen aan Arduino code en nog de nodige uitleg over code toegevoegd.
* Nodige Node dependencies geïnstalleerd en Node test projectje gemaakt.
* Onderzoek gedaan naar gebruikers authenticatie met Node en de modules die hiervoor gebruikt kunnen worden.
* Raspberry Pi scipt bekeken en geraak nog altijd niet 100% uit aan de werking. Hiervoor heb ik een e-mail gestuurd naar mijn voorganger.

### Woensdag
* Verder onderzoek gedaan omtrent Raspberry Pi & eID kaart lezen, a.d.h.v. de informatie die ik heb verkregen van mijn voorganger en stagementor. Wou de werking begrijpen vooraleer ik verder ging.
* Opgezocht voor het aanmaken van cron jobs (Raspberry Pi) & daemons.
* Onderzoek gedaan omtrent socket.io voor nodejs, dat in combinatie met MQTT realtime informatie kan geven aan de webclient omtrent de status van de RaspberryPi.

### Donderdag
* Database aangemaakt voor gebruikers en die properties dat deze moet bevatten.
* Mosquitto (MQTT) broker geïnstalleerd op server
* Onderzoek gedaan naar Eclipse paho project, deze biedt een subscriber/publisher libraries aan voor zowel python (Raspberry Pi) als javascript (webapplicatie).

### Vrijdag
* Les: Professionalisering

## Week 3 (29/02/16 - 06/03/16)
### Maandag
* Onderzoek gedaan omtrent het vervangen van de MySQL server op de Raspberry Pi.
* Het aanpassen van de python scripts van mijn voorganger. Dit resulteerde door een onbekende reden in corruptie van de 2de partitie (waar commandfile zich bevindt).
* Tijdens het aanpassen van de python scripts viel de Raspberry Pi uit, na het herstarten van de Raspberry Pi kreeg ik een foutmelding terug en starte hij kdb (kernel debugger) op. De foutmelding gaf weer dat 
hij zijn boot partitie niet meer kon uitlezen. Na enkele artikels te lezen over de foutmelding op het Raspberry Pi forum, kwam ik tot de vaststelling dat GParted of fsck de mogelijkheid bieden om partities 
na te kijken en deze te repareren indien nodig. Hiervoor had ik dus Linux nodig en heb ik deze geïnstalleerd, het gebruiken van deze tools om de partitie op de SD kaart te repareren heeft niet geleidt tot 
resultaten. Hierna heb ik besloten in consensus met mijn stagebegeleider om met een schone lei te beginnen en dus een nieuwe image te installeren voor de Raspberry Pi.

### Dinsdag
* Verder gewerkt aan het repareren/formateren van het microSD kaartje en tot de consensus gekomen dat deze niet meer bruikbaar is, men kan enkel nog van het
kaartje lezen. Na hierover nog verder onderzoek te doen heb ik ontdekt dat dit waarschijnlijk het resultaat is van het bereiken van de maximum
schriijf cycli, hierdoor zet de microSD kaart zich in read only. Ik heb de volgende tools gebruikt om de partities te verwijderen, repareren en formateren.
Diskpart (via windows commandprompt), windows schijfbeheer, fsck (linux), Gparted (linux) &  SDFormatter v4.
* Verder ben ik ook begonnen aan het ontwikkelen van de webapplicatie zijn layout, dit heb ik gedaan terwijl de verschillende programma's/tools bezig waren
met de microSD kaart.

### Woensdag
* Nogmaals geprobeerd de microSD kaart te formatteren met diskpart, nogmaals geen resultaat. Hierna een test gedaan met een ander microSD kaartje waarop een nieuwe image van raspbian staat,
de Raspberry Pi had geen probleem hiermee te booten. Hierna besproken met de stagementor om een nieuwe microSD kaart aan te kopen.
* Mosquitto broker op server uitgetest en goede publisher/subscriber programma voor te testen gezocht en gevonden in de vorm van MQTT.fx, deze beschikt over een simpele en makkelijk GUI.
* Verder gewerkt aan frontend. Sticky footer toegevoegd en bezig geweest met het laden van de gewenste html code in een container d.m.v. angularjs.

### Donderdag
* Verder gewerkt een Raspberry Pi terug opnieuw te installeren (Raspbian Jessie lite image geinstalleerd) SSH enabled, python terug geïntalleerd, XFCE desktop (zonder goodies/extra programma's), etc.. 
Had hier wel enkele problemen met onder andere python te installeren, mits de Raspbian lite image ontbrekende dependencies had (hierdoor kon python, XFCE, etc. niet geïnstalleerd worden).
* Scripts van voorganger gerecupeerd en terug begonnen vanaf het begin met eigen python scripts en de scripts van de voorganger aan te passen.

### Vrijdag
* Les: Professionalisering

## Week 4 (07/03/16 - 13/03/16)
### Maandag
* XFCE verwijderd en LXDE geïnstalleerd, wegens problemen met Xming (reageerde zeer slecht en traag). Ik heb ook na onderzoek vernomen dat XFCE meer resources verbruikt dan LXDE.
* Python libraries geinstalleerd om te kunnen werken met smartcard reader (pyscard), sqlite databases, gpio pinnen raspberry & paho mqtt client. Doordat de ACSCCID driver ontbreekte kon ik nog niet
de pyscard libarary installeren, dze gave de error dat 'winscard.h' ontbreekte.
* Onderzoek gedaan omtrent het gebruiken van systemd om python scripts te doen starten bij het opstarten en ervoor te zorgen dat deze blijven werken bij een onderbreking of probleem.
* Installeren dependency voor smartcard reader library. ACSCCID, dit is een driver voor linux die het mogelijk maakt om met ACS CCID kaartlezers te communiceren. Ik kon deze driver niet installeren
omdat er dependencies waren die de driver nodig had en die ontbreken op het systeem. Dit werdt niet vermeld in het verslag van mij voorganger. Ik ben deze verder bezig geweest met het uitzoeken van welke
dependencies er ontbreken. 

### Dinsdag
* Verder gedaan met het uitzoeken naar ontbrekende dependencies, uiteindelijk bleken de volgende dependencies nodig te zijn:
    * **pcscd:** dit is een smart card deamon voor pcsc-lite. Het laat toe programma's toe om te communiceren met smartccard readers zondat dat deze details nodig heeft over de kaart of lezer.
    * **libusb:** c-library die toelaat programma's toegang te geven aan USB-apparaten.
* De reden waarom deze dependencies niet vermeld werden in de handleiding van mijn voorganger is omdat ik gebruik maakt de de *lite* image van Raspbian Jessie.
* Tijdens het installeren van de pyscard library via pip/PyPA (python package manager) deedt er zich een onbekende error voor en wou deze zich niet installeren. Na verder onderzoek bleek dat er een bug was
die ervoor zorgde dat als setup.py automatisch via pip wordt uitgevoerd deze de installatie niet correct uitvoerde. Om dit op te lossen moet de library handmatig worden gedownload en geïnstalleerd worden.
Dit stond vermeld op de blog van de ontwikkelaar.

### Woensdag
* Jobbeurs expo antwerpen

### Donderdag
* Testen of de smartcard reader werkt met de Raspberry Pi. Deze werkt nog altijd niet 100% wegens nog een onbekende ontbrekende dependency.
* Nog wat verder gewerkt aan frontend en angular-ui router toegevoegd, dit maakt het handig om kleinde stukken html code zeer makkelijk in te laden in een view.
* Begonnen aan backend met express. Hiervoor heb ik onder andere de package.json aangemaakt (zodat backend makkelijk opnieuw kan gegenereerd worden). Gezocht naar mqtt client v
* Uitwerken van topic generatie (mqtt) voor elke Raspberry Pi.

### Vrijdag
* Vrijaf genomen

## Week 5 (14/03/16 - 20/03/16)
### Maandag
* Verder gezocht naar het oplossen van de ontbrekende dependency voor de smart card reader. Ik heb uiteindelijk hiervoor een tutorial gevonden van Gemalto, deze produceert smart card readers
en heeft hiervoor een tutorial document gemaakt. [Link Tutorial](http://support.gemalto.com/fileadmin/user_upload/IAM/FAQ/How_to_install_the_PC-Link_reader_on_Linux.pdf)
* Ik heb ook de tools geïnstalleerd die in de tutorial stonden voor het nakijken of de smart card werkt.

### Dinsdag
* Getest met de tools die ik maandag had geïnstalleerd of de smart card reader wekte, deze functioneerde correct en ik kon mijn eigen eID uitlezen.
* Script voor het uitlezen van het nationaal nummer ontwikkelt door mijn voorganger overgekopieerd en aangepast.
* Onderzoek gedaan op de [sourceforge pagina](http://pyscard.sourceforge.net/) van pyscard of er een manier was om enkel belgische eID kaarten uit te lezen. Dit bleek mogelijk te zijn door de
smart card reader eerst de ATR (Answer To Reset) te lezen van de smartcard en na te kijken of deze een belgische eID is. Hierna zullen de commando's voor het uitlezen van het nationaal nummer worden uitgevoerd.

### Woensdag
* Script voor de smartcard aangepast door het implementeren van het nakijken ATR voor we het nationaal nummer uitlezen. Hierna heb ik de code getest met mijn eID en deze functioneerde perfect.
* Verder heb ik een functie in de pyscard library gevonden die een vorm van event listener implementeert. Deze laat het script slapen tot er een geldige kaart in de reader wordt geplaats. Dit is beter dan mij
origineel idee om elke seconde te gaan pollen of er een kaart aanwezig is, hierdoor voelt het voor de gebruiker aan of alles spontaan werkt in plaats van met een delay.
* Masterscript aangemaakt en hiervoor een service voorzien in  systemd, zodat deze automatisch opstart met het besturingssysteem en er een watchdog aanwezig is om het script te herstarten bij eventueel falen.

### Donderdag
* Onderzoek gedaan naar threading met python. Python beschikt over een threading libary die ook over een timer beschikt.
* Onderzoek gedaan naar een goede python config parser, om gemakkelijk een config file aan te maken en uit te lezen. Uiteindelijk bleek python standaard over een configparser te beschikken die perfect 
voldoet aan wat ik nodig heb.
* Test script om communicatie met de Arduino uit te testen geschreven. Deze communicatie gebeurt over een seriële verbinding.

### Vrijdag
* Les: Professionalisering

## Week 6 (21/03/16 - 27/03/16)
### Maandag
* Opgezocht wat de wettelijke minimum eisen zijn rondom het opslagen van het nationaal nummer. De wetgeving zegt dat Belgische openbare overheden het nationaal nummer wel mogen gebruiken en opslaan.
Men heeft wel vermeld in de opdracht dat het nationaal nummer niet in "plain-text" mag gedaan worden. Als oplossing heb ik hiervoor gevonden dat ik de nationaal nummers hash met (sha512) en dat ik
voor veiligheidsreden alleen de gehashte nationale nummers verstuur naar de database op de Raspberry Pi zonder overige informatie van de gebruiker.
    [Bron 1](http://economie.fgov.be/nl/binaries/eID-IBM_study_nl_tcm325-73359.pdf)
    [Bron 2](https://www.privacycommission.be/sites/privacycommission/files/documents/beraadslaging_RR_09_2013.pdf)
* Hierna heb ik het volgend zitten implementeren in het python script. Het nationaal nummer dat wordt uitgelezen door de smartcard reader wordt gehasht met sha512 hierna wordt er gekeken in de 
database of deze hash voorkomt. Indien deze statement is voldaan, dan zal de deur geopend worden. 

### Dinsdag
* Verder gedaan aan het implementeren van toegang tot installatie met eID. Ik had hier een probleem met toegang te krijgen tot de SQlite database op de Raspberry Pi, dit is opgelost
door eerst dit script te testen en schrijven op mijn eigen PC in plaats vand de Raspberry Pi.
* Script nog wat opgekuist, commentaar toegevoegd en wat extra functionaliteit. Zoals onder andere als men 3x een niet toegestande eID gebruikt, zal de installatie 1 minuut geen validatie toelaten.

### Woensdag
* Verder onderzoek gedaan rondom multithreading met Python en wat de beste praktijken omtrent hiervan zijn. Multithreading geimplementeerd voor het "card_reader script" en "pin_status script".
Het pin status script, verzend de status van de analoge en digitale pinnen naar de server.
* Ondervonden dat er een probleem is met systemd service, deze voert het script niet uit bij het booten, hiervoor heb ik onderzoek gedaan waarom dit kwam. Systemd geeft de error status '203' terug.
Dit zou komen door verschillende problemen, onder andere met de rechten die de file heeft, de volgende oorzaken heb ik al bekeken/opgelost.
    * File kan niet uitgevoerd worden door ontbrekende rechten => chmod +x gebruikt om bestand rechten te geven, dit haalde niets uit.
    * Geen shebang aanwezig in het script => shebang is/was aanwezig.
    * ExecStart aangepast met verwijzing naar python interpreter => dit haalde niets uit.
    * Bestand bevond zich in de Desktop van de Pi user ik heb deze verplaats naar een eigen directory na root => dit haalde niets uit.
* Ik hoop dit probleem op te lossen door dit hiervoor een post op stackoverflow te plaatsen.

### Donderdag
* Begonnen aan het database update script, dit script doet een aanvraag aan de server of er al nieuwe gebruikers zijn sinds de laatste update. Deze datum wordt in het config.ini bestand weggeschreven
opgezocht en elke geupdate indien er een succesvolle aanvraag is geweest.
* Late namiddag Node.js conferentie gevolgt bij Digipolis (Technolgie beurs/meeting Professionalisering)

### Vrijdag
* Vrijaf genomen

## **Paasvakantie (28/03/16 - 10/04/16)**

## Week 7 (11/04/16 - 17/04/16)
### Maandag
* Verder gewerkt een het updatescript en hiervoor een API ontworpen. De Raspberry Pi doet een POST request naar de server met de volgende informatie, het installatie nummer en/of id en
de datum waarop de lokale database laatste een update heeft ontvangen. Hierna zullen alle nieuwe nationalenummers sinds die datum worden verstuurd naar de Raspberry Pi, die deze dan aan
de lokale database toevoegd. 
* [U4VL](http://www.linux-projects.org/modules/news/) oftewel User space Video4Linux. Dit is een set tools met ondersteuning voor Raspberry Pi & WebRTC dit ik wil gaan
gebruiken voor de video/audi chat functionaliteit. Ik heb hierover onderzoek gedaan en deze al op de Raspberry Pi geïnstalleerd. Ik heb hiermee ook al proberen te werken, maar
dit heeft nog geen vruchtbaar resultaat geleverd.
* Voor de webcam is definitief besloten om de Sony (PS3) eye camera te gebruiken, dit om enkele reden. Het kan aangesloten worden via een USB verbinding, wordt ondersteunt door
de Raspberry Pi, heeft een ingebouwde microfoon en tenslotte beschik ik al over de hardware.

### Dinsdag
* Tussentijdse presentatie bachelorproef

### Woensdag
* Verder gewerkt aan de PS3 camera te kunnen laten werken op de Raspberry Pi. Dit is me momenteel niet gelukt, hiervoor ga ik nogmaals de tutorials die de stagebegeleider heeft
doorgestuurd bekijken.
* Ik heb nader besloten eerst verder te werken aan de overige functionaliteit en hierna terug tijd te besteden aan de video/audio chat funcitonaliteit. Ik blijf wel zeker
of het feit dat de Raspberry Pi B+ model niet krachtig genoeg is om dit met vrucht te kunnen realiseren. 

### Donderdag
* Verder de bootcyclus gewerkt, volgende week zal ik bespreken wat er nog van bijkomende informatie moet worden meegegeven eventueel en de bootcyclus hiervoor verder aanpassen. Deze
aanpassingen zullen afhangen van wat de stagementor nog graag aan extra functionaliteit wilt.
* HTTPS voor Node.js onderzocht. Uitgezocht hoe dit moet worden geïmplementeerd en dit dan ook geïmplementeerd. Ik maak momenteel gebruik van een Self Signed Certificate. Dit zelfde
principe zal ik terug opnieuw moeten uitvoeren om het MQTT verkeer ook te encrypteren. Ik had hier wel een probleem met het foutief genereren van de certificaten waardoor er geen
https verbinding kan aangemaakt worden. Ook heb ik onvervonden doordat ik momenteel geen standaard poort gebruik voor http(s) verkeer, ik voor de URL altijd naar het juiste protocol moet
verwijzen indien ik HTTPS verbinding wil maken (= "https://" gebruiken). 

### Vrijdag
* Vrijaf genomen

## Week 8 (18/04/16 - 24/04/16)
### Maandag
* Besproken met stagementor wat er precies nog van informatie in de database moet komen en wat er nog aan functionaliteit zou moeten worden toegevoegd.
* Bootcyclus aangepast, het systeem dat ik nu gebruik waarbij elke Raspberry Pi standaard hetzelfde paswoord krijgt om als validatie te gebruiken voor het 
consumeren van bepaalde services is onveilig. Hier moet ik dus een oplossing worden gevonden. Hiervoor denk ik het volgende systeem te implementeren, alle nieuwe aangemelde installaties
krijgen een boolean waarde dat weergeeft dat ze nieuw zijn en hierdoor limieten hebben in verband met privileges. In de webapplicatie moet de administrator eerst valideren of de installatie
geldig is. 

### Dinsdag
* Feedback gekregen van de stagementor over de bespreking van gisteren. Hij heeft een document opgesteld met de extra verwachte functionaliteit en wat hij verwacht van
data in de master database.
* Bekeken of we niet [MOSCA](https://github.com/mcollina/mosca) kunnen gebruiken i.p.v. Mosquitto als MQTT broker. Dit is een MQTT broker voor Node.js en zou het probleem elimineren
 van een aparte service/server voor de MQTT.
* Om de extra functionaliteit te implementeren en het overzichtelijk te houden ben ik begonnen met het tekenen van flowcharts van de software. Momenteel zijn deze met de hand getekend, maar
deze zullen later gedigitaliseerd worden en toegevoegd worden aan de scriptie.

### Woensdag
* Master database aangepast:
    * Installaties db toegevoegd met de volgende tabellen: Installaties, InstallatieTypes
    * Users db aangepast met bijkomende informatie die de stagementor wou over de gebruikers zoals woonplaats, telefoon zowel landlijn als mobiel nummer. Ook is er een
     systeem gewenst van verschillende security levels voor de gebruikers, met elk een eigen aantal privileges.
     * Data db toegevoegd deze database bevat tabellen voor de data die door de sensoren verzameld wordt
* Nagedacht en onderzoek gedaan naar hoe ik best de data van de sensoren verwerk. De berichten rechtstreeks opslaan in de database en later verwerken naar de juiste tabellen of deze
rechtstreeks verwerken. Hierbij blijft de vraag hoe groot de delay wordt tussen het verwerken van de berichten, wanneer we scalen naar meer dan één Raspberry Pi.

### Donderdag
* Aanpassing gedaan omtrent het updaten van de lokale database met nationale nummers. Hiervoor liet ik de Raspberry Pi bijhouden wanneer de database laatst was geupdate, dit heb ik
verandert naar dat de masterdatabase dit doet en de Raspberry Pi zich moet inloggen.
* De Raspberry Pi krijgt nu tijdens de random bootcyclus een random paswoord toegewezen, deze wordt in combinatie met de installatienummer (deze is uniek) gebruikt om in te loggen en
bepaalde services te kunnen consumeren (zoals updaten van de lokale database met nieuwe nationale nummers).
* Nog altijd geen oplossing bedacht voor het volgende probleem. Wanneer er meerdere Raspberry Pi's in één installatie worden gebruikt hoe ik alleen voor de eerste Raspberry Pi hardcoded
poorten voorzie voor het sturen van het deurslot en voor nazicht of de deur open of toe is. De overige Raspberry's zouden de dan toch niet gebruikte poorten moeten kunnen gebruiken.

### Vrijdag
* Kickstarterdag Ordina (jobbeurs Professionalisering)

## Week 9 (25/04/16 - 01/05/16)
### Maandag
* Verder gewerkt aan bootcyclus, ik had hier problemen met requests module. Deze was al geïnstalleerd omdat ik de python package manager had geïnstalleerd. Door dit handmatig opnieuw te installeren met sudo
command, had ik een ImportError als ik de python package manager wouw gebruiken. Ik heb dit na wat onderzoek met het 
volgende [stackoverflow artikel](http://stackoverflow.com/questions/27341064/how-do-i-fix-importerror-cannot-import-name-incompleteread) kunnen oplossen. Ik wou de nieuwste versie van pyscard downloaden
de ontwikkelaar had namelijk een bug opgelost die ervoor zorgde dat pyscard niet via de package manager geïnstalleerd kon worden. Dit zou handig zijn om eventueel een bash script te ontwikkelen die automatisch 
alles installeerd van dependencies op de Raspberry Pi.
* Probleem met de UV4L deamon, deze crashed om de zoveel tijd. Het is nog ook altijd niet mogelijk om de videofeed van de PS3 eye weer te geven in de browser.
* Na wat onderzoek heb ik door de extra's van UV4L te downloaden het probleem met de crashende deamon voorlopig kunnen oplossen.

### Dinsdag
* Nog altijd niet in staat beeld te krijgen van de PS3 eye. Ik heb hierna besloten om te kunnen testen of ik in staat ben video beeld te verkrijgen motion te installeren. Motion is de library die Artur vorig 
academie jaar heeft gebruikt om videobeelden te kunnen streamen. Deze driver heeft wel het nadeel niet echt in staat te zijn audio live te streamen en geeft geen mogelijkheden voor wederzijdse
communicatie.
* Ik ben ook niet in staat via motion video beelden te streamen naar de browser, ook al gebruik ik de instellingen van Artur aan de hand van hoe hij deze heeft beschreven in zijn scriptie. Ik heb hierna tevergeefs
enkele online tutorials gevolgd met geen resultaat.

### Woensdag
* Wegens weinig resultaat te boeken met de video/audiochat heb ik besloten met te focussen op de webapplicatie. Ik heb besloten een bootstrap template te gebruiken voor de applicatie zelf.
Ik maak hier gebruik van een vrij te gebruiken template die [hier](http://startbootstrap.com/template-overviews/sb-admin/) terug te vinden is. Ik had hiervoor al een eigen template ontworpen, maar deze zoveel
teveel tijd kosten om verder te ontwikkelen.
* Deze heb ik verder liggen aanpassen voor eigen gebruik. Ik heb onder andere de chat/notificatie elementen verwijderd, de overige pagina's van het menu verwijderd. Deze zijn toch niet nodig
mits ik angular-ui-route ga gebruiken. Deze library laat toe dynamisch html content in een container te laden.

### Donderdag
* Nogmaals een poging gevolgd om de webRTC tutorial van UV4L te volgen, ik heb hier ontdekt dat enkel de Raspberry Pi 2 ondersteuning heeft van UV4L voor webRTC. Mits ik momenteel enkel beschik Raspberry Pi
B+. Ik heb verder nog enkele tutorials gevolgd om met motion te werken, maar dit had ook geen resultaat.

### Vrijdag
* Vrijaf genomen

## Week 10 (02/05/16 - 08/05/16)
### Maandag
* Begonnen met het ontwerpen van de volgende formulieren: login formulier, paswoord herstel formulier en het formulier waar men het nieuwe paswoord kan invullen.
* Voor de aanvragen aan de server ga ik momenteel enkel ajax gebruiken, mits ik toch al jQuery ga gebruiken om DOM-elementen van de formulieren/HTML pagina's te manipuleren. Ik hiervoor geprobeerd
DOM-elementen te verbergen met Angular.js en dit was minder simplistisch dan gewoonweg jQuery te gebruiken.

### Dinsdag
* Verder gewerkt aan het ontwerpen van de html pagina's/formulieren, hiervoor gebruik ik ook bootstrap en zorg er zeker voor dat deze even flexibel is als de admin template om gebruikt te worden
op tablets, smartphones, etc.
* Verder heb ik ook express-sessions met een mySQL session store driver aan het werk gekregen op de Node.js backend. Ik heb hier enkele problemen gehad omtrent dat de mySQL session store niet in staat was
de database te manipuleren, dit kwam omdat het account voor de database server, dat door de Node server wordt gebruikt te gelimiteerd was.

### Woensdag
* API ontwikkelt om gebruikers te kunnen laten inloggen, om de paswoorden te encrypteren/vergelijken gebruik ik bcrypt. Dit is een npm package/library die hiervoor speciaal ontwikkelt is. De genereert
automatisch de salts en hashen en slaagt deze in één string op. Hiervoor heb ik de database ook moeten aanpassen. Mijn origineel plan was om zelf code te schrijven die een salt zou genereren en het paswoord 
zou hashen. Bcrypt heeft een voordeel dat men saltrounds kan instellen, dit laat toe dat het vergelijken van paswoorden en het hashen ervoor vertraagd verloopt. Dit helpt bij het verdedigen tegen
brute force attacks, door het drastisch omlaag brengen van het aantal aanvragen dat de hacker kan doen om in te loggen.
* API ontwikkelt dat een e-mail naar de gebruikers stuurt met hierin een link om hun paswoord opnieuw in te stellen. Ik gebruik hiervoor de nodemailer package en een gmail account, maar dit gaat ook
via elke mailserver met de juiste instellingen. 

### Donderdag
Vrijaf: O.H. Hemelvaart

### Vrijdag
* Verder gewerkt aan de API dat de gebruiker in staat stelt zijn paswoord opnieuw in te stellen. Ook heb ik de manier waarop de hash die in de recovery link wordt gebruikt nog wat aangepast. Ik heb hierbij wel het
probleem dat als de gebruiker het formulier opent om zijn paswoord aan te passen bepaalde resources van de webpagina niet toegankelijk zijn. Dit is onder andere de jQuery file en het eigen javascript file.
Ik heb hiervoor nog geen oplossing gevonden.
* Overigens heb ik de layout van de formulieren nog wat aangepast.

## Week 11 (09/05/16 - 15/05/16)
### Maandag
* Heartbeat geïmplementeerd dat toelaat na te kijken of de sessie nog geldig is (elke 60 seconden), hierdoor zal de pagina vernieuwd worden indien de sessie vervalt en komt men terug bij de inlog pagina terecht.
* Sessie cookie levensduur aangepast hier was een probleem dat ik deze niet lang genoeg had ingesteld, waardoor de cookie vervalt voor de sessie. De levensduur van een cookie en dus ook
van een sessie indien men de API's binnen de 30min aanspreekt is nu 4u.
* Gebruik beginnen maken van .env file (enviroment file) om enviroment variabelen te kunnen gebruiken. Dit laat toe dat de server bepaalde data zoals gebruikersnaam/paswoord voor de database in de file
te definiëren in plaats van deze te hardcoded in de server files zelf. Het laat ook toe deze variabelen meerdere malen te gebruiken en ze maar in één plaats te moeten aanpassen indien mogelijk.
* Probleem opgelost dat ervoor zorgde dat de gebruiker bepaalde resources niet van de server kreeg. Dit kwam omdat de functie om de file te verzenden, te diep genest was in het programma. Als oplossing
krijgt de gebruiker een mini sessie aan waar de recover hash in geplaatst wordt, hierna wordt de gebruiker verwezen naar de reset pagina. Hier kan de gebruiker dan zijn paswoord aanpassen. Het valideren met de
hash wordt dan server side gedaan.

### Dinsdag
* Volgende functionaliteit toegevoegd aan de webapp:
    * De gebruiker kan uitloggen vanuit de webapp
    * De gebruiker kan zijn paswoord wijzingen vanuit de webapp
    * De gebruiker kan zijn gegevens bijwerken vanuit de webapp
    * De gebruiker krijgt zijn naam te zien in de linkerbovenhoek, door op de naam te klikken krijgt de gebruiker de verschillende opties voorgeschoteld die hierboven zijn genoemd. 
### Woensdag
* Volgende functionaliteit toegevoegd aan de webapp:
    * Smart-table implementatie om alle gebruikers en gevalideerde installaties weer te geven in tabellen, hier is ook de optie om installaties of gebruikers te verwijderen en/of verder te inspecteren.

### Donderdag
* Volgende functionaliteit toegevoegd aan de webapp:
    * De gebruiker, als deze hiervoor de rechten heeft kan nieuwe gebruikers toevoegen.
    * Als de gebruiker op info drukt bij een gebruiker in de tabel, opent zich een nieuwe pagina. De pagina geeft meer informatie weer over de gebruiker en indien men genoeg rechten heeft kan men de gekozen
        gebruiker manipuleren (informatie en paswoord wijzigen).
    * De gebruiker krijgt door op info te klikken in de installatie tabel een overzicht van de gekozen installatie. Men heeft hier 3 tabs namelijk overzicht installatie, videochat en gegevens installatie.
        De gebruiker heeft aan de hand van zijn privileges de mogelijk deze te manipuleren.

### Vrijdag
* Er deed zich een bug voor bij de paswoord recuperatie via email, dit kwam omdat de tijdsinstellingen van de MySQL server niet meer correct waren. Dit kwam hoogstwaarschijnlijk door het gebruik van 
een virtuele machine, doordat ik deze elke keer suspende. Ik heb dit opgelost door de MySQL service te herstarten.
* Functionaliteit webapp: De gebruiker krijgt door op info te klikken in de installatie tabel een overzicht van de gekozen installatie. Men heeft hier 3 tabs namelijk overzicht installatie, videochat en gegevens installatie.
De gebruiker heeft aan de hand van zijn privileges de mogelijk deze te manipuleren. 

## Week 12 (16/05/16 - 22/05/16)
### Maandag
* Vrijaf feestdag pinkstermaandag

### Dinsdag
* Sollicitatiegesprek bij Ordina in de voormiddag.
* Database aangepast, er waren problemen met de boolean die gebruikt wordt om na te kijken of een installatie als door de juiste gebruiker is nagekeken of niet.
* Dashboard messages geïmplementeerd, gebruikers kunnen bericht achterlaten op het dashboard zodat andere deze kunnen bekijken. 

### Woensdag
* Layout aangepast zodat elementen verborgen worden indien de gebruiker niet over de juiste permissies beschikt.
* Gebruikers met de privileges om gebruikers aan te maken/aan te passen kunnen nu automatisch een paswoord laten genereren van 10 tekens.
* Voor het laden van de gebruikers, installatie, etc. tabel heb ik een spinner geïmplementeerd. Deze wordt weergegeven terwijl de tabel laadt.

### Donderdag
* Webapplicatie functionaliteit omtrent het toevoegen, aanpassen en weergeven van gebruikers volledig afgewerkt.
* Nog altijd wel een bug dat bij een select de ingestelde value van ng-model niet als gekozen value wordt weergegeven in de select.
* Als men niet de rechten heeft om gebruikers aan te passen zal de delete knop in de gebruikers table worden weergegeven. De paswoord tab en de edit/opslaan veranderingen knop worden niet weergegeven
bij het gedetailleerd overzicht.

### Vrijdag
* Bij het proberen toe te voegen van angular-charts, dat ik ga gebruiken om diagrammen te genereren doet er zich een error voor. Deze error komt doordat ik de javascript files rechstreeks van GitHub
download, dit geeft een error doordat Github een verkeerde doctype meegeeft aan de minified versies van de libraries. Ik heb dan geopteerd om over te schakelen naar bower, zodat het ook makkelijker is
de verschillende libraries te managen.
* TLS geïmplementeerd voor de Mosquitto server.

## Week 13 (23/05/16 - 29/05/16)
### Maandag
* Bug gevonden dat ervoor zorgde dat het paswoord field van een gebruiker leeg kwam te staan. Hierdoor had de gebruiker geen paswoord meer en kon dus niet meer inloggen. Dit gebeurd bij mij tijdens het testen 
van de webapplicatie.
* De node.js server files modulair gemaakt. Momenteel waren alle webapp services in één gigantische file, deze was zeer groot en onoverzichtelijk geworden. Ik heb hiervoor gekozen om alle API's onder te verdelen
a.d.h.v. welke functionaliteit dat ze voorzien voor de webapplicatie. Dit maakt het makkelijker en overzichtelijker om met de server files te werken.

### Dinsdag
* Raspberry Pi 2 beginnen gebruiken om de webRTC implementatie van UV4L, mits er ook een nieuwere versie was van Raspbian heb ik geopteerd met een nieuwe image te beginnen.
* Ik heb hiervoor wel alle files van de Raspberry Pi image geback-upt en ook nog is een back-up gemaakt van de volledige image. Hierna heb ik de nieuwe image geïnstalleerd en alle resources gedownload, files
overgezet, etc.

### Woensdag
* Shell script beginnen ontwikkelen dat alle benodigde resources voor de python scripts automatisch download, dit geldt ook voor alle python packages.
* WebRTC ondersteuning van UV4L proberen te implementeren met behulp van de volgende tutorials/forum posts:
    * [Stackoverflow post](http://raspberrypi.stackexchange.com/questions/39690/configuring-uv4l-for-webrtc-using-usb-camera-on-rpi2-raspbian)
    * [Thread op Raspberry Pi forum](https://www.raspberrypi.org/forums/viewtopic.php?f=43&t=105019&hilit=native+webrtc)
    * [Officiële tutorial van UV4L](http://www.linux-projects.org/modules/sections/index.php?op=viewarticle&artid=14)
* Het was eerst niet mogelijk om de PS3 eye toe te voegen ook als was deze UVC-compliant. Met de webcam die origineel hiervoor was aangekocht was dit wel mogelijk.

### Donderdag
* Script verder aangepast zodat deze UV4L aan sources toegevoegd, hierdoor kunnen alle UV4L libraries gedownload worden.
* WebRTC nog altijd niet kunnen laten functioneren. Ik ga in dit log niet tever hierop ingaan, maar zal deze indien ik het niet werkent krijgen zogoed mogelijk documenteren in de bachelorproef zelf.

### Vrijdag
* Vrijaf genomen

## Week 14 (30/05/16 - 05/06/16)
### Maandag
* Volgende functionaliteit (afgewerkt) aan de webapplicatie
    * Installatie page, voor specifieke installatie afgewerkt.
    * Deur log wordt weergegeven alle personen die de deur hebben geopend via de webapp of via de eID lezer worden weergegeven.
    * Men kan nu de poorten aansturen en de deur openen via de Webapplicatie.

### Dinsdag
* Weergeven van sensor data in de vorm van een grafiek geeft enkele problemen met zich weer. Angular is niet in staat met zulke hoeveelheden data om te gaan (1 uur = 3600 samples). Het instellen van de assen
van de grafiek is ook een probleem met het weergeven van de datum van de sample, deze zou pas om de minuut of meer mogen zijn!
* De webapplicatie geeft nu de ADC waar weer aan de hand van de waardes die meegeven zijn aan het installatietype object (min/max waarde en eenheid).

### Woensdag
* Functionaliteit toegevoegd die toelaat de installatietypes weer te geven in een tabel en de eigenschappen hiervan te wijzigingen.
* Het python script houdt nu bij welke status de uitgaande poorten hadden en bij een reboot worden deze terug opgehaald en naar de Arduino geschreven.
* Gezocht naar het systemd probleem, deze blijft niet in staat het script automatisch te doen opstarten.

### Donderdag
* Problemen in vorm met self-signed certificates, deze werken voor MQTT.fx en voor de Paho libraries maar niet voor de Node MQTT library. Ik heb dit probleem proberen op te lossen
door gebruik te maken van let's encrypt.
* Problemen omtrent Mqtt aan te spreken rechtstreeks via de browser, dit werkt niet dankzij mixed content type error. Dit komt omdat de webapplicatie gebruik maakt van SSL/TLS en de websockets
verbinding niet. Ik heb hier dan geopteerd om geen encryptie toe te passen
* Nog onderzoek gedaan naar mogelijk een andere MQTT broker te gebruiken. Ik ben hierdoor wel te weten gekomen dat in een productie omgeving men de Mosquitto broker beter niet kan gebruiken.
Ik dit bespreken in de scriptie.

### Vrijdag
* Node MQTT services ontwikkelt, deze services ontvangen de sensor samples en plaatsen deze in de databank
* Bug opgelost in Arduino code, waardoor de laatste ADC poort niet correct werd uitgelezen.
* Nogmaals poging gedaan om de WebRTC via de U4VL libraries te doen werken, met weer geen resultaten.

<!--The End-->