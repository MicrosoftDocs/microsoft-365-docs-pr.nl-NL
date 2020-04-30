---
title: Microsoft-aanbevelingen voor EOP- en Office 365 ATP-beveiligingsinstellingen, aanbevelingen, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, stappen, hoe werkt het, beveiligingsbasislijnen, basislijnen voor EOP, basislijnen voor ATP, setup ATP, setup EOP, configureren ATP, configureren EOP, beveiligingsconfiguratie
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Wat zijn best practices voor Exchange Online Protection (EOP) en Advanced Threat Protection (ATP) beveiligingsinstellingen? Wat zijn de huidige aanbevelingen voor standaardbescherming? Wat moet worden gebruikt als u strenger wilt zijn? En welke extra's krijg je als je ook gebruik maakt van Advanced Threat Protection (ATP)?
ms.openlocfilehash: a88d58db68816cd6aeb9173c36b964f3f97653db
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949223"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging

**Exchange Online Protection (EOP)** is de kern van beveiliging voor Microsoft 365-abonnementen en helpt voorkomen dat schadelijke e-mails de inboxen van uw werknemer bereiken. Maar met nieuwe, meer geavanceerde aanvallen die elke dag opduiken, zijn er vaak betere beveiligingen nodig. **Office 365 Advanced Threat Protection (ATP)** ATP Plan 1 of ATP Plan 2 bevatten extra functies die beheerders meer beveiliging, controle en onderzoek geven.

Hoewel we beveiligingsbeheerders in staat stellen hun beveiligingsinstellingen aan te passen, zijn er twee beveiligingsniveaus in EOP en Office 365 ATP die we aanbevelen: **Standaard** en **Strikt.** De omgeving en behoeften van elke klant zijn verschillend, maar we zijn van mening dat deze niveaus van e-mailfilteringconfiguraties zullen helpen voorkomen dat ongewenste e-mail in de meeste situaties de inbox van uw werknemers bereikt.

> [!IMPORTANT]
> De regel voor ongewenste e-mail moet in een postvak worden ingeschakeld om te kunnen filteren om goed te kunnen filteren. Het is standaard ingeschakeld, maar u moet controleren of het filteren niet lijkt te werken. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit onderwerp worden deze door Microsoft aanbevolen instellingen beschreven om uw gebruikers te beschermen.

> [!TIP]
> Er is een nieuwe PowerShell-module die u downloaden, de Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) die helpt bij het bepalen van een aantal van deze instellingen. Wanneer u wordt uitgevoerd als beheerder in uw tenant, helpt Get-ORCAReport bij het genereren van een beoordeling van de anti-spam-, anti-phish- en andere instellingen voor berichthygiëne. U deze https://www.powershellgallery.com/packages/ORCA/module downloaden op.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware en bescherming tegen phishing in EOP

Anti-spam, anti-malware en anti-phishing zijn functies van EOP die door beheerders kunnen worden geconfigureerd. Wij raden de volgende configuraties aan.

### <a name="eop-anti-spam-policy-settings"></a>EOP-beleidsinstellingen voor spam

