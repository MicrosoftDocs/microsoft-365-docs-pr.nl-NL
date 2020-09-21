---
title: Negatieve negatieve of onjuiste negatieven in lucht afhandelen in Microsoft Threat Protection
description: Is er iets misgegaan of heeft de verkeerde lucht gedetecteerd in Microsoft Threat Protection? Meer informatie over het indienen van onjuiste of onjuiste negatieven bij Microsoft voor analyse.
keywords: automatisch, onderzoek, waarschuwing, trigger, actie, herstellen, fout positief, negatief negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: ace9ab8e5b73e4a4310b476c8954b0be81faaa66
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962321"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden

**Van toepassing op:**
- Microsoft Threat Protection

Is er [geautomatiseerd onderzoek-en antwoord mogelijkheden](mtp-autoir.md) in Microsoft Threat Protection, of er is iets misgegaan? Er zijn stappen die u kunt uitvoeren om het probleem op te lossen. U kunt:

- [Meld een fout-positief/negatief aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);

- [Pas uw meldingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig). en 

- [Herstelacties die zijn uitgevoerd op apparaten ongedaan maken](#undo-a-remediation-action-that-was-taken-on-a-device). 

Gebruik dit artikel als leidraad. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Meld een fout-positief/negatief aan Microsoft voor analyse

|Item gemist of onjuist gedetecteerd |Service  |Wat moet u doen?  |
|---------|---------|---------|
|-E-mailbericht <br/>-E-mailbijlage <br/>-URL in een e-mailbericht<br/>-URL in een Office-bestand      |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[Verdachte spam, phishing, Url's en bestanden naar Microsoft versturen voor de scan](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|Bestand of app op een apparaat    |[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection)         |[Een bestand bij Microsoft indienen voor het analyseren van malware](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om fout-positieven van herhaling te voorkomen

|Voorbeeld |Service |Wat moet u doen? |
|--------|--------|--------|
|-Een waarschuwing wordt geactiveerd door legitiem gebruik <br/>-Een waarschuwingssignaal klopt niet    |[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security)<br/> of <br/>[Detectie van Azure Advanced Threat](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[Waarschuwingen beheren in de Cloud app Security Portal](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|Een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig|[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) |[Een aangepaste indicator met een actie toestaan maken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a>Een herstelactie ongedaan maken die op een apparaat is uitgevoerd

Als een herstelbewerking is uitgevoerd op een apparaat (zoals een Windows 10-apparaat) en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de actie voor herstel ongedaan maken in het [Actiecentrum](mtp-action-center.md).

> [!IMPORTANT]
> Zorg ervoor dat u de [benodigde machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) hebt voordat u de volgende taak probeert uit te voeren.

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**. 

3. Selecteer op het tabblad **geschiedenis** een actie die u ongedaan wilt maken. Hiermee wordt een flyout geopend.<br/>
    > [!TIP]
    > Filters gebruiken om de lijst met resultaten te verfijnen. 

4. Selecteer in het vervolgmenu voor het geselecteerde item de optie **onderzoek pagina openen**.

5. Selecteer in de weergave Details van onderzoek het tabblad **acties** .

6. Selecteer een item met de status **voltooid**en zoek een koppeling, zoals **goedgekeurd**, in de kolom **besluiten** . Er wordt een flyout geopend met meer informatie over de actie.

7. Als u de actie ongedaan wilt maken, selecteert u **herstel verwijderen**.

## <a name="see-also"></a>Zie ook

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)
- [Ervaring opzeggen met een geavanceerde jacht in Microsoft Threat Protection](advanced-hunting-overview.md)
