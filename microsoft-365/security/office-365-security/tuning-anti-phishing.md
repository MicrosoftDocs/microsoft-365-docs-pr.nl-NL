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
description: Beheerders kunnen leren om te achterhalen waarom en hoe een phishing-bericht is doorgekomen in Microsoft 365 en wat ze moeten doen om meer phishingberichten in de toekomst te voorkomen.
ms.openlocfilehash: b7a68eb3ab3cf7dbb7156059416cca04d80bb3a8
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44588438"
---
# <a name="tune-anti-phishing-protection"></a>Beveiliging tegen phishing afstemmen

Hoewel Microsoft 365 wordt geleverd met een verscheidenheid aan anti-phishingfuncties die standaard zijn ingeschakeld, is het mogelijk dat sommige phishingberichten nog steeds door kunnen dringen tot uw mailboxen. In dit onderwerp wordt beschreven wat u doen om te ontdekken waarom een phishingbericht is doorgekomen en wat u doen om de anti-phishing-instellingen in uw Microsoft 365-organisatie aan te passen zonder het per ongeluk erger te _maken._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: omgaan met alle gecompromitteerde accounts en zorg ervoor dat u blokkeren meer phishing-berichten van het krijgen door

Als het account van een ontvanger is gecompromitteerd als gevolg van het phishingbericht, volgt u de stappen in [Reageren op een gecompromitteerd e-mailaccount in Microsoft 365](responding-to-a-compromised-email-account.md).

Als uw abonnement Advanced Threat Protection (ATP) bevat, u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishingbericht hebben ontvangen. Je hebt extra opties om phishingberichten te blokkeren:

- [Veilige ATP-koppelingen](set-up-atp-safe-links-policies.md)

- [ATP-veilige bijlagen](set-up-atp-safe-attachments-policies.md)

- [ATP anti-phishing beleid in Microsoft 365](configure-atp-anti-phishing-policies.md). Houd er rekening mee dat u de **geavanceerde phishingdrempels** in het beleid tijdelijk verhogen van **Standaard** naar **Agressief,** **agressiever**of **Meest agressief**.

Controleer of deze ATP-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden aan Microsoft

Het melden van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Microsoft 365 te beschermen. Zie Berichten [en bestanden rapporteren aan Microsoft voor](report-junk-email-messages-to-microsoft.md)instructies.

## <a name="inspect-the-message-headers"></a>De berichtkoppen inspecteren

U de headers van het phishingbericht onderzoeken om te zien of er iets is dat u zelf doen om te voorkomen dat er meer phishingberichten binnenkomen. Met andere woorden, het onderzoeken van de berichten headers kan u helpen bij het identificeren van alle instellingen in uw organisatie die verantwoordelijk waren voor het toestaan van de phishing-berichten in.

Controleer specifiek het kopveld **X-Forefront-Antispam-Report** in de berichtkoppen op indicaties van overgeslagen spam of phish-filtering in de waarde van het spamfilteren (SFV). Berichten die filteren overslaan, hebben een vermelding van `SCL:-1` , wat betekent dat een van uw instellingen dit bericht heeft toegestaan door de spam of phish-uitspraken die door de service zijn bepaald, te overschrijven. Zie [Anti-spamberichtenkoppen in Microsoft 365 voor](anti-spam-message-headers.md)meer informatie over het ophalen van berichtheaders en de volledige lijst met alle beschikbare anti-spam- en anti-phish-berichtkoppen.

## <a name="best-practices-to-stay-protected"></a>Aanbevolen procedures om beschermd te blijven

- Voer maandelijks [Secure Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw organisatie te beoordelen.

- Controleer regelmatig het [spoofinformatierapport](learn-about-spoof-intelligence.md) en [configureer spoofinformatie](set-up-anti-phishing-policies.md#spoof-settings) om verdachte berichten in quarantaine te **plaatsen** in plaats van ze te leveren aan de map Ongewenste e-mail van de gebruiker.

- Controleer regelmatig het [rapport Bedreigingsbeschermingsstatus](view-reports-for-atp.md#threat-protection-status-report).

- Sommige klanten staan per ongeluk phishingberichten toe door hun eigen domeinen in de lijst Afzender toestaan of Domein toestaan in antispambeleid. Als u ervoor kiest om dit te doen, moet u uiterste voorzichtigheid gebruiken. Hoewel deze configuratie zal toestaan dat sommige legitieme berichten door, het zal ook toestaan dat kwaadaardige berichten die normaal gesproken zou worden geblokkeerd door de spam en / of phish filters.

  De beste manier om te gaan met legitieme berichten die worden geblokkeerd door Microsoft 365 (false positives) waarbij afzenders in uw domein betrokken zijn, is door de SPF-, DKIM- en DMARC-records in DNS voor _al_ uw e-maildomeinen volledig en volledig te configureren:

  - Controleer of uw SPF-record _alle_ bronnen van e-mail identificeert voor afzenders in uw domein (vergeet services van derden niet!).

  - Gebruik hard fail ( \- ) om ervoor te zorgen dat onbevoegde afzenders worden geweigerd door e-mailsystemen die zijn geconfigureerd om dit te doen. U [spoofinformatie](learn-about-spoof-intelligence.md) gebruiken om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden opnemen in uw SPF-record.

  Zie voor configuratie-instructies:
  
  - [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md)

- Waar mogelijk raden we u aan om e-mail voor uw domein rechtstreeks naar Microsoft 365 te verzenden. Met andere woorden, wijs de MX-record van uw Microsoft 365-domein aan op Microsoft 365. Exchange Online Protection (EOP) is in staat om de beste bescherming te bieden aan uw cloudgebruikers wanneer hun e-mail rechtstreeks wordt bezorgd aan Microsoft 365. Als u een e-mailhygiënesysteem van derden voor EOP moet gebruiken, gebruikt u Enhanced Filtering for Connectors. Zie Uitgebreide [filtering voor connectoren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

- Multi-factor authenticatie (MFA) is een goede manier om gecompromitteerde accounts te voorkomen. U moet sterk overwegen om MFA in te schakelen voor al uw gebruikers. Voor een gefaseerde aanpak, begin met het inschakelen van MFA voor uw meest gevoelige gebruikers (admins, leidinggevenden, enz.) voordat u MFA voor iedereen inschakelt. Zie [Meerstapverificatie instellen](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)voor instructies.

- Regels voor doorsturen naar externe ontvangers worden vaak gebruikt door aanvallers om gegevens te extraheren. Gebruik de regels **voor het doorsturen van postvakcontrole** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) om regels voor het doorsturen van externe ontvangers te zoeken en zelfs te voorkomen. Zie Externe [doorschakelregels voor extern doorsturen van clients met veilige score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)voor meer informatie.
