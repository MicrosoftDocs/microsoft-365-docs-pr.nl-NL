---
title: Veelgestelde vragen over beveiliging tegen adresvervalsing
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: troubleshooting
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen veelgestelde vragen en antwoorden over bescherming tegen spoofing bekijken in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7e7163037029761a53a5461de592e46ab5ea0485
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917556"
---
# <a name="anti-spoofing-protection-faq"></a>Veelgestelde vragen over beveiliging tegen adresvervalsing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dit artikel bevat veelgestelde vragen en antwoorden over bescherming tegen spoofing voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken.

Zie Veelgestelde vragen over antispambeveiliging voor vragen en antwoorden over bescherming tegen [spam.](anti-spam-protection-faq.md)

Zie Veelgestelde vragen over anti-malwarebeveiliging voor vragen en antwoorden over [anti-malwarebeveiliging](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Waarom heeft Microsoft ervoor gekozen om ongewenste binnenkomende e-mail te gebruiken?

Microsoft is van mening dat het risico van het blijven toestaan van niet-verwerkte binnenkomende e-mail groter is dan het risico dat legitieme binnenkomende e-mail verloren gaat.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Zorgt ongewenste e-mail die niet is verzonden voor inkomende e-mail, ervoor dat legitieme e-mail wordt gemarkeerd als spam?

Toen Microsoft deze functie in 2018 inschakelen, zijn er enkele fout-positieven gebeurd (goede berichten zijn gemarkeerd als slecht). Na een tijd zijn afzenders echter aangepast aan de vereisten. Het aantal berichten dat onjuist is geïdentificeerd als vervalst, is voor de meeste e-mailpaden verwaarloosbaar geworden.

Microsoft zelf heeft de nieuwe vereisten voor e-mailverificatie enkele weken voor de implementatie ervan voor klanten goedgekeurd. Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Is spoof intelligence beschikbaar voor Microsoft 365-klanten zonder Defender voor Office 365?

Ja. Vanaf oktober 2018 is spoof intelligence beschikbaar voor alle organisaties met postvakken in Exchange Online en zelfstandige EOP-organisaties zonder Exchange Online-postvakken.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?

Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ik ben een beheerder en ik ken niet alle bronnen voor berichten in mijn e-maildomein.

Zie [U weet niet alle bronnen voor uw e-mail.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Wat gebeurt er als ik bescherming tegen spoofing voor mijn organisatie uitdoof?

We raden u af om bescherming tegen spoofing uit te uitschakelen. Door de beveiliging uit te stellen, kunnen er meer phishing- en spamberichten worden bezorgd in uw organisatie. Niet alle phishing is spoofing en niet alle vervalste berichten worden gemist. Het risico is echter hoger.

Nu verbeterde [filtering voor connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, wordt het niet meer aangeraden bescherming tegen spoofing uit te schakelen wanneer uw e-mail wordt gerouteerd via een andere service vóór EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Betekent anti-spoofingbeveiliging dat ik tegen alle phishing ben beveiligd?

Helaas niet. Aanvallers passen zich aan om andere technieken te gebruiken (bijvoorbeeld gecompromitteerde accounts of accounts in gratis e-mailservices). Anti-phishingbeveiliging werkt echter veel beter om deze andere typen phishingmethoden te detecteren. De beveiligingslagen in EOP zijn ontworpen om samen te werken en op elkaar te bouwen.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blokkeren andere grote e-mailservices niet-verzonden binnenkomende e-mail?

Bijna alle grote e-mailservices implementeren traditionele SPF-, DKIM- en DMARC-controles. Sommige services hebben andere, strengere controles, maar slechts weinigen gaan zo ver als EOP om niet-genauteerde e-mail te blokkeren en deze te behandelen als vervalste berichten. De industrie wordt echter steeds meer op de hoogte van problemen met niet-genauteerde e-mail, met name vanwege het probleem van phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Moet ik nog steeds de instelling Geavanceerd spamfilter 'SPF-record: hard fail'_(MarkAsSpamSpfRecordHardFail)_ inschakelen als ik anti-spoofing inschakelen?

Nee. Deze ASF-instelling is niet meer vereist. Anti-spoofingbeveiliging is van mening dat zowel SPF hard mislukt als een veel bredere set criteria. Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.

U wordt aangeraden deze functie uit te schakelen, omdat deze vrijwel geen extra voordeel biedt voor het opsporen van spam of phishing en in plaats daarvan voornamelijk onwaar positieven genereert. Zie [AsF-instellingen (Advanced Spam Filter) in EOP voor meer informatie.](advanced-spam-filtering-asf-options.md)

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Helpt Sender Rewriting Scheme bij het oplossen van doorgestuurde e-mail?

SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op. Door SMTP **MAIL FROM** te herschrijven, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF passeert op de volgende bestemming. Omdat anti-spoofing echter is  gebaseerd op het Van-adres in combinatie met het **DOMEIN MAIL FROM** of DKIM-ondertekening (of andere signalen), is het niet voldoende om te voorkomen dat door SRS doorgestuurde e-mail wordt gemarkeerd als vervalst.