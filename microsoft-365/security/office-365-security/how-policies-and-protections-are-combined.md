---
title: Volgorde en prioriteit van e-mailbeveiliging
keywords: beveiliging, malware, Microsoft 365, M365, beveiligingscentrum, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de volgorde van toepassingen van beveiliging in Exchange Online Protection (EOP) en hoe de prioriteitswaarde in beveiligingsbeleid bepaalt welk beleid wordt toegepast.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ec21be03280a8b7da122569d51186efc1f756a69
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286835"
---
# <a name="order-and-precedence-of-email-protection"></a>Volgorde en prioriteit van e-mailbeveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken kan binnenkomende e-mail worden gemarkeerd met meerdere beschermingsvormen. Bijvoorbeeld het ingebouwde anti-phishingbeleid in EOP dat beschikbaar is voor alle klanten van Microsoft 365 en het krachtigere anti-phishingbeleid dat beschikbaar is voor klanten van Microsoft Defender voor Office 365. Berichten worden ook door meerdere detectiescans voor malware, spam, phishing enzovoort verstuurd. Gezien deze activiteit kan er verwarring ontstaan over welk beleid wordt toegepast.

Over het algemeen wordt een beleid dat op een bericht is toegepast, geïdentificeerd in de kop **X-Forefront-Antispam-Report** in de eigenschap **CAT (Category).** Zie berichtkoppen tegen [ongewenste e-mail voor meer informatie.](anti-spam-message-headers.md)

Er zijn twee belangrijke factoren die bepalen welk beleid op een bericht wordt toegepast:

- **De prioriteit van het type e-mailbeveiliging:** deze bestelling kan niet worden geconfigureerd en wordt in de volgende tabel beschreven:

  ****

  |Priority|E-mailbeveiliging|Categorie|Waar beheren|
  |---|---|---|---|
  |1|Malware|KAT:MALW|[Antimalwarebeleid configureren in EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |3|Hoogstwaarschijnlijk spam|CAT:HSPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |4|Spoofing|CAT:SPOOF|[Spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Imitatie van gebruikers (beveiligde gebruikers)|UIMP|[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domein imitatie (beveiligde domeinen)|DIMP|[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)|
  |7|Spam|CAT:SPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |8|Bulk|KAT:BULK|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Deze functies zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365.

- De prioriteit van het **beleid:** Voor elk beveiligingstype (antispam, anti-malware, anti-phishing, enzovoort) is er een standaardbeleid dat op iedereen van toepassing is, maar u kunt aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde die de volgorde bepaalt waarin het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

  Als een gebruiker is gedefinieerd in meerdere beleidsregels van hetzelfde type, wordt alleen het beleid met de hoogste prioriteit toegepast. De resterende beleidsregels van dat type worden niet geëvalueerd voor de gebruiker (inclusief het standaardbeleid).

Denk bijvoorbeeld aan het volgende anti-phishingbeleid in Microsoft Defender voor Office 365 dat van toepassing is op dezelfde gebruikers, en een bericht dat wordt geïdentificeerd als gebruikers imitatie en spoofing:

  ****

  |Beleidsnaam|Priority|Gebruikers imitatie|Anti-spoofing|
  |---|---|---|---|
  |Beleid A|1|Aan|Uit|
  |Beleid B|2|Uit|Aan|
  |

1. Het bericht wordt gemarkeerd en behandeld als spoofing, omdat spoofing een hogere prioriteit heeft (4) dan gebruikers imitatie (5).
2. Beleid A wordt toegepast op de gebruikers omdat dit een hogere prioriteit heeft dan Beleid B.
3. Op basis van de instellingen in Beleid A wordt er geen actie ondernomen op het bericht, omdat antivervalsing is uitgeschakeld in het beleid.
4. De verwerking van beleid stopt, zodat beleid B nooit op de gebruikers wordt toegepast.

Gebruik de volgende ontwerprichtlijnen voor aangepaste beleidsregels omdat het mogelijk is dat dezelfde gebruikers bewust of per ongeluk zijn opgenomen in meerdere aangepaste beleidsregels van hetzelfde type:

- Wijs een hogere prioriteit toe aan beleid dat van toepassing is op een klein aantal gebruikers en een lagere prioriteit aan beleidsregels die van toepassing zijn op een groot aantal gebruikers. Let op: het standaardbeleid wordt altijd als laatste toegepast.
- Configureer uw beleid met een hogere prioriteit als u striktere of meer gespecialiseerde instellingen wilt instellen dan beleid met een lagere prioriteit.
- Overweeg om minder aangepaste beleidsregels te gebruiken (gebruik alleen aangepaste beleidsregels voor gebruikers die striktere of meer gespecialiseerde instellingen nodig hebben).
