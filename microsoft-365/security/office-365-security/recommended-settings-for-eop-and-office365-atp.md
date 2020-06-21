---
title: Microsoft-aanbevelingen voor EOP- en Office 365 ATP-beveiligingsinstellingen, aanbevelingen, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, steps, how does it work, security baselines, baselines for EOP, baselines for ATP, setup ATP, setup EOP, configure ATP, configure EOP, security configuration
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
description: Wat zijn best practices voor Exchange Online Protection (EOP) en Advanced Threat Protection (ATP) beveiligingsinstellingen? Wat zijn de huidige aanbevelingen voor standaardbescherming? Wat moet worden gebruikt als u strenger wilt zijn? En welke extra's krijg je als je ook Advanced Threat Protection (ATP) gebruikt?
ms.openlocfilehash: 15bd63a35b4279efc634115bbdb5248cdd5038db
ms.sourcegitcommit: 589f78fc0f39aff9109959ded48d146cc32fc3c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/16/2020
ms.locfileid: "44761704"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging

**Exchange Online Protection (EOP)** is de kern van beveiliging voor Microsoft 365-abonnementen en helpt voorkomen dat schadelijke e-mails de inboxen van uw werknemer bereiken. Maar met nieuwe, meer geavanceerde aanvallen die elke dag ontstaan, zijn verbeterde beveiligingen vaak vereist. **Atp (Advanced Threat Protection) voor Office 365 (Advanced Threat Protection)** ATP Plan 1 of ATP Plan 2 bevat extra functies die beheerders meer lagen beveiliging, controle en onderzoek geven.

Hoewel we beveiligingsbeheerders in staat stellen hun beveiligingsinstellingen aan te passen, zijn er twee beveiligingsniveaus in EOP en Office 365 ATP die we aanbevelen: **Standaard** en **Strikt**. De omgeving en behoeften van elke klant zijn verschillend, maar we zijn van mening dat deze niveaus van configuraties voor het filteren van e-mail zullen helpen voorkomen dat ongewenste e-mail in de meeste situaties de inbox van uw werknemers bereikt.

> [!IMPORTANT]
> De regel voor ongewenste e-mail moet worden ingeschakeld in een postvak om te kunnen filteren. Het is standaard ingeschakeld, maar u moet controleren of filteren niet lijkt te werken. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit onderwerp worden de door Microsoft aanbevolen instellingen beschreven om uw gebruikers te beschermen.

> [!TIP]
> Er is een nieuwe PowerShell-module die u downloaden, de Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA), waarmee u een aantal van deze instellingen bepalen. Wanneer get-ORCAReport wordt uitgevoerd als beheerder in uw tenant, helpt u bij het genereren van een beoordeling van de instellingen voor antispam, anti-phish en andere instellingen voor berichthygiëne. U deze module downloaden op https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware en anti-phishing bescherming in EOP

Anti-spam, anti-malware en anti-phishing zijn functies van EOP die door beheerders kunnen worden geconfigureerd. We raden de volgende configuraties aan.

### <a name="eop-anti-spam-policy-settings"></a>Instellingen voor eOP-antispambeleid

