---
title: Microsoft-aanbevelingen voor EOP en Defender voor Office 365 beveiligingsinstellingen
keywords: Office 365 beveiligingsaanbevelingen, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, steps, how does it work, security baselines, baselines for EOP, baselines for Defender for Office 365 , set up Defender for Office 365 , set up EOP, configure Defender for Office 365, configure EOP, security configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Wat zijn best practices voor Exchange Online Protection (EOP) en Defender voor Office 365 beveiligingsinstellingen? Wat zijn de huidige aanbevelingen voor standaardbeveiliging? Wat moet u gebruiken als u strikter wilt zijn? En welke extra's krijgt u als u Ook Defender gebruikt voor Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b6661c31d0cc05a1bdfd51de986af1e7b22c9d70
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696524"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Aanbevolen instellingen voor EOP en Microsoft Defender voor Office 365 beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** is de kern van de beveiliging voor Microsoft 365-abonnementen en helpt voorkomen dat schadelijke e-mailberichten de Postvak IN van uw werknemer bereiken. Maar nu er elke dag nieuwe, geavanceerdere aanvallen worden uitgevoerd, zijn verbeterde beveiligingen vaak vereist. **Microsoft Defender voor Office 365** Plan 1 of Plan 2 bevatten extra functies die beheerders meer lagen van beveiliging, controle en onderzoek bieden.

Hoewel we beveiligingsbeheerders in staat stellen hun beveiligingsinstellingen aan te passen, zijn er twee beveiligingsniveaus in EOP en Microsoft Defender voor Office 365 die we aanbevelen: **Standaard** en **Strikt.** De omgeving en behoeften van elke klant zijn verschillend, maar we zijn van mening dat deze filterniveaus voorkomen dat ongewenste e-mail in de meeste situaties het Postvak IN van uw werknemers bereikt.

Zie Vooraf ingestelde beveiligingsbeleidsregels [in EOP](preset-security-policies.md)en Microsoft Defender voor Office 365.

> [!NOTE]
> De regel ongewenste e-mail moet zijn ingeschakeld in postvakken om te kunnen filteren op de juiste manier. Deze functie is standaard ingeschakeld, maar u moet controleren of filteren niet werkt. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit artikel worden de standaardinstellingen beschreven, en ook de aanbevolen standaard- en strikte instellingen om uw gebruikers te beschermen. De tabellen bevatten de instellingen in het Microsoft 365-beveiligingscentrum en PowerShell (Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell voor organisaties zonder Exchange Online postvakken).

> [!TIP]
> De Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) module voor PowerShell kan u (beheerders) helpen de huidige waarden van deze instellingen te vinden. De **get-ORCAReport-cmdlet** genereert met name een beoordeling van antispam, anti-phishing en andere instellingen voor berichthygiëne. U kunt de ORCA-module downloaden op <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam, anti-malware en anti-phishingbeveiliging in EOP

Antispam, anti-malware en anti-phishing zijn EOP-functies die kunnen worden geconfigureerd door beheerders. We raden u de volgende standaard- of strikte configuraties aan.

### <a name="eop-anti-spam-policy-settings"></a>EOP-antispambeleidsinstellingen

Zie [Antispambeleid](configure-your-spam-filter-policies.md)configureren in Office 365.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Actie voor spamdetectie** <p> _SpamActie_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|**Actie voor het opsporen van spam** met veel vertrouwen <p> _HighConfidenceSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Phishingdetectieactie** <p> _PhishSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Phishingdetectieactie met** hoog vertrouwen <p> _HighConfidencePhishAction_|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Bulkdetectieactie** <p> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|**Drempelwaarde voor bulksgewijs e-mail** <p> _BulkThreshold_|7|6|4|Zie Bulk [complaint level (BCL) in](bulk-complaint-level-values.md)Office 365 .|
|_MarkAsSpamBulkMail_|Aan|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|
|**Spam in quarantaine bewaren voor deze dagen** <p> _QuarantineRetentionPeriod_|15 dagen|30 dagen|30 dagen||
|**Tips voor spamveiligheid inschakelen** <p> _InlineSafetyTipsEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|Toegestane afzenders <p> _AllowedSenders_|Geen|Geen|Geen||
|Toegestane afzenderdomeinen <p> _AllowedSenderDomains_|Geen|Geen|Geen|Het toevoegen van domeinen aan de lijst met toegestane afzenders is een heel slecht idee. Aanvallers kunnen u e-mail sturen die anders zou worden gefilterd. <p> Gebruik het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) en de [Tenant Allow/Block List](tenant-allow-block-list.md) om alle afzenders te controleren die e-mailadressen van afzenders spoofen in de e-maildomeinen van uw organisatie of e-mailadressen van afzenders voor spoofing in externe domeinen.|
|Geblokkeerde afzenders <p> _Geblokkeerde senders_|Geen|Geen|Geen||
|Geblokkeerde afzenderdomeinen <p> _BlockedSenderDomains_|Geen|Geen|Geen||
|**Spammeldingen voor eindgebruikers inschakelen** <p> _EnableEndUserSpamNotifications_|Uitgeschakeld <p> `$false`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|**Spammeldingen voor eindgebruikers elke (dagen) verzenden** <p> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen|3 dagen||
|Automatische purge (ZAP) voor phishingberichten inschakelen <p> _PhishZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|ZAP inschakelen voor spambericht <p> _SpamZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|

