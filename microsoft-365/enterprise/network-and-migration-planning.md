---
title: Netwerk- en migratieplanning voor Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: Dit artikel bevat koppelingen naar informatie over netwerkplanning, testen en migratie naar Office 365.
ms.openlocfilehash: aed8bacd4dc08aa6d77ad0c530e721ac9d383bf5
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149104"
---
# <a name="network-and-migration-planning-for-office-365"></a>Netwerk- en migratieplanning voor Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Dit artikel bevat koppelingen naar informatie over netwerkplanning en -testen en migratie naar Office 365.
  
Voordat u voor het eerst implementeert of migreert naar Office 365, kunt u de informatie in deze onderwerpen gebruiken om de bandbreedte te schatten die u nodig hebt en vervolgens te testen en te controleren of u voldoende bandbreedte hebt om te implementeren of te migreren naar Office 365.

Dit artikel maakt deel uit van [netwerkplanning en prestatieafstemming voor Office 365.](./network-planning-and-performance.md)

Zie de poster [Microsoft Cloud Networking for Enterprise Architects](../solutions/cloud-architecture-models.md) voor de stappen om uw netwerk te optimaliseren voor Microsoft 365 en andere Microsoft-cloudplatforms en -services.
   
## <a name="estimate-network-bandwidth-requirements"></a>Netwerkbandbreedtevereisten schatten
<a name="EstimateBandwidthRequirements"> </a>

Het Office 365 kan het gebruik van het internetcircuit van uw organisatie vergroten. Het is belangrijk om te bepalen of de beschikbare bandbreedte voldoende is om de geschatte toename aan te kunnen nadat Office 365 volledig is geïmplementeerd, terwijl ten minste 20% capaciteit over blijft om de drukste dagen af te handelen.
  
Als u de bandbreedte wilt schatten, gebruikt u de volgende stappen:
  
1. Beoordeel het aantal clients dat elk internetgebruik zal gebruiken. Laat ons multi-terabit-netwerk zo veel mogelijk van de verbinding verwerken. 
    
2. Bepaal welke Office 365 en welke functies beschikbaar zijn voor clients. U hebt waarschijnlijk groepen personen met verschillende services of gebruiksprofielen.
    
