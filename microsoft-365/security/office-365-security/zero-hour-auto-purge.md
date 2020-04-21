---
title: Zero-hour auto purge (ZAP) - met terugwerkende kracht bescherming tegen spam, malware en phishing.
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging in Microsoft 365 die spam-, malware- of phishingberichten detecteert die al bij Exchange Online zijn bezorgd. Hoe ZAP dit doet, hangt af van het type schadelijke inhoud dat wordt gedetecteerd.
ms.openlocfilehash: a819269d8596f12e76cbd17b5d1302cd56837f14
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630807"
---
# <a name="zero-hour-auto-purge-zap---protection-against-spam-and-malware-in-microsoft-365"></a>Zero-hour auto purge (ZAP) - bescherming tegen spam en malware in Microsoft 365

## <a name="overview"></a>Overzicht

Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging in Microsoft 365 die met terugwerkende kracht schadelijke phishing-, spam- of malwareberichten detecteert en neutraliseert die al zijn afgeleverd bij Postvakken van Exchange Online.

ZAP is beschikbaar met de standaard Exchange Online Protection (EOP) die is inbegrepen bij elk Microsoft 365-abonnement dat Exchange Online-postvakken bevat. ZAP werkt niet in zelfstandige EOP-omgevingen die on-premises Exchange-postvakken beschermen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Microsoft 365 werkt dagelijks spam- en malwarehandtekeningen in realtime bij. Gebruikers kunnen echter nog steeds schadelijke berichten ontvangen om verschillende redenen, waaronder als inhoud wordt bewapend nadat ze aan gebruikers zijn geleverd. ZAP lost dit probleem op door voortdurend updates van de Microsfot 365 spam- en malwarehandtekeningen te controleren. ZAP kan berichten vinden en verwijderen die zich al in het postvak van een gebruiker bevinden.

De ZAP-actie is naadloos voor de gebruiker; ze worden niet op de hoogte gesteld als een bericht wordt gedetecteerd en verplaatst.

[Lijsten met veilige afzenders,](create-safe-sender-lists-in-office-365.md)regels voor e-mailstromen (ook wel transportregels genoemd), Postvak IN-regels of extra filters hebben voorrang op ZAP.

### <a name="malware-zap"></a>Malware ZAP

Voor **lees- of ongelezen berichten** die malware blijken te bevatten na levering, quarantainet ZAP het bericht dat de malwarebijlage bevat. Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.

Malware ZAP is standaard ingeschakeld in anti-malwarebeleid. Zie [Beleid voor antimalware configureren in Microsoft 365](configure-anti-malware-policies.md)voor meer informatie.

### <a name="phish-zap"></a>Phish ZAP

Voor **gelezen of ongelezen berichten** die na levering als phish worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor een **phishing-e-mailfilteringvonnis** in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor phish en hun mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine. Alleen beheerders kunnen in quarantaine geplaatste berichten in quarantaine bekijken en beheren.

Standaard is phish ZAP ingeschakeld in antispambeleid en de standaardactie voor het **phishing-e-mailfiltervonnis** is **Quarantainebericht**, wat betekent dat phish ZAP het bericht standaard in quarantaine zet.

Zie [Antispambeleid configureren in Microsoft 365 voor](configure-your-spam-filter-policies.md)meer informatie over het configureren van spamfilteruitspraken.

### <a name="spam-zap"></a>Spam ZAP

Voor **ongelezen berichten** die na levering als spam worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor **het** spamfiltervonnis in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor spam en de mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine. Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.

Standaard is spam ZAP ingeschakeld in antispambeleid en de standaardactie voor **het** spamfiltervonnis is Bericht verplaatsen naar **ongewenste e-mailmap,** wat betekent dat spam ZAP **standaard ongelezen** berichten naar de map Ongewenste e-mail verplaatst.

Zie [Antispambeleid configureren in Microsoft 365 voor](configure-your-spam-filter-policies.md)meer informatie over het configureren van spamfilteruitspraken.

### <a name="zap-considerations-for-office-365-advanced-threat-protection-atp"></a>ZAP-overwegingen voor Office 365 Advanced Threat Protection (ATP)

ZAP zal geen bericht in quarantaine plaatsen dat aan het scannen van [Dynamic Delivery](dynamic-delivery-and-previewing.md) is, of waar malwarefiltering de bijlage al heeft vervangen door het bestand Malware **Alert Text.txt.** Als een phish- of spamsignaal wordt ontvangen voor dit soort berichten en het filtervonnis in het antispambeleid is ingesteld om actie te ondernemen op het bericht (Verplaatsen naar ongewenstee items, omleiding, quarantaine, quarantaine) dan zal ZAP standaard een actie 'Verplaatsen naar ongewenste e-mail' uitvoeren.

## <a name="how-to-see-if-zap-moved-your-message"></a>Hoe u zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, u het [rapport Status bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report) of [Threat Explorer (en realtime detecties)](threat-explorer.md)gebruiken. Als systeemactie is ZAP niet aangemeld bij de controlelogboeken van het Exchange-postvak.

## <a name="zap-faq"></a>VEELgestelde VRAGEN OVER ZAP

### <a name="q-what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>V: Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

A: U moet het normale rapportageproces volgen voor [false positives.](report-junk-email-messages-to-microsoft.md) De enige reden waarom het bericht zou worden verplaatst van de Inbox naar de map Ongewenste e-mail zou zijn omdat de service heeft vastgesteld dat het bericht was spam of kwaadaardig.

### <a name="q-what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>V: Wat als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

A: ZAP onderneemt actie op basis van een bericht op basis van de configuratie van uw antispambeleid zoals eerder in dit onderwerp is beschreven.

### <a name="q-what-if-im-using-mail-flow-rules-or-allowedblocked-sender-lists"></a>V: Wat als ik e-mailstroomregels of toegestane/geblokkeerde afzenderlijsten gebruik?

A: Regels voor e-mailstroom of blokkeren en organisatorische instellingen toestaan, hebben voorrang. Deze berichten zijn uitgesloten van ZAP.

### <a name="q-what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>V: Wat gebeurt er als een bericht naar een andere map wordt verplaatst (bijvoorbeeld regels in postvak IN)?

A: ZAP werkt nog steeds zolang het bericht niet is verwijderd, of zolang hetzelfde of sterker, actie nog niet is toegepast. Als het phish-beleid bijvoorbeeld is ingesteld op quarantaine en de gebruiker of beheerder de e-mail al heeft gejunked, wordt er in quarantaine actie ondernomen om het bestand in quarantaine te plaatsen.

### <a name="q-does-zap-change-the-message-header"></a>V: Wijzigt ZAP de berichtkop?

A: Een ZAP-actie brengt geen wijzigingen aan in de berichtkop.

### <a name="q-how-does-zap-affect-mailboxes-on-hold"></a>V: Hoe beïnvloedt ZAP mailboxen in de wacht?

A: ZAP zal geen berichten van postvakken in de wacht plaatsen. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor een spam- of phishingvonnis in antispambeleid.

Zie [In-Place Hold en Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over blokkeringen in Exchange Online.
