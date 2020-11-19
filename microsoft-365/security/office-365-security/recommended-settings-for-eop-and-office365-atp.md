---
title: Microsoft aanbevelingen voor EOP en Defender voor de beveiligingsinstellingen van Office 365, aanbevelingen, kader voor het beleid voor geadresseerden, berichten rapporteren en conformeert, DomainKeys geïdentificeerd, wat betekent dat u E-mail, stappen, hoe dit werkt, hoe u werkt met basislijnen, wat betekent dat het werkt, de basislijnen voor het werken met Office 365 365 365
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Wat zijn de aanbevolen procedures voor de beveiligingsinstellingen van Exchange Online Protection (EOP) en Defender for Office 365? Wat is de huidige aanbevelingen voor standaardbeveiliging? Wat moet worden gebruikt als u striktere informatie wilt? En welke extra's ontvangt u als u ook Defender voor Office 365 gebruikt?
ms.openlocfilehash: af741e1af412d535c53beb83c36c0cbe3fcd617b
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357119"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365-beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** is de kern van beveiliging voor microsoft 365-abonnementen en helpt voorkomen dat ongewenste e-mailberichten in de Postvak in van uw werknemers terechtkomen. Maar met nieuwe, nieuwe, nog geavanceerdere aanvallen die elke dag zijn verbeterd, zijn er vaak betere bescherming nodig. **Microsoft Defender voor Office 365** Abonnement 1 of abonnement 2 bevat extra functies die beheerders meer lagen bieden voor beveiliging, controle en onderzoek.

Hoewel we beveiligingsbeheerders kunnen helpen bij het aanpassen van hun beveiligingsinstellingen, zijn er twee beveiligingsniveaus in EOP en Microsoft Defender voor Office 365 die wij aanraden: **Standard** en **strict**. De omgeving van elke klant en de behoeften zijn niet alleen van toepassing, maar we geloven dat ze in de meeste gevallen het postvak in van uw werknemers kunnen bereiken.

Als u de standaard-of strikte instellingen automatisch wilt toepassen op gebruikers, raadpleegt u [vooraf ingestelde beveiligingsbeleid in EOP en Microsoft Defender voor Office 365](preset-security-policies.md).

> [!NOTE]
> De regel voor ongewenste e-mail moet worden ingeschakeld voor postvakken, zodat de filters goed werken. Het is standaard ingeschakeld, maar u moet controleren of het filteren niet lijkt te werken. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit artikel worden de standaardinstellingen beschreven en worden ook de aanbevolen standaard-en strikte instellingen gebruikt om uw gebruikers te helpen beschermen.

> [!TIP]
> De module Office 365 Advanced Threat Protection recommended configuration Analyzer (ORCA) voor PowerShell kan u helpen (beheerders) de huidige waarden van deze instellingen te zoeken. Met name de cmdlet **Get-ORCAReport** genereert een beoordeling van antispam, anti phishing en andere instellingen voor bericht hygiëne. U kunt de ORCA-module downloaden <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam, anti malware en bescherming tegen phishing in EOP

Antispam, anti-malware en anti phishing zijn EOP functies die kunnen worden geconfigureerd door beheerders. We raden u aan de volgende standaard-of strikte configuraties te volgen.

### <a name="eop-anti-spam-policy-settings"></a>EOP antispam beleidsinstellingen

