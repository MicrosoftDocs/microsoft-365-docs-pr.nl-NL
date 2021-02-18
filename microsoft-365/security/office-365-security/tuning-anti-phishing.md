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
description: Beheerders kunnen achterhalen waarom en hoe een phishing-bericht is binnengezonden in Microsoft 365 en wat er moet gebeuren om in de toekomst meer phishing-berichten te voorkomen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3abbafce36c589f60eb164fb29c714c980f8b98
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286487"
---
# <a name="tune-anti-phishing-protection"></a>Beveiliging tegen phishing afstemmen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Hoewel Microsoft 365 wordt geleverd met diverse anti-phishing-functies die standaard zijn ingeschakeld, is het mogelijk dat sommige phishing-berichten nog steeds in uw postvakken kunnen komen. In dit onderwerp wordt beschreven wat u kunt doen om te ontdekken waarom een phishing-bericht is binnengekomen en wat u kunt doen om de anti-phishing-instellingen in uw Microsoft 365-organisatie aan te passen zonder per ongeluk iets slechter te _maken._

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>Het eerste wat u moet doen: omgaan met gekromde accounts en ervoor zorgen dat u geen phishingberichten meer tegen kunt houden

Als het account van een ontvanger is gehackt als gevolg van het phishingbericht, volgt u de stappen voor het reageren op een gekromd e-mailaccount [in Microsoft 365.](responding-to-a-compromised-email-account.md)

Als uw abonnement Microsoft Defender voor Office 365 omvat, kunt u [Office 365 Threat Intelligence](office-365-ti.md) gebruiken om andere gebruikers te identificeren die ook het phishing-bericht hebben ontvangen. U hebt extra opties om phishing-berichten te blokkeren:

- [Veilige koppelingen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)

- [Veilige bijlagen in Microsoft Defender voor Office 365](set-up-atp-safe-attachments-policies.md)

- [Anti-phishingbeleid in Microsoft Defender voor Office 365.](configure-atp-anti-phishing-policies.md) Houd er rekening mee dat u de drempel  voor geavanceerde  **phishing** in het beleid tijdelijk kunt verhogen van Standaard naar **Agressief,** Meer agressief of **Meest agressief.**

Controleer of deze Defender voor Office 365-functies zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Het phishingbericht melden bij Microsoft

Het melden van phishingberichten is handig bij het afstemmen van de filters die worden gebruikt om alle klanten in Microsoft 365 te beschermen. Zie Berichten en bestanden [rapporteren bij Microsoft voor instructies.](report-junk-email-messages-to-microsoft.md)

## <a name="inspect-the-message-headers"></a>De berichtkoppen controleren

U kunt de koppen van het phishingbericht bekijken om te zien of u zelf iets kunt doen om te voorkomen dat er nog phishingberichten binnen komen. Met andere woorden, door de berichtkoppen na te kijken, kunt u bepalen welke instellingen in uw organisatie verantwoordelijk waren voor het toestaan van phishing-berichten.

U moet met name het veld **X-Forefront-Antispam-Report** in de berichtkoppen controleren op aanwijzingen van overgeslagen filtering op spam of phishing in de waarde spamfilterfilter (SFV). Berichten waarin het filteren wordt overgeslagen, worden weergegeven. Dit betekent dat een van uw instellingen dit bericht heeft toegestaan door het blokkeren van spam of phishing die door de `SCL:-1` service is bepaald. Zie Berichtkoppen tegen [ongewenste e-mail in Microsoft 365](anti-spam-message-headers.md)voor meer informatie over het verkrijgen van berichtkoppen en de volledige lijst met alle beschikbare berichtkoppen tegen spam en anti-phishing.

## <a name="best-practices-to-stay-protected"></a>Best practices om beschermd te blijven

