---
title: Zero-hour automatische zuivering (ZAP)
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
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen meer te weten komen over hoe zap (zero-hour auto purge) met terugwerkende kracht geleverde berichten in een Exchange Online-postvak kan verplaatsen naar de map Ongewenste e-mail of quarantaine die met terugwerkende kracht worden gevonden als spam of phishing.
ms.openlocfilehash: 612ef45194fbf70ef89eee0f455b2d4d8781247f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819422"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour auto purge (ZAP) in Exchange Online

## <a name="basic-features-of-zap"></a>Basiskenmerken van ZAP

In Microsoft 365-organisaties met mailboxen in Exchange Online is zero-hour auto purge (ZAP) een functie voor e-mailbeveiliging die met terugwerkende kracht schadelijke phishing-, spam- of malwareberichten detecteert en neutraliseert die al zijn bezorgd in Exchange Online-postvakken.

ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange-postvakken beschermen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Spam en malware handtekeningen worden bijgewerkt in de dienst real-time op een dagelijkse basis. Gebruikers kunnen echter nog steeds kwaadaardige berichten ontvangen om verschillende redenen, bijvoorbeeld als inhoud is bewapend nadat ze aan gebruikers zijn geleverd. ZAP lost dit probleem op door voortdurend updates van de spam- en malwarehandtekeningen in de service te controleren. ZAP kan berichten vinden en verwijderen die al in het postvak van een gebruiker staan.

De ZAP-actie is naadloos voor de gebruiker; ze worden niet gemeld als een bericht wordt gedetecteerd en verplaatst.

[Veilige afzenderlijsten,](create-safe-sender-lists-in-office-365.md)regels voor e-mailstroom (ook wel transportregels genoemd), Postvak IN-regels of extra filters hebben voorrang op ZAP. Net als bij wat er gebeurt in de e-mailstroom, betekent dit dat zelfs als de service het geleverde bericht zap vereist, het bericht niet wordt gereageerd vanwege de configuratie van de veilige afzenders. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filtering te omzeilen.

### <a name="malware-zap"></a>Malware ZAP

Voor **gelezen of ongelezen berichten** die malware blijken te bevatten na levering, zet ZAP het bericht dat de malwarebijlage bevat in quarantaine. Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.

Malware ZAP is standaard ingeschakeld in anti-malware beleid. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.

### <a name="phish-zap"></a>Phish ZAP

Voor **lees- of ongelezen berichten** die na levering als phish zijn geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor een **phishing-e-mailfilteruitspraak** in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor phish en hun mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-header**toevoegen, **Prepend onderwerpregel met tekst**: ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Omleid bericht naar e-mailadres**, **Bericht verwijderen**, **Quarantaine bericht**: ZAP quarantaine het bericht.

Standaard is phish ZAP ingeschakeld in antispambeleid en de standaardactie voor het **phishing-e-mailfilteringsoordeel** is **Quarantainebericht**, wat betekent dat phish ZAP het bericht standaard in quarantaine houdt.

Zie [Antispambeleid configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van vonnissen voor spamfilters.

### <a name="spam-zap"></a>Spam ZAP

Voor **ongelezen berichten** die na levering als spam zijn geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor het vonnis **voor spamfilteren** in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor spam en hun mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-header**toevoegen, **Prepend onderwerpregel met tekst**: ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken configureren in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Omleid bericht naar e-mailadres**, **Bericht verwijderen**, **Quarantaine bericht**: ZAP quarantaine het bericht. Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.

Standaard is spam ZAP ingeschakeld in het antispambeleid en de standaardactie voor het vonnis **voor het** filteren van spam is Bericht verplaatsen naar map **Ongewenste e-mail**, wat betekent dat SPAM ZAP standaard **ongelezen** berichten naar de map Ongewenste e-mail verplaatst.

Zie [Antispambeleid configureren in Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van vonnissen voor spamfilters.

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>ZAP-overwegingen voor Geavanceerde bedreigingsbeveiliging van Office 365 (AtP voor Office 365)

ZAP zal geen berichten in quarantaine plaatsen die zich in het proces van [Dynamic Delivery-scan](dynamic-delivery-and-previewing.md) bevinden of waar malwarefiltering de bijlage al heeft vervangen door het **Text.txt-bestand van malwarewaarschuwing.** Als een phish- of spamsignaal wordt ontvangen voor dit soort berichten en het filteroordeel in het antispambeleid is ingesteld om actie te ondernemen op het bericht (Verplaats naar Ongewenste e-mail, Omleiden, Verwijderen, Quarantaine) dan zal ZAP standaard een actie 'Verplaatsen naar ongewenste e-mail' uitvoeren.

## <a name="how-to-see-if-zap-moved-your-message"></a>Hoe u zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, u het [rapport Bedreigingsbeveiligingsstatus](view-email-security-reports.md#threat-protection-status-report) of [Threat Explorer (en realtime detecties)](threat-explorer.md)gebruiken. Houd er rekening mee dat ZAP als systeemactie niet is ingelogd in de controlelogboeken van Exchange-postvakken.

## <a name="zap-faq"></a>VRAGEN OVER ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

U moet het normale rapportageproces voor [fout-positieven](report-junk-email-messages-to-microsoft.md)volgen. De enige reden waarom het bericht zou worden verplaatst van het Postvak IN naar de map Ongewenste e-mail zou zijn omdat de service heeft vastgesteld dat het bericht spam of kwaadaardig was.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

ZAP zal actie ondernemen op basis van een bericht op basis van de configuratie van uw anti-spam beleid zoals eerder beschreven in dit onderwerp.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat moet ik doen als ik veilige afzenders, regels voor e-mailstromen of toegestane/geblokkeerde afzenderlijsten gebruik?

Veilige afzenders, regels voor e-mailstromen of het blokkeren en toestaan dat organisatie-instellingen voorrang krijgen. Deze berichten zijn uitgesloten van ZAP omdat de service doet waarvoor u deze hebt geconfigureerd. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filtering te omzeilen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht wordt verplaatst naar een andere map (bijvoorbeeld regels voor Postvak IN)?

ZAP werkt nog steeds zolang het bericht niet is verwijderd, of zolang dezelfde of sterkere actie nog niet is toegepast. Als het phish-beleid bijvoorbeeld in quarantaine is ingesteld en de gebruiker of beheerder de e-mail al heeft weggegooid, wordt in quarantaine actie ondernomen om het bestand in quarantaine te plaatsen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hoe beïnvloedt ZAP brievenbussen in de wachtstand?

ZAP zal geen berichten uit brievenbussen in de wacht plaatsen. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor een spam- of phishing-uitspraak in het antispambeleid.

Zie [In-Place Hold and Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over hold-hold in Exchange Online.
