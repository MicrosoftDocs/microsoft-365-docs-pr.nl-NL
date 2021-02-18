---
title: Bescherming tegen phishing
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
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Beheerders kunnen meer informatie krijgen over de functies voor beveiliging tegen phishing in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4fef8aa30f2b41c0ba84a6535969b12448e80562
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289051"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Beveiliging tegen phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

*Phishing* is een e-mailaanvallen die probeert gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. Er zijn specifieke categorieën phishing. Bijvoorbeeld:

- **Bij phishing** wordt gerichte, aangepaste inhoud gebruikt die specifiek is afgestemd op de specifieke geadresseerden (meestal nadat de aanvaller de ontvangers heeft aangevallen).

- **De organisatie is** gericht op leidinggevenden of andere doelen voor hoge waarden binnen een organisatie voor een maximumeffect.

- In **BEC (Business Email Compromise)** wordt gebruikgemaakt van vervalste vertrouwde afzenders (financiële officers, klanten, vertrouwde partners, enzovoort) om ontvangers te verleiden tot het goedkeuren van betalingen, het overmaken van tegoeden of het onthullen van klantgegevens.

- **Ransomware** die uw gegevens versleutelt en betaling vereist om deze te ontsleutelen, begint vrijwel altijd in phishing-berichten. Bescherming tegen phishing kan u niet helpen versleutelde bestanden te ontsleutelen, maar kan wel helpen bij het detecteren van de eerste phishingberichten die zijn gekoppeld aan de ransomware-campagne. Zie Herstel van een [ransomware-aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een ransomware-aanval.

Door de groeiende complexiteit van aanvallen is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishing-berichten te identificeren. Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 u helpen.

## <a name="anti-phishing-protection-in-eop"></a>Beveiliging tegen phishing in EOP

EOP (dat wil zeggen Microsoft 365-organisaties zonder Microsoft Defender voor Office 365) bevat functies die uw organisatie kunnen beschermen tegen phishing-bedreigingen:

- **Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze. Zie Spoof Intelligence configureren in EOP voor [meer informatie.](learn-about-spoof-intelligence.md)

- **Anti-phishingbeleid in EOP:** spoof intelligence in- of uitschakelen, afzender-id's met niet-geauteerde afzender in Outlook in- of uitschakelen en de actie opgeven voor geblokkeerde vervalste afzenders (verplaatsen naar map Ongewenste e-mail of quarantaine). Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP voor meer informatie.

- Impliciete e-mailverificatie: EOP verbetert standaard-e-mailverificatiecontroles op inkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met reputatie van afzenders, afzendergeschiedenis, geschiedenis van geadresseerden, analyse van analyses en andere geavanceerde technieken om vervalste afzenders te identificeren. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Aanvullende beveiliging tegen phishing in Microsoft Defender voor Office 365

Microsoft Defender voor Office 365 bevat aanvullende en geavanceerdere anti-phishingfuncties:

- **Anti-phishingbeleid in Microsoft Defender voor Office 365:** nieuw aangepast beleid maken, instellingen voor anti-imitatie configureren (gebruikers en domeinen beschermen tegen imitatie), instellingen voor postvakinformatie en aanpasbare geavanceerde drempelwaarden voor phishing. Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365 voor meer informatie.](configure-atp-anti-phishing-policies.md) Zie [Anti-phishingbeleidsregels in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Defender voor Office 365.

- **Campagneweergaven:** machine learning en andere heuristics identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie. Zie Campagneweergaven [in Microsoft Defender voor Office 365 voor meer informatie.](campaigns.md)

- **Aanvals simulator:** beheerders kunnen valse phishingberichten maken en deze als onderwijshulpmiddel naar interne gebruikers verzenden. Zie Attack [Simulator in Microsoft Defender voor Office 365 voor meer informatie.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Andere anti-phishing-informatiebronnen

- Voor eindgebruikers: [bescherm uzelf tegen phishingpogingen en andere vormen van onlinefraude.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Hoe Microsoft 365 het Van-adres valideert](how-office-365-validates-the-from-address.md)om phishing te voorkomen.