- Voer maandelijks Secure [Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw organisatie te beoordelen.

- Voor berichten die per ongeluk in quarantaine worden geplaatst of berichten die zijn toegestaan, raden we u aan te zoeken naar die berichten in Bedreigingsverkenner en [real-time detecties.](threat-explorer.md) U kunt zoeken op afzender, geadresseerde of bericht-id. Nadat u het bericht hebt gevonden, gaat u naar details door op het onderwerp te klikken. Kijk voor een bericht in quarantaine wat de 'detectietechnologie' was, zodat u de juiste methode kunt gebruiken om te overschrijven. Voor een toegestaan bericht kijkt u welk beleid het bericht heeft toegestaan.

- Vervalste e-mail is gelabeld als phishing in Defender voor Office 365. Soms willen gebruikers de adresvervalsing niet in quarantaine plaatsen. Om de gevolgen voor gebruikers tot een minimum te beperken, bekijkt u regelmatig het [intelligence-rapport spoofing.](learn-about-spoof-intelligence.md) Nadat u de benodigde overschrijvingen hebt gecontroleerd en hebt aangebracht, kunt u erop vertrouwen dat spoof [intelligence](set-up-anti-phishing-policies.md#spoof-settings) in quarantaine wordt geconfigureerd voor verdachte berichten in plaats van deze in de map Ongewenste e-mail van de gebruiker te plaatsen. 

- Herhaal de bovenstaande stap voor Imitatie (domein of gebruiker). Het rapport Imitatie vindt u onder **Threat Management** \> **Dashboard** \> **Insights.**

- Bekijk regelmatig het [rapport Status van bedreigingsbeveiliging.](view-reports-for-atp.md#threat-protection-status-report)

- Sommige klanten staan per ongeluk phishing-berichten toe door hun eigen domeinen in de lijst Afzender toestaan of Domeinlijst toestaan in antispambeleid te plaatsen. Hoewel sommige legitieme berichten via deze configuratie worden toegestaan, kunnen ook schadelijke berichten worden geblokkeerd door de spam- en/of phishingfilters. In plaats van het domein toe te staan, moet u het onderliggende probleem oplossen.

  De beste manier om om te gaan met legitieme berichten die worden geblokkeerd door Microsoft 365 (fout-positieven) waarbij afzenders in uw domein  zijn betrokken, is door de SPF-, DKIM- en DMARC-records in DNS volledig en volledig te configureren voor al uw e-maildomeinen:

  - Controleer of met uw  SPF-record alle e-mailbronnen voor afzenders in uw domein worden geïdentificeerd (vergeet geen externe services!).

  - Gebruik harde fail (alle) om ervoor te zorgen dat niet-geautoriseerde afzenders worden geweigerd door e-mailsystemen die \- zijn geconfigureerd om dit te doen. U kunt spoof [intelligence](learn-about-spoof-intelligence.md) gebruiken om afzenders te identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden in uw SPF-record kunt opnemen.

  Zie voor configuratie-instructies:

  - [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md)

- Indien mogelijk is het raadzaam om e-mail voor uw domein rechtstreeks naar Microsoft 365 te verzenden. Met andere woorden, wijs de MX-record van uw Microsoft 365-domein naar Microsoft 365. Exchange Online Protection (EOP) kan uw cloudgebruikers de beste bescherming bieden wanneer hun e-mail rechtstreeks bij Microsoft 365 wordt bezorgd. Als u een e-mailsysteem van derden moet gebruiken voor EOP, gebruikt u Verbeterde filters voor connectors. Zie [Enhanced Filtering for Connectors in Exchange Online voor instructies.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

- Gebruikers moeten de [invoegapp Bericht rapporteren](enable-the-report-message-add-in.md) of de invoegvoegapp [Phishing melden](enable-the-report-phish-add-in.md) gebruiken om berichten te rapporteren aan Microsoft, die ons systeem kan trainen. Beheerders moeten ook profiteren van de mogelijkheden voor [het indienen van](admin-submission.md) beheerders.

- Meervoudige verificatie (Multi Factor Authentication, MFA) is een goede manier om gekromde accounts te voorkomen. Overweeg ten zeerste om MFA in te stellen voor al uw gebruikers. Voor een gefaseeerde aanpak moet u MFA inschakelen voor de meest gevoelige gebruikers (beheerders, leidinggevenden, enzovoort) voordat u MFA voor iedereen inschakelen. Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)

- Het doorsturen van regels naar externe geadresseerden wordt vaak gebruikt door aanvallers om gegevens op te halen. Gebruik de **regelgegevens voor het doorsturen van** postvakken controleren in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) om regels voor doorsturen naar externe geadresseerden te zoeken en zelfs te voorkomen. Zie Regels voor externe doorsturen van klanten verminderen [met Secure Score voor meer informatie.](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score)
