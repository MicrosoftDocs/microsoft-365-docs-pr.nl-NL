---
title: Microsoft aanbevelingen voor EOP en Office 365 vooraf ingestelde beveiligingsinstellingen, aanbevelingen, Framework voor beleidsregels, berichten rapporteren en conformeel, door DomainKeys geïdentificeerde E-mail, stappen, hoe werkt het met de basislijnen voor het werken, het instellen van basislijnen voor het werken met basistaken
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
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
description: Wat zijn de aanbevolen procedures voor beveiligingsinstellingen van Exchange Online Protection (EOP) en Advanced Threat Protection (ATP)? Wat is de huidige aanbevelingen voor standaardbeveiliging? Wat moet worden gebruikt als u striktere informatie wilt? En welke extra's ontvangt u als u ook Advanced Threat Protection (ATP) gebruikt?
ms.openlocfilehash: 78dc1673d20affdfab9228883dbce3b08e8efbb5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202709"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Aanbevolen instellingen voor EOP en Office 365 ATP-beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


**Exchange Online Protection (EOP)** is de kern van beveiliging voor microsoft 365-abonnementen en helpt voorkomen dat ongewenste e-mailberichten in de Postvak in van uw werknemers terechtkomen. Maar met nieuwe, nieuwe, nog geavanceerdere aanvallen die elke dag zijn verbeterd, zijn er vaak betere bescherming nodig. **Office 365 Advanced Threat Protection (ATP)** ATP abonnement 1 of ATP abonnement 2 bevat extra functies die beheerders meer lagen bieden voor beveiliging, controle en onderzoek.

Hoewel we beveiligingsbeheerders kunnen helpen bij het aanpassen van hun beveiligingsinstellingen, zijn er twee beveiligingsniveaus in EOP en Office 365 ATP voor het eerst bedoeld: **Standard** en **strict**. De omgeving en behoefte van elke klant zijn verschillend, maar we geloven dat deze niveaus van de configuraties voor e-mail filteren helpen voorkomen dat ongewenste e-mail in de meeste gevallen het postvak in van uw werknemers ontvangt.

Als u de standaard-of strikte instellingen automatisch wilt toepassen op gebruikers, raadpleegt u [vooraf ingesteld beveiligingsbeleid in EOP en Office 365 ATP](preset-security-policies.md).

> [!IMPORTANT]
> De regel voor ongewenste e-mail moet worden ingeschakeld voor een postvak om de juiste werking van filteren te kunnen filteren. Het is standaard ingeschakeld, maar u moet controleren of het filteren niet lijkt te werken. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit onderwerp worden deze door Microsoft aanbevolen instellingen beschreven om uw gebruikers te helpen beschermen.

> [!TIP]
> Er is een nieuwe PowerShell-module die u kunt downloaden, genaamd Office 365 Advanced Threat Protection recommended configuration Analyzer (ORCA), waarmee u enkele van deze instellingen kunt bepalen. Als u een beheerder van de Tenant uitvoert, kunt u met Get-ORCAReport een beoordeling maken van de antispam, anti phishing en andere instellingen voor bericht hygiëne. U kunt deze module downloaden op https://www.powershellgallery.com/packages/ORCA/ .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam, anti malware en bescherming tegen phishing in EOP

Antispam, anti-malware en anti phishing zijn functies van EOP die kunnen worden geconfigureerd door beheerders. We raden u aan de volgende configuraties te volgen.

### <a name="eop-anti-spam-policy-settings"></a>EOP antispam beleidsinstellingen

