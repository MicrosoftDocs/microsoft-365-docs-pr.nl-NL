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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen Veelgestelde vragen en antwoorden over anti-spoofing beveiliging weergeven in Exchange Online Protection (EOP).
ms.openlocfilehash: 66dbedaf638154c4a35359a4e5bc66c326c04d1e
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826671"
---
# <a name="anti-spoofing-protection-faq"></a>Veelgestelde vragen over beveiliging tegen adresvervalsing

In dit onderwerp vindt u veelgestelde vragen en antwoorden over anti-spoofing beveiliging voor Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP-organisaties zonder Exchange Online-postvakken.

Zie Veelgestelde vragen over [anti-spam beveiliging](anti-spam-protection-faq.md)voor vragen en antwoorden over bescherming tegen ongewenste e-mail.

Zie [Veelgestelde vragen over beveiliging tegen malware](anti-malware-protection-faq-eop.md) voor vragen en antwoorden over beveiliging tegen malware.

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Waarom heeft Microsoft de inkomende e-mail ongeauthenticeerd laten voorkomen?

Vanwege de invloed van phishing-aanvallen en omdat verificatie via e-mail verificatie opvalt over 15 jaar, is Microsoft ervan overtuigd dat het risico van het blijven van niet-geverifieerde binnenkomende e-mail hoger is dan het risico dat het verlies van geldige inkomende e-mail verloren gaat.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Zorgt inkomende e-mailberichten met ongeauthenticeerde inkomende e-mail ervoor dat legitiem e-mailbericht wordt gemarkeerd als spam?

Wanneer Microsoft deze functie inschakelt in 2018, zijn er enkele onbepaalde foutberichten opgetreden (goede berichten zijn gemarkeerd als beschadigd). De afzenders zijn echter in de loop van de tijd afgestemd op de nieuwe vereisten voor verificatie van de afzender en het aantal berichten dat bij de meeste e-mail paden abusievelijk werden verouderd.

Microsoft zelf heeft de nieuwe verificatievereisten voor e-mailberichten eerst enkele weken goedgekeurd voordat u deze implementeert bij klanten. Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-atp"></a>Is spoof Intelligence beschikbaar voor Microsoft 365-klanten zonder ATP?

Ja. Vanaf oktober 2018 is spoof Intelligence beschikbaar voor alle organisaties met postvakken in Exchange Online, en zelfstandige EOP-organisaties zonder postvakken van Exchange Online.

De anti-spoofing technologie werd voor het eerst geïmplementeerd voor organisaties met een Office 365 Enterprise E5-abonnement of de Office 365 Advanced Threat Protection-invoegtoepassing (Office 365 ATP) voor hun abonnement.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?

Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ik ben een beheerder en ik weet niet alle bronnen voor berichten in mijn e-mail domein.

Zie [niet alle bronnen voor uw e-mail](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email).

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Wat gebeurt er als ik anti-spoofing beveiliging voor mijn organisatie uitschakel?

We raden dit af omdat u wordt blootgesteld aan meer gemiste phishing- en spamberichten. Niet alle phishingberichten zijn spoofs en niet alle spoofberichten worden gemist. Uw risico is echter groter dan bij een klant die anti-adresvervalsing heeft ingeschakeld.

Nu een [uitgebreide filtering voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, is het niet meer raadzaam om anti-spoofing beveiliging uit te schakelen als uw MX-record verwijst naar een andere server of service voordat u e-mail aanlevert bij EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Wordt in anti-spoofing bescherming bedoeld dat ik tegen phishing wordt beschermd?

Helaas, Nee, nee. Hackers worden aangepast om andere technieken te gebruiken (bijvoorbeeld gemanipuleerd accounts of accounts in gratis e-mailservices). De bescherming tegen phishing van deze andere typen veranderings methoden werkt echter sterk beter. De beschermings lagen in EOP zijn geschikt voor samenwerking en samenwerken.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Andere grote e-mailservices blokkeren inkomende e-mail blokkeren?

Bijna alle grote e-mailservices voeren traditionele SPF-, DKIM-en DMARC-controles uit. Voor sommige services zijn er nog meer strikte controles, maar enkele voorbeelden van EOP voor het blokkeren van niet-geverifieerde e-mail en behandel ze als vervalste berichten. De branche maakt echter meer kennis met betrekking tot problemen met niet-geverifieerde e-mail, met name vanwege het probleem van phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Moet ik de beleidsinstelling voor geavanceerde spam van de instelling SPF-record (_MarkAsSpamSpfRecordHardFail_) nog steeds inschakelen als ik anti-spoofing inschakel?

Nee. Deze ASF-instelling is niet meer vereist, omdat anti-spoofing niet alleen is ingesteld op SPF hard mislukt, maar een veel bredere set criteria. Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.

We raden u aan deze functie uit te schakelen omdat dit bijna geen extra voordeel uitmaakt voor het detecteren van spam of phishing en daarom vooral foutberichten verloopt. Zie voor meer informatie [Geavanceerde instellingen voor spam filter (ASF) in EOP](advanced-spam-filtering-asf-options.md).

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Wordt in het schema voor het opnieuw schrijven van de afzender het doorgestuurde e-mail opgelost?

SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op. Wanneer u de SMTP **-e-mail**herschrijft van, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF op de volgende bestemming doorgeeft. Aangezien ook anti-spoofing is gebaseerd op het **van** -adres in combinatie met de **e-mail van** of het dkim-handtekeningen domein (of andere signalen), is het niet voldoende om te voorkomen dat doorgestuurde e-mailberichten worden gemarkeerd als spoofed.
