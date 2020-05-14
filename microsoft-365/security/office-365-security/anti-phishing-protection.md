---
title: Bescherming tegen phishing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- M365-security-compliance
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over de anti-phishingbeveiligingsfuncties in Exchange Online Protection (EOP) en Office 365 Advanced Threat Protection (Office 365 ATP).
ms.openlocfilehash: 3c15c67f059793c904641a70c12cd072bb69e2aa
ms.sourcegitcommit: 98782ee4497d72232462c51a3071fae313282980
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44222727"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Bescherming tegen phishing in Microsoft 365

*Phishing* een e-mail aanval die probeert om gevoelige informatie te stelen in berichten die lijken te zijn van legitieme of vertrouwde afzenders. Er zijn specifieke categorieën van phishing. Bijvoorbeeld:

- **Spear phishing** maakt gebruik van zeer gerichte en aangepaste inhoud die specifiek is afgestemd op de beoogde ontvangers (meestal, na verkenning op de ontvangers door de aanvaller).

- **Walvisvangst** is gericht op leidinggevenden of andere hoogwaardige doelen binnen een organisatie voor een maximaal effect.

- **Business e-mail compromis (BEC)** maakt gebruik van vervalste vertrouwde afzenders (financiële functionarissen, klanten, vertrouwde partners, enz.) in een poging om de ontvanger te verleiden tot het goedkeuren van betalingen, het overbrengen van fondsen, of het vrijgeven van klantgegevens.

- **Ransomware** die uw gegevens versleutelt en betaling eist om deze te decoderen, begint bijna altijd in phishingberichten. Anti-phishing bescherming kan u niet helpen versleutelde bestanden te decoderen, maar het kan helpen bij het detecteren van de eerste phishing-berichten die zijn gekoppeld aan de ransomware campagne. Voor meer informatie over het herstellen van een ransomware aanval, zie [Herstellen van een ransomware aanval in Microsoft 365](recover-from-ransomware.md).

Met de toenemende complexiteit van aanvallen, is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishing-berichten te identificeren. Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Office 365 Advanced Threat Protection (Office 365 ATP) helpen.

## <a name="anti-phishing-protection-in-eop"></a>Bescherming tegen phishing in EOP

EOP (dat wil zeggen Microsoft 365-organisaties zonder ATP) bevat functies die uw organisatie kunnen beschermen tegen phishingbedreigingen:

- **Spoof-intelligentie**: bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze. Zie [Spoofinformatie configureren in EOP](learn-about-spoof-intelligence.md)voor meer informatie.

- **Anti-phishingbeleid in EOP:** Schakel spoofinformatie in of uit, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders (ga naar de map Ongewenste e-mail of quarantaine). Zie [Beleid voor antiphishing configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.

- **Impliciete e-mailverificatie:** EOP verbetert standaard e-mailverificatiecontroles voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, ontvangstgeschiedenis, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Aanvullende bescherming tegen phishing in Office 365 ATP

Office 365 ATP bevat aanvullende en meer geavanceerde antiphishingfuncties:

- **ATP-antiphishingbeleid:** maak nieuwe aangepaste beleidsregels, configureer anti-imitatie-instellingen (bescherm gebruikers en domeinen tegen imitatie), instellingen voor postvakintelligentie en aanpasbare geavanceerde phishingdrempels. Zie [ATP-antiphishingbeleid configureren in Microsoft 365](configure-atp-anti-phishing-policies.md)voor meer informatie. Zie [Antiphishingbeleid in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen antiphishingbeleid en ATP-antiphishingbeleid.

- **Campagneweergaven:** Machine learning en andere heuristiek identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie. Zie [Campagneweergaven in Office 365 ATP](campaigns.md)voor meer informatie.

- **Aanval simulator:** Beheerders kunnen nep phishing-berichten te maken en stuur ze naar interne gebruikers als een educatieve tool. Zie [Attack Simulator in Office 365 ATP](attack-simulator.md)voor meer informatie.

## <a name="other-anti-phishing-resources"></a>Andere anti-phishing bronnen

- Voor eindgebruikers: [Bescherm uzelf tegen phishing-programma's en andere vormen van online fraude.](https://support.office.com/article/protect-yourself-from-phishing-schemes-and-other-forms-of-online-fraud-be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen.](how-office-365-validates-the-from-address.md)
