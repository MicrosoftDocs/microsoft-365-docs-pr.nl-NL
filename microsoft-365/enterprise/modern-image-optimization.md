---
title: Afbeeldingen optimaliseren op moderne sitepagina's van SharePoint Online
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
description: Lees hoe u de hulpmiddelen in SharePoint Online kunt gebruiken om afbeeldingen te optimaliseren op moderne sitepagina's van SharePoint Online.
ms.openlocfilehash: a4f2def86e1378a9fb76ae9ecbe6a55da75ecffc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923014"
---
# <a name="optimize-images-in-sharepoint-online-modern-site-pages"></a>Afbeeldingen optimaliseren op moderne sitepagina's van SharePoint Online

In dit artikel vindt u meer informatie over het optimaliseren van afbeeldingen op moderne sitepagina's van SharePoint Online.

Zie Afbeeldingsoptimalisatie voor [SharePoint Online](image-optimization-for-sharepoint-online.md)voor informatie over het optimaliseren van afbeeldingen in klassieke publicatiesites.

>[!NOTE]
>Zie Prestaties in de [moderne SharePoint-ervaring](/sharepoint/modern-experience-performance)voor meer informatie over de prestaties in moderne SharePoint Online-portals.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-analyze-image-optimization"></a>Het hulpprogramma Paginadiagnose voor SharePoint gebruiken om afbeeldingsoptimalisatie te analyseren

Het hulpprogramma Paginadiagnose voor SharePoint is een browserextensie voor de nieuwe Microsoft Edge - en Chrome-browsers waarmee zowel moderne portals van SharePoint Online als klassieke https://www.microsoft.com/edge) publicerende sitepagina's worden geanalyseerd. Het hulpprogramma bevat een rapport voor elke geanalyseerde pagina die laat zien hoe de pagina presteert op basis van een gedefinieerde set prestatiecriteria. Als u het hulpprogramma Paginadiagnose voor SharePoint wilt installeren en meer wilt weten, gaat u naar Het hulpprogramma [Paginadiagnose gebruiken voor SharePoint Online.](page-diagnostics-for-spo.md)

>[!NOTE]
>Het hulpprogramma Paginadiagnose werkt alleen voor SharePoint Online en kan niet worden gebruikt op een SharePoint-systeempagina.

Wanneer u een moderne SharePoint-site analyseert met het hulpprogramma Paginadiagnose voor SharePoint, ziet u informatie over grote afbeeldingen in het deelvenster _Diagnostische tests._

Mogelijke resultaten zijn:

- **Aandacht vereist** (rood): De pagina bevat **een of meer** afbeeldingen van meer dan 300 KB in grootte
- **Geen actie vereist** (groen): De pagina bevat geen afbeeldingen van meer dan 300 KB in grootte

Als het **gedetecteerde resultaat Grote**  afbeeldingen wordt weergegeven in de sectie Aandacht vereist van de resultaten, kunt u op het resultaat klikken om meer informatie te zien.

![Resultaten van het hulpprogramma Paginadiagnose](../media/modern-portal-optimization/pagediag-large-images.png)

## <a name="remediate-large-image-issues"></a>Grote problemen met afbeeldingen oplossen

Als een pagina afbeeldingen van meer dan 300 KB groot bevat, selecteert u het resultaat Grote afbeeldingen gedetecteerd om te zien welke afbeeldingen te groot zijn.  Op moderne SharePoint Online-pagina's worden afbeeldingen automatisch weergegeven en de grootte is afhankelijk van de grootte van het browservenster en de resolutie van de clientmonitor. U moet afbeeldingen altijd optimaliseren voor webgebruik voordat u ze uploadt naar SharePoint Online. Zeer grote afbeeldingen worden automatisch verkleind in grootte en resolutie, wat kan leiden tot onverwachte weergavekenmerken.

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