Zie [Antispambeleid configureren in Office 365](configure-your-spam-filter-policies.md)voor het maken en configureren van antispambeleid.

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Spamdetectieactie** <br/><br/> _SpamActie_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantainebericht** <br/><br/> `Quarantine`||
|**Actie voor spamdetectie** met hoog vertrouwen <br/><br/> _HighConfidenceSpamAction_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|Actie voor detectie van **phishing-e-mail** <br/><br/> _PhishSpamAction PhishSpamActie_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|**Hoog vertrouwen phishing e-mail** detectie actie <br/><br/> _HighConfidencePhishActie_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|Actie voor detectie van **bulke-mail** <br/><br/> _BulkSpamActie_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantainebericht** <br/><br/> `Quarantine`||
|Drempelwaarde voor bulke-mail <br/><br/> _Bulkdrempel_|6|4|De standaardwaarde is momenteel 7, maar we raden u aan deze te wijzigen in 6. Zie [Bulkklachtenniveau (BCL) in Office 365 voor](bulk-complaint-level-values.md)meer informatie.|
|Bewaartermijn quarantaine <br/><br/> _QuarantaineBewaarperiode_|30 dagen|30 dagen||
|**Veiligheidstips** <br/><br/> _InlineSafetyTipsIngeschakeld_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Toegestane afzenders <br/><br/> _Toegestane afzenders_|Geen|Geen||
|Toegestane afzenderdomeinen <br/><br/> _Toegestane SenderDomains_|Geen|Geen|Het is niet vereist om domeinen die u bezit (ook wel _geaccepteerde domeinen_genoemd) toe te voegen aan de lijst met toegestane afzenders. In feite wordt het beschouwd als een hoog risico, omdat het kansen creëert voor slechte acteurs om u e-mail te sturen die anders zou worden gefilterd. Gebruik [spoofinformatie](learn-about-spoof-intelligence.md) in het Security & Compliance Center op de pagina **Antispam-instellingen** om alle afzenders te controleren die e-mailadressen van afzenders in de e-maildomeinen van uw organisatie spoofen of e-mailadressen van afzenders in externe domeinen spoofen.|
|Geblokkeerde afzenders <br/><br/> _Geblokkeerde afzenders_|Geen|Geen||
|Geblokkeerde afzenderdomeinen <br/><br/> _Geblokkeerde senderdomeinen_|Geen|Geen||
|**Spammeldingen van eindgebruikers inschakelen** <br/><br/> _EndUserSpammeldingen inschakelen_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Elke (dag) spammeldingen van eindgebruikers verzenden** <br/><br/> _Frequentie van de gebruikerspammelding_|3 dagen|3 dagen||
|**Spam ZAP** <br/><br/> _SpamZapEnabled SpamZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Phish ZAP** <br/><br/> _PhishZapEnabled PhishZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|_MarkasspamBulkMail_|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|

Er zijn verschillende andere Advanced Spam Filter (AsF) instellingen in anti-spam beleid die in het proces van worden afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies zal worden meegedeeld buiten dit onderwerp.

We raden u aan deze ASF-instellingen **uit te** schakelen voor zowel **standaard-** als **strikte** niveaus. Zie Instellingen voor [Geavanceerd spamfilter (Asf) in Office 365](advanced-spam-filtering-asf-options.md)voor meer informatie over asf-instellingen.

|Naam beveiligingsfunctie|Opmerkingen|
|----|---|
|**Afbeeldingskoppelingen naar externe sites** _(IncreaseScoreWithImageLinks)_||
|**Numeriek IP-adres in URL** _(IncreaseScoreWithNumericIps)_||
|**UL omleiden naar andere poort** _(IncreaseScoreWithRedirectToOtherPort)_||
|**URL naar .biz of .info websites** _(IncreaseScoreWithBizOrInfoUrls)_||
|**Lege berichten** _(MarkAsSpamEmptyMessages)_||
|**JavaScript of VBScript in HTML** _(MarkAsSpamJavaScriptInHtml)_||
|**Frame- of IFrame-tags in HTML** _(MarkAsSpamFramesInHtml)_||
|**Objecttags in HTML** _(MarkAsSpamObjectTagsInHtml)_||
|**Tags insluiten in HTML** _(MarkAsSpamEmbedTagsInHtml)_||
|**Formuliertags in HTML** _(MarkAsSpamFormTagsInHtml_)||
|**Webbugs in HTML** _(MarkAsSpamWebBugsInHtml)_||
|**Gevoelige woordenlijst toepassen** (_MarkAsSpamSensitiveWordList_)||
|**SPF record: hard fail** _(MarkAsSpamSpfRecordHardFail)_||
|**Voorwaardelijke sender ID filtering: hard fail** _(MarkAsSpamFromAddressAuthFail)_||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||

#### <a name="eop-outbound-spam-policy-settings"></a>Instellingen voor eOP-uitgaand spambeleid

