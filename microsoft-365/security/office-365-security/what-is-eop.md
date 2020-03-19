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
description: Dit inleidende document helpt u inzicht te krijgen in Exchange Online Protection (EOP) en een aantal belangrijke terminologie. Dit geldt voor Office 365-klanten die exchange online-mailboxen in de cloud beschermen en eop-zelfstandige klanten die on-premises postvakken zoals Exchange Server 2016 beschermen.
ms.openlocfilehash: b1a8e9360005b31cf03c5e9921e3285ff7119926
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811314"
---
# <a name="what-is-exchange-online-protection-eop"></a>Wat is Exchange Online Protection (EOP)

Exchange Online Protection (EOP) is een cloudgebaseerde e-mailfilterservice die uw organisatie beschermt tegen spam en malware. Als u postvakken in Office 365 hebt, worden deze automatisch beschermd door EOP omdat deze deel uitmaken van de service. Dit geldt ook voor organisaties die postvakken hebben in zowel Office 365 als on-premise, wat algemeen bekend staat als een hybride scenario. EOP standalone is ook beschikbaar voor klanten die geen postvakken in de cloud hebben, maar hun on-premises mailboxen willen beschermen.

EOP probeert ongewenste e-rommel uit te filteren, zodat uw Postvak IN vrij blijft van inhoud die gebruikers niet willen zien. Normaal gesproken wordt ongewenste e-mail bezorgd in de map Ongewenste e-mail. Sommige gebruikers willen controleren om ervoor te zorgen dat het filteren doet wat ze willen, zodat de Map Ongewenste e-mail een gemakkelijke manier is voor gebruikers om zelf te controleren.  

> [!TIP]
> Het is een goede zaak wanneer junk of anderszins slechte e-mail gaat in de Junk Email map automatisch. De service doet wat nodig is op basis van de standaardstatus of de status van de aangepaste beheerdersinstellingen. Met andere woorden, gebruikers moeten zich geen zorgen maken over het zien van veel spam mail in de map Ongewenste e-mail. Als beheerders liever alle rommel uit het zicht verplaatsen, moet de quarantaine worden geconfigureerd. Zie het bericht [in quarantaine in het artikel van Office 365](quarantine-email-messages.md) voor meer informatie.

## <a name="important-terms"></a>Belangrijke termen

**Binnenkomend:** berichten die in Office 365 binnenkomen.

**Uitgaand**: berichten die uitgaan van Office 365.

**Intern**: Berichten die van iemand binnen de organisatie zijn tot iemand binnen de organisatie. Dit geldt ook voor klanten die zich in hybride scenario's bevinden en één postvak kan on-premises zijn en het andere postvak bevindt zich in de cloud.

**False Negative (FN)**: Spam en andere rommel die ten onrechte wordt verzonden in de inbox.

**False Positive (FP)**: Legitieme berichten die ten onrechte worden gemarkeerd als spam en in de map Ongewenste e-mail of quarantaine worden geplaatst.

**Spam, ook wel ongevraagde e-mail**genoemd: Dit komt in de vorm van commerciële reclame, kettingbrieven, politieke mailings, enz. Dit is e-mail waarvoor gebruikers zich niet aanmelden voor en van spammers die proberen om producten te werven of proberen om fraude te plegen.

**Phish**: Phishing is een speciaal type spam dat is bedoeld om u te verleiden tot het opgeven van persoonlijke informatie met het oog op het plegen van identiteitsdiefstal of fraude. Dit type bericht bevat meestal een kwaadaardige link of bijlage, maar niet altijd.

**Spoof**: Spoofing is wanneer spammers de FROM-header vervalsen, zodat berichten afkomstig lijken te zijn van iemand of ergens anders dan de werkelijke bron. Dit kan spam zijn, maar meestal gebruikt om phish-gebruikers.

**Imitatie:** Dit type spam is ook een manier om het afzenderadres te vervalsen, maar het wordt gedaan door een deel van de naam of het domein te wijzigen, zodat het lijkt op de echte bron. Bijvoorbeeld, Bi11@micr0s0ft.com, waar de "l" in Bill was eigenlijk de nummer elf en de "o" in Microsoft werd vervangen door het nummer nul.

**Bulk**: Bulk mail wordt meestal gevraagd door gebruikers, hoewel soms indirect wanneer bedrijven informatie verkopen aan andere bedrijven. Het is gebruikelijk dat gebruikers zich bewust aanmelden voor bulk mail (dwz newletters), maar vergeet later en denk dat het spam. Bulk mail wordt spam wanneer bulk mailers sturen meer dan gebruikers aanmelden en klachten niveaus te hoog.
