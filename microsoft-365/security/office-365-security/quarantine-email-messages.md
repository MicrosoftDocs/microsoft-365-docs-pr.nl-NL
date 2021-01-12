---
title: Gequarantinede e-mailberichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over quarantaine in Exchange Online Protection (EOP) die mogelijk schadelijke of ongewenste berichten bevat.
ms.openlocfilehash: 8a978ece029de06bcb7b434de730b0baea33a5e1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794326"
---
# <a name="quarantined-email-messages-in-eop"></a>Gequarantinede e-mailberichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvak in van Exchange

Beleidsregels voor malware die een bericht met malware *tegenkomen.* Zie voor meer informatie [anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).

Standaard wordt in antispam voor de gebruiker in de map Ongewenste E-mail in de map Ongewenste E-mail gebruikt om spamberichten te ontvangen en spam en bulk-e-mailberichten te verzenden. U kunt ook Antispambeleid maken en aanpassen voor het Quarantine spam en bulk-e-mailberichten. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Gebruikers en beheerders kunnen werken met berichten in quarantaine:

- Beheerders kunnen werken met alle typen quarantaine berichten voor alle gebruikers. Alleen beheerders kunnen werken met berichten die zijn gequarantined als malware, phishing van hoge betrouwbaarheid of als gevolg van de regels voor de e-mail stroom (ook wel een transportregel genoemd). Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

- Gebruikers kunnen werken met berichten in quarantaine waarvan ze een geadresseerde zijn als het bericht is gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing. Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).

  Om te voorkomen dat gebruikers hun eigen verplaatste phishingberichten kunnen beheren, kunnen beheerders een andere actie voor het filteren van **e-mail** berichten verdict in Antispambeleid configureren. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders en gebruikers kunnen fout-positieven rapporteren aan Microsoft in Quarantine.

Zie [Veelgestelde vragen over quarantaine](quarantine-faq.md)voor meer informatie over quarantaine.
