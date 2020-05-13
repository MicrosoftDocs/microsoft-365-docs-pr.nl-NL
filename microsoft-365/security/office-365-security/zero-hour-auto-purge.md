---
title: Nuluur automatische zuivering (ZAP)
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
description: Beheerders kunnen meer te weten komen over hoe zero-hour auto purge (ZAP) met terugwerkende kracht afgeleverde berichten in een Exchange Online-postvak kan verplaatsen naar de map Ongewenste e-mail of quarantaine die met terugwerkende kracht spam of phishing blijken te zijn.
ms.openlocfilehash: 643063139f5d65b0271fd14ee5a2d1ca1f42ad1a
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208438"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour auto purge (ZAP) in Exchange Online

## <a name="overview"></a>Overzicht

In Microsoft 365-organisaties met postvakken in Exchange Online is zero-hour auto purge (ZAP) een functie voor e-mailbeveiliging die met terugwerkende kracht schadelijke phishing-, spam- of malwareberichten detecteert en neutraliseert die al zijn afgeleverd bij Postvakken van Exchange Online.

ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange-postvakken beschermen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Spam en malware handtekeningen worden bijgewerkt in de dienst real-time op een dagelijkse basis. Gebruikers kunnen echter nog steeds schadelijke berichten ontvangen om verschillende redenen, waaronder als inhoud wordt bewapend nadat ze aan gebruikers zijn geleverd. ZAP lost dit probleem op door voortdurend updates te controleren voor de spam- en malwarehandtekeningen in de service. ZAP kan berichten vinden en verwijderen die zich al in het postvak van een gebruiker bevinden.

De ZAP-actie is naadloos voor de gebruiker; ze worden niet op de hoogte gesteld als een bericht wordt gedetecteerd en verplaatst.

[Lijsten met veilige afzenders,](create-safe-sender-lists-in-office-365.md)regels voor e-mailstromen (ook wel transportregels genoemd), Postvak IN-regels of extra filters hebben voorrang op ZAP. Vergelijkbaar met wat er gebeurt in de e-mailstroom, betekent dit dat zelfs als de service bepaalt dat het geleverde bericht ZAP nodig heeft, het bericht niet wordt gereageerd vanwege de configuratie van de veilige afzenders. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filtering te omzeilen.

### <a name="malware-zap"></a>Malware ZAP

Voor **lees- of ongelezen berichten** die malware blijken te bevatten na levering, quarantainet ZAP het bericht dat de malwarebijlage bevat. Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.

Malware ZAP is standaard ingeschakeld in anti-malwarebeleid. Zie [Beleid voor anti-malware configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.

### <a name="phish-zap"></a>Phish ZAP

Voor **gelezen of ongelezen berichten** die na levering als phish worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor een **phishing-e-mailfilteringvonnis** in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor phish en hun mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine.

Standaard is phish ZAP ingeschakeld in antispambeleid en de standaardactie voor het **phishing-e-mailfiltervonnis** is **Quarantainebericht**, wat betekent dat phish ZAP het bericht standaard in quarantaine zet.

Zie [Antispambeleid configureren in Microsoft 365 voor](configure-your-spam-filter-policies.md)meer informatie over het configureren van spamfilteruitspraken.

### <a name="spam-zap"></a>Spam ZAP

Voor **ongelezen berichten** die na levering als spam worden geïdentificeerd, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor **het** spamfiltervonnis in het toepasselijke antispambeleid. De beschikbare filtering verdict acties voor spam en de mogelijke ZAP resultaten worden beschreven in de volgende lijst:

- **X-Header**, **Prepend onderwerpregel toevoegen met tekst:** ZAP onderneemt geen actie op het bericht.

- **Bericht verplaatsen naar ongewenste e-mail:** ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie [Instellingen voor ongewenste e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres**, **Bericht verwijderen**, **Quarantainebericht:** ZAP zet het bericht in quarantaine. Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.

Standaard is spam ZAP ingeschakeld in antispambeleid en de standaardactie voor **het** spamfiltervonnis is Bericht verplaatsen naar **ongewenste e-mailmap,** wat betekent dat spam ZAP **standaard ongelezen** berichten naar de map Ongewenste e-mail verplaatst.

Zie [Antispambeleid configureren in Microsoft 365 voor](configure-your-spam-filter-policies.md)meer informatie over het configureren van spamfilteruitspraken.

### <a name="zap-considerations-for-office-365-advanced-threat-protection-office-365-atp"></a>ZAP-overwegingen voor Geavanceerde bedreigingsbeveiliging van Office 365 (Office 365 ATP)

ZAP zal geen bericht in quarantaine plaatsen dat aan het scannen van [Dynamic Delivery](dynamic-delivery-and-previewing.md) is, of waar malwarefiltering de bijlage al heeft vervangen door het bestand Malware **Alert Text.txt.** Als een phish- of spamsignaal wordt ontvangen voor dit soort berichten en het filtervonnis in het antispambeleid is ingesteld om actie te ondernemen op het bericht (Verplaatsen naar ongewenstee items, omleiding, quarantaine, quarantaine) dan zal ZAP standaard een actie 'Verplaatsen naar ongewenste e-mail' uitvoeren.

## <a name="how-to-see-if-zap-moved-your-message"></a>Hoe u zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, u het [rapport Status bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report) of [Threat Explorer (en realtime detecties)](threat-explorer.md)gebruiken. Als systeemactie is ZAP niet aangemeld bij de controlelogboeken van het Exchange-postvak.

## <a name="zap-faq"></a>VEELgestelde VRAGEN OVER ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

U moet het normale rapportageproces volgen voor [false positives.](report-junk-email-messages-to-microsoft.md) De enige reden waarom het bericht zou worden verplaatst van de Inbox naar de map Ongewenste e-mail zou zijn omdat de service heeft vastgesteld dat het bericht was spam of kwaadaardig.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

ZAP onderneemt actie op basis van een bericht op basis van de configuratie van uw antispambeleid zoals eerder in dit onderwerp beschreven.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat moet ik doen als ik veilige afzenders, e-mailstroomregels of toegestane/geblokkeerde afzenderlijsten gebruik?

Veilige afzenders, regels voor e-mailstromen of het blokkeren en toestaan van organisatie-instellingen hebben voorrang. Deze berichten zijn uitgesloten van ZAP, omdat de service doet waarvoor u het hebt geconfigureerd. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filtering te omzeilen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht naar een andere map wordt verplaatst (bijvoorbeeld regels in postvak IN)?

ZAP werkt nog steeds zolang het bericht niet is verwijderd, of zolang dezelfde of sterker actie nog niet is toegepast. Als het phish-beleid bijvoorbeeld is ingesteld op quarantaine en de gebruiker of beheerder de e-mail al heeft gejunked, wordt er in quarantaine actie ondernomen om het bestand in quarantaine te plaatsen.

### <a name="does-zap-change-the-message-header"></a>Wijzigt ZAP de berichtkop?

Een ZAP-actie brengt geen wijzigingen aan in de berichtkop.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hoe beïnvloedt ZAP mailboxen in de wacht?

ZAP zal geen berichten van postvakken in de wacht plaatsen. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor een spam- of phishingvonnis in antispambeleid.

Zie [In-Place Hold en Litigation Hold in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over blokkeringen in Exchange Online.
