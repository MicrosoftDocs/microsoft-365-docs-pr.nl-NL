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
description: Beheerders kunnen meer informatie krijgen over het betrouwbaarheidsniveau voor spam dat is toegepast op berichten in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e4fc20b7d7db5b85b5bdde02ab720fa26af2a4b5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167153"
---
# <a name="spam-confidence-level-scl-in-eop"></a>Betrouwbaarheidsniveau voor ongewenste e-mail in EOP

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken worden inkomende berichten in EOP door spamfilters heen geplaatst en krijgen ze een spamscore toegewezen. Deze score wordt toegesneden op een individueel spamver vertrouwelijkheidsniveau dat is toegevoegd aan het bericht in een X-koptekst. Een hogere SCL geeft aan dat de kans groter is dat het om een bericht gaat om spam. EOP voert een actie uit op het bericht op basis van de SCL.

Wat de SCL betekent en wat de standaardacties zijn die worden ondernomen op berichten, worden in de volgende tabel beschreven. Zie [Antispambeleid](configure-your-spam-filter-policies.md)configureren in EOP voor meer informatie over acties die u op berichten kunt uitvoeren op basis van het spamfilterbeleid.

****

|SCL|Definitie|Standaardactie|
|:---:|---|---|
|-1|Het bericht heeft het spamfilter overgeslagen. Het bericht is bijvoorbeeld afkomstig van een veilige afzender, is verzonden naar een veilige geadresseerde of is afkomstig van een e-mailbronserver op de lijst met toegestane IP-adressen. Zie Lijsten met veilige [afzenders maken in EOP](create-safe-sender-lists-in-office-365.md)voor meer informatie.|Bezorg het bericht in het Postvak IN van de geadresseerden.|
|0, 1|Het filteren van ongewenste e-mail bepaalt dat het bericht geen spam is.|Bezorg het bericht in het Postvak IN van de geadresseerden.|
|5, 6|Spamfilter heeft het bericht gemarkeerd als **Spam**|Bezorg het bericht in de map Ongewenste e-mail van de geadresseerde.|
|9|Spamfilter heeft het bericht gemarkeerd als **zeer snelle spam**|Bezorg het bericht in de map Ongewenste e-mail van de geadresseerde.|
|

SCL 2, 3, 4, 7 en 8 worden niet gebruikt door spamfilters.

U kunt regels voor de e-mailstroom (ook wel transportregels genoemd) gebruiken om de SCL op berichten te stempelen. Als u een regel voor de e-mailstroom gebruikt om de spamfilterregel in te stellen, activeren de waarden 5 of 6 de spamfilteractie voor **spam,** en activeren de waarden 7, 8 of 9 de spamfilteractie voor spam met hoge **betrouwbaarheid.** Zie Regels voor de e-mailstroom gebruiken om het betrouwbaarheidsniveau voor ongewenste e-mail [in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)

Net als bij de SCL identificeert het bulksgelaagde niveau (BCL) bad bulk-e-mail (ook wel _grijze e-mail genoemd)._ Een hogere BCL duidt op een bulk-e-mailbericht en levert vermoedelijk meer klachten op (en is dus vermoedelijk spam). U configureert de drempelwaarde voor BCL in antispambeleid. Zie Antispambeleid configureren [in EOP,](configure-your-spam-filter-policies.md)bulksgewijs klachtniveau [(BCL) in EOP)](bulk-complaint-level-values.md)en wat is het verschil tussen ongewenste e-mail en [bulkmail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

****

![Het korte pictogram voor LinkedIn Learning ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New voor Microsoft 365?** Ontdek gratis videocursussen voor **Microsoft 365-beheerders en IT-professionals,** aangeboden door LinkedIn Learning.