Er zijn veel geavanceerde instellingen voor spamfilter (ASF) in antispambeleid die momenteel worden afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies wordt buiten dit artikel gecommuniceerd.

Het is raadzaam om de volgende ASF-instellingen uit te **laten voor** zowel **standaard-** als **strikte** niveaus. Zie Asf-instellingen (Advanced Spam Filter) in Office 365 voor [meer informatie over ASF-instellingen.](advanced-spam-filtering-asf-options.md)

<br>

****

|Naam van beveiligingsfunctie|Opmerking|
|---|---|
|**Afbeeldingskoppelingen naar externe sites** (_IncreaseScoreWithImageLinks_)||
|**Numeriek IP-adres in URL** (_IncreaseScoreWithNumericIps_)||
|**UL redirect to other port** _(IncreaseScoreWithRedirectToOtherPort_)||
|**URL naar .biz- of .info-websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Lege berichten** (_MarkAsSpamEmptyMessages_)||
|**JavaScript of VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Frame- of IFrame-tags in HTML** (_MarkAsSpamFramesInHtml_)||
|**Objectlabels in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Tags insluiten in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Formulierlabels in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Web bugs in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Lijst met gevoelige woorden toepassen** (_MarkAsSpamSensitiveWordList_)||
|**SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Voorwaardelijke afzender-id-filtering: hard fail** (_MarkAsSpamFromAddressAuthFail_)||
|**NDR backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-instellingen voor uitgaand spambeleid

Zie Uitgaande [spamfilters](configure-the-outbound-spam-policy.md)configureren in Office 365.

Zie Limieten verzenden voor meer informatie over de standaardlimieten voor verzenden in [de](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)service.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Maximum aantal geadresseerden per gebruiker: limiet voor extern uur** <p> _RecipientLimitExternalPerHour_|0|500|400|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Maximum aantal geadresseerden per gebruiker: interne uurlimiet** <p> _RecipientLimitInternalPerHour_|0|1000|800|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Maximum aantal geadresseerden per gebruiker: dagelijkse limiet** <p> _RecipientLimitPerDay_|0|1000|800|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Actie wanneer een gebruiker de limieten overschrijdt** <p> _ActionWhenThresholdReached_|**De gebruiker beperken van het verzenden van e-mail tot de volgende dag** <p> `BlockUserForToday`|**De gebruiker beperken van het verzenden van e-mail** <p> `BlockUser`|**De gebruiker beperken van het verzenden van e-mail** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-beleid voor anti-malwarebeleid

Zie [Anti-malwarebeleid](configure-anti-malware-policies.md)configureren in Office 365 .

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Geadresseerden op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _Actie_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Als malware wordt gedetecteerd in een e-mailbijlage, wordt het bericht in quarantaine geplaatst en kan het alleen worden uitgebracht door een beheerder.|
|**Het algemene bijlagefilter inschakelen** <p> _EnableFileFilter_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van bestandstype, ongeacht de inhoud van de bijlage.|
|**Automatische purge van nul uur inschakelen voor malware** <p> _ZapEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Interne afzenders op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _EnableInternalSenderNotifications_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|**Externe afzenders op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _ExternalSenderNotifications inschakelen_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Standaardinstellingen voor anti-phishingbeleid van EOP

