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
ms.openlocfilehash: 6a95c59a5cd629b704753c6c05c9b8069d9240b1
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537411"
---
# <a name="order-and-precedence-of-email-protection-in-office-365"></a>Volgorde en voorrang van e-mailbeveiliging in Office 365

In Office 365 wordt binnenkomende e-mail geëvalueerd door en kan daarom worden gemarkeerd door meerdere vormen van bescherming (malware, spam, phishing, enz.). Gezien al deze activiteiten kan het moeilijk zijn om te bepalen welk beleid is toegepast en in welke volgorde.

In het algemeen wordt een beleid dat op een bericht wordt toegepast, geïdentificeerd in de header **X-Forefront-Antispam-Report** in de eigenschap **CAT (Categorie).** Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie.

Er zijn twee belangrijke factoren die bepalen welk beleid wordt toegepast op een bericht:

- **De prioriteit van het type e-mailbeveiliging:** deze volgorde is niet configureerbaar en wordt beschreven in de volgende tabel:

  |||||
  |---|---|---|---|
  |**Prioriteit**|**E-mailbeveiliging**|**Categorie**|**Waar te beheren**|
  |1|Malware|CAT:MALW|[Anti-malwarebeleid configureren in Office 365](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |3|Hoogstwaarschijnlijk spam|CAT:HSPM|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |4|Spoofing|CAT:SPOOF|[Spoofinformatie configureren in Office 365](learn-about-spoof-intelligence.md)|
  |5|Spam|CAT:SPM|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |6|Bulk|CAT:BULK|[Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Imitatie van domeinen (beveiligde gebruikers)|DIMP (DIMP)|[ATP-beleid voor phishing configureren in Office 365](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Imitatie door gebruiker (beveiligde domeinen)|UIMP (UIMP)|[ATP-beleid voor phishing configureren in Office 365](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Deze functies zijn alleen beschikbaar in het ANTI-phishingbeleid van ATP.

- **De prioriteit van het beleid:** Voor elk beveiligingstype (anti-spam, anti-malware, anti-phishing, enz.) is er een standaardbeleid dat voor iedereen geldt, maar u vaak aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde die de volgorde bepaalt waarin het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

  Als een gebruiker is gedefinieerd in meerdere beleidsregels van hetzelfde type, wordt alleen het beleid met de hoogste prioriteit op deze beleidsregels toegepast. Alle resterende beleidsregels van dat type worden niet geëvalueerd voor de gebruiker (inclusief het standaardbeleid).

Denk bijvoorbeeld aan de volgende ATP-antiphishingbeleidsregels **die van toepassing zijn op dezelfde gebruikers**en een bericht dat is geïdentificeerd als zowel gebruikersimitatie als spoofing:

  |||||
  |---|---|---|---|
  |**ATP anti-phishing beleid**|**Prioriteit**|**Imitatie door gebruiker**|**Anti-spoofing**|
  |Beleid A|1|Aan|Uit|
  |Beleid B|2|Uit|Aan|
  |

1. Het bericht wordt gemarkeerd en behandeld als spoof, omdat spoofing een hogere prioriteit heeft (4) dan gebruikersimitatie (8).
2. Beleid A wordt toegepast op de gebruikers omdat het een hogere prioriteit heeft dan Beleid B.
3. Op basis van de instellingen in Beleid A wordt er geen actie ondernomen op het bericht, omdat anti-spoofing is uitgeschakeld in het beleid.
4. Beleidsverwerking stopt, dus beleid B wordt nooit toegepast op de gebruikers.

Omdat het mogelijk is dat dezelfde gebruikers opzettelijk of onbedoeld zijn opgenomen in meerdere aangepaste beleidsregels van hetzelfde type, gebruikt u de volgende ontwerprichtlijnen voor aangepast beleid:

- Wijs een hogere prioriteit toe aan beleid dat van toepassing is op een klein aantal gebruikers en een lagere prioriteit voor beleidsregels die van toepassing zijn op een groot aantal gebruikers. Houd er rekening mee dat het standaardbeleid altijd als laatste wordt toegepast.
- Configureer uw beleid met een hogere prioriteit om strengere of meer gespecialiseerde instellingen te hebben dan beleid met een lagere prioriteit.
- Overweeg minder aangepaste beleidsregels te gebruiken (gebruik alleen aangepast beleid voor gebruikers die strengere of meer gespecialiseerde instellingen nodig hebben).
