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
description: Beheerders kunnen meer informatie krijgen over spammeldingen voor eindgebruikers voor berichten in quarantaine in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb347f7fd3d3793b563714e8116316b30165ef9a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287543"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages"></a>Spammeldingen van gebruikers gebruiken om berichten in quarantaine vrij te geven en te rapporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-bedrijven met postvakken in Exchange Online of EOP-bedrijven (standalone Exchange Online Protection) zonder Exchange Online-postvakken worden potentieel gevaarlijke of ongewenste berichten in quarantaine geplaatst. Zie Berichten in [quarantaine in EOP](quarantine-email-messages.md)voor meer informatie.

Spammeldingen voor eindgebruikers worden standaard uitgeschakeld in antispambeleid. Wanneer een beheerder [spammeldingen](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)voor eindgebruikers inschakelen, ontvangen geadresseerden (inclusief gedeelde postvakken waarop automatisch toewijzen is ingeschakeld) periodieke meldingen over hun berichten die in quarantaine zijn geplaatst als spam, bulkmail of (vanaf april 2020) phishing.

Spammeldingen voor gedeelde postvakken worden alleen ondersteund voor gebruikers aan wie FullAccess-machtigingen voor het gedeelde postvak zijn verleend. Zie het EAC gebruiken [om gedeelde postvakdelegering te bewerken.](https://docs.microsoft.com/Exchange/collaboration-exo/shared-mailboxes#use-the-eac-to-edit-shared-mailbox-delegation)

Spammeldingen voor eindgebruikers worden niet ondersteund voor groepen.

> [!NOTE]
> Berichten die in quarantaine zijn geplaatst als zeer vertrouwelijk phishing, malware of door regels voor de e-mailstroom (ook wel transportregels genoemd), zijn alleen beschikbaar voor beheerders. Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

Een spammelding voor eindgebruikers bevat de volgende informatie voor elk bericht in quarantaine:

- **Afzender:** de naam en het e-mailadres van het in quarantaine geplaatste bericht.

- **Onderwerp:** de onderwerpregeltekst van het in quarantaine geplaatste bericht.

- **Datum:** de datum en tijd (in UTC) waarop het bericht in quarantaine is geplaatst.

- **Afzender blokkeren:** klik op deze koppeling om de afzender toe te voegen aan de lijst geblokkeerde afzenders. Zie Een afzender van een [e-mail blokkeren voor meer informatie.](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)

- **Release:** Voor spamberichten (geen phishingberichten) kunt u het bericht hier vrijgeven zonder het beveiligings- of compliancecentrum in quarantaine & te plaatsen.

- **Controleren:** Klik op deze koppeling om naar Quarantaine te gaan in het beveiligings- & Compliancecentrum, waar u (afhankelijk van de reden waarom het bericht in quarantaine is geplaatst) uw in quarantaine geplaatste berichten kunt bekijken, vrijgeven, verwijderen of rapporteren. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

![Voorbeeld van spammeldingen voor eindgebruikers](../../media/end-user-spam-notification.png)

> [!NOTE]
> Een geblokkeerde afzender kan u nog steeds e-mail sturen. Berichten van deze afzender die in uw postvak komen, worden onmiddellijk naar de map Ongewenste e-mail verplaatst. Toekomstige berichten van deze afzender gaan naar de map Ongewenste e-mail of in de quarantaine van de eindgebruiker. Als u deze berichten bij aankomst wilt verwijderen in plaats van ze te quarantineren, gebruikt u regels voor de [e-mailstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) om de berichten bij aankomst te verwijderen.
