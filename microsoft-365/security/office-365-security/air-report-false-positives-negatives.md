---
title: Fout-positieven of fout-negatieven rapporteren na geautomatiseerd onderzoek in Microsoft Defender voor Office 365
description: Is er iets gemist of ten onrechte gedetecteerd door AIR in Microsoft Defender voor Office 365? Informatie over het indienen van fout-positieven of fout-negatieven bij Microsoft voor analyse.
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
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 48d7e1a7497f9bc2a07a84b36fb07939d25609bf
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289147"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als functies voor automatisch onderzoek en reactie [(AIR) in Office 365](automated-investigation-response-office.md) iets hebben gemist of onjuist zijn gedetecteerd, zijn er stappen die uw team voor beveiligingsbewerkingen kan nemen om dit op te lossen. Dergelijke acties zijn:

- [Een fout-positief/negatief rapporteren aan Microsoft;](#report-a-false-positivenegative-to-microsoft-for-analysis)
- [Waarschuwingen aanpassen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (indien nodig); en
- [Herstelacties ongedaan maken die zijn gemaakt.](#undo-a-remediation-action)

Gebruik dit artikel als richtlijn.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een fout-positief/negatief rapporteren bij Microsoft voor analyse

Als AIR in Microsoft Defender voor Office 365 een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, kunt u verdachte spam, phish, URL's en bestanden verzenden naar Microsoft voor het scannen van [Office 365.](admin-submission.md)

U kunt ook [een bestand naar Microsoft verzenden voor malwareanalyse.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat fout-positieven terugkeren

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u [waarschuwingen beheren in de cloud-app-beveiligingsportal.](https://docs.microsoft.com/cloud-app-security/managing-alerts)

Als uw organisatie naast Office 365 gebruik maakt van [Microsoft Defender for Endpoint,](https://docs.microsoft.com/windows/security/threat-protection) en een bestand, IP-adres, URL of domein op een apparaat wordt beschouwd als malware, zelfs als dit veilig is, kunt u een aangepaste indicator maken met de actie Toestaan [voor](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)uw apparaat.

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

In de meeste gevallen, als er een herstelactie is ondernomen voor een e-mailbericht, e-mailbijlage of URL en het item is eigenlijk geen bedreiging, kan uw team voor beveiligingsbewerkingen de herstelactie ongedaan maken en stappen uitvoeren om te voorkomen dat het fout-positieve punt terugkeren. U kunt [Bedreigingsverkenner of](#undo-an-action-using-threat-explorer) het [tabblad Acties gebruiken voor een onderzoek om](#undo-an-action-in-the-action-center) een actie ongedaan te maken.

> [!IMPORTANT]
> Zorg ervoor dat u de benodigde machtigingen hebt voordat u de volgende taken uitvoert.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met Bedreigingsverkenner

Met Bedreigingsverkenner kan het team voor beveiligingsbewerkingen een e-mailbericht vinden dat is beïnvloed door een actie en de actie mogelijk ongedaan maken.

|Scenario|Opties voor ongedaan maken|Meer informatie|
|---|---|---|
|Een e-mailbericht is omgeleid naar de map Ongewenste e-mail van een gebruiker|- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker<br/>- Het bericht verplaatsen naar het Postvak IN van de gebruiker<br/>- Het bericht verwijderen|[Schadelijke e-mail zoeken en onderzoeken die is afgeleverd in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Een e-mailbericht of bestand is in quarantaine geplaatst|- Het e-mailbericht of bestand vrijgeven<br/>- Het e-mailbericht of bestand verwijderen|[Berichten in quarantaine beheren als beheerder](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a>Een actie ongedaan maken in het Actiecentrum

In het Actiecentrum kunt u herstelacties zien die zijn ondernomen en de actie mogelijk ongedaan maken.

1. Ga naar het Microsoft 365-beveiligingscentrum ( [https://security.microsoft.com](https://security.microsoft.com) ).
2. Selecteer Actiecentrum in het **navigatiedeelvenster.** 
3. Selecteer het **tabblad Geschiedenis** om de lijst met voltooide acties te bekijken.
4. Selecteer een item. Het deelvenster flyout wordt geopend. 
5. Selecteer Ongedaan maken in het deelvenster Flyout. (Alleen acties die ongedaan kunnen worden gemaakt, hebben een **knop Ongedaan** maken.)

## <a name="see-also"></a>Zie ook

- [Microsoft Defender voor Office 365](office-365-atp.md)
- [Automatische onderzoeken in Microsoft Defender voor Office 365](office-365-air.md)
