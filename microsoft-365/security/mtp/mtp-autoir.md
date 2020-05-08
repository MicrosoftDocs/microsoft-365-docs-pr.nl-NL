---
title: Geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection
description: Krijg een overzicht van geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel
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
ms.openlocfilehash: 6ac6d74b027cc533f689c1d67c7fce246c73984f
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44166159"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Geautomatiseerde air-mogelijkheden (Investigation and Response) in Microsoft Threat Protection

**Geldt voor:**
- Microsoft Threat Protection

Als beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen. Het prioriteren en onderzoeken van waarschuwingen kan zeer tijdrovend zijn, vooral wanneer er steeds nieuwe waarschuwingen binnenkomen terwijl er een onderzoek gaande is. Beveiligingsteams kunnen zich overweldigd voelen door de enorme hoeveelheid bedreigingen die ze moeten controleren en beschermen tegen. Automatische air-mogelijkheden (Investigation and Response) in Microsoft Threat Protection kunnen u helpen. AIR is als het hebben van een virtuele analist in uw security operations center.

## <a name="your-virtual-analyst"></a>Uw virtuele analist

Stel je voor dat je een virtuele analist in je Tier 1 / Tier 2 security operations team hebt. De virtuele analist bootst de ideale stappen na die beveiligingsoperaties zouden nemen om bedreigingen te onderzoeken en te verhelpen. De virtuele assistent zou 24x7 kunnen werken, met onbeperkte capaciteit, en een aanzienlijke belasting van onderzoeken en bedreigingsherstel kunnen aannemen. Zo'n virtuele assistent kan de reactietijd aanzienlijk verkorten, waardoor uw beveiligingsteam vrijkomt voor andere belangrijke strategische projecten. Als dit scenario klinkt als science fiction, is het niet! Zo'n virtuele analist maakt deel uit van uw Microsoft Threat Protection-suite en de naam is *geautomatiseerd onderzoek en respons* (AIR).

AIR stelt uw beveiligingsteam in staat om de capaciteit van uw organisatie om beveiligingswaarschuwingen en incidenten aan te pakken aanzienlijk te vergroten. Met AIR u de kosten van het omgaan met onderzoeks- en herstelactiviteiten verlagen en het meeste uit uw bedreigingsbeschermingssuite halen. AIR helpt uw beveiligingsteam door:

1. Bepalen of een bedreiging actie vereist;
2. Het uitvoeren (of aanbevelen) van de nodige herstelacties;
3. Bepalen welke aanvullende onderzoeken moeten plaatsvinden; En
4. Het proces herhalen als dat nodig is voor andere waarschuwingen.

## <a name="the-automated-investigation-process"></a>Het geautomatiseerde onderzoeksproces

**Alert** > **incident** > **geautomatiseerd onderzoek** > **vonnis** > sanering**actie**

Een geactiveerde waarschuwing zorgt voor een incident, dat een geautomatiseerd onderzoek kan starten. Dat onderzoek kan leiden tot een of meer saneringsacties. In Microsoft Threat Protection correleert elk geautomatiseerd onderzoek signalen in Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) en Office 365 Advanced Threat Protection (Office 365 ATP), zoals samengevat in de volgende tabel: 

|Entiteiten |Diensten voor bedreigingsbescherming  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mailinhoud (bestanden en berichten in postvakken)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Elk onderzoek genereert vonnissen (*Kwaadaardig*, *Verdacht*, of *Geen bedreigingen gevonden*) voor elk stuk van het bewijs onderzocht. Afhankelijk van het type bedreiging en de daaruit voortvloeiende uitspraak, worden herstelacties automatisch of na goedkeuring door het beveiligingsteam van uw organisatie uitgevoerd. In behandeling zijnde en voltooide acties worden weergegeven in het [actiecentrum](mtp-action-center.md).

> [!TIP]
> Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe valse positieven/negatieven in geautomatiseerde onderzoeks- en reactiemogelijkheden (AIR) kunnen worden gemeld in Microsoft Threat Protection.](mtp-autoir-report-false-positives-negatives.md)

Terwijl een onderzoek wordt uitgevoerd, worden alle andere gerelateerde waarschuwingen die zich voordoen aan het onderzoek toegevoegd totdat het is voltooid. Als een belastende entiteit elders wordt gezien, zal het geautomatiseerde onderzoek het toepassingsgebied uitbreiden tot die entiteit en wordt een algemeen beveiligingsplaybook uitgevoerd. 

> [!NOTE]
> Niet elke waarschuwing leidt tot een geautomatiseerd onderzoek, en niet elk onderzoek resulteert in geautomatiseerde herstelacties; Dit hangt allemaal af van hoe AIR is geconfigureerd voor uw organisatie. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Vereisten voor AIR in Microsoft Threat Protection

| | |
|--|--|
|Abonnementsvereisten |Een van de volgende opties: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5-beveiliging<br/>- Microsoft 365 A5 Beveiliging<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Zie [licentievereisten voor Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netwerkvereisten |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [McAS (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) geconfigureerd<br/>- [MCAS geïntegreerd met Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-machinevereisten |- Windows 10, versie 1709 of hoger geïnstalleerd (Zie [Windows 10 release informatie)](https://docs.microsoft.com/windows/release-information/)met de volgende threat protection services geconfigureerd:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Beveiliging voor e-mailinhoud en Office-bestanden |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) geconfigureerd |
|Machtigingen |- Als u AIR wilt configureren, moet u de rol Globale[https://portal.azure.com](https://portal.azure.com)beheerder of beveiligingsbeheerder hebben toegewezen[https://admin.microsoft.com](https://admin.microsoft.com)in Azure Active Directory ( ) of in het Microsoft 365-beheercentrum ( ).<br/><br/>- Zie Vereiste machtigingen [voor Action Center-taken](mtp-action-center.md#required-permissions-for-action-center-tasks)als u AIR-mogelijkheden wilt gebruiken. |

## <a name="next-steps"></a>Volgende stappen

- [Acties met betrekking tot geautomatiseerd onderzoek en antwoord goedkeuren of afwijzen](mtp-autoir-actions.md)
- [Meer informatie over het actiecentrum](mtp-action-center.md)
