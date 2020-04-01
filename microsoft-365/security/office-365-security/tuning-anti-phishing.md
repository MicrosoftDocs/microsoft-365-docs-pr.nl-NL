---
title: Bescherming tegen phishing afstemmen in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Beheerders kunnen leren om te bepalen waarom en hoe een phishing-berichten is doorgekomen en wat ze moeten doen om meer phishingberichten in de toekomst te voorkomen.
ms.openlocfilehash: 37d1e8bbf91bc6f0a1c8e9b5aa97fe460e8b5c82
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081206"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Bescherming tegen phishing afstemmen in Office 365

Hoewel Office 365 wordt geleverd met een verscheidenheid aan anti-phishing functies die standaard zijn ingeschakeld, is het mogelijk dat sommige phishing-berichten nog steeds kunnen doordringen tot uw mailboxen. In dit onderwerp wordt beschreven wat u doen om te ontdekken waarom een phishingbericht is doorgekomen en wat u doen om de anti-phishing-instellingen in uw Exchange Online-organisatie aan te passen _zonder de problemen per ongeluk erger te maken._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: omgaan met alle gecompromitteerde accounts en zorg ervoor dat u nog meer phishing-berichten te blokkeren van het krijgen door

Als het account van een ontvanger is gecompromitteerd als gevolg van het phishingbericht, voert u de stappen uit [om te reageren op een gecompromitteerd e-mailaccount in Office 365.](responding-to-a-compromised-email-account.md)

Als uw abonnement Advanced Threat Protection (ATP) bevat, u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishingbericht hebben ontvangen. Je hebt extra opties om phishingberichten te blokkeren:

- [ATP Veilige Links](set-up-atp-safe-links-policies.md)

- [ATP-veilige bijlagen](set-up-atp-safe-attachments-policies.md)

- [ATP anti-phishing beleid](set-up-anti-phishing-policies.md). Houd er rekening mee dat u de **geavanceerde phishingdrempels** in het beleid tijdelijk verhogen van **Standaard** naar **Agressief,** **agressiever**of **meest agressief**.

Controleer of deze ATP-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden aan Microsoft

Het melden van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Office 365 te beschermen. Zie Berichten [en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)instructies.

## <a name="inspect-the-message-headers"></a>De berichtkoppen inspecteren

U de headers van het phishingbericht bekijken om te zien of er iets is dat u zelf doen om te voorkomen dat er meer phishingberichten binnenkomen. Met andere woorden, het onderzoeken van de berichten headers kan u helpen bij het identificeren van alle instellingen in uw organisatie die verantwoordelijk waren voor het toestaan van de phishing-berichten in.

In het bijzonder moet u het headerveld **X-Forefront-Antispam-Report** in de berichtkoppen controleren op aanwijzingen van overgeslagen spam of phish-filtering in de Waarde van het Spamfiltering Verdict (SFV). Berichten die filteren overslaan hebben een `SCL:-1`vermelding van , wat betekent dat een van uw instellingen dit bericht doorliet door de spam- of phish-uitspraken te overschrijven die door de service zijn bepaald. Zie [Kopteksten voor antispamberichten in Office 365](anti-spam-message-headers.md)voor meer informatie over het ontvangen van berichtenkoppen en de volledige lijst met alle beschikbare antispam- en anti-phish-berichtkoppen.

## <a name="best-practices-to-stay-protected"></a>Aanbevolen procedures om beschermd te blijven

- Voer maandelijks [Secure Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw Office 365-organisatie te beoordelen.

- Controleer regelmatig het [spoofrapport](learn-about-spoof-intelligence.md) en [schakel anti-spoofingbescherming in het antiphishingbeleid in](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) om verdachte berichten **in quarantaine** te plaatsen in plaats van ze te leveren aan de map Ongewenste e-mail van de gebruiker.

- Controleer regelmatig het [rapport statusstatus bedreiging](view-reports-for-atp.md#threat-protection-status-report).

- Sommige klanten staan per ongeluk phishingberichten toe door hun eigen domeinen in de lijst Afzender toestaan of domeintoestaan in antispambeleid. Als u ervoor kiest om dit te doen, moet u extreme voorzichtigheid gebruiken. Hoewel deze configuratie een aantal legitieme berichten doorlaat, worden ook schadelijke berichten mogelijk gemaakt die normaal gesproken worden geblokkeerd door de Office 365-spam- en/of phish-filters.

  De beste manier om te gaan met legitieme berichten die worden geblokkeerd door Office 365 (false positives) waarbij afzenders in uw domein betrokken zijn, is door de SPF-, DKIM- en DMARC-records volledig te configureren in DNS voor _al_ uw e-maildomeinen in Office 365:

  - Controleer of uw SPF-record _alle_ bronnen van e-mail identificeert voor afzenders in uw domein (vergeet services van derden niet!).

  - Gebruik hard\-fail ( ) om ervoor te zorgen dat onbevoegde afzenders worden afgewezen door e-mailsystemen die zijn geconfigureerd om dit te doen. U [spoofinformatie](learn-about-spoof-intelligence.md) gebruiken om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden in uw SPF-record opnemen.

  Zie voor configuratie-instructies:
  
  - [SPF in Office 365 instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein in Office 365](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail in Office 365 te valideren](use-dmarc-to-validate-email.md)

- Waar mogelijk raden we u aan e-mail voor uw domein rechtstreeks naar Office 365 te sturen. Met andere woorden, wijs de MX-record van uw Office 365-domein naar Office 365. Exchange Online Protection (EOP) is in staat om de beste bescherming te bieden aan uw cloudgebruikers wanneer hun e-mail rechtstreeks naar Office 365 wordt bezorgd. Als u een e-mailhygiënesysteem van derden moet gebruiken voor EOP, gebruikt u Verbeterde filtering voor connectors. Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

- Multi factor authentication (MFA) is een echt goede manier om gecompromitteerde accounts te voorkomen. U moet sterk overwegen mfa in te schakelen voor al uw gebruikers. Voor een gefaseerde aanpak u beginnen met mfa in te schakelen voor uw meest gevoelige gebruikers (beheerders, leidinggevenden, enz.) voordat u MFA voor iedereen inschakelt. Zie Meervoudige [verificatie instellen](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)voor instructies .

- Doorsturen van regels naar externe ontvangers worden vaak gebruikt door aanvallers om gegevens te extraheren. Gebruik de gegevens **van postvakdoorstuurregels controleren** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) om regels naar externe ontvangers te zoeken en zelfs te voorkomen. Zie [Externe doorstuurregels van client beperken met beveiligde score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)voor meer informatie.
