---
title: Externe e-mailberichten configureren en beheren, automatisch doorsturen, 5.7.520 toegang geweigerd, externe forwarding uitschakelen, de beheerder heeft extern doorsturen uitgeschakeld, beleid voor uitgaand Antispambeleid
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: .
ms.openlocfilehash: 76cd560c3b97bb67d25d2e4ff2c219669c3d4f0d
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658879"
---
# <a name="control-automatic-external-email-forwarding-in-microsoft-365"></a>Automatische doorsturen van e-mail instellen in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Als beheerder hebt u mogelijk een bedrijf nodig om automatisch doorgestuurde berichten te beperken of te beheren voor externe geadresseerden (geadresseerden buiten uw organisatie). Het doorsturen van e-mail kan handig zijn, maar kan ook een beveiligingsrisico vormen door de potentiële informatie. Kwaadwillenden kunnen deze gegevens gebruiken om uw organisatie of partners te vermoeden.

De volgende typen automatisch doorsturen zijn beschikbaar in Microsoft 365:

- Gebruikers kunnen [regels voor Postvak in](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) instellen om berichten automatisch door te sturen naar externe afzenders (een onopzettelijke of als gevolg van een gemanipuleerd account).

- Beheerders kunnen [Postvak doorsturen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) (ook wel _SMTP-doorsturen_ genoemd) configureren om berichten automatisch door te sturen naar externe geadresseerden. De beheerder kan kiezen of u berichten gewoon wilt doorsturen of kopieën van doorgestuurde berichten in het postvak wilt bewaren.

U kunt uitgaande spamfilter beleidsregels gebruiken om automatisch doorsturen naar externe geadresseerden te beheren. Drie instellingen zijn beschikbaar:

- **Automatisch**: automatisch extern doorsturen wordt geblokkeerd. Interne automatisch doorsturen van berichten blijft werken. Dit is de standaardinstelling.
- **Aan**: automatisch extern doorsturen is toegestaan en niet beperkt.
- **Off**: automatisch extern doorsturen is uitgeschakeld en resulteert in een rapport over niet-uitgevoerde bezorging (ook wel een NDR-of stuiter bericht) voor de afzender.

Zie [uitgaande spamfilters in EOP](configure-the-outbound-spam-policy.md)voor instructies voor het configureren van deze instellingen.

> [!NOTE]
>
> - Als u automatisch doorsturen uitschakelt, worden regels voor Postvak in (gebruikers) of postvak doorsturen (beheerders) uitgeschakeld waarmee berichten naar externe adressen worden doorgestuurd.
>
> - Het automatisch doorsturen van berichten tussen interne gebruikers heeft geen invloed op de instellingen in het filter beleid voor uitgaande spam.
>
> - U vindt informatie over gebruikers die berichten automatisch doorsturen naar externe geadresseerden in het [rapport met automatisch doorgestuurde berichten](mfi-auto-forwarded-messages-report.md).

## <a name="how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls"></a>Hoe de beleidsinstellingen voor het uitgaande spamfilter werken met andere besturingselementen voor automatisch doorsturen van e-mail

Als beheerder hebt u mogelijk al andere besturingselementen geconfigureerd, zodat u het automatisch doorsturen van e-mail toestaat of blokkeert. Bijvoorbeeld:

- [Externe domeinen](https://docs.microsoft.com/exchange/mail-flow-best-practices/remote-domains/remote-domains) voor het toestaan of blokkeren van automatische e-mail doorsturen naar bepaalde of alle externe domeinen.

- Voorwaarden en acties in Exchange [-e-mail stroom regels](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (ook wel een zogenaamde transportregels genoemd) voor het detecteren en blokkeren van automatisch doorgestuurde berichten naar externe geadresseerden.

De instellingen voor extern domein en de e-mail stroom regels zijn onafhankelijk van de instellingen in het filter beleid voor uitgaande spam. Bijvoorbeeld:

- U kunt het automatisch doorsturen van een extern domein toestaan, maar u blokkeert automatisch doorsturen in het filter beleid voor uitgaande spam. In dit voorbeeld worden automatisch doorgestuurde berichten geblokkeerd.

- U kunt automatisch doorsturen in het beleid voor uitgaande spam filteren, maar u kunt de e-mail stroom regels of de externe Domeininstellingen gebruiken om automatisch doorgestuurde e-mail te blokkeren. In dit voorbeeld wordt de instelling voor de e-mail stroom regels of het externe domein voor het automatisch doorsturen van berichten blokkeren.

Deze functie onafhankelijkheid biedt u de mogelijkheid om automatisch doorsturen in te schakelen in een uitgaand spamfilter beleid, maar externe domeinen gebruiken voor het beheren van de externe domeinen waarnaar gebruikers berichten kunnen doorsturen.

## <a name="the-blocked-email-forwarding-message"></a>Bericht met doorsturen van geblokkeerde e-mail

Wanneer een bericht wordt weergegeven als automatisch doorgeschakeld, en het organisatiebeleid deze activiteit *blokkeert* , wordt het bericht geretourneerd aan de afzender in een NDR met de volgende informatie:

`5.7.520 Access denied, Your organization does not allow external forwarding. Please contact your administrator for further assistance. AS(7555)`
