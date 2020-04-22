---
title: Spamvertrouwensniveau
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
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer te weten komen over hoe het spamvertrouwensniveau (SCL) bepaalt hoe waarschijnlijk of onwaarschijnlijk een bericht spam is en welke standaardacties spamfiltereren op berichten op basis van de SCL.
ms.openlocfilehash: 519bc48e7285283ad0570b8f3ac598615b132875
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638282"
---
# <a name="spam-confidence-level-scl-in-office-365"></a>Spambetrouwbaarheidsniveau (SCL) in Office 365

Wanneer Microsoft 365 (Exchange Online of standalone Exchange Online Protection (EOP) zonder Exchange Online-postvakken) een binnenkomend e-mailbericht ontvangt, wordt het bericht door spamgefilterd en krijgt het een spamscore toegewezen. Die score wordt toegewezen aan een individueel spambetrouwbaarheidsniveau (SCL) dat in een X-header aan het bericht is toegevoegd. Een hogere SCL geeft aan dat een bericht eerder spam is. De service onderneemt actie op basis van het bericht op basis van de SCL.

Wat de SCL betekent en de standaardacties die op berichten worden uitgevoerd, worden beschreven in de volgende tabel. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor meer informatie over acties die u uitvoeren op berichten op basis van het spamfiltervonnis.

||||
|:---:|---|---|
|**SCL**|**Definitie**|**Standaardactie**|
|-1|Het bericht heeft spamfilters overgeslagen. Het bericht is bijvoorbeeld van een veilige afzender, is verzonden naar een veilige ontvanger of is afkomstig van een e-mailbronserver op de LIJST met IP-toegestane. Zie [Lijsten met veilige afzenders maken in Office 365](create-safe-sender-lists-in-office-365.md)voor meer informatie.|Breng het bericht naar het postvak IN van de geadresseerden.|
|0, 1|Spamfiltering bepaalde dat het bericht geen spam was.|Breng het bericht naar het postvak IN van de geadresseerden.|
|5, 6|Spamfiltering heeft het bericht gemarkeerd als **Spam**|Breng het bericht naar de map Ongewenste e-mail van de geadresseerden.|
|9|Spamfiltering markeerde het bericht als **spam met een hoog vertrouwen**|Breng het bericht naar de map Ongewenste e-mail van de geadresseerden.|
|

U zult merken dat SCL 2, 3, 4, 7 en 8 niet worden gebruikt door spamfiltering.

U de regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen. Als u een regel voor e-mailstroom gebruikt om de SCL in te stellen, activeren de waarden 5 of 6 de spamfilteractie voor **Spam**en activeren de waarden 7, 8 of 9 de spamfilteractie voor **spam met een hoog vertrouwen**. Zie [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.

Vergelijkbaar met de SCL, de bulk klacht niveau (BCL) identificeert slechte bulk e-mail (ook bekend als _grijze e-mail)._ Een hogere BCL geeft aan dat een bulk e-mailbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam). U configureert de BCL-drempel in antispambeleid. Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md), [Bulkklachtenniveau (BCL) in Office 365](bulk-complaint-level-values.md)en [Wat is het verschil tussen ongewenste e-mail en bulke-mail configureren?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![Het korte pictogram voor](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New to Office 365?**         Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** die u worden aangeboden door LinkedIn Learning.|
