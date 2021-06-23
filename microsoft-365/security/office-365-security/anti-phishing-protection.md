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
ms.openlocfilehash: 2a28e2ecc45be941dbd6e346f9918e1692357840
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083102"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Bescherming tegen phishing in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Phishing* is een e-mailaanval die gevoelige informatie probeert te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders. Er zijn specifieke categorieën van phishing. Bijvoorbeeld:

- **Bij phishing** met speerpunten wordt gerichte, aangepaste inhoud gebruikt die specifiek is afgestemd op de beoogde geadresseerden (meestal na verkenning van de geadresseerden door de aanvaller).

- **Whaling** is gericht op leidinggevenden of andere doelen met een hoge waarde binnen een organisatie voor een maximaal effect.

- Zakelijke e-mailcompromitteerden **(BEC)** gebruikt vervalste vertrouwde afzenders (financiële verantwoordelijken, klanten, vertrouwde partners, enzovoort) om geadresseerden te verleiden tot het goedkeuren van betalingen, het overmaken van tegoeden of het onthullen van klantgegevens. Meer informatie vindt u in [deze video](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2).

- **Ransomware** die uw gegevens versleutelt en betaling vereist om deze te ontsleutelen, begint bijna altijd in phishingberichten. Anti-phishingbeveiliging kan u niet helpen versleutelde bestanden te ontsleutelen, maar kan wel helpen bij het opsporen van de eerste phishingberichten die zijn gekoppeld aan de ransomware-campagne. Zie Herstellen van een ransomware-aanval in Microsoft 365 voor meer informatie over het herstellen van een [ransomware-aanval.](recover-from-ransomware.md)

Met de toenemende complexiteit van aanvallen is het zelfs moeilijk voor getrainde gebruikers om geavanceerde phishingberichten te identificeren. Gelukkig kunnen Exchange Online Protection (EOP) en de extra functies in Microsoft Defender voor Office 365 helpen.

## <a name="anti-phishing-protection-in-eop"></a>Anti-phishingbeveiliging in EOP

EOP (dat wil zeggen Microsoft 365 zonder Microsoft Defender voor Office 365) bevat functies die uw organisatie kunnen beschermen tegen phishing-bedreigingen:

- **Spoof intelligence:** Gebruik het inzicht in spoof intelligence om gedetecteerde vervalste afzenders in berichten van externe en interne domeinen te controleren en deze gedetecteerde afzenders handmatig toe te staan of te blokkeren. Zie [Inzicht in adresvervalsingsanalyse in EOP](learn-about-spoof-intelligence.md) voor meer informatie.

- **Anti-phishingbeleid in EOP:** Schakel spoofinformatie in of uit, schakel niet-genauteerde afzenderidentificatie in Outlook in of uit en geef de actie op voor geblokkeerde vervalste afzenders. Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)voor meer informatie.

- **Vervalste afzenders toestaan of blokkeren in de lijst Tenant toestaan/blokkeren**: wanneer u het oordeel in inzicht in adresvervalsingsanalyse overschrijft, wordt de vervalste afzender een handmatige vermelding voor toestaan of blokkeren die alleen wordt weergegeven op het tabblad **Adresvervalsing gebruiken** in de lijst Tenant toestaan/blokkeren. U kunt ook handmatig vermeldingen maken voor toestaan of blokkeren voor vervalste afzenders voordat deze worden gedetecteerd door adresvervalsingsanalyse. Zie voor meer informatie [Lijst Tenant toestaan/blokkeren beheren in EOP](tenant-allow-block-list.md).

- Impliciete e-mailverificatie: EOP verbetert standaardcontroles voor e-mailverificatie voor binnenkomende e-mail[(SPF,](set-up-spf-in-office-365-to-help-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)en [DMARC)](use-dmarc-to-validate-email.md)met de reputatie van afzenders, afzendergeschiedenis, geschiedenis van geadresseerden, gedragsanalyse en andere geavanceerde technieken om vervalste afzenders te identificeren. Zie [E-mailverificatie in Microsoft 365](email-validation-and-authentication.md) voor meer informatie.

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Aanvullende bescherming tegen phishing in Microsoft Defender voor Office 365

Microsoft Defender voor Office 365 bevat extra en geavanceerdere anti-phishingfuncties:

- **Anti-phishingbeleid in Microsoft Defender voor Office 365:** Instellingen voor imitatiebeveiliging configureren voor specifieke bericht afzenders en afzenderdomeinen, instellingen voor postvakinformatie en aanpasbare geavanceerde phishingdrempels. Zie [Anti-phishingbeleid configureren in Microsoft Defender](configure-mdo-anti-phishing-policies.md)voor Office 365. Zie Anti-phishingbeleid in Microsoft 365 voor meer informatie over de verschillen tussen [anti-phishingbeleid](set-up-anti-phishing-policies.md)in EOP en anti-phishingbeleid in Defender voor Office 365.
- **Campagneweergaven:** Machine learning en andere heuristische acties identificeren en analyseren berichten die betrokken zijn bij gecoördineerde phishingaanvallen tegen de hele service en uw organisatie. Zie Campagneweergaven in Microsoft Defender voor [Office 365.](campaigns.md)
- **Training voor** aanvalssimulatie: beheerders kunnen nep-phishingberichten maken en deze als hulpmiddel voor onderwijs naar interne gebruikers verzenden. Zie Een [phishing-aanval simuleren voor meer informatie.](attack-simulation-training.md)

## <a name="other-anti-phishing-resources"></a>Andere anti-phishingbronnen

- Voor eindgebruikers: [Bescherm uzelf tegen phishingschema's en andere vormen van onlinefraude.](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593)

- [Hoe Microsoft 365 het Van-adres valideert om phishing te voorkomen.](how-office-365-validates-the-from-address.md)
