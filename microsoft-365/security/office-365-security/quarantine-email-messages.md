---
title: Quarantaine in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: In dit artikel wordt in quarantaine in Microsoft 365 uitgelegd. Quarantaine bevat potentieel gevaarlijke of ongewenste berichten.
ms.openlocfilehash: 396be17e07a347ab4d28a3e0b67dd137bda999db
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033864"
---
# <a name="quarantine-email-messages"></a>E-mailberichten in quarantaine plaatsen

Als u een Microsoft 365-klant bent met postvakken in Exchange Online of een zelfstandige Exchange Online Protection-klant (EOP) zonder Exchange Online-postvakken, is quarantaine beschikbaar om potentieel gevaarlijke of ongewenste berichten vast te houden.

Anti-malwarebeleid plaatst een bericht automatisch in quarantaine als *blijkt dat er* een bijlage is die malware bevat. Zie [Beleid voor antimalware configureren in Office 365](configure-anti-malware-policies.md)voor meer informatie.

Standaard worden phishingberichten in quarantaine geplaatst en worden spam- en bulk-e-mailberichten verzonden naar de map Ongewenste e-mail van de gebruiker. U echter ook antispambeleid maken en aanpassen om spam en bulk-e-mailberichten in quarantaine te plaatsen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

Zowel gebruikers als beheerders kunnen werken met in quarantaine geplaatste berichten:

- Beheerders kunnen werken met alle soorten in quarantaine geplaatste berichten voor alle gebruikers. Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, phishing met veel vertrouwen of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd). Zie [Berichten en bestanden in quarantaine beheren als Office 365-beheerder](manage-quarantined-messages-and-files.md).

- Gebruikers kunnen werken met in quarantaine geplaatste berichten waar ze een ontvanger zijn als het bericht in quarantaine is geplaatst als spam, bulke-mail of (vanaf april 2020) phishing. Zie [In quarantaine geplaatste berichten zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

  Om te voorkomen dat gebruikers hun eigen phishingberichten in quarantaine beheren, kunnen beheerders een andere actie configureren voor het **phishing-e-mailfiltervonnis** in antispambeleid. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders en gebruikers kunnen valse positieven melden aan Microsoft in quarantaine.

Zie [Veelgestelde vragen](quarantine-faq.md)over quarantaine voor meer informatie over quarantaine.
