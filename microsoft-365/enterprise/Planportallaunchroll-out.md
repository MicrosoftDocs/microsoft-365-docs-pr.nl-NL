---
title: Rollen plan voor het lanceren van uw portal in SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In dit artikel wordt beschreven hoe u de introductie van uw portal in SharePoint Online kunt plannen en welke stappen u moet uitvoeren om een succesvolle lancering te ondernemen
ms.openlocfilehash: e22fa4d9cbfed79841d844f111e3eb91a708512e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689531"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Rollen plan voor het lanceren van uw portal in SharePoint Online

Een portal is een SharePoint-site op uw intranet met een groot aantal sitebezoekers die inhoud op de site gebruiken. In grote organisaties kan dit verschillende oorzaken hebben; bijvoorbeeld een bedrijfsportal en een HR-Portal. Meestal hebben portals relatief weinig personen die de site en de inhoud ervan maken en maken. De meeste bezoekers van de portal lezen en gebruiken de inhoud.

In dit artikel wordt beschreven hoe u een implementatie en Uitvouw schema plant voor SharePoint Online. Dit levert ook benaderingen voor het volgen van traditionele belasting tests zijn niet toegestaan op SharePoint Online. SharePoint Online is een cloudservice en de geladen functies, status en algemeen saldo van de belasting van de service worden beheerd door Microsoft.

