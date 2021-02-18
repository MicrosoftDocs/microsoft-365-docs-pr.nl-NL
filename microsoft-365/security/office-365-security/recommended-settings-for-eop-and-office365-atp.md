---
title: Microsoft-aanbevelingen voor beveiligingsinstellingen van EOP en Defender voor Office 365
keywords: Beveiligingsaanbevelingen voor Office 365, Sender Policy Framework, Berichtrapportage en Conformance op basis van een domein, Geïdentificeerde e-mail van DomainKeys, stappen, hoe werkt het, beveiligingsbasislijnen, basislijnen voor EOP, basislijnen voor Defender voor Office 365, defender voor Office 365 instellen, EOP instellen, Defender configureren voor Office 365, EOP configureren, configuratie van beveiliging
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
description: Wat zijn de beste procedures voor Exchange Online Protection (EOP) en Defender voor Office 365-beveiligingsinstellingen? Wat zijn de huidige aanbevelingen voor standaardbeveiliging? Wat moet u gebruiken als u strikter wilt zijn? En welke extra's krijgt u als u ook Defender voor Office 365 gebruikt?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d635a28c41c9aceb0e3c499301156e53a1e2fa68
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289351"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Aanbevolen instellingen voor EOP- en Microsoft Defender voor Office 365-beveiliging

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Exchange Online Protection (EOP)** is de kern van de beveiliging van Microsoft 365-abonnementen en helpt voorkomen dat schadelijke e-mailberichten in de Postvak IN van uw werknemer worden bereikt. Maar met nieuwe, geavanceerdere aanvallen die elke dag worden ontwikkeld, zijn vaak verbeterde beveiligingen vereist. **Microsoft Defender voor Office 365** Plan 1 of Plan 2 bevatten extra functies die beheerders meer beveiliging, controle en onderzoek bieden.

Hoewel we beveiligingsbeheerders in staat stellen om hun beveiligingsinstellingen aan te passen, zijn er twee beveiligingsniveaus in EOP en Microsoft Defender voor Office 365 die we aanraden: **Standaard** en **Strikt.** De omgeving en behoeften van elke klant zijn verschillend, maar wij zijn van mening dat deze filterniveaus helpen voorkomen dat ongewenste e-mail in de meeste gevallen in het Postvak IN van uw werknemers terecht komt.

Zie Vooraf ingestelde beveiligingsbeleidsregels in EOP en [Microsoft Defender voor Office 365](preset-security-policies.md)als u de standaard- of strikte instellingen automatisch wilt toepassen op gebruikers.

