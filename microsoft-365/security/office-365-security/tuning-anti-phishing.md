---
title: Anti-phishingbeveiliging afstemmen in Office 365
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
description: Beheerders kunnen leren om de redenen waarom en hoe een phishing-berichten door te krijgen, en wat te doen om meer phishing-berichten te voorkomen in de toekomst te identificeren.
ms.openlocfilehash: 94c28bf63ad7ba87d06298576cf7989b6848f8e6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812791"
---
# <a name="tune-anti-phishing-protection-in-office-365"></a>Anti-phishingbeveiliging afstemmen in Office 365

Hoewel Office 365 wordt geleverd met een verscheidenheid aan anti-phishingfuncties die standaard zijn ingeschakeld, is het mogelijk dat sommige phishingberichten nog steeds door naar uw mailboxen kunnen worden doorgegeven. In dit onderwerp wordt beschreven wat u doen om te ontdekken waarom een phishingbericht is binnengekomen en wat u doen om de anti-phishing-instellingen in uw Exchange Online-organisatie aan te passen zonder het per ongeluk erger te _maken._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: deal with any compromised accounts and sure you block more phishing messages from getting through First things first: deal with any compromised accounts and make you block more phishing messages from getting through First things first: deal with any compromised accounts and make you block more phishing messages from getting through First things first: deal with any compromise

Als het account van een ontvanger is gecompromitteerd als gevolg van het phishingbericht, voert u de stappen [uit in Reageren op een gecompromitteerd e-mailaccount in Office 365](responding-to-a-compromised-email-account.md).

Als uw abonnement Advanced Threat Protection (ATP) bevat, u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishingbericht hebben ontvangen. Je hebt extra opties om phishingberichten te blokkeren:

- [ATP Veilige links](set-up-atp-safe-links-policies.md)

- [ATP Veilige bijlagen](set-up-atp-safe-attachments-policies.md)

- [ATP anti-phishing beleid](set-up-anti-phishing-policies.md). Houd er rekening mee dat u de **geavanceerde phishingdrempels** in het beleid tijdelijk verhogen van **Standaard** naar **Agressief,** **agressiever**of **agressiever.**

Controleer of deze ATP-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden bij Microsoft

Het melden van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Office 365 te beschermen.

