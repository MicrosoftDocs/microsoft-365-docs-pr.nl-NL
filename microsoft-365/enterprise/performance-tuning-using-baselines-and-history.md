---
title: Office 365-prestatieafstemming gebruikt basislijnen en prestatiegeschiedenis
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
description: Lees hoe u de geschiedenis van uw clientcomputerverbindingen kunt controleren om u te helpen bij het vroegtijdig opsporen van nieuwe problemen.
ms.openlocfilehash: 314b1acea5935bfd6d93d1da3789657e21cd2d57
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339368"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Office 365-prestatieafstemming gebruikt basislijnen en prestatiegeschiedenis

Er zijn enkele eenvoudige manieren om de verbindingsprestaties tussen uw Office 365 en uw bedrijf te controleren, zodat u een ruwe basislijn van uw connectiviteit kunt vaststellen. Als u de prestatiesgeschiedenis van uw clientcomputerverbindingen kent, kunt u nieuwe problemen vroegtijdig opsporen, problemen identificeren en voorspellen.
  
Als u niet gewend bent om te werken aan prestatieproblemen, is dit artikel ontworpen om u te helpen enkele veelvoorkomende vragen te overwegen, zoals Hoe weet u dat het probleem dat u ziet een prestatieprobleem is en niet een Office 365 service-incident? Hoe kunt u goede prestaties op lange termijn plannen? Hoe kunt u de prestaties in de gaten houden? Als uw team of klanten trage prestaties zien tijdens het gebruik van Office 365 en u zich afvraagt wat deze vragen zijn, leest u verder.
  
> [!IMPORTANT]
> **Hebt u op dit moment een prestatieprobleem tussen Office 365 klant en klant?** Volg de stappen die worden beschreven in het plan voor [prestatieproblemen voor Office 365.](performance-troubleshooting-plan.md) 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Iets wat u moet weten over Office 365 prestaties

Office 365 in een speciaal Microsoft-netwerk met hoge capaciteit dat niet alleen wordt gecontroleerd door automatisering, maar ook door echte personen. Een deel van de rol van het Office 365 cloud is het inbouwen van prestatieafstemming en stroomlijnen waar dit mogelijk is. Aangezien clients van de Office 365 cloud verbinding moeten maken via internet, is er een continue inspanning om de prestaties van de verschillende services Office 365 optimaliseren. Prestatieverbeteringen stoppen nooit echt in de cloud en er is veel ervaring met het gezond en snel houden van de cloud. Als er een prestatieprobleem is dat vanaf uw locatie verbinding maakt met Office 365, kunt u het beste niet beginnen met en wachten op een ondersteuningscase. In plaats daarvan moet u beginnen met het onderzoeken van het probleem van 'van binnen naar buiten'. Dat wil zeggen: begin binnen uw netwerk en werk uw weg naar Office 365. Voordat u een zaak opent met Office 365 ondersteuning, kunt u gegevens verzamelen en acties ondernemen om uw probleem te verkennen en mogelijk op te lossen.
  
> [!IMPORTANT]
> Wees op de hoogte van capaciteitsplanning en limieten in Office 365. Met deze informatie bent u voor op de curve wanneer u een prestatieprobleem probeert op te lossen. Hier is een koppeling naar de Microsoft 365 [en Office 365 servicebeschrijvingen.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) Dit is een centrale hub en alle services die door Office 365 worden aangeboden, hebben een koppeling naar hun eigen Servicebeschrijvingen vanaf hier. Dat betekent dat als u de standaardlimieten voor SharePoint Online wilt zien, u bijvoorbeeld op [SharePoint Online servicebeschrijving](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description) klikt en de SharePoint [onlinelimieten](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)zoekt. 
  
Zorg ervoor dat u de probleemoplossing doorneemt met de kennis dat prestaties een schuivende schaal zijn, dat het niet gaat om het bereiken van een ideale waarde en het permanent onderhouden ervan (als u dit denkt, zijn af en toe taken met een hoge bandbreedte, zoals het instappen van een groot aantal gebruikers of het uitvoeren van grote gegevensmigraties, erg belastend, dus plan dan de gevolgen voor de prestaties). U kunt en moet een goed idee hebben van uw prestatiedoelen, maar veel variabelen spelen in op de prestaties, dus de prestaties variëren. Dat is de aard van de prestaties. 
  
Prestatieproblemen gaan niet over het bereiken van specifieke doelen en het voor onbepaalde tijd behouden van deze getallen, maar het verbeteren van bestaande activiteiten, gezien alle variabelen. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Hoe ziet een prestatieprobleem eruit?

Eerst moet u ervoor zorgen dat wat u ondervindt inderdaad een prestatieprobleem is en niet een service-incident. Een prestatieprobleem verschilt van een service-incident in Office 365. U kunt ze als eerste van elkaar onderscheiden.
  
