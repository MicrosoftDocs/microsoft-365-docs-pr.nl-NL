---
title: Volgorde en voorrang van e-mailbeveiliging in Office 365
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Beschrijft de toepassingsvolgorde van Office 365-beveiligingen en hoe de prioriteitswaarde in beveiligingsbeleid bepaalt welk beleid wordt toegepast.
ms.openlocfilehash: 9f2033b1ec066c1f8501ce019b8f8c7f3748fd15
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895333"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Volgorde en voorrang van e-mailbeveiliging in Office 365

Als Office 365-gebruiker kan uw binnenkomende e-mail worden gemarkeerd door meerdere vormen van bescherming. Bijvoorbeeld het ingebouwde EOP-antiphishingbeleid dat beschikbaar is voor alle Office 365-klanten en het robuustere ATP-antiphishingbeleid dat ook beschikbaar is voor klanten van Office 365 Advanced Threat Protection. Berichten passeren ook meerdere detectiescans voor malware, spam, phishing, enz. Gezien al deze activiteiten kan er enige verwarring bestaan over welk beleid wordt toegepast.

In het algemeen wordt een beleid dat op een bericht wordt toegepast, geïdentificeerd in de header **X-Forefront-Antispam-Report** in de eigenschap **CAT (Categorie).** Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie.

Er zijn twee belangrijke factoren die bepalen welk beleid wordt toegepast op een bericht:

- **De prioriteit van het type e-mailbeveiliging:** deze volgorde is niet configureerbaar en wordt beschreven in de volgende tabel:

  |||||
  |---|---|---|---|
  |**Priority**|**E-mailbeveiliging**|**Categorie**|**Waar te beheren**|
  |1|Malware|CAT:MALW|[Anti-malwarebeleid configureren in Office 365](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |3|Veel vertrouwen spam|CAT:HSPM|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |4|Spoofing|CAT:SPOOF|[Office 365 ATP antiphishing- en antiphishingbeleid instellen](set-up-anti-phishing-policies.md) <Br/><br/> [Meer informatie over spoofinformatie](learn-about-spoof-intelligence.md)|
  |5|Spam|CAT:SPM|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |6|Bulk|CAT:BULK|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Imitatie van domeinen|DIMP (DIMP)|[Office 365 ATP antiphishing- en antiphishingbeleid instellen](set-up-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Imitatie van gebruiker|UIMP (UIMP)|[Office 365 ATP antiphishing- en antiphishingbeleid instellen](set-up-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Deze functies zijn alleen beschikbaar in ATP.

- **De prioriteit van het beleid:** Voor elk beveiligingstype (anti-spam, anti-malware, anti-phishing, enz.) is er een standaardbeleid dat voor iedereen geldt, maar u aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde die de volgorde bepaalt waarin het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

  Als een gebruiker is gedefinieerd in meerdere aangepaste beleidsregels, wordt alleen het beleid met de hoogste prioriteit op deze opties toegepast. Alle resterende beleidsregels worden niet geëvalueerd voor de gebruiker (inclusief het standaardbeleid).

Denk bijvoorbeeld aan de volgende antiphishingbeleidsregels **die van toepassing zijn op dezelfde gebruikers**en een bericht dat is geïdentificeerd als zowel gebruikersimitatie als spoofing:

  |||||
  |---|---|---|---|
  |**Antispambeleid**|**Priority**|**Imitatie van gebruikers (ATP)**|**Anti-spoofing (EOP)**|
  |Beleid A|1|Op|Uit|
  |Beleid B|2|Uit|Op|
  |

1. Het bericht wordt gemarkeerd en behandeld als spoof, omdat spoofing een hogere prioriteit heeft (4) dan gebruikersimitatie (8).
2. Beleid A wordt toegepast op de gebruikers omdat het een hogere prioriteit heeft dan prioriteit B.
3. Op basis van de instellingen in Beleid A wordt er geen actie ondernomen op het bericht, omdat anti-spoofing is uitgeschakeld in het beleid.
4. Verwerking van antispambeleid stopt, zodat beleid B nooit wordt toegepast op de gebruikers.

Omdat er een potentieel is om veel gebruikers in veel aangepaste beleidsregels van hetzelfde type te hebben, u de volgende ontwerprichtlijnen voor aangepaste beleidsregels overwegen:

- Wijs een hogere prioriteit toe aan beleid dat van toepassing is op een klein aantal gebruikers en een lagere prioriteit voor beleidsregels die van toepassing zijn op een groot aantal gebruikers. Houd er rekening mee dat het standaardbeleid altijd als laatste wordt toegepast.
- Configureer uw beleid met een hogere prioriteit om strengere of meer gespecialiseerde instellingen te hebben dan beleid met een lagere prioriteit.
- Overweeg minder aangepaste beleidsregels te gebruiken (gebruik alleen aangepast beleid voor gebruikers die strengere of meer gespecialiseerde instellingen nodig hebben).
