---
title: Spammeldingen van eindgebruikers in Microsoft 365
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
description: Beheerders kunnen meer informatie krijgen over spammeldingen van eindgebruikers voor in quarantaine geplaatste berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71f2a33ad83f94895c396f92c18753bfca7f2905
ms.sourcegitcommit: ac3e9ccb7b43a42e600af8f44e6f30019533faeb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/15/2021
ms.locfileid: "52933165"
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
- **Afzender blokkeren:** Klik op deze koppeling om de afzender toe te voegen aan de lijst Geblokkeerde afzenders in uw postvak. Raadpleeg [Afzender van e-mail blokkeren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4) voor meer informatie.
- **Release:** Voor spamberichten (geen phishingberichten) kunt u het bericht hier vrijgeven zonder naar **De** portal van de Microsoft 365 Defender te gaan.
- **Controleren:** Klik op deze koppeling om naar **Quarantaine** te gaan in de Microsoft 365 Defender-portal, waar u (afhankelijk van waarom het bericht in quarantaine is geplaatst) uw in quarantaine geplaatste berichten kunt bekijken, vrijgeven, verwijderen of rapporteren. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)

> [!NOTE]
> Een geblokkeerde afzender kan u nog steeds e-mail sturen. Alle berichten van deze afzender die uw postvak binnen komen, worden onmiddellijk verplaatst naar de map Ongewenste e-mail. Toekomstige berichten van deze afzender gaan naar de map Ongewenste e-mail of naar de quarantaine van de eindgebruiker. Als u deze berichten bij aankomst wilt verwijderen in plaats van ze te quarantineren, gebruikt u regels voor e-mailstroom [(ook](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) wel transportregels genoemd) om de berichten bij aankomst te verwijderen.
