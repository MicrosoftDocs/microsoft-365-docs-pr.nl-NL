---
title: In quarantaine geplaatste e-mailberichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: overview
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
description: Beheerders kunnen meer informatie krijgen over quarantaine in Exchange Online Protection (EOP) die potentieel gevaarlijke of ongewenste berichten bevat.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bd748871cc09905f9878d5917351b1c185cc1106
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060062"
---
# <a name="quarantined-email-messages-in-eop"></a>In quarantaine geplaatste e-mailberichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken is quarantaine beschikbaar voor het vasthouden van potentieel gevaarlijke of ongewenste berichten.

Anti-malwarebeleid zet een bericht automatisch in quarantaine als *een* bijlage malware bevat. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.

Antispam polices quarantaine phishingberichten standaard, en leveren spam en bulk-e-mailberichten aan de map Ongewenste e-mail van de gebruiker. Maar u kunt ook antispambeleid maken en aanpassen om spam en bulk-e-mailberichten in quarantaine te plaatsen. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Zowel gebruikers als beheerders kunnen werken met in quarantaine geplaatste berichten:

- Beheerders kunnen werken met alle typen in quarantaine geplaatste berichten voor alle gebruikers. Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, phishing met hoge betrouwbaarheid of als gevolg van regels voor e-mailstroom (ook wel transportregels genoemd). Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

- Gebruikers kunnen werken met in quarantaine geplaatste berichten waar ze een geadresseerde zijn als het bericht in quarantaine is geplaatst als spam, bulk-e-mail of (vanaf april 2020) phishing. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

  Om te voorkomen dat gebruikers hun eigen in quarantaine geplaatste phishingberichten beheren, kunnen beheerders een andere actie configureren voor het **filteren** van phishing-e-mail in antispambeleid. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders en gebruikers kunnen fout-positieven melden bij Microsoft in quarantaine.

Zie Veelgestelde vragen over quarantaine voor [meer informatie](quarantine-faq.md)over quarantaine.
