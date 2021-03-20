---
title: Het plannen van een implementatieplan voor het starten van uw portal in SharePoint Online
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
description: In dit artikel wordt beschreven hoe u de lancering van uw portal kunt plannen in SharePoint Online en welke stappen u moet ondernemen voor een geslaagde start
ms.openlocfilehash: d77baac6209a4002bb1c27513d5ccfdf5c4ac28a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905690"
---
# <a name="planning-your-portal-launch-roll-out-plan-in-sharepoint-online"></a>Het plannen van een implementatieplan voor het starten van uw portal in SharePoint Online

Een portal is een SharePoint-site op uw intranet met een groot aantal sitekijkers die inhoud op de site gebruiken. In grote organisaties kunnen er verschillende van deze zijn; bijvoorbeeld een bedrijfsportal en een HR-portal. Portals hebben meestal relatief weinig personen die de site en de inhoud ervan maken en maken. De meeste bezoekers van de portal lezen en gebruiken alleen de inhoud.

In dit artikel wordt beschreven hoe u uw implementatie- en implementatieplan kunt plannen voor SharePoint Online. Het biedt ook benaderingen om te volgen, omdat traditionele belastingstests niet zijn toegestaan in SharePoint Online. SharePoint Online is een cloudservice en de laadmogelijkheden, de status en de totale belastingsbalans in de service worden beheerd door Microsoft.

Als u wilt helpen bij het maken van een succesvolle portal, volgt u de basisprincipes, procedures en aanbevelingen die worden beschreven in het [maken,](/sharepoint/portal-health) starten en onderhouden van een gezonde portal 

De implementatiebenadering is hieronder gemarkeerd.

## <a name="overview-of-capacity-planning-in-sharepoint-online"></a>Overzicht van capaciteitsplanning in SharePoint Online
Om de capaciteit efficiënt te kunnen gebruiken en onverwachte groei aan te kunnen, hebben we in elke farm automatisering die bepaalde gebruiksscenario's bij houdt. Hoewel de exacte groei onvoorspelbaar is voor elke tenant in een farm, is de samengevoegde som van aanvragen voorspelbaar in de tijd. Door de groeitrends in SharePoint Online te identificeren, kunnen we toekomstige uitbreiding plannen. Voor meer informatie over [capaciteitsplanning en laadtests van SharePoint Online.](capacity-planning-and-load-testing-sharepoint-online.md)

Een belangrijk onderdeel van een geslaagde lancering is de 'wave' of 'phased roll-out' benadering die hieronder wordt beschreven. 

## <a name="can-i-load-test-sharepoint-online"></a>Kan ik test SharePoint Online laden?
SharePoint Online is een gedeelde omgeving met meerdere tenants die is gebalanceerd tussen farms en de schaal wordt regelmatig aangepast. Het laden van het testen van een omgeving, zoals SharePoint Online, waarvan de schaal continu wordt gewijzigd, levert niet alleen onverwachte resultaten op, maar is niet toegestaan. 

Meer informatie:  [Capaciteitsplanning en laden testen SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)

## <a name="optimize-pages-by-following-recommended-guidelines"></a>Pagina's optimaliseren op basis van aanbevolen richtlijnen
Pagina's van een on-Premises implementatie moeten niet worden verplaatst naar SharePoint Online zonder ze te controleren op basis van aanbevolen richtlijnen voor SharePoint Online. De beste methode is om elke startpagina altijd te optimaliseren voor een site of portal in SharePoint, omdat dit de plaats is waar de meeste gebruikers in uw organisatie toegang krijgen als uitgangspunt voor uw site(en).

Er moet rekening worden gehouden met enkele basisfactoren:
- On-Premises implementaties kunnen gebruikmaken van traditionele caches aan de serverzijde, zoals objectcache, uitvoercache en blobcache. Met de verschillen in de topologie in de cloud zijn deze opties niet per se beschikbaar, omdat ze door de grote schaalverschillen minder haalbaar zijn.
- Pagina's/functies/aanpassingen die worden gebruikt voor cloudverbruik, moeten worden geoptimaliseerd voor hogere latentie en de gedistribueerde locaties van gebruikers, zodat gebruikers in verschillende gebieden of regio's een consistentere ervaring hebben. Cloud biedt optimalisaties, zoals CdN (Content Delivery Networks) om te optimaliseren voor een gedistribueerde gebruikersbasis en voor modern SharePoint, het laatst bekende goede (LKG) wordt gebruikt door onze out-of-the-box (OOTB) webonderdelen.