Zie [Uitgaand spamfiltering configureren in Office 365](configure-the-outbound-spam-policy.md)voor het maken en configureren van uitgaande spambeleid.

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Maximum aantal ontvangers per gebruiker: externe uurlimiet** <br/><br/> _RecipientLimitExternalPerhour_|500|400||
|**Maximum aantal ontvangers per gebruiker: interne uurlimiet** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Maximum aantal ontvangers per gebruiker: dagelijkse limiet** <br/><br/> _RecipientLimitperday_|1000|800||
|**Actie wanneer een gebruiker de limieten overschrijdt** <br/><br/> _ActionWhenThresholdReached_|**De gebruiker beperken om e-mail te verzenden** <br/><br/> `BlockUser`|**De gebruiker beperken om e-mail te verzenden** <br/><br/> `BlockUser`||

### <a name="eop-anti-malware-policy-settings"></a>EOP anti-malware beleidsinstellingen

Zie [Beleid voor antimalware configureren in Office 365](configure-anti-malware-policies.md)als u anti-malwarebeleid wilt maken en configureren.

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Wilt u ontvangers op de hoogte stellen als hun berichten in quarantaine zijn geplaatst?** <br/><br/> _Actie_|Nee <br/><br/> _Bericht verwijderen_|Nee <br/><br/> _Bericht verwijderen_|Als er malware wordt gedetecteerd in een e-mailbijlage, wordt het bericht in quarantaine geplaatst en kan het alleen door een beheerder worden vrijgegeven.|
|**Common Attachment Types Filter** <br/><br/> _Bestandfilter inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van het bestandstype, ongeacht de inhoud van de bijlage.|
|**Malware Zero-hour Auto Purge** <br/><br/> _ZapEnabled ZapEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Interne afzenders op** de hoogte stellen van het niet-afgeleverde bericht <br/><br/> _InternalSenderMeldingen inschakelen_|Handicap <br/><br/> `$false`|Handicap <br/><br/> `$false`||
|**Externe afzenders op** de hoogte stellen van het niet-afgeleverde bericht <br/><br/> _Extern verzondenmeldingen inschakelen_|Handicap <br/><br/> `$false`|Handicap <br/><br/> `$false`||

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standaard anti-phishing beleidsinstellingen

Zie [Antiphishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)om deze instellingen te configureren.

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Anti-spoofing-beveiliging inschakelen** <br/><br/> _AntispoofHandhaving inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _Niet-geverifieerde afzender inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoof intelligence.](learn-about-spoof-intelligence.md)|

## <a name="office-365-advanced-threat-protection-security"></a>Beveiliging van geavanceerde bedreigingsbeveiliging van Office 365

Extra beveiligingsvoordelen worden geleverd met een ATP-abonnement (Office 365 Advanced Threat Protection). Voor het laatste nieuws en informatie u zien [wat er nieuw is in Office 365 ATP.](whats-new-in-office-365-atp.md)

Office 365 ATP bevat het beleid voor veilige bijlagen en veilige koppelingen om te voorkomen dat e-mail met mogelijk schadelijke bijlagen wordt geleverd en om te voorkomen dat gebruikers op mogelijk onveilige URL's klikken.

> [!IMPORTANT]
> Geavanceerde anti-phishing is een van de voordelen van een Office 365 ATP-abonnement. Hoewel het standaard is ingeschakeld, ***moet*** u ten minste één antiphishingbeleid configureren voordat het e-mail kan filteren. Het vergeten om anti-phishing beleid te configureren kan gebruikers blootstellen aan riskante e-mails. Zorg ervoor dat u uw antiphishingbeleid configureert nadat u een Office 365 ATP-abonnement hebt toegevoegd.

Als u een Office 365 ATP-abonnement aan uw EOP hebt toegevoegd, stelt u de volgende configuraties in.

### <a name="office-atp-anti-phishing-policy-settings"></a>Beleidsinstellingen voor office ATP-antiphishing

EOP-klanten krijgen basisantiphishing zoals eerder beschreven, maar Office 365 ATP bevat meer functies en controle om aanvallen te voorkomen, te detecteren en te saneren. Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)als u dit beleid wilt maken en configureren.

