---
title: Spam meldingen voor eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie lezen over spam meldingen voor eindgebruikers voor berichten in quarantaine in Exchange Online Protection (EOP).
ms.openlocfilehash: 9e9c95fafe3610e0ad945f18aa85ff13342d8d65
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827359"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Gebruik spam meldingen van gebruikers om berichten in quarantaine vrij te geven en te rapporteren

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie voor meer informatie [quarantaine berichten in EOP](quarantine-email-messages.md).

Standaard zijn meldingen voor spam van eindgebruikers uitgeschakeld in antispambeleid. Wanneer een beheerder [meldingen voor spam van eindgebruikers](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)uitschakelt, ontvangen geadresseerden (inclusief gedeelde postvakken met automatisch toewijzen ingeschakeld) periodieke meldingen over hun berichten die zijn gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing.

Voor gedeelde postvakken worden meldingen voor spam van eindgebruikers alleen ondersteund voor gebruikers aan wie de machtiging machtiging fullaccess is verleend voor het gedeelde Postvak. Zie voor meer informatie [gedeeld postvak delegering bewerken](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation).

Spam melding voor eindgebruikers wordt niet ondersteund voor groepen.

> [!NOTE]
> Berichten die zijn gequarantined als phishing van hoge betrouwbaarheid, malware of via e-mail stroom regels (ook wel bekend als transportregels), zijn alleen beschikbaar voor beheerders. Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

Een melding voor spam van eindgebruikers bevat de volgende informatie voor elk gequarantine bericht:

- **Afzender**: de naam en het e-mailadres van het gequarantinede bericht verzenden.

- **Onderwerp**: het onderwerp van de tekst van het bericht in de quarantaine.

- **Datum**: de datum en tijd (in UTC) waarop het bericht is in quarantaine geplaatst.

- **Afzender blokkeren**: Klik op deze link om de afzender toe te voegen aan uw lijst met geblokkeerde afzenders. Zie voor meer informatie [de afzender van een e-mailbericht blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).

- **Release**: voor spamberichten (niet voor phishing), kunt u het bericht hier vrijgeven zonder dat u de beveiliging voor de beveiliging & Quarantine.

- **Controleren**: Klik op deze koppeling om naar Quarantine te gaan in het beveiligings & nalevings centrum, waarin u kunt zien welke berichten in quarantaine zijn geplaatst, of laat zien, verwijderen of rapporteren. Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).

![Voorbeeld van spam met eindgebruikers](../../media/end-user-spam-notification.png)
