---
title: Spammeldingen van eindgebruikers in Office 36
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
description: Wanneer een beheerder spammeldingen van eindgebruikers inschakelt in antispambeleid, ontvangen ontvangers van berichten periodieke meldingen over hun in quarantaine geplaatste berichten.
ms.openlocfilehash: 67dbf311c37ae61c007b78110522033d79c0b161
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857143"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Spammeldingen voor eindgebruikers in Office 365

Quarantaine bevat mogelijk gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken. Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

Spammeldingen van eindgebruikers zijn standaard uitgeschakeld in het antispambeleid. Wanneer een beheerder spammeldingen van [eindgebruikers inschakelt,](configure-your-spam-filter-policies.md)ontvangen ontvangers van berichten periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.

> [!NOTE]
> In oktober 2019 hebben we de mogelijkheid om in quarantaine geplaatste berichten rechtstreeks uit spammeldingen van eindgebruikers vrij te geven, verwijderd. In plaats daarvan kunnen gebruikers nu naar het Office 365 Security & Compliance Center gaan om hun berichten in quarantaine vrij te geven (rechtstreeks of door op **Controleren** in de melding te klikken). Zie Berichten in [quarantaine zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie. <br/><br/> Berichten die in quarantaine zijn geplaatst als phishing, malware of mailflowregels (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders. Zie Berichten in [quarantaine zoeken en vrijgeven als beheerder in Office 365](find-and-release-quarantined-messages-as-an-administrator.md)voor meer informatie.

Een spammelding van eindgebruikers bevat de volgende informatie voor elk bericht in quarantaine:

- **Afzender**: De verzendnaam en het e-mailadres van het bericht in quarantaine.

- **Onderwerp**: De onderwerpregeltekst van het bericht in quarantaine.

- **Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.

- **Afzender blokkeren:** Klik op deze koppeling om de afzender toe te voegen aan de lijst Met geblokkeerde afzenders.

- **Review**: Klik op deze link om de quarantaine in het Security & Compliance Center te gaan, waar u uw berichten in quarantaine vrijgeven, verwijderen of rapporteren.

![Voorbeeld spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
