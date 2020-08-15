---
title: Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Meer informatie over hoe u de geschiedenis van de clientcomputer verbindingen controleert, zodat u de nieuwste problemen in de loop van de client snel kunt ontdekken.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689214"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Prestaties afstemmen van Office 365 met basislijnen en prestatie geschiedenis

Er zijn enkele eenvoudige manieren om de prestaties van de verbinding tussen Office 365 en uw bedrijf te controleren, zodat u een grove basislijn van uw verbinding kunt maken. Door de prestatie geschiedenis van de clientcomputer verbindingen op te lossen, kunt u de meest opkomende problemen vroegtijdig detecteren, identificeren en voorspellen.
  
Dit artikel is bedoeld om u te helpen bij het maken van een aantal veelgestelde vragen, zoals hoe u weet dat het probleem niet is opgelost en geen Office 365-service-incident is. Hoe kunt u de prestaties van een goede periode plannen? Hoe zorgt u ervoor dat u de prestaties kunt verbeteren? Als uw team of clients trage prestaties zien wanneer u Office 365 gebruikt en u zich afvraagt over een van deze vragen, lees dan verder.
  
> [!IMPORTANT]
> **Hebt u nu een prestatieprobleem tussen de client en Office 365?** Voer de stappen uit die worden beschreven in het [prestatieprobleem oplossen van Office 365](performance-troubleshooting-plan.md). 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Wat u moet weten over de prestaties van Office 365

Office 365 valt binnen een gespecialiseerde, gespecialiseerde, gespecialiseerde Microsoft-netwerken die niet alleen op basis van automatisering worden gecontroleerd, maar ook door echte personen. Deel van de rol van het behoud van de Office 365-wolk maakt het optimaliseren van de prestaties en het stroomlijnen. Aangezien clients van de cloud van Office 365 verbinding willen hebben via internet, is er een voortdurende inspanningen om de prestaties van Office 365-services te verfijnen. Prestatieverbeteringen worden nooit langer in de Cloud beëindigd en er is een heleboel geaccumuleerde ervaring met het behoud van de cloud in orde en snel. Als u problemen ondervindt bij het maken van de verbinding vanaf uw locatie met Office 365, kunt u het beste beginnen met een ondersteuningsaanvraag. In plaats daarvan dient u eerst te beginnen met het onderzoek van het probleem. U kunt dus in uw netwerk beginnen en verder werken naar Office 365. Voordat u een zaak opent met ondersteuning voor Office 365, kunt u gegevens verzamelen en acties ondernemen waarmee u het probleem kunt verhelpen.
  
