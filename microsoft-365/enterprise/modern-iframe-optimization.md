---
title: iFrames optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online
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
description: Meer informatie over het optimaliseren van de prestaties van iFrames in SharePoint moderne en klassieke publicerende sitepagina's online.
ms.openlocfilehash: d6e9aefa23972589c752540959b17f5d20ed0889
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923054"
---
# <a name="optimize-iframes-in-sharepoint-online-modern-and-classic-publishing-site-pages"></a>iFrames optimaliseren in SharePoint moderne en klassieke publicatiesitepagina's online

iFrames kunnen handig zijn voor het bekijken van uitgebreide inhoud, zoals video's of andere media. Omdat iFrames echter een afzonderlijke pagina laden op de sitepagina van SharePoint, kan inhoud die in het iFrame wordt geladen, grote afbeeldingen, video's of andere elementen bevatten die kunnen bijdragen aan de totale laadtijden van pagina's en die u niet kunt bepalen op de pagina. In dit artikel wordt beschreven hoe u kunt bepalen hoe iFrames op uw pagina's van invloed zijn op de waargenomen latentie van de gebruiker en hoe u veelvoorkomende problemen kunt oplossen.

>[!NOTE]
>Zie Prestaties in de moderne SharePoint voor meer informatie over prestaties in SharePoint moderne [onlinesites.](/sharepoint/modern-experience-performance)

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-web-parts-using-iframes"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om webonderdelen te analyseren met iFrames

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge ( en Chrome-browsers die zowel SharePoint Moderne portal online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's analyseren. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken](page-diagnostics-for-spo.md)voor SharePoint Online.

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen SharePoint Online en kan niet worden gebruikt op een SharePoint systeempagina.

Wanneer u een SharePoint sitepagina analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over webonderdelen met iFrames in het deelvenster _Diagnostische_ tests. De basislijnmetriek is hetzelfde voor moderne en klassieke pagina's.

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): de pagina bevat **drie of meer** webonderdelen met iFrames
- **Verbeterkansen** (geel): De pagina bevat **een of twee** webonderdelen met iFrames
- **Geen actie vereist** (groen): de pagina bevat geen webonderdelen met iFrames

Als de webonderdelen met **iFrames** gedetecteerd resultaat  worden  weergegeven in de sectie Verbeterkansen of Aandacht vereist) van de resultaten, kunt u op het resultaat klikken om de webonderdelen te zien die iFrames bevatten.

![Resultaten van het hulpprogramma Paginadiagnose](../media/modern-portal-optimization/pagediag-iframe-yellow.png)

## <a name="remediate-iframe-performance-issues"></a>Problemen met de prestaties van iFrame oplossen

Gebruik de webonderdelen met **iFrames** gedetecteerd resultaat in het hulpprogramma Paginadiagnose om te bepalen welke webonderdelen iFrames bevatten en kunnen bijdragen aan trage laadtijden voor pagina's.

iFrames zijn inherent traag omdat ze een afzonderlijke externe pagina laden, inclusief alle bijbehorende inhoud, zoals javascript, CSS en framework-elementen, waardoor de overhead van de sitepagina mogelijk met twee of meer wordt verhogen.

Volg de onderstaande richtlijnen om ervoor te zorgen dat iFrames optimaal worden gebruikt.

- Gebruik indien mogelijk afbeeldingen in plaats van iFrames als de preview klein is om te beginnen of niet interactief is.
- Als iFrames moeten worden gebruikt, minimaliseert u het aantal en/of verplaatst u deze uit de viewport.
- Ingesloten Office, zoals Word, Excel en PowerPoint zijn interactief, maar worden traag geladen. Miniatuurafbeeldingen met een koppeling naar het volledige document presteren vaak beter.
- Ingesloten YouTube-video's en Twitter-feeds presteren meestal beter in iFrames, maar gebruiken dit soort insluitingen op een verstandige manier.
- Geïsoleerde webonderdelen vormen een redelijke uitzondering, maar minimaliseren het aantal en de plaatsing ervan in de viewport.
- Als een iFrame zich buiten de viewport bevindt, kunt u overwegen een _IntersectionObserver_ te gebruiken om de weergave van het iFrame uit te stellen totdat deze in beeld komt.

Voordat u paginaherzieningen maakt om prestatieproblemen op te lossen, noteert u de laadtijd van de pagina in de analyseresultaten. Voer het hulpprogramma na de revisie opnieuw uit om te zien of het nieuwe resultaat binnen de basislijnstandaard valt en controleer de laadtijd van de nieuwe pagina om te zien of er een verbetering is.

![De laadtijd van pagina's](../media/modern-portal-optimization/pagediag-page-load-time.png)

>[!NOTE]
>De laadtijd van pagina's kan variëren op basis van verschillende factoren, zoals de netwerkbelasting, de tijd van de dag en andere tijdelijke omstandigheden. U moet de laadtijd van pagina's een paar keer voor en na het aanbrengen van wijzigingen testen, zodat u de resultaten kunt gemiddelden.

## <a name="related-topics"></a>Verwante onderwerpen

[Prestaties SharePoint online afstemmen](tune-sharepoint-online-performance.md)

[Prestaties Office 365 afstemmen](tune-microsoft-365-performance.md)

[Prestaties in de moderne SharePoint ervaring](/sharepoint/modern-experience-performance)