> [!NOTE]
> De regel voor ongewenste e-mail moet zijn ingeschakeld in postvakken om te kunnen filteren. De functie is standaard ingeschakeld, maar u moet deze controleren als filteren niet lijkt te werken. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken in Office 365](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit artikel worden de standaardinstellingen beschreven en ook de aanbevolen standaard- en strikte instellingen om uw gebruikers te beschermen.

> [!TIP]
> Met de ORCA-module (Advanced Threat Protection Recommended Configuration Analyzer) voor PowerShell van Office 365 Advanced Threat Protection voor PowerShell kunt u (beheerders) de huidige waarden van deze instellingen vinden. Met name de **cmdlet Get-ORCAReport** genereert een evaluatie van anti-spam, anti-phishing en andere berichtinstellingen. U kunt de ORCA-module downloaden op <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Bescherming tegen spam, anti-malware en anti-phishing in EOP

Antispam, anti-malware en anti-phishing zijn EOP-functies die kunnen worden geconfigureerd door beheerders. De volgende standaard- of strikte configuraties worden aanbevolen.

### <a name="eop-anti-spam-policy-settings"></a>Instellingen voor antispambeleid van EOP

Zie Antispambeleid configureren [in Office 365](configure-your-spam-filter-policies.md)als u antispambeleid wilt maken en configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Actie bij het** detecteren van ongewenste e-mail <p> _SpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|**Actie bij het detecteren van ongewenste** e-mail met hoge betrouwbaarheid <p> _HighConfidenceSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Actie bij het detecteren van phishing-e-mail** <p> _PhishSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Zeer betrouwbaarheidsactie bij het detecteren van phishing-e-mail** <p> _HighConfidencePhishAction_|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Bulkactie voor e-maildetectie** <p> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|Drempelwaarde voor bulkmail <p> _BulkThreshold_|7|6|4|Zie bulksgewijs [klachtniveau in Office 365 voor meer informatie.](bulk-complaint-level-values.md)|
|Bewaarperiode in quarantaine <p> _QuarantineRetentionPeriod_|15 dagen|30 dagen|30 dagen||
|**Veiligheidstips** <p> _InlineSafetyTipsEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|Toegestane afzenders <p> _AllowedSenders_|Geen|Geen|Geen||
|Toegestane afzenderdomeinen <p> _AllowedSenderDomains_|Geen|Geen|Geen|Het toevoegen van domeinen aan de lijst met toegestane afzenders is een erg slecht idee. Kwaadwillende mensen kunnen u e-mailberichten sturen die anders zouden worden uitgefilterd. <p> Gebruik [spoof intelligence](learn-about-spoof-intelligence.md) in het beveiligings- & Compliancecentrum op de pagina met antispaminstellingen om alle afzenders te bekijken die e-mailadressen van afzenders in de e-maildomeinen van uw organisatie of **e-mailadressen** van afzenders in externe domeinen spoofing gebruiken.|
|Geblokkeerde afzenders <p> _BlockedSenders_|Geen|Geen|Geen||
|Geblokkeerde afzenderdomeinen <p> _BlockedSenderDomains_|Geen|Geen|Geen||
|**Spammeldingen voor eindgebruikers inschakelen** <p> _EnableEndUserSpamNotifications_|Uitgeschakeld <p> `$false`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|**Spammeldingen aan eindgebruikers verzenden elke (dagen)** <p> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen|3 dagen||
|**Spam ZAP** <p> _SpamZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`|Ingeschakeld <p> `$true`||
|_MarkAsSpamBulkMail_|Aan|Aan|Aan|Deze instelling is alleen beschikbaar in PowerShell.|
|

Er zijn verschillende andere instellingen voor geavanceerd spamfilter (ASF) in antispambeleid die worden afgeschaft. Buiten dit artikel wordt meer informatie over de tijdlijnen over de afschrijving van deze functies bekendgemaakt.

U wordt aangeraden deze ASF-instellingen **uit te** schakelen voor zowel **standaardniveaus** als **strikte** niveaus. Zie [asf-instellingen (Advanced Spam Filter) in Office 365](advanced-spam-filtering-asf-options.md)voor meer informatie over ASF-instellingen.

****

|Naam van beveiligingsfunctie|Opmerking|
|---|---|
|**Afbeeldingskoppelingen naar externe sites** _(IncreaseScoreWithImageLinks)_||
|**Numeriek IP-adres in URL** (_IncreaseScoreWithNumericIps_)||
|**UL redirect to other port** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL naar websites van .biz of .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Lege berichten** (_MarkAsSpamEmptyMessages_)||
|**JavaScript of VBScript in HTML** _(MarkAsSpamJavaScriptInHtml)_||
|**Frame- of IFrame-codes in HTML** _(MarkAsSpamFramesInHtml)_||
|**Objectlabels in HTML** _(MarkAsSpamObjectTagsInHtml)_||
|**Labels insluiten in HTML** _(MarkAsSpamEmbedTagsInHtml)_||
|**Formuliercodes in HTML** _(MarkAsSpamFormTagsInHtml)_||
|**Web bugs in HTML** _(MarkAsSpamWebBugsInHtml)_||
|**Lijst met gevoelige woorden toepassen** _(MarkAsSpamSensitiveWordList)_||
|**SPF-record: harde fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Filteren van voorwaardelijke afzender-id: mislukt** _(MarkAsSpamFromAddressAuthFail)_||
|**NDR-backscatter** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Instellingen voor uitgaand spambeleid voor EOP

Zie Uitgaande spamfilters configureren [in Office 365](configure-the-outbound-spam-policy.md)voor het maken en configureren van uitgaand spambeleid.

Zie Verzenden-limieten voor meer informatie over de standaardlimieten voor het verzenden van berichten in [de service.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Maximum aantal geadresseerden per gebruiker: Externe uurlimiet** <p> _RecipientLimitExternalPerHour_|0|500|400|De standaardwaarde 0 betekent dat de standaardinstellingen van de service worden gebruikt.|
|**Maximum aantal geadresseerden per gebruiker: interne uurlimiet** <p> _RecipientLimitInternalPerHour_|0|1000|800|De standaardwaarde 0 betekent dat de standaardinstellingen van de service worden gebruikt.|
|**Maximum aantal geadresseerden per gebruiker: daglimiet** <p> _RecipientLimitPerDay_|0|1000|800|De standaardwaarde 0 betekent dat de standaardinstellingen van de service worden gebruikt.|
|**Actie wanneer een gebruiker de limieten overschrijdt** <p> _ActionWhenThresholdReached_|**De gebruiker beperken tot het verzenden van e-mail tot de volgende dag** <p> `BlockUserForToday`|**De gebruiker beperken voor het verzenden van e-mail** <p> `BlockUser`|**De gebruiker beperken voor het verzenden van e-mail** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Instellingen voor antimalwarebeleid van EOP

Zie Antimalwarebeleid configureren [in Office 365](configure-anti-malware-policies.md)als u antimalwarebeleid wilt maken en configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Wilt u geadresseerden op de hoogte stellen als hun berichten in quarantaine zijn geplaatst?** <p> _Actie_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Nee <p> _DeleteMessage_|Als malware in een e-mailbijlage wordt gedetecteerd, wordt het bericht in quarantaine geplaatst en kan het alleen worden vrijgegeven door een beheerder.|
|**Filter voor veelvoorkomende typen bijlagen** <p> _EnableFileFilter_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Hiermee worden berichten die uitvoerbare bijlagen bevatten, in quarantaine geplaatst op basis van bestandstype, ongeacht de inhoud van de bijlage.|
|**Malware Zero-hour Auto Purge** <p> _ZapEnabled_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Interne afzenders op** de hoogte stellen van het niet-bezorgdbericht <p> _EnableInternalSenderNotifications_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|**Externe afzenders op de** hoogte stellen van het niet-bezorgdbericht <p> _EnableExternalSenderNotifications_|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`|Uitgeschakeld <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Standaardinstellingen voor anti-phishingbeleid van EOP

Zie Spoof-instellingen voor meer informatie [over deze instellingen.](set-up-anti-phishing-policies.md#spoof-settings) Zie [Anti-phishingbeleid configureren in EOP](configure-anti-phishing-policies-eop.md)om deze instellingen te configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Beveiliging tegen spoofing inschakelen** <p> _EnableSpoofIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Niet-geauteerde afzender inschakelen** <p> _EnableUauhenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op geblokkeerde afzenders in [spoof intelligence.](learn-about-spoof-intelligence.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender voor Office 365-beveiliging

Extra beveiligingsvoordelen worden mogelijk met een Microsoft Defender voor Office 365-abonnement. Voor het laatste nieuws en informatie kunt u de nieuwe functies [van Defender voor Office 365 bekijken.](whats-new-in-office-365-atp.md)

> [!IMPORTANT]
>
> - Het standaardbeleid tegen phishing in Microsoft Defender voor Office 365 biedt [spoof-beveiliging](set-up-anti-phishing-policies.md#spoof-settings) en postvakinformatie voor alle geadresseerden. De andere beschikbare functies voor [](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) [imitatiebeveiliging](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) en geavanceerde instellingen worden echter niet geconfigureerd of ingeschakeld in het standaardbeleid. Als u alle beveiligingsfuncties wilt inschakelen, wijzigt u het standaardbeleid tegen phishing of maakt u aanvullende anti-phishingbeleidsregels.
>
> - Er zijn geen standaardbeleidsregels voor veilige koppelingen of veilige bijlagen die automatisch alle geadresseerden in de organisatie beveiligen. Om de beveiliging te krijgen, moet u ten minste één beleid voor veilige koppelingen en veilige bijlagen maken.
>
> - [Veilige bijlagen voor de beveiliging van SharePoint, OneDrive](atp-for-spo-odb-and-teams.md) en Microsoft Teams en de beveiliging van veilige documenten zijn niet afhankelijk van het beleid voor veilige koppelingen. [](safe-docs.md)

Als uw abonnement Microsoft Defender voor Office 365 omvat of als u Defender voor Office 365 als een invoegabonnement hebt gekocht, stelt u de volgende standaard- of strikte configuraties in.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Anti-phishingbeleidsinstellingen in Microsoft Defender voor Office 365

EOP-klanten krijgen standaard anti-phishing zoals eerder beschreven, maar Microsoft Defender voor Office 365 bevat meer functies en controle om aanvallen te voorkomen, detecteren en herstellen. Zie Anti-phishingbeleid configureren in Defender voor [Office 365](configure-atp-anti-phishing-policies.md)als u dit beleid wilt maken en configureren.

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie [Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor meer informatie over deze instellingen. Zie Anti-phishingbeleid configureren in Defender voor [Office 365 om](configure-atp-anti-phishing-policies.md)deze instellingen te configureren.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|Beveiligde gebruikers: **Gebruikers toevoegen om te beveiligen** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of users\>|Aan <p> `$true` <p> \<list of users\>|Afhankelijk van uw organisatie, wordt u aangeraden gebruikers (afzenders van berichten) toe te voegen aan belangrijke rollen. Intern beveiligde afzenders zijn mogelijk uw CEO, CFO en andere senior leidinggevenden. Externe, beveiligde afzenders kunnen raadsleden of uw raad van bestuur omvatten.|
|Beveiligde domeinen: automatisch de domeinen opnemen **die ik bezit** <p> _EnableOrganizationDomainsProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|Beveiligde domeinen: **aangepaste domeinen opnemen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Uit <p> `$false` <p> geen|Aan <p> `$true` <p> \<list of domains\>|Aan <p> `$true` <p> \<list of domains\>|Afhankelijk van uw organisatie, wordt u aangeraden domeinen (afzenderdomeinen) toe te voegen die u niet hebt, maar die u vaak gebruikt.|
|Beveiligde gebruikers: **Als e-mail wordt verzonden door een gemitmiteerde gebruiker** <p> _TargetedUserProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|Beveiligde domeinen: **Als e-mail wordt verzonden door een gemitmiteerd domein** <p> _TargetedDomainProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Tip voor imiteerde gebruikers** <p> _EnableSimilarUsersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip voor gemitmiteerde domeinen** <p> _EnableSimilarDomainsSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Tip voor ongebruikelijke tekens tonen** <p> _EnableUnusualCharactersSafetyTips_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Postvakinformatie inschakelen?** <p> _EnableMailboxIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Beveiliging van imitatie op basis van postvakintelligentie inschakelen?** <p> _EnableMailboxIntelligenceProtection_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Als e-mail wordt verzonden door een gemitmiteerde gebruiker die is beveiligd door postvakinformatie** <p> _MailboxIntelligenceProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Vertrouwde afzenders** <p> _ExcludedSenders_|Geen|Geen|Geen|Afhankelijk van uw organisatie, wordt u aangeraden gebruikers toe te voegen die ten onrechte als phishing zijn gemarkeerd vanwege imitatie en niet door andere filters.|
|**Vertrouwde domeinen** <p> _ExcludedDomains_|Geen|Geen|Geen|Afhankelijk van uw organisatie, wordt u aangeraden domeinen toe te voegen die ten onrechte als phishing zijn gemarkeerd vanwege imitatie en niet door andere filters.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Spoof-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Houd er rekening mee dat dit dezelfde instellingen zijn die beschikbaar zijn in de instellingen voor [antispambeleid in EOP.](#eop-anti-spam-policy-settings)

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|---|---|---|---|
|**Beveiliging tegen spoofing inschakelen** <p> _EnableSpoofIntelligence_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|**Niet-geauteerde afzender inschakelen** <p> _EnableUauhenticatedSender_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Hiermee voegt u een vraagteken (?) toe aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie Spoof-instellingen [in anti-phishingbeleid](set-up-anti-phishing-policies.md)voor meer informatie.|
|**Als e-mail wordt verzonden door iemand die uw domein niet mag vervalsen** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen voor ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op geblokkeerde afzenders in [spoof intelligence.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie Geavanceerde drempelwaarden voor [phishing in anti-phishingbeleid in Microsoft Defender voor Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor meer informatie over deze instelling. Zie Anti-phishingbeleid configureren in Defender voor [Office 365 om deze instelling te configureren.](configure-atp-anti-phishing-policies.md)

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Geavanceerde drempelwaarden voor phishing** <p> _PhishThresholdLevel_|**1 - Standaard** <p> `1`|**2 - Aggressive** <p> `2`|**3 - Meer agressief** <p> `3`||
|

### <a name="safe-links-settings"></a>Instellingen voor veilige koppelingen

Veilige koppelingen in Defender voor Office 365 omvatten globale instellingen die van toepassing zijn op alle gebruikers die zijn opgenomen in het actieve beleid voor veilige koppelingen, en instellingen die specifiek zijn voor elk beleid voor veilige koppelingen. Zie Veilige koppelingen [in Defender voor Office 365](atp-safe-links.md)voor meer informatie.

#### <a name="global-settings-for-safe-links"></a>Algemene instellingen voor veilige koppelingen

Zie Algemene instellingen configureren voor veilige koppelingen in Defender voor [Office 365](configure-global-settings-for-safe-links.md)als u deze instellingen wilt configureren.

In PowerShell gebruikt u de [set-AtpPolicyForO365-cmdlet](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Veilige koppelingen gebruiken in: Office 365-toepassingen** <p> _EnableSafeLinksForO365Clients_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Gebruik veilige koppelingen in ondersteunde Office 365-desktop- en mobiele apps (iOS en Android). Zie instellingen voor veilige koppelingen [voor Office 365-apps](atp-safe-links.md#safe-links-settings-for-office-365-apps)voor meer informatie.|
|**Niet bijhouden wanneer gebruikers op veilige koppelingen klikken** <p> _TrackClicks_|Aan <p> `$false`|Uit <p> `$true`|Uit <p> `$true`|Als u deze instelling uit schakelen _(trackClicks in stellen_ op) houdt u `$true` klikken van gebruikers bij in ondersteunde Office 365-apps.|
|**Gebruikers niet door veilige koppelingen laten klikken naar de oorspronkelijke URL** <p> _AllowClickThrough_|Aan <p> `$false`|Aan <p> `$false`|Aan <p> `$false`|Als u deze instelling (door _AllowClickThrough_ in te stellen) in te stellen, wordt niet doorklikken naar de oorspronkelijke URL in ondersteunde `$false` Office 365-apps.|
|

#### <a name="safe-links-policy-settings"></a>Beleidsinstellingen voor veilige koppelingen

Zie Beleidsregels voor veilige koppelingen instellen [in Microsoft Defender voor Office 365](set-up-atp-safe-links-policies.md)om deze instellingen te configureren.

In PowerShell gebruikt u de cmdlets [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) en [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder is beschreven, is er geen standaardbeleid voor veilige koppelingen. De waarden in de kolom Standaard zijn de standaardwaarden in het nieuwe beleid voor veilige koppelingen dat u maakt.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**De actie selecteren voor onbekende, potentieel schadelijke URL's in berichten** <p> _IsEnabled_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**De actie selecteren voor onbekende of mogelijk schadelijke URL's in Microsoft Teams** <p> _EnableSafeLinksForTeams_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Real-time URL's scannen op verdachte koppelingen en koppelingen die naar bestanden wijzen** <p> _ScanUrls_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Wacht totdat het scannen van de URL is voltooid voordat het bericht wordt weergegeven** <p> _DeliverMessageAfterScan_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden** <p> _EnableForInternalSenders_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Klikken van gebruikers niet bijhouden** <p> _DoNotTrackUserClicks_|Uit <p> `$false`|Uit <p> `$false`|Uit <p> `$false`|Als u deze instelling uit schakelen _(instelling DoNotTrackUserClicks_ `$false` op) worden klikken van gebruikers bij houdt.|
|**Gebruikers niet toestaan door te klikken naar de oorspronkelijke URL** <p> _DoNotAllowClickThrough_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Als u deze instelling _(waarin DoNotAllowClickThrough_ is opgegeven) in te stellen, wordt `$true` niet doorklikken naar de oorspronkelijke URL.|
|

### <a name="safe-attachments-settings"></a>Instellingen voor veilige bijlagen

Veilige bijlagen in Microsoft Defender voor Office 365 bevatten globale instellingen die geen relatie hebben met het beleid voor veilige bijlagen en instellingen die specifiek zijn voor elk beleid voor veilige koppelingen. Zie Veilige bijlagen [in Defender voor Office 365](atp-safe-attachments.md)voor meer informatie.

#### <a name="global-settings-for-safe-attachments"></a>Algemene instellingen voor veilige bijlagen

Zie Veilige bijlagen voor [SharePoint, OneDrive en Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) en veilige documenten [in Microsoft 365 E5](safe-docs.md)in om deze instellingen te configureren.

In PowerShell gebruikt u de [set-AtpPolicyForO365-cmdlet](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) voor deze instellingen.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Aan <p> `$true`|Aan <p> `$true`||
|**Veilige documenten voor Office-clients in te stellen** <p> _EnableSafeDocs_|Aan <p> `$true`|Aan <p> `$true`|Deze instelling is alleen beschikbaar voor microsoft 365 E5- of Microsoft 365 E5-beveiligingslicenties. Zie Veilige documenten [in Microsoft Defender voor Office 365](safe-docs.md)voor meer informatie.|
|**Toestaan dat personen door de beveiligde weergave klikken, zelfs als veilige documenten het bestand als schadelijk hebben geïdentificeerd** <p> _AllowSafeDocsOpen_|Uit <p> `$false`|Uit <p> `$false`|Deze instelling is gerelateerd aan Veilige documenten.|
|

#### <a name="safe-attachments-policy-settings"></a>Beleidsinstellingen voor veilige bijlagen

Zie Beleidsregels voor veilige bijlagen instellen in Defender voor [Office 365](set-up-atp-safe-attachments-policies.md)om deze instellingen te configureren.

In PowerShell gebruikt u de cmdlets [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) and [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) voor deze instellingen.

> [!NOTE]
> Zoals eerder is beschreven, is er geen standaardbeleid voor veilige bijlagen. De waarden in de kolom Standaard zijn de standaardwaarden in het nieuwe beleid voor veilige bijlagen dat u maakt.

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Onbekende malwarereactie op veilige bijlagen** <p> _Actie_|Blokkeren <p> `Block`|Blokkeren <p> `Block`|Blokkeren <p> `Block`||
|**Bijlage omleiden bij detectie** : **omleiding inschakelen** <p> _Omleiden_ <p> _RedirectAddress_|Uitgeschakeld en geen e-mailadres opgegeven. <p> `$true` <p> geen|Aan en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Aan en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Berichten omleiden naar een beveiligingsbeheerder voor revisie.|
|**Pas de bovenstaande selectie toe als er malware wordt gescand op bijlagen of als er een fout optreedt.** <p> _ActionOnError_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`||
|

## <a name="related-articles"></a>Verwante artikelen

- Bent u op zoek naar best practices voor **Exchange-regels voor de e-mailstroom (ook wel transportregels genoemd)?** Zie [de best practices voor het configureren van regels voor de e-mailstroom in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- Beheerders en gebruikers kunnen fout-positieven (goede e-mail gemarkeerd als slecht) en fout-negatieven (niet-toegestane e-mail) naar Microsoft verzenden voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor  informatie over het instellen van uw [EOP-service](set-up-your-eop-service.md)en het **configureren** van [Microsoft Defender voor Office 365.](office-365-atp.md) Vergeet niet de handige aanwijzingen in['Protect Against Threats in Office 365'](protect-against-threats.md)(Beveiligen tegen bedreigingen in Office 365).

- U vindt hier basislijnen voor beveiliging voor **Windows:** Waar kan ik de basislijnen voor beveiliging [krijgen?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) voor opties voor het GPO/on-premises en gebruik basislijnen voor beveiliging om [Windows 10-apparaten te](https://docs.microsoft.com/intune/protect/security-baselines) configureren in Intune voor intune-beveiliging. Ten slotte is er een vergelijking beschikbaar tussen de beveiligingsbasislijnen van Microsoft Defender voor Eindpunt en Microsoft Intune in Microsoft Defender voor Eindpunt vergelijken met de [beveiligingsbasislijnen van Windows Intune.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
