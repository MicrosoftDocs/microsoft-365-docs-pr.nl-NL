---
title: Ondersteuning voor validatie van DKIM-ondertekende berichten
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
ms.openlocfilehash: e2e91fe426348487fa4dfa8ef929d2d8129ffddc
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202135"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Ondersteuning voor validatie van DKIM-ondertekende berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online Protection (EOP) en Exchange Online ondersteuning voor inkomende verificatie van domein sleutels geïdentificeerde e-mail berichten ([dkim](https://www.rfc-editor.org/rfc/rfc6376.txt)). DKIM is een methode waarmee wordt gecontroleerd of een bericht is verzonden vanaf het domein waaruit het is afgeleid en dat het niet door iemand anders is vervalst. U ontvangt een e-mailbericht aan de organisatie die verantwoordelijk is voor het verzenden van het bericht. DKIM-verificatie wordt automatisch gebruikt voor alle berichten die via IPv6-communicatie worden verzonden. Microsoft 365 biedt nu ondersteuning voor DKIM wanneer mail wordt verzonden via IPv4. (Zie [ondersteuning voor anonieme inkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)) voor meer informatie over IPv6-ondersteuning.

DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de koptekst DKIM-Signature in de berichtkoppen. De resultaten van de validatie van een DKIM-handtekening worden voorzien van een stempel in de header voor verificatie-resultaten die voldoet aan de RFC'S 7001 ([bericht veldnamen veld waarmee de status van de berichtverificatie wordt aangegeven](https://www.rfc-editor.org/rfc/rfc7001.txt)). De kop van het bericht wordt weergegeven op de volgende manier (waarbij contoso.com de afzender is):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Beheerders kunnen Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel de zogenaamde transportregels genoemd) maken op de resultaten van een dkim-validatie om berichten naar wens te filteren of te routeren.
