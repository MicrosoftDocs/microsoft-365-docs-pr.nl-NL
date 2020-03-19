---
title: Zero-hour automatische zuivering - bescherming tegen spam en malware
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
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
description: Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging die berichten detecteert met spam of malware die al zijn geleverd aan de inboxen van uw gebruikers en vervolgens de schadelijke inhoud onschadelijk maakt. Hoe ZAP dit doet, hangt af van het type schadelijke inhoud dat wordt gedetecteerd.
ms.openlocfilehash: 6616281a98487c7edd7ca7721ade9a8510f6a21f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811658"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>Zero-hour automatische zuivering - bescherming tegen spam en malware

## <a name="overview"></a>Overzicht

Zero-hour auto purge (ZAP) is een functie voor e-mailbeveiliging die berichten detecteert met phish, spam of malware die al zijn geleverd aan de inboxen van uw gebruikers en vervolgens de schadelijke inhoud onschadelijk maakt. Hoe ZAP dit doet, hangt af van het type schadelijke inhoud dat wordt gedetecteerd. E-mail kan worden gezapped als gevolg van e-mailinhoud, URL's of bijlagen.

ZAP is beschikbaar met de standaard Exchange Online Protection die is inbegrepen bij elk Office 365-abonnement dat Exchange Online-postvakken bevat.

## <a name="how-zap-works"></a>Hoe ZAP werkt

Office 365 werkt dagelijks handtekeningen van antispam-engineen en malware in realtime bij. Uw gebruikers kunnen echter nog steeds schadelijke berichten naar hun inboxen krijgen om verschillende redenen, waaronder als inhoud wordt bewapend nadat ze aan gebruikers zijn geleverd. ZAP pakt dit op door voortdurend updates van de office 365-spam- en malwarehandtekeningen te controleren. ZAP kan eerder geleverde berichten vinden en verwijderen die al in de inboxen van gebruikers staan.

De ZAP-actie is naadloos voor de gebruiker van het postvak; ze worden niet op de hoogte gesteld als een e-mailbericht wordt verplaatst. 

Sta lijsten, [e-mailstroomregels](use-transport-rules-to-configure-bulk-email-filtering.md) (ook wel transportregels genoemd) toe en regels voor eindgebruikers of extra filters hebben voorrang op ZAP.

### <a name="malware-zap"></a>Malware ZAP

Voor nieuw gedetecteerde malware verplaatst ZAP het hele bericht, inclusief de bijlage ervan, naar malware Quarantine. Berichten worden verplaatst, ongeacht de leesstatus van de e-mail. Als we een malwaresignaal krijgen voor een bericht tijdens het scannen van Dynamic Delivery, neemt ZAP een Move to Junk-actie op het bericht. Dan kan Dynamic Delivery de time of delivery-scan voltooien en de juiste actie ondernemen.

