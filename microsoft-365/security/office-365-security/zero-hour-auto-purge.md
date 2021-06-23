---
title: Auto purge van nul uur in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 06/22/2021
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
description: Zap (Zero Hour Auto Purge) verplaatst bezorgde berichten in een Exchange Online-postvak met terugwerkende kracht naar de map Ongewenste e-mail of quarantaine die na bezorging spam of phishing zijn.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fdfc39b8bd18d33f95b85028e3661008a17a1209
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083498"
---
# <a name="zero-hour-auto-purge-zap-in-exchange-online"></a>Auto purge (ZAP) van nul uur in Exchange Online

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="zero-hour-auto-purge-zap-basics"></a>Basisbeginselen voor automatische automatische purge (ZAP) van nul uur

In Microsoft 365 organisaties met postvakken in Exchange Online is automatisch verwijderen van nul uur (ZAP) een functie voor e-mailbeveiliging waarmee schadelijke phishing-, spam- of malwareberichten die al in Exchange Online-postvakken zijn bezorgd, met terugwerkende kracht worden gedetecteerd en geneutraliseerd.

ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange beschermen.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Spam- en malwarehandtekeningen worden dagelijks in realtime in de service bijgewerkt. Gebruikers kunnen echter nog steeds om verschillende redenen schadelijke berichten ontvangen, waaronder als inhoud is gewapend nadat ze bij gebruikers zijn bezorgd. ZAP lost dit probleem op door updates voor de spam- en malwarehandtekeningen in de service voortdurend te controleren. ZAP kan berichten zoeken en verwijderen die al in het postvak van een gebruiker staan.

De ZAP-actie is naadloos voor de gebruiker. ze worden niet op de hoogte gesteld als een bericht wordt gedetecteerd en verplaatst.

[Safe afzenderlijsten,](create-safe-sender-lists-in-office-365.md)e-mailstroomregels (ook wel transportregels genoemd), Regels voor Postvak IN of extra filters hebben voorrang op ZAP. Net als wat er in de e-mailstroom gebeurt, betekent dit dat zelfs als de service bepaalt dat het bezorgde bericht ZAP nodig heeft, het bericht niet wordt gebruikt vanwege de veilige afzendersconfiguratie. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filteren te omzeilen.

### <a name="zero-hour-auto-purge-zap-for-malware"></a>Zero-hour auto purge (ZAP) voor malware

Voor **gelezen of ongelezen berichten** die na de bezorging malware bevatten, wordt het bericht met de malwarebijlage door ZAP in quarantaine geplaatst. Alleen beheerders kunnen malwareberichten vanuit quarantaine bekijken en beheren.

ZAP voor malware is standaard ingeschakeld in anti-malwarebeleid. Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md)voor meer informatie.

### <a name="zero-hour-auto-purge-zap-for-phishing"></a>Zero-hour Auto Purge (ZAP) voor phishing

