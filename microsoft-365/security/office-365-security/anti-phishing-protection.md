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
ms.service: O365-seccomp
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
description: Beheerders kunnen leren werken met de functies van bescherming tegen phishing in Exchange Online Protection (EOP) en Microsoft Defender voor Office 365.
ms.openlocfilehash: 51c539a47f1c137dbacbfaaf63212e1bb115860c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844510"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Bescherming tegen phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


*Phishing* is een aanval via een e-mailbericht dat probeert gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. Phishing bevat specifieke soorten phishing. Bijvoorbeeld:

- Met **Spear Phishingfilter** gerichte inhoud die speciaal is afgestemd op de gerichte geadresseerden (meestal na Reconnaissance van de aanvaller).

- **Whaling** wordt op de werknemers of andere high-value-doelen binnen een organisatie omgeleid voor de maximale kracht.

- **Misbruik van zakelijke e-mail (BEC)** maakt gebruik van vertrouwde vertrouwde afzenders (financiële medewerkers, klanten, vertrouwde partners, etc.) om geadresseerden te laten overgaan op betaling, het overdragen van bedragen of het onthullen van klantgegevens.

- **Ransomware** waarmee u uw gegevens kunt versleutelen en betaling hoeft te decoderen om te voorkomen dat u in phishingberichten begint. Met anti malafide bescherming kunt u versleutelde bestanden niet ontsleutelen, maar u kunt wel de eerste Phishingberichten detecteren die aan de campagne van Ransomware zijn gekoppeld. Zie [herstel van een Ransomware aanval in Microsoft 365](recover-from-ransomware.md)voor meer informatie over het herstellen van een Ransomware-aanval.

Met de toenemende complexiteit van aanvallen is het zelfs moeilijk voor gebruikers met een opgeleid, zodat ze een verfijnde malafide bericht kunnen vinden. Gelukkig, Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 kan u helpen.

## <a name="anti-phishing-protection-in-eop"></a>Bescherming tegen phishing in EOP

EOP (dat wil zeggen Microsoft 365-organisaties zonder Microsoft Defender for Office 365) bevat functies waarmee u uw organisatie tegen phishing kunt beschermen:

- **Spoof-intelligentie** : bekijk vervalste berichten van afzenders in interne en externe domeinen en sta die afzenders toe of blokkeer ze. Zie voor meer informatie [spoof Intelligence configureren in EOP](learn-about-spoof-intelligence.md).

- **Anti-phishingfilter in EOP** : Schakel spoof Intelligence in of uit, schakel de id van niet-geverifieerde afzenders in Outlook in of uit en geef de actie op voor geblokkeerde spoof afzenders (verplaatsen naar map Ongewenste e-mail of Quarantine). Zie [anti-phishings beleid in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.

- **Impliciete e-mail verificatie** : EOP verbetert standaardverificatie van e-mail verificatie voor inkomende E-mail ( [SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [dkim](use-dkim-to-validate-outbound-email.md)en [DMARC](use-dmarc-to-validate-email.md)) met de reputatie van de afzender, de geschiedenis van de afzender, de geschiedenis van de ontvanger, de gedrags analyse en andere geavanceerde technieken om vervalste afzenders te helpen identificeren. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Extra bescherming tegen phishing in Microsoft Defender voor Office 365

Microsoft Defender voor Office 365 bevat extra en meer geavanceerde functies voor het anti-phishing van functies:

- **Anti phishingfilter in Microsoft Defender voor Office 365** : Maak nieuwe aangepaste beleidsregels en configureer anti-impersonele instellingen (gebruikers en domeinen beschermen tegen imitatie), Postvak Intelligence-instellingen en instelbare geavanceerde phishing-trucs. Zie [anti phishingberichten configureren in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md)voor meer informatie. Zie [anti phishing Policies in Microsoft 365](set-up-anti-phishing-policies.md)voor meer informatie over de verschillen tussen een anti-phishing beleid in EOP en anti 365 Phishingfilter.

- **Campagne weergaven** : machine learning en andere heuristische analyses identificeren en analyseren van berichten die betrokken zijn bij gecoördineerde phishing-aanvallen tegen de hele service en uw organisatie. Zie [campagne weergaven in Microsoft Defender voor Office 365](campaigns.md)voor meer informatie.

- **Aanvals Simulator** : beheerders kunnen valse phishingberichten maken en ze verzenden naar interne gebruikers als een Education-programma. Zie [aanvals Simulator in Microsoft Defender voor Office 365](attack-simulator.md)voor meer informatie.

## <a name="other-anti-phishing-resources"></a>Andere anti malafide bronnen

- Voor eindgebruikers: [Bescherm uzelf tegen phishing en andere vormen van online fraude](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [Hoe Microsoft 365 het van-adres valideert om phishing te voorkomen](how-office-365-validates-the-from-address.md).
