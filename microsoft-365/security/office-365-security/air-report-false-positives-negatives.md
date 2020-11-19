---
title: Onjuiste of onjuiste negatieven rapporteren na geautomatiseerd onderzoek in Microsoft Defender voor Office 365
description: Is er een fout opgetreden bij een gemiste of onjuiste detectie van de lucht in Microsoft Defender voor Office 365? Meer informatie over het indienen van onjuiste of onjuiste negatieven bij Microsoft voor analyse.
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
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: 27edc44145e7b61768d9caf00a3f308e8561d708
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357397"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Onjuiste positief en negatief rapporteren in automatisch onderzoek en antwoord mogelijkheden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Van toepassing op:**
- Microsoft Defender voor Office 365

Is er [geautomatiseerd onderzoek-en antwoord mogelijkheden in Office 365](automated-investigation-response-office.md) mis of er is iets misgegaan? Er zijn stappen die u kunt uitvoeren om het probleem op te lossen. U kunt:

- [Meld een fout-positief/negatief aan Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Pas uw meldingen](#adjust-an-alert-to-prevent-false-positives-from-recurring) aan (indien nodig). en
- [Herstelbewerkingen die zijn uitgevoerd, ongedaan maken](#undo-a-remediation-action).

Gebruik dit artikel als leidraad.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Meld een fout-positief/negatief aan Microsoft voor analyse

Als AIR in Microsoft Defender for Office 365 een e-mailbericht, een e-mailbijlage, een URL in een e-mailbericht of een URL in een Office-bestand heeft gemist, kunt u [verdachte spam, phishing, url's en bestanden verzenden naar Microsoft Office 365 scan](admin-submission.md).

U kunt ook [een bestand bij Microsoft indienen voor de analyse van malware](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Een waarschuwing aanpassen om fout-positieven van herhaling te voorkomen

Als een waarschuwing wordt geactiveerd door legitiem gebruik of als de waarschuwing onjuist is, kunt u [waarschuwingen beheren in de portal van de Cloud-app](https://docs.microsoft.com/cloud-app-security/managing-alerts).

Als uw organisatie [Microsoft Defender voor eind 365 punt](https://docs.microsoft.com/windows/security/threat-protection) gebruikt, en een bestand, IP-adres, URL of domein wordt behandeld als malware op een apparaat, ook als dit veilig is, kunt u [een aangepaste indicator maken met een actie toestaan voor uw apparaat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Een herstelactie ongedaan maken

In de meeste gevallen geldt dat als een herstelactie is ondernomen voor een e-mailbericht, e-mailbijlage of URL, en het item eigenlijk geen bedreiging is, kan uw beveiligingsteam de actie ongedaan maken en stappen uitvoeren om te voorkomen dat de fout iets positief is. U kunt met behulp van de optie [bedreigingen](#undo-an-action-using-threat-explorer) en het [tabblad acties](#undo-an-action-using-the-actions-tab-for-an-investigation) een actie ongedaan maken.

> [!IMPORTANT]
> Zorg ervoor dat u over de benodigde machtigingen beschikt voordat u probeert de volgende taken uit te voeren.

### <a name="undo-an-action-using-threat-explorer"></a>Een actie ongedaan maken met de bedreigings Verkenner

Met de bedreigings Verkenner kan uw beveiligingsteam een e-mailbericht vinden dat wordt beïnvloed door een actie en mogelijk de actie ongedaan gemaakt.

****

|Voorbeeld|Opties voor ongedaan maken|Meer informatie|
|---|---|---|
|Een e-mailbericht is doorgestuurd naar de map Ongewenste E-mail van een gebruiker|<ul><li>Verplaats het bericht naar de map Verwijderde items van de gebruiker</li><li>Het bericht verplaatsen naar het postvak in van de gebruiker</li><li>Het bericht verwijderen</li></ul>|[Schadelijke e-mail zoeken en onderzoeken die is bezorgd in Office 365](investigate-malicious-email-that-was-delivered.md)|
|Een e-mailbericht of een bestand is in quarantaine geplaatst|<ul><li>Het e-mailbericht of het bestand vrijgeven</li><li>Het e-mailbericht of het bestand verwijderen</li></ul>|[Geplaatste berichten in quarantaine beheren als beheerder](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a>Een bewerking ongedaan maken via het tabblad acties voor een onderzoek

In het Actiecentrum ziet u de acties die u kunt uitvoeren om de actie te herstellen.

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan. U gaat nu naar de beveiligings & compliance Center.

2. Ga naar onderzoek voor **Threat Management**  >  **Investigations**.

3. Selecteer in de lijst met onderzoek het pictogram **openen in nieuw venster** naast de id van het item.

4. Selecteer het tabblad **acties** .

5. Selecteer een item met de status **voltooid** en zoek een koppeling, zoals **goedgekeurd**, in de kolom **beslissing** . Er wordt een flyout geopend met meer informatie over de actie.

6. Als u de actie ongedaan wilt maken, selecteert u **herstel verwijderen**.

## <a name="related-articles"></a>Verwante artikelen

[Microsoft Defender voor Office 365](office-365-atp.md)

[AIR in Microsoft Defender voor Office 365](office-365-air.md)
