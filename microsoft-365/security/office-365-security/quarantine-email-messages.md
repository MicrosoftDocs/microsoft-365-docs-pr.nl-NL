---
title: E-mailberichten in quarantaine plaatsen in Office 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
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
description: Quarantaine in Office 365 bevat mogelijk gevaarlijke of ongewenste berichten. Beheerders en eindgebruikers hebben toegang tot quarantaine.
ms.openlocfilehash: 9c82ba9821c42fe6c3dd78dbcecf63327d176e93
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857307"
---
# <a name="quarantine-in-office-365"></a>Quarantaine in Office 365

Als u een Office 365-klant bent met postvakken in Exchange Online of een zelfstandige EOP-klant (Exchange Online Protection) zonder Exchange Online-postvakken, is quarantaine beschikbaar om mogelijk gevaarlijke of ongewenste berichten vast te houden.

Anti-malware beleid automatisch quarantaine een bericht als *een* bijlage wordt gevonden om malware bevatten. Zie [Anti-malwarebeleid configureren in Office 365](configure-anti-malware-policies.md)voor meer informatie.

Antispampolitie slinkt standaard phishingberichten en levert spam- en bulk-e-mailberichten aan de map Ongewenste e-mail van de gebruiker. Maar u ook antispambeleid maken en aanpassen om spam en bulk-e-mailberichten in quarantaine te plaatsen. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie.

Zowel gebruikers als beheerders kunnen werken met berichten in quarantaine:

- Beheerders kunnen werken met alle soorten berichten in quarantaine voor alle gebruikers. Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, phishing met een hoog vertrouwen of als gevolg van regels voor de stroom (ook wel transportregels genoemd). Zie Berichten en bestanden in quarantaine beheren [als beheerder in Office 365](manage-quarantined-messages-and-files.md)voor meer informatie.

- Gebruikers kunnen werken met berichten in quarantaine waar ze een ontvanger zijn als het bericht in quarantaine is geplaatst als spam, bulke-mail of (vanaf april 2020) phishing. Zie Berichten in [quarantaine zoeken en vrijgeven als gebruiker in Office 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

  Om te voorkomen dat gebruikers hun eigen phishingberichten in quarantaine beheren, kunnen beheerders een andere actie configureren voor het **phishing-e-mailfiltervonnis** in het antispambeleid. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie.

- Beheerders en gebruikers kunnen valse positieven melden aan Microsoft in quarantaine.

Zie [Veelgestelde vragen](quarantine-faq.md)over quarantaine voor meer informatie over quarantaine.
