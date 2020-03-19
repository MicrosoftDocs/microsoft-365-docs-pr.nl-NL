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
ms.openlocfilehash: 58800d5645241c2115356bc9899ce53302d1e37e
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42856903"
---
# <a name="quarantine-faq-in-office-365"></a>Veelgestelde vragen voor quarantaine in Office 365

In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over quarantaine voor Office 365-klanten met postvakken in Exchange Online- of zelfstandige EOP-klanten (Exchange Online Protection) zonder Exchange Online-postvakken.

## <a name="q-how-do-i-manage-messages-that-were-quarantined-for-malware"></a>V: Hoe beheer ik berichten die in quarantaine zijn geplaatst voor malware?

Alleen beheerders kunnen berichten beheren die in quarantaine zijn geplaatst voor malware. Zie Berichten en bestanden in quarantaine beheren [als beheerder in Office 365](manage-quarantined-messages-and-files.md)voor meer informatie.

## <a name="q-how-do-i-quarantine-spam"></a>V: Hoe quarantaine ik spam?

A. Berichten die door spamfiltering als spam of bulke-mail zijn geclassificeerd, worden standaard in het postvak van de gebruiker bezorgd en worden verplaatst naar de map Ongewenste e-mail. Maar u antispambeleid maken en configureren om spam of bulke-mailberichten in quarantaine te plaatsen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie.

## <a name="q-how-do-i-give-users-access-to-the-quarantine"></a>V: Hoe geef ik gebruikers toegang tot de quarantaine?

A. Een gebruiker moet een geldig account hebben om toegang te krijgen tot zijn eigen berichten in quarantaine. Standalone EOP vereist dat gebruikers worden weergegeven als e-mailgebruikers in EOP (handmatig gemaakt of gemaakt via directorysynchronisatie). Zie [E-mailgebruikers beheren in EOP voor](manage-mail-users-in-eop.md)meer informatie over het beheren van gebruikers in zelfstandige EOP-omgevingen.

## <a name="q-what-messages-can-end-users-access-in-quarantine"></a>V: Welke berichten kunnen eindgebruikers in quarantaine openen?

A. Gebruikers hebben toegang tot spam, bulke-mail en (vanaf april 2020) phishingberichten waar ze een ontvanger zijn. Eindgebruikers hebben geen toegang tot in quarantaine geplaatste malware, phishing met een hoog vertrouwen of berichten die in quarantaine zijn geplaatst vanwege de **bericht leveren aan de gehoste quarantaineactie** in de regels voor e-mailstromen (ook wel transportregels genoemd). Zie Berichten in [quarantaine zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie over gebruikers die toegang hebben tot berichten in quarantaine.

## <a name="q-how-long-are-messages-kept-in-the-quarantine"></a>V: Hoe lang worden berichten in quarantaine bewaard?

A. U configureert hoe lang spam-, phishing- en bulk-e-mailberichten in quarantaine worden bewaard met behulp van antispambeleid. De standaardis 30 dagen, wat ook het maximum is. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie

Voor berichten die in quarantaine zijn geplaatst door de actie E-mailstroomregel **Lever het bericht af aan de gehoste quarantaine,** worden de berichten 30 dagen in quarantaine bewaard. U deze duur niet configureren.

Nadat de periode is verstreken, worden de berichten verwijderd en kunnen ze niet worden hersteld.

## <a name="q-can-i-release-or-report-more-than-one-quarantined-message-at-a-time"></a>V: Kan ik meer dan één bericht in quarantaine tegelijk vrijgeven of rapporteren?

A. In het Security & Compliance Center u maximaal 100 berichten tegelijk selecteren en vrijgeven.

Beheerders kunnen de in quarantaine [geplaatste](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage) berichten en [release-quarantainemessage-cmdlets](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage) in Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell gebruiken om in quarantaine geplaatste berichten in bulk te vinden en vrij te geven en valse positieven in bulk te melden.

## <a name="q-are-wildcards-supported-when-searching-for-quarantined-messages-can-i-search-for-quarantined-messages-for-a-specific-domain"></a>V: Worden wildcards ondersteund bij het zoeken naar berichten in quarantaine? Kan ik zoeken naar berichten in quarantaine voor een specifiek domein?

A. Jokertekens worden niet ondersteund in het Security & Compliance Center. Als u bijvoorbeeld naar een afzender zoekt, moet u het volledige e-mailadres opgeven. U echter wildcards gebruiken in Exchange Online PowerShell of Exchange Online Protection PowerShell.

Voer bijvoorbeeld de volgende opdracht uit om spamberichten te vinden van alle afzenders in het domein contoso.com:

```powershell
$CQ = Get-QuarantineMessage -Type Spam | where {$_.SenderAddress -like "*@contoso.com"}
```

Voer vervolgens de volgende opdracht uit om deze berichten vrij te geven aan alle oorspronkelijke ontvangers:

```powershell
$CQ | foreach {Release-QuarantineMessage -Identity $CQ.Identity -ReleaseToAll}
```

Nadat je een bericht hebt uitgebracht, kun je het niet meer vrijgeven.
