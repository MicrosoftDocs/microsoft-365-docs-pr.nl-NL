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
ms.openlocfilehash: d2d307d201af8ad09a4faf7a865a29da8942bdf8
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288907"
---
# <a name="anti-spoofing-protection-faq"></a>Veelgestelde vragen over beveiliging tegen adresvervalsing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dit artikel bevat veelgestelde vragen en antwoorden over bescherming tegen spoofing voor Microsoft 365-organisaties met postvakken in Exchange Online, of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken.

Zie Veelgestelde vragen en antwoorden over bescherming tegen ongewenste [e-mail.](anti-spam-protection-faq.md)

Voor vragen en antwoorden over bescherming tegen malware, zie [veelgestelde vragen over bescherming tegen malware](anti-malware-protection-faq-eop.md)

## <a name="why-did-microsoft-choose-to-junk-unauthenticated-inbound-email"></a>Waarom heeft Microsoft gekozen voor ongewenste inkomende e-mail?

Microsoft is van mening dat het risico op het blijven toestaan van niet-geauteerde inkomende e-mail hoger is dan het risico op het verliezen van legitieme inkomende e-mail.

## <a name="does-junking-unauthenticated-inbound-email-cause-legitimate-email-to-be-marked-as-spam"></a>Zorgt niet-geauteerde inkomende e-mail ervoor dat legitieme e-mail wordt gemarkeerd als spam?

Toen Microsoft deze functie in 2018 inschakelen, gebeurde er een aantal fout-positieven (goede berichten waren gemarkeerd als slecht). Na een aantal keer hebben afzenders zich echter aan de vereisten aangepast. Het aantal berichten dat onjuist is geïdentificeerd als vervalst, werd steeds belangrijker voor de meeste e-mailpaden.

Microsoft zelf heeft enkele weken voor de implementatie bij klanten de nieuwe vereisten voor e-mailverificatie in gebruik genomen. Hoewel er aanvankelijk sprake was van verstoring, nam deze geleidelijk af.

## <a name="is-spoof-intelligence-available-to-microsoft-365-customers-without-defender-for-office-365"></a>Is spoof intelligence beschikbaar voor Microsoft 365-klanten zonder Defender voor Office 365?

Ja. Vanaf oktober 2018 is spoof intelligence beschikbaar voor alle organisaties met postvakken in Exchange Online en zelfstandige EOP-organisaties zonder Exchange Online-postvakken.

## <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>Hoe kan ik spam- of niet-spamberichten terugmelden bij Microsoft?

Zie [ Berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="im-an-admin-and-i-dont-know-all-of-sources-for-messages-in-my-email-domain"></a>Ik ben een beheerder en ik weet niet alle bronnen voor berichten in mijn e-maildomein.

Zie [U weet niet alle bronnen voor uw e-mail.](email-validation-and-authentication.md#you-dont-know-all-sources-for-your-email)

## <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization"></a>Wat gebeurt er als ik de beveiliging tegen spoofing voor mijn organisatie uitspoe?

Het wordt afgeraden om bescherming tegen spoofing uit te uitschakelen. Door de beveiliging uit te stellen, kunnen er meer phishing- en spamberichten worden afgeleverd in uw organisatie. Niet alle phishingberichten worden vervalst en niet alle vervalste berichten worden gemist. Uw risico is echter hoger.

Nu [Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschikbaar is, raden we niet langer aan om de beveiliging tegen spoofing uit te schakelen wanneer uw e-mail wordt doorverrouteerd via een andere service vóór EOP.

## <a name="does-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>Betekent de beveiliging tegen spoofing dat ik tegen alle phishing ben beveiligd?

Helaas niet. Aanvallers passen zich aan om andere technieken te gebruiken (bijvoorbeeld gekromde accounts of accounts in gratis e-mailservices). Anti-phishingbeveiliging werkt echter veel beter om deze andere typen phishingmethoden te detecteren. De beveiligingslagen in EOP zijn ontworpen om samen te werken en elkaar te beschermen.

## <a name="do-other-large-email-services-block-unauthenticated-inbound-email"></a>Blokkeren andere grote e-mailservices niet-geauteerde inkomende e-mail?

Bijna alle grote e-mailservices implementeren traditionele SPF-, DKIM- en DMARC-controles. Sommige services hebben andere, striktere controles, maar slechts weinig services zijn zo ver als EOP om niet-geauteerde e-mail te blokkeren en deze te behandelen als vervalste berichten. De branche wordt echter steeds meer op de hoogte van problemen met niet-geauteerde e-mail, met name vanwege het probleem van phishing.

## <a name="do-i-still-need-to-enable-the-advanced-spam-filter-setting-spf-record-hard-fail-_markasspamspfrecordhardfail_-if-i-enable-anti-spoofing"></a>Moet ik nog steeds de instelling voor het geavanceerde spamfilter 'SPF-record: hard fail'_(MarkAsSpamSpfRecordHardFail)_ inschakelen als ik anti-spoofing inschakelen?

Nee. Deze ASF-instelling is niet meer vereist. Beveiliging tegen adresvervalsing houdt in dat zowel SPF hard mislukt als dat er meer criteria worden gehanteerd. Als u anti-adresvervalsing hebt ingeschakeld en het **SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_) is ingeschakeld, krijgt u waarschijnlijk meer fout-positieven.

U wordt aangeraden deze functie uit te schakelen, omdat het vrijwel geen extra voordeel biedt voor het detecteren van spam of phishingbericht, en in plaats daarvan voornamelijk fout-positieven genereert. Zie [asf-instellingen (Advanced Spam Filter) in EOP](advanced-spam-filtering-asf-options.md)voor meer informatie.

## <a name="does-sender-rewriting-scheme-help-fix-forwarded-email"></a>Helpt het schema Voor het herschrijven van afzenders om doorgestuurde e-mail op te lossen?

SRS lost het probleem van doorgestuurde e-mail slechts gedeeltelijk op. Door SMTP **MAIL FROM** te herschrijven, kan SRS ervoor zorgen dat het doorgestuurde bericht SPF passeert op de volgende bestemming. Omdat antivervalsing echter is gebaseerd op het **Van-adres** in combinatie met het domein voor **MAIL FROM-** of DKIM-ondertekening (of andere signalen), is het niet voldoende om te voorkomen dat door SRS doorgestuurde e-mail wordt gemarkeerd als vervalst.
