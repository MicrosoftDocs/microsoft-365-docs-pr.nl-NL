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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over quarantaine in Exchange Online Protection (EOP) die mogelijk schadelijke of ongewenste berichten bevat.
ms.openlocfilehash: d2ccf174ae929c6db14f2a5319e9594495c0778e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826799"
---
# <a name="quarantined-email-messages-in-eop"></a>Gequarantinede e-mailberichten in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder postvak in van Exchange

Beleidsregels voor malware die een bericht met malware *tegenkomen.* Zie voor meer informatie [anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md).

Standaard wordt in antispam voor de gebruiker in de map Ongewenste E-mail in de map Ongewenste E-mail gebruikt om spamberichten te ontvangen en spam en bulk-e-mailberichten te verzenden. U kunt ook Antispambeleid maken en aanpassen voor het Quarantine spam en bulk-e-mailberichten. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Gebruikers en beheerders kunnen werken met berichten in quarantaine:

- Beheerders kunnen werken met alle typen quarantaine berichten voor alle gebruikers. Alleen beheerders kunnen werken met berichten die zijn gequarantined als malware, phishing van hoge betrouwbaarheid of als gevolg van de regels voor de e-mail stroom (ook wel een transportregel genoemd). Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

- Gebruikers kunnen werken met berichten in quarantaine waarvan ze een geadresseerde zijn als het bericht is gequarantined als spam, bulk-e-mail, of (vanaf april 2020) phishing. Voor meer informatie raadpleegt u [gequarantinede berichten zoeken en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md).

  Om te voorkomen dat gebruikers hun eigen verplaatste phishingberichten kunnen beheren, kunnen beheerders een andere actie voor het filteren van **e-mail** berichten verdict in Antispambeleid configureren. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders en gebruikers kunnen fout-positieven rapporteren aan Microsoft in Quarantine.

Zie [Veelgestelde vragen over quarantaine](quarantine-faq.md)voor meer informatie over quarantaine.