|Naam van de functie voor imitatiebeveiliging|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|(Imitatiebeleid bewerken) Gebruikers toevoegen om te beschermen|Aan|Aan|Is afhankelijk van uw organisatie, maar we raden u aan gebruikers toe te voegen in belangrijke rollen. Intern kunnen dit uw CEO, CFO en andere senior leiders zijn. Extern kunnen dit raadsleden of uw raad van bestuur zijn.|
|(Imitatiebeleid bewerken) Voeg automatisch de domeinen toe die ik bezit|Aan|Aan||
|(Imitatiebeleid bewerken) Aangepaste domeinen opnemen|Aan|Aan|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen waarmee u het meest communiceert en waarvan u niet de eigenaar bent.|
|Als e-mail wordt verzonden door een nagebootste gebruiker die u hebt opgegeven|Het bericht in quarantaine plaatsen|Het bericht in quarantaine plaatsen||
|Als e-mail wordt verzonden door een geïmiteerd domein dat u hebt opgegeven|Het bericht in quarantaine plaatsen|Het bericht in quarantaine plaatsen||
|Tip weergeven voor geïmiteerde gebruikers|Aan|Aan||
|Tip weergeven voor nagebootste domeinen|Aan|Aan||
|Tip weergeven voor ongebruikelijke tekens|Aan|Aan||
|Postvakintelligentie inschakelen|Aan|Aan||
|Bescherming op basis van postvakintelligentie inschakelen op basis van imitatie|Aan|Aan||
|Als e-mail wordt verzonden door een nagebootste gebruiker die is beschermd door postvakinformatie|Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden|Het bericht in quarantaine plaatsen||
|(Imitatiebeleid bewerken) Vertrouwde afzenders en domeinen toevoegen|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan gebruikers of domeinen toe te voegen die ten onrechte als phish worden gemarkeerd vanwege alleen imitatie en niet andere filters.|