Voor gelezen of **ongelezen** berichten die na de bezorging als phishing worden geïdentificeerd, is  het ZAP-resultaat afhankelijk van de actie die is geconfigureerd voor een phishing-e-mailfilteringsuitspraak in het toepasselijke antispambeleid. De beschikbare filteracties voor phishing en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-Header**, **Prepend onderwerpregel** met tekst toe , Bericht omleiden naar **e-mailadres**, **Bericht** verwijderen : ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar ongewenste** e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste e-mail configureren op [Exchange Online postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.

- **Quarantainebericht:** HET BERICHT wordt door ZAP in quarantaine geplaatst.

ZAP voor phishing is standaard ingeschakeld in antispambeleid en  de standaardactie voor het filteren van phishing-e-mail is **Quarantainebericht,** wat betekent dat ZAP voor phishing het bericht standaard in quarantaine zet.

Zie [Antispambeleid](configure-your-spam-filter-policies.md)configureren in Microsoft 365.

### <a name="zero-hour-auto-purge-zap-for-high-confidence-phishing"></a>Zero-hour auto purge (ZAP) voor phishing met hoog vertrouwen

Voor **gelezen of ongelezen berichten** die worden geïdentificeerd als phishing met veel vertrouwen na de bezorging, wordt het bericht door ZAP in quarantaine geplaatst. Alleen beheerders kunnen phish-berichten met veel vertrouwen vanuit quarantaine bekijken en beheren.

ZAP voor phish met hoog vertrouwen is standaard ingeschakeld. Zie Standaard Beveiligen [in Office 365.](secure-by-default.md)

### <a name="zero-hour-auto-purge-zap-for-spam"></a>Zero-hour auto purge (ZAP) voor spam

Voor **ongelezen berichten** die na de bezorging als spam worden geïdentificeerd, is het  ZAP-resultaat afhankelijk van de actie die is geconfigureerd voor de uitspraak over spamfilters in het toepasselijke antispambeleid. De beschikbare filteracties voor spam en de mogelijke ZAP-resultaten worden in de volgende lijst beschreven:

- **Voeg X-Header**, **Prepend onderwerpregel** met tekst toe , Bericht omleiden naar **e-mailadres**, **Bericht** verwijderen : ZAP voert geen actie uit op het bericht.

- **Bericht verplaatsen naar ongewenste** e-mail: ZAP verplaatst het bericht naar de map Ongewenste e-mail, zolang de regel voor ongewenste e-mail is ingeschakeld in het postvak (het is standaard ingeschakeld). Zie Instellingen voor ongewenste e-mail configureren op [Exchange Online postvakken in](configure-junk-email-settings-on-exo-mailboxes.md)Microsoft 365.

- **Quarantainebericht:** HET BERICHT wordt door ZAP in quarantaine geplaatst. Eindgebruikers kunnen hun eigen spamberichten in quarantaine bekijken en beheren.

Spam ZAP is standaard ingeschakeld in antispambeleid en de  standaardactie voor het filteren van spam **is**  Bericht verplaatsen naar de map Ongewenste e-mail, wat betekent dat spam ZAP ongelezen berichten standaard naar de map Ongewenste e-mail verplaatst.

Zie [Antispambeleid](configure-your-spam-filter-policies.md)configureren in Microsoft 365.

### <a name="zero-hour-auto-purge-zap-considerations-for-microsoft-defender-for-office-365"></a>Zap-overwegingen (Zero Hour Auto Purge) voor Microsoft Defender voor Office 365

ZAP zet geen berichten in quarantaine die bezig zijn met dynamische bezorging [in](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies) het scannen van Safe Bijlagen, of waar EOP-malwarefilters de bijlage al hebben vervangen door het malwarewaarschuwingsbestand **Text.txt** bestand. Als er een phishing- of spamsignaal wordt ontvangen voor dit type berichten en het filterbeleid in het antispambeleid is ingesteld op actie ondernemen op het bericht (Verplaatsen naar ongewenste e-mail, Omleiden, Verwijderen of Quarantaine) wordt zap standaard ingesteld op een actie 'Verplaatsen naar ongewenste e-mail'.

## <a name="how-to-see-if-zap-moved-your-message"></a>Zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, kunt u het rapport Threat [Protection Status of](view-email-security-reports.md#threat-protection-status-report) Threat Explorer [(en realtime detecties) gebruiken.](threat-explorer.md) Houd er rekening mee dat ZAP als een systeemactie niet is aangemeld in de Exchange auditlogboeken voor postvakken.

## <a name="zero-hour-auto-purge-zap-faq"></a>Veelgestelde vragen over auto purge (ZAP) van nul uur

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-email-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map Ongewenste e-mail?

U moet het normale rapportageproces voor [fout-positieven volgen.](report-junk-email-messages-to-microsoft.md) De enige reden dat het bericht zou worden verplaatst van het Postvak IN naar de map Ongewenste e-mail, is omdat de service heeft vastgesteld dat het bericht spam of schadelijk was.

### <a name="what-if-i-use-the-quarantine-folder-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de map Quarantaine gebruik in plaats van de map Ongewenste e-mail?

ZAP onderneemt actie op basis van een bericht op basis van de configuratie van uw antispambeleid, zoals eerder in dit artikel wordt beschreven.

### <a name="what-if-im-using-safe-senders-mail-flow-rules-or-allowedblocked-sender-lists"></a>Wat gebeurt er als ik veilige afzenders, regels voor e-mailstroom of lijsten met toegestane/geblokkeerde afzenders gebruik?

Safe afzenders, e-mailstroomregels of blokkeren en toestaan dat organisatie-instellingen voorrang krijgen. Deze berichten zijn uitgesloten van ZAP omdat de service doet waarvoor u deze hebt geconfigureerd. Dit is een andere reden om voorzichtig te zijn met het configureren van berichten om filteren te omzeilen.

### <a name="what-are-the-licensing-requirements-for-zero-hour-auto-purge-zap-to-work"></a>Wat zijn de licentievereisten voor automatische purge (ZAP) van nul uur om te werken?

Er zijn geen beperkingen voor licenties. ZAP werkt op alle postvakken die worden gehost op Exchange online. ZAP werkt niet in zelfstandige Exchange Online Protection (EOP)-omgevingen die on-premises Exchange beschermen.

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rules"></a>Wat gebeurt er als een bericht wordt verplaatst naar een andere map (bijvoorbeeld Regels voor Postvak IN)?

Automatische purge van nul uur werkt nog steeds zolang het bericht niet is verwijderd, of zolang dezelfde of sterkere actie nog niet is toegepast. Als het anti-phishingbeleid bijvoorbeeld is ingesteld op quarantaine en het bericht al in de ongewenste e-mail staat, zal ZAP actie ondernemen om het bericht in quarantaine te plaatsen.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Wat is de invloed van ZAP op postvakken in de wacht?

Berichten van postvakken die in de wacht staan, worden in quarantaine geplaatst. ZAP kan berichten verplaatsen naar de map Ongewenste e-mail op basis van de actie die is geconfigureerd voor spam of phishing in antispambeleid.

Zie [In-Place Hold](/Exchange/security-and-compliance/in-place-and-litigation-holds)and Litigation Hold in Exchange Online Exchange Online voor meer informatie over in- en Exchange Online.
