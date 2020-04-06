---
title: Beheermitigaties voor bedrijfscontinuïteit van Microsoft 365 Enterprise
author: chrfox
f1.keywords:
- NOCSH
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Enkele voorbeelden van mitigaties voor incident-scenario's van de Microsoft 365-service.
ms.openlocfilehash: ea9804d4f22a11ea9ffcda9d9939d70574c2e87e
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812437"
---
# <a name="service-incident-mitigation-strategies"></a>Strategieën voor het beperken van service-incidenten

Hier vindt u enkele strategieën en scenario's die uitleggen hoe u de gevolgen van een service-incident in Microsoft 365 kunt beperken voor uw bedrijfsproces.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>Scenario's en mogelijke mitigaties voor service-incidenten

|Afhankelijkheid Microsoft 365|mogelijke mitigaties|
|---------|---------|
|Incidentenbeheer is afhankelijk van Exchange Online voor het inschakelen van technici en incidentmanagers.|Zorg ervoor dat uw systeem voor incidentenbeheer meerkanaalse communicatie ondersteunt, zoals parallelle e-mail, telefonische gesprekken, SMS-meldingen en gesprekshiërarchieën, zodat het systeem in het geval dat de primaire medewerker on-call niet beschikbaar is, direct contact opneemt met de back-up. Neem ook alternatieve contactmethoden op in elke melding, zodat iedereen gemakkelijk kan zien wat de alternatieve communicatiemethoden zijn. Alternatieve communicatiemethoden, zoals Yammer, kunnen worden gebruikt voor samenwerking in noodgevallen wanneer de incidentbeheerservice niet beschikbaar is.|
|Microsoft Teams wordt gebruikt voor het opslaan van bestanden die worden geopend via de client.|Teams slaat bestanden die naar de client zijn geüpload op in een documentbibliotheek van SharePoint Online. Bestanden zijn nog steeds toegankelijk via SharePoint Online. Leid gebruikers op over bestandslocaties in SharePoint Online.|
|Telefonische vergaderingen via Microsoft Teams worden gebruikt voor algemene communicatie en het beoordelen van incidenten.|Regel een alternatieve oplossing vergaderingen met een externe provider.|
|VoIP-telefoons worden gebruikt als secundaire communicatiemethode.|Implementeer niet-VoIP-telefoons die geschikt zijn voor bellen via PSTN, met name voor het operationele centrum voor het netwerk en de service tijdens incidenten. Zet mobiele telefoonnummers van werknemers in de adreslijst van het bedrijfs, zodat cruciale medewerkers via het mobiele netwerk bereikt kunnen worden.|
|OneDrive voor Bedrijven wordt gebruikt voor het opslaan van bestanden en gebruikersproductiviteit. [Files On-Demand](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234) wordt geconfigureerd om ruimte vrij te maken op lokale gebruikersstations.|Met OneDrive-synchronisatie kunt u groepsbeleid maken dat beheerders de mogelijkheid geeft het lokaal synchroniseren van specifieke inhoud of het vrijmaken van ruimte te verplichten. Als u het risico op ontoegankelijkheid van documenten wilt beperken, configureert u dit beleid voor het lokaal synchroniseren van kritieke documenten. Leid gebruikers op voor het handmatig toepassen van de instelling “altijd bewaren op dit apparaat” voor belangrijke documenten.|
|De communicatie van zakelijke storingen naar klanten en leveranciers is afhankelijk van Exchange Online.|Openbare sociale netwerken van derden kunnen worden gebruikt als een alternatief middel voor massacommunicatie.

## <a name="leveraging-mobile-app-access"></a>Gebruikmaken van toegang tot mobiele apps

Omdat het gebruik van mobiele telefoons toeneemt, zijn er nieuwe middelen om verbonden te blijven en kunnen mobiele toepassingen voor Microsoft 365 een belangrijk onderdeel van uw tolerantiestrategie worden. Aangezien ze via het netwerk van de mobiele provider verbonden zijn met cloudservices, zijn ze niet afhankelijk van de netwerkinfrastructuur van uw organisatie.

Laten we Outlook als voorbeeld gebruiken. Gebruikers kunnen via verschillende netwerkprotocollen (https of MAPI) verbinding maken met hun Exchange Online-postvakken, afhankelijk van de gebruikte e-mail-app. Als er sprake is van een service-incident met betrekking tot één van de protocollen, zoals bijvoorbeeld MAPI dat door de desktop-client wordt gebruikt, hebben uw gebruikers nog steeds toegang tot hun postvak via de Outlook Mobile-app of Outlook on the Web.
  
Als u besluit gebruikers toestemming te geven om via hun mobiele apparaten verbinding te maken met Microsoft 365-services, kunt u Microsoft Intune gebruiken om die apparaten veilig te configureren en beheren. Zodra de gebruikersaccounts en apparaten zijn geregistreerd in de mobiele beheeroplossing, moet u ervoor zorgen dat de apps zijn gedownload en geconfigureerd.
