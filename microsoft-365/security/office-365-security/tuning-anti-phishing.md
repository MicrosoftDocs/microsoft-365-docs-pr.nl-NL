---
title: Beveiliging tegen phishing afstemmen
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
description: Beheerders kunnen leren om te bepalen waarom en hoe een phishing-bericht is doorgekomen in Microsoft 365 en wat ze moeten doen om meer phishingberichten in de toekomst te voorkomen.
ms.openlocfilehash: a9b7a58f32fd14c157d72e8f91a1f1b8bfe3aedc
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208583"
---
# <a name="tune-anti-phishing-protection"></a>Beveiliging tegen phishing afstemmen

Hoewel Microsoft 365 wordt geleverd met een verscheidenheid aan anti-phishing-functies die standaard zijn ingeschakeld, is het mogelijk dat sommige phishing-berichten nog steeds door kunnen dringen tot uw mailboxen. In dit onderwerp wordt beschreven wat u doen om te ontdekken waarom een phishingbericht is doorgekomen en wat u doen om de anti-phishing-instellingen in uw Microsoft 365-organisatie aan te passen _zonder de dingen per ongeluk erger te maken._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: omgaan met alle gecompromitteerde accounts en zorg ervoor dat u nog meer phishing-berichten te blokkeren van het krijgen door

Als het account van een ontvanger is gecompromitteerd als gevolg van het phishingbericht, volgt u de stappen in [Reageren op een gecompromitteerd e-mailaccount in Microsoft 365.](responding-to-a-compromised-email-account.md)

Als uw abonnement Advanced Threat Protection (ATP) bevat, u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishingbericht hebben ontvangen. Je hebt extra opties om phishingberichten te blokkeren:

- [Veilige ATP-koppelingen](set-up-atp-safe-links-policies.md)

- [ATP-veilige bijlagen](set-up-atp-safe-attachments-policies.md)

- [ATP anti-phishing beleid in Microsoft 365](configure-atp-anti-phishing-policies.md). Houd er rekening mee dat u de **geavanceerde phishingdrempels** in het beleid tijdelijk verhogen van **Standaard** naar **Agressief,** **agressiever**of **meest agressief**.

Controleer of deze ATP-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden aan Microsoft

Het melden van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Microsoft 365 te beschermen. Zie Berichten [en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)instructies.

## <a name="inspect-the-message-headers"></a>De berichtkoppen inspecteren

U de headers van het phishingbericht bekijken om te zien of er iets is dat u zelf doen om te voorkomen dat er meer phishingberichten binnenkomen. Met andere woorden, het onderzoeken van de berichten headers kan u helpen bij het identificeren van alle instellingen in uw organisatie die verantwoordelijk waren voor het toestaan van de phishing-berichten in.

In het bijzonder moet u het headerveld **X-Forefront-Antispam-Report** in de berichtkoppen controleren op aanwijzingen van overgeslagen spam of phish-filtering in de Waarde van het Spamfiltering Verdict (SFV). Berichten die filteren overslaan hebben een vermelding van `SCL:-1` , wat betekent dat een van uw instellingen dit bericht doorliet door de spam- of phish-uitspraken te overschrijven die door de service zijn bepaald. Zie [Anti-spam berichtheaders in Microsoft 365](anti-spam-message-headers.md)voor meer informatie over het ontvangen van berichtenkoppen en de volledige lijst met alle beschikbare antispam- en anti-phish-berichtkoppen.

## <a name="best-practices-to-stay-protected"></a>Aanbevolen procedures om beschermd te blijven

- Voer maandelijks [Secure Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw organisatie te beoordelen.

- Controleer het [spoofrapport regelmatig](learn-about-spoof-intelligence.md) en [configureer spoofinformatie](set-up-anti-phishing-policies.md#spoof-settings) om verdachte berichten **in quarantaine** te plaatsen in plaats van ze te leveren aan de map Ongewenste e-mail van de gebruiker.

- Controleer regelmatig het [rapport statusstatus bedreiging](view-reports-for-atp.md#threat-protection-status-report).

- Sommige klanten staan per ongeluk phishingberichten toe door hun eigen domeinen in de lijst Afzender toestaan of domeintoestaan in antispambeleid. Als u ervoor kiest om dit te doen, moet u extreme voorzichtigheid gebruiken. Hoewel deze configuratie zal toestaan dat een aantal legitieme berichten door, het zal ook toestaan dat kwaadaardige berichten die normaal gesproken zou worden geblokkeerd door de spam en / of phish filters.

  De beste manier om te gaan met legitieme berichten die worden geblokkeerd door Microsoft 365 (false positives) die afzenders in uw domein betrekken, is door de SPF-, DKIM- en DMARC-records volledig en volledig te configureren in DNS voor _al_ uw e-maildomeinen:

  - Controleer of uw SPF-record _alle_ bronnen van e-mail identificeert voor afzenders in uw domein (vergeet services van derden niet!).

  - Gebruik hard fail ( \- ) om ervoor te zorgen dat onbevoegde afzenders worden afgewezen door e-mailsystemen die zijn geconfigureerd om dit te doen. U [spoofinformatie](learn-about-spoof-intelligence.md) gebruiken om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden in uw SPF-record opnemen.

  Zie voor configuratie-instructies:
  
  - [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md)

- Waar mogelijk raden we u aan e-mail voor uw domein rechtstreeks naar Microsoft 365 te sturen. Met andere woorden, wijs de MX-record van uw Microsoft 365-domein naar Microsoft 365. Exchange Online Protection (EOP) is in staat om de beste bescherming te bieden aan uw cloudgebruikers wanneer hun e-mail rechtstreeks aan Microsoft 365 wordt bezorgd. Als u een e-mailhygiënesysteem van derden moet gebruiken voor EOP, gebruikt u Verbeterde filtering voor connectors. Zie Uitgebreide [filtering voor connectors in Exchange Online voor](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)instructies .

- Multifactorauthenticatie (MFA) is een goede manier om gecompromitteerde accounts te voorkomen. U moet sterk overwegen mfa in te schakelen voor al uw gebruikers. Voor een gefaseerde aanpak u beginnen met mfa in te schakelen voor uw meest gevoelige gebruikers (beheerders, leidinggevenden, enz.) voordat u MFA voor iedereen inschakelt. Zie Meervoudige [verificatie instellen](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)voor instructies .

- Doorsturen van regels naar externe ontvangers worden vaak gebruikt door aanvallers om gegevens te extraheren. Gebruik de gegevens **van postvakdoorstuurregels controleren** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) om regels naar externe ontvangers te zoeken en zelfs te voorkomen. Zie [Externe doorstuurregels van client beperken met beveiligde score](https://blogs.technet.microsoft.com/office365security/mitigating-client-external-forwarding-rules-with-secure-score/)voor meer informatie.
