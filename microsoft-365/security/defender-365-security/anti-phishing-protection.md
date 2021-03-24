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
description: Beheerders kunnen meer informatie krijgen over de anti-phishingbeveiligingsfuncties in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b0ca7a83e8e8d66bd58fddfc46f53df32f4f623c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059045"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Anti-phishingbeveiliging in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* is een e-mailaanval die gevoelige informatie probeert te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. Er zijn specifieke categorieën van phishing. Bijvoorbeeld:

- **Bij phishing** met speerpunten wordt gerichte, aangepaste inhoud gebruikt die specifiek is afgestemd op de beoogde geadresseerden (meestal na verkenning van de geadresseerden door de aanvaller).

- **Whaling** is gericht op leidinggevenden of andere doelen met een hoge waarde binnen een organisatie voor een maximaal effect.

- Zakelijke e-mailcompromitteerden **(BEC)** gebruikt vervalste vertrouwde afzenders (financiële verantwoordelijken, klanten, vertrouwde partners, enzovoort) om geadresseerden te verleiden tot het goedkeuren van betalingen, het overmaken van tegoeden of het onthullen van klantgegevens.

- **Ransomware** die uw gegevens versleutelt en betaling vereist om deze te ontsleutelen, begint bijna altijd in phishingberichten. Anti-phishingbeveiliging kan u niet helpen versleutelde bestanden te ontsleutelen, maar kan wel helpen bij het opsporen van de eerste phishingberichten die zijn gekoppeld aan de ransomware-campagne. Zie Herstellen van een [ransomware-aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een ransomware-aanval.

Met de toenemende complexiteit van aanvallen is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishingberichten te identificeren. Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 u helpen.

## <a name="anti-phishing-protection-in-eop"></a>Anti-phishingbeveiliging in EOP

EOP (dat wil zeggen Microsoft 365-organisaties zonder Microsoft Defender voor Office 365) bevat functies die uw organisatie kunnen beschermen tegen phishing-bedreigingen:

- **Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze. Zie Spoof [intelligence configureren in EOP voor meer informatie.](learn-about-spoof-intelligence.md)

- **Anti-phishingbeleid in EOP:** Schakel spoofinformatie in of uit, schakel niet-genauteerde afzender-identificatie in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders (ga naar map Ongewenste e-mail of quarantaine). Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.

- Impliciete e-mailverificatie: EOP verbetert standaardcontroles voor e-mailverificatie voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, geschiedenis van geadresseerden, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Aanvullende bescherming tegen phishing in Microsoft Defender voor Office 365

Microsoft Defender voor Office 365 bevat extra en geavanceerdere anti-phishingfuncties:

- **Anti-phishingbeleid in Microsoft Defender voor Office 365:** Nieuwe aangepaste beleidsregels maken, instellingen voor anti-imitatie configureren (gebruikers en domeinen beschermen tegen imitatie), instellingen voor postvakinformatie en aanpasbare geavanceerde phishingdrempels. Zie [Anti-phishingbeleid configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie. Zie [Anti-phishingbeleid in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen anti-phishingbeleid in EOP en anti-phishingbeleid in Defender voor Office 365.

- **Campagneweergaven:** Machine learning en andere heuristische acties identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishingaanvallen tegen de hele service en uw organisatie. Zie Campagneweergaven [in Microsoft Defender voor Office 365](campaigns.md)voor meer informatie.

- **Aanvalssimulator:** beheerders kunnen nep-phishingberichten maken en deze als onderwijshulpmiddel naar interne gebruikers verzenden. Zie Attack [Simulator in Microsoft Defender voor Office 365 voor meer informatie.](attack-simulator.md)

## <a name="other-anti-phishing-resources"></a>Andere anti-phishingbronnen

- Voor eindgebruikers: [Bescherm uzelf tegen phishingschema's en andere vormen van onlinefraude.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Hoe Microsoft 365 het Van-adres](how-office-365-validates-the-from-address.md)valideert om phishing te voorkomen.
