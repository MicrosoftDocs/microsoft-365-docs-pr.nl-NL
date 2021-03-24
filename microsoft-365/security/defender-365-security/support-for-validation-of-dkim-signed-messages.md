---
title: Ondersteuning voor validatie van DKIM-ondertekende berichten (Domain Keys Identified Mail)
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
ms.openlocfilehash: 8695e25000390cf6c5d58adf63db1984c873d75b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058485"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Ondersteuning voor validatie van DKIM-ondertekende berichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online Protection (EOP) en Exchange Online ondersteunen beide inkomende validatie van[DKIM-berichten](https://www.rfc-editor.org/rfc/rfc6376.txt)(Domain Keys Identified Mail).

DKIM valideert dat een e-mailbericht niet is vervalst door iemand anders en is verzonden vanuit het domein *waar* het vandaan komt.  Er wordt een e-mailbericht aan de organisatie verbonden die het heeft verzonden. DKIM-verificatie wordt automatisch gebruikt voor alle berichten die met IPv6 worden verzonden. Microsoft 365 ondersteunt ook DKIM wanneer e-mail wordt verzonden via IPv4. (Zie Ondersteuning voor anonieme inkomende e-mailberichten [via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)voor meer informatie over IPv6-ondersteuning .)

DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de DKIM-Signature koptekst van de berichtkoppen. De resultaten van een DKIM-Signature validatie worden gestempeld in de Authentication-Results koptekst. De tekst van de berichtkoptekst lijkt op het volgende (waarbij contoso.com afzender is):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

> [!NOTE]
> Zie RFC 7001 (Veld voor berichtkoptekst voor het aangeven van de status van berichtverificatie) voor meer informatie over de Authentication-Results[koptekst.](https://www.rfc-editor.org/rfc/rfc7001.txt) De DKIM-implementatie van Microsoft voldoet aan deze RFC.

Beheerders kunnen [Exchange-regels](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor e-mailstroom (ook wel transportregels genoemd) maken op de resultaten van DKIM-validatie. Met deze regels voor e-mailstroom kunnen beheerders berichten zo nodig filteren of doorgestuurd worden.