Zie [Antispambeleid in Office 365 configureren](configure-your-spam-filter-policies.md)om Antispambeleid te maken en te configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Spam** detectie actie <p> _SpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantaine bericht** <p> `Quarantine`||
|**Hoge betrouwbaarheid van spam** detectie actie <p> _HighConfidenceSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantaine bericht** <p> `Quarantine`|**Quarantaine bericht** <p> `Quarantine`||
|Detectie actie **malafide e-mailadres** <p> _PhishSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantaine bericht** <p> `Quarantine`|**Quarantaine bericht** <p> `Quarantine`||
|Detectie van **phishing-e-mail voor hoog vertrouwen** <p> _HighConfidencePhishAction_|**Quarantaine bericht** <p> `Quarantine`|**Quarantaine bericht** <p> `Quarantine`|**Quarantaine bericht** <p> `Quarantine`||
|Actie **bulksgewijs e-mail** detectie <p> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantaine bericht** <p> `Quarantine`||
|Drempelwaarde voor bulk mail <p> _BulkThreshold_|7,5|zes|3|Zie [bulk klachten niveau (BCL) in Office 365](bulk-complaint-level-values.md)voor meer informatie.|
|Bewaarperiode voor quarantaine <p> _QuarantineRetentionPeriod_|15 dagen|30 dagen|30 dagen||
|**Veiligheids tips** <p> _InlineSafetyTipsEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|Toegestane afzenders <p> _AllowedSenders_|Geen|Geen|Geen||
|Toegestaan domein van afzender <p> _AllowedSenderDomains_|Geen|Geen|Geen|Het toevoegen van domeinen aan de lijst met toegestane afzenders is een zeer slecht idee. Hackers kunnen u e-mailberichten sturen met een andere filter. <p> Gebruik [spoof Intelligence](learn-about-spoof-intelligence.md) in het beveiligings & compliance op de pagina **anti spam instellingen** om alle afzenders te bekijken die e-mailadressen van de afzender in de e-mail domeinen van uw organisatie of e-mailadressen van de afzender in de e-mail domeinen van uw organisatie spoofen.|
|Geblokkeerde afzenders <p> _BlockedSenders_|Geen|Geen|Geen||
|Geblokkeerde afzender domeinen <p> _BlockedSenderDomains_|Geen|Geen|Geen||
|**Spam meldingen voor eindgebruikers inschakelen** <p> _EnableEndUserSpamNotifications_|Uitgeschakeld <p> `$false`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|**Spam meldingen voor eindgebruikers elke (dagen) verzenden** <p> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen|3 dagen||
|**Spam ZAP** <p> _SpamZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|**Phishing ZAP** <p> _PhishZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|_MarkAsSpamBulkMail_|Aan|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|
|

Er zijn verschillende andere instellingen voor Advanced Spam filters (ASF) in anti spam beleid dat wordt afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies wordt buiten dit artikel meegedeeld.

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

Zie [limieten verzenden](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)voor meer informatie over de standaard verzendings limieten in de service.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Maximum aantal geadresseerden per gebruiker: extern uur limiet** <p> _RecipientLimitExternalPerHour_|0|500|400|De standaardwaarde 0 betekent dat de service standaardwaarden worden gebruikt.|
|**Maximaal aantal geadresseerden per gebruiker: intern uur limiet** <p> _RecipientLimitInternalPerHour_|0|1000|800|De standaardwaarde 0 betekent dat de service standaardwaarden worden gebruikt.|
|**Maximum aantal geadresseerden per gebruiker: dagelijkse limiet** <p> _RecipientLimitPerDay_|0|1000|800|De standaardwaarde 0 betekent dat de service standaardwaarden worden gebruikt.|
|**Actie wanneer een gebruiker de limieten overschrijdt** <p> _ActionWhenThresholdReached_|**Zorgen dat de gebruiker geen e-mail meer kan verzenden voor de volgende dag** <p> `BlockUserForToday`|**Verhinderen dat gebruikers e-mail verzenden** <p> `BlockUser`|**Verhinderen dat gebruikers e-mail verzenden** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP anti malware-beleidsinstellingen

Zie [anti malware-beleidsregels in Office 365 configureren](configure-anti-malware-policies.md)om anti-malwarebeleid te maken en te configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Wilt u geadresseerden informeren wanneer hun berichten in quarantaine worden geplaatst?** <p> _Actierij_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Als er malware in een e-mailbijlage is gedetecteerd, wordt het bericht in quarantaine geplaatst en kan het alleen door een beheerder worden vrijgegeven.|
|**Algemene bijlage typen filter** <p> _EnableFileFilter_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van bestandstypen, ongeacht de inhoud van de bijlage.|
|**Malware 0-uur automatisch wissen** <p> _ZapEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Interne afzenders** van het niet-bezorgde bericht informeren <p> _EnableInternalSenderNotifications_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|**Externe afzenders** van het niet-bezorgde bericht informeren <p> _EnableExternalSenderNotifications_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>EOP standaard anti phishingfilter-beleidsinstellingen

