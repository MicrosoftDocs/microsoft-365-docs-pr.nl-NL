---
title: Spammeldingen van eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
description: In dit artikel vindt u meer informatie over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten.
ms.openlocfilehash: 2a865130bf1fa0c09b5b68254fb604795b204c22
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034996"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Spammeldingen van gebruikers gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren

Potentieel gevaarlijke of ongewenste berichten worden in quarantaine geplaatst in Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken. Zie [Quarantaine in Office 365](quarantine-email-messages.md) voor meer informatie.

Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid. Wanneer een beheerder [spammeldingen van eindgebruikers inschakelt,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ontvangen ontvangers periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.

> [!NOTE]
> Berichten die in quarantaine zijn geplaatst als phishing, malware of door regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders. Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).

Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:

- **Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.

- **Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.

- **Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.

- **Afzender blokkeren:** klik op deze koppeling om de afzender toe te voegen aan de lijst Geblokkeerde afzenders. Zie [Een e-mailafzender blokkeren in Outlook](https://support.office.com/article/b29fd867-cac9-40d8-aed1-659e06a706e4)voor meer informatie.

- **Release:** Voor spam (niet phish) berichten, u het bericht hier vrijgeven zonder naar Quarantaine de Security & Compliance Center.

- **Controle:** Klik op deze link om naar Quarantaine te gaan in het Security & Compliance Center, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren. Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

![Voorbeeld van spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
