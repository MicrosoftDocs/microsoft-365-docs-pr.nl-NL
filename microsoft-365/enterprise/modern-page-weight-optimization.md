---
title: Paginagewicht optimaliseren in SharePoint moderne onlinesitepagina's
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
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: sstewart
search.appverid:
- MET150
description: Meer informatie over het gebruik van het hulpprogramma Paginadiagnose om het paginagewicht te SharePoint moderne sitepagina's online.
ms.openlocfilehash: 780d8ca0debbc5efb834f8f3543b9a5a8d168108
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907442"
---
# <a name="optimize-page-weight-in-sharepoint-online-modern-site-pages"></a>Paginagewicht optimaliseren in SharePoint moderne onlinesitepagina's

SharePoint Moderne onlinesitepagina's bevatten seriële code die is vereist om pagina-inhoud van de pagina weer te geven, inclusief afbeeldingen, tekst, objecten in het inhoudsgebied onder navigatie-/opdrachtbalken en andere HTML-code die het kader van de pagina vormt. Paginagewicht is een meting van deze HTML-code en moet worden beperkt om optimale laadtijden voor pagina's te garanderen.

In dit artikel wordt beschreven hoe u het paginagewicht op uw moderne sitepagina's kunt verminderen.

>[!NOTE]
>Zie Prestaties in de moderne SharePoint voor meer informatie over prestaties in SharePoint moderne [onlineportalen.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-page-weight"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om het paginagewicht te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](page-diagnostics-for-spo.md)voor SharePoint Online.

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

Wanneer u een SharePoint-sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over de pagina  in het paginagewicht onder **500 KB-resultaat** van het deelvenster Diagnostische tests. Het resultaat wordt groen weergegeven als het paginagewicht onder de basislijnwaarde valt en rood als het paginagewicht de basislijnwaarde overschrijdt.

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): Paginagewicht groter dan 500 KB
- **Geen actie vereist** (groen): Paginagewicht is minder dan 500 KB

Als het  **paginagewicht onder 500 KB** wordt weergegeven in de sectie Aandacht vereist, kunt u op het resultaat klikken voor meer informatie.

![Aanvragen om SharePoint resultaten](../media/modern-portal-optimization/pagediag-page-weight.png)

## <a name="remediate-page-weight-issues"></a>Problemen met het gewicht van pagina's oplossen

Als het paginagewicht meer dan 500 KB bedraagt, kunt u de totale laadtijd van pagina's verbeteren door het aantal webonderdelen te verminderen en de pagina-inhoud in de juiste mate te beperken.

Algemene richtlijnen voor het verminderen van het paginagewicht zijn:

- Beperk de pagina-inhoud tot een redelijk bedrag en gebruik meerdere pagina's voor gerelateerde inhoud.
- Minimaliseer het gebruik van webonderdelen met grote eigenschappentassen.
- Gebruik indien mogelijk niet-interactieve rollupweergaven.
- Optimaliseer de grootte van afbeeldingen door afbeeldingen op de juiste manier te formaatken, gecomprimeerde afbeeldingsindelingen te gebruiken en ervoor te zorgen dat ze worden gedownload van een CDN.

In het volgende artikel vindt u aanvullende richtlijnen voor het beperken van het paginagewicht:

- [Paginaprestaties optimaliseren in SharePoint](/sharepoint/dev/general-development/optimize-page-performance-in-sharepoint)

Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden. U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties SharePoint online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint ervaring](/sharepoint/modern-experience-performance)

[Netwerken voor contentlevering](content-delivery-networks.md)

[De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online](use-microsoft-365-cdn-with-spo.md)