Zie [Antispambeleid configureren in Office 365 als](configure-your-spam-filter-policies.md)u antispambeleid wilt maken en configureren.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|Actie voor **spamdetectie** <br/><br/> _SpamAction SpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantainebericht** <br/><br/> `Quarantine`||
|**Hoog vertrouwen spam** detectie actie <br/><br/> _HighConfidenceSpamAction_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|**Phishing-e-maildetectieactie** <br/><br/> _PhishSpamAction_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|**Hoog vertrouwen phishing e-mail** detectie actie <br/><br/> _HighConfidencePhishAction_|**Quarantainebericht** <br/><br/> `Quarantine`|**Quarantainebericht** <br/><br/> `Quarantine`||
|Actie voor detectie van **bulke-mail** <br/><br/> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantainebericht** <br/><br/> `Quarantine`||
|Drempelwaarde voor bulke-mail <br/><br/> _BulkThreshold BulkThreshold_|6|4|De standaardwaarde is momenteel 7, maar we raden u aan deze te wijzigen in 6. Zie [Bulkklachtenniveau (BCL) in Office 365](bulk-complaint-level-values.md)voor meer informatie.|
|Quarantaineretentieperiode <br/><br/> _QuarantaineRetentionPeriod_|30 dagen|30 dagen||
|**Veiligheidstips** <br/><br/> _InlineSafetyTipsEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Toegestane afzenders <br/><br/> _ToegestaneSenders_|Geen|Geen||
|Toegestane afzenderdomeinen <br/><br/> _AllowedSenderDomains_|Geen|Geen|Het toevoegen van domeinen die u bezit (ook wel _geaccepteerde domeinen_genoemd) aan de lijst met toegestane afzenders is niet vereist. In feite wordt het beschouwd als een hoog risico, omdat het kansen creëert voor slechte acteurs om u e-mail te sturen die anders zou worden uitgefilterd. Gebruik [spoofinformatie](learn-about-spoof-intelligence.md) in het Security & Compliance Center op de pagina **Antispam-instellingen** om alle afzenders te controleren die e-mailadressen van afzenders spoofen in de e-maildomeinen van uw organisatie of e-mailadressen van afzenders in externe domeinen spoofen.|
|Geblokkeerde afzenders <br/><br/> _Geblokkeerdesverders_|Geen|Geen||
|Geblokkeerde afzenderdomeinen <br/><br/> _GeblokkeerdeSenderDomeinen_|Geen|Geen||
|**Spammeldingen voor eindgebruikers inschakelen** <br/><br/> _Meldingen inschakelen_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Stuur spammeldingen van eindgebruikers elke (dagen)** <br/><br/> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen||
|**Spam ZAP** <br/><br/> _SpamZapEnabled SpamZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Phish ZAP** <br/><br/> _PhishZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|_MarkAsSpamBulkMail MarkAsSpamBulkMail_|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|
|

Er zijn verschillende andere Geavanceerde Spam Filter (AsF) instellingen in anti-spam beleid die in het proces van wordt afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies zal worden gecommuniceerd buiten dit onderwerp.

We raden u aan deze AS-instellingen **uit te** schakelen voor zowel **standaard-** als **strikte** niveaus. Zie AZG-instellingen [(Advanced Spam Filter) in Office 365 voor](advanced-spam-filtering-asf-options.md)meer informatie over AVO-instellingen.

