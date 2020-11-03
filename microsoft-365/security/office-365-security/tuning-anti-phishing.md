---
title: Beveiliging tegen phishing afstemmen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- MET150
description: Beheerders kunnen leren welke redenen en hoe een malafide bericht krijg in Microsoft 365 en wat u moet doen om te voorkomen dat er meer phishingberichten in de toekomst worden verstaan.
ms.openlocfilehash: e933769b6bce9eb10765fb2b58025445432bed18
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845466"
---
# <a name="tune-anti-phishing-protection"></a>Beveiliging tegen phishing afstemmen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hoewel Microsoft 365 diverse functies van concurrentiebeperkende functies ondersteunt, is het mogelijk dat sommige malafide berichten ook naar uw postvakken gaan. In dit onderwerp wordt beschreven wat u kunt doen om te ontdekken waarom een malafide bericht is ontvangen en wat u kunt doen om de anti phishing-instellingen in uw Microsoft 365-organisatie te wijzigen _zonder per ongeluk dingen_ te doen.

## <a name="first-things-first-deal-with-any-compromised-accounts-and-make-sure-you-block-any-more-phishing-messages-from-getting-through"></a>U moet eerst het volgende doen: omgaan met verenigende accounts en ervoor zorgen dat u meer phishingberichten blokkeert voor het downloaden

Als het account van een geadresseerde in het geval van een malafide account is aangetast, volgt u de stappen in [reageren op een gemanipuleerd e-mailaccount in Microsoft 365](responding-to-a-compromised-email-account.md).

Als uw abonnement Microsoft Defender voor Office 365 bevat, kunt u de [bedreigings informatie van Office 365](office-365-ti.md) gebruiken voor het identificeren van andere gebruikers die het malafide bericht ook hebben ontvangen. U hebt extra opties voor het blokkeren van malafide berichten:

- [Veilige koppelingen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)

- [Veilige bijlagen in Microsoft Defender voor Office 365](set-up-atp-safe-attachments-policies.md)

- [Anti malafide beleid in Microsoft Defender voor Office 365](configure-atp-anti-phishing-policies.md). Houd er rekening mee dat u de geavanceerde **verduidelijkings** **drempels** **van de** beleidsregels tijdelijk kunt verhogen, hoger **of agressief** **.**

Controleer of de functies voor de functies van Defender voor Office 365 zijn ingeschakeld.

## <a name="report-the-phishing-message-to-microsoft"></a>Meld het phishingberichten aan Microsoft

