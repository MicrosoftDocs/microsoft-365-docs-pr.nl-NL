---
title: Automatische purge van nul uur (ZAP)
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
description: Beheerders kunnen meer informatie krijgen over hoe zap (Zero Hour Auto Purge) bezorgde berichten in een Exchange Online-postvak met terugwerkende kracht kan verplaatsen naar de map Ongewenste e-mail of quarantaine die met terugwerkende kracht spam of phishing zijn.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b5744fdd4ce371f62fcb4b07a4cbcd003405c3db
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907974"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Auto Purge (ZAP) van nul uur in Exchange Online

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-features-of-zap"></a>Basisfuncties van ZAP

In Microsoft 365-organisaties met postvakken in Exchange Online is automatisch verwijderen van nul uur (ZAP) een functie voor e-mailbeveiliging waarmee schadelijke phishing-, spam- of malwareberichten die al in Exchange Online-postvakken zijn bezorgd, met terugwerkende kracht worden gedetecteerd en geneutraliseerd.

ZAP werkt niet in zelfstandige EOP-omgevingen (Exchange Online Protection) die on-premises Exchange-postvakken beveiligen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Spam- en malwarehandtekeningen worden dagelijks in realtime in de service bijgewerkt. Gebruikers kunnen echter nog steeds om verschillende redenen schadelijke berichten ontvangen, waaronder als inhoud is gewapend nadat ze bij gebruikers zijn bezorgd. ZAP lost dit probleem op door updates voor de spam- en malwarehandtekeningen in de service voortdurend te controleren. ZAP kan berichten zoeken en verwijderen die al in het postvak van een gebruiker staan.

De ZAP-actie is naadloos voor de gebruiker. ze worden niet op de hoogte gesteld als een bericht wordt gedetecteerd en verplaatst.

[Lijsten met veilige afzenders,](create-safe-sender-lists-in-office-365.md)regels voor e-mailstroom (ook wel transportregels genoemd), Regels voor Postvak IN of extra filters hebben voorrang op ZAP. Net als wat er in de e-mailstroom gebeurt, betekent dit dat zelfs als de service bepaalt dat het bezorgde bericht ZAP nodig heeft, het bericht niet wordt gebruikt vanwege de veilige afzendersconfiguratie. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filteren te omzeilen.

### <a name="malware-zap"></a>Malware ZAP

Voor **gelezen of ongelezen berichten** die na de bezorging malware bevatten, wordt het bericht met de malwarebijlage door ZAP in quarantaine geplaatst. Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.

Malware ZAP is standaard ingeschakeld in anti-malwarebeleid. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.

### <a name="phish-zap"></a>Phish ZAP

Voor gelezen of **ongelezen** berichten die na de bezorging als phishing worden geïdentificeerd, is  het ZAP-resultaat afhankelijk van de actie die is geconfigureerd voor een phishing-e-mailfilteringsuitspraak in het toepasselijke antispambeleid. De beschikbare filteracties voor phishing en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-Header**, **Prepend onderwerpregel** met tekst toe , Bericht omleiden naar **e-mailadres**, **Bericht** verwijderen : ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar ongewenste** e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Quarantainebericht:** HET BERICHT wordt door ZAP in quarantaine geplaatst.

Phish ZAP is standaard ingeschakeld in antispambeleid en de  standaardactie voor het filteren van phishing-e-mail is **Quarantainebericht,** wat betekent dat phish ZAP het bericht standaard in quarantaine zet.

