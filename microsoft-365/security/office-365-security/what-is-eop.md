---
title: Wat is EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
ms.reviewer: andypunt
manager: dansimp
ms.date: 02/25/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 393b0050-7c7e-49e6-a03d-b1e09fe4de9e
description: Dit inleidende document helpt u bij het begrijpen van Exchange Online Protection (EOP) en een aantal belangrijke terminologie. Dit is van toepassing op klanten die exchange online-postvakken en eop-zelfstandige klanten beschermen die on-premises postvakken zoals Exchange Server 2016 beschermen.
ms.openlocfilehash: dc08507a80db8e15d2e08ff5b954dec1905cfada
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630915"
---
# <a name="what-is-exchange-online-protection-eop"></a>Wat is Exchange Online Protection (EOP)

Exchange Online Protection (EOP) is een cloudservice voor e-mailfiltering die uw organisatie beschermt tegen spam en malware. Als u postvakken in Microsoft 365 hebt, worden deze automatisch beschermd door EOP omdat deze deel uitmaken van de service. Dit geldt ook voor organisaties die mailboxen hebben in zowel Microsoft 365 als on-premise, wat algemeen bekend staat als een hybride scenario. EOP standalone is ook beschikbaar voor klanten die geen mailboxen in de cloud hebben, maar hun on-premises mailboxen willen beschermen.

EOP probeert rommel uit te filteren, zodat uw Postvak IN vrij blijft van inhoud die gebruikers niet willen zien. Normaal gesproken wordt ongewenste e-mail bezorgd in de map Ongewenste e-mail. Sommige gebruikers willen controleren om ervoor te zorgen dat het filteren doet wat ze willen, zodat de junk e-map is een gemakkelijke manier voor gebruikers om te controleren op hun eigen.  

> [!TIP]
> Het is een goede zaak wanneer junk of anderszins slechte e-mail gaat in de Junk Email map automatisch. De service doet wat nodig is op basis van de standaard- of de aangepaste beheerinstellingen. Met andere woorden, gebruikers moeten zich geen zorgen maken over het zien van veel spammail in de map Ongewenste e-mail. Als beheerders alle rommel liever uit het zicht verplaatsen, moet de quarantaine worden geconfigureerd. Zie het artikel [Voor e-mailberichten quarantaine](quarantine-email-messages.md) voor meer informatie.

## <a name="important-terms"></a>Belangrijke voorwaarden

**Binnenkomend:** berichten die in Microsoft 365 binnenkomen.

**Uitgaand:** Berichten die uit Microsoft 365 gaan.

**Intern**: Berichten die van iemand binnen de organisatie zijn naar iemand binnen de organisatie. Dit geldt ook voor klanten die zich in hybride scenario's bevinden en een postvak kan on-premises zijn en het andere postvak bevindt zich in de cloud.

**False Negative (FN)**: Spam en andere rommel die ten onrechte wordt verzonden in de inbox.

**False Positive (FP)**: Legitieme berichten die ten onrechte worden gemarkeerd als spam en in de map Ongewenste e-mail of Quarantaine worden geplaatst.

**Spam, ook wel bekend als ongevraagde e-mail**: Dit komt in de vorm van commerciële reclame, kettingbrieven, politieke mailings, enz. Dit is e-mail die gebruikers niet aanmelden voor en van spammers die proberen om producten te werven of een poging om fraude te plegen.

**Phish**: Phishing is een speciaal type spam dat is bedoeld om u te verleiden tot het opgeven van persoonlijke informatie met het oog op het plegen van identiteitsdiefstal of fraude. Dit type bericht bevat meestal een kwaadaardige link of bijlage, maar niet altijd.

**Spoof:** Spoofing is wanneer spammers de FROM-header vervalsen, zodat berichten afkomstig lijken te zijn van iemand of ergens anders dan de werkelijke bron. Dit kan spam zijn, maar meestal gebruikt om phish gebruikers.

**Imitatie**: Dit soort spam is ook een manier om de afzender adres te smeden, maar het wordt gedaan door het wijzigen van een deel van de naam of het domein, zodat het lijkt op de echte bron. Bijvoorbeeld, Bi11@micr0s0ft.com, waar de "l" in Bill was eigenlijk het nummer elf en de "o" in Microsoft werd vervangen door het nummer nul.

**Bulk**: Bulk mail wordt meestal gevraagd door gebruikers, hoewel soms indirect wanneer bedrijven informatie verkopen aan andere bedrijven. Het is gebruikelijk dat gebruikers zich opzettelijk aanmelden voor bulkmail (d.w.z. nieuwe brieven), maar vergeet later en denk dat het spam is. Bulk mail wordt spam wanneer bulk mailers meer verzenden dan gebruikers zich aanmelden en klachtenniveaus te hoog worden.
