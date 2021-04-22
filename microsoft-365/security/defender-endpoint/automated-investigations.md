---
title: Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren
description: Meer informatie over de geautomatiseerde onderzoeksstroom in Microsoft Defender voor Eindpunt.
keywords: geautomatiseerd, onderzoek, detectie, Microsoft Defender voor Eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 5ea869d4016cc794b3046a664c1519f6b3250c67
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933971"
---
# <a name="overview-of-automated-investigations"></a>Overzicht van geautomatiseerde onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Wilt u zien hoe het werkt? Bekijk de volgende video: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

De technologie in geautomatiseerd onderzoek maakt gebruik van verschillende inspectiealgoritmen en is gebaseerd op processen die worden gebruikt door beveiligingsanalisten. Air-mogelijkheden zijn ontworpen om waarschuwingen te onderzoeken en onmiddellijk actie te ondernemen om inbreuken op te lossen. Air-mogelijkheden verminderen het alarmvolume aanzienlijk, zodat beveiligingsbewerkingen zich kunnen richten op geavanceerdere bedreigingen en andere hoogwaardige initiatieven. Alle herstelacties, in behandeling of voltooid, worden bijgeplaatst in het [Actiecentrum.](auto-investigation-action-center.md) In het Actiecentrum worden acties in behandeling goedgekeurd (of geweigerd) en kunnen voltooide acties zo nodig ongedaan worden gemaakt.

Dit artikel bevat een overzicht van AIR en bevat koppelingen naar de volgende stappen en aanvullende bronnen.

> [!TIP]
> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>Hoe het geautomatiseerde onderzoek begint

Een geautomatiseerd onderzoek kan beginnen wanneer een waarschuwing wordt geactiveerd of wanneer een beveiligingsoperator het onderzoek start.

|Situatie  |Wat gebeurt er?  |
|---------|---------|
|Er wordt een waarschuwing geactiveerd     | In het algemeen wordt een geautomatiseerd onderzoek gestart wanneer een [waarschuwing](review-alerts.md) wordt geactiveerd en er een [incident](view-incidents-queue.md) wordt gemaakt. Stel dat een schadelijk bestand zich op een apparaat bevindt. Wanneer dat bestand wordt gedetecteerd, wordt er een waarschuwing geactiveerd en wordt een incident gemaakt. Er wordt een geautomatiseerd onderzoek gestart op het apparaat. Aangezien andere waarschuwingen worden gegenereerd vanwege hetzelfde bestand op andere apparaten, worden ze toegevoegd aan het bijbehorende incident en aan het geautomatiseerde onderzoek.         |
|Er wordt handmatig een onderzoek gestart     | Een geautomatiseerd onderzoek kan handmatig worden gestart door uw beveiligingsteam. Stel dat een beveiligingsoperator een lijst met apparaten bekijkt en merkt dat een apparaat een hoog risiconiveau heeft. De beveiligingsoperator kan het apparaat in de lijst selecteren om de flyout te openen en vervolgens Automatisch onderzoek **starten te selecteren.** |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Hoe het bereik van een geautomatiseerd onderzoek wordt uitgebreid

Terwijl een onderzoek wordt uitgevoerd, worden alle andere waarschuwingen die van het apparaat worden gegenereerd, toegevoegd aan een lopend geautomatiseerd onderzoek totdat dat onderzoek is voltooid. Bovendien worden deze apparaten toegevoegd aan het onderzoek als dezelfde bedreiging op andere apparaten wordt gezien.

Als een belastende entiteit wordt gezien op een ander apparaat, wordt het geautomatiseerde onderzoeksproces uitgebreid met dat apparaat en wordt een algemene beveiligingss playbook gestart op dat apparaat. Als er tijdens dit uitbreidingsproces 10 of meer apparaten uit dezelfde entiteit worden gevonden, moet deze uitbreidingsactie worden goedgekeurd en is deze zichtbaar op het tabblad Acties in **behandeling.**

## <a name="how-threats-are-remediated"></a>Hoe bedreigingen worden gesaneerd

Wanneer waarschuwingen worden geactiveerd en een geautomatiseerd onderzoek wordt uitgevoerd, wordt een vonnis gegenereerd voor elk bewijs dat wordt onderzocht. Vonnissen kunnen worden 
- *Schadelijk*;
- *Verdacht*; of 
- *Er zijn geen bedreigingen gevonden.* 

Wanneer vonnissen worden bereikt, kunnen geautomatiseerde onderzoeken leiden tot een of meer herstelacties. Voorbeelden van herstelacties zijn het verzenden van een bestand naar quarantaine, het stoppen van een service, het verwijderen van een geplande taak en meer. Zie Herstelacties [voor meer informatie.](manage-auto-investigation.md#remediation-actions)  

Afhankelijk van het automatiseringsniveau dat is ingesteld voor uw organisatie en andere beveiligingsinstellingen, kunnen herstelacties automatisch [of](automation-levels.md) alleen plaatsvinden na goedkeuring door uw beveiligingsbewerkingsteam. Extra beveiligingsinstellingen die van invloed kunnen zijn op automatische herstelmaatregelen, zijn onder andere bescherming tegen mogelijk [ongewenste toepassingen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA). 

Alle herstelacties, in behandeling of voltooid, worden bijgeplaatst in het [Actiecentrum.](auto-investigation-action-center.md) Zo nodig kan uw beveiligingsbewerkingsteam een herstelactie ongedaan maken. Zie Herstelacties controleren en goedkeuren na een geautomatiseerd onderzoek voor meer [informatie.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> Bekijk de nieuwe, geïntegreerde onderzoekspagina in het Microsoft 365-beveiligingscentrum. Zie [(NIEUW!) voor meer informatie. Geïntegreerde onderzoekspagina](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Vereisten voor AIR

Uw organisatie moet Defender voor Eindpunt hebben (zie [Minimumvereisten voor Microsoft Defender voor Eindpunt](minimum-requirements.md)).

Op dit moment ondersteunt AIR alleen de volgende besturingssysteemversies:
- Windows Server 2019
- Windows 10, versie 1709 (os build 16299.1085 met [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) of hoger
- Windows 10, versie 1803 (os build 17134.704 met [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) of hoger
- Windows 10, versie [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) of hoger

## <a name="next-steps"></a>Volgende stappen

- [Meer informatie over automatiseringsniveaus](automation-levels.md)
- [Zie de interactieve handleiding: Bedreigingen onderzoeken en corrigeren met Microsoft Defender voor Eindpunt](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Geautomatiseerde onderzoeks- en herstelmogelijkheden configureren in Microsoft Defender voor Eindpunt](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Zie ook

- [PUA-beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
