---
title: Veelgestelde vragen over anti-spoofingbescherming
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Veelgestelde vragen en antwoorden voor beheerders over anti-spoofing bescherming in Exchange Online en standalone Exchange Online Protection (EOP).
ms.openlocfilehash: b39e48fd57b899e6296d40ab10aac265cb4165a3
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2020
ms.locfileid: "43529843"
---
# <a name="anti-spoofing-protection-faq-in-office-365"></a>Veelgestelde vragen over antispoofingbeveiliging in Office 365

In dit onderwerp worden veelgestelde vragen en antwoorden gegeven over anti-spoofingbescherming voor Office 365-klanten met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP)-klanten zonder Exchange Online-postvakken.

Zie [Veelgestelde vragen](anti-spam-protection-faq.md)over spambescherming voor vragen en antwoorden over bescherming tegen spam.

Zie Veelgestelde vragen over bescherming [tegen malware in Office 365](anti-malware-protection-faq-eop.md) voor vragen en antwoorden over bescherming tegen malware

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Waarom heeft Microsoft ervoor gekozen om niet-geverifieerde binnenkomende e-mail te verzenden?

Vanwege de impact van phishing-aanvallen, en omdat e-mail authenticatie is al meer dan 15 jaar, Microsoft is van mening dat het risico van de voortzetting van niet-geverifieerde inkomende e-mail is hoger dan het risico van het verliezen van legitieme inkomende e-mail.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Zorgt ongewenste e-mail ervoor dat legitieme e-mail wordt gemarkeerd als spam?

Toen Microsoft deze functie in 2018 instelde, gebeurde er een aantal false positives (goede berichten werden gemarkeerd als slecht). Na verloop van tijd zijn afzenders echter aangepast aan de vereisten voor de nieuwe verificatie van afzenders en het aantal berichten dat verkeerd is geïdentificeerd als vervalst, is voor de meeste e-mailpaden verwaarloosbaar geworden.

Microsoft zelf heeft de nieuwe vereisten voor e-mailverificatie enkele weken voor de implementatie ervan voor het eerst aangenomen aan klanten. Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.

## <a name="is-spoof-intelligence-available-to-office-365-customers-without-atp"></a>Is spoofinformatie beschikbaar voor Office 365-klanten zonder ATP?

Ja. Vanaf oktober 2018 is spoofintelligence beschikbaar voor alle organisaties met Exchange Online-mailboxen en zelfstandige EOP-organisaties zonder Exchange Online-mailboxen.

Anti-spoofing-technologie werd in eerste instantie geïmplementeerd bij organisaties die Office 365 Enterprise E5-abonnementen of de ATP-add-on (Office 365 Advanced Threat Protection) voor hun abonnement hadden.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?

Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ik ben een admin en ik weet niet alle bronnen voor berichten in mijn e-mail domein!

Zie [Je kent niet alle bronnen voor je e-mail.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Wat gebeurt er als ik anti-spoofing bescherming voor mijn organisatie uitschakel?

We raden dit af omdat u wordt blootgesteld aan meer gemiste phishing- en spamberichten. Niet alle phishingberichten zijn spoofs en niet alle spoofberichten worden gemist. Uw risico is echter groter dan bij een klant die anti-adresvervalsing heeft ingeschakeld.

Nu [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, raden we u niet langer aan anti-spoofing beveiliging uit te schakelen als uw MX-record naar een andere server of service verwijst voordat u e-mail naar EOP levert.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Betekent anti-spoofing bescherming dat ik zal worden beschermd tegen alle phishing?

Helaas, nee. Aanvallers passen zich aan om andere technieken te gebruiken (bijvoorbeeld gecompromitteerde accounts of accounts in gratis e-mailservices). Echter, anti-phishing bescherming werkt veel beter om deze andere vormen van phishing-methoden te detecteren. De beveiligingslagen in Office 365 zijn ontworpen om samen te werken en op elkaar te bouwen.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blokkeren andere grote e-mailservices niet-geverifieerde binnenkomende e-mail?

Bijna alle grote e-mailservices implementeren traditionele SPF-, DKIM- en DMARC-controles. Sommige services hebben andere, strengere controles, maar weinigen gaan zo ver als Office 365 om niet-geverifieerde e-mail te blokkeren en ze te behandelen als vervalste berichten. Echter, de industrie wordt steeds meer bewust over problemen met niet-geverifieerde e-mail, met name als gevolg van het probleem van phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Moet ik nog steeds de instelling Geavanceerd spamfilter inschakelen dat "SPF-record: hard fail"_(MarkAsSpamSpfRecordHardFail_) instelt als ik anti-spoofing inschakel?

Nee. Deze AsF-instelling is niet langer nodig omdat anti-spoofing niet alleen spf hard als mislukt beschouwt, maar een veel bredere reeks criteria. Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.

We raden u aan deze functie uit te schakelen, omdat deze bijna geen extra voordeel biedt voor het detecteren van spam of phishingberichten en in plaats daarvan voornamelijk valse positieven genereert. Zie [ASF-instellingen (Advanced Spam Filter) in Office 365](advanced-spam-filtering-asf-options.md) voor meer informatie.

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Helpt sender rewriting Scheme bij het oplossen van doorgestuurde e-mail?

SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op. Door de SMTP **MAIL FROM**te herschrijven, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF passeert op de volgende bestemming. Omdat anti-spoofing echter is gebaseerd op het **Van-adres** in combinatie met het domein **MAIL FROM** of DKIM-signing (of andere signalen), is het niet voldoende om te voorkomen dat door SRS doorgestuurde e-mail wordt gemarkeerd als vervalst.
