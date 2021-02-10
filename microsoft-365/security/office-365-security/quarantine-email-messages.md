---
title: E-mailberichten in quarantaine
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
description: Beheerders kunnen meer te weten komen over quarantaine in Exchange Online Protection (EOP) die mogelijk gevaarlijke of ongewenste berichten bevat.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4b111ea0d07453ef4280ec9e57247c8215420074
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167405"
---
# <a name="quarantined-email-messages-in-eop"></a>E-mailberichten in quarantaine in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
-   [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
-   [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken is quarantaine beschikbaar voor het plaatsen van mogelijk gevaarlijke of ongewenste berichten.

Een bericht wordt automatisch in  quarantaine geplaatst als malware wordt aangetroffen bij bijlagen. Zie [Antimalwarebeleid](configure-anti-malware-policies.md)configureren in EOP voor meer informatie.

Standaard worden phishingberichten in quarantaine tegen ongewenste e-mail in quarantaine geplaatst en worden spam en bulk-e-mailberichten naar de map Ongewenste e-mail van de gebruiker verzonden. Maar u kunt ook antispambeleid maken en aanpassen voor spam en bulk-e-mailberichten in quarantaine. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

Zowel gebruikers als beheerders kunnen in quarantaine geplaatste berichten gebruiken:

- Beheerders kunnen voor alle gebruikers werken met alle typen in quarantaine geplaatste berichten. Alleen beheerders kunnen werken met berichten die in quarantaine zijn geplaatst als malware, zeer vertrouwelijk phishing of als gevolg van regels voor de e-mailstroom (ook wel transportregels genoemd). Zie [Berichten en bestanden in quarantaine beheren als EOP-beheerder](manage-quarantined-messages-and-files.md).

- Gebruikers kunnen in quarantaine geplaatste berichten plaatsen waar ze geadresseerden zijn als het bericht in quarantaine is geplaatst als spam, bulk-e-mail of (vanaf april 2020) phishing. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

  Beheerders kunnen voorkomen dat gebruikers hun eigen phishingberichten in quarantaine  beheren door een andere actie te configureren voor het filteren van phishing-e-mails in antispambeleidsregels. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md) voor meer informatie.

- Beheerders en gebruikers kunnen fout-positieven rapporteren aan Microsoft in quarantaine.

Zie veelgestelde vragen over [quarantaine](quarantine-faq.md)voor meer informatie over quarantaine.