Zie Antispambeleid configureren in [Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van antispambeleid.

### <a name="spam-zap"></a>Spam ZAP

Voor **ongelezen berichten** die na de bezorging als spam worden geïdentificeerd, is het  ZAP-resultaat afhankelijk van de actie die is geconfigureerd voor de uitspraak over spamfilters in het toepasselijke antispambeleid. De beschikbare filteracties voor spam en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-Header**, **Prepend onderwerpregel** met tekst toe , Bericht omleiden naar **e-mailadres**, **Bericht** verwijderen : ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar ongewenste** e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste [e-mail configureren in Exchange Online-postvakken in Microsoft 365](configure-junk-email-settings-on-exo-mailboxes.md)voor meer informatie.

- **Quarantainebericht:** HET BERICHT wordt door ZAP in quarantaine geplaatst. Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.

Spam ZAP is standaard ingeschakeld in antispambeleid en de  standaardactie voor het filteren van spam **is**  Bericht verplaatsen naar de map Ongewenste e-mail, wat betekent dat spam ZAP ongelezen berichten standaard naar de map Ongewenste e-mail verplaatst.

Zie Antispambeleid configureren in [Microsoft 365](configure-your-spam-filter-policies.md)voor meer informatie over het configureren van antispambeleid.

### <a name="zap-considerations-for-microsoft-defender-for-office-365"></a>ZAP-overwegingen voor Microsoft Defender voor Office 365

ZAP zet geen berichten in quarantaine die bezig zijn met dynamische bezorging [in](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) het scannen van veilige bijlagen, of waar EOP-malwarefilters de bijlage al hebben vervangen door het bestand **MalwareWaarschuwing Text.txt** bestand. Als er een phishing- of spamsignaal wordt ontvangen voor dit type berichten en het filterbeleid in het antispambeleid is ingesteld op actie ondernemen op het bericht (Verplaatsen naar ongewenste e-mail, Omleiden, Verwijderen of Quarantaine) wordt zap standaard ingesteld op een actie 'Verplaatsen naar ongewenste e-mail'.

## <a name="how-to-see-if-zap-moved-your-message"></a>Zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, kunt u het rapport Threat [Protection Status of](view-email-security-reports.md#threat-protection-status-report) Threat Explorer [(en realtime detecties) gebruiken.](threat-explorer.md) Als systeemactie wordt ZAP niet geregistreerd in de auditlogboeken van Exchange-postvakken.

## <a name="zap-faq"></a>VEELGESTELDE VRAGEN OVER ZAP

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

U moet het normale rapportageproces voor [fout-positieven volgen.](report-junk-email-messages-to-microsoft.md) De enige reden dat het bericht zou worden verplaatst van het Postvak IN naar de map Ongewenste e-mail, is omdat de service heeft vastgesteld dat het bericht spam of schadelijk was.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

ZAP onderneemt actie op basis van een bericht op basis van de configuratie van uw antispambeleid, zoals eerder in dit artikel wordt beschreven.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat gebeurt er als ik veilige afzenders, regels voor e-mailstroom of lijsten met toegestane/geblokkeerde afzenders gebruik?

Veilige afzenders, regels voor e-mailstromen of blokkeren en toestaan dat organisatie-instellingen voorrang krijgen. Deze berichten zijn uitgesloten van ZAP omdat de service doet waarvoor u deze hebt geconfigureerd. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filteren te omzeilen.

### <a name="what-are-the-licensing-requirements-for-zap-to-work"></a>Wat zijn de licentievereisten voor ZAP om te werken?

Er zijn geen beperkingen voor licenties. ZAP werkt op alle postvakken die worden gehost op Exchange Online. ZAP werkt niet in zelfstandige EOP-omgevingen (Exchange Online Protection) die on-premises Exchange-postvakken beveiligen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht wordt verplaatst naar een andere map (bijvoorbeeld Regels voor Postvak IN)?

ZAP werkt nog steeds zolang het bericht niet is verwijderd, of zolang dezelfde of sterkere actie nog niet is toegepast. Als het anti-phishingbeleid bijvoorbeeld is ingesteld op quarantaine en het bericht al in de ongewenste e-mail staat, zal ZAP actie ondernemen om het bericht in quarantaine te plaatsen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wat is de invloed van ZAP op postvakken in de wacht?

ZAP zal geen berichten uit postvakken in quarantaine plaatsen in de wacht. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor spam of phishing in antispambeleid.

Zie [In-Place Hold and Litigation Hold in Exchange Online (In-Place Hold and Litigation Hold in Exchange Online)](/Exchange/security-and-compliance/in-place-and-litigation-holds)voor meer informatie over het houden van in exchange online.