Zie [spoof Settings (spoof Settings](set-up-anti-phishing-policies.md#spoof-settings)) voor meer informatie over deze instellingen. Zie [anti phishingfilter in EOP](configure-anti-phishing-policies-eop.md)voor informatie over het configureren van deze instellingen.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Anti spoofing-beveiliging inschakelen** <p> _EnableAntispoofEnforcement_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Niet-geverifieerde afzender inschakelen** <p> _EnableUnauthenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Voegt een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-aangewezen vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md).|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <p> `MoveToJmf`|**Het bericht Quarantine** <p> `Quarantine`|Deze instelling geldt voor geblokkeerde afzenders in [spoof Intelligence](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender voor Office 365-beveiliging

Extra beveiligingsvoordelen worden geleverd met een Microsoft Defender for Office 365-abonnement. Voor het laatste nieuws en informatie kunt u zien [wat er nieuw is in Defender voor Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Het standaard anti-phishingfilter in Microsoft Defender voor Office 365 biedt [vervalsings beveiliging](set-up-anti-phishing-policies.md#spoof-settings) en Postvak intelligentie voor alle geadresseerden. De andere beschikbare functies voor [imitatie beveiliging](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en [Geavanceerde instellingen](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) zijn echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u alle beveiligingsfuncties wilt inschakelen, wijzigt u het standaard anti-phishingfilter of maakt u een extra anti-phishingfilter.
>
> - Er zijn geen standaardbeleid voor veilige koppelingen of beleidsregels voor veilige bijlagen waarmee alle geadresseerden in de organisatie automatisch worden beveiligd. Voor de bescherming moet u minimaal één beleid voor veilige koppelingen en een veilig bijlage beleid creëren.
>
> - Het beleid voor [de bescherming van](safe-docs.md) [ATP voor SharePoint, OneDrive en Microsoft teams](atp-for-spo-odb-and-teams.md) heeft geen afhankelijkheden voor beleidsregels voor veilige koppelingen.

Als uw abonnement Microsoft Defender voor Office 365 bevat of als u Defender voor Office 365 als een invoegtoepassing hebt gekocht, kunt u de volgende standaard-of strikte configuraties instellen.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Anti malafide beleidsinstellingen in Microsoft Defender voor Office 365

EOP-klanten hebben een eenvoudige anti-phishing zoals hierboven beschreven, maar Microsoft Defender voor Office 365 bevat meer functies en beheer voor het voorkomen, detecteren en oplossen van aanvallen. Als u deze beleidsregels wilt maken en configureren, raadpleegt u [anti phishingfilter configureren in de Defender voor Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishing beleid in Microsoft Defender voor Office 365

Zie voor meer informatie over deze instellingen de instelling [imitatie in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Als u deze instellingen wilt configureren, raadpleegt u [anti phishingfilter configureren in de Defender voor Office 365](configure-atp-anti-phishing-policies.md).

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|Beveiligde gebruikers: **gebruikers toevoegen om te beschermen** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of users\>|Aan <p> `$true` <p> \<list of users\>|Afhankelijk van uw organisatie adviseren we u om gebruikers (afzenders van berichten) toe te voegen in belangrijke rollen. Intern, beveiligde afzenders kunnen de directeur, CFO en andere leidinggevenden zijn. Extern kunnen beveiligde afzenders ook onder de Commissie vallen.|
|Beveiligde domeinen: **automatisch de domeinen opnemen waarvan ik eigenaar ben** <p> _EnableOrganizationDomainsProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of domains\>|Aan <p> `$true` <p> \<list of domains\>|Afhankelijk van uw organisatie, wordt u aangeraden domeinen toe te voegen (de domeinen van de afzender) waarvan u geen eigenaar bent, maar waarmee u regelmatig communiceert.|
|Beveiligde gebruikers: **als e-mail wordt verzonden door een geïmiteerde gebruiker** <p> _TargetedUserProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht Quarantine** <p> `Quarantine`|**Het bericht Quarantine** <p> `Quarantine`||
|Beveiligde domeinen: **als e-mail wordt verzonden door een geïmiteerd domein** <p> _TargetedDomainProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht Quarantine** <p> `Quarantine`|**Het bericht Quarantine** <p> `Quarantine`||
|**Tip weergeven voor geïmiteerde gebruikers** <p> _EnableSimilarUsersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip weergeven voor geïmiteerde domeinen** <p> _EnableSimilarDomainsSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip voor ongebruikelijk tekens weergeven** <p> _EnableUnusualCharactersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Postvak intelligentie inschakelen?** <p> _EnableMailboxIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Schakelt u de bescherming van imitatie op basis van een postvak in?** <p> _EnableMailboxIntelligenceProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**E-mail wordt verzonden door een geïmiteerde gebruiker die is beveiligd via een postvak intelligentie** <p> _MailboxIntelligenceProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <p> `MoveToJmf`|**Het bericht Quarantine** <p> `Quarantine`||
|**Vertrouwde afzenders** <p> _ExcludedSenders_|Geen|Geen|Geen|Afhankelijk van uw organisatie wordt u aangeraden gebruikers toe te voegen die niet als phishing worden aangemerkt, en geen andere filters.|
|**Vertrouwde domeinen** <p> _ExcludedDomains_|Geen|Geen|Geen|Afhankelijk van uw organisatie, wordt u aangeraden domeinen toe te voegen die niet als phishing worden aangemerkt, en geen andere filters.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoofberichten instellingen in Microsoft Defender voor Office 365

Dit zijn de instellingen die beschikbaar zijn in de instellingen voor [Antispambeleid in EOP](#eop-anti-spam-policy-settings).

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|---|---|---|---|
|**Anti spoofing-beveiliging inschakelen** <p> _EnableAntispoofEnforcement_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Niet-geverifieerde afzender inschakelen** <p> _EnableUnauthenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Voegt een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-aangewezen vervalste afzenders. Zie voor meer informatie [spoofberichten instellingen in anti-phishingfilter](set-up-anti-phishing-policies.md).|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste E-mail van de geadresseerde** <p> `MoveToJmf`|**Het bericht Quarantine** <p> `Quarantine`|Deze instelling geldt voor geblokkeerde afzenders in [spoof Intelligence](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde instellingen in anti-phishing-beleid in Microsoft Defender voor Office 365

Zie voor meer informatie over deze instelling [Geavanceerde phishingberichten in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Als u deze instelling wilt configureren, raadpleegt u [anti phishingfilter configureren in de Defender voor Office 365](configure-atp-anti-phishing-policies.md).

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Geavanceerde phishingberichten** <p> _PhishThresholdLevel_|**1-standaard** <p> `1`|**2-agressief** <p> `2`|**3-meer agressief** <p> `3`||
|

### <a name="safe-links-settings"></a>Instellingen voor veilige koppelingen

Veilige koppelingen in Defender voor Office 365 bevatten algemene instellingen die van toepassing zijn op alle gebruikers die deel uitmaken van het beleid van Active links Zie voor meer informatie [veilige koppelingen in Defender voor Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Algemene instellingen voor veilige koppelingen

Als u deze instellingen wilt configureren, raadpleegt u [algemene instellingen configureren voor veilige koppelingen in Defender voor Office 365](configure-global-settings-for-safe-links.md).

In PowerShell gebruikt u de cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Veilige koppelingen gebruiken in: Office 365-toepassingen** <p> _EnableSafeLinksForO365Clients_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Gebruik veilige koppelingen in ondersteunde Office 365-bureaubladtoepassingen en mobiele apparaten (iOS-en Android-apps). Zie [instellingen voor veilige koppelingen voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.|
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <p> _TrackClicks_|Aan <p> `$false`|Uit <p> `$true`|Uit <p> `$true`|Als u deze instelling uitschakelt (bij het instellen van _TrackClicks_ op `$true` ), worden de gebruikers in ondersteunde Office 365-apps bijgehouden.|
|**Gebruikers niet laten klikken via veilige koppelingen naar de oorspronkelijke URL** <p> _AllowClickThrough_|Aan <p> `$false`|Aan <p> `$false`|Aan <p> `$false`|Als u deze instelling inschakelt ( _AllowClickThrough_ instellen op `$false` ), kunt u door de oorspronkelijke URL in ondersteunde Office 365-apps klikken.|
|

#### <a name="safe-links-policy-settings"></a>Beleidsinstellingen voor veilige koppelingen

Als u deze instellingen wilt configureren, raadpleegt u [beleidsregels voor veilige koppelingen instellen in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md).

In PowerShell gebruikt u de cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) en [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder is beschreven, is er geen standaardbeleid voor veilige koppelingen. De waarden in de standaardkolom zijn de standaardwaarden in nieuwe beleidsregels voor veilige koppelingen die u maakt.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Selecteer de actie voor onbekende, mogelijk schadelijke Url's in berichten** <p> _IsEnabled_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Selecteer de actie voor onbekende of mogelijk schadelijke Url's in Microsoft teams** <p> _EnableSafeLinksForTeams_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Het scannen van realtime-URL'S toepassen op verdachte koppelingen en koppelingen die verwijzen naar bestanden** <p> _ScanUrls_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Wachten tot URL-Scan is voltooid voordat het bericht wordt bezorgd** <p> _DeliverMessageAfterScan_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden** <p> _EnableForInternalSenders_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Geclickte gebruikers niet bijhouden** <p> _DoNotTrackUserClicks_|Uit <p> `$false`|Uit <p> `$false`|Uit <p> `$false`|Als u deze instelling inschakelt (instellingen _DoNotTrackUserClicks_ aan `$false` ) spoort u gebruikers op.|
|**Gebruikers kunnen niet naar de oorspronkelijke URL klikken** <p> _DoNotAllowClickThrough_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Als u deze instelling inschakelt ( _DoNotAllowClickThrough_ instellen op `$true` ), kunt u door de oorspronkelijke URL klikken.|
|

### <a name="safe-attachments-settings"></a>Instellingen voor veilige bijlagen

Veilige bijlagen in Microsoft Defender voor Office 365 bevatten algemene instellingen die geen relatie hebben met beleidsregels voor veilige bijlagen en instellingen die specifiek zijn voor elk beleid voor veilige koppelingen. Zie voor meer informatie [veilige bijlagen in de Defender voor Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Algemene instellingen voor veilige bijlagen

Als u deze instellingen wilt configureren, raadpleegt u [ATP voor SharePoint, OneDrive en Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) en [veilige documenten inschakelen in Microsoft 365 E5](safe-docs.md).

In PowerShell gebruikt u de cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**ATP inschakelen voor SharePoint, OneDrive en Microsoft teams** <p> _EnableATPForSPOTeamsODB_|Aan <p> `$true`|Aan <p> `$true`||
|**Veilige documenten voor Office-clients inschakelen**<bt/><br/> _EnableSafeDocs_|Aan <p> `$true`|Aan <p> `$true`|Deze instelling is alleen beschikbaar in de beveiligings licenties voor Microsoft 365 E5 of Microsoft 365 E5. Zie voor meer informatie [veilige documenten in Microsoft Defender voor Office 365](safe-docs.md).|
|**Toestaan dat personen kunnen klikken via de beveiligde weergave, zelfs als het bestand door veilige documenten wordt geïdentificeerd als schadelijk**<bt/><br/> _AllowSafeDocsOpen_|Uit <p> `$false`|Uit <p> `$false`|Deze instelling is gerelateerd aan veilige documenten.|
|

#### <a name="safe-attachments-policy-settings"></a>Beleidsinstellingen voor veilige bijlagen

Als u deze instellingen wilt configureren, raadpleegt u [beleidsregels voor veilige bijlagen instellen in Defender voor Office 365](set-up-atp-safe-attachments-policies.md).

In PowerShell gebruikt u de cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) en [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder is beschreven, is er geen standaardbeleid voor veilige bijlagen. De waarden in de standaardkolom zijn de standaardwaarden in nieuwe beleidsregels voor veilige bijlagen die u maakt.

****

|Naam van beveiligingsfunctie|Standaard|Standaard|Klep|Opmerking|
|---|:---:|:---:|:---:|---|
|**Veilige bijlagen onbekende schadelijk malware-antwoord** <p> _Actierij_|Blokkeren <p> `Block`|Blokkeren <p> `Block`|Blokkeren <p> `Block`||
|**Bijlage omleiden bij detectie** : **omleiden inschakelen** <p> _Omleiden_ <p> _RedirectAddress_|Off, en geen e-mailadres opgegeven. <p> `$true` <p> geen|En geef een e-mailadres op. <p> `$true` <p> een e-mailadres|En geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Berichten doorsturen naar een beveiligingsbeheerder voor revisie.|
|**De bovenstaande selectie toepassen als malware wordt gescand op bijlagen wanneer de fout optreedt.** <p> _ActionOnError_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|

## <a name="related-articles"></a>Verwante artikelen

- Bent u op zoek naar aanbevolen procedures voor **Exchange-e-mail stroom regels (ook wel een zogenaamde transportregels genoemd**)? Zie [Aanbevolen procedures voor het configureren van e-mail stroom regels in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Beheerders en gebruikers kunnen fout-positieven (goede e-mailberichten die als beschadigd zijn gemarkeerd) en foutieve negatieven (onjuiste e-mail toegestaan) indienen bij Microsoft voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het **instellen** van uw [EOP-service](set-up-your-eop-service.md)en het **configureren** [van Microsoft Defender voor Office 365](office-365-atp.md). Vergeet de handige aanwijzingen niet te zien in '[beveiliging tegen bedreigingen in Office 365](protect-against-threats.md)'.

- In dit onderwerp vindt u de **beveiligings basislijnen voor Windows** : [waar kan ik de basislijnen voor beveiliging vinden? voor de](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) opties voor GPO en on-premises, en [beveiligings basislijnen gebruiken om Windows 10-apparaten te configureren in intune](https://docs.microsoft.com/intune/protect/security-baselines) voor intune-based beveiliging. Ten slotte is er een vergelijking tussen Microsoft Defender voor eindpunten en Microsoft intune-beveiligings lijnen beschikbaar in [de Microsoft-eindpunten voor eindpunten en de Windows intune-beveiligings basislijnen vergelijken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
