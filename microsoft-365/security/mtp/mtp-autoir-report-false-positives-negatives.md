---
title: Onwaar-positieven of fout-negatieven verwerken in AIR in Microsoft 365 Defender
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft 365 Defender? Informatie over het indienen van fout-positieven of fout-negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, trigger, actie, herstel, fout-positief, fout-negatief
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/16/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: dbef240e28258d1ac4000c05538d0ce073a9d910
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930352"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Hebben [geautomatiseerde onderzoeks- en antwoordmogelijkheden](mtp-autoir.md) in Microsoft 365 Defender iets gemist of ten onrechte gedetecteerd? U kunt stappen ondernemen om dit op te lossen. U kunt:

- [Een fout-positief/negatief melden bij Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Pas uw waarschuwingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig); en 

- [Herstelacties ongedaan maken die zijn gemaakt op apparaten.](#undo-a-remediation-action-that-was-taken-on-a-device) 

Gebruik dit artikel als richtlijn. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een fout-positief/negatief rapporteren bij Microsoft voor analyse

|Item gemist of ten onrechte gedetecteerd |Service  |Wat moet u doen?  |
|---------|---------|---------|
|- E-mailbericht <br/>- E-mailbijlage <br/>- URL in een e-mailbericht<br/>- URL in een Office-bestand      |[Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor scannen](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Bestand of app op een apparaat    |[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection)         |[Een bestand bij Microsoft indienen voor malwareanalyse](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

|Scenario |Service |Wat moet u doen? |
|--------|--------|--------|
|- Een waarschuwing wordt geactiveerd door legitiem gebruik <br/>- Een waarschuwing klopt niet    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> of <br/>[Azure Advanced Threat Detection](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Waarschuwingen beheren in de cloud-app-beveiligingsportal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Een bestand, IP-adres, URL of domein wordt op een apparaat beschouwd als malware, ook al is het veilig|[Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) |[Een aangepaste indicator maken met de actie Toestaan](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Een herstelactie ongedaan maken die is ondernomen op een apparaat

Als er een herstelactie is ondernomen op een apparaat (zoals een Windows 10-apparaat) en het item in feite geen bedreiging is, kan uw team voor beveiligingsbewerkingen de herstelactie ongedaan maken in het [Actiecentrum.](mtp-action-center.md)

> [!IMPORTANT]
> Zorg ervoor dat u de [benodigde machtigingen hebt voordat](mtp-action-center.md#required-permissions-for-action-center-tasks) u de volgende taak probeert uit te voeren.

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies Actiecentrum in het **navigatiedeelvenster.** 

3. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken. Er wordt een flyout geopend.<br/>
    > [!TIP]
    > Gebruik filters om de lijst met resultaten te beperken. 

4. Selecteer Onderzoek openen in de flyout voor **het** geselecteerde item.

5. Selecteer in de detailweergave voor onderzoek het **tabblad** Acties.

6. Selecteer een item met de status Voltooid en zoek naar een koppeling, zoals **Goedgekeurd,** in **de** kolom Beslissingen. Hiermee opent u een flyout met meer details over de actie.

7. Als u de actie ongedaan wilt maken, **selecteert u Herstelactie verwijderen.**

## <a name="see-also"></a>Zie ook

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)
- [Proactief zoeken naar bedreigingen met geavanceerd zoeken in Microsoft 365 Defender](advanced-hunting-overview.md)
