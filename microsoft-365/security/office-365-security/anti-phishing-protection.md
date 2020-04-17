---
title: Beveiliging tegen phishing in Office 365
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
ms.custom: TopSMBIssues
ms.collection:
- M365-security-compliance
description: Office 365 biedt standaard een verscheidenheid aan bescherming tegen phishing-aanvallen en ook via extra functies in Office 365 Advanced Threat Protection (ATP). In dit onderwerp worden de onlinebronnen geïntroduceerd die u gebruiken om antiphishingopties en -strategieën te leren en te implementeren in Office 365.
ms.openlocfilehash: 321d983f422bf4d231a772ca445bb74a7150a56e
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537423"
---
# <a name="anti-phishing-protection-in-office-365"></a>Beveiliging tegen phishing in Office 365

*Phishing* een e-mail aanval die probeert om gevoelige informatie te stelen in berichten die lijken te zijn van legitieme of vertrouwde afzenders. Er zijn specifieke categorieën van phishing. Bijvoorbeeld:

- **Spear phishing** maakt gebruik van zeer gerichte en aangepaste inhoud die specifiek is afgestemd op de beoogde ontvangers (meestal, na verkenning op de ontvangers door de aanvaller).

- **Walvisvangst** is gericht op leidinggevenden of andere hoogwaardige doelen binnen een organisatie voor een maximaal effect.

- **Business e-mail compromis (BEC)** maakt gebruik van vervalste vertrouwde afzenders (financiële functionarissen, klanten, vertrouwde partners, enz.) in een poging om de ontvanger te verleiden tot het goedkeuren van betalingen, het overbrengen van fondsen, of het vrijgeven van klantgegevens.

- **Ransomware** die uw gegevens versleutelt en betaling eist om deze te decoderen, begint bijna altijd in phishingberichten. Anti-phishing bescherming kan u niet helpen versleutelde bestanden te decoderen, maar het kan helpen bij het detecteren van de eerste phishing-berichten die zijn gekoppeld aan de ransomware campagne. Zie [Herstellen van een ransomware-aanval in Office 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een ransomware-aanval.

Met de toenemende complexiteit van aanvallen, is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishing-berichten te identificeren. Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Office 365 Advanced Threat Protection (ATP) helpen.

## <a name="anti-phishing-protection-in-eop"></a>Bescherming tegen phishing in EOP

EOP (dat wil zeggen Office 365-organisaties zonder ATP) bevat functies die uw organisatie kunnen beschermen tegen phishingbedreigingen:

- **Spoofinformatie:** bekijk vervalste berichten van afzenders in interne en externe domeinen en sta deze afzenders toe of blokkeer deze. Zie [Spoofinformatie configureren in Office 365](learn-about-spoof-intelligence.md)voor meer informatie.

- **Standaardbeleid tegen phishing:** Schakel spoofinformatie in of uit, schakel de identificatie van niet-geverifieerde afzenders in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders (ga naar de map Ongewenste e-mail of quarantaine). Zie [Beleid voor antiphishing configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.

- **Impliciete e-mailverificatie:** EOP verbetert standaard e-mailverificatiecontroles voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, ontvangstgeschiedenis, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren. Zie [E-mailverificatie in Office 365](email-validation-and-authentication.md)voor meer informatie.

## <a name="additional-anti-phishing-protection-in-office-365-atp"></a>Aanvullende bescherming tegen phishing in Office 365 ATP

Office 365 ATP bevat aanvullende en meer geavanceerde antiphishingfuncties:

- **ATP-antiphishingbeleid:** maak nieuwe aangepaste beleidsregels, configureer anti-imitatie-instellingen (bescherm gebruikers en domeinen tegen imitatie), instellingen voor postvakintelligentie en aanpasbare geavanceerde phishingdrempels. Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie. Zie [Antiphishingbeleid in Office 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen antiphishingbeleid en ATP-antiphishingbeleid.

- **Campagneweergaven:** Machine learning en andere heuristiek identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie. Zie [Campagneweergaven in Office 365 ATP](campaigns.md)voor meer informatie.

- **Aanval simulator:** Beheerders kunnen nep phishing-berichten te maken en stuur ze naar interne gebruikers als een educatieve tool. Zie [Attack Simulator in Office 365 ATP](attack-simulator.md)voor meer informatie.

## <a name="other-anti-phishing-resources"></a>Andere anti-phishing bronnen

- Voor eindgebruikers: [Bescherm uzelf tegen phishing-programma's en andere vormen van online fraude.](https://support.office.com/article/f84750b4-2f2c-46c3-89f6-e65f7f8c3546)

- [Hoe Office 365 het Van-adres valideert om phishing te voorkomen.](how-office-365-validates-the-from-address.md)
