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
description: Meer informatie over de validatie van door DKIM ondertekende berichten in Exchange Online Protection en Exchange Online
ms.openlocfilehash: 1abe517ed7922b60abb3a78436ed61b4d0b3ed55
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631203"
---
# <a name="support-for-validation-of-dkim-signed-messages"></a>Ondersteuning voor validatie van DKIM-ondertekende berichten

Exchange Online Protection (EOP) en Exchange Online ondersteunen inkomende validatie van[DKIM-berichten (Domain](https://www.rfc-editor.org/rfc/rfc6376.txt)Keys Identified Mail). DKIM is een methode om te valideren dat een bericht is verzonden vanuit het domein waarvan staat dat het afkomstig is van en dat het niet door iemand anders is vervalst. Het koppelt een e-mailbericht aan de organisatie die verantwoordelijk is voor het verzenden van het. DKIM-verificatie wordt automatisch gebruikt voor alle berichten die via IPv6-communicatie worden verzonden. Microsoft 365 ondersteunt nu ook DKIM wanneer e-mail via IPv4 wordt verzonden. (Zie [Ondersteuning voor anonieme binnenkomende e-mailberichten via IPv6](support-for-anonymous-inbound-email-messages-over-ipv6.md)voor meer informatie over IPv6-ondersteuning.)

DKIM valideert een digitaal ondertekend bericht dat wordt weergegeven in de header DKIM-Signature in de berichtkoppen. De resultaten van een DKIM-Signature-validatie worden gestempeld in de header Verificatieresultaten die voldoet aan RFC 7001[(Message Header Field for Indicating Message Authentication Status).](https://www.rfc-editor.org/rfc/rfc7001.txt) De tekst van de berichtkoptekst wordt weergegeven als de volgende tekst (waarbij contoso.com de afzender is):

 `Authentication-Results: <contoso.com>; dkim=pass (signature was verified) header.d=example.com;`

Beheerders kunnen [Exchange-mailstroomregels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel transportregels genoemd) maken voor de resultaten van een DKIM-validatie om berichten te filteren of te routeren als dat nodig is.
