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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over het spamvertrouwensniveau (SCL) dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.openlocfilehash: bc3a1e7e4b3e5f737b8861c14e0fd2c3d0841940
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208010"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Spam betrouwbaarheidsniveau (SCL) in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken gaan binnenkomende berichten door spamfiltering in EOP en krijgen ze een spamscore toegewezen. Die score wordt toegewezen aan een individueel spambetrouwbaarheidsniveau (SCL) dat in een X-header aan het bericht is toegevoegd. Een hogere SCL geeft aan dat een bericht eerder spam is. EOP onderneemt actie op basis van het bericht op basis van de SCL.

Wat de SCL betekent en de standaardacties die op berichten worden uitgevoerd, worden beschreven in de volgende tabel. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md)voor meer informatie over acties die u uitvoeren op berichten op basis van het spamfilteringsvonnis.

||||
|:---:|---|---|
|**SCL**|**Definitie**|**Standaardactie**|
|-1|Het bericht heeft spamfilters overgeslagen. Het bericht is bijvoorbeeld van een veilige afzender, is verzonden naar een veilige ontvanger of is afkomstig van een e-mailbronserver op de LIJST met IP-toegestane. Zie [Lijsten met veilige afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.|Breng het bericht naar het postvak IN van de geadresseerden.|
|0, 1|Spamfiltering bepaalde dat het bericht geen spam was.|Breng het bericht naar het postvak IN van de geadresseerden.|
|5, 6|Spamfiltering heeft het bericht gemarkeerd als **Spam**|Breng het bericht naar de map Ongewenste e-mail van de geadresseerden.|
|9|Spamfiltering markeerde het bericht als **spam met een hoog vertrouwen**|Breng het bericht naar de map Ongewenste e-mail van de geadresseerden.|
|

U zult merken dat SCL 2, 3, 4, 7 en 8 niet worden gebruikt door spamfiltering.

U de regels voor e-mailstroom (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen. Als u een regel voor e-mailstroom gebruikt om de SCL in te stellen, activeren de waarden 5 of 6 de spamfilteractie voor **Spam**en activeren de waarden 7, 8 of 9 de spamfilteractie voor **spam met een hoog vertrouwen**. Zie [Regels voor e-mailstroom gebruiken om het spamvertrouwensniveau (SCL) in berichten in te stellen](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)voor meer informatie.

Vergelijkbaar met de SCL, de bulk klacht niveau (BCL) identificeert slechte bulk e-mail (ook bekend als _grijze e-mail)._ Een hogere BCL geeft aan dat een bulk e-mailbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam). U configureert de BCL-drempel in antispambeleid. Zie [Antispambeleid configureren in EOP](configure-your-spam-filter-policies.md), [Bulkklachtenniveau (BCL) in EOP](bulk-complaint-level-values.md)en [Wat is het verschil tussen ongewenste e-mail en bulke-mail configureren?](what-s-the-difference-between-junk-email-and-bulk-email.md).

||
|:-----|
|![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Microsoft 365?** Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** die u worden aangeboden door LinkedIn Learning.|
