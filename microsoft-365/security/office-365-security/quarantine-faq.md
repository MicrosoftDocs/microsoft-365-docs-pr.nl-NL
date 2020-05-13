---
title: Veelgestelde vragen over in quarantaine geplaatste berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c440b2ac-cafa-4be5-ba4c-14278a7990ae
ms.collection:
- M365-security-compliance
description: Beheerders kunnen veelgestelde vragen en antwoorden over in quarantaine geplaatste berichten bekijken in Exchange Online Protection (EOP).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b2022a43f1dd89d47fdb4f3898f8f481419962c0
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213102"
---
# <a name="quarantined-messages-faq"></a>Veelgestelde vragen over in quarantaine geplaatste berichten

In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over in quarantaine geplaatste e-mailberichten voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken.

Zie [Veelgestelde vragen](anti-spam-protection-faq.md)over spambescherming voor vragen en antwoorden over bescherming tegen spam.

Zie [Veelgestelde vragen](anti-malware-protection-faq-eop.md)over bescherming tegen malware voor vragen en antwoorden over bescherming tegen malware.

Zie Veelgestelde vragen over [anti-spoofing bescherming](anti-spoofing-protection-faq.md)voor vragen en antwoorden over anti-spoofing bescherming.

## <a name="how-do-i-manage-messages-that-were-quarantined-for-malware"></a>Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?

Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware. Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder voor](manage-quarantined-messages-and-files.md)meer informatie.

## <a name="how-do-i-quarantine-spam"></a>Hoe quarantaine spam?

Berichten die door spamfilter worden geclassificeerd als spam of bulk-e-mail worden standaard naar het postvak van de gebruiker verzonden en worden verplaatst naar de map Ongewenste e-mail. Maar u in plaats daarvan antispambeleid maken en configureren om spam of bulke-mailberichten in quarantaine te plaatsen. Zie [Beleid voor antispam configureren in EOP](configure-your-spam-filter-policies.md)voor meer informatie.

## <a name="how-do-i-give-users-access-to-the-quarantine"></a>Hoe geef ik gebruikers toegang tot de quarantaine?

Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn eigen berichten in quarantaine. Standalone EOP vereist dat gebruikers worden vertegenwoordigd als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie). Zie [E-mailgebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.

## <a name="what-messages-can-end-users-access-in-quarantine"></a>Welke berichten kunnen eindgebruikers in quarantaine openen?

Gebruikers hebben toegang tot spam, bulke-mail en (vanaf april 2020) phishingberichten waar ze een ontvanger zijn. Eindgebruikers hebben geen toegang tot in quarantaine geplaatste malware, phishing met een hoog vertrouwen of berichten die in quarantaine zijn geplaatst vanwege de **actie Het bericht leveren aan de gehoste quarantaineactie** in de regels voor e-mailstromen (ook wel transportregels genoemd). Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker voor](find-and-release-quarantined-messages-as-a-user.md)meer informatie over gebruikers die toegang hebben tot in quarantaine geplaatste berichten.

## <a name="how-long-are-messages-kept-in-the-quarantine"></a>Hoe lang worden berichten in quarantaine gehouden?

U configureert hoe lang spam- en phishing- en bulke-mailberichten in quarantaine worden gehouden met behulp van antispambeleid. De standaard instelling is 30 dagen, wat ook het maximum is. Zie [Beleid voor antispam configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie

Voor berichten die in quarantaine zijn geplaatst door de regelactie E-mailstroom **Breng het bericht naar de gehoste quarantaine,** worden de berichten 30 dagen in quarantaine gehouden. U deze duur niet configureren.

Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet worden hersteld.

## <a name="can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>Kan ik meerdere in quarantaine geplaatste berichten tegelijk vrijgeven of rapporteren?

In het Security & Compliance Center u maximaal 100 berichten tegelijk selecteren en vrijgeven.

Beheerders kunnen de cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) en [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) gebruiken in Exchange Online PowerShell of standalone EOP PowerShell om in bulk in quarantaine geplaatste berichten te vinden en vrij te geven en om valse positieven in bulk te melden.

## <a name="are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>Worden wildcards ondersteund bij het zoeken naar in quarantaine geplaatste berichten? Kan ik zoeken naar in quarantaine geplaatste berichten voor een specifiek domein?

Jokertekens worden niet ondersteund in het Beveiligingscentrum & Compliance. Wanneer u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven. Maar u wildcards gebruiken in Exchange Online PowerShell of standalone EOP PowerShell.

Voer bijvoorbeeld de volgende opdracht uit om spamin quarantaine geplaatste berichten van alle afzenders in het domein contoso.com te vinden:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Voer vervolgens de volgende opdracht uit om deze berichten vrij te geven aan alle oorspronkelijke ontvangers:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Nadat u een bericht hebt vrijgegeven, u het bericht niet meer vrijgeven.
