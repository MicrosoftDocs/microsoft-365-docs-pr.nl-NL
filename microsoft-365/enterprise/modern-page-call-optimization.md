---
title: Paginagesprekken optimaliseren in moderne en klassieke publicatiesitepagina's van SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 03/11/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.reviewer: sstewart
search.appverid:
- MET150
description: Meer informatie over het optimaliseren van moderne en klassieke publicatiesitepagina's in SharePoint Online door het aantal oproepen naar SharePoint Online-service-eindpunten te beperken.
ms.openlocfilehash: cab0f6a020bd1148a0e852b5a393a6ad907f9771
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921616"
---
# <a name="optimize-page-calls-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>Paginagesprekken optimaliseren in moderne en klassieke publicatiesitepagina's van SharePoint Online

Zowel moderne als klassieke publicatiesites van SharePoint Online bevatten koppelingen die gegevens laden van (of bellen naar) SharePoint-functies en CDN's. Hoe meer oproepen door een pagina worden gedaan, hoe langer de pagina duurt om te laden. Dit staat bekend als **de waargenomen latentie van eindgebruikers of** **EUPL.**

In dit artikel wordt beschreven hoe u het aantal en de impact van oproepen naar externe eindpunten kunt bepalen vanaf uw moderne en klassieke publicerende sitepagina's en hoe u het effect ervan op de waargenomen latentie van de eindgebruiker kunt beperken.

>[!NOTE]
>Zie Prestaties in de [moderne SharePoint-ervaring](/sharepoint/modern-experience-performance)voor meer informatie over de prestaties in moderne SharePoint Online-portals.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-calls"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om paginagesprekken te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge - en Chrome-browsers waarmee zowel moderne portals van SharePoint Online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's worden geanalyseerd. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken voor SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over externe oproepen in het resultaat Aanvragen naar **SharePoint** in het deelvenster _Diagnostische_ tests. De regel wordt groen weergegeven als de sitepagina minder dan het basislijnaantal oproepen bevat en rood als de pagina het basislijnnummer overschrijdt. Het basislijnnummer is anders voor moderne en klassieke pagina's omdat klassieke sitepagina's HTTP1.1 gebruiken en moderne pagina's HTTP2.0 gebruiken:

- Moderne sitepagina's mogen niet meer dan **25 oproepen** bevatten
- Klassieke publicatiepagina's mogen niet meer dan **6 oproepen** bevatten

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): De pagina overschrijdt het aantal oproepen volgens de basislijn
- **Geen actie vereist** (groen): De pagina bevat minder dan het basislijnaantal oproepen

Als het resultaat Aanvragen naar **SharePoint** wordt weergegeven in de sectie Aandacht vereist, kunt u op het resultaat klikken voor meer informatie, inclusief het totale aantal oproepen op de pagina en een lijst met URL's. 

![Aanvragen voor SharePoint-resultaten](../media/modern-portal-optimization/pagediag-requests.png)

## <a name="remediate-performance-issues-related-to-too-many-calls-on-a-page"></a>Prestatieproblemen met te veel oproepen op een pagina oplossen

Als een pagina te veel oproepen bevat, kunt u de lijst met URL's in de resultaten van Aanvragen voor **Sharepoint** gebruiken om te bepalen of er herhaalde oproepen zijn, oproepen die moeten worden gebatcheerd of oproepen die gegevens retourneren die in de cache moeten worden opgeslagen.

**Batching REST calls can** help to reduce performance overhead. Zie Batchaanvragen maken met de [REST-API's](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis)voor meer informatie over api-oproepbatching.

**Als** u een cache gebruikt om de resultaten van een API-oproep op te slaan, kunt u de prestaties van een warm verzoek verbeteren door de client de gegevens in de cache te laten gebruiken in plaats van extra te bellen voor elke volgende paginabelasting. Er zijn verschillende manieren om deze oplossing te benaderen, afhankelijk van de bedrijfsvereisten. Als de gegevens voor alle gebruikers hetzelfde zijn, is het gebruik van een cachingservice met een middenlaag, zoals [ _Azure Redis-cache,_](https://azure.microsoft.com/services/cache/) een goede optie om het API-verkeer ten opzichte van een site aanzienlijk te verminderen, omdat de gebruikers de gegevens bij de caching-service zouden aanvragen in plaats van rechtstreeks bij SPO. De enige SPO-oproepen die nodig zijn, zijn het vernieuwen van de cache van de middelste laag. Als de gegevens per gebruiker fluctueren, kunt u het beste een cache aan de clientzijde implementeren, zoals LocalStorage of zelfs een Cookie. Hierdoor worden de gespreksvolumes nog steeds beperkt doordat de volgende aanvragen van dezelfde gebruiker voor de duur van de cache worden verwijderd, maar minder efficiënt zijn dan een speciale caching-service. Met PnP kunt u LocalStorage gebruiken met weinig extra ontwikkeling vereist.

Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden. U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties van SharePoint Online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties van Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint-ervaring](/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)