|||
|---|---|
|**Naam beveiligingsfunctie**|**Opmerking**|
|**Afbeeldingskoppelingen naar externe sites** _(IncreaseScoreWithImageLinks_)||
|**Numeriek IP-adres in URL** _(IncreaseScoreWithNumericIps_)||
|**UL omleiden naar andere poort** _(IncreaseScoreWithRedirectToOtherPort_)||
|**URL naar .biz of .info websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Lege berichten** _(MarkAsSpamEmptyMessages_)||
|**JavaScript of VBScript in HTML** _(MarkAsSpamJavaScriptInHtml_)||
|**Frame- of IFrame-tags in HTML** _(MarkAsSpamFramesInHtml_)||
|**Objecttags in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Insluiten tags in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formuliertags in HTML** _(MarkAsSpamFormTagsInHtml_)||
|**Webbugs in HTML** _(MarkAsSpamWebBugsInHtml_)||
|**Gevoelige woordenlijst toepassen** _(MarkAsSpamSensitiveWordList_)||
|**SPF record: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Voorwaardelijke afzender-ID-filtering: harde fail** _(MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Instellingen voor uitgaande spambeleid van EOP

Zie Uitgaande [spamfiltering configureren in Office 365 als](configure-the-outbound-spam-policy.md)u uitgaand spambeleid wilt maken en configureren.

Zie [Verzendlimieten voor](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1) meer informatie over de standaard verzendlimieten in de service

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Maximaal aantal ontvangers per gebruiker: externe uurlimiet** <br/><br/> _OntvangerLimitExternalPerHour_|500|400||
|**Maximaal aantal ontvangers per gebruiker: interne uurlimiet** <br/><br/> _OntvangerLimitInternalPerHour_|1000|800||
|**Maximaal aantal ontvangers per gebruiker: Dagelijkse limiet** <br/><br/> _OntvangerLimitPerDay_|1000|800||
|**Actie wanneer een gebruiker de limieten overschrijdt** <br/><br/> _ActionWhenThresholdReached_|**De gebruiker beperken tot het verzenden van e-mail** <br/><br/> `BlockUser`|**De gebruiker beperken tot het verzenden van e-mail** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Beleidsinstellingen voor EOP-anti-malware

Zie [Anti-malwarebeleid configureren in Office 365](configure-anti-malware-policies.md)als u antimalwarebeleid wilt maken en configureren.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Wilt u ontvangers op de hoogte stellen als hun berichten in quarantaine zijn geplaatst?** <br/><br/> _Actie_|Nee <br/><br/> _Berichten verwijderen_|Nee <br/><br/> _Berichten verwijderen_|Als malware wordt gedetecteerd in een e-mailbijlage, wordt het bericht in quarantaine geplaatst en kan het alleen door een beheerder worden vrijgegeven.|
|**Filter Algemene bijlagetypen** <br/><br/> _Bestand inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van bestandstype, ongeacht de bijlage-inhoud.|
|**Malware Zero-hour Auto Purge** <br/><br/> _ZapEnabled ZapEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Interne afzenders op** de hoogte stellen van het niet-geleverde bericht <br/><br/> _Meldingen inschakelen_|Uitgeschakeld <br/><br/> `$false`|Uitgeschakeld <br/><br/> `$false`||
|**Externe afzenders op** de hoogte stellen van het niet-geleverde bericht <br/><br/> _EnableExternalSenderNotifications_|Uitgeschakeld <br/><br/> `$false`|Uitgeschakeld <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standaard anti-phishing beleidsinstellingen

Zie [Spoofinstellingen](set-up-anti-phishing-policies.md#spoof-settings)voor meer informatie over deze instellingen. Zie [Anti-phishingbeleid configureren in EOP om](configure-anti-phishing-policies-eop.md)deze instellingen te configureren.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Bescherming tegen spoofing inschakelen** <br/><br/> _EnableAntispoofEnforcement_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _EnableunauthenticatedSender_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Quarantaine het bericht** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoofintelligentie.](learn-about-spoof-intelligence.md)|
|

## <a name="office-365-advanced-threat-protection-security"></a>Beveiliging van geavanceerde bedreigingsbeveiliging van Office 365

Extra beveiligingsvoordelen worden geleverd met een ATP-abonnement (Advanced Threat Protection) van Office 365. Voor het laatste nieuws en informatie u zien [wat er nieuw is in Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP bevat het beleid voor veilige bijlagen en veilige koppelingen om te voorkomen dat e-mail met mogelijk schadelijke bijlagen wordt geleverd en om te voorkomen dat gebruikers op mogelijk onveilige URL's klikken.

> [!IMPORTANT]
> Geavanceerde antiphishing is een van de voordelen van een Office 365 ATP-abonnement. Hoewel het standaard is ingeschakeld, ***moet*** u ten minste één antiphishingbeleid configureren voordat het e-mail kan filteren. Het vergeten om anti-phishing beleid te configureren kan gebruikers blootstellen aan riskante e-mails. Zorg ervoor dat u uw antiphishingbeleid configureert nadat u een Office 365 ATP-abonnement hebt toegevoegd.

Als u een AtP-abonnement voor Office 365 aan uw EOP hebt toegevoegd, stelt u de volgende configuraties in.

### <a name="office-atp-anti-phishing-policy-settings"></a>Office ATP-beleidsinstellingen voor phishing

EOP-klanten krijgen basisantiphishing zoals eerder beschreven, maar Office 365 ATP bevat meer functies en controle om aanvallen te voorkomen, op te sporen en te herstellen. Zie [ATP-antiphishingbeleid configureren in Office 365](configure-atp-anti-phishing-policies.md)als u dit beleid wilt maken en configureren.

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in atp-anti-phishingbeleid

Zie [Imitatie-instellingen in het ATP-antiphishingbeleid voor](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)meer informatie over deze instellingen. Zie [ATP-antiphishingbeleid configureren](configure-atp-anti-phishing-policies.md)als u deze instellingen wilt configureren.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|Beveiligde gebruikers: **gebruikers toevoegen om te beschermen** <br/><br/> _Beveiliging van doelgericht gebruikers_ <br/><br/> _TargetedUsersToProtect_|Aan <br/><br/> `$true` <br/><br/> \<list of users\>|Aan <br/><br/> `$true` <br/><br/> \<list of users\>|Afhankelijk van uw organisatie, maar we raden u aan gebruikers in belangrijke rollen toe te voegen. Intern kunnen dit uw CEO, CFO en andere senior leiders zijn. Extern kunnen dit ook raadsleden of uw raad van bestuur zijn.|
|Beveiligde domeinen: **voeg automatisch de domeinen op die ik bezit** <br/><br/> _Bescherming van organisatiedomeinen inschakelen_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <br/><br/> _Beveiliging inschakelen_ <br/><br/> _TargetedDomainsToProtect_|Aan <br/><br/> `$true` <br/><br/> \<list of domains\>|Aan <br/><br/> `$true` <br/><br/> \<list of domains\>|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen waarmee u vaak communiceert die u niet bezit.|
|Beveiligde gebruikers: **als e-mail wordt verzonden door een geïmiteerde gebruiker** <br/><br/> _TargetedUserProtectionAction_|**Quarantaine het bericht** <br/><br/> `Quarantine`|**Quarantaine het bericht** <br/><br/> `Quarantine`||
|Beveiligde domeinen: **als e-mail wordt verzonden door een geïmcipeel domein** <br/><br/> _TargetedUserProtectionAction_|**Quarantaine het bericht** <br/><br/> `Quarantine`|**Quarantaine het bericht** <br/><br/> `Quarantine`||
|**Tip weergeven voor geïmiteerde gebruikers** <br/><br/> _EnableSimilarUsersSafetyTips_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip weergeven voor geïmiteerde domeinen** <br/><br/> _Schakelen Op dezelfde manier_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip weergeven voor ongebruikelijke tekens** <br/><br/> _EnableUnusualCharactersSafetyTips_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Postvakinformatie inschakelen?** <br/><br/> _EnableMailboxIntelligence_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Postvakintelligentie inschakelen op basis van imitatiebeveiliging?** <br/><br/> _Beveiliging van EnableMailboxIntelligenceProtection_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Als e-mail wordt verzonden door een geïmiteerde gebruiker die wordt beschermd door postvakinformatie** <br/><br/> _MailboxIntelligenceProtectionAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Quarantaine het bericht** <br/><br/> `Quarantine`||
|**Vertrouwde afzenders** <br/><br/> _Exclusief-verderingen_|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan gebruikers toe te voegen die ten onrechte worden gemarkeerd als phish vanwege imitatie en niet andere filters.|
|**Vertrouwde domeinen** <br/><br/> _Uitgeslotendomeinen_|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen die ten onrechte worden gemarkeerd als phish vanwege imitatie en niet andere filters.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Spoofinstellingen in atp-antiphishingbeleid

Houd er rekening mee dat dit dezelfde instellingen zijn die beschikbaar zijn in [antispambeleidsinstellingen in EOP.](#eop-anti-spam-policy-settings)

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Bescherming tegen spoofing inschakelen** <br/><br/> _EnableAntispoofEnforcement_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _EnableunauthenticatedSender_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Spoofinstellingen in het antiphishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <br/><br/> `MoveToJmf`|**Quarantaine het bericht** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoofintelligentie.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Geavanceerde instellingen in atp-anti-phishingbeleid

Zie [Geavanceerde phishingdrempels in het ATP-antiphishingbeleid](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)voor meer informatie over deze instelling. Zie [ATP-antiphishingbeleid configureren](configure-atp-anti-phishing-policies.md)als u deze instelling wilt configureren.

|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|---|---|---|---|
|**Geavanceerde phishingdrempels** <br/><br/> _PhishThresholdLevel_|**2 - Agressief** <br/><br/> `2`|**3 - Agressiever** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>Beleidsinstellingen voor VEILIGE koppelingen ATP

Zie [Office 365 ATP-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md)instellen als u deze instellingen wilt configureren.

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>Beleidsinstellingen voor veilige koppelingen in het standaardbeleid voor alle gebruikers

**Opmerking**: In PowerShell gebruikt u de cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Veilige koppelingen gebruiken in: Office 365-toepassingen** <br/><br/> _EnableSafeLinksForO365Clients_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Gebruik ATP Safe Links in Office 365 Apps, Office voor iOS en Android.|
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <br/><br/> _TrackClicks_|Uit <br/><br/> `$true`|Uit <br/><br/> `$true`||
|**Laat gebruikers niet doorklikken naar veilige links naar de oorspronkelijke URL** <br/><br/> _Klikdoor_|Aan <br/><br/> `$false`|Aan <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>Beleidsinstellingen voor veilige koppelingen in aangepast beleid voor specifieke gebruikers

**Opmerking**: In PowerShell gebruikt u voor deze instellingen het [Beleid nieuw-SafeLinksBeleid](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) en [Set-SafeLinksPolicy]. https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicycmdlet

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Selecteer de actie voor onbekende mogelijk schadelijke URL's in berichten** <br/><br/> _Isenabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Selecteer de actie voor onbekende of mogelijk schadelijke URL's binnen Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Real-time URL-scannen toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** <br/><br/> _Scanurls_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Wacht tot het scannen van url's is voltooid voordat u het bericht aflevert** <br/><br/> _DeliverMessageAfterScan_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden** <br/><br/> _EnableForInternalSenders_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <br/><br/> _DoNotTrackUserClicks_|Uit <br/><br/> `$false`|Uit <br/><br/> `$false`|
|**Laat gebruikers niet doorklikken naar veilige links naar de oorspronkelijke URL** <br/><br/> _DoNotAllowClickThrough_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>Beleidsinstellingen voor ATP-veilige bijlagen

Zie Beleid voor [veilige bijlagen van Office 365 ATP instellen](set-up-atp-safe-attachments-policies.md)als u deze instellingen wilt configureren.

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>Beleidsinstellingen voor veilige bijlagen in het standaardbeleid voor alle gebruikers

**Opmerking**: In PowerShell gebruikt u de cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen** <br/><br/> _EnableATPForSPOTeamsODB_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Veilige documenten voor Office-clients inschakelen**<bt/><br/> _EnableSafeDocs_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||Deze instelling is alleen beschikbaar met Microsoft 365 E5- of Microsoft 365 E5-beveiligingslicenties. Zie [Veilige documenten in Geavanceerde bedreigingsbeveiliging van Office 365](safe-docs.md)voor meer informatie.|
|**Mensen toestaan om door beveiligde weergave te klikken, zelfs als Safe Documents het bestand als kwaadaardig heeft geïdentificeerd**<bt/><br/> _AllowSafeDocsOpen_|Uit <br/><br/> `$false`|Uit <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>Beleidsinstellingen voor veilige bijlagen in aangepast beleid voor specifieke gebruikers

**Opmerking**: In PowerShell gebruikt u voor deze instellingen de cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) en [Set-SafeAttachmentPolicy.](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)

|||||
|---|---|---|---|
|**Naam beveiligingsfunctie**|**Standaard**|**Strikte**|**Opmerking**|
|**Veilige bijlagen onbekende malware reactie** <br/><br/> _Actie_|Blok <br/><br/> `Block`|Blok <br/><br/> `Block`||
|**Bijlage omleiden bij detectie** : **Omleiding inschakelen** <br/><br/> _Omleiden_ <br/><br/> _Omleidadres_|Een e-mailadres aan en geef op. <br/><br/> `$true` <br/><br/> een e-mailadres|Een e-mailadres aan en geef op. <br/><br/> `$true` <br/><br/> een e-mailadres|Stuur berichten om naar een beveiligingsbeheerder voor controle.|
|**Pas de bovenstaande selectie toe als er een keer een keer een fout optreedt bij het scannen van malware voor bijlagen.** <br/><br/> _ActionOnError_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|

## <a name="related-topics"></a>Verwante onderwerpen

- Bent u op zoek naar best practices met **Exchange Mail Flow / Exchange Transport Rules?** Zie [dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) voor meer informatie.

- Beheerders en gebruikers kunnen valse positieven (goede e-mail gemarkeerd als slecht) en valse negatieven (slechte e-mail toegestaan) naar Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het **instellen van** uw [EOP-service](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)en **het configureren van** [Geavanceerde bedreigingsbeveiliging van Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Vergeet niet om de nuttige aanwijzingen te zien in '[Protect Against Threats in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.)

- **Beveiligingsbasislijnen voor Windows** zijn [hier](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) te vinden voor GPO/on-premises opties en voor intune-gebaseerde [beveiliging, hier.](https://docs.microsoft.com/intune/protect/security-baselines) Tot slot, een vergelijking tussen Microsoft Defender Advanced Threat Protection (ATP) en Windows Intune security baselines kan [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)worden gevonden.
