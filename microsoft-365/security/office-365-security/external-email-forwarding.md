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
ms.openlocfilehash: e578cadf6687e02c900299a75bdd00a9d6e5b2ee
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166145"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Automatische doorsturen van externe e-mail in Microsoft 365 instellen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als beheerder hebt u misschien te maken met bedrijfsvereisten om automatisch doorgestuurde berichten te beperken of te beheren voor externe geadresseerden (geadresseerden buiten uw organisatie). Het doorsturen van e-mail kan nuttig zijn, maar kan ook een beveiligingsrisico vormen vanwege de mogelijke openbaarmaking van gegevens. Aanvallers kunnen deze gegevens gebruiken om uw organisatie of partners aan te vallen.


De volgende typen automatische doorsturen zijn beschikbaar in Microsoft 365:

- Gebruikers kunnen regels [voor Postvak](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) IN zo configureren dat berichten automatisch worden doorgestuurd naar externe afzenders (opzettelijk of als gevolg van een gekromd account).

- Beheerders kunnen het doorsturen [van postvakken](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden. De beheerder kan kiezen of u alleen berichten wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.

U kunt uitgaand spamfilterbeleid gebruiken om automatische doorsturen naar externe geadresseerden te bepalen. Er zijn drie instellingen beschikbaar:

- **Automatisch:** automatisch extern doorsturen wordt geblokkeerd. Het intern automatisch doorsturen van berichten blijft werken. Dit is de standaardinstelling.
- **Aan:** Automatisch extern doorsturen is toegestaan en wordt niet beperkt.
- **Uit:** automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-bezorging (ook wel een NDR of niet-bezorgdbericht genoemd) voor de afzender.

Zie Uitgaande spamfilters configureren in EOP voor instructies over het configureren van [deze instellingen.](configure-the-outbound-spam-policy.md)

> [!NOTE]
>
> - Als u automatisch doorsturen uit schakelen, worden regels voor Postvak IN (gebruikers) of postvak doorsturen (beheerders) uitgeschakeld die berichten omleiden naar externe adressen.
>
> - Het automatisch doorsturen van berichten tussen interne gebruikers wordt niet beïnvloed door de instellingen van het beleid voor het filteren van uitgaande spam.
>
> - In het rapport Met automatisch doorgestuurde berichten kunt u informatie zien over gebruikers die berichten automatisch doorsturen naar [externe geadresseerden.](mfi-auto-forwarded-messages-report.md)

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>De manier waarop de beleidsinstellingen voor uitgaande spamfilters werken met andere besturingselementen voor automatisch doorsturen van e-mail

Als beheerder hebt u mogelijk andere besturingselementen geconfigureerd om het automatisch doorsturen van e-mail toe te staan of te blokkeren. Bijvoorbeeld:

- [Externe domeinen om](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) het automatisch doorsturen van e-mail naar bepaalde of alle externe domeinen toe te staan of te blokkeren.

- Voorwaarden en acties in [Exchange-regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) voor de e-mailstroom (ook wel transportregels genoemd) om automatisch doorgestuurde berichten naar externe geadresseerden te detecteren en te blokkeren.

Instellingen voor externe domeinen en regels voor de e-mailstroom zijn onafhankelijk van de instellingen in het beleid van het filter voor uitgaande spam. Bijvoorbeeld:

- U staat automatisch doorsturen toe voor een extern domein, maar u blokkeert het automatisch doorsturen van berichten in uitgaande spamfilterbeleidsregels. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.

- U staat automatisch doorsturen van uitgaande spamfilterbeleid toe, maar u gebruikt regels voor de e-mailstroom of instellingen van externe domeinen om automatisch doorgestuurde e-mail te blokkeren. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd door de regels voor de e-mailstroom of externe domeininstellingen.

Met deze functie onafhankelijkheid kunt u (bijvoorbeeld) automatisch doorsturen toestaan in beleidsregels voor uitgaande spamfilters, maar externe domeinen gebruiken om de externe domeinen te beheren naar wie gebruikers berichten kunnen doorsturen.

## <a name="the-blocked-email-forwarding-message"></a>Het geblokkeerde doorsturen van e-mailberichten

Wanneer een bericht wordt gedetecteerd als automatisch doorgestuurd  en het organisatiebeleid die activiteit blokkeert, wordt het bericht geretourneerd aan de afzender in een NDR die de volgende informatie bevat:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
