---
title: Ondersteuning voor validatie van de domein sleutels met een ondertekende e-mail adres (DKIM)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Meer informatie over het valideren van DKIM ondertekende berichten in Exchange Online Protection en Exchange Online
ms.openlocfilehash: 91a01f89bb633a38d27ddd3f2945b8707643d7e9
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845057"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Ondersteuning voor validatie van DKIM-ondertekende berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Exchange Online Protection (EOP) en Exchange Online ondersteunen beide inkomende verificatie van domein sleutels geïdentificeerde E-mail ([dkim](https://www.rfc-editor.org/rfc/rfc6376.txt))-berichten.

DKIM valideert dat een e-mailbericht niet door iemand anders is *vervalst* en is verzonden vanaf het domein *waarnaar wordt aangegeven dat het e* -mailbericht afkomstig is. Met deze functie wordt een e-mailbericht verzonden naar de organisatie die het heeft verzonden. DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden. Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4. (Zie [ondersteuning voor anonieme inkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)) voor meer informatie over IPv6-ondersteuning.

DKIM controleert een digitaal ondertekend bericht dat wordt weergegeven in de koptekst DKIM-Signature van de berichtkoppen. De resultaten van een DKIM-Signature validatie worden in de Authentication-Results koptekst vastgelegd. De kop van het bericht wordt weergegeven op de volgende manier (waarbij contoso.com de afzender is):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Als u meer wilt weten over de koptekst van Authentication-Results, raadpleegt u RFC 7001 ([berichtkop veld voor het aangeven van de status van de berichtverificatie](https://www.rfc-editor.org/rfc/rfc7001.txt). De DKIM-implementatie van Microsoft vervalt met deze RFC'S.

Beheerders kunnen Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) maken (ook wel een zogenaamde transportregels genoemd) op de resultaten van de validatie van dkim. Met deze regels voor e-mail stroom kunnen beheerders berichten naar wens filteren of routeren.