Zie [Antispambeleid in Office 365 configureren](configure-your-spam-filter-policies.md)om Antispambeleid te maken en te configureren.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Spam** detectie actie <br/><br/> _SpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantaine bericht** <br/><br/> `Quarantine`||
|**Hoge betrouwbaarheid van spam** detectie actie <br/><br/> _HighConfidenceSpamAction_|**Quarantaine bericht** <br/><br/> `Quarantine`|**Quarantaine bericht** <br/><br/> `Quarantine`||
|Detectie actie **malafide e-mailadres** <br/><br/> _PhishSpamAction_|**Quarantaine bericht** <br/><br/> `Quarantine`|**Quarantaine bericht** <br/><br/> `Quarantine`||
|Detectie van **phishing-e-mail voor hoog vertrouwen** <br/><br/> _HighConfidencePhishAction_|**Quarantaine bericht** <br/><br/> `Quarantine`|**Quarantaine bericht** <br/><br/> `Quarantine`||
|Actie **bulksgewijs e-mail** detectie <br/><br/> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <br/><br/> `MoveToJmf`|**Quarantaine bericht** <br/><br/> `Quarantine`||
|Drempelwaarde voor bulk mail <br/><br/> _BulkThreshold_|zes|3|De standaardwaarde is momenteel 7, maar we raden u aan om dit te wijzigen in 6. Zie [bulk klachten niveau (BCL) in Office 365](bulk-complaint-level-values.md)voor meer informatie.|
|Bewaarperiode voor quarantaine <br/><br/> _QuarantineRetentionPeriod_|30 dagen|30 dagen||
|**Veiligheids tips** <br/><br/> _InlineSafetyTipsEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Toegestane afzenders <br/><br/> _AllowedSenders_|Geen|Geen||
|Toegestaan domein van afzender <br/><br/> _AllowedSenderDomains_|Geen|Geen|Het toevoegen van domeinen waarvan u de eigenaar bent (ook wel _geaccepteerde domeinen_genoemd) aan de lijst met toegestane afzenders is niet vereist. Eigenlijk wordt het beschouwd als hoog risico, omdat er verkoopkansen worden gemaakt voor beschadigde actoren om u e-mailberichten te sturen die anders worden gefilterd. Gebruik [spoof Intelligence](learn-about-spoof-intelligence.md) in het beveiligings & compliance op de pagina **anti spam instellingen** om alle afzenders te bekijken die e-mailadressen van de afzender in de e-mail domeinen van uw organisatie of e-mailadressen van de afzender in de e-mail domeinen van uw organisatie spoofen.|
|Geblokkeerde afzenders <br/><br/> _BlockedSenders_|Geen|Geen||
|Geblokkeerde afzender domeinen <br/><br/> _BlockedSenderDomains_|Geen|Geen||
|**Spam meldingen voor eindgebruikers inschakelen** <br/><br/> _EnableEndUserSpamNotifications_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Spam meldingen voor eindgebruikers elke (dagen) verzenden** <br/><br/> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen||
|**Spam ZAP** <br/><br/> _SpamZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|**Phishing ZAP** <br/><br/> _PhishZapEnabled_|Ingeschakeld <br/><br/> `$true`|Ingeschakeld <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|
|

Er zijn verschillende andere instellingen voor Advanced Spam filters (ASF) in anti spam beleid dat wordt afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies wordt buiten dit onderwerp meegedeeld.

U wordt aangeraden deze ASF-instellingen voor **standaard** -en **strikte** niveaus **uit** te schakelen. Zie voor meer informatie over ASF-instellingen de [instellingen voor Geavanceerd spam filter (ASF) in Office 365](advanced-spam-filtering-asf-options.md).

****

|Naam van beveiligingsfunctie|Opmerking|
|---|---|
|**Afbeeldingskoppelingen naar externe sites** (_IncreaseScoreWithImageLinks_)||
|Het **numerieke IP-adres in URL** (_IncreaseScoreWithNumericIps_)||
|**Ul redirect to other Port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL naar. info-of. info-websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Lege berichten** (_MarkAsSpamEmptyMessages_)||
|**JavaScript of VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Tags van het kader of IFRAME in HTML** (_MarkAsSpamFramesInHtml_)||
|**Object-Tags in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Tags insluiten in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulier Tags in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Web bugs in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Gevoelige woordenlijst toepassen** (_MarkAsSpamSensitiveWordList_)||
|**SPF-record: vast failed** (_MarkAsSpamSpfRecordHardFail_)||
|**Filteren van voorwaardelijke Sender-ID: harde fout** (_MarkAsSpamFromAddressAuthFail_)||
|**Ndr's Backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP uitgaande spam beleidsinstellingen

Als u een uitgaand spam beleid wilt maken en configureren, raadpleegt u [uitgaande spam filteren in Office 365](configure-the-outbound-spam-policy.md).

Zie [limieten verzenden](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1) voor meer informatie over de standaard verzendings limieten in de service.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Maximum aantal geadresseerden per gebruiker: extern uur limiet** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Maximaal aantal geadresseerden per gebruiker: intern uur limiet** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Maximum aantal geadresseerden per gebruiker: dagelijkse limiet** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Actie wanneer een gebruiker de limieten overschrijdt** <br/><br/> _ActionWhenThresholdReached_|**Verhinderen dat gebruikers e-mail verzenden** <br/><br/> `BlockUser`|**Verhinderen dat gebruikers e-mail verzenden** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP anti malware-beleidsinstellingen

