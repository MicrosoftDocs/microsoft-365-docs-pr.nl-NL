---
title: Volgorde en prioriteit van e-mail beveiliging
keywords: beveiliging, malware, Microsoft 365, M365, Security Center, ATP, Microsoft Defender ATP, Office 365 ATP, Azure ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie vinden over de toepassings volgorde van beveiligingsregels in Exchange Online Protection (EOP) en de manier waarop de prioriteitswaarde in beveiligingsbeleid bepaalt welk beleid wordt toegepast.
ms.openlocfilehash: 6b17a524fb9dfbf5e33604c2ec26a678befc8834
ms.sourcegitcommit: 153f413402f93b79be421741f3b9fed318d6d270
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/20/2020
ms.locfileid: "48600283"
---
# <a name="order-and-precedence-of-email-protection"></a>Volgorde en prioriteit van e-mail beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken kunnen inkomende e-mail door meerdere vormen van bescherming worden gemarkeerd. Het ingebouwde anti-virus beleid van EOP dat beschikbaar is voor alle Microsoft 365-klanten en het krachtigere ATP anti-phishingfilter dat ook beschikbaar is voor Office 365 Advanced Threat Protection (Office 365 ATP)-klanten. Berichten lopen ook door meerdere detectie scans voor malware, spam, phishing en dergelijke. Voor al deze activiteit is er sprake van enige verwarring waarop het beleid wordt toegepast.

In het algemeen wordt een beleid dat wordt toegepast op een bericht, aangeduid met de kop **X-Forefront-spam-report** in de eigenschap **Cat (categorie)** . Zie [anti spambericht koppen](anti-spam-message-headers.md)voor meer informatie.

Er zijn twee belangrijke factoren die bepalen welke beleidsregels op een bericht worden toegepast:

- **De prioriteit van het type e-mail beveiliging**: deze volgorde kan niet worden geconfigureerd en wordt beschreven in de volgende tabel:

  ****

  |Priority|E-mail beveiliging|Categorie|Waar beheren|
  |---|---|---|---|
  |1|Malware|CAT: MALW|[Beleidsregels voor anti-malware configureren in EOP](configure-anti-malware-policies.md)|
  |3|Phishing|CAT: PHSH|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |driefasig|Hoogstwaarschijnlijk spam|CAT: HSPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |3|Spoofing|CAT: SPOOF|[Spoof informatie configureren in EOP](learn-about-spoof-intelligence.md)|
  |vijf<sup>\*</sup>|Gebruikers imitatie (beveiligde domeinen)|UIMP|[ATP-beleid tegen phishing configureren](configure-atp-anti-phishing-policies.md)|
  |zes<sup>\*</sup>|Imitatie van domein (beveiligde gebruikers)|DIMP|[ATP-beleid tegen phishing configureren](configure-atp-anti-phishing-policies.md)|
  |7,5|Spam|KAT: SPM|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |8:00|Bulk|CAT: BULKSGEWIJS|[Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)|
  |

  <sup>\*</sup> Deze functies zijn alleen beschikbaar in het ATP anti-phishings beleid.

- **De prioriteit van het beleid**: voor elk beveiligingstype (antispam, anti-malware, anti-phishing, etc.) is er een standaardbeleid voor iedereen, maar u kunt wel aangepaste beleidsregels maken die van toepassing zijn op specifieke gebruikers. Elk aangepast beleid heeft een prioriteitswaarde waarmee wordt bepaald in welke volgorde het beleid wordt toegepast. Het standaardbeleid wordt altijd als laatste toegepast.

  Als een gebruiker is gedefinieerd in meerdere beleidsregels van hetzelfde type, wordt alleen het beleid met de hoogste prioriteit toegepast. Resterende beleidsregels van dat type worden niet geëvalueerd voor de gebruiker (met inbegrip van het standaardbeleid).

Kijk bijvoorbeeld naar het volgende ATP anti-phishings beleid **dat van toepassing is op dezelfde gebruikers**en een bericht dat wordt geïdentificeerd als gebruikers imitatie en spoofing:

  ****

  |ATP anti-phishingfilter|Priority|Gebruikers imitatie|Anti-spoofing|
  |---|---|---|---|
  |Beleid A|1|Aan|Uit|
  |Beleid B|3|Uit|Aan|
  |

1. Het bericht is gemarkeerd en wordt behandeld als spoof omdat het gebruik van spoofing een hogere prioriteit heeft dan de gebruikers imitatie (8).
2. Beleid A wordt toegepast op de gebruikers omdat dit een hogere prioriteit heeft dan de beleidsregels B.
3. Afhankelijk van de instellingen in beleid A, wordt er geen actie ondernomen voor het bericht, omdat anti-spoofing voor het beleid is uitgeschakeld.
4. Beleidsverwerking stopt, zodat de beleidsregels nooit op de gebruikers worden toegepast.

Aangezien het mogelijk is dat dezelfde gebruikers in meerdere aangepaste beleidsregels of onbedoelde functies in meerdere aangepaste beleidsregels van hetzelfde type zijn opgenomen, kunt u de volgende ontwerprichtlijnen voor aangepaste beleidsregels gebruiken:

- Wijs een hogere prioriteit toe aan beleidsregels die van toepassing zijn op een klein aantal gebruikers en een lagere prioriteit voor beleidsregels die van toepassing zijn op een groot aantal gebruikers. Let op: het standaardbeleid wordt altijd de laatste toegepast.
- Configureer uw beleidsregels voor een hoge prioriteit zodat u strengere of gespecialiseerde instellingen moet hebben dan een beleid voor lagere prioriteit.
- U kunt minder aangepaste beleidsregels gebruiken (gebruik alleen aangepaste beleidsregels voor gebruikers met een strikte of gespecialiseerde instellingen).
