---
title: SharePoint 2007-migratieopties om rekening mee te houden
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Dit artikel bevat informatie voor gebruikers die SharePoint Server 2007 gebruiken om hen te helpen bij het plannen van hun upgrade.
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924878"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>SharePoint 2007-migratieopties om rekening mee te houden

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft SharePoint 2007 en SharePoint Server 2007 hebben het einde van de ondersteuning bereikt. Het is tijd om een upgrade uit te voeren. In dit artikel vindt u informatie over uw migratieopties.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Algemene upgradestrategieën voor SharePoint

Er zijn meerdere methoden voor het upgraden van een SharePoint Server-omgeving. Als u een Microsoft Office SharePoint Server 2007-farm hebt, zijn hier enkele voorbeelden van de upgrademethoden:
  
- Database-bijlage
    
- Side-by-side upgrade
    
- In-place upgrade
    
- Hybride upgrade (in-place met losgemaakte databases / aparte database attach)
    
- SharePoint hybriden (online verbinding maken met on-premises SharePoint)
    
- Gegevens handmatig verplaatsen tussen siteverzamelingen of bibliotheken
    
- FastTrack Wizard upgrade naar Microsoft 365 ([SharePoint Online implementatieadviseur](https://aka.ms/spoguidance))
    
- Migratie-API naar SharePoint Online (SPO) in Microsoft 365
    
Wat werkt het beste voor u?
  
Uw kennis van wat uw farm doet en waarvoor u wordt gebruikt, is een tactische kracht als het gaat om upgraden. De manier waarop personen de SharePoint-farm gebruiken, helpt u bij het kiezen van uw opties.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 heeft ook een geleidelijke upgrade die hier niet wordt behandeld. Zie de [sharepoint server 2007 end of support Roadmap](sharepoint-2007-end-of-support.md)voor een lijst met stapsgewijse upgrade-artikelen. 
  
Controleer de [productlevenscyclus](https://support.microsoft.com/lifecycle/search) en systeemvereisten voor de versie van SharePoint waar u een upgrade naar wilt uitvoeren. U weet dus wanneer de volgende upgrade nodig is (bijvoorbeeld als u bij een oud product, zoals SharePoint Server 2010, pauzeert om meer upgrades te plannen, zorg ervoor dat u het einde van de ondersteuningsdatum weet) en dat u zeker weet dat u hardware hebt die uw abonnement ondersteunt. 
  
Als u van plan bent om bepaalde of alle SharePoint-sites over te brengen naar Microsoft 365 in de cloud, is dit een tijd om een bladwijzer te maken voor een koppeling naar de servicebeschrijvingen van [Microsoft 365 en Office 365.](/office365/servicedescriptions/office-365-service-descriptions-technet-library) U hebt de servicebeschrijvingen nodig om meer te weten te komen over SharePoint Online-functies en hoe deze kunnen verschillen van on-premises SharePoint Server. Upgrade functionele Microsoft Office SharePoint Server 2007-farms. Als uw installatie sites heeft die zijn verbroken, kunt u deze herstellen vóór de upgrade.
  
## <a name="a-note-about-managing-risk"></a>Een opmerking over het beheren van risico's

Methoden zoals 'side-by-side' zijn belangrijk in het schema van upgradelogica. Wanneer u een upgrade naast elkaar hebt uitgevoerd, onderhoudt u uw Microsoft Office SharePoint Server 2007-farm, maar bouwt u een farm met de volgende versie (SharePoint Server 2010) op nieuwe hardware. Dit helpt op drie manieren:
  
1. U kunt back-ups van uw Microsoft Office SharePoint Server 2007-databases maken om ze afzonderlijk te upgraden, met behulp van database attach.
    
2. Als u erachter komt dat er slechts een klein aantal kritieke documentbibliotheken en andere informatie wordt gebruikt op uw Microsoft Office SharePoint Server 2007-farm, kunt u ervoor kiezen om gegevens handmatig te verplaatsen van Microsoft Office SharePoint Server 2007 naar SharePoint Server 2010, of alleen specifieke sites en webs naar de volgende versie te verplaatsen (wat uw taak gemakkelijker kan maken).
    
3. Hoe minder u doet met de Microsoft Office SharePoint Server 2007-serverfarm, hoe veiliger de gegevens die farm bevat tijdens de upgrade.
    
Methoden zoals In-Place upgrade werken rechtstreeks op uw Microsoft Office SharePoint Server 2007-farm, waardoor u minder eenvoudige opties hebt om een pad te verlaten en opnieuw te beginnen met uw ongerepte omgeving. Bouw zoveel mogelijk enkele veiligheidsmaatregelen in (zoals het maken en testen van back-ups van de oorspronkelijke omgeving). Als uw Microsoft Office SharePoint Server 2007-farm bijvoorbeeld virtueel is en wordt gedupliceerd voor het maken van een back-up en herstel, maakt u een back-up en herstelt u de meest recente databases vóór het servicevenster voor de upgrade. Als u weet dat u de optie hebt om databaseback-ups te herstellen, hebt u niet alleen een failsafe, maar kunt u ook gerust zijn.
  
> [!TIP]
> Best practices documents for upgrade exist for [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)), [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013), and [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade). U kunt ook zoeken naar [Microsoft-partners](https://partnercenter.microsoft.com/pcv/search) die ervaring hebben met upgrades of Microsoft 365-migraties. 
  
## <a name="make-your-plan"></a>Uw plan maken

Als u een upgrade wilt uitvoeren, hebt u een abonnement nodig en in deze gevallen past één formaat niet allemaal. Uw abonnement kan net zo eenvoudig zijn als 'Een Microsoft 365-abonnement maken met SharePoint Online, een domein registreren en personen omleiden om hun bestanden daar op te slaan'. En dat is het misschien niet. Die beslissing is aan u en het ligt aan wat u en uw gebruikers echt nodig hebben.
  
> [!NOTE]
> Het is riskant om te werken met software waarvan de levenscyclus is beëindigd. Producten die geen ondersteuning meer hebben, worden niet meer gepatcht wanneer er problemen worden gevonden. Dit betekent ook dat als er nieuwe beveiligingsrisico's optreden, er geen beveiligingspatches of fixes zijn omdat de producten aan het einde van de levenscyclus niet meer worden ondersteund. Vermijd deze situatie! 
  
### <a name="first-know-your-farm"></a>Ken eerst uw farm

Bij het upgraden moet uw besluitvorming zijn gebaseerd op wat uw farm voor uw organisatie doet. Aan welke behoefte voldoet het? Wat is de rol? Elke farm in uw bedrijf kan een andere rol hebben. Sommige SharePoint-farms zijn mogelijk  *kritiek,*  sommige zijn bestandsarchieven, zodat ze veilig kunnen worden behouden. Of als uw farm veel rollen tegelijk vult, moet u mogelijk weten wat siteverzamelingen, webs of zelfs documentbibliotheken doen, eventuele aanpassingen en hoe belangrijk ze zijn. Het analyseren van uw gegevens op dit niveau lijkt misschien veel werk, maar het bespaart tijd en moeite om uw domein onder de knie te krijgen voordat u een upgrade uitwerkt of migreert. Zodra u alle bewegende onderdelen en de belangrijkste bits kent, weet u ook wat u hebt ontgroeid en kunt u achterblijven. Die kennis is alleen maar goed voor de toekomst. 
  
Dus wat zeggen gebruikers dat het belangrijkst is voor uw SharePoint Server-farm?
  
- Ingebouwde SharePoint-functies
    
- Het grote gegevensarchief (zoals een archief met bestanden)
    
- Beschikbaarheid
    
- Kritieke apps, webonderdelen of documenten in de farm (mission critical farm)
    
- Aan de nalevingsstandaarden is voldaan
    
- Aanpassingen
    
Als u vanuit uw SharePoint-farm iets essentieels voor uw bedrijf runt, zegt u dat het werkt als een grote catalogus met kritieke gegevens over vereisten voor clientservice, kunt u een vinkje zetten naast 'Kritieke apps', maar ook 'Beschikbaarheid', dat wil zeggen dat uw bedrijf gevolgen zou hebben als u SharePoint een tijdje niet kon gebruiken. U kunt ook 'Aanpassingen' controleren omdat de kritieke services die uw farm aanbiedt, zijn gebaseerd op aangepaste code, sitedefinities of een aantal aanpassingen die samenwerken.
  
Als SharePoint aan deze behoeften heeft voldaan zonder dat u iets hoeft te doen buiten het gebruik van de ingebouwde software en u deze over het algemeen bijwerkt en normaal beheer en onderhoud voert, hebt u mogelijk 'Ingebouwde SharePoint' gekozen. Dit kan ook uw reden zijn om in een oudere versie van SharePoint te zitten. Met andere woorden, het doet al wat u nodig hebt en u hoeft tot nu toe niet te upgraden bij Het einde van de ondersteuning van Microsoft Office SharePoint Server 2007.
  
Wanneer u deze dingen op een opsommingstekenlijst hebt geplaatst, maakt u criteria voor uw upgrade. Met andere woorden, elke upgrade moet voldoen aan deze balk om in aanmerking te komen. Op deze manier kunt u methoden uitsluiten die momenteel niet aan uw behoeften voldoen.
  
### <a name="a-simple-sample-plan"></a>Een eenvoudig voorbeeldplan

Mogelijk moet er bredere consensus zijn met het leiderschap en andere beheerders op het pad dat uw SharePoint-upgrade zal volgen. SharePoint Server-beheerders werken vaak samen met Microsoft SQL Server-beheerders, werken met netwerk- en beveiligingsteams en meer. Als er veel belanghebbenden zijn, moet u mogelijk een overeenkomst maken voor of aanpassen aan uw upgrade- en migratieplan. Als u bijvoorbeeld gegevens migreert zodat een deel van uw bedrijf SharePoint Online gebruikt in Microsoft 365, moet de prestaties waarschijnlijk worden afgestemd of getest in uw netwerk. Betrokken teams moeten van tevoren worden geïnformeerd.
  
In mijn eenvoudige voorbeeld laat ik het voorstel van een SharePoint-beheerder zien en vermeld ik vervolgens het plan dat alle belanghebbenden hebben afgesproken. Document uw overeenkomsten en beslissingen voor de duidelijkheid.
  
Het plan begint na een uitgebreide analyse van een farm en probeert de rol van de farm, pijnpunten en andere belangrijke informatie te identificeren die ertoe leidt dat sommige upgradeopties worden verkleind. Daarna wordt een upgradevoorstel gedaan door de SharePoint-beheerder en zijn belanghebbenden het eens over een actieplan.
  
Mijn 'belangrijkste' lijst met opsommingstekens:
  
- Beschikbaarheid, functies die zijn ingebouwd in SharePoint en compliancestandaarden.
    
- De meeste gegevens bevinden zich in drie siteverzamelingen, met één vergaderwerkruimte die door een Dev-team wordt gebruikt, met name belangrijk en in zwaar gebruik in meerdere tijdzones wereldwijd.
    
- Er zijn nog zeventien andere sites die veel worden gebruikt.
    
- Twee documentbibliotheken (Vergaderwerkruimte en Documenten in de hoofdsiteverzameling) zijn het grootst (elk meer dan 8000 documenten). We hebben een groot aantal gearchiveerde documenten en lijst met spreadsheetbijlagen.
    
- Er zijn veertien lijsten met bibliotheken met gevoelige gegevens die moeten worden nageleefd.
    
- We MOETEN de mogelijkheid hebben om te houden en e-discovery te doen, waar we ook naartoe gaan.
    
- Sommige van deze gegevens moeten on-premises blijven vanwege InfoSec-regels.
    
 **Mijn upgrade- en migratieopties:**
  
| Ja | Nee |
|:-----|:-----|
|Databases upgraden met database als bijlage  <br/> |In-place upgrade  <br/> |
|Upgraden met farms naast elkaar  <br/> |Hybride upgrade  <br/> |
|Migratie-API naar SPO in Microsoft 365 (voor persoonlijke sitegegevens)  <br/> |SharePoint Hybrid (nog niet nodig)  <br/> |
|Enkele handmatige gegevensmigraties naar SharePoint Online voor kritieke gegevens  <br/> |FastTrack wizard upgrade naar Microsoft 365  <br/> |
   
 **Mijn voorgestelde plan:**
  
Upgrade on-premises, met versies van SharePoint naast elkaar, sommige gevirtualiseerd, zodat we de databases eerst kunnen upgraden. Ga van SharePoint 2007 naar SharePoint 2010. Beheerders en ontwikkelaars testen de resulterende farm. Gebruikers testen de resulterende farm. Los eventuele problemen met het stoppen van de show in deze periode op. Opnieuw upgradet u SharePoint 2010-databases naast elkaar naar SharePoint 2013. Test. Gebruikerstest/pilot. Los eventuele problemen met het stoppen van de show in deze periode op.
  
- Overweeg of een federatief hybride zoeken met SPO aan uw behoeften voldoet.
    
- Overweeg [FastTrack-hulp](https://fasttrack.microsoft.com) als u vanaf hier een upgrade wilt uitvoeren naar SharePoint Online. 
    
- Bepaal of siteverzamelingen kunnen worden geladen naar een Microsoft 365-abonnement. (Microsoft 365 voldoet aan veel [compliancestandaarden.](/compliance/regulatory/offering-home) Microsoft 365 heeft [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) en kan [het](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) compliancecentrum gebruiken.) 
    
Ga anders door met een side-by-side upgrade naar SharePoint Server 2016.
  
> [!NOTE]
> Tussen de aanbevelingen van de beheerders die de upgrade plannen en het werkelijke proces zijn de gesprekken die plaatsvinden met andere belanghebbenden waarop de upgrade is gebaseerd. Soms worden beheerders bijvoorbeeld gedwongen hun plannen te wijzigen. Wat de uiteindelijke beslissing ook is, u moet in de toekomst documenteren wat het overeengekomen plan is. Het ziet er mogelijk zo uit: 
  
 **Mijn actieplan:**
  
On-premises gebruiken we een virtuele omgeving om standaard SharePoint Server 2010 en 2013 te maken. SharePoint Server 2016 wordt gebouwd op nieuwe hardware die voldoet aan de systeemvereisten voor 2016. We doen database-attaches voor het upgraden van databases vanuit SharePoint 2007 via alle versies ertussen en SharePoint Server 2016. Kernaanpassingen worden op dit moment opnieuw gemaakt en getest in de SharePoint Server 2016-omgeving, als native functies nog niet aan onze behoeften voldoen. Als dit lukt, hebben we een on-premises farm met nieuwe hardware met bijgewerkte databases en minder aanpassingen. We voegen de bijgewerkte inhoudsdatabases toe aan nieuwe siteverzamelingen in SharePoint Server 2013, testen, gebruikerstest/pilot en doen vervolgens een DNS-cut-over aan de nieuwe SharePoint Server 2016-omgeving voor live gebruik.
  
- Federated Hybrid tussen SharePoint Server 2016 en SharePoint Online wordt momenteel niet als federatief hybride gezien.
    
- Naar schatting kan 35% van onze sites worden omgezet in nieuwe SPO-sites met vanity-domeinen, of uiteindelijk OneDrive voor Bedrijven-opslag worden. Op zoek naar andere mogelijkheden voor het converteren van sites of het doorverplaatsen van nieuwe sites naar SPO.
    
- Een deel van dit deel van de migratie is handmatig, door te slepen naar persoonlijke sites van OneDrive voor Bedrijven en andere via de migratie-API.
    
Meer gedetailleerde stappen of een aantal koppelingen naar specifieke upgradebeschrijvingen moeten een plan volgen. De MOSS 2007-computer mag niet worden buiten gebruik gesteld en virtuele omgevingen moeten ter vergelijking worden onderhouden. De upgrade is echter voltooid wanneer gebruikers worden omgeleid naar SharePoint Server 2016.
  
Vaak belangrijke factoren bij het kiezen van een methode zijn de totale kosten van de upgrade en de kosten in de tijd (u ziet hier meer informatie over in het artikel SharePoint Migration Roadmap). Maar vooruit plannen zal u veel voordeel doen bij het stellen van verwachtingen, het verstandig kiezen en het inlijsten van succes.
  
## <a name="related-links"></a>Verwante koppelingen

[Resources om u te helpen bij het upgraden van Office 2007-servers en -clients](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Lifecycle Policy and Lifecycle search](https://support.microsoft.com/lifecycle)
  
[Microsoft-partners zoeken die u kunnen helpen met upgraden of migratie](https://partnercenter.microsoft.com/pcv/search)