3. Meet het netwerkgebruik voor een pilotgroep clients. Zorg ervoor dat de pilot-clients representatief zijn voor de verschillende profielen van personen in de organisatie en de verschillende geografische locaties. U kunt uw resultaten kruisen met [](https://techcommunity.microsoft.com/t5/exchange-team-blog/announcing-the-exchange-client-network-bandwidth-calculator-beta/ba-p/601744) onze oude rekenmachines voor Exchange en [Microsoft Teams](/microsoftteams/prepare-network) of de case [study](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365) die we hebben uitgevoerd in ons eigen netwerk. 
    
4. Gebruik de metingen van de testgroep om de behoeften van de hele organisatie te extrapoleren en opnieuw te testen om de schattingen te valideren voordat u wijzigingen aan uw netwerk aan gaat brengen.
    
## <a name="test-your-existing-network"></a>Uw bestaande netwerk testen
<a name="calculators"> </a>

 **Netwerkhulpmiddelen.** Test en valideer uw internetbandbreedte om de beperkingen voor downloaden, uploaden en latentie te bepalen. Met deze hulpprogramma's kunt u de mogelijkheden van uw netwerk voor migratie bepalen, evenals nadat u volledig bent geïmplementeerd. 
    
- [Microsoft Remote Connectivity Analyzer:](https://go.microsoft.com/fwlink/p/?LinkId=517243)Test connectiviteit in uw Exchange Online omgeving.
    
- Gebruik de [Microsoft-Ondersteunings- en herstelassistent voor Office 365](https://diagnostics.office.com/#/Download?env=SOC) om problemen Outlook en Office 365 oplossen. 
    
## <a name="best-practices-for-network-planning-and-improving-migration-performance-for-office-365"></a>Best practices voor netwerkplanning en het verbeteren van de migratieprestaties voor Office 365
<a name="BestPractices"> </a>

Verdiept u in deze best practices voor meer informatie over het verbeteren van uw Office 365 ervaring.
  
1. Wilt u meteen aan de slag met het helpen van uw gebruikers? Zie Best practices voor het [gebruik van Office 365](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) in een traag netwerk voor tips over het gebruik van Office 365, waaronder SharePoint Online, Exchange Online en Lync Online, wanneer uw netwerk gewoon niet samenwerkt. In dit artikel vindt u koppelingen naar tal van inhoud op TechNet en Support.office.com voor het optimaliseren van uw Office 365-ervaring en bevat informatie over eenvoudige manieren om uw webpagina's aan te passen en hoe u uw Internet Explorer-instellingen in kunt stellen voor de beste Office 365 ervaring. 
    
2. Lees [Office 365 Netwerkconnectiviteitsprincipes](./microsoft-365-network-connectivity-principles.md) om de connectiviteitsprincipes te begrijpen voor het veilig beheren van Office 365 en het verkrijgen van de best mogelijke prestaties. In dit artikel vindt u meer informatie over de meest recente richtlijnen voor het veilig optimaliseren van Office 365 netwerkconnectiviteit. 
    
3. Verbeter de prestaties van e-mailmigratie door de planning voor Windows updates. U kunt uw clientcomputers in batches bijwerken en ervoor zorgen dat alle clientcomputers worden bijgewerkt voordat u migreert naar Office 365 om het gebruik van netwerkbandbreedte te reguleren. Zie Bureaubladen handmatig bijwerken en configureren voor Office 365 voor de meest recente updates voor [meer informatie.](https://support.microsoft.com/gp/office-2013-365-update)
    
4. Office 365 netwerkverkeer het beste presteert wanneer het wordt beschouwd als een vertrouwde internetservice en veel van de traditionele filtering en scanning die sommige organisaties op netwerkverkeer plaatsen, kan omzeilen voor niet-vertrouwde internetservices. Dit omvat meestal het verwijderen van uitgaande verwerking, zoals verificatie van proxygebruikers en pakketcontrole, en het waarborgen van lokale uitstap naar internet met de juiste NAT (Network Address Translation) en voldoende bandbreedtecapaciteit om de toegenomen netwerkaanvragen af te handelen. Raadpleeg [Beheer Office 365 eindpunten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)voor aanvullende richtlijnen voor het configureren van uw netwerk om uw Office 365 te verwerken als een vertrouwde internetservice in uw netwerk.
    
1. Zorg [ervoor dat Office 365 eindpunten beheren.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) Het extra verkeer dat wordt Office 365 resulteert in een toename van uitgaande proxyverbindingen en een toename van veilig verkeer via TLS/SSL.
    
2. Als uw uitgaande proxies gebruikersverificatie vereisen, kan er een trage verbinding of een verlies van functionaliteit zijn. Als u de verificatievereiste voor Office 365 domeinen overbrugt, kan deze overhead worden beperkt.
    
3. Als u een groot aantal gedeelde agenda's en postvakken hebt, ziet u mogelijk een toename van het aantal verbindingen van Outlook naar Exchange. De Outlook kan bijvoorbeeld twee extra verbindingen openen voor elke gedeelde agenda die wordt gebruikt. In dit geval moet u ervoor zorgen dat de uitgangsproxy de verbindingen kan verwerken of de proxy voor verbindingen met Office 365 voor Outlook.
    
4. Bepaal het maximum aantal ondersteunde apparaten voor een openbaar IP-adres en hoe u de balans tussen meerdere IP-adressen kunt laden. Zie NAT-ondersteuning [met Office 365.](nat-support-with-microsoft-365.md)
    
5. Als u uitgaande verbindingen van computers in uw netwerk controleert, worden de connectiviteit en prestaties verbeterd door deze filtering te omzeilen Office 365 domeinen. Als u uitgaande controles overbrugt, hoeft u vaak niet meer één internetverwijdering te gebruiken en kan lokaal internet uitgaan voor Office 365 netwerkaanvragen.
    
6. Sommige klanten vinden dat interne netwerkinstellingen van invloed kunnen zijn op de prestaties. Instellingen zoals maximale overdrachtseenheid (MTU), automatische netwerkonderhandeling of automatische detectie en sub-optimale routes naar internet zijn veelvoorkomende locaties om te zoeken.
    
## <a name="network-planning-reference-for-office-365"></a>Verwijzing naar netwerkplanning voor Office 365
<a name="NetReference"> </a>

Deze onderwerpen bevatten gedetailleerde Office 365 informatie over netwerkverwijzingen.
  
- [Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
    
- [Netwerken voor contentlevering](content-delivery-networks.md)
    
- [Externe DNS-records (Domain Name System) voor Office 365](external-domain-name-system-records.md)
    
- [IPv6-ondersteuning in Office 365-services](ipv6-support.md)
    
- [Beginselen voor Office 365-netwerkverbinding](./microsoft-365-network-connectivity-principles.md)
    
- [Netwerkapparaten plannen die verbinding maken met Office 365 services](plan-for-network-devices.md)
    
- [Installatiehulplijnen voor Office 365 services](setup-guides-for-microsoft-365.md)
 
## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise overzicht](microsoft-365-overview.md)