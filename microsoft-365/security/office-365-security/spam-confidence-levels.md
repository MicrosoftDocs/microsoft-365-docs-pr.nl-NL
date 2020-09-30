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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen informatie krijgen over het spam betrouwbaarheidsniveau (SCL) dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: 51d00b36ae826676f436c0a74617ddbbadf7a30a
ms.sourcegitcommit: 61ef32f802a1fb6d1e3a3aa005764ead32a7951e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48318238"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Spam niveau (SCL) in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken worden inkomende berichten via spam filteren in EOP en worden er een spam score aan toegewezen. Deze score wordt toegewezen aan een afzonderlijk spam niveau (SCL) dat wordt toegevoegd aan het bericht in een X-header. Een hogere SCL geeft aan dat een bericht waarschijnlijk spam moet zijn. EOP maakt actie op het bericht op basis van de SCL.

Wat de SCL betekenen, en de standaardacties die worden uitgevoerd op berichten worden beschreven in de volgende tabel. Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md)voor meer informatie over acties die u kunt uitvoeren op berichten op basis van de spam filtering Verdict.

****

|SCL|Definitie|Standaardactie|
|:---:|---|---|
|-1|Het bericht heeft het filteren op ongewenste e-mail overgeslagen. Het bericht is bijvoorbeeld afkomstig van een veilige afzender, is verzonden naar een veilige ontvanger of is afkomstig van een e-mail bronserver in de lijst met toegestane IP-adressen. Zie voor meer informatie [lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md).|Zorg dat u het bericht in het postvak in van de geadresseerden bezorgt.|
|0, 1|Spam filteren heeft bepaald dat het bericht geen spam opneemt.|Zorg dat u het bericht in het postvak in van de geadresseerden bezorgt.|
|5, 6|Spamfilters gemarkeerd als **spam**|U ontvangt het bericht naar de map Ongewenste E-mail van de geadresseerde.|
|aanhaling|Filteren van ongewenste e-mail markeert het bericht als **spam van hoge betrouwbaarheid**|U ontvangt het bericht naar de map Ongewenste E-mail van de geadresseerde.|
|

U zult merken dat SCL 2, 3, 4, 7 en 8 niet worden gebruikt bij het filteren van spam.

U kunt de e-mail stroom regels (ook wel transport-regels genoemd) gebruiken om de SCL op berichten te stempelen. Als u een e-mail stroom regel gebruikt om de SCL in te stellen, activeren de waarden 5 of 6 de actie spam filtert voor **spam**, en de waarden 7, 8 of 9 veroorzaken de spamfilter actie voor spam van **hoge betrouwbaarheid**. Zie voor meer informatie [de regels voor e-mail stroom gebruiken voor het instellen van het spam betrouwbaarheidsniveau (SCL) in berichten](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

Vergelijkbaar met de SCL wordt met het niveau voor bulk klachten (BCL) onjuiste bulk-e-mail (ook wel _grijze e-mail_genoemd) aangegeven. Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam). U configureert de BCL-drempelwaarde in antispambeleid. Zie [Antispambeleid in EOP](configure-your-spam-filter-policies.md), [bulk klachten niveau (BCL) in EOP)](bulk-complaint-level-values.md)en [Wat is het verschil tussen ongewenste e-mail en bulk-e-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)voor meer informatie.

****

![Het kleine pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Nieuw bij microsoft 365?** Ontdek gratis video cursussen voor **Microsoft 365-beheerders en IT-professionals**, aangeboden via LinkedIn learning.
