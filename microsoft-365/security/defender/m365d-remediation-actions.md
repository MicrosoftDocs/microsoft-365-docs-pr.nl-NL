---
title: Herstelacties in Microsoft 365 Defender
description: Een overzicht krijgen van herstelacties die volgen op geautomatiseerde onderzoeken in Microsoft 365 Defender
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
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
ms.openlocfilehash: c8d3838194c25ba49b2611dc355b21e228291b01
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842525"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Herstelacties in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd. Andere herstelacties worden ondernomen voor e-mailinhoud. Geautomatiseerde onderzoeken die zijn voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.

> [!IMPORTANT]
> Of herstelacties automatisch of alleen worden ondernomen op basis van goedkeuring, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt. Zie de volgende artikelen voor meer informatie:
> - [Uw geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md)
> - [Hoe bedreigingen worden gesaneerd op apparaten](../defender-endpoint/automated-investigations.md)
> - [Bedreigingen en herstelacties op e-mail & samenwerkingsinhoud](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft 365 Defender. 

|Herstelacties voor apparaten (eindpunten)  |Herstelacties voor e-mail  |
|:---------|:---------|
|- Onderzoekspakket verzamelen <br/>- Apparaat isoleren (deze actie kan ongedaan worden gemaakt)<br/>- Offboard machine <br/>- Uitvoering van code vrijgeven <br/>- Uit quarantaine worden gezet <br/>- Voorbeeld aanvragen <br/>- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt) <br/>- Antivirusscan uitvoeren <br/>- Stoppen en in quarantaine plaatsen      |- URL blokkeren (time-of-click)<br/>- E-mailberichten of clusters zacht verwijderen<br/>- E-mail in quarantaine plaatsen<br/>- Een e-mailbijlage in quarantaine plaatsen<br/>- Externe e-mail doorsturen uitschakelen          |

Herstelacties, ongeacht of deze in behandeling zijn of al zijn voltooid, kunnen worden bekeken in het [Actiecentrum.](m365d-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Herstelacties die volgen op geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek is voltooid, wordt een vonnis bereikt voor elk bewijs dat hierbij betrokken is. Afhankelijk van de uitspraak worden herstelacties geïdentificeerd. In sommige gevallen worden herstelacties automatisch genomen. in andere gevallen wachten herstelacties op goedkeuring. Het hangt allemaal af van hoe [geautomatiseerd onderzoek en antwoord zijn geconfigureerd.](m365d-configure-auto-investigation-response.md)

De volgende tabel bevat mogelijke vonnissen en resultaten:

| Vonnis    | Betrokken entiteiten    | Resultaten|
|------|------|------|
| Kwaadaardig    | Apparaten (eindpunten)    | Herstelacties worden automatisch ondernomen (ervan uitgaande [](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig - automatisch bedreigingen **corrigeren)**|
| Kwaadaardig    | E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
| Verdacht    | Apparaten of e-mailinhoud | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
| Geen bedreigingen gevonden    | Apparaten of e-mailinhoud    | Er zijn geen herstelacties nodig|


## <a name="remediation-actions-that-are-taken-manually"></a>Herstelacties die handmatig worden ondernomen

Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan uw beveiligingsteam bepaalde herstelacties handmatig uitvoeren. Deze omvatten de volgende:

- Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine
- Handmatige e-mailactie, zoals het verwijderen van e-mailberichten 
- [Geavanceerde zoekactie](../defender-endpoint/advanced-hunting-overview.md) op apparaten of e-mail
- [Explorer-actie](../office-365-security/threat-explorer.md) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, zacht verwijderen van e-mail of moeilijk verwijderen van e-mail
- Handmatige [livereactieactie,](/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak
- Live response action with [Microsoft Defender for Endpoint API's](../defender-endpoint/management-apis.md#microsoft-defender-for-endpoint-apis), such as isolating a device, running a antivirus scan, and getting information about a file

## <a name="next-steps"></a>Volgende stappen

- [Naar het Actiecentrum](m365d-action-center.md)
- [Herstelacties weergeven en beheren](m365d-autoir-actions.md)
- [Fout-positieven of onwaar-negatieven adresseert](m365d-autoir-report-false-positives-negatives.md)
