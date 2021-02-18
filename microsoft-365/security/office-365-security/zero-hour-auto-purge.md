---
title: Zero-hour Auto Purge (ZAP)
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
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
description: Beheerders kunnen met terugwerkende kracht bezorgde berichten in een Exchange Online-postvak met terugwerkende kracht verplaatsen naar de map Ongewenste e-mail of quarantaine die met terugwerkende kracht spam of phishing worden gevonden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5fd41cf45ad2a49d74684ae3e20dded5c1b8f034
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287303"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Zero-hour auto purge (ZAP) in Exchange Online

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Basisfuncties van ZAP

In Microsoft 365-organisaties met postvakken in Exchange Online is Zero-Hour Auto Purge (ZAP) een e-mailbeveiligingsfunctie waarmee met terugwerkende kracht schadelijke phishing-, spam- of malwareberichten worden gedetecteerd en gedetecteerd die al in Exchange Online-postvakken zijn bezorgd.

ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange-postvakken beschermen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Spam- en malwarehandtekeningen worden dagelijks in realtime in de service bijgewerkt. Gebruikers kunnen echter nog steeds om verschillende redenen schadelijke berichten ontvangen, bijvoorbeeld als inhoud wordt gedimd nadat deze bij gebruikers is bezorgd. ZAP lost dit probleem op door voortdurend updates van de spam en malwarehandtekeningen in de service te controleren. ZAP kan berichten zoeken en verwijderen die al in het postvak van een gebruiker staan.

De ZAP-actie is naadloos voor de gebruiker; er wordt geen melding weergegeven als er een bericht is gedetecteerd en verplaatst.

[Lijsten met veilige afzenders,](create-safe-sender-lists-in-office-365.md)regels voor de e-mailstroom (ook wel transportregels genoemd), Regels voor Postvak IN of aanvullende filters hebben voorrang op ZAP. Net zoals in de e-mailstroom gebeurt, betekent dit dat zelfs als de service bepaalt dat ZAP nodig is voor het bezorgde bericht, het bericht niet wordt geacteerd vanwege de configuratie voor veilige afzenders. Dit is een andere reden om voorzichtig te zijn bij het configureren van berichten om filters te omzeilen.

### <a name="malware-zap"></a>Malware ZAP

Voor **gelezen of ongelezen berichten** die na bezorging malware bevatten, wordt het bericht dat de malwarebijlage bevat in quarantaine geplaatst door ZAP. Alleen beheerders kunnen malwareberichten in quarantaine weergeven en beheren.

Malware ZAP is standaard ingeschakeld in antimalwarebeleidsregels. Zie [Antimalwarebeleid](configure-anti-malware-policies.md)configureren in EOP voor meer informatie.

### <a name="phish-zap"></a>Phish ZAP

Voor gelezen of **ongelezen** berichten die na bezorging als phishing zijn aangemerkt, hangt ZAP af van de actie die is geconfigureerd voor het filteren van phishing-e-mails in het toepasselijke antispambeleid.  De beschikbare filteracties voor phishing en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-header** toe, **onderwerpregel laten voorvoegen met tekst:** ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar Ongewenste** e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (deze is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres,** **Bericht verwijderen,** **Quarantainebericht:** ZAP quarantaines het bericht.

Standaard is phish ZAP ingeschakeld in antispambeleid en de  standaardactie voor het filteren van phishing-e-mails is **quarantainebericht,** wat betekent dat phish ZAP het bericht standaard in quarantaine zet.

Zie Antispambeleid configureren in [Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spamfilters.

### <a name="spam-zap"></a>Spam ZAP

Voor **ongelezen berichten** die na bezorging als spam zijn aangemerkt, is de ZAP-uitkomst afhankelijk van de actie die is geconfigureerd voor het spamfilter in het toepasselijke antispambeleid.  De beschikbare filteracties voor spam en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-header** toe, **onderwerpregel laten voorvoegen met tekst:** ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar** Ongewenste e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (deze is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Bericht omleiden naar e-mailadres,** **Bericht verwijderen,** **Quarantainebericht:** ZAP quarantaines het bericht. Eindgebruikers kunnen hun eigen berichten in quarantaine weergeven en beheren.

Standaard is spam ZAP ingeschakeld in antispambeleid en de  standaardactie voor de spamfilteractie is Bericht  verplaatsen naar de map Ongewenste e-mail, wat betekent dat spam ZAP standaard ongelezen berichten verplaatst naar de map Ongewenste e-mail.

Zie Antispambeleid configureren in [Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van spamfilters.

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-overwegingen voor Microsoft Defender voor Office 365

ZAP stuurt geen berichten in quarantaine die bezig zijn met het scannen van dynamische bezorging [in](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) veilige bijlagen of waarbij het malwarefilter van EOP de bijlage al heeft vervangen door het bestand **Malwarewaarschuwing Text.txt** bestand. Als er een phishing- of spamsignaal wordt ontvangen voor dit soort berichten en het filterfilter in het antispambeleid zo is ingesteld dat er actie wordt ondernomen op het bericht (Verplaatsen naar Ongewenste e-mail, Omleiden, Verwijderen of Quarantaine), dan wordt ZAP standaard ingesteld op 'Verplaatsen naar ongewenste e-mail'.

## <a name="how-to-see-if-zap-moved-your-message"></a>Zien of ZAP uw bericht heeft verplaatst

Om te bepalen of ZAP uw bericht heeft verplaatst, kunt u het rapport Status van bedreigingsbeveiliging [of](view-email-security-reports.md#threat-protection-status-report) Bedreigingsverkenner [(en realtime detecties) gebruiken.](threat-explorer.md) Als systeemactie is ZAP niet aangemeld in de auditlogboeken van Exchange-postvakken.

## <a name="zap-faq"></a>Veelgestelde vragen over ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

U moet de normale procedure voor het rapporteren van [fout-positieven volgen.](report-junk-email-messages-to-microsoft.md) De enige reden waarom het bericht uit het Postvak IN naar de map Ongewenste e-mail zou worden verplaatst, is omdat de service heeft vastgesteld dat het bericht spam of schadelijk is.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat gebeurt er als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

ZAP onderneemt actie op basis van de configuratie van uw antispambeleid, zoals eerder in dit artikel beschreven.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat gebeurt er als ik veilige afzenders, regels voor e-mailstroom of lijsten met toegestane/geblokkeerde afzenders gebruik?

Veilige afzenders, regels voor e-mailstroom, of organisatie-instellingen blokkeren en toestaan die prioriteit hebben. Deze berichten zijn uitgesloten van ZAP omdat de service doet waarvoor u deze hebt geconfigureerd. Dit is een andere reden om voorzichtig te zijn bij het configureren van berichten om filters te omzeilen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht naar een andere map wordt verplaatst (zoals regels voor Postvak IN)?

ZAP werkt nog steeds zolang het bericht niet is verwijderd, of als dezelfde, of sterkere actie nog niet is toegepast. Als het anti-phishingbeleid bijvoorbeeld is ingesteld op quarantaine en het bericht al in de map Ongewenste e-mail staat, wordt er door ZAP actie ondernomen om het bericht in quarantaine te plaatsen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wat is de invloed van ZAP op postvakken die in de wacht staan?

ZAP gaat geen berichten in quarantaine plaatsen uit postvakken die in de wacht staan. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor een spam- of phishingactie in antispambeleid.

Zie In-place hold en Litigation Hold in Exchange Online voor meer informatie over [in-place](https://docs.microsoft.com/Exchange/security-and-compliance/in-place-and-litigation-holds)hold en litigation hold in Exchange Online.
