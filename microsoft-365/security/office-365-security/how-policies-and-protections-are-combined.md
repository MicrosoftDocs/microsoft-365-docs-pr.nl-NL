---
title: Volgorde en voorrang van e-mailbeveiliging
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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de toepassingsvolgorde van beveiligingen in Exchange Online Protection (EOP) en hoe de prioriteitswaarde in het beveiligingsbeleid bepaalt welk beleid wordt toegepast.
ms.openlocfilehash: 176d39a240d49e0118b4bb8e8cee52a6e7c61b0e
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209437"
---
# <a name="order-and-precedence-of-email-protection"></a>Volgorde en voorrang van e-mailbeveiliging

In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken, kan binnenkomende e-mail worden gemarkeerd door meerdere vormen van bescherming. Bijvoorbeeld het ingebouwde EOP-antiphishingbeleid dat beschikbaar is voor alle Microsoft 365-klanten en het robuustere ATP-antiphishingbeleid dat ook beschikbaar is voor Office 365 Advanced Threat Protection (Office 365 ATP)-klanten. Berichten passeren ook meerdere detectiescans voor malware, spam, phishing, enz. Gezien al deze activiteiten kan er enige verwarring bestaan over welk beleid wordt toegepast.

In het algemeen wordt een beleid dat op een bericht wordt toegepast, geïdentificeerd in de header **X-Forefront-Antispam-Report** in de eigenschap **CAT (Categorie).** Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie.

Er zijn twee belangrijke factoren die bepalen welk beleid wordt toegepast op een bericht:

- **De prioriteit van het type e-mailbeveiliging:** deze volgorde is niet configureerbaar en wordt beschreven in de volgende tabel:

  |||||
  |---|---|---|---|
  |**Prioriteit**|**E-mailbeveiliging**|**Categorie**|**Waar te beheren**|
  |1|Malware|CAT:MALW|[Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |3|Hoogstwaarschijnlijk spam|CAT:HSPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |4|Spoofing|CAT:SPOOF|[Spoofinformatie configureren in EOP](learn-about-spoof-intelligence.md)|
  |5|Spam|CAT:SPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |6|Bulk|CAT:BULK|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |7<sup>\*</sup>|Imitatie van domeinen (beveiligde gebruikers)|DIMP (DIMP)|[ATP-beleid tegen phishing configureren](configure-atp-anti-phishing-policies.md)|
  |8<sup>\*</sup>|Imitatie door gebruiker (beveiligde domeinen)|UIMP (UIMP)|[ATP-beleid tegen phishing configureren](configure-atp-anti-phishing-policies.md)|
  |

  <sup>\*</sup>Deze functies zijn alleen beschikbaar in het ANTI-phishingbeleid van ATP.

- **De prioriteit van het beleid:** Voor elk beveiligingstype (anti-spam, anti-malware, anti-phishing, enz.) is er een standaardbeleid dat voor iedereen geldt, maar u aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde die de volgorde bepaalt waarin het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

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
