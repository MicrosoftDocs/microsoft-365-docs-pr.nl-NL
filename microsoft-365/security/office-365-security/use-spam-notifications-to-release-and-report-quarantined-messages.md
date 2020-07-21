---
title: Spammeldingen voor eindgebruikers in Microsoft 365
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
description: Beheerders kunnen meer te weten komen over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: 4c3275b6af1eb452ed420b8eb2f923dfbb1267d6
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/21/2020
ms.locfileid: "45200014"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Spammeldingen van gebruikers gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie [In quarantaine geplaatste berichten in EOP](quarantine-email-messages.md)voor meer informatie.

Standaard worden spammeldingen van eindgebruikers uitgeschakeld in het antispambeleid. Wanneer een beheerder [spammeldingen voor eindgebruikers inschakelt,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)ontvangen ontvangers (inclusief gedeelde postvakken met automapping ingeschakeld) periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulke-mail of (vanaf april 2020) phishing.

> [!NOTE]
> Berichten die in quarantaine zijn geplaatst als phishing met een hoog vertrouwen, malware of via regels voor e-mailstromen (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders. Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

Een spammelding voor eindgebruikers bevat de volgende informatie voor elk bericht in quarantaine:

- **Afzender**: de verzendnaam en het e-mailadres van het bericht in quarantaine.

- **Onderwerp**: De onderwerpregeltekst van het bericht in quarantaine.

- **Datum**: de datum en tijd (in UTC) waarop het bericht in quarantaine is geplaatst.

- **Afzender blokkeren**: klik op deze koppeling om de afzender toe te voegen aan de lijst Met geblokkeerde afzenders. Zie [Een afzender van een e-mail blokkeren voor](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)meer informatie.

- **Release:** Voor spamberichten (geen phish) berichten u het bericht hier vrijgeven zonder het Security & Compliance Center in quarantaine te gaan.

- **Review**: Klik op deze link om naar Quarantaine te gaan in het Security & Compliance Center, waar u uw in quarantaine geplaatste berichten vrijgeven, verwijderen of rapporteren. Zie [Berichten zoeken en vrijgeven als gebruiker in EOP voor](find-and-release-quarantined-messages-as-a-user.md)meer informatie.

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)
