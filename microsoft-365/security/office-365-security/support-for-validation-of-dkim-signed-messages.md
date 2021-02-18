---
title: Ondersteuning voor validatie van met domeinsleutels geïdentificeerde e-mail (DKIM) ondertekende berichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a4c95148-a00c-4d12-85ed-88520b547d97
ms.collection:
- M365-security-compliance
description: Meer informatie over de validatie van DKIM-ondertekende berichten in Exchange Online Protection en Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9da41cc7918b36e1aa6a4a8cc48aea6cd2a865c6
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290259"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Ondersteuning voor validatie van DKIM-ondertekende berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online Protection (EOP) en Exchange Online ondersteunen beide inkomende validatie van[DKIM-berichten](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

DKIM controleert of een e-mailbericht niet door iemand anders is  vervalst en is verzonden vanaf het domein waar het vandaan komt.  De tekst bindt een e-mailbericht aan de organisatie die het heeft verzonden. DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden. Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4. (Zie Ondersteuning voor anonieme inkomende e-mailberichten via IPv6 voor meer informatie [over IPv6-ondersteuning.)](support-for-anonymous-inbound-email-messages-over-ipv6.md)

DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in DKIM-Signature koptekst van de berichtkoppen. De resultaten van een DKIM-Signature worden in de koptekst van Authentication-Results stempel voorzien. De tekst van de berichtkop ziet er ongeveer als volgt uit (contoso.com afzender is):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Zie RFC 7001 (berichtkopveld voor het[](https://www.rfc-editor.org/rfc/rfc7001.txt)aangeven van de status van de berichtverificatie) voor meer informatie over Authentication-Results berichtkoptekst. De DKIM-implementatie van Microsoft voldoet aan deze RFC.

Beheerders kunnen Exchange-regels voor [de e-mailstroom](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) maken voor de resultaten van DKIM-validatie. Met deze regels voor de e-mailstroom kunnen beheerders berichten filteren of routeeren naar behoefte.