Het melden van phishing-berichten is handig bij het afstemmen van de filters die worden gebruikt voor de beveiliging van alle klanten in Microsoft 365. Zie voor instructies [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="inspect-the-message-headers"></a>De berichtkoppen controleren

U kunt de kopteksten van het malafide bericht bekijken om te zien of er iets is wat u kunt doen om te voorkomen dat u meer malafide berichten kunt voorkomen. Met andere woorden: wanneer u de berichtkoppen evalueert, kunt u de instellingen in uw organisatie identificeren die verantwoordelijk zijn voor het toestaan van malafide berichten.

Daarom moet u het koptekstveld **X-Forefront-spam-report** in de berichtkoppen controleren op de plaats van overgeslagen spam of phishing-filters in de Verdict (SFV) voor spam filtering. Berichten die het filteren overslaan heeft een vermelding van `SCL:-1` , wat betekent dat een van uw instellingen dit bericht toestaat door de spam of phishing Verdicts te vervangen door de service. Zie [antispam berichtkoppen in Microsoft 365](anti-spam-message-headers.md)voor meer informatie over het weergeven van berichtkoppen en de volledige lijst met alle beschikbare antispam-en anti-spambericht koppen.

## <a name="best-practices-to-stay-protected"></a>Aanbevolen procedures om beveiligd te blijven

- Voer op een maandbasis [beveiligde Score](../mtp/microsoft-secure-score.md) uit om de beveiligingsinstellingen van uw organisatie te beoordelen.

- Voor berichten die per ongeluk worden beëindigd, of voor berichten die zijn toegestaan via, raden we u aan om die berichten te zoeken in de [bedreigings Verkenner en de detectie van realtime](threat-explorer.md). U kunt zoeken op afzender, geadresseerde of bericht-ID. Wanneer u het bericht hebt gevonden, gaat u naar details door op het onderwerp te klikken. Voor een gequarantined bericht bekijkt u wat de detectietechnologie is, zodat u kunt gebruikmaken van de juiste methode om deze te overschrijven. Kijk voor een toegestaan bericht welke beleidsregels het bericht hebben toegestaan. 

- Vervalste e-mail is als phishing gelabeld in de Defender voor Office 365. Soms is spoofing onschadelijk en soms willen gebruikers deze niet in quarantaine plaatsen. Regelmatig het [spoof Intelligence-rapport](learn-about-spoof-intelligence.md)voordat u de overlast voor gebruikers beperkt. Wanneer u alle benodigde overschrijvingen hebt gecontroleerd en de nodige overschrijvingen hebt aangebracht, kunt u verdachte [informatie configureren](set-up-anti-phishing-policies.md#spoof-settings) voor verdachte berichten in plaats van deze naar de map Ongewenste e-mail van de **gebruiker te verzenden** .

- U kunt de bovenstaande stap voor imitatie (domein of gebruiker) herhalen. Het imitatie rapport vindt u onder **Threat Management** \> **Dashboard** \> **inzichten**.

- Controleer regelmatig het [status rapport bedreigingsbeveiliging](view-reports-for-atp.md#threat-protection-status-report).

- Sommige klanten maken per ongeluk malafide e-mailberichten door hun eigen domeinen in te voegen in de lijst afzender toestaan of domein toestaan in antispambeleid. Hoewel u met deze configuratie enkele originele berichten kunt ontvangen, worden ook schadelijke berichten die normaal worden geblokkeerd door de spam-en/of phishings filters toegestaan. In plaats van het domein toe te staan, moet u het onderliggende probleem corrigeren.

  De beste manier om te bepalen welke berichten worden geblokkeerd door Microsoft 365 (fout-positief) waarbij afzenders in uw domein worden gebruikt, is door de SPF-, DKIM-en DMARC-records in DNS voor _al_ uw e-mail domeinen volledig en volledig te configureren.

  - Controleer of uw SPF-record _alle_ bronnen van e-mailberichten identificeert voor afzenders in uw domein (u hoeft geen service van derden te doen).

  - Gebruik hard fail ( \- alle) om ervoor te zorgen dat ongeautoriseerde afzenders worden geweigerd door e-mail systemen die hiervoor zijn geconfigureerd. U kunt met behulp van [spoof Intelligence](learn-about-spoof-intelligence.md) afzenders identificeren die uw domein gebruiken, zodat u geautoriseerde afzenders van derden kunt opnemen in uw SPF-record.

  Zie voor meer informatie:
  
  - [SPF instellen om adresvervalsing te helpen voorkomen](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

  - [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanuit uw aangepaste domein](use-dkim-to-validate-outbound-email.md)

  - [DMARC gebruiken om e-mail te valideren](use-dmarc-to-validate-email.md)

- U wordt aangeraden e-mail voor uw domein rechtstreeks te bezorgen bij Microsoft 365. Met andere woorden: wijs de MX-record van uw Microsoft 365-domein naar Microsoft 365. Exchange Online Protection (EOP) kan de beste bescherming bieden voor uw Cloud gebruikers wanneer hun e-mail rechtstreeks wordt bezorgd bij Microsoft 365. Als u een e-mailsysteem van derden voor EOP moet gebruiken, kunt u beter filteren op connectors. Zie voor meer informatie het artikel [uitgebreid filteren op connectors in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

- Gebruikers moeten [berichten](enable-the-report-message-add-in.md) voor Microsoft melden, zodat we ons systeem kunnen trainen. Beheerders kunnen ook gebruikmaken van functies voor het [indienen van beheerders](admin-submission.md) .

- MFA (multi factor Authentication) is een goede manier om te voorkomen dat accounts met een account worden vertrouwd. Het is raadzaam MFA in te schakelen voor al uw gebruikers. Voor een gefaseerde aanpak moet u eerst MFA inschakelen voor uw meeste gevoelige gebruikers (beheerders, leidinggevenden, etc.) voordat u MFA voor iedereen inschakelt. Zie [multi-factor Authentication instellen](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)voor instructies.

- Doorstuurregels naar externe geadresseerden worden vaak gebruikt door aanvallers om gegevens op te halen. Gebruik de **regels voor het doorsturen van postvakken** in [Microsoft Secure Score](../mtp/microsoft-secure-score.md) om doorstuurregels naar externe geadresseerden te zoeken en te voorkomen. Zie voor meer informatie het artikel [beperken van externe doorstuurregels van clients met een beveiligde Score](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score).
