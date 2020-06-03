---
title: Valse positieven of false negatives melden in geautomatiseerd onderzoek en reactie van Office 365
description: Is er iets gemist of ten onrechte gedetecteerd door Office 365 Advanced Threat Protection? Meer informatie over het indienen van false positives of false negatives bij Microsoft voor analyse.
keywords: geautomatiseerd, onderzoek, alert, trigger, actie, sanering, vals positief, vals negatief
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 837232550ca392a364b9842f64a1c3f0d790a502
ms.sourcegitcommit: 33be6075fcc89d4c0a48fa7e59f3b3ebc605d9f3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2020
ms.locfileid: "44520156"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Valse positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en reactiemogelijkheden

**Van toepassing op:**
- Office 365 Advanced Threat Protection

Hebben [geautomatiseerde mogelijkheden voor onderzoek en respons (AIR) in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) iets gemist of ten onrechte gedetecteerd? Er zijn stappen die u nemen om het te repareren. U kunt:
- [Een false positive/negatief melden aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Pas uw waarschuwingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig); En 
- [Herstelacties ongedaan maken die zijn uitgevoerd](#undo-a-remediation-action). 

Gebruik dit artikel als een gids. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Een false positive/negatief melden aan Microsoft voor analyse

Als Office 365 AIR een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, u [vermoedelijke spam, phish, URL's en bestanden verzenden naar Microsoft voor office 365-scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

U ook [een bestand indienen bij Microsoft voor malware-analyse.](https://www.microsoft.com/wdsi/filesubmission)

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om te voorkomen dat false positives zich herhalen

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, u [waarschuwingen beheren in de Cloud App Security-portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Als uw organisatie naast Office 365 [ook Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) gebruikt en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook al is het veilig, u een aangepaste indicator maken met een actie ['Toestaan' voor uw apparaat.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

In de meeste gevallen kan uw beveiligingsteam de herstelactie ongedaan maken als er een herstelactie is ondernomen op een e-mailbericht, e-mailbijlage of URL en het item eigenlijk geen bedreiging vormt, dan kan uw beveiligingsteam de herstelactie ongedaan maken en stappen ondernemen om te voorkomen dat het fout-positieve zich opnieuw voordoet. U [Threat Explorer](#undo-an-action-using-threat-explorer) of het tabblad Acties gebruiken [voor een onderzoek](#undo-an-action-using-the-actions-tab-for-an-investigation) om een actie ongedaan te maken. 

> [!IMPORTANT]
> Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u de volgende taken probeert uit te voeren.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met Threat Explorer

Met Threat Explorer kan uw beveiligingsteam een e-mail vinden die door een actie is beïnvloed en de actie mogelijk ongedaan maken.

|Scenario  |Ongedaan maken Opties  |Meer informatie |
|---------|---------|---------|
|Een e-mailbericht is doorgestuurd naar de map Ongewenste e-mail van een gebruiker     |- Het bericht verplaatsen naar de map Verwijderde items van de gebruiker<br/>- Het bericht verplaatsen naar het Postvak IN van de gebruiker <br/>- Het bericht verwijderen          |[Schadelijke e-mail zoeken en onderzoeken die is geleverd in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|Een e-mailbericht of een bestand is in quarantaine geplaatst     |- De e-mail of het bestand vrijgeven <br/>- De e-mail of het bestand verwijderen         |[Berichten en bestanden in quarantaine beheren als beheerder in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Een actie ongedaan maken met het tabblad Handelingen voor een onderzoek

In het Centrum van Het Actie u herstelacties zien die zijn uitgevoerd en de actie mogelijk ongedaan maken.

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld je aan. Dit brengt u naar het Security & Compliance Center.

2. Ga naar **Threat management**  >  **Investigations**.

3. Selecteer in de lijst met onderzoeken het pictogram **Openen in een nieuw venster** naast de id van een item.

4. Selecteer het tabblad **Handelingen.**

5. Selecteer een item met de status **Voltooid**en zoek naar een koppeling, zoals **Goedgekeurd,** in de kolom **Besluit.** Dit opent een flyout met meer details over de actie.

6. Als u de actie ongedaan wilt maken, selecteert u **Herstel verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Aan de slag met Geautomatiseerd onderzoek en antwoord (AIR) in Office 365](office-365-air.md)
