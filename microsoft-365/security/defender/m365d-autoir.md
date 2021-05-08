---
title: Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender
description: Krijg een overzicht van geautomatiseerde onderzoeks- en antwoordmogelijkheden, ook wel self-healing genoemd, in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, zelfherstel
search.appverid: met150
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
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: fcb7283faed6fe8c5af59cedeeb90577b557ab34
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259533"
---
# <a name="automated-investigation-and-response-in-microsoft-365-defender"></a>Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Als uw organisatie Microsoft 365 [Defender](microsoft-365-defender.md)gebruikt, ontvangt uw beveiligingsteam een waarschuwing in het Microsoft 365-beveiligingscentrum wanneer een schadelijke of verdachte activiteit of artefact wordt gedetecteerd. Gezien de schijnbaar eindeloze stroom van bedreigingen die kunnen binnenstromen, worden beveiligingsteams vaak geconfronteerd met de uitdaging om het grote aantal waarschuwingen aan te pakken. Gelukkig bevat Microsoft 365 Defender geautomatiseerde mogelijkheden voor onderzoek en herstel (AIR) die uw beveiligingsteam kunnen helpen om bedreigingen efficiënter en effectiever aan te pakken.

Dit artikel bevat een overzicht van AIR en bevat koppelingen naar de volgende stappen en aanvullende bronnen.

> [!TIP]
> Wilt u Microsoft 365 Defender ervaren? U kunt het [evalueren in een testomgeving](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) of [uw pilotproject uitvoeren in een productieomgeving](m365d-pilot.md?ocid=cx-evalpilot).

## <a name="how-automated-investigation-and-self-healing-works"></a>Hoe geautomatiseerd onderzoek en zelfherstel werken

Wanneer beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen. Het kan erg tijdrovend zijn om prioriteit te geven aan waarschuwingen en deze te onderzoeken, met name wanneer er nieuwe waarschuwingen binnen blijven komen terwijl er een onderzoek wordt gestart. Beveiligingsbewerkingsteams kunnen zich overstelpt voelen door het grote aantal bedreigingen dat ze moeten bewaken en beschermen. Geautomatiseerde onderzoeks- en antwoordmogelijkheden, met self-heling, in Microsoft 365 Defender kan helpen.

Bekijk de volgende video om te zien hoe zelfherstel werkt: <p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

In Microsoft 365 Defender werkt automatisch onderzoek en antwoord met self-helende mogelijkheden op uw apparaten, e-mail & inhoud en identiteiten.
 
> [!TIP]
> In dit artikel wordt beschreven hoe geautomatiseerd onderzoek en antwoord werken. Zie Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 [Defender om deze mogelijkheden te configureren.](m365d-configure-auto-investigation-response.md)

## <a name="your-own-virtual-analyst"></a>Uw eigen virtuele analist

Imagine virtuele analist in uw beveiligingsteam van Tier 1 of Tier 2. De virtuele analist bootst de ideale stappen na die beveiligingsbewerkingen zouden ondernemen om bedreigingen te onderzoeken en te corrigeren. De virtuele analist kan 24x7 werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingsremediatie op zich nemen. Een dergelijke virtuele analist kan de tijd om te reageren aanzienlijk verminderen, waardoor uw team voor beveiligingsactiviteiten vrij komt voor andere belangrijke bedreigingen of strategische projecten. Als dit scenario klinkt als sciencefiction, is dat niet zo. Een dergelijke virtuele analist maakt deel uit van Microsoft 365 Defender-suite en de naam is *geautomatiseerd onderzoek en antwoord.*

Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan uw beveiligingsteam de capaciteit van uw organisatie voor beveiligingswaarschuwingen en incidenten aanzienlijk vergroten. Met geautomatiseerde onderzoeken en antwoorden kunt u de kosten van het omgaan met onderzoek- en herstelactiviteiten verlagen en het beste uit uw suite voor bedreigingsbeveiliging halen. Geautomatiseerde onderzoeks- en antwoordmogelijkheden helpen uw team voor beveiligingsbewerkingen door:

1. Bepalen of een bedreiging actie vereist.
2. Het nemen (of aanbevelen van) de benodigde herstelacties.
3. Bepalen of en welke andere onderzoeken moeten worden uitgevoerd.
4. Herhaal het proces zo nodig voor andere waarschuwingen.

## <a name="the-automated-investigation-process"></a>Het geautomatiseerde onderzoeksproces

Met een waarschuwing wordt een incident gemaakt dat een geautomatiseerd onderzoek kan starten. Het geautomatiseerde onderzoek resulteert in een vonnis voor elk bewijs. Vonnissen kunnen zijn:
- *Schadelijk*
- *Verdacht* 
- *Geen bedreigingen gevonden* 

Herstelacties voor schadelijke of verdachte entiteiten worden geïdentificeerd. Voorbeelden van herstelacties zijn:

- Een bestand in quarantaine plaatsen
- Een proces stoppen
- Een apparaat isoleren
- Een URL blokkeren 
- Andere acties

Zie Herstelacties in Microsoft 365 [Defender voor meer informatie.](m365d-remediation-actions.md)

Afhankelijk van [hoe](m365d-configure-auto-investigation-response.md) geautomatiseerde onderzoeks- en antwoordmogelijkheden voor uw organisatie zijn geconfigureerd, worden herstelacties automatisch of alleen uitgevoerd na goedkeuring door uw beveiligingsteam. Alle acties, in behandeling of voltooid, worden weergegeven in het [Actiecentrum.](m365d-action-center.md)

Terwijl een onderzoek wordt uitgevoerd, worden eventuele andere gerelateerde waarschuwingen toegevoegd aan het onderzoek totdat het is voltooid. Als een betrokken entiteit ergens anders wordt gezien, wordt het bereik van het geautomatiseerde onderzoek uitgebreid met deze entiteit en wordt het onderzoeksproces herhaald. 

In Microsoft 365 Defender correleert elk geautomatiseerd onderzoek signalen in Microsoft Defender voor identiteit, Microsoft Defender voor eindpunt en Microsoft Defender voor Office 365, zoals samengevat in de volgende tabel: 

|Entiteiten |Bedreigingsbeveiligingsservices  |
|:---------|:---------|
|Apparaten (ook wel eindpunten of machines genoemd) |[Defender voor Eindpunt](../defender-endpoint/automated-investigations.md) |      
|On-premises Active Directory-gebruikers, entiteitsgedrag en activiteiten     |[Defender for Identity](/azure-advanced-threat-protection/what-is-atp) |      
|E-mailinhoud (e-mailberichten die bestanden en URL's kunnen bevatten)     |[Defender voor Office 365](../office-365-security/defender-for-office-365.md) |

> [!NOTE]
> Niet elke waarschuwing activeert een geautomatiseerd onderzoek en niet elk onderzoek resulteert in geautomatiseerde herstelacties. Dit hangt af van de configuratie van geautomatiseerde onderzoeken en antwoorden voor uw organisatie. Zie [Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren.](m365d-configure-auto-investigation-response.md)

## <a name="viewing-a-list-of-investigations"></a>Een lijst met onderzoeken weergeven

Als u onderzoeken wilt bekijken, gaat u naar de **pagina Incidenten.** Selecteer een incident en selecteer vervolgens het **tabblad Onderzoeken.** Zie Details en resultaten van een geautomatiseerd onderzoek voor [meer informatie.](m365d-autoir-results.md)


## <a name="next-steps"></a>Volgende stappen

- [Bekijk de vereisten voor geautomatiseerd onderzoek en antwoord](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
- [Geautomatiseerd onderzoek en antwoord configureren voor uw organisatie](m365d-configure-auto-investigation-response.md)
- [Meer informatie over het Actiecentrum](m365d-action-center.md)