Malware ZAP is standaard ingeschakeld in het malwarebeleid. U malware ZAP uitschakelen met behulp van de parameter *ZapEnabled* op de cmdlet [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in Exchange Online PowerShell of Exchange Online Protection PowerShell. Malware ZAP kan ook worden ingeschakeld of uitgeschakeld door het malwarebeleid in het Beveiligings- en Compliancecenter te bewerken.

### <a name="phish-zap"></a>Phish ZAP

Voor e-mail die na levering als phish is geïdentificeerd, onderneemt ZAP actie volgens het spambeleid dat betrekking heeft op een specifieke gebruiker, ongeacht de leesstatus van de e-mail. Als de phish-actie van het beleid is ingesteld om *geen* actie te ondernemen (X-header toevoegen, Onderwerp wijzigen, Geen actie) dan onderneemt ZAP geen actie op de e-mail. Als de Phish-actie is ingesteld op Verplaatsen naar Ongewenste e-mail, verplaatst ZAP het bericht naar de map Ongewenste e-mail van de postvak in de gebruiker. **Voor elke andere Phish-actie (Redirect, Delete, Quarantine) verplaatst ZAP het bericht naar phish Quarantine**. Lees hieronder voor configuratievereisten en uitsluitingen. Meer informatie over het [configureren van uw beleid voor spamfilters](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) vindt u hier.

Phish ZAP is standaard ingeschakeld in het spambeleid. Phish ZAP kan worden uitgeschakeld met behulp van de *PhishZapEnabled* parameter van [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), een EOP cmdlet.

### <a name="spam-zap"></a>Spam ZAP

Voor e-mail die na levering als spam wordt geïdentificeerd, onderneemt ZAP actie volgens het spambeleid dat betrekking heeft op de specifieke gebruiker, alleen als het bericht ongelezen is.  Als de actie Voor spam van het beleid is ingesteld om geen actie te ondernemen (X-header toevoegen, Onderwerp wijzigen, Geen actie) dan onderneemt ZAP geen actie op de e-mail. Als de actie Spam is ingesteld op Verplaatsen naar Ongewenste e-mail, verplaatst ZAP het bericht naar de map Ongewenste e-mail van het postvak in de gebruiker. **Voor elke andere spamactie (Redirect, Delete, Quarantine) verplaatst ZAP het bericht naar spam quarantaine.** Lees hieronder voor configuratievereisten en uitsluitingen. Meer informatie over het [configureren van uw beleid voor spamfilters](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) vindt u hier.

Spam ZAP is standaard ingeschakeld in het spambeleid. U Spam ZAP uitschakelen met behulp van de parameter *SpamZapEnabled* van [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) cmdlet in Exchange Online PowerShell of Exchange Online Protection PowerShell.

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>Phish- en Spam ZAP-vereisten, uitsluitingen en aankondigingen

> [!IMPORTANT]
> de vorige *ZapEnabled* cmdlet parameter die zowel Phish als Spam ZAP controleerde, wordt **op 1 februari 2020 afgeschaft.** Als u scripts hebt geschreven die de parameter ZapEnabled gebruiken, raden we u aan deze bij te werken om SpamZapEnabled en PhishZapEnabled te gebruiken. In de overgangsperiode zijn alle 3 parameters (ZapEnabled, PhishZapEnabled en SpamZapEnabled) beschikbaar via de cmdlet. Totdat phishZapEnabled en SpamZapEnabled expliciet via UI of PowerShell zijn ingesteld, wordt een overgenomen waarde van de parameter ZapEnabled weergegeven. Zodra de nieuwe parameters zijn ingesteld, zullen ze niet langer overerven van de parameter ZapEnabled. Nadat de instelling is afgeschaft, heeft ZapEnabled geen invloed op de eigenschappen PhishZapEnabled of SpamZapEnabled en wordt ZapEnabled verwijderd uit de lijst met parameters in cmdlets.

ZAP zal geen bericht verplaatsen naar Quarantaine die in het proces van Dynamic Delivery scannen, of die al een malware vonnis met een vervangen bijlage. Als een phish- of spamsignaal wordt ontvangen voor dit soort berichten en het spambeleid / Phish-actie is ingesteld om actie te ondernemen (Verplaatsen naar ongewenstee, omleiding, verwijdering, quarantaine) dan zal ZAP standaard een actie 'Verplaatsen naar ongewenste e-mail' uitvoeren. Als ZAP een actie 'Verplaatsen naar ongewenstee' actie op een bericht wilt uitvoeren, moet de gebruiker de beveiliging van ongewenste e-mail hebben ingeschakeld, met de standaardinstellingen voor ongewenste e-mail. (Zie [Het beschermingsniveau in het filter voor ongewenste e-mail wijzigen](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) voor meer informatie over gebruikersopties in Outlook.)

## <a name="how-to-see-if-zap-moved-your-message"></a>Hoe u zien of ZAP uw bericht heeft verplaatst

Als u wilt bepalen of ZAP uw bericht heeft verplaatst, u het [rapport Status bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report) of [Threat Explorer (en realtime detecties)](threat-explorer.md)gebruiken. Houd er rekening mee dat ZAP als systeemactie niet is aangemeld bij controlelogboeken van exchange mailboxen. 
 
## <a name="disable-zap"></a>ZAP uitschakelen

Zie Verbinding maken met Exchange Online PowerShell als u verbinding wilt maken met Exchange Online [PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met Exchange Online Protection PowerShell.

### <a name="disable-malware-zap"></a>Malware ZAP uitschakelen**

Malware ZAP kan worden uitgeschakeld via de *parameter ZapEnabled* op de [cmdlet Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) in Exchange Online PowerShell of Exchange Online Protection PowerShell. Malware ZAP kan ook worden ingeschakeld of uitgeschakeld door het malwarebeleid in het Beveiligings- en Compliancecenter te bewerken.

In dit voorbeeld wordt ZAP uitgeschakeld in het beleid voor malwarefilters met de naam 'Testen'.

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

Zie [Set-MalwareFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)gedetailleerde syntaxis- en parameterinformatie.

### <a name="disable-phish-zap-and-spam-zap"></a>Phish ZAP en Spam ZAP uitschakelen

Als u Phish- en Spam ZAP wilt uitschakelen voor uw O365-tenant of een set gebruikers, gebruikt u de *PhishZapEnabled-* en *SpamZapEnabled-parameters* van [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy), een EOP-cmdlet.

In het volgende voorbeeld worden phish en spam ZAP uitgeschakeld voor een inhoudsfilterbeleid met de naam 'Testen'.

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

Zie [Set-HostedContentFilterPolicy voor](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)gedetailleerde syntaxis- en parameterinformatie.

## <a name="faq"></a>Veelgestelde vragen

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>Wat gebeurt er als een legitiem bericht wordt verplaatst naar de map met ongewenste e-mail?

U moet het normale rapportageproces volgen voor [false-positives.](prevent-email-from-being-marked-as-spam.md) De enige reden waarom het bericht zou worden verplaatst van de inbox naar de junk mail map zou zijn omdat de dienst heeft vastgesteld dat het bericht was spam of kwaadaardig.

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>Wat moet ik doen als ik de quarantaine van Office 365 gebruik in plaats van de map met ongewenste e-mail?

ZAP onderneemt actie op basis van de configuratie van de actie-instellingen Phish en Spam in uw antispambeleid. Zie hierboven voor meer informatie over Malware, Phish en Spam ZAP.

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>Wat moet ik doen als ik een aangepaste regel voor e-mailstroom heb (Regel blokkeren/ toestaan)?

Regels die zijn gemaakt door beheerders (regels voor e-mailstromen) of Regels blokkeren en toestaan hebben voorrang. Dergelijke berichten zijn uitgesloten van de functiecriteria, zodat de e-mailstroom de regelactie volgt (Regel blokkeren/toestaan).

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>Wat gebeurt er als een bericht naar een andere map wordt verplaatst (bijvoorbeeld de regel in postvak IN)?

ZAP werkt nog steeds in dit geval, tenzij het bericht is verwijderd of in Ongewenste e-mail staat.

### <a name="does-zap-change-the-email-header"></a>Wijzigt ZAP de e-mailheader?

Een ZAP-actie brengt geen wijzigingen aan in de koptekst van een e-mail.

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>Hoe beïnvloedt ZAP mailboxen in Hold?

ZAP verwijdert geen berichten uit in de wachtstaande postvakken en onderneemt daarom geen actie Verplaatsen naar quarantaine op berichten. Berichten worden nog steeds verplaatst naar de map Ongewenste e-mail als dit is opgegeven door het beleid. 

[Klik hier voor meer informatie over mailboxholds.](https://docs.microsoft.com/exchange/policy-and-compliance/holds/holds?view=exchserver-2019)

## <a name="related-topics"></a>Verwante onderwerpen

[Beveiliging van antispam in Office 365](anti-spam-protection.md)

[Block email spam with the Office 365 spam filter to prevent false negative issues](reduce-spam-email.md)