Stuur het phishingbericht _als bijlage_ in een nieuw, anders leeg bericht naar **phish@office365.microsoft.com**. Stuur niet alleen het oorspronkelijke bericht door; anders kunnen we de oorspronkelijke berichtkoppen niet onderzoeken. U de invoegtoepassing [Rapportbericht](https://docs.microsoft.com/office365/securitycompliance/enable-the-report-message-add-in) gebruiken in Outlook of de webversie van Outlook (voorheen Outlook Web App genoemd).

Zie [Spam-, niet-spam- en phishingberichten verzenden naar Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)voor meer informatie.

## <a name="inspect-the-message-headers"></a>De berichtkoppen inspecteren

U de headers van het phishingbericht onderzoeken om te zien of er iets is dat u zelf doen om te voorkomen dat er meer phishingberichten binnenkomen. Met andere woorden, het onderzoeken van de berichtenheaders kan u helpen bij het identificeren van alle instellingen in uw organisatie die verantwoordelijk waren voor het toestaan van de phishing-berichten in.

In het bijzonder moet u het kopveld **X-Forefront-Antispam-Report** in de kopteksten van het bericht controleren op aanwijzingen van overgeslagen spam of phish-filtering in de waarde Spam Filtering Verdict (SFV). Berichten die filteren overslaan hebben een `SCL:-1`vermelding van , wat betekent dat een van uw instellingen toegestaan dit bericht door door het overschrijven van de spam of phish uitspraken die werden bepaald door de dienst. Zie [Anti-spamberichtkoppen](https://docs.microsoft.com/office365/SecurityCompliance/anti-spam-message-headers)voor meer informatie over het ontvangen van kopteksten voor berichten en de volledige lijst met alle beschikbare antispam- en anti-phish-berichtkoppen.

## <a name="best-practices-to-stay-protected"></a>Best practices om beschermd te blijven

- Voer maandelijks [Secure Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw Office 365-organisatie te beoordelen.

- Controleer het [spoof-inlichtingenrapport](learn-about-spoof-intelligence.md) periodiek en [schakel anti-spoofingbescherming in het anti-phishingbeleid in](learn-about-spoof-intelligence.md#configuring-the-anti-spoofing-policy) om verdachte berichten in quarantaine te **plaatsen** in plaats van ze af te leveren aan de map Ongewenste e-mail van de gebruiker.

- Controleer periodiek het [rapport Threat Protection Status](view-reports-for-atp.md#threat-protection-status-report).

- Sommige klanten staan per ongeluk phishingberichten toe door hun eigen domeinen in de afzender toestaan of domeinlijst toestaan in antispambeleid. Als u ervoor kiest om dit te doen, moet u extreme voorzichtigheid gebruiken. Hoewel deze configuratie een aantal legitieme berichten via zal toestaan, zal het ook kwaadaardige berichten die normaal gesproken zou worden geblokkeerd door de Office 365 spam en / of phish filters.

  De beste manier om te gaan met legitieme berichten die zijn geblokkeerd door Office 365 (false positives) waarbij afzenders in uw domein betrokken zijn, is door de SPF-, DKIM- en DMARC-records in DNS volledig en volledig te configureren voor _al_ uw e-maildomeinen in Office 365:

  - Controleer of uw SPF-record _alle_ e-mailbronnen voor afzenders in uw domein identificeert (vergeet services van derden niet!).

  - Gebruik hard\-fail ( ) om ervoor te zorgen dat onbevoegde afzenders worden afgewezen door e-mailsystemen die zijn geconfigureerd om dit te doen. U [spoofinformatie](https://docs.microsoft.com/office365/securitycompliance/learn-about-spoof-intelligence) gebruiken om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden opnemen in uw SPF-record.

  Zie voor configuratie-instructies:
  
  - [Set up SPF in Office 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md) (SPF in Office 365 instellen om spoofing te helpen voorkomen)

  - [DKIM gebruiken om uitgaande e-mails die vanuit uw aangepaste domein zijn verzonden in Office 365 te valideren](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren in Office 365](use-dmarc-to-validate-email.md)

- Waar mogelijk raden we u aan e-mail voor uw domein rechtstreeks aan Office 365 te leveren. Richt met andere woorden de MX-record van uw Office 365-domein op Office 365. Exchange Online Protection (EOP) kan uw cloudgebruikers de beste bescherming bieden wanneer hun e-mail rechtstreeks naar Office 365 wordt bezorgd. Als u een e-mailhygiënesysteem van derden voor EOP moet gebruiken, zorg er dan voor dat u de richtlijnen [hier](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)hebt gevolgd.

- Multi factor authenticatie (MFA) is echt een goede manier om gecompromitteerde accounts te voorkomen. U moet sterk overwegen mfa in te schakelen voor al uw gebruikers. Voor een gefaseerde aanpak, begin met het inschakelen van MFA voor uw meest gevoelige gebruikers (beheerders, leidinggevenden, enz.) voordat u MFA voor iedereen inschakelt. Zie Meervoudige [verificatie instellen](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies.

- Doorstuurregels naar externe ontvangers worden vaak gebruikt door aanvallers om gegevens te extraheren. Gebruik de gegevens van de **regels voor het doorsturen** van postvakcontroleren in Microsoft Secure [Score](../mtp/microsoft-secure-score.md) om regels voor het doorsturen naar externe ontvangers te vinden en zelfs te voorkomen. Zie [Regels voor extern doorschakelen van client met secure score voor](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)meer informatie.
