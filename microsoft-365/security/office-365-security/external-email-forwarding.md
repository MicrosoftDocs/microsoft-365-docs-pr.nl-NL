---
title: Extern doorsturen, Automatisch doorsturen, 5.7.520 Toegang geweigerd, extern doorsturen uitschakelen, uw beheerder heeft extern doorsturen en uitgaand antispambeleid uitgeschakeld
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 77f666e5eeceee3f5b324e5b9b6fac721c10e410
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286862"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Automatische doorsturen van externe e-mail in Microsoft 365 instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Als beheerder hebt u misschien te maken met bedrijfsvereisten om automatisch doorgestuurde berichten te beperken of te beheren voor externe geadresseerden (geadresseerden buiten uw organisatie). Het doorsturen van e-mail kan nuttig zijn, maar kan ook een beveiligingsrisico vormen vanwege de mogelijke openbaarmaking van gegevens. Aanvallers kunnen deze gegevens gebruiken om uw organisatie of partners aan te vallen.


De volgende typen automatische doorsturen zijn beschikbaar in Microsoft 365:

- Gebruikers kunnen regels [voor Postvak](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) IN zo configureren dat berichten automatisch worden doorgestuurd naar externe afzenders (opzettelijk of als gevolg van een gekromd account).

- Beheerders kunnen het doorsturen [van postvakken](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden. De beheerder kan kiezen of u alleen berichten wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.

U kunt uitgaand spamfilterbeleid gebruiken om automatische doorsturen naar externe geadresseerden te bepalen. Er zijn drie instellingen beschikbaar:

- **Automatisch:** automatisch extern doorsturen wordt geblokkeerd. Het intern automatisch doorsturen van berichten blijft werken. Dit is de standaardinstelling.
- **Aan:** Automatisch extern doorsturen is toegestaan en niet beperkt.
- **Uit:** automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-bezorging (ook wel een NDR of niet-bezorgdbericht genoemd) voor de afzender.

Zie Uitgaande spamfilters configureren in EOP voor instructies over het configureren van [deze instellingen.](configure-the-outbound-spam-policy.md)

> [!NOTE]
>
> - Als u automatisch doorsturen uit schakelen, worden regels voor Postvak IN (gebruikers) of postvak doorsturen (beheerders) uitgeschakeld die berichten omleiden naar externe adressen.
>
> - Het automatisch doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door de instellingen van het beleid voor het filteren van uitgaande spam.
>
> - In het rapport Met automatisch doorgestuurde berichten kunt u informatie zien over gebruikers die berichten automatisch doorsturen naar [externe geadresseerden.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>De manier waarop de beleidsinstellingen voor uitgaande spamfilters werken met andere besturingselementen voor het automatisch doorsturen van e-mail

Als beheerder hebt u mogelijk andere besturingselementen geconfigureerd om het automatisch doorsturen van e-mail toe te staan of te blokkeren. Bijvoorbeeld:

- [Externe domeinen om](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) het automatisch doorsturen van e-mail naar bepaalde of alle externe domeinen toe te staan of te blokkeren.

- Voorwaarden en acties in [Exchange-regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor de e-mailstroom (ook wel transportregels genoemd) om automatisch doorgestuurde berichten naar externe geadresseerden te detecteren en te blokkeren.

Instellingen voor externe domeinen en regels voor de e-mailstroom zijn onafhankelijk van het beleid voor het filteren van uitgaande spam. Bijvoorbeeld:

- U staat automatisch doorsturen toe voor een extern domein, maar u blokkeert automatisch doorsturen in beleidsregels voor uitgaande spamfilters. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.

- U staat automatisch doorsturen van uitgaande spamfilterbeleid toe, maar u gebruikt regels voor de e-mailstroom of instellingen van externe domeinen om automatisch doorgestuurde e-mail te blokkeren. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd door de regels voor de e-mailstroom of externe domeininstellingen.

Met deze functie onafhankelijkheid kunt u (bijvoorbeeld) automatisch doorsturen toestaan in beleidsregels voor uitgaande spamfilters, maar externe domeinen gebruiken om de externe domeinen te beheren naar wie gebruikers berichten kunnen doorsturen.

## <a name="blocked-email-forwarding-messages"></a>Geblokkeerde doorsturen van e-mailberichten

Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en  het uitgaande [spamfilterbeleid](configure-the-outbound-spam-policy.md) die activiteit blokkeert, wordt het bericht geretourneerd aan de afzender in een NDR die de volgende informatie bevat:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
