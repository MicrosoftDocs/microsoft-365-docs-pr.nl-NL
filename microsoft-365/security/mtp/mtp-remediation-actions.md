---
title: Herstelacties in Microsoft 365 Defender
description: Een overzicht van herstelacties volgen voor geautomatiseerde onderzoek in Microsoft 365 Defender
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.date: 12/09/2020
ms.reviewer: evaldm, isco
ms.openlocfilehash: 9e489e3b0100aa138b11d4bfb4ccc8048a2113f4
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683293"
---
# <a name="remediation-actions-in-microsoft-365-defender"></a>Herstelacties in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

## <a name="remediation-actions"></a>Herstelacties

Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 Defender, worden herstelacties herkend voor schadelijke of verdachte items. Sommige soorten herstelbewerkingen worden uitgevoerd op apparaten, ook wel eindpunten genoemd. Voor e-mail inhoud worden andere herstelacties gebruikt. Geautomatiseerd onderzoek na voltooiing van herstelacties worden uitgevoerd, goedgekeurd of afgekeurd.

> [!IMPORTANT]
> Of herstelacties automatisch of alleen na de goedkeuring worden uitgevoerd, zijn afhankelijk van bepaalde instellingen, zoals de werking van automatiserings niveaus. Zie de volgende artikelen voor meer informatie:
> - [De mogelijkheden voor automatisch onderzoek en antwoorden configureren in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md)
> - [Hoe bedreigingen op apparaten worden hersteld](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
> - [Bedreigingen en herstelacties op e-mail & samenwerkingsinhoud](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions#threats-and-remediation-actions)

De volgende tabel bevat een overzicht van herstelacties die momenteel worden ondersteund in Microsoft 365 Defender: 

|Acties voor herstel van apparaten (eindpunten)  |Acties voor het herstel van e-mailberichten  |
|---------|---------|
|-Onderzoek pakket verzamelen <br/>-Isoleer apparaat (deze actie kan ongedaan worden gemaakt)<br/>-Verwijderen-computer <br/>Uitvoering van uitvoering van programmacode <br/>-Na quarantaine publicatie <br/>-Voorbeeld van aanvraag <br/>-Uitvoering van code beperken (deze actie kan ongedaan worden gemaakt) <br/>-Virusscan uitvoeren <br/>-Stop en Quarantine      |-Blok URL (time-of-klik)<br/>-Tijdelijke e-mail-en cluster berichten verwijderen<br/>-E-mail in quarantaine<br/>-Een e-mailbijlage in quarantaine plaatsen<br/>-Externe e-mail doorsturen uitschakelen          |

Herstelacties, ongeacht of ze goedkeuring of al zijn voltooid, kunnen worden weergegeven in het [Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="remediation-actions-that-follow-automated-investigations"></a>Herstelacties die volgen op geautomatiseerde onderzoeken

Wanneer een geautomatiseerd onderzoek wordt voltooid, wordt een verdict voor elk bewijs van het bewijs bereikt. Afhankelijk van het verdict worden herstelacties aangegeven. In sommige gevallen worden herstelacties automatisch uitgevoerd. in andere gevallen zijn herstelacties in afwachting van goedkeuring. Het is alles afhankelijk van de manier waarop [automatisch onderzoek en beantwoorden zijn geconfigureerd](mtp-configure-auto-investigation-response.md).

De volgende tabel bevat mogelijke Verdicts en resultaten:

| Verdict    | Ziet    | Resultaten|
|------|------|------|
| Schadelijke    | Apparaten (eindpunten)    | Herstel stappen worden automatisch uitgevoerd (als u ervan uitgaat dat de [Apparaatgroepen](mtp-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups) van uw organisatie **automatisch** worden ingesteld op volledig herstelde bedreigingen)|
| Schadelijke    | E-mail inhoud (Url's of bijlagen) | Aanbevolen herstelacties wachten op goedkeuring|
| Melden    | Apparaten of e-mail inhoud | Aanbevolen herstelacties wachten op goedkeuring|
| Geen bedreigingen gevonden    | Apparaten of e-mail inhoud    | Er zijn geen herstelacties nodig|


## <a name="remediation-actions-that-are-taken-manually"></a>Herstelacties die handmatig worden uitgevoerd

Naast de acties voor herstel die na geautomatiseerde tests volgen, kunnen uw beveiligingsteam bepaalde herstelacties handmatig uitvoeren. Dit zijn de volgende acties:

- Handmatige actie van het apparaat, zoals isolatie van apparaten of bestands quarantaine.
- Handmatige e-mail actie, zoals een tijdelijke verwijdering van e-mailberichten. 
- [Geavanceerde jacht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) actie op apparaten of e-mail.
- [Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) -actie voor e-mail inhoud, zoals het verplaatsen van e-mail naar ongewenste e-mail, het verwijderen van e-mail of het permanent verwijderen van e-mail.
- Handmatige actie van [Live antwoord](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response) , zoals het verwijderen van een bestand, het stoppen van een proces en het verwijderen van een geplande taak.
- Actie met Live antwoord met [Microsoft Defender voor eindpunten api's](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis#microsoft-defender-for-endpoint-apis), zoals het isoleren van een apparaat, het uitvoeren van antivirus scans en het verkrijgen van informatie over een bestand. 

## <a name="next-steps"></a>Volgende stappen

- [Naar het Actiecentrum](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [Acties in behandeling goedkeuren of afwijzen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden](mtp-autoir-report-false-positives-negatives.md)
