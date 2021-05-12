---
title: Zoeken naar inhoud
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.assetid: df2d1e0f-b476-42c9-aade-4a260b24f193
description: Gebruik het hulpprogramma Inhoud zoeken eDiscovery in het beveiligings- & compliancecentrum om snel e-mail te vinden in Exchange-postvakken, documenten op SharePoint-sites en OneDrive-locaties en chatgesprekken in Skype voor Bedrijven.
ms.openlocfilehash: 80234a512d13deda29a61073bec62990d135f30e
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333684"
---
# <a name="search-for-content-using-the-content-search-tool"></a>Zoeken naar inhoud met behulp van het hulpprogramma Inhoud zoeken

Gebruik het hulpprogramma Inhoud zoeken in het Beveiligings- & Compliancecentrum om snel e-mail te vinden in Exchange-postvakken, documenten op SharePoint-sites en OneDrive-locaties en chatgesprekken in Skype voor Bedrijven. U kunt het zoekprogramma voor inhoud gebruiken om te zoeken naar e-mail, documenten en chatgesprekken in samenwerkingshulpmiddelen zoals Microsoft Teams en Microsoft 365 Groepen.
  
## <a name="search-for-content"></a>Zoeken naar inhoud

De eerste stap is het gebruik van het hulpprogramma Inhoud zoeken om inhoudslocaties te kiezen om een trefwoordquery te zoeken en te configureren om te zoeken naar specifieke items. U kunt de query ook leeg laten en alle items op de doellocaties retourneren.
  
- [Een inhoudszoekactie](content-search.md) maken en uitvoeren

- [Functieverwijzing] voor zoeken naar inhoud (content-search-reference.md)

- [Zoekquery's maken en voorwaarden gebruiken om](keyword-queries-and-search-conditions.md) uw zoekopdracht te beperken 

- [Zoekmachtigingen filteren zo](permissions-filtering-for-content-search.md) configureren dat een eDiscovery-manager alleen kan zoeken in subset van postvakken of sites in uw organisatie 

- [Een id-lijst zoeken uitvoeren om](csv-file-for-an-id-list-content-search.md) te zoeken naar specifieke e-mailberichten 

- [Zoeken in postvakken in de cloud voor ](search-cloud-based-mailboxes-for-on-premises-users.md) on-premises gebruikers in Microsoft 365

- [Trefwoordstatistieken](view-keyword-statistics-for-content-search.md) weergeven voor de resultaten van een zoekopdracht en de query zo nodig verfijnen

- [Zoeken naar gegevens van derden die](use-content-search-to-search-third-party-data-that-was-imported.md) uw organisatie heeft geïmporteerd in Microsoft 365

- [De query-](bulk-edit-content-searches.md) en inhoudslocaties bulksgewijs bewerken voor meerdere zoekopdrachten

- [Een inhoudszoekactie opnieuw proberen om](retry-failed-content-search.md) een inhoudslocatiefout op te lossen

- [BCC-geadresseerden behouden,](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) zodat u ze kunt zoeken 

## <a name="perform-actions-on-content-you-find"></a>Acties uitvoeren op inhoud die u vindt

Nadat u een zoekopdracht hebt uitgevoerd en deze zo nodig hebt verfijnd, is de volgende stap om iets te doen met de resultaten die door de zoekopdracht worden geretourneerd. U kunt de resultaten exporteren en downloaden naar uw lokale computer of in het geval van een e-mail aanval op uw organisatie, kunt u de resultaten van een zoekopdracht verwijderen uit postvakken van gebruikers.
  
- [De resultaten van een inhoudszoekactie exporteren](export-search-results.md) en deze downloaden naar uw lokale computer 

- [E-mailberichten](search-for-and-delete-messages-in-your-organization.md) zoeken en verwijderen, zoals berichten met een virus, gevaarlijke bijlagen of phishingberichten

- [Een rapport exporteren over](export-a-content-search-report.md) de resultaten van een inhoudszoekactie, zonder de werkelijke resultaten te exporteren 

## <a name="learn-more-about-content-search"></a>Meer informatie over zoeken naar inhoud

Inhoud zoeken is eenvoudig te gebruiken, maar het is ook een krachtig hulpmiddel. Achter de schermen is er veel aan de hand. Hoe meer u ervan weet en hoe meer u weet over het gedrag en de beperkingen ervan, hoe succesvoller u deze gebruikt voor de zoek- en onderzoeksbehoeften van uw organisatie. Meer informatie over:
  
- [Gedeeltelijk geïndexeerde items in Exchange en SharePoint](partially-indexed-items-in-content-search.md) en hoe u deze kunt opnemen of uitsluiten wanneer u zoekresultaten exporteert en downloadt

- [Gedeeltelijk geïndexeerde items onderzoeken](investigating-partially-indexed-items-in-ediscovery.md) en de blootstelling van uw organisatie aan items bepalen

- [Limieten van het hulpprogramma Inhoud](limits-for-content-search.md)zoeken, zoals het maximum aantal zoekopdrachten dat u tegelijk kunt uitvoeren en het maximum aantal inhoudslocaties dat u in één zoekopdracht kunt opnemen

- [Geschatte en werkelijke zoekresultaten](differences-between-estimated-and-actual-ediscovery-search-results.md) en de redenen waarom er verschillen tussen de zoekresultaten kunnen zijn wanneer u zoekresultaten exporteert en downloadt

- [Dubbele gegevens in zoekresultaten verwijderen die u kunt](de-duplication-in-ediscovery-search-results.md) inschakelen wanneer u e-mailberichten exporteert die de resultaten van een zoekopdracht zijn

## <a name="use-scripts-for-advanced-scenarios"></a>Scripts gebruiken voor geavanceerde scenario's

Soms moet u geavanceerdere, complexere en terugkerende zoektaken voor inhoud uitvoeren. In deze gevallen is het eenvoudiger en snel om PowerShell-opdrachten te gebruiken in het Beveiligings- & Compliancecentrum. Om dit gemakkelijker te maken, hebben we een aantal PowerShell-scripts & Beveiligingscentrum gemaakt om complexe zoektaken voor inhoud te voltooien.
  
- [Specifieke postvak- en sitemappen](use-content-search-for-targeted-collections.md) doorzoeken (een *targeted-verzameling genoemd) wanneer u zeker weet dat items die reageren op een zaak zich in die map bevinden

- [Zoeken in het postvak en de OneDrive-locatie](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md) voor een lijst met gebruikers 

- [Meerdere zoekopdrachten maken,](create-report-on-and-delete-multiple-content-searches.md) rapporteren en verwijderen om snel en efficiënt zoekgegevens te identificeren en te verwijderen 

- [Kloon een inhoudszoekactie](clone-a-content-search.md) en vergelijk snel de resultaten van verschillende trefwoordzoekquery's die op dezelfde inhoudslocaties worden uitgevoerd. of gebruik het script om tijd te besparen door een groot aantal inhoudslocaties niet opnieuw in te voeren wanneer u een nieuwe zoekopdracht maakt