Zie [anti malware-beleidsregels in Office 365 configureren](configure-anti-malware-policies.md)om anti-malwarebeleid te maken en te configureren.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Wilt u geadresseerden informeren wanneer hun berichten in quarantaine worden geplaatst?** <br/><br/> _Actierij_|Nee <br/><br/> _DeleteMessage_|Nee <br/><br/> _DeleteMessage_|Als er malware in een e-mailbijlage is gedetecteerd, wordt het bericht in quarantaine geplaatst en kan het alleen door een beheerder worden vrijgegeven.|
|**Algemene bijlage typen filter** <br/><br/> _EnableFileFilter_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van bestandstypen, ongeacht de inhoud van de bijlage.|
|**Malware 0-uur automatisch wissen** <br/><br/> _ZapEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Interne afzenders** van het niet-bezorgde bericht informeren <br/><br/> _EnableInternalSenderNotifications_|Uitgeschakeld <br/><br/> `$false`|Uitgeschakeld <br/><br/> `$false`||
|**Externe afzenders** van het niet-bezorgde bericht informeren <br/><br/> _EnableExternalSenderNotifications_|Uitgeschakeld <br/><br/> `$false`|Uitgeschakeld <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standaard anti phishingfilter-beleidsinstellingen

Zie [spoof Settings (spoof Settings](set-up-anti-phishing-policies.md#spoof-settings)) voor meer informatie over deze instellingen. Zie [anti phishingfilter in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van deze instellingen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Anti spoofing-beveiliging inschakelen** <br/><br/> _EnableAntispoofEnforcement_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _EnableUnauthenticatedSender_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Voegt een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-aangewezen vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md).|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <br/><br/> `MoveToJmf`|**Het bericht Quarantine** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoof Intelligence](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Beveiliging van Office 365 Advanced Threat Protection

Extra beveiligingsvoordelen worden geleverd met een abonnement op Office 365 Advanced Threat Protection (ATP). Voor het laatste nieuws en informatie kunt u zien [wat er nieuw is in Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP bevat de beleidsregels voor veilige bijlagen en veilige koppelingen om e-mail met mogelijk schadelijke bijlagen te voorkomen, en om te voorkomen dat gebruikers op mogelijk onveilige Url's klikken.

> [!IMPORTANT]
> Geavanceerde anti-phishing is een van de voordelen van een ATP-abonnement van Office 365. Het standaard ATP anti phishingfilter biedt de bescherming van de [spoofing](set-up-anti-phishing-policies.md#spoof-settings) voor alle geadresseerden. De beschikbare instellingen voor [imitatie beveiliging](#impersonation-settings-in-atp-anti-phishing-policies) van bepaalde afzenders of het verzenden van domeinen worden echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u de bescherming van de bescherming van de bescherming wilt inschakelen, moet u minimaal één anti-phishings beleid configureren.

Als u een Office 365 ATP-abonnement hebt toegevoegd aan uw EOP, moet u de volgende configuraties instellen.

### <a name="office-atp-anti-phishing-policy-settings"></a>Instellingen voor Phishingfilter van Office ATP

EOP-klanten hebben een eenvoudige anti-phishing zoals eerder beschreven, maar Office 365 ATP bevat meer functies en controle voor het voorkomen, detecteren en herstellen tegen aanvallen. Als u deze beleidsregels wilt maken en configureren, raadpleegt u [het artikel ATP anti-phishing configureren in Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Imitatie-instellingen in ATP anti-phishingfilter

Zie voor meer informatie over deze instellingen de [instelling in een anti-phishingfilter-beleidsregels voor imitatie](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Als u deze instellingen wilt configureren, raadpleegt u [het artikel ATP anti-phishingfilter configureren](configure-atp-anti-phishing-policies.md).

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|Beveiligde gebruikers: **gebruikers toevoegen om te beschermen** <br/><br/> _EnableTargetedUserProtection_ <br/><br/> _TargetedUsersToProtect_|Aan <br/><br/> `$true` <br/><br/> \<list of users\>|Aan <br/><br/> `$true` <br/><br/> \<list of users\>|Afhankelijk van uw organisatie, wordt u aangeraden gebruikers toe te voegen in belangrijke rollen. Intern zijn dit mogelijk de directeur, CFO en andere leidinggevenden. Extern kunnen dit deelnemen aan de leden van de Raad of van het bord van directeur.|
|Beveiligde domeinen: **automatisch de domeinen opnemen waarvan ik eigenaar ben** <br/><br/> _EnableOrganizationDomainsProtection_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Aan <br/><br/> `$true` <br/><br/> \<list of domains\>|Aan <br/><br/> `$true` <br/><br/> \<list of domains\>|Afhankelijk van uw organisatie, kunt u het beste domeinen toevoegen waarmee u regelmatig communiceert.|
|Beveiligde gebruikers: **als e-mail wordt verzonden door een geïmiteerde gebruiker** <br/><br/> _TargetedUserProtectionAction_|**Het bericht Quarantine** <br/><br/> `Quarantine`|**Het bericht Quarantine** <br/><br/> `Quarantine`||
|Beveiligde domeinen: **als e-mail wordt verzonden door een geïmiteerd domein** <br/><br/> _TargetedDomainProtectionAction_|**Het bericht Quarantine** <br/><br/> `Quarantine`|**Het bericht Quarantine** <br/><br/> `Quarantine`||
|**Tip weergeven voor geïmiteerde gebruikers** <br/><br/> _EnableSimilarUsersSafetyTips_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip weergeven voor geïmiteerde domeinen** <br/><br/> _EnableSimilarDomainsSafetyTips_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Tip voor ongebruikelijk tekens weergeven** <br/><br/> _EnableUnusualCharactersSafetyTips_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Postvak intelligentie inschakelen?** <br/><br/> _EnableMailboxIntelligence_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Schakelt u de bescherming van imitatie op basis van een postvak in?** <br/><br/> _EnableMailboxIntelligenceProtection_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**E-mail wordt verzonden door een geïmiteerde gebruiker die is beveiligd via een postvak intelligentie** <br/><br/> _MailboxIntelligenceProtectionAction_|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <br/><br/> `MoveToJmf`|**Het bericht Quarantine** <br/><br/> `Quarantine`||
|**Vertrouwde afzenders** <br/><br/> _ExcludedSenders_|Geen|Geen|Is afhankelijk van uw organisatie, maar u wordt aangeraden gebruikers toe te voegen die niet meer als phishing zijn gemarkeerd als gevolg van imitatie en geen andere filters.|
|**Vertrouwde domeinen** <br/><br/> _ExcludedDomains_|Geen|Geen|Afhankelijk van uw organisatie, wordt u aangeraden domeinnamen toe te voegen die niet meer als phishing zijn gemarkeerd als gevolg van imitatie en geen andere filters.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Vervalsings instellingen in ATP anti-phishings beleid

Dit zijn de instellingen die beschikbaar zijn in de instellingen voor [Antispambeleid in EOP](#eop-anti-spam-policy-settings).

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Anti spoofing-beveiliging inschakelen** <br/><br/> _EnableAntispoofEnforcement_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet-geverifieerde afzender inschakelen** <br/><br/> _EnableUnauthenticatedSender_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Voegt een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-aangewezen vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md).|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <br/><br/> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <br/><br/> `MoveToJmf`|**Het bericht Quarantine** <br/><br/> `Quarantine`|Dit geldt voor geblokkeerde afzenders in [spoof Intelligence](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Geavanceerde instellingen in ATP anti-phishings beleid

Zie voor meer informatie over deze instelling [Geavanceerde phishingberichten in het anti-phishingfilter-beleid](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Zie beleid voor de [anti-phishing van ATP configureren](configure-atp-anti-phishing-policies.md)voor informatie over het configureren van deze instelling.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Geavanceerde phishingberichten** <br/><br/> _PhishThresholdLevel_|**2-agressief** <br/><br/> `2`|**3-meer agressief** <br/><br/> `3`||

### <a name="atp-safe-links-policy-settings"></a>Beleidsinstellingen voor veilige koppelingen met ATP

Zie [beleidsregels voor veilige koppelingen van Office 365 instellen](set-up-atp-safe-links-policies.md)voor het configureren van deze instellingen.

#### <a name="safe-links-policy-settings-in-the-default-policy-for-all-users"></a>Beleidsinstellingen voor veilige koppelingen in het standaardbeleid voor alle gebruikers

**Opmerking**: in PowerShell gebruikt u de cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Veilige koppelingen gebruiken in: Office 365-toepassingen** <br/><br/> _EnableSafeLinksForO365Clients_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Gebruik op de PC-en Mobile-clients van Office 365 Office.|
|**Veilige koppelingen gebruiken in: Office Web Access-assistenten** <br/><br/> _EnableSafeLinksForWebAccessCompanion_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`|Gebruik in Office Web apps de veilige ATP-koppelingen. Let op: deze instelling kan niet worden geconfigureerd.|
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <br/><br/> _TrackClicks_|Uit <br/><br/> `$true`|Uit <br/><br/> `$true`||
|**Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL** <br/><br/> _AllowClickThrough_|Aan <br/><br/> `$false`|Aan <br/><br/> `$false`||
|

#### <a name="safe-links-policy-settings-in-custom-policies-for-specific-users"></a>Beleidsinstellingen voor veilige koppelingen in aangepaste beleidsregels voor specifieke gebruikers

**Opmerking**: in PowerShell gebruikt u de cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) en [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Selecteer de actie voor onbekende, mogelijk schadelijke Url's in berichten** <br/><br/> _IsEnabled_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Selecteer de actie voor onbekende of mogelijk schadelijke Url's in Microsoft teams** <br/><br/> _EnableSafeLinksForTeams_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Het scannen van realtime-URL'S toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** <br/><br/> _ScanUrls_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Wachten tot URL-Scan is voltooid voordat het bericht wordt bezorgd** <br/><br/> _DeliverMessageAfterScan_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden** <br/><br/> _EnableForInternalSenders_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <br/><br/> _DoNotTrackUserClicks_|Uit <br/><br/> `$false`|Uit <br/><br/> `$false`|
|**Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL** <br/><br/> _DoNotAllowClickThrough_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|

### <a name="atp-safe-attachments-policy-settings"></a>Beleidsinstellingen voor veilige bijlagen

Als u deze instellingen wilt configureren, raadpleegt u [Office 365 ATP voor veilige bijlagen instellen](set-up-atp-safe-attachments-policies.md).

#### <a name="safe-attachments-policy-settings-in-the-default-policy-for-all-users"></a>Beleidsinstellingen voor veilige bijlagen in het standaardbeleid voor alle gebruikers

**Opmerking**: in PowerShell gebruikt u de cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**ATP voor SharePoint, OneDrive en Microsoft Teams inschakelen** <br/><br/> _EnableATPForSPOTeamsODB_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|**Veilige documenten voor Office-clients inschakelen**<bt/><br/> _EnableSafeDocs_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||Deze instelling is alleen beschikbaar in de beveiligings licenties voor Microsoft 365 E5 of Microsoft 365 E5. Zie voor meer informatie [veilige documenten in Office 365 Advanced Threat Protection](safe-docs.md).|
|**Toestaan dat personen kunnen klikken via de beveiligde weergave, zelfs als het bestand door veilige documenten wordt geïdentificeerd als schadelijk**<bt/><br/> _AllowSafeDocsOpen_|Uit <br/><br/> `$false`|Uit <br/><br/> `$false`||
|

#### <a name="safe-attachments-policy-settings-in-custom-policies-for-specific-users"></a>Beleidsinstellingen voor veilige bijlagen in aangepaste beleidsregels voor specifieke gebruikers

**Opmerking**: in PowerShell gebruikt u de cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) en [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standard|Klep|Opmerking|
|---|---|---|---|
|**Veilige bijlagen onbekende schadelijk malware-antwoord** <br/><br/> _Actierij_|Blokkeren <br/><br/> `Block`|Blokkeren <br/><br/> `Block`||
|**Bijlage omleiden bij detectie** : **omleiden inschakelen** <br/><br/> _Omleiden_ <br/><br/> _RedirectAddress_|Op en opgeven van een e-mailadres. <br/><br/> `$true` <br/><br/> een e-mailadres|Op en opgeven van een e-mailadres. <br/><br/> `$true` <br/><br/> een e-mailadres|Berichten doorsturen naar een beveiligingsbeheerder voor revisie.|
|**De bovenstaande selectie toepassen als malware wordt gescand op bijlagen wanneer de fout optreedt.** <br/><br/> _ActionOnError_|Aan <br/><br/> `$true`|Aan <br/><br/> `$true`||
|

## <a name="related-topics"></a>Verwante onderwerpen

- Bent u op zoek naar aanbevolen procedures met **Exchange mail flow/Exchange-Transport regels**? Raadpleeg [dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) voor meer informatie.

- Beheerders en gebruikers kunnen fout-positieven (goede e-mailberichten die als beschadigd zijn gemarkeerd) en foutieve negatieven (onjuiste e-mail toegestaan) indienen bij Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het **instellen** van uw [EOP-service](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)en het **configureren** van [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Vergeet niet de handige aanwijzingen te zien in '[beveiliging tegen bedreigingen in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.

- De **beveiligings basislijnen voor Windows** kunt u [vinden in](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) de opties voor groepsbeleidsobjecten/on-premises, en voor [beveiliging op basis](https://docs.microsoft.com/intune/protect/security-baselines)van intune. Ten slotte vindt u een vergelijking tussen de Microsoft Defender Advanced Threat Protection (ATP) en Windows intune-beveiligings lijnen vindt u [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