Zie Spoof-instellingen voor [meer informatie over deze instellingen.](set-up-anti-phishing-policies.md#spoof-settings) Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP om deze instellingen te configureren.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Bescherming tegen spoofing inschakelen** <p> _EnableSpoofIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Unauthenticated Sender inschakelen** <p> _EnableUnauthenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Hiermee wordt een vraagteken (?) toegevoegd aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md) voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op vervalste afzenders die automatisch zijn geblokkeerd, zoals wordt weergegeven in het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) of handmatig is geblokkeerd in de [lijst Tenant Allow/Block](tenant-allow-block-list.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender voor Office 365 beveiliging

Extra beveiligingsvoordelen worden bij een Microsoft Defender voor Office 365 abonnement. Voor het laatste nieuws en informatie kunt u Zien Wat is er nieuw [in Defender voor Office 365.](whats-new-in-defender-for-office-365.md)

> [!IMPORTANT]
>
> - Het standaard anti-phishingbeleid in Microsoft Defender voor Office 365 biedt [spoofbeveiliging](set-up-anti-phishing-policies.md#spoof-settings) en postvakinformatie voor alle geadresseerden. De andere beschikbare functies voor [imitatiebeveiliging](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en geavanceerde instellingen [zijn](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u alle beveiligingsfuncties wilt inschakelen, wijzigt u het standaardbeleid voor phishing of maakt u extra anti-phishingbeleid.
>
> - Er zijn geen standaardinstellingen Safe koppelingen of Safe bijlagen die automatisch alle geadresseerden in de organisatie beveiligen. Als u de beveiligingen wilt krijgen, moet u ten minste één Safe Koppelingenbeleid en Safe bijlagenbeleid maken.
>
> - Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams](mdo-for-spo-odb-and-teams.md) beveiliging en [Safe](safe-docs.md) Documentenbeveiliging zijn niet afhankelijk van Safe koppelingenbeleid.

Als uw abonnement Microsoft Defender voor Office 365 bevat of als u Defender voor Office 365 hebt gekocht als invoegabonnement, stelt u de volgende standaard- of strikte configuraties in.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Anti-phishingbeleidsinstellingen in Microsoft Defender voor Office 365

EOP-klanten krijgen standaard anti-phishing zoals eerder beschreven, maar Microsoft Defender voor Office 365 bevat meer functies en controle om aanvallen te voorkomen, te detecteren en te herstellen. Zie [Anti-phishingbeleid](configure-atp-anti-phishing-policies.md)configureren in Defender voor Office 365.

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie Instellingen voor imitatie in [anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365. Zie [Anti-phishingbeleid](configure-atp-anti-phishing-policies.md)configureren in Defender voor Office 365.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|Beveiligde gebruikers: **Gebruikers toevoegen om ze te beveiligen** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of users\>|Aan <p> `$true` <p> \<list of users\>|Afhankelijk van uw organisatie wordt u aangeraden gebruikers (afzenders van berichten) toe te voegen aan belangrijke rollen. Intern kunnen beveiligde afzenders uw CEO, CFO en andere senior leaders zijn. Externe, beveiligde afzenders kunnen leden van de raad of uw raad van bestuur bevatten.|
|Beveiligde domeinen: automatisch de domeinen **opnemen die ik bezit** <p> _EnableOrganizationDomainsProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of domains\>|Aan <p> `$true` <p> \<list of domains\>|Afhankelijk van uw organisatie raden we u aan domeinen (afzenderdomeinen) toe te voegen die niet van u zijn, maar die u vaak gebruikt.|
|Beveiligde gebruikers: **Als e-mail wordt verzonden door een nagebootsde gebruiker** <p> _TargetedUserProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|Beveiligde domeinen: **Als e-mail wordt verzonden door een nagebootsd domein** <p> _TargetedDomainProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Tip voor imiteerde gebruikers tonen** <p> _EnableSimilarUsersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip voor nagebootste domeinen tonen** <p> _EnableSimilarDomainsSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip voor ongebruikelijke tekens tonen** <p> _EnableUnusualCharactersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Postvakintelligentie inschakelen?** <p> _EnableMailboxIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Postvakintelligentie inschakelen op basis van imitatiebeveiliging?** <p> _EnableMailboxIntelligenceProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Als e-mail wordt verzonden door een nagebootsde gebruiker die is beveiligd met postvakinformatie** <p> _MailboxIntelligenceProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Vertrouwde afzenders** <p> _ExcludedSenders_|Geen|Geen|Geen|Afhankelijk van uw organisatie raden we u aan gebruikers toe te voegen die ten onrechte als phishing zijn gemarkeerd vanwege imitatie en niet door andere filters.|
|**Vertrouwde domeinen** <p> _ExcludedDomains_|Geen|Geen|Geen|Afhankelijk van uw organisatie raden we u aan domeinen toe te voegen die ten onrechte als phishing worden gemarkeerd vanwege imitatie en niet door andere filters.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoofinstellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Houd er rekening mee dat dit dezelfde instellingen zijn die beschikbaar zijn in de instellingen voor [antispambeleid in EOP.](#eop-anti-spam-policy-settings)

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|---|---|---|---|
|**Bescherming tegen spoofing inschakelen** <p> _EnableSpoofIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Unauthenticated Sender inschakelen** <p> _EnableUnauthenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Hiermee wordt een vraagteken (?) toegevoegd aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Instellingen voor adresvervalsing in anti-phishingbeleid](set-up-anti-phishing-policies.md) voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op vervalste afzenders die automatisch zijn geblokkeerd, zoals wordt weergegeven in het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) of handmatig is geblokkeerd in de [lijst Tenant Allow/Block](tenant-allow-block-list.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie Advanced [phishing thresholds in anti-phishing policies in Microsoft Defender](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)for Office 365 voor meer informatie over deze instelling. Zie [Anti-phishingbeleid](configure-atp-anti-phishing-policies.md)configureren in Defender voor Office 365.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Geavanceerde phishingdrempels** <p> _PhishThresholdLevel_|**1 - Standaard** <p> `1`|**2 - Agressief** <p> `2`|**3 - Agressiever** <p> `3`||
|

### <a name="safe-links-settings"></a>Safe Koppelingeninstellingen

Safe Koppelingen in Defender voor Office 365 bevat algemene instellingen die van toepassing zijn op alle gebruikers die zijn opgenomen in het beleid voor actieve Safe Koppelingen en instellingen die specifiek zijn voor elk Safe Koppelingenbeleid. Zie Koppelingen in [Defender voor Safe voor meer Office 365.](safe-links.md)

#### <a name="global-settings-for-safe-links"></a>Algemene instellingen voor Safe koppelingen

Zie Algemene instellingen configureren voor Safe koppelingen in Defender voor [Office 365.](configure-global-settings-for-safe-links.md)

In PowerShell gebruikt u de [set-AtpPolicyForO365-cmdlet](/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Koppelingen Safe gebruiken in: Office 365 toepassingen** <p> _EnableSafeLinksForO365Clients_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Gebruik Safe Koppelingen in ondersteunde Office 365 desktop- en mobiele apps (iOS en Android). Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)|
|**Niet bijhouden wanneer gebruikers op koppelingen Safe klikken** <p> _TrackClicks_|Aan <p> `$false`|Uit <p> `$true`|Uit <p> `$true`|Als u deze instelling uit schakelen _(trackclicks_ instellen op) worden `$true` gebruikersklikken in ondersteunde Office 365 bij.|
|**Gebruikers mogen niet door de Safe koppelingen naar de oorspronkelijke URL klikken** <p> _AllowClickThrough_|Aan <p> `$false`|Aan <p> `$false`|Aan <p> `$false`|Door deze instelling in te stellen _(allowClickThrough_ in te stellen) wordt voorkomen dat doorklikken naar de oorspronkelijke URL in ondersteunde `$false` Office 365 apps.|
|

#### <a name="safe-links-policy-settings"></a>Safe Beleidsinstellingen voor koppelingen

Als u deze instellingen wilt configureren, gaat u naar [Beleidsregels Safe Koppelingen instellen in Microsoft Defender voor Office 365.](set-up-safe-links-policies.md)

In PowerShell gebruikt u de [cmdlets New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) en [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder beschreven, is er geen standaardinstelling Safe koppelingenbeleid. De waarden in de kolom Standaard zijn de standaardwaarden in nieuwe Safe koppelingenbeleid dat u maakt.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten** <p> _IsEnabled_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Selecteer de actie voor onbekende of potentieel schadelijke URL's binnen Microsoft Teams** <p> _EnableSafeLinksForTeams_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Realtime URL-scan toepassen op verdachte koppelingen en koppelingen die naar bestanden wijzen** <p> _ScanUrls_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt** <p> _DeliverMessageAfterScan_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Koppelingen Safe toepassen op e-mailberichten die binnen de organisatie zijn verzonden** <p> _EnableForInternalSenders_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Gebruikersklikken niet bijhouden** <p> _DoNotTrackUserClicks_|Uit <p> `$false`|Uit <p> `$false`|Uit <p> `$false`|Als u deze instelling uit schakelen _(doNotTrackUserClicks_ instellen `$false` op) worden gebruikersklikken bij de gebruiker bij de muisaanklikken bij het volgen van de muisklikken.|
|**Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL** <p> _DoNotAllowClickThrough_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Door deze instelling in te stellen _(doNotAllowClickThrough_ in te stellen) wordt voorkomen dat u `$true` doorklikt naar de oorspronkelijke URL.|
|

### <a name="safe-attachments-settings"></a>Safe Instellingen voor bijlagen

Safe Bijlagen in Microsoft Defender voor Office 365 bevat algemene instellingen die geen relatie hebben met Safe Bijlagen-beleid en instellingen die specifiek zijn voor elk Safe Koppelingenbeleid. Zie bijlagen in [Defender voor Safe voor meer Office 365.](safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>Algemene instellingen voor Safe bijlagen

Als u deze instellingen wilt configureren, gaat u naar Safe Bijlagen in [SharePoint, OneDrive en Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) en [Safe Documenten in](safe-docs.md)Microsoft 365 E5.

In PowerShell gebruikt u de [set-AtpPolicyForO365-cmdlet](/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Aan <p> `$true`|Aan <p> `$true`||
|**Documenten in Safe voor Office-clients** <p> _EnableSafeDocs_|Aan <p> `$true`|Aan <p> `$true`|Deze instelling is alleen beschikbaar met Microsoft 365 E5 of Microsoft 365 E5 Security licenties. Zie voor meer informatie [Safe Documenten in Microsoft Defender voor Office 365.](safe-docs.md)|
|**Toestaan dat personen door de beveiligde weergave kunnen klikken, zelfs Safe documenten het bestand als schadelijk hebben geïdentificeerd** <p> _AllowSafeDocsOpen_|Uit <p> `$false`|Uit <p> `$false`|Deze instelling is gerelateerd aan Safe Documenten.|
|

#### <a name="safe-attachments-policy-settings"></a>Safe Instellingen voor bijlagenbeleid

Als u deze instellingen wilt configureren, gaat u naar Het beleid Safe [Bijlagen instellen in Defender voor Office 365.](set-up-safe-attachments-policies.md)

In PowerShell gebruikt u de [cmdlets New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) en [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder is beschreven, is er geen standaardinstelling Safe bijlagenbeleid. De waarden in de kolom Standaard zijn de standaardwaarden in nieuwe Safe bijlagen die u maakt.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Safe Attachments unknown malware response** <p> _Actie_|Blokkeren <p> `Block`|Blokkeren <p> `Block`|Blokkeren <p> `Block`||
|**Bijlage omleiden bij detectie:** **Omleiding inschakelen** <p> _Redirect_ <p> _RedirectAddress_|Uit en geen e-mailadres opgegeven. <p> `$true` <p> geen|Aan en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Aan en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Berichten omleiden naar een beveiligingsbeheerder voor controle.|
|**Pas de bovenstaande selectie toe als er malware wordt gescand op bijlagen of als er een fout optreedt.** <p> _ActionOnError_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|

## <a name="related-articles"></a>Aanverwante artikelen

- Zoekt u best practices voor Exchange regels voor **e-mailstroom (ook** wel transportregels genoemd)? Zie [Best practices for configuring mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Beheerders en gebruikers kunnen fout-positieven (goede e-mail die als slecht is gemarkeerd) en onwaar negatieven (slechte e-mail toegestaan) bij Microsoft indienen voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het instellen **van** uw [EOP-service](/exchange/standalone-eop/set-up-your-eop-service)en **het** configureren van [Microsoft Defender voor Office 365.](defender-for-office-365.md) Vergeet niet de nuttige aanwijzingen in 'Beschermen[tegen bedreigingen in](protect-against-threats.md)Office 365'.

- **Beveiligingslijnlijnen** voor Windows vindt u hier: Waar vind ik de beveiligingslijnlijnen? voor opties voor GPO/on-premises en Gebruik beveiligingslijnlijnen om Windows 10-apparaten te configureren [in Intune](/intune/protect/security-baselines) voor op Intune gebaseerde beveiliging. [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) Ten slotte is er een vergelijking beschikbaar tussen microsoft Defender voor eindpunten en Microsoft Intune-beveiligingslijnlijnen in Microsoft Defender voor eindpunt vergelijken met de [Windows Intune-beveiligingslijnlijnen.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
