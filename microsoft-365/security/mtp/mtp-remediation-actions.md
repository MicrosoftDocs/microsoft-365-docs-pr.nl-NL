---
title: Herstelacties na geautomatiseerd onderzoek in Microsoft Threat Protection
description: Bekijk een overzicht van de acties voor herstel na de geautomatiseerde tests in Microsoft Threat Protection
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstel
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.date: 09/16/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 232d19cb0bcb6a2f91c1bdad15d842ec7396499c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201049"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Herstelacties na geautomatiseerd onderzoek in Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft Threat Protection


## <a name="remediation-actions"></a>Herstelacties

Bij een geautomatiseerd onderzoek in Microsoft Threat Protection worden herstelacties herkend voor schadelijke of verdachte items. Sommige soorten herstelbewerkingen worden uitgevoerd op apparaten, ook wel eindpunten genoemd. Voor e-mail inhoud worden andere herstelacties gebruikt. Geautomatiseerd onderzoek na voltooiing van herstelacties worden uitgevoerd, goedgekeurd of afgekeurd.

De volgende tabel bevat een overzicht van herstelacties die momenteel worden ondersteund in Microsoft Threat Protection: 

|Acties voor herstel van apparaten (eindpunten)  |Acties voor het herstel van e-mailberichten  |
|---------|---------|
|-Onderzoek pakket verzamelen <br/>-Isoleer apparaat (deze actie kan ongedaan worden gemaakt)<br/>-Verwijderen-computer <br/>Uitvoering van uitvoering van programmacode <br/>-Na quarantaine publicatie <br/>-Voorbeeld van aanvraag <br/>-Uitvoering van code beperken (deze actie kan ongedaan worden gemaakt) <br/>-Virusscan uitvoeren <br/>-Stop en Quarantine      |-Blok URL (time-of-klik)<br/>-Tijdelijke e-mail-en cluster berichten verwijderen<br/>-E-mail in quarantaine<br/>-Een e-mailbijlage in quarantaine plaatsen<br/>-Externe e-mail doorsturen uitschakelen          |

Herstelacties, ongeacht of ze goedkeuring of al zijn voltooid, kunnen worden weergegeven in het [Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-follow-automated-investigations"></a>Voor herstelacties volgen geautomatiseerd onderzoek

Wanneer een geautomatiseerd onderzoek wordt voltooid, wordt een verdict voor elk bewijs van het bewijs bereikt. Afhankelijk van het verdict worden herstelacties aangegeven. In sommige gevallen worden herstelacties automatisch uitgevoerd. in andere gevallen zijn herstelacties in afwachting van goedkeuring. Het is alles afhankelijk van de manier waarop [automatisch onderzoek en beantwoorden zijn geconfigureerd](mtp-configure-auto-investigation-response.md).

De volgende tabel bevat mogelijke Verdicts en resultaten:

|Verdict    |Ziet    |Resultaten|
|------|------|------|
|Schadelijke    |Apparaten (eindpunten)    |Herstel stappen worden automatisch uitgevoerd (als u ervan uitgaat dat de [Apparaatgroepen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) van uw organisatie **automatisch**worden ingesteld op volledig herstelde bedreigingen)|
|Schadelijke    |E-mail inhoud (Url's of bijlagen) | Aanbevolen herstelacties wachten op goedkeuring|
|Melden    |Apparaten of e-mail inhoud |Aanbevolen herstelacties wachten op goedkeuring|
|Geen bedreigingen gevonden    |Apparaten of e-mail inhoud    |Er zijn geen herstelacties nodig|

> [!IMPORTANT]
> Of herstelacties automatisch of alleen na de goedkeuring worden uitgevoerd, hangt af van bepaalde instellingen, zoals het beleid van de groep apparaat van uw organisatie. Zie de volgende artikelen voor meer informatie:
> - [Geautomatiseerd onderzoek-en antwoord mogelijkheden in Microsoft Threat Protection configureren](mtp-configure-auto-investigation-response.md)
> - [Hoe bedreigingen op apparaten worden hersteld](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

## <a name="next-steps"></a>Volgende stappen

- [Naar het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Acties in behandeling goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden](mtp-autoir-report-false-positives-negatives.md)
