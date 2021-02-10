---
title: Veelgestelde vragen over in quarantaine geplaatste berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen veelgestelde vragen en antwoorden over berichten in quarantaine bekijken in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 019f1c103ef1aaf7641072cd1259d22e83f0de4c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166925"
---
# <a name="quarantined-messages-faq"></a>Veelgestelde vragen over in quarantaine geplaatste berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Dit onderwerp bevat veelgestelde vragen en antwoorden over e-mailberichten in quarantaine voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.

Zie Veelgestelde vragen en antwoorden [](anti-spam-protection-faq.md)over bescherming tegen spam.

Zie veelgestelde vragen en antwoorden over bescherming tegen malware tegen [malware.](anti-malware-protection-faq-eop.md)

Zie Veelgestelde vragen en antwoorden over bescherming tegen [spoofing.](anti-spoofing-protection-faq.md)

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?

Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware. Zie Berichten en bestanden in quarantaine beheren als [beheerder voor meer informatie.](manage-quarantined-messages-and-files.md)

## <a name="how-do-i-quarantine-spam"></a>Hoe kan ik spam in quarantaine plaatsen?

Standaard worden berichten die als spam of bulkmail zijn geclassificeerd door spamfilters, bezorgd in het postvak van de gebruiker en verplaatst naar de map Ongewenste e-mail. U kunt echter antispambeleid maken en configureren voor spam of bulk-e-mailberichten. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Hoe geef ik gebruikers toegang tot de quarantaine?

Gebruikers moeten een geldig account hebben om toegang te krijgen tot hun eigen berichten in quarantaine. Voor zelfstandige EOP moeten gebruikers worden weergegeven als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie). Zie E-mailgebruikers beheren in EOP voor meer informatie over het beheren van gebruikers in zelfstandige [EOP-omgevingen.](manage-mail-users-in-eop.md)

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Welke berichten kunnen eindgebruikers in quarantaine openen?

Gebruikers kunnen toegang krijgen tot spam-, bulk-e-mail en (vanaf april 2020) phishingberichten waarin ze geadresseerd zijn. Eindgebruikers hebben geen toegang tot malware in quarantaine, zeer berichten die in quarantaine zijn geplaatst of phishingberichten die in quarantaine zijn geplaatst vanwege de actie Het bericht verzenden naar de gehoste **quarantaine** in de regels voor de e-mailstroom (ook wel transportregels genoemd). Zie Berichten in quarantaine zoeken en als gebruiker vrijgeven voor meer informatie over gebruikers die in [quarantaine geplaatste berichten openen.](find-and-release-quarantined-messages-as-a-user.md)

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Hoe lang worden berichten in de quarantaine bewaard?

U configureert hoe lang spam, phishing en bulk-e-mailberichten in de quarantaine worden bewaard door middel van antispambeleid. De standaardwaarde is 30 dagen, wat ook het maximum is. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie

Voor berichten die in quarantaine zijn geplaatst door de regelactie voor de e-mailstroom, worden de berichten 30 dagen in quarantaine bewaard. U kunt deze duur niet configureren.

Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet meer worden hersteld.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kan ik meerdere berichten in quarantaine tegelijk vrijgeven of rapporteren?

In het & compliancecentrum kunt u maximaal 100 berichten tegelijk selecteren en vrijgeven.

Beheerders kunnen de cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) en [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell of zelfstandige EOP PowerShell gebruiken om bulksgewijs in quarantaine geplaatste berichten te zoeken en los te laten, en om fout-positieven bulksgewijs te rapporteren.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Worden jokertekens ondersteund bij het zoeken naar in quarantaine geplaatste berichten? Kan ik in quarantaine zoeken naar berichten voor een specifiek domein?

Jokertekens worden niet ondersteund in het & compliancecentrum. Als u bijvoorbeeld een afzender zoekt, moet u het volledige e-mailadres opgeven. U kunt echter wel jokertekens gebruiken in Exchange Online PowerShell of de zelfstandige EOP PowerShell.

Kopieer bijvoorbeeld de volgende PowerShell-code naar Kladblok en sla het bestand op als PS1-bestand op een locatie die u eenvoudig kunt vinden (bijvoorbeeld C:\Data\QuarantineRelease.ps1).

Voer daarna, nadat u verbinding hebt gemaakt [met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) of [Exchange Online Protection PowerShell,](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)de volgende opdracht uit om het script uit te voeren:

```powershell
& C:\Data\QuarantineRelease.ps1
```

Het script doet de volgende acties:

- Zoek niet-uitgebrachte berichten die in quarantaine waren geplaatst als spam van alle afzenders in het fabrikam-domein. Het maximum aantal resultaten is 50.000 (50 pagina's van 1000 resultaten).
- Sla de resultaten op in een CSV-bestand.
- Laat de overeenkomende berichten in quarantaine vrijgeven aan alle oorspronkelijke geadresseerden.

```powershell
$Page = 1
$List = $null

Do
{
Write-Host "Getting Page " $Page

$List = (Get-QuarantineMessage -Type Spam -PageSize 1000 -Page $Page | where {$_.Released -like "False" -and $_.SenderAddress -like "*fabrikam.com"})
Write-Host "                     " $List.count " rows in this page match"
Write-Host "                                                             Exporting list to appended CSV for logging"
$List | Export-Csv -Path "C:\Data\Quarantined Message Matches.csv" -Append -NoTypeInformation

Write-Host "Releasing page " $Page
$List | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}

$Page = $Page + 1

} Until ($Page -eq 50)
```

Nadat u een bericht hebt uitgebracht, kunt u het niet meer vrijgeven.
