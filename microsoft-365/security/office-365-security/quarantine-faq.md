---
title: Veelgestelde vragen over quarantaine berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Beheerders kunnen Veelgestelde vragen en antwoorden over berichten in quarantaine weergeven in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9cf1281338de66f54a6c4546b047259d647cc3ea
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615994"
---
# <a name="quarantined-messages-faq"></a>Veelgestelde vragen over quarantaine berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In dit onderwerp vindt u veelgestelde vragen en antwoorden over geposte e-mailberichten voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.

Zie Veelgestelde vragen over [anti-spam beveiliging](anti-spam-protection-faq.md)voor vragen en antwoorden over bescherming tegen ongewenste e-mail.

Zie [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md)voor vragen en antwoorden over beveiliging tegen malware.

Zie [Veelgestelde vragen over beveiliging tegen spoofing](anti-spoofing-protection-faq.md)voor vragen en antwoorden over beveiliging tegen spoofing.

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Hoe beheer ik berichten die zijn gequarantined voor malware?

Alleen beheerders kunnen berichten beheren die zijn gequarantined voor malware. Zie voor meer informatie [gequarantinee berichten en bestanden beheren als beheerder](manage-quarantined-messages-and-files.md).

## <a name="how-do-i-quarantine-spam"></a>Hoe kan ik spam in quarantaine plaatsen?

Standaard worden berichten die als ongewenste e-mail of bulksgewijs e-mailbericht zijn geclassificeerd via spamfilters bezorgd in het postvak van de gebruiker en worden ze naar de map Ongewenste E-mail verplaatst. U kunt echter wel antispam-beleidsregels maken en configureren zodat u in plaats daarvan spam en bulk-e-mailberichten kunt maken en configureren. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Hoe kan ik gebruikers toegang geven tot de quarantaine?

Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn of haar eigen berichten in quarantaine. Voor zelfstandige EOP moet gebruikers worden weergegeven als e-mail gebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie). Zie [e-mail gebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Met welke berichten hebben gebruikers toegang tot de eindgebruikers in quarantaine?

Gebruikers hebben toegang tot spam, bulk-e-mail en (vanaf april 2020) malafide berichten waarin ze een geadresseerde zijn. Eindgebruikers hebben geen toegang tot geïsoleerde malware van de werkstroom of berichten die zijn gequarantined vanwege het **bezorgen van het bericht naar de actie in de gehoste quarantaine** -actie in de e-mail stroom regels (ook wel de zogenaamde transportregels genoemd). Zie geplaatste [berichten in quarantaine plaatsen en vrijgeven als een gebruiker](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over gebruikers die quarantaine berichten gebruiken.

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Hoe lang worden berichten in de quarantaine bewaard?

U configureert hoe lang spamberichten, phishing en bulk-e-mailberichten in quarantaine worden bewaard met behulp van antispambeleid. De standaardinstelling is 30 dagen, wat ook het maximum is. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Voor berichten waarvan de actie de e-mail stroom regel is gequarantined, wordt **het bericht verzonden naar de gehoste quarantaine**, en worden de berichten in quarantaine bewaard gedurende 30 dagen. U kunt deze duur niet configureren.

Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet meer worden hersteld.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kan ik meerdere berichten in quarantaine plaatsen of rapporteren?

In het beveiligings & nalevings centrum kunt u 100-berichten tegelijk selecteren en vrijgeven.

Beheerders kunnen gebruikmaken van de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) en [release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage) in Exchange Online PowerShell of zelfstandige EOP PowerShell om geplaatste berichten bulksgewijs te zoeken en uit te brengen, en om fout-positieven in bulk te rapporteren.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Worden jokertekens ondersteund bij het zoeken naar berichten in quarantaine? Kan ik zoeken naar berichten in quarantaine voor een bepaald domein?

Jokertekens worden niet ondersteund in het beveiligings & nalevings centrum. Als u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven. U kunt jokertekens gebruiken in Exchange Online PowerShell of zelfstandige EOP PowerShell.

Voer bijvoorbeeld de volgende opdracht uit om spamberichten in quarantaine te plaatsen van alle afzenders in de domein contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Voer vervolgens de volgende opdracht uit om die berichten op alle oorspronkelijke geadresseerden te brengen:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Wanneer u een bericht hebt vrijgegeven, kunt u het niet meer vrijgeven.
