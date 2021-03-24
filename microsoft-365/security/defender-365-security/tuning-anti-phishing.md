---
title: Beveiliging tegen phishing afstemmen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Beheerders kunnen leren om de redenen te identificeren waarom en hoe een phishingbericht in Microsoft 365 is verzonden en wat ze moeten doen om in de toekomst meer phishingberichten te voorkomen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1772a0329825b8808352892c8d99f0d7680112f5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058482"
---
# <a name="tune-anti-phishing-protection"></a>Beveiliging tegen phishing afstemmen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hoewel Microsoft 365 wordt geleverd met diverse anti-phishingfuncties die standaard zijn ingeschakeld, is het mogelijk dat sommige phishingberichten nog steeds in uw postvakken kunnen worden verzonden. In dit onderwerp wordt beschreven wat u kunt doen om erachter te komen waarom een phishingbericht is binnengekomen en wat u kunt doen om de anti-phishing-instellingen in uw Microsoft 365-organisatie aan te passen zonder dat dit per ongeluk erger _wordt._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>First things first: deal with any compromised accounts and make sure you block any more phishing messages from getting through

Als het account van een geadresseerde is gecompromitteerd als gevolg van het phishingbericht, volgt u de stappen in Reageren op een [gekromd e-mailaccount in Microsoft 365.](responding-to-a-compromised-email-account.md)

Als uw abonnement Microsoft Defender voor Office 365 bevat, kunt u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishingbericht hebben ontvangen. U hebt extra opties om phishingberichten te blokkeren:

- [Veilige koppelingen in Microsoft Defender voor Office 365](set-up-safe-links-policies.md)

- [Veilige bijlagen in Microsoft Defender voor Office 365](set-up-safe-attachments-policies.md)

- [Anti-phishingbeleid in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md). Houd er rekening mee dat u de drempelwaarden voor **geavanceerde phishing** in het beleid tijdelijk kunt verhogen van Standaard naar **Agressief,** **Agressiever** of **Meest agressief.** 

Controleer of deze Defender voor Office 365-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden bij Microsoft