Als de Office 365 service problemen heeft, is dat een service-incident. U ziet rode of gele pictogrammen onder Huidige status **in** de Microsoft 365-beheercentrum, mogelijk ziet u ook trage prestaties op clientcomputers die verbinding maken met Office 365. Als huidige status bijvoorbeeld een rood pictogram  rapporteert en u Onderzoeken naast Exchange ziet, kunt u dan ook een aantal oproepen ontvangen van personen in uw organisatie die klagen dat clientpostvakken die Exchange Online gebruiken, slecht presteren. In dat geval is het redelijk om ervan uit te gaan dat uw Exchange Online net het slachtoffer is geworden van problemen binnen de Service. 
  
![Het Office 365 Health dashboard met alle werkbelastingen die groen worden weergegeven, behalve Exchange, met Service hersteld.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
Op dit moment moet u, de Office 365-beheerder, de huidige status controleren en vervolgens regelmatig details en geschiedenis weergeven om op de hoogte te blijven van het onderhoud dat we op het systeem uitvoeren.  Het **dashboard Huidige status** is gemaakt om u bij te werken over wijzigingen in en problemen in de service. De notities en uitleg die zijn geschreven naar de gezondheidsgeschiedenis, beheerder naar beheerder, zijn er om u te helpen uw impact te meten en om u op de hoogte te houden van lopende werkzaamheden. 
  
![Een afbeelding van het Office 365 waarin wordt uitgelegd dat de Exchange Online is hersteld en waarom.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Een prestatieprobleem is geen service-incident, ook al kunnen incidenten trage prestaties veroorzaken. Een prestatieprobleem ziet er als volgende uit:
  
- Er treedt een prestatieprobleem op, ongeacht wat het beheercentrum **Huidige status** rapporteert voor de service. 
    
-  Een gedrag dat vroeger relatief naadloos was, duurt lang voordat het is voltooid of nooit is voltooid. 
    
- U kunt het probleem ook repliceren, of u weet in ieder geval dat dit gebeurt als u de juiste reeks stappen doet.
    
-  Als het probleem af en toe is, is er nog steeds een patroon, bijvoorbeeld dat u om 10:00 uur gesprekken hebt van gebruikers die geen betrouwbare toegang hebben tot Office 365 en dat de oproepen rond 12.00 uur zullen afsterven. 
    
Dit klinkt waarschijnlijk bekend; misschien te bekend. Zodra u weet dat het een prestatieprobleem is, wordt de vraag' Wat doet u nu? De rest van dit artikel helpt u precies dat te bepalen.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Het prestatieprobleem definiëren en testen

Prestatieproblemen ontstaan vaak in de tijd, dus het kan lastig zijn om het werkelijke probleem te definiëren. U moet een goede probleemverklaring en een goed idee van de context van problemen maken, en vervolgens moet u herhaalbare teststappen uitvoeren om de dag te winnen. Anders gaat u mogelijk verloren zonder uw eigen schuld. Waarom? Hier zijn enkele voorbeelden van problemen die onvoldoende informatie bevatten:
  
- Het overstappen van mijn Postvak IN naar mijn agenda was iets wat ik niet heb gezien en nu is het een koffiepauze. Kunt u ervoor zorgen dat het zich zo gedragen als vroeger?
    
- Het uploaden van mijn bestanden naar SharePoint Online duurt een eeuwigheid. Waarom is het traag in de middag, maar een andere keer is het snel? Kan het niet gewoon snel zijn?
    
De bovenstaande probleemverklaringen bieden verschillende grote uitdagingen. Er zijn met name veel dubbelzinnigheden om mee om te gaan. bijvoorbeeld:
  
- Het is niet duidelijk hoe het schakelen tussen Postvak IN en Agenda op de laptop werkt.
    
- Wanneer de gebruiker zegt: 'Kan het niet gewoon snel zijn', wat is 'snel'?
    
- Hoe lang is 'voor altijd'? Is dat enkele seconden of minuten, of kan de gebruiker gaan lunchen en wordt deze tien minuten nadat de gebruiker terug is, klaar?
    
Dit alles zonder rekening te houden met het feit dat de beheerder en probleemoplosser niet op de hoogte kunnen zijn van veel details uit probleemverklaringen zoals deze. Bijvoorbeeld wanneer het probleem zich voordeed. Dat de gebruiker thuis werkt en alleen maar langzaam ziet schakelen terwijl hij of zij een thuisnetwerk gebruikt. Dat de gebruiker meerdere andere RAM-intensieve toepassingen moet uitvoeren op de lokale client, of dat de gebruiker een ouder besturingssysteem gebruikt of geen recente updates heeft uitgevoerd.
  
Wanneer gebruikers een prestatieprobleem melden, moet er veel informatie worden verzameld. Het verzamelen van deze gegevens maakt deel uit van een proces dat scoping van het probleem wordt genoemd, of het onderzoeken ervan. Het volgende is een eenvoudige scopinglijst die u kunt gebruiken om informatie over uw prestatieprobleem te verzamelen. Deze lijst is niet volledig, maar het is een plek om een eigen lijst te starten: 
  
- Op welke datum is het probleem gebeurd en rond welk tijdstip van de dag of nacht?
    
- Welk type clientcomputer gebruikte u en hoe maakt deze verbinding met het zakelijke netwerk (VPN, Wired, Wireless)?
    
- Werkte u op afstand of was u op kantoor?
    
- Hebt u dezelfde acties op een andere computer geprobeerd en hetzelfde gedrag gezien?
    
- Doorloop de stappen die u de problemen geven, zodat u de acties kunt schrijven die u hebt genomen.
    
- Hoe traag zijn de prestaties in seconden of minuten?
    
- Waar ter wereld bevindt u zich?
    
Sommige van deze vragen zijn duidelijker dan andere. De meeste mensen begrijpen dat een probleemoplosser de exacte stappen nodig heeft om het probleem te reproduceren. Hoe kunt u anders opnemen wat er mis is en hoe kunt u anders testen of het probleem is opgelost? Minder voor de hand liggend zijn dingen als 'Welke datum en tijd hebt u het probleem gezien?' en 'Waar ter wereld bevindt u zich?', informatie die u kunt gebruiken in combinatie. Afhankelijk van wanneer de gebruiker aan het werk was, kan een paar uur tijdverschil betekenen dat er al onderhoud wordt gedaan aan delen van het netwerk van uw bedrijf. Als uw bedrijf bijvoorbeeld een hybride implementatie heeft, zoals een hybride SharePoint Search, waarmee zoekopdrachten kunnen worden uitgevoerd in zowel SharePoint Online als een on-premises SharePoint Server 2013-exemplaar, worden er mogelijk updates uitgevoerd in de on-premises farm. Als uw bedrijf allemaal in de cloud is, kan systeemonderhoud bestaan uit het toevoegen of verwijderen van netwerkhardware, het uitrollen van updates die voor het hele bedrijf zijn, of het aanbrengen van wijzigingen in DNS of andere kerninfrastructuur.
  
Wanneer u een prestatieprobleem oplost, lijkt het een beetje op een plaats delict. U moet nauwkeurig en oplettend zijn om conclusies te trekken uit het bewijs. Hiervoor moet u een goede probleemverklaring krijgen door bewijs te verzamelen. Het moet de context van de computer, de context van de gebruiker, het begin van het probleem en de exacte stappen bevatten die het prestatieprobleem hebben blootgelegd. Deze probleemverklaring moet de bovenste pagina in uw notities zijn en blijven. Door de probleemverklaring opnieuw te doorlopen nadat u aan de oplossing hebt gewerkt, neemt u de stappen om te testen en te bewijzen of de acties die u ondernomen hebt het probleem hebben opgelost. Dit is essentieel om te weten wanneer uw werk, daar, klaar is.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Weet u hoe de prestaties er vroeger uit zien als deze goed waren?

Als u pech hebt, weet niemand het. Niemand had getallen. Dat betekent dat niemand de eenvoudige vraag 'Over hoeveel seconden heeft het gebruikt om een Postvak IN in Office 365 weer te geven' kan beantwoorden, of 'Hoe lang heeft het duren voordat de leidinggevenden een Lync Online-vergadering hebben gehad?', wat een veelvoorkomende scenario is voor veel bedrijven.
  
Wat hier ontbreekt, is een basislijn voor prestaties.
  
Basislijnen geven u een context voor uw prestaties. U moet af en toe een basislijn nemen om regelmatig te werken, afhankelijk van de behoeften van uw bedrijf. Als u een groter bedrijf bent, kan uw Operations-team al basislijnen voor uw on-premises omgeving maken. Als u bijvoorbeeld alle Exchange-servers patcht op de eerste maandag van de maand en al uw SharePoint-servers op de derde maandag, heeft uw Operations-team waarschijnlijk een lijst met taken en scenario's die na het patchen worden uitgevoerd, om te bewijzen dat kritieke functies operationeel zijn. U opent bijvoorbeeld het Postvak IN, klikt op Verzenden/ontvangen en zorgt ervoor dat de mappen worden bijgewerkt of bladert in SharePoint op de hoofdpagina van de site, gaat naar de pagina Zoeken in het bedrijf en doet een zoekopdracht die resultaten oplevert.
  
Als uw toepassingen in Office 365 staan, kunt u de tijd (in milliseconden) meten vanaf een clientcomputer in uw netwerk, naar een uitgangspunt of het punt waar u uw netwerk verlaat en naar Office 365. Hier vindt u enkele handige basislijnen die u kunt onderzoeken en opnemen:
  
- Identificeer de apparaten tussen uw clientcomputer en het uitgangspunt, bijvoorbeeld uw proxyserver.
    
  - U moet uw apparaten kennen, zodat u context (IP-adressen, type apparaat, enzovoort) hebt voor prestatieproblemen die zich voordoen.
    
  - Proxyservers zijn veelvoorkomende uitgangspunten, dus u kunt uw webbrowser controleren om te zien welke proxyserver deze kan gebruiken, indien van toepassing.
    
  - Er zijn hulpprogramma's van derden die uw netwerk kunnen ontdekken en in kaart kunnen brengen, maar de veiligste manier om uw apparaten te kennen, is door een lid van uw netwerkteam te vragen.
    
- Identificeer uw internetprovider (internetprovider), schrijf de contactgegevens op en vraag hoeveel circuits u hebt.
    
- Identificeer binnen uw bedrijf resources voor de apparaten tussen uw client en het uitgangspunt of identificeer een contactpersoon voor noodgevallen om mee te praten over netwerkproblemen.
    
Hier zijn enkele basislijnen die u kunt berekenen met eenvoudige tests met hulpprogramma's:
  
- Tijd van uw clientcomputer naar het uitgangspunt in milliseconden
    
- Tijd van het uitgangspunt naar Office 365 in milliseconden
    
- Locatie in de wereld van de server die de URL's voor Office 365 wanneer u bladert
    
- De snelheid van de DNS-resolutie van uw internetprovider in milliseconden, inconsistenties in de ontvangst van pakketten (netwerk jitter), upload- en downloadtijden in milliseconden
    
Als u niet bekend bent met het uitvoeren van deze stappen, gaan we verder met meer informatie in dit artikel. 
  
## <a name="what-is-a-baseline"></a>Wat is een basislijn?

U weet wat de gevolgen zijn wanneer het fout gaat, maar als u uw historische prestatiegegevens niet kent, is het niet mogelijk om een context te hebben voor hoe slecht het kan zijn geworden en wanneer. Dus zonder basislijn ontbreekt de belangrijkste aanwijzing om de puzzel op te lossen: de afbeelding in het puzzelvak. Bij prestatieproblemen hebt u een *vergelijkingspunt nodig.* Eenvoudige basislijnen voor prestaties zijn niet moeilijk te nemen. Uw Operations-team kan worden belast met het uitvoeren van deze taken volgens een planning. Stel dat uw verbinding er zo uitziet: 
  
![Een eenvoudige netwerkafbeelding met client, proxy en Office 365 cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Dat betekent dat u hebt gecontroleerd bij uw netwerkteam en hebt ontdekt dat u uw bedrijf voor internet verlaat via een proxyserver en dat deze proxy alle aanvragen verwerkt die uw clientcomputer naar de cloud verzendt. In dit geval moet u een vereenvoudigde versie van uw verbinding tekenen waarin alle tussenliggende apparaten worden vermeld. Voeg nu hulpprogramma's in die u kunt gebruiken om de prestaties te testen tussen de client, het uitgangspunt (waar u uw netwerk verlaat voor internet) en de Office 365 cloud.
  
![Basic network with client, proxy, and cloud, and tools suggestions PSPing, TraceTCP, and network traces.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
De opties worden weergegeven als **Eenvoudig** en Geavanceerd **vanwege** de hoeveelheid expertise die u nodig hebt om de prestatiegegevens te vinden. Een netwerkspoor neemt veel tijd in vergelijking met het uitvoeren van opdrachtregelhulpmiddelen zoals PsPing en TraceTCP. Deze twee opdrachtregelhulpmiddelen zijn gekozen omdat ze geen ICMP-pakketten gebruiken, die worden geblokkeerd door Office 365 en omdat ze in milliseconden de tijd geven die nodig is om de clientcomputer te verlaten, of proxyserver (als u toegang hebt) en bij Office 365. Elke afzonderlijke hop van de ene naar de andere computer krijgt een tijdswaarde en dat is heel goed voor basislijnen. Net zo belangrijk is dat u met deze opdrachtregelhulpmiddelen een poortnummer aan de opdracht kunt toevoegen, dit is handig omdat Office 365 communiceert via poort 443, de poort die wordt gebruikt door Secure Sockets Layer en Transport Layer Security (SSL en TLS). Andere hulpprogramma's van derden kunnen echter betere oplossingen zijn voor uw situatie. Microsoft biedt geen ondersteuning voor al deze hulpprogramma's, dus als psPing en TraceTCP om de een of andere reden niet werken, gaat u verder met een netwerkspoor met een hulpprogramma zoals Netmon. 
  
U kunt een basislijn maken vóór werkuren, opnieuw tijdens intensief gebruik en daarna opnieuw na uren. Dit betekent dat u mogelijk een mapstructuur hebt die er op het einde een beetje zo uitziet:
  
![Afbeelding die een manier voorstelt om uw prestatiegegevens in te delen in mappen.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Kies ook een naamgevingsconventie voor uw bestanden. Dit zijn enkele voorbeelden:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Er zijn veel verschillende manieren om dit te doen, maar het gebruik van de indeling **\<dateTime\>\<what's happening in the test\>** is een goede plek om te beginnen. Als u hier zorgvuldig mee bezig bent, helpt dit veel wanneer u problemen later probeert op te lossen. Later kunt u zeggen: 'Ik heb twee sporen op 8 februari, een goede prestatie en een slecht resultaat, zodat we ze kunnen vergelijken'. Dit is zeer handig voor het oplossen van problemen. 
  
U moet een georganiseerde manier hebben om uw historische basislijnen te behouden. In dit voorbeeld hebben de eenvoudige methoden drie opdrachtregeluitvoeren geproduceerd en zijn de resultaten verzameld als schermafbeeldingen, maar in plaats daarvan hebt u mogelijk netwerkopnamebestanden. Gebruik de methode die het beste voor u werkt. Sla uw historische basislijnen op en raadpleeg deze op punten waar u wijzigingen ziet in het gedrag van onlineservices. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Waarom prestatiegegevens verzamelen tijdens een pilot?

Er is geen betere tijd om basislijnen te maken dan tijdens een pilot van de Office 365 service. Uw kantoor kan duizenden gebruikers, honderdduizenden of vijf gebruikers hebben, maar zelfs met een klein aantal gebruikers kunt u tests uitvoeren om schommelingen in prestaties te meten. In het geval van een groot bedrijf kan een representatieve steekproef van enkele honderden gebruikers die Office 365 piloten, naar buiten worden geprojecteerd op enkele duizenden, zodat u weet waar problemen kunnen optreden voordat ze optreden.
  
In het geval van een klein bedrijf, waarbij instappen betekent dat alle gebruikers tegelijk naar de service gaan en er geen pilot is, moet u prestatie-metingen houden, zodat u gegevens hebt om aan iedereen weer te geven die mogelijk een slecht presterende bewerking moet oplossen. Als u bijvoorbeeld merkt dat u plotseling door uw gebouw kunt lopen in de tijd die nodig is om een middelgrote afbeelding te uploaden, waar dit vroeger heel snel gebeurde.
  
## <a name="how-to-collect-baselines"></a>Basislijnen verzamelen

Voor alle probleemoplossingsplannen moet u deze dingen minimaal identificeren:
  
- De clientcomputer die u gebruikt (het type computer of apparaat, een IP-adres en de acties die het probleem hebben veroorzaakt)
    
- Waar de clientcomputer zich in de wereld bevindt (bijvoorbeeld of deze gebruiker een VPN gebruikt voor het netwerk, op afstand werkt of op het bedrijfs intranet)
    
- Het uitgangspunt dat de clientcomputer gebruikt vanuit uw netwerk (het punt waarop het verkeer uw bedrijf verlaat voor een internetprovider of internet)
    
 U kunt de indeling van uw netwerk vinden via de netwerkbeheerder. Als u een klein netwerk hebt, bekijkt u de apparaten die u verbinden met internet en belt u uw internetprovider als u vragen hebt over de indeling. Maak een afbeelding van de uiteindelijke indeling voor uw verwijzing. 
  
Deze sectie is onderverdeeld in eenvoudige opdrachtregelhulpmiddelen en -methoden en meer geavanceerde hulpmiddelenopties. We behandelen eerst eenvoudige methoden. Maar als u op dit moment een prestatieprobleem hebt, moet u naar geavanceerde methoden gaan en het voorbeeld van het actieplan voor prestatieproblemen uitproberen.
  
### <a name="simple-methods"></a>Eenvoudige methoden

Het doel van deze eenvoudige methoden is om eenvoudige prestatielijnlijnen in de tijd op te nemen, te begrijpen en correct op te slaan, zodat u op de hoogte bent van de Office 365 prestaties. Hier is het eenvoudige diagram voor eenvoudig, zoals u eerder hebt gezien:
  
![Basic network with client, proxy, and cloud, and tools suggestions PSPing, TraceTCP, and network traces.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP is opgenomen in deze schermafbeelding, omdat het een handig hulpmiddel is om in milliseconden weer te geven hoe lang een aanvraag duurt om te verwerken, en hoeveel netwerkhops of verbindingen van de ene computer naar de volgende, die de aanvraag nodig heeft om een bestemming te bereiken. TraceTCP kan ook de namen geven van servers die tijdens hops worden gebruikt, wat handig kan zijn voor een Microsoft Office 365 probleemoplosser in ondersteuning. > TraceTCP-opdrachten kunnen heel eenvoudig zijn, zoals: >> Vergeet niet om het poortnummer in de opdracht  `tracetcp.exe outlook.office365.com:443` op te nemen! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) is een gratis download, maar is afhankelijk van Wincap. Wincap is een hulpprogramma dat ook wordt gebruikt en geïnstalleerd door Netmon. We gebruiken Netmon ook in de sectie Geavanceerde methoden. 
  
 Als u meerdere kantoren hebt, moet u ook op elk van deze locaties een set gegevens van een client bewaren. Deze test meet de latentie, die in dit geval een getalwaarde is die de tijd beschrijft tussen een client die een aanvraag naar Office 365 verstuurt en Office 365 de aanvraag beantwoordt. Het testen vindt zijn oorsprong in uw domein op een clientcomputer en kijkt naar een retourreis vanuit uw netwerk, via een uitgangspunt, via internet naar Office 365 en terug. 
  
Er zijn een paar manieren om met het uitgangspunt om te gaan, in dit geval de proxyserver. U kunt van 1 naar 2 en vervolgens 2 tot 3 traceren en vervolgens de getallen in milliseconden toevoegen om een definitief totaal te krijgen aan de rand van uw netwerk. U kunt de verbinding ook zo configureren dat de proxy voor Office 365 wordt overgeslagen. In een groter netwerk met een firewall, reverse proxy of een combinatie van de twee moet u mogelijk uitzonderingen maken op de proxyserver, waardoor het verkeer voor veel URL's kan worden doorgelaten. Zie url's en IP-adresbereiken voor Office 365 lijst met eindpunten die door Office 365 [worden gebruikt.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) Als u een authenticerende proxy hebt, begint u met het testen van uitzonderingen voor het volgende:
  
- Poorten 80 en 443
    
- TCP- en HTTP's
    
- Verbindingen die uitgaand zijn van een van deze URL's:
    
- \*.microsoftonline.com
    
- \*.microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*.outlook.com
    
- \*.lync.com
    
- osub.microsoft.com
    
Alle gebruikers moeten toegang hebben tot deze adressen zonder tussenkomst van proxy's of verificatie. Op een kleiner netwerk moet u deze toevoegen aan de lijst met proxy-bypasss in uw webbrowser. 
  
Als u deze wilt toevoegen aan uw lijst met proxy-bypasss in Internet Explorer, gaat u naar **Extra** \> **internetopties** \> **Verbindingen** \> **LAN-instellingen** \> **Geavanceerd.** Op het tabblad Geavanceerd vindt u ook de proxyserver en de proxyserverpoort. Mogelijk moet u op het selectievakje **Een proxyserver** voor uw LAN gebruiken klikken om toegang te krijgen **tot** de knop Geavanceerd. U moet ervoor zorgen dat proxyserver voor **lokale** adressen omzeilen is ingeschakeld. Wanneer u op **Geavanceerd** klikt, ziet u een tekstvak waarin u uitzonderingen kunt invoeren. Scheid de jokerteken-URL's die hierboven worden vermeld, bijvoorbeeld door punt-dubbele punt:
  
\*.microsoftonline.com; \*.sharepoint.com
  
Wanneer u de proxy hebt overgeslagen, kunt u ping of PsPing rechtstreeks op een url Office 365 gebruiken. De volgende stap is het testen van ping **outlook.office365.com.** Of als u PsPing **gebruikt of** een ander hulpmiddel waarmee u een poortnummer aan de opdracht kunt leveren, psping tegen portal.microsoftonline.com:443 om de gemiddelde retourtijd in milliseconden te zien. 
  
De retourtijd, of RTT, is een getalwaarde die meet hoe lang het duurt om een HTTP-aanvraag naar een server zoals outlook.office365.com te verzenden en een antwoord terug te krijgen dat bevestigt dat de server weet dat u het hebt gedaan. U ziet dit soms afgekort als RTT. Dit moet een relatief korte tijd zijn.
  
U moet [PSPing](/sysinternals/downloads/psping) of een ander hulpprogramma gebruiken dat geen ICMP-pakketten gebruikt die door de Office 365 worden geblokkeerd om deze test uit te kunnen doen. 
  
 **PsPing gebruiken om een algemene retourtijd in milliseconden rechtstreeks vanuit een url Office 365 krijgen**
  
1. Voer een opdrachtprompt met verhoogde opdracht uit door de volgende stappen uit te voeren:
    
1. Klik op **Start**.
    
2. Typ cmd **in het** vak Zoeken starten en druk op Ctrl+Shift+Enter.
    
3. Als het **dialoogvenster Gebruikersaccountbeheer** wordt weergegeven, controleert u of de actie die wordt weergegeven, is wat u wilt en klikt u vervolgens op **Doorgaan.**
    
2. Ga naar de map waar het hulpprogramma (in dit geval PsPing) is geïnstalleerd en test deze Office 365 URL's:
    
  - psping admin.microsoft.com:443
    
  - psping microsoft-my.sharepoint.com:443
    
  - psping outlook.office365.com:443
    
  - psping www.yammer.com:443
    
    ![De opdracht PSPing gaat naar microsoft-my.sharepoint.com poort 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Zorg ervoor dat u het poortnummer van 443 op moet nemen. Houd er Office 365 werkt op een versleuteld kanaal. Als u PsPing zonder het poortnummer hebt, mislukt uw aanvraag. Wanneer u uw korte lijst hebt gepingt, kijkt u naar de gemiddelde tijd in milliseconden (ms). Dat is wat u wilt opnemen!
  
![Afbeelding met een afbeelding van client-naar-proxy-PSPing met een retourtijd van 2,8 milliseconden.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Als u niet bekend bent met proxy bypass en de voorkeur geeft aan stap voor stap, moet u eerst de naam van de proxyserver weten. Ga in Internet Explorer naar **Tools** \> **Internet Options** \> **Connections** LAN \> **settings** \> **Advanced**. Op **het** tabblad Geavanceerd wordt de proxyserver weergegeven. Ping die proxyserver bij een opdrachtprompt door deze taak uit te voeren: 
  
 **De proxyserver pingen en een retourwaarde krijgen in milliseconden voor fase 1 tot en met 2**
  
1. Voer een opdrachtprompt met verhoogde opdracht uit door de volgende stappen uit te voeren:
    
1. Klik op **Start**.
    
2. Typ cmd **in het** vak Zoeken starten en druk op Ctrl+Shift+Enter.
    
3. Als het **dialoogvenster Gebruikersaccountbeheer** wordt weergegeven, controleert u of de actie die wordt weergegeven, is wat u wilt en klikt u vervolgens op **Doorgaan.**
    
2. Typ ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> en druk op Enter. Als u PsPing of een ander hulpprogramma hebt geïnstalleerd, kunt u ervoor kiezen om dat hulpprogramma te gebruiken. 
    
    Uw opdracht ziet er mogelijk uit als een van deze voorbeelden: 
    
  - ping ourproxy.ourdomain.industry.business.com
    
  - ping 155.55.121.55
    
  - ping ourproxy
    
  - psping ourproxy.ourdomain.industry.business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy:80
    
3. Wanneer de trace stopt met het verzenden van testpakketten, krijgt u een klein overzicht met een gemiddelde, in milliseconden, en dat is de waarde waar u achter aan zit. Maak een schermafbeelding van de prompt en sla deze op met uw naamgevingsconventie. Op dit moment kan het ook helpen om het diagram in te vullen met de waarde.
    
Misschien hebt u 's morgens vroeg een trace gemaakt en kan uw client snel bij de proxy (of via een uitgangsserver naar internet) komen. In dit geval kunnen uw getallen er als volgende uitzien:
  
![Afbeelding met de retourtijd van een client naar een proxy van 2,8 milliseconden.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Als uw clientcomputer een van de weinige geselecteerde gebruikers is met toegang tot de proxyserver (of de uitgangsserver), kunt u het volgende deel van de test uitvoeren door op afstand verbinding te maken met die computer en de opdrachtprompt naar PsPing uit te voeren naar een Office 365-URL. Als u geen toegang hebt tot die computer, kunt u contact opnemen met uw netwerkbronnen voor hulp bij de volgende leg en op die manier exacte nummers krijgen. Als dat niet mogelijk is, neemt u een PsPing tegen de Office 365 URL in kwestie en vergelijkt u deze met de PsPing- of Ping-tijd tegen de proxyserver. 
  
Als u bijvoorbeeld 51,84 milliseconden van de client naar de OFFICE 365-URL hebt en u 2,8 milliseconden van de client naar de proxy (of het uitgangspunt) hebt, hebt u 49,04 milliseconden van het uitgangspunt naar Office 365. Als u een PsPing van 12,25 milliseconden hebt van de client naar de proxy tijdens de hoogte van de dag en 62,01 milliseconden van de client naar de URL van Office 365, is de gemiddelde waarde voor de proxy die naar de OFFICE 365-URL gaat 49,76 milliseconden.
  
![Extra afbeelding met de ping in milliseconden van client naar proxy naast client Office 365 zodat de waarden kunnen worden afgetrokken.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
In termen van probleemoplossing kunt u iets interessants vinden door deze basislijnen te behouden. Bijvoorbeeld: als u in het algemeen ongeveer 40 tot 59 milliseconden latentie hebt van de proxy of het uitgangspunt naar de URL van Office 365 en een client voor proxy- of uitgangspuntlatentie van ongeveer 3 tot 7 milliseconden hebt (afhankelijk van het netwerkverkeer dat u op dat moment ziet) dan weet u zeker dat er iets problematisch is als uw laatste drie client-to-proxy- of uitgangslijnlijnen een latentie van 45 milliseconden laten zien.
  
### <a name="advanced-methods"></a>Geavanceerde methoden

Als u echt wilt weten wat er gebeurt met uw internetaanvragen om Office 365, moet u vertrouwd raken met netwerksporen. Het maakt niet uit welke hulpprogramma's u wilt gebruiken voor deze traces, HTTPWatch, Netmon, Message Analyzer, Wireshark, Fiddler, Developer Dashboard tool of andere functies, zolang dit hulpprogramma netwerkverkeer kan vastleggen en filteren. In deze sectie ziet u dat het handig is om meer dan een van deze hulpprogramma's uit te voeren om een vollediger beeld van het probleem te krijgen. Wanneer u aan het testen bent, fungeren sommige van deze hulpprogramma's ook als proxies in hun eigen recht. Hulpmiddelen die worden gebruikt in het begeleidende artikel Performance [troubleshooting plan for Office 365](performance-troubleshooting-plan.md), include [Netmon 3.4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/), or [WireShark](https://www.wireshark.org/).
  
Het maken van een basislijn voor prestaties is het eenvoudige deel van deze methode en veel van de stappen zijn hetzelfde als wanneer u een prestatieprobleem oplost. Voor de geavanceerdere methoden voor het maken van basislijnen voor prestaties moet u netwerksporen nemen en opslaan. De meeste voorbeelden in dit artikel gebruiken SharePoint Online, maar u moet een lijst met algemene acties ontwikkelen in de Office 365-services waarop u zich abonneert om te testen en op te nemen. Hier is een basislijnvoorbeeld:
  
- Basislijnlijst voor SPO - ** Stap 1: ** Blader op de startpagina van de SPO-website en doe een netwerkspoor. Sla de trace op. 
    
- Basislijnlijst voor SPO - **Stap 2:** Zoek via Enterprise Search naar een term (zoals uw bedrijfsnaam) en doe een netwerkspoor. Sla de trace op. 
    
- Basislijnlijst voor SPO - **Stap 3:** Upload een groot bestand naar een SharePoint Online-documentbibliotheek en een netwerkspoor maken. Sla de trace op. 
    
- Basislijnlijst voor SPO - **Stap 4:** Blader op de startpagina van de OneDrive website en doe een netwerkspoor. Sla de trace op. 
    
Deze lijst moet de belangrijkste algemene acties bevatten die gebruikers uitvoeren tegen SharePoint Online. In de laatste stap, om naar OneDrive voor Bedrijven te gaan, wordt een vergelijking gemaakt tussen de belasting van de startpagina van SharePoint Online (die vaak door bedrijven wordt aangepast) en OneDrive voor Bedrijven startpagina, die zelden wordt aangepast. Dit is een zeer eenvoudige test als het gaat om een trage SharePoint Online-site. U kunt een record van dit verschil maken in uw testen.
  
Als u in het midden van een prestatieprobleem zit, zijn veel van de stappen hetzelfde als bij het maken van een basislijn. Netwerksporen worden kritiek, dus we gaan nu om  *met*  de belangrijke traceringen. 
  
Als u een prestatieprobleem  *wilt*  oplossen, moet u op dit moment een trace nemen op het moment dat u het prestatieprobleem ondervindt. U hebt de juiste hulpmiddelen nodig om logboeken te verzamelen en u hebt een actieplan nodig, dat wil zeggen een lijst met acties voor het oplossen van problemen die moeten worden ondernomen om de beste informatie te verzamelen die u kunt. Het eerste wat u moet doen, is de datum en tijd van de test opnemen, zodat de bestanden kunnen worden opgeslagen in een map die de tijdsinstelling weerspiegelt. Vervolgens kunt u beperken tot de probleemstappen zelf. Dit zijn de exacte stappen die u voor het testen gaat gebruiken. Vergeet de basisbeginselen niet: als het probleem alleen met Outlook is, moet u registreren dat het probleemgedrag slechts in één service Office 365 gebeurt. Als u het bereik van dit probleem verkleint, kunt u zich concentreren op iets dat u kunt oplossen. 
  
## <a name="see-also"></a>Zie ook

[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)