### <a name="what-to-do"></a>Wat moet u doen:
 - Voor alle sitepagina's in [](./page-diagnostics-for-spo.md)SharePoint Online gebruikt u het hulpprogramma Paginadiagnose, een Chromium-extensie die helpt bij het analyseren en verstrekken van richtlijnen. Dit kan worden gebruikt door site-eigenaren, editors, beheerders en ontwikkelaars, omdat het is ontworpen om een beginpunt te zijn voor analyse en optimalisatie.
 - Ontwikkelaars moeten ook ontwikkelhulpprogramma's zoals F12-browserontwikkelaars en Ctrl-F12 gebruiken in de browser op moderne pagina's. [Fiddler](https://www.telerik.com/download/fiddler) kan ook worden gebruikt om het formaat van de pagina te controleren (hoe groot de pagina is in megabytes) van de pagina en het aantal oproepen en elementen dat van invloed is op de totale paginabelasting. 

Deze sectie was een korte samenvatting voor het optimaliseren van pagina's.  Zie Een gezonde portal  [maken, starten](/sharepoint/portal-health)en onderhouden voor meer informatie.

## <a name="follow-a-wave--phased-roll-out-approach"></a>Een wave/gefaseerd implementatie-aanpak volgen
Met de traditionele big bang-methode voor sitelanceringen kan niet worden geverifieerd dat aanpassingen, externe bronnen, services of processen op de juiste schaal zijn getest. Dit betekent niet dat het maanden duurt om te starten, maar het wordt aanbevolen gedurende ten minste enkele dagen, afhankelijk van de grootte van uw organisatie. Het volgen van een wave roll-outplan biedt u daarom de mogelijkheid om problemen te onderbreken en op te lossen voordat u verdergaat met de volgende fase, zodat het potentiële aantal gebruikers dat door eventuele problemen wordt beïnvloed, wordt verlaagd. In SharePoint as a service wordt uw capaciteit geschaald op basis van gebruik en voorspeld gebruik en hoewel u ons niet op de hoogte hoeft te stellen van de lancering, moet u de richtlijnen volgen om succes te garanderen.
  
Zoals wordt weergegeven in de volgende afbeelding, is het aantal gebruikers dat wordt uitgenodigd vaak aanzienlijk hoger dan het aantal gebruikers dat de site daadwerkelijk gebruikt. In deze afbeelding ziet u een strategie voor het uitrollen van een release. Met deze methode kunt u manieren identificeren om de SharePoint-site te verbeteren voordat de meerderheid van de gebruikers deze ziet.
  
![Grafiek met uitgenodigde en actieve gebruikers](../media/0bc14a20-9420-4986-b9b9-fbcd2c6e0fb9.png)
  
In de testfase is het goed om feedback te krijgen van gebruikers die de organisatie vertrouwt en weet dat ze betrokken zijn. Op deze manier kunt u meten hoe het systeem wordt gebruikt en hoe het werkt.
  
Verzamel tijdens elk van de golven feedback van gebruikers over de functies en de prestaties tijdens elke implementatiegolf. Dit heeft het voordeel dat het systeem langzaam wordt doorgevoerd en verbeteringen worden aangebracht naarmate het systeem meer wordt gebruikt. Hierdoor kunnen we ook reageren op de toegenomen belasting wanneer de site wordt uitgerold naar meer en meer gebruikers en gecombineerd met het volgen van de richtlijnen voor pagina-optimalisatie zorgt voor een positieve ervaring voor uw gebruikers.

### <a name="what-to-do"></a>Wat moet u doen:
- Bepaal de timing van elke fase en zorg ervoor dat u een kans voor onvoorziene/pauze hebt, mocht u wijzigingen moeten aanbrengen voordat u doorgaat
- Plan uw eerste groep gebruikers die u wilt inschakelen, om ervoor te zorgen dat u de feedback ontvangt die u nodig hebt om verder te gaan. Dit betekent dat u waar mogelijk een actieve groep gebruikers selecteert die tijdig feedback geeft
- Terwijl u elke golf plant, probeert u te beginnen met een kleine gebruikersbasis (minder dan 5000 gebruikers) en vergroot u vervolgens de groepsgrootte terwijl u verdergaat met elke golf. Dit helpt bij het maken van een gespreide aanpak en maakt gemakkelijkere pauzemogelijkheden mogelijk.