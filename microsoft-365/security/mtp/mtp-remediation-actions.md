---
title: Herstelacties in Microsoft 365 Defender
description: Een overzicht van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: c6b0275335f32419b470c789d83b069be7839c36
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932848"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Herstelacties in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Herstelacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd. Andere herstelacties worden ondernomen op e-mailinhoud. Automatische onderzoeken worden voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.

> [!IMPORTANT]
> Of herstelacties automatisch of alleen bij goedkeuring worden ondernomen, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt. Zie de volgende artikelen voor meer informatie:
> - [Geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Hoe bedreigingen worden verteerd op apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedreigingen en herstelacties voor e-mail & samenwerkingsinhoud](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

De volgende tabel bevat een overzicht van herstelacties die momenteel worden ondersteund in Microsoft 365 Defender: 

|Herstelacties voor apparaten (eindpunt)  |Herstelacties voor e-mail  |
|---------|---------|
|- Pakket voor onderzoek verzamelen <br/>- Isoleert apparaat (deze actie kan ongedaan worden gemaakt)<br/>- Offboard machine <br/>- Uitvoering van releasecode <br/>- In quarantaine worden vrijgegeven <br/>- Voorbeeld aanvragen <br/>- De uitvoering van code beperken (deze actie kan ongedaan worden gemaakt) <br/>- Antivirusscan uitvoeren <br/>- Stoppen en quarantaine      |- URL blokkeren (time-of-click)<br/>- E-mailberichten of clusters zacht verwijderen<br/>- E-mail in quarantaine<br/>- Een e-mailbijlage in quarantaine plaatsen<br/>- Externe doorsturen uitschakelen          |

Herstelacties, in behandeling of al voltooid, kunnen worden bekeken in het [Actiecentrum.](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Herstelacties die geautomatiseerde onderzoeken volgen

Wanneer een geautomatiseerd onderzoek is voltooid, wordt er een overeenkomst bereikt voor elk stukje bewijs dat daarbij betrokken is. Afhankelijk van de situatie worden herstelacties vastgesteld. In sommige gevallen worden er automatisch herstelacties ondernomen. In andere gevallen wachten herstelacties op goedkeuring. Het hangt allemaal af van hoe [automatisch onderzoek en antwoorden zijn geconfigureerd.](mtp-configure-auto-investigation-response.md)

In de volgende tabel worden mogelijke voor- en resultaatresultaten vermeld:

| 16:    | Gebied    | Resultaten|
|------|------|------|
| Schadelijk    | Apparaten (eindpunten)    | Herstelacties worden automatisch ondernomen (ervan uitgaande [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig- automatisch herstellen van **bedreigingen)**|
| Schadelijk    | E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties wachten op goedkeuring|
| Verdacht    | Apparaten of e-mailinhoud | Aanbevolen herstelacties wachten op goedkeuring|
| Geen bedreigingen gevonden    | Apparaten of e-mailinhoud    | Er zijn geen herstelacties nodig|


## <a name="remediation-actions-that-are-taken-manually"></a>Herstelacties die handmatig worden ondernomen

Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan het team voor beveiligingsbewerkingen bepaalde herstelacties handmatig uitvoeren. Dit zijn onder andere de volgende acties:

- Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine.
- Handmatige e-mailactie, zoals het verwijderen van e-mailberichten. 
- [Geavanceerde zoekactie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) op apparaten of e-mail.
- [Verkenner-actie](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, het verwijderen van e-mail of het moeilijk verwijderen van e-mail.
- Handmatige [live antwoordactie,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals een bestand verwijderen, een proces stoppen en een geplande taak verwijderen.
- Live-actie met [Microsoft Defender voor eindpunt-API's,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis)zoals het isoleren van een apparaat, het uitvoeren van een antivirusscan en het verkrijgen van informatie over een bestand. 

## <a name="next-steps"></a>Volgende stappen

- [Naar het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Acties in behandeling goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken](mtp-autoir-report-false-positives-negatives.md)
