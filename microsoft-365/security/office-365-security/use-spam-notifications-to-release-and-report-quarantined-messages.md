---
title: Spammeldingen voor eindgebruikers in Office 36
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
description: Wanneer een beheerder spammeldingen van eindgebruikers inantispambeleid inschakelt, ontvangen ontvangers van berichten periodieke meldingen over hun in quarantaine geplaatste berichten.
ms.openlocfilehash: 6cde4681d7ea3ef5795201e9a2816b7224ad36f6
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895057"
---
# <a name="end-user-spam-notifications-in-office-365"></a>Spammeldingen voor eindgebruikers in Office 365

Quarantaine bevat potentieel gevaarlijke of ongewenste berichten in Office 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken. Zie [Quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid. Wanneer een beheerder [spammeldingen van eindgebruikers inschakelt,](configure-your-spam-filter-policies.md)ontvangen ontvangers van berichten periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.

> [!NOTE]
> In oktober 2019 hebben we de mogelijkheid verwijderd om in quarantaine geplaatste berichten rechtstreeks uit spammeldingen van eindgebruikers vrij te geven. In plaats daarvan kunnen gebruikers nu naar het Office 365 Security & Compliance Center gaan om hun in quarantaine geplaatste berichten vrij te geven (rechtstreeks of door op **Controleren** in de melding te klikken). Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie. <br/><br/> Berichten die in quarantaine zijn geplaatst als phishing, malware of door regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders. Zie [In quarantaine geplaatste berichten en bestanden beheren als beheerder in Office 365](manage-quarantined-messages-and-files.md)voor meer informatie.

Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:

- **Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.

- **Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.

- **Datum**: De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.

- **Afzender blokkeren:** klik op deze koppeling om de afzender toe te voegen aan de lijst Geblokkeerde afzenders.

- **Controle:** Klik op deze koppeling om de quarantaine in het Security & Compliance Center te gaan, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren.

![Voorbeeld van spammelding voor eindgebruikers](../../media/end-user-spam-notification.png)
