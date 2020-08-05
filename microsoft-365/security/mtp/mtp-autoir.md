---
title: Geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection
description: Een overzicht krijgen van geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection
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
ms.openlocfilehash: c45b7d1b01ee776e9519d67ee52d36b8f48bf0ef
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552352"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection

**Van toepassing op:**
- Microsoft Threat Protection

Aangezien beveiligingswaarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te bekijken en stappen te ondernemen om uw organisatie te beschermen. Het prioriteren en onderzoeken van waarschuwingen kan zeer tijdrovend zijn, vooral wanneer er nieuwe waarschuwingen binnenkomen terwijl er een onderzoek loopt. Beveiligingsteams kunnen zich overweldigd voelen door de enorme hoeveelheid bedreigingen die ze moeten controleren en waartegen ze zich moeten beschermen. Geautomatiseerde onderzoeks- en reactiemogelijkheden (ook wel *geautomatiseerde zelfherstellende* mogelijkheden genoemd) in Microsoft Threat Protection kunnen helpen. 

Bekijk de volgende video om te zien hoe geautomatiseerde zelfhelende mogelijkheden werken:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

Geautomatiseerd onderzoek en reactie is als het hebben van een virtuele analist in uw security operations center.

## <a name="your-virtual-analyst"></a>Uw virtuele analist

Stel je voor dat je een virtuele analist hebt in je Tier 1 / Tier 2 security operations team. De virtuele analist bootst de ideale stappen na die beveiligingsoperaties zouden nemen om bedreigingen te onderzoeken en te herstellen. De virtuele assistent zou kunnen werken 24x7, met onbeperkte capaciteit, en nemen op een aanzienlijke belasting van onderzoeken en bedreiging sanering. Zo'n virtuele assistent kan de tijd om te reageren aanzienlijk verkorten, waardoor uw beveiligingsteam vrij komt voor andere belangrijke strategische projecten. Als dit scenario klinkt als science fiction, is het niet! Zo'n virtuele analist maakt deel uit van uw Microsoft Threat Protection-suite en de naam is *geautomatiseerd onderzoek en reactie.*

Geautomatiseerd onderzoek en respons stelt uw beveiligingsteam in staat om de capaciteit van uw organisatie om beveiligingswaarschuwingen en -incidenten aan te pakken drastisch te vergroten. Met geautomatiseerd onderzoek en respons u de kosten van het omgaan met onderzoeks- en saneringsactiviteiten verlagen en het meeste uit uw suite voor bedreigingsbescherming halen. geautomatiseerd onderzoek en respons helpt uw security operations team door:

1. Bepalen of een bedreiging actie vereist;
2. Het uitvoeren (of aanbevelen) van de nodige saneringsacties;
3. Bepalen welke aanvullende onderzoeken moeten plaatsvinden; En
4. Het proces herhalen indien nodig voor andere waarschuwingen.

## <a name="the-automated-investigation-process"></a>Het geautomatiseerde onderzoeksproces

**Waarschuwing**  >  **incident**  >  **geautomatiseerd onderzoek**  >  **vonnis**  >  **saneringsactie**

Een geactiveerde waarschuwing creëert een incident, dat een geautomatiseerd onderzoek kan starten. Dat onderzoek kan leiden tot een of meer saneringsacties. In Microsoft Threat Protection correleert elk geautomatiseerd onderzoek signalen in Azure Advanced Threat Protection (Azure ATP), Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) en Office 365 Advanced Threat Protection (Office 365 ATP), zoals samengevat in de volgende tabel: 

|Entiteiten |Diensten voor bedreigingsbescherming  |
|---------|---------|
|Apparaten (ook wel eindpunten genoemd)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|E-mailinhoud (bestanden en berichten in postvakken)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

Elk onderzoek genereert vonnissen (*Kwaadaardig*, *Verdacht*, of *geen bedreigingen gevonden*) voor elk stuk van het onderzochte bewijs. Afhankelijk van het type bedreiging en het daaruit voortvloeiende vonnis, worden herstelacties automatisch of na goedkeuring door het beveiligingsteam van uw organisatie uitgevoerd. In behandeling zijnde en voltooide acties vermeld in het [Actiecentrum](mtp-action-center.md).

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe foutieve positieven/negatieven te rapporteren in geautomatiseerde onderzoeks- en reactiemogelijkheden in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).

Terwijl een onderzoek wordt uitgevoerd, worden alle andere gerelateerde waarschuwingen die zich voordoen toegevoegd aan het onderzoek totdat het is voltooid. Als een belastende entiteit elders wordt gezien, zal het geautomatiseerde onderzoek zijn werkingssfeer uitbreiden met die entiteit en wordt een algemeen beveiligingsspeelboek uitgevoerd. 

> [!NOTE]
> Niet elke waarschuwing leidt tot een geautomatiseerd onderzoek, en niet elk onderzoek resulteert in geautomatiseerde saneringsacties; dit hangt allemaal af van hoe geautomatiseerd onderzoek en reactie is geconfigureerd voor uw organisatie. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Vereisten voor geautomatiseerd onderzoek en respons in Microsoft Threat Protection

|Vereiste |Details |
|--|--|
|Abonnementsvereisten |Een van de volgende: <br/>- Microsoft 365 E5 <br/>- Microsoft 365 A5 <br/>- Microsoft 365 E5 Beveiliging<br/>- Microsoft 365 A5-beveiliging<br/>- Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>Zie [Microsoft Threat Protection-licentievereisten](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements).|
|Netwerkvereisten |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) ingeschakeld<br/>- [McAS (Microsoft Cloud App Security)](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) geconfigureerd<br/>- [MCAS geïntegreerd met Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows-machinevereisten |- Windows 10, versie 1709 of hoger geïnstalleerd (Zie [Windows 10 release informatie](https://docs.microsoft.com/windows/release-information/)) met de volgende bedreiging bescherming diensten geconfigureerd:<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|Beveiliging voor e-mailinhoud en Office-bestanden |[Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) geconfigureerd |
|Machtigingen |- Als u geautomatiseerd onderzoek en antwoord wilt configureren, moet de rol Global Administrator of Security Administrator zijn toegewezen in Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) of in het Microsoft 365-beheercentrum ( [https://admin.microsoft.com](https://admin.microsoft.com) ).<br/><br/>- Zie [Vereiste machtigingen voor action center-taken voor](mtp-action-center.md#required-permissions-for-action-center-tasks)geautomatiseerde onderzoeks- en reactiemogelijkheden. |

## <a name="next-steps"></a>Volgende stappen

- [Acties met betrekking tot geautomatiseerd onderzoek en reactie goedkeuren of afwijzen](mtp-autoir-actions.md)
- [Meer informatie over het Actiecentrum](mtp-action-center.md)
