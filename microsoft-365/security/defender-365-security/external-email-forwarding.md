---
title: Externe e-mail doorsturen configureren en beheren, Automatisch doorsturen, 5.7.520 Toegang geweigerd, extern doorsturen uitschakelen, Uw beheerder heeft extern doorsturen, uitgaand antispambeleid uitgeschakeld
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
ms.openlocfilehash: 0f42da077ca84341824fad01fcb23eae976336a1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057965"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Automatische externe e-mail doorsturen in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Als beheerder hebt u mogelijk bedrijfsvereisten voor het beperken of beheren van automatisch doorgestuurde berichten naar externe geadresseerden (geadresseerden buiten uw organisatie). E-mail doorsturen kan handig zijn, maar kan ook een beveiligingsrisico opleveren vanwege de mogelijke openbaarmaking van informatie. Aanvallers kunnen deze informatie gebruiken om uw organisatie of partners aan te vallen.


De volgende typen automatische doorsturen zijn beschikbaar in Microsoft 365:

- Gebruikers kunnen regels [voor Postvak IN zo](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) configureren dat berichten automatisch worden doorgestuurd naar externe afzenders (bewust of als gevolg van een gekromd account).

- Beheerders kunnen het [doorsturen van postvakken](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden. De beheerder kan kiezen of u alleen berichten wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.

U kunt beleidsregels voor uitgaand spamfilter gebruiken om automatische doorsturen naar externe geadresseerden te controleren. Er zijn drie instellingen beschikbaar:

- **Automatisch:** Automatisch extern doorsturen wordt geblokkeerd. Interne automatische doorsturen van berichten blijft werken. Dit is de standaardinstelling.
- **Op**: Automatisch extern doorsturen is toegestaan en niet beperkt.
- **Uit:** Automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-bezorging (ook wel een NDR- of bouncebericht genoemd) naar de afzender.

Zie Uitgaande [spamfilters](configure-the-outbound-spam-policy.md)configureren in EOP voor instructies over het configureren van deze instellingen.

> [!NOTE]
>
> - Als u automatisch doorsturen uit schakelt u regels voor Postvak IN (gebruikers) of postvak doorsturen (beheerders) uit die berichten omleiden naar externe adressen.
>
> - Het automatisch doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door de instellingen in beleidsregels voor uitgaand spamfilter.
>
> - U kunt informatie zien over gebruikers die berichten automatisch doorsturen naar externe geadresseerden in het [rapport Automatisch doorgestuurde berichten.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Hoe de beleidsinstellingen voor uitgaand spamfilter werken met andere besturingselementen voor automatisch doorsturen van e-mail

Als beheerder hebt u mogelijk al andere besturingselementen geconfigureerd om automatisch doorsturen van e-mail toe te staan of te blokkeren. Bijvoorbeeld:

- [Externe domeinen om](/exchange/mail-flow-best-practices/remote-domains/remote-domains) automatische doorsturen van e-mail naar bepaalde of alle externe domeinen toe te staan of te blokkeren.

- Voorwaarden en acties in [Exchange-regels](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor e-mailstroom (ook wel transportregels genoemd) om automatisch doorgestuurde berichten naar externe geadresseerden te detecteren en te blokkeren.

Externe domeininstellingen en e-mailstroomregels zijn onafhankelijk van de instellingen in beleidsregels voor uitgaand spamfilter. Bijvoorbeeld:

- U staat automatisch doorsturen voor een extern domein toe, maar u blokkeert automatisch doorsturen in beleidsregels voor uitgaand spamfilter. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.

- U staat automatisch doorsturen toe in beleidsregels voor uitgaand spamfilter, maar u gebruikt regels voor e-mailstroom of externe domeininstellingen om automatisch doorgestuurde e-mail te blokkeren. In dit voorbeeld blokkeren de regels voor e-mailstroom of externe domeininstellingen automatisch doorgestuurde berichten.

Met deze functieafhankelijkheid kunt u (bijvoorbeeld) automatisch doorsturen toestaan in beleidsregels voor uitgaand spamfilter, maar externe domeinen gebruiken om de externe domeinen te beheren waar gebruikers berichten naar kunnen doorsturen.

## <a name="blocked-email-forwarding-messages"></a>Geblokkeerde e-mailberichten doorsturen

Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd en  het beleid voor uitgaand [spamfilter](configure-the-outbound-spam-policy.md) deze activiteit blokkeert, wordt het bericht geretourneerd aan de afzender in een NDR die de volgende informatie bevat:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`