Het rapporteren van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Microsoft 365 te beschermen. Zie Berichten en bestanden [rapporteren aan Microsoft voor instructies.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>De berichtkoppen controleren

U kunt de kopteksten van het phishingbericht bekijken om te zien of u zelf iets kunt doen om te voorkomen dat er meer phishingberichten worden verzonden. Met andere woorden, als u de berichtenkoppen onderzoekt, kunt u de instellingen in uw organisatie identificeren die verantwoordelijk zijn voor het toestaan van de phishingberichten in.

In het bijzonder moet u het **veld X-Forefront-Antispam-Report** in de berichtkoppen controleren op aanwijzingen voor overgeslagen filtering op spam of phishing in de waarde SpamFiltering (SFV). Berichten die het filteren overslaan, hebben een vermelding van , wat betekent dat een van uw instellingen dit bericht heeft toegestaan door de spam- of phishing-berichten te overschrijven die door de `SCL:-1` service zijn bepaald. Zie Kopteksten tegen [spam in Microsoft 365](anti-spam-message-headers.md)voor meer informatie over het verkrijgen van berichtkoppen en de volledige lijst met alle beschikbare kopteksten voor antispam- en phishingberichten.

## <a name="best-practices-to-stay-protected"></a>Best practices om beschermd te blijven

- Voer maandelijks Secure [Score](../defender/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw organisatie te beoordelen.

- Voor berichten die per ongeluk in quarantaine worden geplaatst of voor berichten die zijn toegestaan, raden we u aan te zoeken naar deze berichten in Threat Explorer en [realtime detecties.](threat-explorer.md) U kunt zoeken op afzender, geadresseerde of bericht-id. Nadat u het bericht hebt gevonden, gaat u naar details door op het onderwerp te klikken. Kijk voor een bericht in quarantaine wat de 'detectietechnologie' was, zodat u de juiste methode kunt gebruiken om deze te overschrijven. Kijk voor een toegestaan bericht welk beleid het bericht heeft toegestaan.

- Vervalste e-mail wordt gemarkeerd als phishing in Defender voor Office 365. Soms is spoof goedaardig en soms willen gebruikers het niet in quarantaine plaatsen. Als u de impact voor gebruikers wilt minimaliseren, controleert u regelmatig het [rapport Spoof intelligence.](learn-about-spoof-intelligence.md) Nadat u de benodigde overschrijvingen hebt gecontroleerd en aangebracht,  kunt u erop vertrouwen dat u [spoofinformatie](set-up-anti-phishing-policies.md#spoof-settings) configureert op Verdachte berichten in quarantaine plaatsen in plaats van ze af te leveren bij de map Ongewenste e-mail van de gebruiker.

- U kunt de bovenstaande stap voor imitatie (domein of gebruiker) herhalen. Het rapport Imitatie vindt u onder **Threat Management** \> **Dashboard** \> **Insights**.

- Bekijk het rapport [Bedreigingsbeveiligingsstatus regelmatig.](view-reports-for-mdo.md#threat-protection-status-report)

- Sommige klanten staan per ongeluk phishingberichten toe door hun eigen domeinen in de lijst Afzender toestaan of Domein toestaan in antispambeleid. Hoewel met deze configuratie enkele legitieme berichten kunnen worden verzonden, kunnen er ook schadelijke berichten worden verzonden die normaal gesproken worden geblokkeerd door de spam- en/of phishingfilters. In plaats van het domein toe te staan, moet u het onderliggende probleem corrigeren.

  De beste manier om te gaan met legitieme berichten die worden geblokkeerd door Microsoft 365 (false positives) waarbij afzenders in uw domein betrokken  zijn, is door de SPF-, DKIM- en DMARC-records in DNS volledig en volledig te configureren voor al uw e-maildomeinen:

  - Controleer of uw SPF-record alle _e-mailbronnen_ voor afzenders in uw domein identificeert (vergeet geen services van derden!).

  - Gebruik hard fail (alle) om ervoor te zorgen dat niet-geautoriseerde afzenders worden geweigerd door e-mailsystemen die zijn \- geconfigureerd om dit te doen. U kunt [spoofinformatie gebruiken](learn-about-spoof-intelligence.md) om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden kunt opnemen in uw SPF-record.

  Zie voor configuratie-instructies:

  - [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md)

- Waar mogelijk wordt u aangeraden e-mail voor uw domein rechtstreeks naar Microsoft 365 te verzenden. Met andere woorden, wijs de MX-record van uw Microsoft 365-domein aan op Microsoft 365. Exchange Online Protection (EOP) kan de beste beveiliging bieden voor uw cloudgebruikers wanneer hun e-mail rechtstreeks wordt bezorgd bij Microsoft 365. Als u een e-mailhygiënesysteem van derden moet gebruiken voor EOP, gebruikt u Verbeterde filtering voor verbindingslijnen. Zie Verbeterde filtering [voor connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)voor instructies.

- Gebruikers moeten de [invoegapp Rapportbericht of de invoeging](enable-the-report-message-add-in.md) [Phishing](enable-the-report-phish-add-in.md) melden gebruiken om berichten te rapporteren aan Microsoft, waarmee ze ons systeem kunnen trainen. Beheerders moeten ook profiteren van de mogelijkheden [voor het indienen van](admin-submission.md) beheerders.

- Meervoudige verificatie (MFA) is een goede manier om gekromde accounts te voorkomen. U moet sterk overwegen om MFA in te stellen voor al uw gebruikers. Voor een gefaseerd benadering moet u eerst MFA inschakelen voor uw meest gevoelige gebruikers (beheerders, leidinggevenden, enzovoort) voordat u MFA inschakelen voor iedereen. Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Het doorsturen van regels naar externe geadresseerden wordt vaak door aanvallers gebruikt om gegevens op te halen. Gebruik de **informatie over het doorsturen van postvakken** in [Microsoft Secure Score](../defender/microsoft-secure-score.md) om regels voor doorsturen naar externe geadresseerden te zoeken en zelfs te voorkomen. Zie [Mitigating Client External Forwarding Rules](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)with Secure Score (Regels voor extern doorsturen van client met secure score) voor meer informatie.
