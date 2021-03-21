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
ms.date: 01/29/2021
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 7dd95e8d7fe6424e294fbc9500fb908819463678
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928626"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Herstelacties in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Herstelacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender worden herstelacties geïdentificeerd voor schadelijke of verdachte items. Sommige soorten herstelacties worden ondernomen op apparaten, ook wel eindpunten genoemd. Andere herstelacties worden ondernomen voor e-mailinhoud. Geautomatiseerde onderzoeken die zijn voltooid nadat herstelacties zijn ondernomen, goedgekeurd of geweigerd.

> [!IMPORTANT]
> Of herstelacties automatisch of alleen worden ondernomen op basis van goedkeuring, hangt af van bepaalde instellingen, zoals de manier waarop automatiseringsniveaus worden gebruikt. Zie de volgende artikelen voor meer informatie:
> - [Uw geautomatiseerde onderzoeks- en antwoordmogelijkheden configureren in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Hoe bedreigingen worden gesaneerd op apparaten](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedreigingen en herstelacties op e-mail & samenwerkingsinhoud](../office-365-security/air-remediation-actions.md#threats-and-remediation-actions)

In de volgende tabel worden herstelacties samengevat die momenteel worden ondersteund in Microsoft 365 Defender: 

|Herstelacties voor apparaten (eindpunten)  |Herstelacties voor e-mail  |
|:---------|:---------|
|- Onderzoekspakket verzamelen <br/>- Apparaat isoleren (deze actie kan ongedaan worden gemaakt)<br/>- Offboard machine <br/>- Uitvoering van code vrijgeven <br/>- Uit quarantaine worden gezet <br/>- Voorbeeld aanvragen <br/>- Codeuitvoering beperken (deze actie kan ongedaan worden gemaakt) <br/>- Antivirusscan uitvoeren <br/>- Stoppen en in quarantaine plaatsen      |- URL blokkeren (time-of-click)<br/>- E-mailberichten of clusters zacht verwijderen<br/>- E-mail in quarantaine plaatsen<br/>- Een e-mailbijlage in quarantaine plaatsen<br/>- Externe e-mail doorsturen uitschakelen          |

Herstelacties, in behandeling of al voltooid, kunnen worden bekeken in het [Actiecentrum.](./mtp-action-center.md)

## <a name="remediation-actions-that-follow-automated-investigations"></a>Herstelacties die volgen op geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek is voltooid, wordt een vonnis bereikt voor elk bewijs dat hierbij betrokken is. Afhankelijk van de uitspraak worden herstelacties geïdentificeerd. In sommige gevallen worden herstelacties automatisch genomen. in andere gevallen wachten herstelacties op goedkeuring. Het hangt allemaal af van hoe [geautomatiseerd onderzoek en antwoord zijn geconfigureerd.](mtp-configure-auto-investigation-response.md)

De volgende tabel bevat mogelijke vonnissen en resultaten:

| Vonnis    | Gebied    | Resultaten|
|------|------|------|
| Schadelijk    | Apparaten (eindpunten)    | Herstelacties worden automatisch ondernomen (ervan uitgaande [](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) dat de apparaatgroepen van uw organisatie zijn ingesteld op Volledig - automatisch bedreigingen **corrigeren)**|
| Schadelijk    | E-mailinhoud (URL's of bijlagen) | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
| Verdacht    | Apparaten of e-mailinhoud | Aanbevolen herstelacties zijn in afwachting van goedkeuring|
| Geen bedreigingen gevonden    | Apparaten of e-mailinhoud    | Er zijn geen herstelacties nodig|


## <a name="remediation-actions-that-are-taken-manually"></a>Herstelacties die handmatig worden ondernomen

Naast herstelacties die volgen op geautomatiseerde onderzoeken, kan uw beveiligingsteam bepaalde herstelacties handmatig uitvoeren. Hieronder volgen de volgende acties:

- Handmatige apparaatactie, zoals apparaatisolatie of bestands quarantaine.
- Handmatige e-mailactie, zoals het verwijderen van e-mailberichten. 
- [Geavanceerde zoekactie](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) op apparaten of e-mail.
- [Explorer-actie](../office-365-security/threat-explorer.md) voor e-mailinhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, het verwijderen van e-mail of het moeilijk verwijderen van e-mail.
- Handmatige [livereactieactie,](/windows/security/threat-protection/microsoft-defender-atp/live-response) zoals het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak.
- Live response action with [Microsoft Defender for Endpoint API's](/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), such as isolating a device, running an antivirus scan, and getting information about a file. 

## <a name="next-steps"></a>Volgende stappen

- [Naar het Actiecentrum](./mtp-action-center.md)
- [Herstelacties weergeven en beheren](./mtp-autoir-actions.md)
- [False positives/negatives verwerken in geautomatiseerde onderzoeks- en antwoordmogelijkheden](mtp-autoir-report-false-positives-negatives.md)