---
title: Betrouwbaarheidsniveau voor spam
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over het betrouwbaarheidsniveau voor spam (SCL) dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 951bbcb5fcbcc7b7916ee1c34c4ab489d54b6667
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058490"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Betrouwbaarheidsniveau voor spam (SCL) in EOP

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, worden binnenkomende berichten via spamfilters in EOP gefilterd en krijgen ze een spamscore toegewezen. Die score wordt in kaart gebracht aan een individueel betrouwbaarheidsniveau voor spam (SCL) dat wordt toegevoegd aan het bericht in een X-header. Een hogere SCL geeft aan dat een bericht waarschijnlijker spam is. EOP onderneemt actie op basis van het bericht op basis van de SCL.

Wat de SCL betekent en de standaardacties die worden ondernomen op berichten, worden in de volgende tabel beschreven. Zie Antispambeleid configureren in EOP voor meer informatie over acties die u kunt uitvoeren op berichten op basis van de uitspraak over [spamfilters.](configure-your-spam-filter-policies.md)

****

|SCL|Definitie|Standaardactie|
|:---:|---|---|
|-1|Het bericht heeft spamfilters overgeslagen. Het bericht is bijvoorbeeld afkomstig van een veilige afzender, is verzonden naar een veilige geadresseerde of is afkomstig van een e-mailbronserver in de LIJST MET TOESTAAN VAN IP. Zie Lijsten met veilige afzenders maken in EOP voor [meer informatie.](create-safe-sender-lists-in-office-365.md)|Bezorg het bericht in het Postvak IN van de geadresseerden.|
|0, 1|Spamfilters hebben vastgesteld dat het bericht geen spam was.|Bezorg het bericht in het Postvak IN van de geadresseerden.|
|5, 6|Spamfilters hebben het bericht gemarkeerd als **Spam**|Bezorg het bericht bij de map Ongewenste e-mail van de geadresseerden.|
|9|Spamfilters hebben het bericht gemarkeerd als **spam met hoge betrouwbaarheid**|Bezorg het bericht bij de map Ongewenste e-mail van de geadresseerden.|
|

U ziet dat SCL 2, 3, 4, 7 en 8 niet worden gebruikt door spamfilters.

U kunt e-mailstroomregels (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen. Als u een regel voor de e-mailstroom gebruikt om de SCL in te stellen, worden met de waarden 5 of 6 de actie spamfilters voor **Spam** in gang gezet en worden de waarden 7, 8 of 9 de actie voor het filteren van spam met hoge betrouwbaarheid **ingesteld.** Zie Regels voor e-mailstroom gebruiken om het betrouwbaarheidsniveau voor [spam (SCL)](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)in berichten in te stellen voor meer informatie.

Net als bij de SCL identificeert het bulkklachtsniveau (BCL) slechte bulk-e-mail (ook wel _grijze e-mail genoemd)._ Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam). U configureert de BCL-drempel in antispambeleid. Zie Antispambeleid configureren in EOP , Bulk [complaint level (BCL) in EOP)](bulk-complaint-level-values.md)en Wat is het verschil tussen ongewenste [e-mail](configure-your-spam-filter-policies.md)en [bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)voor meer informatie.

****

![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.
