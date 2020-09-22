---
title: Onjuiste of onjuiste negatieven rapporteren in Office 365 automatisch onderzoek en antwoord
description: Is er een fout opgetreden bij een gemiste of onjuiste detectie van Office 365 Advanced Threat Protection? Meer informatie over het indienen van onjuiste of onjuiste negatieven bij Microsoft voor analyse.
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 66b81a474ff81df57c0b2a59672b17061f7235cb
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196073"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Onjuiste positief en negatief rapporteren in automatisch onderzoek en antwoord mogelijkheden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Van toepassing op:**
- Office 365 Advanced Threat Protection

Is er [geautomatiseerd onderzoek-en antwoord mogelijkheden in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) mis of er is iets misgegaan? Er zijn stappen die u kunt uitvoeren om het probleem op te lossen. U kunt:
- [Meld een fout-positief/negatief aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Pas uw meldingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig). en 
- [Herstelbewerkingen die zijn uitgevoerd, ongedaan maken](#undo-a-remediation-action). 

Gebruik dit artikel als leidraad. 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Meld een fout-positief/negatief aan Microsoft voor analyse

Als Office 365 AIR een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand mist, kunt u [verdachte spam, phishing, url's en bestanden versturen naar Microsoft voor Office 365 scan](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

U kunt ook [een bestand bij Microsoft indienen voor de analyse van malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om fout-positieven van herhaling te voorkomen

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u [waarschuwingen beheren in de portal van de Cloud-app](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Als in uw organisatie behalve Office 365 niet alleen Office [wordt gebruikt en](https://docs.microsoft.com/windows/security/threat-protection) een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, kunt u [een aangepaste indicator maken met een actie toestaan voor uw apparaat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators), ook als dit veilig is.

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

In de meeste gevallen geldt dat als een herstelactie is ondernomen voor een e-mailbericht, e-mailbijlage of URL, en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de actie ongedaan maken en stappen uitvoeren om te voorkomen dat de fout iets positief is. U kunt met behulp van de optie [bedreigingen](#undo-an-action-using-threat-explorer) en het [tabblad acties](#undo-an-action-using-the-actions-tab-for-an-investigation) een actie ongedaan maken. 

> [!IMPORTANT]
> Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u probeert de volgende taken uit te voeren.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met de bedreigings Verkenner

Met de bedreigings Verkenner kan uw beveiligingsteam een e-mailbericht vinden dat wordt beïnvloed door een actie en mogelijk de actie ongedaan gemaakt.

****

|Voorbeeld|Opties voor ongedaan maken|Meer informatie|
|---|---|---|
|Een e-mailbericht is doorgestuurd naar de map Ongewenste E-mail van een gebruiker|-Verplaats het bericht naar de map Verwijderde items van de gebruiker<br/>-Verplaats het bericht naar het postvak in van de gebruiker <br/>-Verwijder het bericht|[Schadelijke e-mail zoeken en onderzoeken die is bezorgd in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|Een e-mailbericht of een bestand is in quarantaine geplaatst|-De e-mail of het bestand vrijgeven <br/>-De e-mail of het bestand verwijderen|[Geplaatste berichten en bestanden in een beheerder in Office 365 beheren](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Een bewerking ongedaan maken via het tabblad acties voor een onderzoek

In het Actiecentrum ziet u de acties die u kunt uitvoeren om de actie te herstellen.

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan. U gaat nu naar de beveiligings & compliance Center.

2. Ga naar onderzoek voor **Threat Management**  >  **Investigations**.

3. Selecteer in de lijst met onderzoek het pictogram **openen in nieuw venster** naast de id van het item.

4. Selecteer het tabblad **acties** .

5. Selecteer een item met de status **voltooid**en zoek een koppeling, zoals **goedgekeurd**, in de kolom **beslissing** . Er wordt een flyout geopend met meer informatie over de actie.

6. Als u de actie ongedaan wilt maken, selecteert u **herstel verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[Aan de slag met geautomatiseerd onderzoek en antwoord (lucht) in Office 365](office-365-air.md)
