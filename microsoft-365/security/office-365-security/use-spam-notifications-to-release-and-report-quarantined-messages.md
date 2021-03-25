---
title: Spammeldingen voor eindgebruikers in Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Beheerders kunnen informatie krijgen over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9cff91be399bd98eb7e6e5a2a6d91a4a8bb602ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204448"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Gebruikersspammeldingen gebruiken om in quarantaine geplaatste berichten vrij te geven en te rapporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie Berichten in quarantaine plaatsen [in EOP voor meer informatie.](quarantine-email-messages.md)

Spammeldingen van eindgebruikers worden standaard uitgeschakeld in antispambeleid. Wanneer een [beheerder](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)spammeldingen voor eindgebruikers inschakelen, ontvangen geadresseerden (inclusief gedeelde postvakken waarop automatischmapping is ingeschakeld) periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulkmail of (vanaf april 2020) phishing.

Voor gedeelde postvakken worden spammeldingen van eindgebruikers alleen ondersteund voor gebruikers die fullaccess-machtigingen krijgen voor het gedeelde postvak. Zie Het EAC gebruiken om gedeelde [postvakdelegering](/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)te bewerken voor meer informatie.

Spammeldingen van eindgebruikers worden niet ondersteund voor groepen.

> [!NOTE]
> Berichten die in quarantaine zijn geplaatst als phishing, malware of e-mailstroomregels (ook wel transportregels genoemd) zijn alleen beschikbaar voor beheerders. Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

Een spammelding voor eindgebruikers bevat de volgende informatie voor elk in quarantaine geplaatst bericht:

- **Afzender:** de verzendnaam en het e-mailadres van het in quarantaine geplaatste bericht.

- **Onderwerp:** De onderwerpregeltekst van het in quarantaine geplaatste bericht.

- **Datum:** De datum en tijd (in UTC) dat het bericht in quarantaine is geplaatst.

- **Afzender blokkeren:** Klik op deze koppeling om de afzender toe te voegen aan uw lijst met geblokkeerde afzenders. Zie Een afzender van [e-mail blokkeren voor meer informatie.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Release:** Voor spamberichten (geen phishingberichten) kunt u het bericht hier vrijgeven zonder naar het Beveiligingscentrum & quarantaine te gaan.

- **Controleren:** Klik op deze koppeling om naar Quarantaine te gaan in het beveiligings- & compliancecentrum, waar u (afhankelijk van waarom het bericht in quarantaine is geplaatst) uw in quarantaine geplaatste berichten kunt bekijken, vrijgeven, verwijderen of rapporteren. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)

> [!NOTE]
> Een geblokkeerde afzender kan u nog steeds e-mail sturen. Alle berichten van deze afzender die uw postvak binnen komen, worden onmiddellijk verplaatst naar de map Ongewenste e-mail. Toekomstige berichten van deze afzender gaan naar de map Ongewenste e-mail of naar de quarantaine van de eindgebruiker. Als u deze berichten bij aankomst wilt verwijderen in plaats van ze te quarantineren, gebruikt u regels voor e-mailstroom [(ook](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) wel transportregels genoemd) om de berichten bij aankomst te verwijderen.