Als u hulp nodig hebt bij het maken van een succesvolle Portal, volgt u de basisprincipes, oefeningen en aanbevelingen die specifiek zijn voor het [maken, starten en onderhouden van een gezonde Portal](https://go.microsoft.com/fwlink/?linkid=2105838) 

De implementatiemethode is hieronder gemarkeerd.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Overzicht van capaciteitsplanning in SharePoint Online
Om de capaciteit efficiënt te kunnen gebruiken en de onverwachte groei van een farm te regelen, hebben we automatisering voor het bijhouden van bepaalde gebruiksscenario's. Hoewel de exacte groei onvoorspelbaar is voor één Tenant in een van de bedrijven, kan de geaggregeerde som van aanvragen gedurende een bepaalde periode voorspelbaar zijn. Door de groeitrends te identificeren in SharePoint Online, kunnen we voor toekomstige expansie plannen. Voor meer informatie over [capaciteitsplanning en belasting test van SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md).

Een belangrijk onderdeel van een succesvolle lancering is de aanpak van ' Golf ' of ' gefaseerd gephasd '. 

## <a name="can-i-load-test-sharepoint-online"></a>Kan ik testen van SharePoint Online laden?
SharePoint Online is een gedeelde omgeving met meerdere tenants die evenwichtig over Farms en schaal wordt aangepast. Laad het testen van een omgeving, zoals SharePoint Online, waarvan de schaal voortdurend continu resultaten geeft, maar deze niet is toegestaan. 

Meer informatie:  [capaciteitsplanning en belasting test van SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Pagina's optimaliseren door aanbevolen richtlijnen te volgen
Pagina's van een on-premises implementatie mogen niet simpelweg worden verplaatst wanneer ze zich bevinden op SharePoint Online, zonder ze te reviseren tegen aanbevolen richtlijnen voor SharePoint Online. De beste manier is om de startpagina van een site of portal in SharePoint te optimaliseren, aangezien dit de meeste gebruikers in uw organisatie toegang hebben tot het beginpunt voor uw site (s).

U dient enkele van de volgende basis factoren te overwegen:
- On-premises implementaties kunnen traditionele caches voor servers, zoals objectcache, uitvoercache en cache voor blobcache, gebruiken. Met de verschillen tussen de topologie in de Cloud zijn deze opties niet noodzakelijkerwijs beschikbaar voor de doorschijnende-schaal verschillen, zodat deze minder levensvatbare methoden zijn.
- Pagina's/functies/aanpassingen die worden gebruikt voor het Cloud verbruik, moeten worden geoptimaliseerd voor hoge latentie en de Distributed locaties van gebruikers, zodat gebruikers in verschillende gebieden of regio's een consistente ervaring hebben. Cloud biedt optimalisaties zoals netwerken voor content levering (CDN) voor het optimaliseren van een uitgesplitste gebruikersbasis en voor moderne SharePoint, de laatste bekende goede (LKG) wordt gebruikt door onze kant-en-klare webonderdelen (OOTB).

### <a name="what-to-do"></a>Actie:
 - Voor alle sitepagina's in SharePoint Online gebruikt u het [hulpprogramma pagina diagnose](https://aka.ms/perftool), een chroom extensie waarmee u hulp kunt analyseren en leveren. Dit kan worden gebruikt door site-eigenaren, editors, beheerders en ontwikkelaars, omdat dit is bedoeld om te beginnen met analyse en optimalisering.
 - Ontwikkelaars dienen ook ontwikkelingsprogramma's te gebruiken, zoals F12 browser Developer Tool en CTRL-F12 in de browser op moderne pagina's. [Fiddler](https://www.telerik.com/download/fiddler) kan ook worden gebruikt om de grootte van de pagina te bekijken (de grootte van de pagina in megabytes) van de pagina en het aantal oproepen en onderdelen die de volledige pagina belasting beïnvloeden. 

Dit gedeelte is een beknopt overzicht van het optimaliseren van pagina's.  Zie voor meer informatie:  [een gezonde portal maken en starten en onderhouden](https://go.microsoft.com/fwlink/?linkid=2105838).

## <a name="follow-a-wave--phased-roll-out-approach"></a>Een in-en uitvouwen met een golf/gefaseerde methode
Met de traditionele, grote begeleidende aanpak van site start kunt u niet verifiëren dat aanpassingen, externe bronnen, services of processen zijn getest op de juiste schaal. Dit houdt niet in dat u maanden duurt voor de lancering, maar u wordt aangeraden minstens enkele dagen afhankelijk van de grootte van uw organisatie. Na het uitvoeren van een kantelings abonnement krijgt u daarom de mogelijkheid om problemen te onderbreken en op te lossen voordat u verder gaat met de volgende fase, en verlaagt u daarom het mogelijke aantal gebruikers dat invloed heeft op problemen. SharePoint omdat een service een service schaalt op basis van gebruik en voor speling en u hoeft u niet te informeren over uw lancering, dan moet u de richtlijnen volgen om te zorgen dat u succes hebt.
  
Zoals u ziet in de volgende afbeelding, is het aantal gebruikers dat is uitgenodigd aanzienlijk hoger dan de personen die de site gebruiken. In deze afbeelding ziet u een strategie voor het samenstellen van een release. Met deze methode kunt u aangeven hoe u de SharePoint-site wilt verbeteren voordat het merendeel van de gebruikers wordt weergegeven.
  
![Grafiek met genodigden en actieve gebruikers](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
In de pilot fase is het handig om feedback van gebruikers te krijgen die de organisatie vertrouwt en bekend wordt. Op deze manier kunt u ook meten hoe het systeem wordt gebruikt en hoe dit wordt uitgevoerd.
  
U kunt tijdens elk van de Golf gebruikers feedback over de functies en de prestaties van de implementatie van de implementatie van de toepassing verzamelen. Dit heeft het voordeel van het gebruik van de computer en het maken van verbeteringen omdat het systeem meer wordt gebruikt. Hiermee kunnen we er ook voor zorgen dat de site groter wordt geladen omdat de site wordt uitgerold naar meer en meer gebruikers en gecombineerd met de richtlijnen voor het optimaliseren van pagina's, dat de gebruikers een positieve ervaring bieden.

### <a name="what-to-do"></a>Actie:
- Bepaal de timing van elke fase en zorg ervoor dat u een mogelijkheid voor een ramp/onderbreking hebt, moet u correcties aanbrengen voordat u verder gaat
- Plan de eerste groep gebruikers die u wilt inschakelen, zodat u zeker weet dat u de feedback die u nodig hebt, moet doorlopen. Dit betekent dat u, indien mogelijk, selecteert voor een actieve groep gebruikers, die op een redelijke manier feedback geeft
- Wanneer u elke golf plant, kunt u het proberen en beginnen met een kleine gebruikersbasis (minder dan 5000 gebruikers) en vervolgens de groepsgrootte verhogen terwijl u met elke golf begint. Dit helpt bij het maken van een overlopende aanpak, zodat u gemakkelijker de benodigde onderbrekings mogelijkheden kunt onderbreken.
