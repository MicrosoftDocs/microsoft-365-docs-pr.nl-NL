---
title: Incidenten in Microsoft 365 Defender
description: Incidenten op verschillende apparaten, gebruikers en postvakken onderzoeken.
keywords: incidenten, waarschuwingen, onderzoeken, correlatie, aanval, machines, apparaten, gebruikers, identiteiten, identiteit, postvak, e-mail, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861621"
---
# <a name="incidents-in-microsoft-365-defender"></a>Incidenten in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u Microsoft 365 Defender ervaren? U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).
>

Een incident in Microsoft 365 Defender is een verzameling van gecorreleerde waarschuwingen en bijbehorende gegevens die het verhaal van een aanval bevatten. 

Microsoft 365-services en -apps maken waarschuwingen wanneer ze een verdachte of schadelijke gebeurtenis of activiteit detecteren. Afzonderlijke waarschuwingen geven waardevolle aanwijzingen over een voltooide of lopende aanval. Aanvallen gebruiken echter meestal verschillende technieken voor verschillende typen entiteiten, zoals apparaten, gebruikers en postvakken. Het resultaat is meerdere waarschuwingen voor meerdere entiteiten in uw tenant. 

Omdat het lastig en tijdrovend kan zijn om de afzonderlijke waarschuwingen samen te cirkelen om inzicht te krijgen in een aanval, worden de waarschuwingen en de bijbehorende informatie automatisch samengevoegd tot een incident.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Hoe Microsoft 365 Defender gebeurtenissen van entiteiten correleert in een incident":::

Bekijk dit korte overzicht van incidenten in Microsoft 365 Defender (4 minuten).

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

Door gerelateerde waarschuwingen in een incident te groeperen, krijgt u een uitgebreide weergave van een aanval. U kunt bijvoorbeeld het volgende zien:

- Waar de aanval is begonnen.
- Welke tactieken zijn gebruikt.
- Hoe ver de aanval is gegaan in uw tenant.
- Het bereik van de aanval, zoals het aantal apparaten, gebruikers en postvakken dat is beïnvloed. 
- Alle gegevens die aan de aanval zijn gekoppeld.

Als [dit is ingeschakeld,](m365d-enable.md)kan Microsoft 365 Defender automatisch waarschuwingen onderzoeken en oplossen via automatisering en kunstmatige intelligentie. U kunt ook aanvullende herstelstappen uitvoeren om de aanval op te lossen. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Incidenten en waarschuwingen in het Microsoft 365-beveiligingscentrum

U beheert incidenten van **incidenten & waarschuwingen > incidenten** tijdens de snelle lancering van het Microsoft 365-beveiligingscentrum [(security.microsoft.com).](https://security.microsoft.com) Hier is een voorbeeld.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="De pagina Incidenten in het Microsoft 365-beveiligingscentrum":::

Als u een incidentnaam selecteert, wordt een overzicht van het incident weergegeven en krijgt u toegang tot tabbladen met aanvullende informatie.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Voorbeeld van de pagina Overzicht voor een incident in het Microsoft 365-beveiligingscentrum":::

De extra tabbladen voor een incident zijn:

- Waarschuwingen 

  Alle waarschuwingen met betrekking tot het incident en de bijbehorende informatie.

- Apparaten

  Alle apparaten die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Gebruikers

  Alle gebruikers die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Postvakken

  Alle postvakken die zijn geïdentificeerd als onderdeel van of gerelateerd aan het incident.

- Onderzoeken

  Alle automatische onderzoeken die worden veroorzaakt door waarschuwingen bij het incident.

- Bewijs en antwoord

  Alle ondersteunde gebeurtenissen en verdachte entiteiten in de waarschuwingen in het incident.

Hier is de relatie tussen een incident en de gegevens en de tabbladen van een incident in het Microsoft 365-beveiligingscentrum.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="De relatie van een incident en de gegevens ervan met de tabbladen van een incident in het Microsoft 365-beveiligingscentrum":::

## <a name="next-step"></a>Volgende stap

De incidentenwachtrij van de pagina **Incidenten** bevat de meest recente incidenten. Hier kunt u het volgende doen:

- Bekijk welke incidenten prioriteit [moeten krijgen op](incident-queue.md) basis van ernst en andere factoren. 
- Voer een [onderzoek uit](investigate-incidents.md) naar een incident.
- [Beheer incidenten,](manage-incidents.md)waaronder het wijzigen van de naam, het toewijzen, classificeren en toevoegen van tags voor uw werkstroom voor incidentbeheer.
