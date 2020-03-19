---
title: Geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection
description: Krijg een overzicht van geautomatiseerde onderzoeks- en responsmogelijkheden in Microsoft Threat Protection
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering
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
ms.openlocfilehash: f7ae1a285e22ad18d292d37aab0bba0b4a441461
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857449"
---
# <a name="automated-investigation-and-response-air-capabilities-in-microsoft-threat-protection"></a>Automatische onderzoeks- en responsmogelijkheden (AIR) in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Als beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen. Prioriteren en onderzoeken van waarschuwingen kan zeer tijdrovend zijn, vooral wanneer nieuwe waarschuwingen blijven komen terwijl een onderzoek gaande is. Teams van beveiligingsoperaties kunnen zich overweldigd voelen door de enorme hoeveelheid bedreigingen die ze moeten controleren en beschermen tegen. De mogelijkheden voor geautomatiseerd onderzoek en respons (AIR) in Microsoft Threat Protection kunnen u helpen. AIR is als het hebben van een virtuele analist in uw security operations center.

## <a name="your-virtual-analyst"></a>Uw virtuele analist

Stel je voor dat je een virtuele analist hebt in je Tier 1/ Tier 2 security operations team. De virtuele analist bootst de ideale stappen na die beveiligingsoperaties zouden nemen om bedreigingen te onderzoeken en te verhelpen. De virtuele assistent zou kunnen werken 24x7, met onbeperkte capaciteit, en nemen op een aanzienlijke belasting van onderzoeken en bedreiging saneren. Zo'n virtuele assistent kan de tijd om te reageren aanzienlijk verkorten, waardoor uw beveiligingsteam vrijkomt voor andere belangrijke strategische projecten. Als dit scenario klinkt als science fiction, is het niet! Zo'n virtuele analist maakt deel uit van uw Microsoft Threat Protection-suite en de naam is *geautomatiseerd onderzoek en respons* (AIR).

AIR stelt uw beveiligingsteam in staat om de capaciteit van uw organisatie om beveiligingswaarschuwingen en incidenten aan te pakken drastisch te vergroten. Met AIR u de kosten van het omgaan met onderzoeks- en herstelactiviteiten verlagen en het meeste uit uw suite voor bedreigingsbeveiliging halen. AIR helpt uw team voor beveiligingsoperaties door:

1. Bepalen of een bedreiging actie vereist;
2. Het uitvoeren (of aanbevelen) van de nodige saneringsacties;
3. Bepalen welke aanvullende onderzoeken moeten plaatsvinden; En
4. Het proces herhalen als dat nodig is voor andere waarschuwingen.

## <a name="the-automated-investigation-process"></a>Het geautomatiseerde onderzoeksproces

**Alert** > **incident** > **geautomatiseerdonderzoek** > **vonnis** > sanering**actie**

Een geactiveerde waarschuwing zorgt voor een incident, dat een geautomatiseerd onderzoek kan starten. Dat onderzoek kan leiden tot een of meer saneringsacties. In Microsoft Threat Protection correleert elk geautomatiseerd onderzoek signalen voor Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) en Office 365 Advanced Threat Protection (Office 365 ATP), zoals samengevat in de volgende tabel: 

|Entiteiten |Diensten ter bescherming van bedreigingen  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mailinhoud (bestanden en berichten in postvakken)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Elk onderzoek genereert vonnissen (*Kwaadaardig,* *Verdacht,* of *Schoon*) voor elk stuk van het onderzochte bewijs. Afhankelijk van het type bedreiging en het resulterende vonnis vinden herstelacties automatisch of na goedkeuring plaats door het beveiligingsteam van uw organisatie. Hangende en voltooide acties worden weergegeven in het [actiecentrum](mtp-action-center.md).

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerd onderzoek en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe valse positieven /negatieven in geautomatiseerde onderzoeks- en responsmogelijkheden (AIR)](mtp-autoir-report-false-positives-negatives.md)in Microsoft Threat Protection worden gemeld.

Terwijl een onderzoek wordt uitgevoerd, worden alle andere gerelateerde waarschuwingen die zich voordoen toegevoegd aan het onderzoek totdat het is voltooid. Als een belastende entiteit elders wordt gezien, breidt het geautomatiseerde onderzoek het toepassingsgebied uit met die entiteit en wordt een algemeen beveiligingsplaybook uitgevoerd. 

> [!NOTE]
> Niet elke waarschuwing activeert een geautomatiseerd onderzoek, en niet elk onderzoek resulteert in geautomatiseerde saneringsacties; dit hangt allemaal af van hoe AIR is geconfigureerd voor uw organisatie. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Vereisten voor AIR in Microsoft Threat Protection

| | |
|--|--|
|Abonnementsvereisten |Een van de volgende: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5-beveiliging<br/>- Microsoft 365 A5-beveiliging<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Zie [licentievereisten](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)voor Microsoft Threat Protection .|
|Netwerkvereisten |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) (MCAS) geconfigureerd<br/>- [MCAS geïntegreerd met Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-machinevereisten |- Windows 10, versie 1709 of hoger geïnstalleerd (Zie [Windows 10-releasegegevens)](https://docs.microsoft.com/windows/release-information/)met de volgende services voor bedreigingsbeveiliging die zijn geconfigureerd:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Bescherming voor e-mailinhoud en Office-bestanden |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) geconfigureerd |
|Machtigingen |- Als u AIR wilt configureren, moet de rol Globale beheerder[https://portal.azure.com](https://portal.azure.com)of Beveiligingsbeheerder zijn toegewezen in[https://admin.microsoft.com](https://admin.microsoft.com)Azure Active Directory ( ) of in het Microsoft 365-beheercentrum ( ).<br/><br/>- Zie Vereiste machtigingen [voor actiecentrumtaken](mtp-action-center.md#required-permissions-for-action-center-tasks)voor air-mogelijkheden als u AIR-mogelijkheden wilt gebruiken. |

## <a name="next-steps"></a>Volgende stappen

- [Acties in verband met geautomatiseerd onderzoek en respons goedkeuren of afwijzen](mtp-autoir-actions.md)
- [Meer informatie over het actiecentrum](mtp-action-center.md)