|Naam van de spoofbeveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Anti-spoofing-beveiliging inschakelen|Aan|Aan||
|Niet-geverifieerde afzender inschakelen (taggen)|Aan|Aan||
|Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen|Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden|Het bericht in quarantaine plaatsen||

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in het ANTI-phishingbeleid van ATP

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|Beveiligde gebruikers: **gebruikers toevoegen om te beschermen** <br/><br/> _TargetedUserProtection inschakelen_ <br/><br/> _TargetedUsersToProtect_|Aan <br/><br/> `$true` <br/><br/> \<lijst met gebruikers\>|Aan <br/><br/> `$true` <br/><br/> \<lijst met gebruikers\>|Is afhankelijk van uw organisatie, maar we raden u aan gebruikers toe te voegen in belangrijke rollen. Intern kunnen dit uw CEO, CFO en andere senior leiders zijn. Extern kunnen dit raadsleden of uw raad van bestuur zijn.|
|Beveiligde domeinen: **voeg automatisch de domeinen toe die ik bezit** <br/><br/> _Bescherming van organisatiedomeinen inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <br/><br/> _Protection inschakelen_ <br/><br/> _TargeteddomainsToProtect_|Aan <br/><br/> `$true` <br/><br/> \<lijst met domeinen\>|Aan <br/><br/> `$true` <br/><br/> \<lijst met domeinen\>|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen waarmee u vaak communiceert en waarvan u niet de eigenaar bent.|
|Beveiligde gebruikers: **als e-mail wordt verzonden door een nagebootste gebruiker** <br/><br/> _TargetedUserProtectionAction_|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`||
|Beveiligde domeinen: **als e-mail wordt verzonden door een nagebootst domein** <br/><br/> _TargetedUserProtectionAction_|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`||
|**Tip weergeven voor geïmiteerde gebruikers** <br/><br/> _Informatieover de veiligheid van vergelijkbare gebruikers inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip weergeven voor nagebootste domeinen** <br/><br/> _Informatieover verschillende domeineninschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip weergeven voor ongebruikelijke tekens** <br/><br/> _Ongebruikelijketekensveiligheidstips inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Postvakinformatie inschakelen?** <br/><br/> _PostvakIne inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Mailbox intelligence based impersonation protection inschakelen?** <br/><br/> _MailboxIntelligenceProtection inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Als e-mail wordt verzonden door een nagebootste gebruiker die is beschermd door postvakinformatie** <br/><br/> _MailboxIntelligenceProtectionAction_|**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`||
|**Vertrouwde afzenders** <br/><br/> _Uitgesloten afzenders_|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan gebruikers toe te voegen die ten onrechte als phish worden gemarkeerd vanwege alleen imitatie en niet andere filters.|
|**Vertrouwde domeinen** <br/><br/> _Uitgesloten domeinen_|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen die ten onrechte als phish worden gemarkeerd vanwege alleen imitatie en niet andere filters.|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Spoofinstellingen in ATP-beleid voor phishing

Houd er rekening mee dat dit dezelfde instellingen zijn die beschikbaar zijn in [de instellingen voor antispambeleid in EOP.](#eop-anti-spam-policy-settings)

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Anti-spoofing-beveiliging inschakelen** <br/><br/> _AntispoofHandhaving inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _Niet-geverifieerde afzender inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Spoofinstellingen in antiphishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoof intelligence.](learn-about-spoof-intelligence.md)|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Geavanceerde instellingen in ATP-antiphishingbeleid

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---|---|---|---|
|**Geavanceerde phishingdrempels** <br/><br/> _PhishThresholdLevel PhishThresholdLevel_|**2 - Agressief** <br/><br/> `2`|**3 - Agressiever** <br/><br/> `3`||

### <a name="safe-links-settings"></a>Instellingen voor veilige koppelingen

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|ATP-veilige koppelingen gebruiken in Office 365-apps, Office voor iOS en Android|Ingeschakeld|Ingeschakeld|Dit valt onder het ATP Safe Links-beleid dat van toepassing is op de hele organisatie|
Niet bijhouden wanneer gebruikers op veilige koppelingen klikken|Handicap|Handicap|Dit is voor zowel beleid dat van toepassing is op de hele organisatie als voor alle beleidsregels die van toepassing zijn op specifieke ontvangers|
|Laat gebruikers niet door veilige links naar de oorspronkelijke URL klikken|Ingeschakeld|Ingeschakeld|Dit is voor zowel het beleid dat van toepassing is op de hele organisatie als voor alle beleidsregels die van toepassing zijn op specifieke ontvangers|
|Actie voor onbekende mogelijk schadelijke URL's in berichten|Aan|Aan||
|Real-time URL scannen toepassen op verdachte links en koppelingen die naar bestanden verwijzen|Ingeschakeld|Ingeschakeld||
|Wachten tot het scannen van url's is voltooid voordat het bericht wordt geleverd|Ingeschakeld|Ingeschakeld||
|Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden|Ingeschakeld|Ingeschakeld||

### <a name="safe-attachments"></a>Veilige bijlagen

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen|Ingeschakeld|Ingeschakeld||
|ATP Safe bijlagen onbekende malware reactie|Blok|Blok||
|Bijlage bij detectie omleiden|Ingeschakeld|Ingeschakeld|Omleiden naar e-mailadres voor een beveiligingsbeheerder die weet hoe te bepalen of de bijlage malware is of niet|
|ATP Safe bijlagen reactie als malware scannen op bijlagen een tijd uit of fout optreedt|Ingeschakeld|Ingeschakeld||

## <a name="related-topics"></a>Verwante onderwerpen

- Bent u op zoek naar best practices met **Exchange Mail Flow / Exchange Transport Rules?** Zie [dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) voor meer informatie.

- Beheerders en gebruikers kunnen valse positieven (goede e-mail gemarkeerd als slecht) en valse negatieven (slechte e-mail toegestaan) naar Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het **instellen van** uw [EOP-service](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)en **configureren van** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Vergeet niet de nuttige aanwijzingen te zien in['Beschermen tegen bedreigingen in Office 365'.)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

- **Beveiligingsbasislijnen voor Windows** zijn [hier](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) te vinden voor GPO/on-premises opties en voor Intune-gebaseerde beveiliging, [hier.](https://docs.microsoft.com/intune/protect/security-baselines) Tot slot is [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)een vergelijking te vinden tussen Microsoft Defender Advanced Threat Protection (ATP) en Windows Intune security baselines.
