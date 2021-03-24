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
description: Beheerders kunnen meer informatie krijgen over de toepassingsorder van beveiligingen in Exchange Online Protection (EOP) en hoe de prioriteitswaarde in beveiligingsbeleid bepaalt welk beleid wordt toegepast.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b2a72420340993c027ec99820dcd3edddab1a304
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057938"
---
# <a name="order-and-precedence-of-email-protection"></a>Volgorde en prioriteit van e-mailbeveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, kan binnenkomende e-mail worden gemarkeerd met meerdere vormen van beveiliging. Bijvoorbeeld het ingebouwde anti-phishingbeleid in EOP dat beschikbaar is voor alle Microsoft 365-klanten en het krachtigere anti-phishingbeleid dat beschikbaar is voor Microsoft Defender voor Office 365-klanten. Berichten worden ook door meerdere detectiescans voor malware, spam, phishing, enzovoort gestuurd. Gezien al deze activiteiten kan het verwarrend zijn welk beleid wordt toegepast.

In het algemeen wordt een beleid dat is toegepast op een bericht, geïdentificeerd in de **koptekst X-Forefront-Antispam-Report** in de eigenschap **CAT (Categorie).** Zie Kopteksten [van antispamberichten voor meer informatie.](anti-spam-message-headers.md)

Er zijn twee belangrijke factoren die bepalen welk beleid wordt toegepast op een bericht:

- **De prioriteit van het type e-mailbeveiliging:** deze volgorde kan niet worden geconfigureerd en wordt in de volgende tabel beschreven:

  ****

  |Priority|E-mailbeveiliging|Categorie|Waar kunt u beheren|
  |---|---|---|---|
  |1|Malware|CAT:MALW|[Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)|
  |2|Phishing|CAT:PHSH|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |3|Hoogstwaarschijnlijk spam|CAT:HSPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |4|Spoofing|CAT:SPOOF|[Spoof intelligence configureren in EOP](learn-about-spoof-intelligence.md)|
  |5<sup>\*</sup>|Gebruikers imitatie (beveiligde gebruikers)|UIMP|[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)|
  |6<sup>\*</sup>|Domein-imitatie (beveiligde domeinen)|DIMP|[Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)|
  |7|Spam|CAT:SPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |8|Bulk|CAT:BULK|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Deze functies zijn alleen beschikbaar in anti-phishingbeleid in Microsoft Defender voor Office 365.

- De prioriteit van het **beleid:** Voor elk beveiligingstype (antispam, anti-malware, anti-phishing, enzovoort) is er een standaardbeleid dat voor iedereen geldt, maar u kunt aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde die de volgorde bepaalt waarin het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

  Als een gebruiker is gedefinieerd in meerdere beleidsregels van hetzelfde type, wordt alleen het beleid met de hoogste prioriteit op de gebruiker toegepast. Resterende beleidsregels van dat type worden niet geëvalueerd voor de gebruiker (inclusief het standaardbeleid).

Denk bijvoorbeeld aan de volgende anti-phishingbeleidsregels in Microsoft Defender voor Office 365 die van toepassing zijn op dezelfde gebruikers en een bericht dat is geïdentificeerd als gebruikersomitatie en spoofing:

  ****

  |Beleidsnaam|Priority|Gebruikers imiteren|Anti-spoofing|
  |---|---|---|---|
  |Beleid A|1|Aan|Uit|
  |Beleid B|2|Uit|Aan|
  |

1. Het bericht is gemarkeerd en wordt als spoof behandeld, omdat spoofing een hogere prioriteit heeft (4) dan imitatie van gebruikers (5).
2. Beleid A wordt toegepast op de gebruikers omdat deze een hogere prioriteit heeft dan Beleid B.
3. Op basis van de instellingen in Beleid A wordt er geen actie ondernomen op het bericht, omdat anti-spoofing is uitgeschakeld in het beleid.
4. Beleidsverwerking stopt, zodat beleid B nooit wordt toegepast op de gebruikers.

Omdat het mogelijk is dat dezelfde gebruikers opzettelijk of onbedoeld worden opgenomen in meerdere aangepaste beleidsregels van hetzelfde type, gebruikt u de volgende ontwerprichtlijnen voor aangepast beleid:

- Wijs een hogere prioriteit toe aan beleidsregels die van toepassing zijn op een klein aantal gebruikers en een lagere prioriteit aan beleidsregels die van toepassing zijn op een groot aantal gebruikers. Vergeet niet dat het standaardbeleid altijd als laatste wordt toegepast.
- Configureer uw beleid met een hogere prioriteit om striktere of meer gespecialiseerde instellingen te hebben dan beleidsregels met een lagere prioriteit.
- U kunt minder aangepaste beleidsregels gebruiken (gebruik alleen aangepaste beleidsregels voor gebruikers die striktere of meer gespecialiseerde instellingen nodig hebben).
