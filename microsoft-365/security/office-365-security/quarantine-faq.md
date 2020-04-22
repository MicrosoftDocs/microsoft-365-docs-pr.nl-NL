---
title: Veelgestelde vragen over quarantaine
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
description: Antwoorden op veelgestelde vragen over quarantaine in Office 365.
ms.openlocfilehash: 3947fbed2a17380a18320a8bffd08a8178ad2b3f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634422"
---
# <a name="quarantine-faq"></a>Veelgestelde vragen over quarantaine

In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over quarantaine voor Microsoft 365-klanten met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>V: Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?

Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware. Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).

## <a name="q-how-do-i-quarantine-spam"></a>V: Hoe quarantaine spam?

A. Berichten die door spamfilter worden geclassificeerd als spam of bulk-e-mail worden standaard naar het postvak van de gebruiker verzonden en worden verplaatst naar de map Ongewenste e-mail. Maar u in plaats daarvan antispambeleid maken en configureren om spam of bulke-mailberichten in quarantaine te plaatsen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>V: Hoe geef ik gebruikers toegang tot de quarantaine?

A. Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn eigen berichten in quarantaine. Standalone EOP vereist dat gebruikers worden vertegenwoordigd als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via adreslijstsynchronisatie). Zie [E-mailgebruikers beheren in EOP](manage-mail-users-in-eop.md)voor meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>V: Welke berichten kunnen eindgebruikers in quarantaine openen?

A. Gebruikers hebben toegang tot spam, bulke-mail en (vanaf april 2020) phishingberichten waar ze een ontvanger zijn. Eindgebruikers hebben geen toegang tot in quarantaine geplaatste malware, phishing met een hoog vertrouwen of berichten die in quarantaine zijn geplaatst vanwege de **actie Het bericht leveren aan de gehoste quarantaineactie** in de regels voor e-mailstromen (ook wel transportregels genoemd). Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over gebruikers die toegang hebben tot in quarantaine geplaatste berichten.

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>V: Hoe lang worden berichten in quarantaine gehouden?

A. U configureert hoe lang spam- en phishing- en bulke-mailberichten in quarantaine worden gehouden met behulp van antispambeleid. De standaard instelling is 30 dagen, wat ook het maximum is. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie

Voor berichten die in quarantaine zijn geplaatst door de regelactie E-mailstroom **Breng het bericht naar de gehoste quarantaine,** worden de berichten 30 dagen in quarantaine gehouden. U deze duur niet configureren.

Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet worden hersteld.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>V: Kan ik meer dan één in quarantaine geplaatst bericht tegelijk vrijgeven of rapporteren?

A. In het Security & Compliance Center u maximaal 100 berichten tegelijk selecteren en vrijgeven.

Beheerders kunnen de cmdlets [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) en [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) gebruiken in Exchange Online PowerShell of standalone Exchange Online Protection PowerShell om in bulk in quarantaine geplaatste berichten te vinden en vrij te geven en valse positieven in bulk te melden.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>V: Worden wildcards ondersteund bij het zoeken naar in quarantaine geplaatste berichten? Kan ik zoeken naar in quarantaine geplaatste berichten voor een specifiek domein?

A. Jokertekens worden niet ondersteund in het Beveiligingscentrum & Compliance. Wanneer u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven. U echter wildcards gebruiken in Exchange Online PowerShell of Exchange Online Protection PowerShell.

Voer bijvoorbeeld de volgende opdracht uit om spamin quarantaine geplaatste berichten van alle afzenders in het domein contoso.com te vinden:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Voer vervolgens de volgende opdracht uit om deze berichten vrij te geven aan alle oorspronkelijke ontvangers:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $_.Identity -ReleaseToAll}
```

Nadat u een bericht hebt vrijgegeven, u het bericht niet meer vrijgeven.