> [!IMPORTANT]
> Let op de capaciteitsplanning en limieten in Office 365. Deze informatie zet u vóór de bocht wanneer u probeert een prestatieprobleem op te lossen. Hier ziet u een koppeling naar de beschrijvingen van de [Services van Microsoft 365 en Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Dit is een spil hub en alle services die worden aangeboden door Office 365 hebben een koppeling die van hieruit overgaat op hun eigen service beschrijvingen. Dat betekent dat u de standaardlimieten voor SharePoint Online moet zien, bijvoorbeeld door te klikken op [Beschrijving van SharePoint Online service](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) en de [sectie limieten voor SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=856113)te zoeken. 
  
Zorg ervoor dat u de problemen oplost met de werking van de schuif schaal, het maakt niet uit een ideaal bedrag te bezorgen en de handmatig te onderhouden (als u van mening bent dat dit geen gevolgen heeft voor een groot aantal gebruikers of als grote gegevens migraties zeer lang zijn), dan moet u ervoor zorgen dat u de prestatie beïnvloedt. En wel, en wel, een goede indruk te hebben van de prestatiedoelstellingen, maar een groot aantal variabelen voor de prestaties is dus verschillend. Dat is de aard van de prestaties. 
  
Problemen bij het oplossen van problemen is niet te weten over het bereiken van specifieke doelstellingen en het bijhouden van deze nummers, het verbeteren van bestaande activiteiten, gegeven aan alle variabelen. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Hoe ziet een prestatieprobleem eruit?

U dient eerst te controleren of het probleem een prestatieprobleem is en niet een service-incident. Een prestatieprobleem is niet hetzelfde als een service-incident in Office 365. U kunt deze als volgt opzeggen.
  
Als de Office 365-serviceproblemen ondervindt, is dit een service-incident. U ziet de rode of gele pictogrammen onder **huidige status** in het microsoft 365-Beheercentrum, maar u kunt ook vertragingen in de prestaties van clientcomputers die verbinding maken met Office 365. Als u bijvoorbeeld de statusrapporten van de huidige status meldt en u **onderzoek** uitziet naast Exchange, kunt u vervolgens ook een aantal oproepen ontvangen van personen in uw organisatie die voorkomen dat Exchange Online met Exchange Online werken. In dat geval is het redelijk om te voorkomen dat de prestaties van Exchange Online het slachtoffer van problemen binnen de service werden. 
  
![Het Office 365-status dashboard met alle werkbelasting in het groen, met uitzondering van Exchange, waarin service hersteld wordt weergegeven.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
Op dit moment moet u, de Office 365-beheerder, de **huidige status** controleren en vervolgens **Details en geschiedenis**, vaak raadplegen om het onderhoud van de werkstroom te behouden. De **huidige status** dashboard werd gemaakt voor het bijwerken van de wijzigingen in en problemen in de service. De opmerkingen en uitleg die zijn geschreven naar de status geschiedenis, beheerder aan beheerder, zijn er om u te helpen uw gevolgen te meten en te zorgen dat u over lopend werk blijft. 
  
![Een afbeelding van het Office 365-status dashboard waarin wordt uitgelegd dat de Exchange Online-service is hersteld en waarom.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Een prestatieprobleem is geen service-incident, zelfs niet als incidenten de prestaties kunnen veroorzaken. Een prestatieprobleem ziet er als volgt uit:
  
- Een prestatieprobleem treedt op, ongeacht wat de **huidige status** van het Beheercentrum voor de service is. 
    
-  Functies die eerder relatief naadloos werden gebruikt, duren nu erg lang en worden niet uitgevoerd. 
    
- Als u de juiste reeks stappen uitvoert, kunt u het probleem ook repliceren of, ten minste.
    
-  Als het probleem zich blijft voordoen, wordt er nog steeds een patroon weergegeven, bijvoorbeeld: u weet dat er in 10:00 is dat u gesprekken voert van gebruikers die geen betrouwbare toegang hebben tot Office 365 en dat de oproepen niet langer dan 12:00 worden. 
    
Dit klinkt waarschijnlijk bekend; misschien bekend. Wanneer u weet dat het een prestatieprobleem is, wordt de vraag ' wat doet u verder? ' weergegeven? De rest van dit artikel helpt u exact te bepalen.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Hoe definieert en test u een prestatieprobleem?

De prestaties zijn vaak te vaak achter de tijd, zodat u het feitelijke probleem moeilijk kunt definiëren. U moet een goed overzicht van de problemen en een goed idee van de probleem context maken en dan moet u de stappen voor het uitvoeren van tests herhalen om de dag te winnen. Anders, vanwege geen storing van uw eigen, gaat u mogelijk verloren. Waarom? Hier volgen enkele voorbeelden van probleem verklaringen die niet voldoende informatie leveren:
  
- Overstappen van mijn postvak in op mijn agenda werd gebruikt om iets te doen dat ik niet heb opgemerkt, en het is nu een koffie-einde. Kunt u ervoor zorgen dat de toepassing op de gebruikte manier functioneert?
    
- Het uploaden van mijn bestanden naar SharePoint Online duurt altijd. Waarom is de middag traag, maar nog steeds snel? Is het niet zo snel?
    
De hierboven genoemde probleem verklaringen vormen diverse grote uitdagingen. Met name is er een groot aantal ambiguïteiten waarop u kunt handelen. voorbeeld:
  
- Het is niet duidelijk hoe het schakelen tussen het postvak in en de agenda die wordt gebruikt om op de laptop te reageren.
    
- Als de gebruiker zegt: "kan het niet snel snel zijn", wat is dan "snel"?
    
- Hoe lang is ' permanent '? Is er enkele seconden of minuten, of kan de gebruiker tien minuten nadat de gebruiker weer is geworden, voltooien.
    
Dit houdt in dat de beheerder en de probleemoplosser niet op de hoogte zijn van een groot aantal informatie van probleem overzichten zoals deze. Als het probleem zich bijvoorbeeld voordoet, Of de gebruiker werkt vanaf thuis en ziet maar ooit overstappen op een thuisnetwerk. De gebruiker moet meerdere andere geheugenintensieve toepassingen op de lokale client uitvoeren, of de gebruiker voert een ouder besturingssysteem uit of geen recente updates uit.
  
Wanneer gebruikers een prestatieprobleem rapporteren, zijn er veel gegevens om te verzamelen. Het verzamelen van deze gegevens maakt deel uit van het proces dat de naam van het probleem aanroept of het onderzoek doet. Hieronder ziet u een eenvoudige lijst met scopes die u kunt gebruiken om informatie te verzamelen over uw prestatieprobleem. Deze lijst is niet volledig, maar het is een plek waar u een van uw eigen kunt beginnen: 
  
- Op welke datum is het probleem opgetreden en op welk tijdstip van de dag of 's nachts?
    
- Welk type clientcomputer gebruikt u en hoe maakt u verbinding met het bedrijfsnetwerk (VPN, bedraad, draadloos)?
    
- Werkte u op afstand of was u op kantoor?
    
- Hebt u dezelfde acties op een andere computer uitgevoerd en hetzelfde gedrag weergegeven?
    
- Doorloop de stappen die de problemen veroorzaken, zodat u de ingevoerde acties kunt schrijven.
    
- Hoe lang duurt de vertraging (in seconden of minuten)?
    
- Waar ter wereld bevindt u zich?
    
Sommige vragen zijn duidelijker dan andere vragen. De meeste iedereen begrijpt inzicht in de juiste stappen om het probleem te reproduceren. Vervolgens kunt u nog meer op de gewenste manier vastleggen wat er mis is en hoe u nog meer kunt testen of het probleem is opgelost? Minder duidelijk: wat voor datum en tijd hebt u het probleem zien? "en" waar ter wereld u zich bevindt? ", informatie die u overal kunt gebruiken. Afhankelijk van het moment dat de gebruiker werkte, kan het onderhoud een paar uur lang duren voordelen van het netwerk van uw bedrijf. Als uw bedrijf bijvoorbeeld een hybride implementatie heeft, zoals een hybride SharePoint-zoektoepassing waarmee zoekindexen kunnen worden gezocht in zowel SharePoint Online als een on-premises SharePoint Server-exemplaar van 2013, zijn er mogelijk updates beschikbaar in de on-premises farm. Als uw bedrijf in de Cloud staat, kan systeemonderhoud gebruikmaken van netwerkhardware, het implementeren van updates die in het hele bedrijf zijn, of het aanbrengen van wijzigingen in DNS of andere basisinfrastructuur.
  
Als u problemen ondervindt bij het oplossen van problemen, moet u een goede en observant om de conclusies van het bewijs te tekenen. U kunt dit alleen doen als u een goed overzicht van de problemen met het verzamelen van bewijsmateriaal ontvangt. De computer context moet de context van de computer bevatten, de context van de gebruiker, wanneer het probleem is begonnen, en de exacte stappen die het prestatieprobleem hebben veroorzaakt. Dit probleem kan worden opgelost en de bovenste pagina in uw notities bewaard blijft. Door de foutmelding weer te geven nadat u aan de oplossing hebt gewerkt, voert u de stappen uit die u moet uitvoeren om te controleren of de acties die u uitvoert het probleem hebben opgelost. Dit is belangrijk om te weten wanneer uw werk, daar, klaar is.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Weet u wat de prestaties waren wanneer een goede werking werd gekeken?

Als u unlucky hebt, weet niemand. Niemand heeft getallen. Dat betekent dat niemand de eenvoudige vraag kan beantwoorden, wat het kost om een postvak in Office 365 in Office? ' of ' hoe lang het duurt voordat de leidinggevenden een Lync online-vergadering hadden? ', wat een veelvoorkomend scenario is voor veel bedrijven.
  
Wat hier ontbreekt is een basislijn voor prestaties.
  
Met basislijnen beschikt u over een context voor uw prestaties. Afhankelijk van de behoeften van uw bedrijf moet u de basislijn regelmatig instellen. Als u een groter bedrijf bent, kunnen uw activiteiten team al basislijnen maken voor uw on-premises omgeving. Als u bijvoorbeeld alle Exchange-servers op de eerste maandag van de maand, en al uw SharePoint-servers op de derde maandag bijwerkt, bevat uw activiteiten team waarschijnlijk een lijst met taken en scenario's waarin de post-patch wordt uitgevoerd om te bewijzen dat de kritieke functies operationeel zijn. U kunt bijvoorbeeld het postvak in openen, op verzenden/ontvangen klikken en ervoor zorgen dat de mappen worden bijgewerkt, of, in SharePoint, doorbladeren op de hoofdpagina van de site, naar de pagina Enterprise Search gaan en een zoekopdracht uitvoeren om resultaten te retourneren.
  
Als uw toepassingen deel uitmaken van Office 365, kunt u een aantal van de belangrijkste basislijnen voor het meten van de tijd (in milliseconden) van de clientcomputer in uw netwerk, een uitgangspunt of het punt waar u het netwerk verlaten en naar Office 365 gaan. Hier volgen een aantal handige basislijnen die u kunt onderzoeken en opnemen:
  
- Identificeer de apparaten tussen de clientcomputer en het uitgangspunt, bijvoorbeeld uw proxyserver.
    
  - U moet uw apparaten kennen, zodat u een context hebt (IP-adressen, type apparaat, et enzovoort tot) voor de prestatieproblemen die zich voordoen.
    
  - Proxy servers zijn algemene uitgangspunten, dus kijk in uw browser welke proxyserver er is ingesteld om te worden gebruikt, indien van toepassing.
    
  - Er bestaan hulpprogramma's van derden waarmee u uw netwerk kunt vaststellen en in kaart brengen, maar u kunt het beste vragen aan een lid van uw netwerkteam.
    
- Neem contact op met uw internetprovider (ISP), noteer de contactgegevens en vraag hoeveel circuits hoeveel bandbreedte u hebt.
    
- Identificeer binnen uw bedrijf de resources tussen de client en het uitgangspunt, of zoek een contactpersoon voor noodgevallen met wie u over netwerkproblemen kunt praten.
    
Hier volgen enkele basislijnen die eenvoudig testen met hulpprogramma's voor u kunnen worden berekend:
  
- Tijd van de clientcomputer naar uw uitgangspunt (in milliseconden)
    
- Tijd van uw uitgangspunt naar Office 365 in milliseconden
    
- Locatie in de wereld van de server die de URL'S voor Office 365 oplost wanneer u bladert
    
- De snelheid van de DNS-resolutie van uw INTERNETPROVIDER in milliseconden, inconsistentie van pakket ontvangst (netwerk-jitter), uploaden en downloaden van milliseconden
    
Als u niet weet hoe u deze stappen moet uitvoeren, gaat u naar meer informatie in dit artikel. 
  
## <a name="what-is-a-baseline"></a>Wat is een basislijn?

U weet wat de gevolgen zijn wanneer het slecht is, maar als u de historische prestatiegegevens niet weet, is het niet mogelijk om een context te hebben voor de manier waarop de fout is opgegroeid en wanneer. Dus als u geen basislijn hebt, mist u de belangrijkste aanwijzingen om de puzzel op te lossen: de afbeelding in het vak puzzel. Voor het oplossen van prestaties hebt u een  *vergelijkings*  punt nodig. Eenvoudige basislijnen voor de prestaties zijn niet moeilijk te ondernemen. U kunt een operationeel team met een planning maken. Stel dat uw verbinding er bijvoorbeeld zo uitziet: 
  
![Een afbeelding van een basisnetwerk met client, proxy en Office 365 Cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Dat betekent dat u bij uw netwerkteam hebt gekeken en dat u uw bedrijf voor het Internet verlaat via een proxyserver, en dat de proxy zorgt voor alle verzoeken waarop de clientcomputer naar de Cloud wordt verzonden. In dit geval moet u een vereenvoudigde versie van de verbinding tekenen met alle tussenliggende apparaten. Voeg nu hulpmiddelen voor invoegen die u kunt gebruiken om de prestaties van de client te testen, het uitgangspunt (waar u het netwerk voor Internet gebruikt) en de Office 365-wolk.
  
![Basisnetwerk met client, proxy en Cloud, suggesties voor PSPing, TraceTCP en netwerk traceringen.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
De opties zijn **eenvoudig** en **Geavanceerd** , vanwege de hoeveelheid expertise die u nodig hebt om de prestatiegegevens te vinden. Een netwerktracering kan veel tijd in beslag nemen, vergeleken met actieve opdrachtregelprogramma's, zoals PsPing en TraceTCP. Deze twee opdrachtregelprogramma's zijn gekozen omdat ze geen ICMP-pakketten gebruiken, die worden geblokkeerd door Office 365 en omdat ze de tijd in milliseconden aangeven dat het duurt voordat de clientcomputer of proxyserver overblijft (als u toegang hebt) en arriveert bij Office 365. Elke afzonderlijke hop van de ene computer naar een andere, eindigt met een tijdwaarde en dat is uitstekend voor basislijnen. Op deze manier kunt u op deze manier een poortnummer toevoegen aan de opdracht door in Office 365 via poort 443 door Office te communiceren, dat wil zeggen de gebruikte poort van Secure Sockets Layer en Transport Layer Security (SSL en TLS). Andere hulpprogramma's van derden kunnen echter betere oplossingen zijn voor uw situatie. Microsoft biedt geen ondersteuning voor al deze hulpmiddelen, dus als u om wat voor reden dan ook geen PsPing-en TraceTCP-werk kunt doen, gaat u naar een netwerktracering met een programma zoals Netmon. 
  
U kunt een basislijn vóór kantooruren, opnieuw tijdens een intensief gebruik, en daarna weer na uur weer doen. Dat betekent dat u mogelijk een mapstructuur ziet die er ongeveer zo uitziet als die in het einde:
  
![Afbeelding van een manier om prestatiegegevens in mappen te ordenen.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
U dient ook een naamconventie te kiezen voor uw bestanden. Dit zijn enkele voorbeelden:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
U kunt dit op tal van verschillende manieren doen, maar het gebruik van de notatie **\<dateTime\>\<what's happening in the test\>** is een goede plek om te beginnen. Dit helpt een heleboel wanneer u later problemen probeert op te lossen. Later kunt u zeggen dat ik twee sporen heb gemaakt op 8 februari, één vertoont een goede prestaties en een vertoonde fout, zodat we ze kunnen vergelijken. Dit is een zeer handige oplossing voor het oplossen van problemen. 
  
U moet een georganiseerde manier hebben om uw historische basislijnen te behouden. In dit voorbeeld zijn de eenvoudige methoden met drie opdrachtregels-uitvoer en de resultaten als schermafbeeldingen verzameld, maar mogelijk hebt u in plaats daarvan een netwerk opnamebestanden gemaakt. Gebruik de methode die het meest geschikt is voor u. Sla uw historische basislijnen op en vermeld ze op punten waar u de wijzigingen aanbrengt in de werking van Online Services. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Waarom zou u prestatiegegevens verzamelen tijdens een testfase?

U kunt geen basislijnen meer maken dan tijdens een pilot van de Office 365-service. Uw Office kan duizenden gebruikers, honderden duizenden gebruikers of vijf, maar zelfs met een klein aantal gebruikers, kunt u testen uitvoeren om fluctuaties in prestaties te meten. In het geval van een groot bedrijf kan een representatieve steekproef van verschillende honderd gebruikers die Office 365 testen, naar buiten geprojecteerd worden, zodat u weet waar de problemen zich voordoen.
  
In het geval van een klein bedrijf waarbij aan boord wordt aangegeven dat alle gebruikers tegelijk naar de service gaan en dat er geen pilot is, behoud de prestatie maatregelen zodat u de gegevens kunt weergeven aan iedereen die mogelijk problemen heeft met een verkeerd uitvoeren van de werkstroom. Als u bijvoorbeeld merkt dat u het gebouw in de loop van de tijd kunt omlopen wanneer het gaat om een middelgrote afbeelding te uploaden, zodat de afbeelding zeer snel verloopt.
  
## <a name="how-to-collect-baselines"></a>Basislijnen verzamelen

Voor alle plannen voor het oplossen van problemen moet u het volgende doen:
  
- De clientcomputer die u gebruikt (het type computer of apparaat, een IP-adres en de acties die het probleem hebben veroorzaakt)
    
- Waarbij de clientcomputer zich bevindt in de wereld (bijvoorbeeld of deze gebruiker met een VPN-verbinding op het netwerk, extern of via het bedrijfsintranet werkt)
    
- Het uitgangspunt dat door de clientcomputer wordt gebruikt vanuit uw netwerk (het punt waarop verkeer uw bedrijf verlaat voor een INTERNETPROVIDER of Internet)
    
 U kunt de indeling van uw netwerk achterhalen via de netwerkbeheerder. Als u een klein netwerk gebruikt, kijk dan eens naar de apparaten die u verbindt met internet en neem contact op met uw INTERNETPROVIDER als u vragen hebt over de lay-out. Maak een afbeelding van de uiteindelijke indeling voor uw verwijzing. 
  
Deze sectie is opgetreden in eenvoudige opdrachtregelprogramma's en-methoden, en meer geavanceerde extra opties. We bieden eerst eenvoudige methoden aan. Als u nu een prestatieprobleem hebt, moet u op geavanceerde methoden overstappen en de voorbeelden van het gebruik van de programmeer kwaliteit oplossen.
  
### <a name="simple-methods"></a>Eenvoudige methoden

Het doel van deze eenvoudige methoden is om te leren hoe u eenvoudige onderhoudskosten in de loop van de tijd maakt, begrijpt en juist opslaat, zodat u op de hoogte wordt gesteld van de prestaties van Office 365. Dit is een eenvoudig diagram voor eenvoudige functies, zoals u dit eerder hebt gezien:
  
![Basisnetwerk met client, proxy en Cloud, suggesties voor PSPing, TraceTCP en netwerk traceringen.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP is opgenomen in deze schermafbeelding omdat dit een handig hulpmiddel is voor het weergeven van de hoeveelheid tijd die nodig is voor het verwerken van een aanvraag en hoeveel netwerk hops of verbindingen van de ene computer naar de volgende gaan, dat de aanvraag een bestemming bereikt. Met TraceTCP kunt u ook de namen opgeven van servers die worden gebruikt tijdens de hops en die handig kunnen zijn voor een probleem met Microsoft Office 365 in de ondersteuning. > TraceTCP-opdrachten kunnen heel eenvoudig zijn, bijvoorbeeld: >  `tracetcp.exe outlook.office365.com:443`> vergeet het poortnummer in de opdracht op te nemen. > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) is gratis te downloaden, maar is afhankelijk van Wincap. Wincap is een tool dat ook wordt gebruikt en geïnstalleerd door Netmon. U kunt netmon ook gebruiken in de sectie Geavanceerde methoden. 
  
 Als u meerdere kantoren hebt, moet u ook op elk van deze locaties een set gegevens van een client bewaren. Met deze test wordt de latentie gemeten, wat in dit geval een waarde is die het aantal seconden aangeeft tussen een client die een aanvraag verzendt naar Office 365 en Office 365 op de aanvraag reageert. De test bevindt zich op een clientcomputer en ziet een afronding binnen uw netwerk, vanaf een uitgangspunt, via internet naar Office 365 en terug. 
  
U kunt op een aantal manieren omgaan met het uitgangspunt, in dit geval de proxyserver. U kunt een waarde opgeven van 1 naar 2 en vervolgens 2 tot 3, en de getallen in milliseconden optellen om het uiteindelijke totaal van de rand van het netwerk te bepalen. U kunt ook de verbinding configureren om de proxy voor Office 365-adressen over te slaan. In een groter netwerk met een firewall, omgekeerde proxy of een combinatie van beide, moet u mogelijk een uitzondering op de proxyserver maken waarmee verkeer wordt toegestaan voor veel Url's. Zie [url's en IP-](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)adresbereiken voor Office 365 voor de lijst met eindpunten die worden gebruikt door Office 365. Als u een verificatie proxy hebt, moet u eerst uitzonderingen testen voor de volgende bewerkingen:
  
- Poorten 80 en 443
    
- TCP en HTTPs
    
- Uitgaande verbindingen naar een van deze Url's:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*. sharepoint.com
    
- \*. outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
Alle gebruikers moeten gemachtigd zijn om toegang te krijgen tot deze adressen, zonder proxy storing of verificatie. In een kleiner netwerk moet u deze toevoegen aan de lijst met genegeerde proxy's in uw webbrowser. 
  
Als u deze wilt toevoegen aan de lijst met negeren van de proxy in Internet Explorer, gaat u naar **extra** \> **Internet opties** \> **verbindingen** \> **LAN-instellingen** \> **uitgebreid**. Op het tabblad Geavanceerd kunt u ook de poort van de proxyserver en de proxyserver vinden. Mogelijk moet u op het selectievakje klikken om **een proxyserver voor het LAN-netwerk te gebruiken voor**toegang tot de knop **Geavanceerd** . Zorg ervoor dat **proxyserver negeren voor lokale adressen** is ingeschakeld. Wanneer u op **Geavanceerd**klikt, ziet u een tekstvak waarin u uitzonderingen kunt invoeren. Scheid de Url's van de jokertekens met puntkomma's, bijvoorbeeld:
  
\*. microsoftonline.com; \*. SharePoint.com
  
Als u de proxy niet meer weet, moet u ping of PsPing rechtstreeks op een URL van Office 365. De volgende stap is het testen van de ping **Outlook.office365.com**. Als u gebruikmaakt van PsPing of een ander hulpmiddel waarmee u een poortnummer moet opgeven voor de opdracht, kunt PsPing tegen **Portal.microsoftonline.com:443** de gemiddelde retourtijd in milliseconden zien. 
  
De retourtijd, of de RTT, is een waarde die bepalen hoe lang het duurt om een HTTP-aanvraag naar een server te verzenden, zoals outlook.office365.com, en het vragen van de server erkent. U ziet soms dit afkort weergeven als RTT. Dit moet een relatief kort tijdsduur zijn.
  
U moet [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) of een ander hulpprogramma gebruiken die geen ICMP-pakketten gebruikt die worden geblokkeerd door Office 365, zodat u deze test kunt uitvoeren. 
  
 **Het gebruik van PsPing rechtstreeks vanuit een Office 365-URL voor een algemene retourtijd in milliseconden**
  
1. Voer een opdrachtprompt met verhoogde bevoegdheid uit door deze stappen uit te voeren:
    
1. Klik op **Start**.
    
2. Typ cmd in het vak **zoekopdracht starten** en druk op CTRL + SHIFT + ENTER.
    
3. Als het dialoogvenster **Gebruikersaccountbeheer** wordt weergegeven, bevestigt u of de actie die wordt weergegeven, is wat u wilt en klikt u vervolgens op **Doorgaan**.
    
2. Ga naar de map met het hulpprogramma (in dit geval PsPing) en test deze Office 365-Url's:
    
  - psping portal.office.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![Met de opdracht PSPing wordt de microsoft-my.sharepoint.com-poort 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Zorg ervoor dat u het poortnummer van 443 opneemt. Houd er rekening mee dat Office 365 werkt op een versleuteld kanaal. Als u PsPing zonder poortnummer, mislukt uw aanvraag. Als u de kortste lijst hebt gepingt, kijkt u naar de gemiddelde tijd in milliseconden (MS). Dat is wat u wilt opnemen.
  
![Afbeelding waarin een illustratie wordt weergegeven van client-naar-proxy PSPing met een retourtijd van 2,8 milliseconden.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Als u niet bekend bent met het negeren van de proxy en u wilt een stap voor stap volgen, moet u eerst de naam van uw proxyserver achterhalen. Ga in Internet Explorer naar **extra** \> **Internet Options** \> **Connections** \> **LAN-instellingen voor LAN** -verbindingen \> **Advanced**. Op het tabblad **Geavanceerd** kunt u de naam van uw proxyserver weergeven. Ping met behulp van de volgende taak met de opdrachtprompt: 
  
 **De proxyserver pingen en een waarde voor de retourwaarde in milliseconden voor fase 1 en 2 aanvragen**
  
1. Voer een opdrachtprompt met verhoogde bevoegdheid uit door deze stappen uit te voeren:
    
1. Klik op **Start**.
    
2. Typ cmd in het vak **zoekopdracht starten** en druk op CTRL + SHIFT + ENTER.
    
3. Als het dialoogvenster **Gebruikersaccountbeheer** wordt weergegeven, bevestigt u of de actie die wordt weergegeven, is wat u wilt en klikt u vervolgens op **Doorgaan**.
    
2. Typ ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> en druk vervolgens op ENTER. Als u een PsPing of een ander hulpprogramma hebt geïnstalleerd, kunt u dat programma gebruiken in plaats hiervan. 
    
    De opdracht kan er als een van deze voorbeelden uitzien: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping onzeproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping onzeproxy: 80
    
3. Wanneer de tracering stopt met het verzenden van testpakketten, krijgt u een kleine samenvatting met een gemiddelde, in milliseconden, en dat is de waarde die u hebt. Neem een schermafbeelding van de prompt en sla deze op met de naamgevingsconventie. Op dit moment kan het ook handig zijn om het diagram in te vullen met de waarde.
    
Misschien hebt u een tracering in de loop van de tijd genomen, en de client kan de proxy (of de server voor het opsporen van Internet) snel weer verlaten. In dit geval kunnen uw nummers er als volgt uitzien:
  
![Afbeelding met de retourtijd van een client naar een proxy van 2,8 milliseconden.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Als de clientcomputer een van de selectievakjes met toegang tot de proxy-of uitvoerende server is, kunt u de volgende arm van de test uitvoeren door een externe verbinding met die computer uit te voeren, waarna u de opdrachtprompt uitvoert om vanaf de computer te PsPing naar een URL van Office 365. Als u geen toegang hebt tot die computer, kunt u contact opnemen met uw netwerkbronnen voor hulp bij de volgende etappe en de getallen op die manier exact weergeven. Als dat niet mogelijk is, kunt u een PsPing voor de URL van Office 365 in kwestie en vergelijkt u deze met de PsPing of ping-tijd voor uw proxyserver. 
  
Als u bijvoorbeeld 51,84 milliseconden van de client hebt voor de URL van Office 365 en 2,8 u de milliseconden van de client hebt voor de proxy (of uitgangspunt), 49,04 hebt u de bewerkings punten van de 365 Office-app. Ook als u een PsPing van 12,25 milliseconden van de client voor de proxy hebt en 62,01 milliseconden van de client naar de Office 365-URL, dan wordt uw gemiddelde waarde voor de proxy-uituitgang voor de Office 365-URL 49,76 milliseconden.
  
![Extra afbeelding met de ping in milliseconden van client naar proxy naast client naar Office 365, zodat de waarden kunnen worden afgetrokken.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Ter voorbereiding van het oplossen van problemen, is het mogelijk dat u iets interessant vindt. Als u bijvoorbeeld merkt dat u meestal over 40 tot 59 milliseconden van de latentie van de proxy of uitgangspunt naar de URL van Office 365 gaat, en een client de latentie van een client voor proxy of uitgangspunt willen hebben van 3 tot 7 milliseconden (afhankelijk van het aantal netwerkverkeer dat u tijdens de laatste tijd) ziet, want u weten dat iets mis is als de laatste drie client-naar-proxy-of uitgangs basislijnen een latentie van 45 milliseconds aangeven.
  
### <a name="advanced-methods"></a>Geavanceerde methoden

Als u wilt weten wat er gebeurt met uw Internet verzoeken naar Office 365, moet u bekend zijn met de netwerk traceringen. Het maakt niet uit welke hulpmiddelen u wilt gebruiken voor deze tracering, HTTPWatch, Netmon, Message Analyzer, wireshark, Fiddler, dashboard dashboard, of andere taken kunnen worden uitgevoerd, zolang dit hulpprogramma netwerkverkeer kan vastleggen en filteren. In deze sectie wordt het beste om meer dan een van deze hulpmiddelen uit te voeren voor een compleetere foto van het probleem. Wanneer u gaat testen, kunnen sommige van deze hulpmiddelen ook in eigen gevallen fungeren als proxy's. De hulpprogramma's die worden gebruikt in het Companion-artikel [prestatieproblemen met het oplossen van Office 365](performance-troubleshooting-plan.md), waaronder [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)of [WireShark](https://www.wireshark.org/).
  
Het maken van een prestatie lijn is de eenvoudige kant van deze methode en veel van de stappen zijn dezelfde als wanneer u een prestatieprobleem verhelpt. Voor de geavanceerdere methoden voor het maken van basislijnen moet u netwerk sporen maken en opslaan. In de meeste van de voorbeelden in dit artikel wordt SharePoint Online gebruikt, maar u moet een lijst met veelgebruikte acties ontwikkelen op de Office 365-Services waarop u zich kunt abonneren op testen en opnemen. Dit is een voorbeeld van basislijn:
  
- Lijst met basislijnen voor SPO-* * stap 1: * * Blader naar de startpagina van de SPO-website en voer een netwerk spoor. Sla de tracering op. 
    
- Basislijn lijst voor SPO- **stap 2:** Zoek een term (zoals uw bedrijfsnaam) via Enterprise Search en voer een netwerktracering uit. Sla de tracering op. 
    
- Lijst met basislijnen voor SPO: **stap 3:** een groot bestand uploaden naar een SharePoint Online-documentbibliotheek en een netwerktracering uitvoeren. Sla de tracering op. 
    
- Lijst met basislijnen voor SPO- **stap 4:** browsen op de startpagina van de OneDrive-website en voer een netwerk spoor. Sla de tracering op. 
    
Deze lijst bevat de belangrijkste veelvoorkomende acties die gebruikers uitvoeren op SharePoint Online. De laatste stap voor het aanwijzen van gaan naar OneDrive voor bedrijven, versies van de SharePoint Online-Startpagina (die vaak door bedrijven is aangepast) en de startpagina van OneDrive voor bedrijven, wat niet helemaal is aangepast. Dit is een zeer eenvoudige proef wanneer het gaat om een langzaamere laad site van SharePoint Online. U kunt in uw tests een record maken van dit verschil.
  
Als u zich in het midden van een prestatieprobleem voordoet, zijn veel van de stappen hetzelfde als bij het maken van een basislijn. Netwerktracering wordt kritiek geworden, dus we gaan *how* de belangrijkste punten ernaast gaan volgen. 
  
Om een prestatieprobleem  *op te sporen, moet*  u op het moment van tracering een tracering ondernemen wanneer u de prestaties van het prestatieprobleem ondervindt. U moet beschikken over de juiste hulpprogramma's voor het verzamelen van Logboeken, en u hebt een actieplan nodig, dat wil zeggen een lijst met stappen voor het oplossen van de beste informatie die u kunt nemen. Allereerst moet u de datum en tijd van de test vastleggen, zodat de bestanden kunnen worden opgeslagen in een map die de tijdsinstelling weerspiegelt. Verfijn vervolgens de probleem stappen zelf. Dit zijn de exacte stappen die u moet uitvoeren om te testen. De basisbeginselen voor het maken van de basisversie: als het probleem zich alleen met Outlook voordoet, moet u opnemen dat het gedrag van het probleem optreedt in slechts één Office 365-service. Om het bereik van dit probleem te beperken, kunt u zich richten op iets wat u kunt oplossen. 
  
## <a name="see-also"></a>Zie ook

[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

