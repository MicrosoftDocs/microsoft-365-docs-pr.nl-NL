---
title: Fout-positieven of onwaar negatieven in Microsoft 365 Defender
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft 365 Defender? Meer informatie over het indienen van fout-positieven of onwaar negatieven bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, waarschuwing, herstel, onwaar positief, onwaar negatief
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 3cffa97d26b2b28de8d9e45d7030e0931a7ba072
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269574"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a>Fout-positieven of onwaar negatieven in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

Onwaar positieven of negatieven kunnen af en toe optreden met een bedreigingsbeveiligingsoplossing. Als [geautomatiseerde onderzoeks- en antwoordmogelijkheden](m365d-autoir.md) in Microsoft 365 defender iets hebben gemist of ten onrechte zijn gedetecteerd, zijn er stappen die uw beveiligingsteam kan uitvoeren:

- [Een onwaar positief/negatief melden bij Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Uw waarschuwingen aanpassen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig)
- [Herstelacties ongedaan maken die zijn genomen op apparaten](#undo-a-remediation-action-that-was-taken-on-a-device)

In de volgende secties wordt beschreven hoe u deze taken uitvoert.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een onwaar positief/negatief melden bij Microsoft voor analyse

|Item gemist of ten onrechte gedetecteerd |Service  |Wat moet u doen?  |
|---------|---------|---------|
|- E-mailbericht <br/>- E-mailbijlage <br/>- URL in een e-mailbericht<br/>- URL in een Office bestand      |[Microsoft Defender voor Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)        |[Verdachte spam, phish, URL's en bestanden indienen bij Microsoft voor scannen](../office-365-security/admin-submission.md)         |
|Bestand of app op een apparaat    |[Microsoft Defender voor Eindpunt](/windows/security/threat-protection)         |[Een bestand indienen bij Microsoft voor malwareanalyse](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

|Scenario |Service |Wat moet u doen? |
|--------|--------|--------|
|- Een waarschuwing wordt geactiveerd door legitiem gebruik <br/>- Een waarschuwing is onjuist    |[Microsoft Cloud App Security](/cloud-app-security)<br/> of <br/>[Beveiliging van Azure-bedreigingen](/azure/security/fundamentals/threat-detection)         |[Waarschuwingen beheren in de Cloud App Security portal](/cloud-app-security/managing-alerts)         |
|Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig|[Microsoft Defender voor Eindpunt](/windows/security/threat-protection) |[Een aangepaste indicator maken met de actie Toestaan](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Een herstelactie ongedaan maken die is ondernomen op een apparaat

Als er een herstelactie is uitgevoerd op een entiteit (zoals een apparaat of een e-mailbericht) en de betreffende entiteit geen bedreiging is, kan uw beveiligingsteam de herstelactie ongedaan maken in het [Actiecentrum.](m365d-action-center.md)

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 
2. Kies actiecentrum in het **navigatiedeelvenster.** 
3. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken. Het deelvenster Flyout wordt geopend.
4. Selecteer ongedaan maken in het deelvenster Flyout.

> [!TIP]
> Zie [Voltooide acties ongedaan maken.](m365d-autoir-actions.md#undo-completed-actions)

## <a name="see-also"></a>Zie ook

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](m365d-autoir-results.md)
- [Proactief op bedreigingen zoeken met geavanceerde Microsoft 365 Defender](advanced-hunting-overview.md)
- [Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)