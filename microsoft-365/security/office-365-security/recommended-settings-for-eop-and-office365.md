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
ms.openlocfilehash: 67d1b133e0d0ac7e622ed0bfdbfd17214608d77a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083546"
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
> De regel ongewenste e-mail moet zijn ingeschakeld in postvakken om te kunnen filteren op de juiste manier. Deze functie is standaard ingeschakeld, maar u moet controleren of filteren niet werkt. Zie [Instellingen voor ongewenste e-mail configureren voor Exchange Online-postvakken](configure-junk-email-settings-on-exo-mailboxes.md) voor meer informatie.

In dit artikel worden de standaardinstellingen beschreven, en ook de aanbevolen standaard- en strikte instellingen om uw gebruikers te beschermen. De tabellen bevatten de instellingen in de Microsoft 365 Defender portal en PowerShell (Exchange Online PowerShell of zelfstandige Exchange Online Protection PowerShell voor organisaties zonder Exchange Online postvakken).

> [!TIP]
> De Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) module voor PowerShell kan u (beheerders) helpen de huidige waarden van deze instellingen te vinden. De **get-ORCAReport-cmdlet** genereert met name een beoordeling van antispam, anti-phishing en andere instellingen voor berichthygiëne. U kunt de ORCA-module downloaden op <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Antispam, anti-malware en anti-phishingbeveiliging in EOP

Antispam, anti-malware en anti-phishing zijn EOP-functies die kunnen worden geconfigureerd door beheerders. We raden u de volgende standaard- of strikte configuraties aan.

### <a name="eop-anti-spam-policy-settings"></a>EOP-antispambeleidsinstellingen

Zie Antispambeleid configureren in EOP als u antispambeleid wilt maken en [configureren.](configure-your-spam-filter-policies.md)

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Drempelwaarde voor bulksgewijs & spam**||||
|**Drempelwaarde voor bulksgewijs e-mail** <p> _BulkThreshold_|7|6|4|Zie Bulk [complaint level (BCL) in EOP voor meer informatie.](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Deze instelling is alleen beschikbaar in PowerShell.|
|**Instellingen voor spamscores** verhogen|Uit|Uit|Uit|Al deze instellingen maken deel uit van het Advanced Spam Filter (ASF). Zie de sectie [ASF-instellingen in antispambeleid in](#asf-settings-in-anti-spam-policies) dit artikel voor meer informatie.|
|**Markeren als spam-instellingen**|Uit|Uit|Uit|De meeste van deze instellingen maken deel uit van ASF. Zie de sectie [ASF-instellingen in antispambeleid in](#asf-settings-in-anti-spam-policies) dit artikel voor meer informatie.|
|**Bevat specifieke talen** <p> _LanguageBlockList inschakelen_ <p> _LanguageBlockList_|**Uit** <p> `$false` <p> Leeg|**Uit** <p> `$false` <p> Leeg|**Uit** <p> `$false` <p> Leeg|We hebben geen specifieke aanbeveling voor deze instelling. U kunt berichten in specifieke talen blokkeren op basis van uw zakelijke behoeften.|
|**Uit deze landen** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**Uit** <p> `$false` <p> Leeg|**Uit** <p> `$false` <p> Leeg|**Uit** <p> `$false` <p> Leeg|We hebben geen specifieke aanbeveling voor deze instelling. U kunt berichten uit specifieke landen blokkeren op basis van uw zakelijke behoeften.|
|**Testmodus** (_TestModeAction_)|**Geen**|**Geen**|**Geen**|Deze instelling maakt deel uit van ASF. Zie de sectie [ASF-instellingen in antispambeleid in](#asf-settings-in-anti-spam-policies) dit artikel voor meer informatie.|
|**Acties**|||||
|**Actie voor spamdetectie** <p> _SpamActie_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|**Actie voor het opsporen van spam** met veel vertrouwen <p> _HighConfidenceSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Phishingdetectieactie** <p> _PhishSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Phishingdetectieactie met** hoog vertrouwen <p> _HighConfidencePhishAction_|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`|**Quarantainebericht** <p> `Quarantine`||
|**Bulkdetectieactie** <p> _BulkSpamAction_|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Bericht verplaatsen naar map Ongewenste e-mail** <p> `MoveToJmf`|**Quarantainebericht** <p> `Quarantine`||
|**Spam in quarantaine bewaren voor deze dagen** <p> _QuarantineRetentionPeriod_|15 dagen|30 dagen|30 dagen||
|**Tips voor spamveiligheid inschakelen** <p> _InlineSafetyTipsEnabled_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|Automatische purge (ZAP) voor phishingberichten inschakelen <p> _PhishZapEnabled_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|ZAP inschakelen voor spamberichten <p> _SpamZapEnabled_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Spammeldingen voor eindgebruikers inschakelen** <p> _EnableEndUserSpamNotifications_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Spammeldingen voor eindgebruikers elke (dagen) verzenden** <p> _EndUserSpamNotificationFrequency_|3 dagen|3 dagen|3 dagen||
|**Lijst & blokkeren toestaan**|||||
|Toegestane afzenders <p> _AllowedSenders_|Geen|Geen|Geen||
|Toegestane afzenderdomeinen <p> _AllowedSenderDomains_|Geen|Geen|Geen|Het toevoegen van domeinen aan de lijst met toegestane afzenders is een heel slecht idee. Aanvallers kunnen u e-mail sturen die anders zou worden gefilterd. <p> Gebruik het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) en de [Tenant Allow/Block List](tenant-allow-block-list.md) om alle afzenders te controleren die e-mailadressen van afzenders spoofen in de e-maildomeinen van uw organisatie of e-mailadressen van afzenders voor spoofing in externe domeinen.|
|Geblokkeerde afzenders <p> _Geblokkeerde senders_|Geen|Geen|Geen||
|Geblokkeerde afzenderdomeinen <p> _BlockedSenderDomains_|Geen|Geen|Geen||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>ASF-instellingen in antispambeleid

Er zijn veel geavanceerde instellingen voor spamfilter (ASF) in antispambeleid die momenteel worden afgeschaft. Meer informatie over de tijdlijnen voor de afschrijving van deze functies wordt buiten dit artikel gecommuniceerd.

Het is raadzaam om de volgende ASF-instellingen uit te **laten voor** zowel **standaard-** als **strikte** niveaus. Zie [AsF-instellingen (Advanced Spam Filter) in EOP voor meer informatie over ASF-instellingen.](advanced-spam-filtering-asf-options.md)

<br>

****

|Naam van beveiligingsfunctie|Opmerking|
|---|---|
|**Afbeeldingskoppelingen naar externe sites** (_IncreaseScoreWithImageLinks_)||
|**Numeriek IP-adres in URL** (_IncreaseScoreWithNumericIps_)||
|**URL omleiden naar andere poort** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Koppelingen naar .biz- of .info-websites** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Lege berichten** (_MarkAsSpamEmptyMessages_)||
|**Tags insluiten in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript of VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Formulierlabels in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Frame- of iframetags in HTML** (_MarkAsSpamFramesInHtml_)||
|**Web bugs in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Objectlabels in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Gevoelige woorden** (_MarkAsSpamSensitiveWordList_)||
|**SPF-record: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Sender ID filtering hard fail** _(MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**Testmodus** (_TestModeAction_)|Voor ASF-instellingen die **Test** ondersteunen als een actie, kunt u de actie in de testmodus configureren op **Geen,** **Standaard X-koptekst** toevoegen of **BCC-bericht** verzenden ( `None` , of `AddXHeader` `BccMessage` ). Zie [ASF-instellingen inschakelen, uitschakelen of testen](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)voor meer informatie.|
|

#### <a name="eop-outbound-spam-policy-settings"></a>EOP-instellingen voor uitgaand spambeleid

Zie Uitgaand spamfilters configureren in EOP als u uitgaand spambeleid wilt maken en [configureren.](configure-the-outbound-spam-policy.md)

Zie Limieten verzenden voor meer informatie over de standaardlimieten voor verzenden in [de](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)service.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Een externe berichtlimiet instellen** <p> _RecipientLimitExternalPerHour_|0|500|400|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Een interne berichtlimiet instellen** <p> _RecipientLimitInternalPerHour_|0|1000|800|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Een dagelijkse berichtlimiet instellen** <p> _RecipientLimitPerDay_|0|1000|800|De standaardwaarde 0 betekent dat u de standaardinstellingen van de service gebruikt.|
|**Beperking die is opgelegd aan gebruikers die de berichtlimiet bereiken** <p> _ActionWhenThresholdReached_|**De gebruiker beperken van het verzenden van e-mail tot de volgende dag** <p> `BlockUserForToday`|**De gebruiker beperken van het verzenden van e-mail** <p> `BlockUser`|**De gebruiker beperken van het verzenden van e-mail** <p> `BlockUser`||
|**Regels voor automatisch doorsturen** <p> _AutoForwardingMode_|**Automatisch - Systeemgestuurd** <p> `Automatic`|**Automatisch - Systeemgestuurd** <p> `Automatic`|**Automatisch - Systeemgestuurd** <p> `Automatic`|
|**Een kopie van uitgaande berichten verzenden die deze limieten overschrijden voor deze gebruikers en groepen** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|Niet geselecteerd <p> `$false` <p> Leeg|Niet geselecteerd <p> `$false` <p> Leeg|Niet geselecteerd <p> `$false` <p> Leeg|We hebben geen specifieke aanbeveling voor deze instelling. <p> Deze instelling werkt alleen in het standaardbeleid voor uitgaande spam. Het werkt niet in aangepaste uitgaande spambeleidsregels die u maakt.|
|**Informeer deze gebruikers en groepen als een afzender is geblokkeerd vanwege het verzenden van uitgaande spam** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|Niet geselecteerd <p> `$false` <p> Leeg|Niet geselecteerd <p> `$false` <p> Leeg|Niet geselecteerd <p> `$false` <p> Leeg|Het [standaardwaarschuwingsbeleid](../../compliance/alert-policies.md) met de naam Gebruiker die geen e-mail mag verzenden, verzendt al e-mailmeldingen naar leden van de **groep TenantAdmins** **(Globale** beheerders) wanneer gebruikers worden geblokkeerd vanwege het overschrijden van de limieten in het beleid.  **We raden u ten zeerste aan het waarschuwingsbeleid** te gebruiken in plaats van deze instelling in het uitgaande spambeleid om beheerders en andere gebruikers op de hoogte te stellen. Zie De [waarschuwingsinstellingen voor](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)beperkte gebruikers controleren voor instructies.|
|

### <a name="eop-anti-malware-policy-settings"></a>EOP-beleid voor anti-malwarebeleid

Zie [Anti-malwarebeleid](configure-anti-malware-policies.md)configureren in EOP als u anti-malwarebeleid wilt maken en configureren.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Beveiligingsinstellingen**|||||
|**Het algemene bijlagefilter inschakelen** <p> _EnableFileFilter_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Met deze instelling worden berichten in quarantaine geplaatst die uitvoerbare bijlagen bevatten op basis van bestandstype, ongeacht de inhoud van de bijlage.|
|**Automatische purge van nul uur inschakelen voor malware** <p> _ZapEnabled_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Meldingen van geadresseerden**|||||
|**Geadresseerden op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _Actie_|Niet geselecteerd <p> _DeleteMessage_|Niet geselecteerd <p> _DeleteMessage_|Niet geselecteerd <p> _DeleteMessage_|Als malware wordt gedetecteerd in een e-mailbijlage, wordt het bericht in quarantaine geplaatst en kan het alleen worden uitgebracht door een beheerder.|
|**Afzendermeldingen**|||||
|**Interne afzenders op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _EnableInternalSenderNotifications_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`||
|**Externe afzenders op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware** <p> _ExternalSenderNotifications inschakelen_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`||
|**Beheerdersmeldingen**|||||
|**Een beheerder op de hoogte stellen van niet-bezorgde berichten van interne afzenders** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|We hebben geen specifieke aanbeveling voor deze instelling.|
|**Een beheerder op de hoogte stellen van niet-bezorgde berichten van externe afzenders** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|We hebben geen specifieke aanbeveling voor deze instelling.|
|**Meldingen aanpassen**||||We hebben geen specifieke aanbevelingen voor deze instellingen.|
|**Aangepaste meldingstekst gebruiken** <p> _Aangepastenotificaties_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`||
|**Van naam** <p> _CustomFromName_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|**Van adres** <p> _CustomFromAddress_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|**Meldingen aanpassen voor berichten van interne afzenders**||||Deze instellingen worden alleen gebruikt als Interne **afzenders** op de hoogte stellen wanneer berichten in quarantaine worden geplaatst als malware of Een beheerder informeren over **niet-bezorgde** berichten van interne afzenders is geselecteerd.|
|**Onderwerp** <p> _CustomInternalSubject_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|**Bericht** <p> _CustomInternalBody_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|**Meldingen aanpassen voor berichten van externe afzenders**||||Deze instellingen worden alleen gebruikt als externe **afzenders** op de hoogte worden gesteld wanneer berichten in quarantaine worden geplaatst als malware of Een beheerder informeren over **niet-bezorgde** berichten van externe afzenders is geselecteerd.|
|**Onderwerp** <p> _CustomExternalSubject_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|**Bericht** <p> _CustomExternalBody_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>EOP-anti-phishingbeleidsinstellingen

Zie Spoof-instellingen voor [meer informatie over deze instellingen.](set-up-anti-phishing-policies.md#spoof-settings) Zie [Anti-phishingbeleid](configure-anti-phishing-policies-eop.md)configureren in EOP om deze instellingen te configureren.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Phishing-drempelwaarde & beveiliging**|||||
|**Spoof intelligence inschakelen** <p> _EnableSpoofIntelligence_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Acties**|||||
|**Als bericht wordt gedetecteerd als spoof** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op vervalste afzenders die automatisch zijn geblokkeerd, zoals wordt weergegeven in het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) of handmatig is geblokkeerd in de [lijst Tenant Allow/Block](tenant-allow-block-list.md).|
|**Eerste contactpersoon veiligheidstip** <p> _EnableFirstContactSafetyTips_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Zie Eerste contactpersoon voor meer [informatie veiligheidstip.](set-up-anti-phishing-policies.md#first-contact-safety-tip)|
|**Toon (?) voor niet-genauteerde afzenders voor spoofing** <p> _EnableUnauthenticatedSender_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Hiermee wordt een vraagteken (?) toegevoegd aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Niet-genauteerde afzender voor meer informatie.](set-up-anti-phishing-policies.md#unauthenticated-sender)|
|**Tag 'via' tonen** <p> _EnableViaTag_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Hiermee voegt u een via-tag (chris@contoso.com via fabrikam.com) toe aan het Van-adres als deze verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.** <p> Zie [Niet-genauteerde afzender voor meer informatie.](set-up-anti-phishing-policies.md#unauthenticated-sender)|
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

EOP-klanten krijgen standaard anti-phishing zoals eerder beschreven, maar Defender voor Office 365 bevat meer functies en controle om aanvallen te voorkomen, te detecteren en te herstellen. Zie [Anti-phishingbeleid](configure-mdo-anti-phishing-policies.md)configureren in Defender voor Office 365.

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Geavanceerde instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie Advanced [phishing thresholds in anti-phishing policies in Microsoft Defender](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)for Office 365 voor meer informatie over deze instelling. Zie [Anti-phishingbeleid](configure-mdo-anti-phishing-policies.md)configureren in Defender voor Office 365.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Drempelwaarde voor phishing-e-mail** <p> _PhishThresholdLevel_|**1 - Standaard** <p> `1`|**2 - Agressief** <p> `2`|**3 - Agressiever** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Imitatie-instellingen in anti-phishingbeleid in Microsoft Defender voor Office 365

Zie Instellingen voor imitatie in [anti-phishingbeleid in Microsoft Defender](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)voor Office 365. Zie [Anti-phishingbeleid](configure-mdo-anti-phishing-policies.md)configureren in Defender voor Office 365.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Phishing-drempelwaarde & beveiliging**|||||
|**Gebruikers inschakelen om te beveiligen** (gebruikersbeveiliging die wordt nagebootsd)<p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Niet geselecteerd <p> `$false` <p> geen|Geselecteerd <p> `$true` <p> \<list of users\>|Geselecteerd <p> `$true` <p> \<list of users\>|Het is raadzaam gebruikers (afzenders van berichten) toe te voegen aan belangrijke rollen. Intern kunnen beveiligde afzenders uw CEO, CFO en andere senior leaders zijn. Externe, beveiligde afzenders kunnen leden van de raad of uw raad van bestuur bevatten.|
|**Domeinen beveiligen** (nagebootsd domeinbeveiliging) inschakelen|Niet geselecteerd|Geselecteerd|Geselecteerd||
|**Domeinen opnemen die ik bezit** <p> _EnableOrganizationDomainsProtection_|Uit <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Aangepaste domeinen opnemen** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Uit <p> `$false` <p> geen|Geselecteerd <p> `$true` <p> \<list of domains\>|Geselecteerd <p> `$true` <p> \<list of domains\>|We raden u aan domeinen (afzenderdomeinen) toe te voegen die niet van u zijn, maar die u vaak gebruikt.|
|**Vertrouwde afzenders en domeinen toevoegen** <p> _ExcludedSenders_ <p> _ExcludedDomains_|Geen|Geen|Geen|Afhankelijk van uw organisatie wordt u aangeraden afzenders of domeinen toe te voegen die onjuist zijn geïdentificeerd als imitatiepogingen.|
|**Postvakintelligentie inschakelen** <p> _EnableMailboxIntelligence_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Intelligentie inschakelen voor imitatiebeveiliging** <p> _EnableMailboxIntelligenceProtection_|Uit <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Met deze instelling kunt u de opgegeven actie voor imitatiedetecties door postvakinformatie instellen.|
|**Acties**|||||
|**Als bericht wordt gedetecteerd als een nagebootsde gebruiker** <p> _TargetedUserProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Als bericht wordt gedetecteerd als een nagebootsd domein** <p> _TargetedDomainProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Als postvakinformatie gebruikers detecteert en nabootst** <p> _MailboxIntelligenceProtectionAction_|**Geen actie toepassen** <p> `NoAction`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`||
|**Gebruikers imiteren veiligheidstip** <p> _EnableSimilarUsersSafetyTips_|Uit <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Domein-imitatie veiligheidstip** <p> _EnableSimilarDomainsSafetyTips_|Uit <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Ongebruikelijke tekens voor gebruikers imiteren veiligheidstip** <p> _EnableUnusualCharactersSafetyTips_|Uit <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>EOP anti-phishingbeleidsinstellingen in Microsoft Defender voor Office 365

Dit zijn dezelfde instellingen die beschikbaar zijn in de instellingen voor [antispambeleid in EOP.](#eop-anti-spam-policy-settings)

De spoofinstellingen zijn onderling gerelateerd, maar de instelling Eerste **contactpersoon** veiligheidstip is niet afhankelijk van spoofinstellingen.

<br>

****

|Naam van beveiligingsfunctie|Standaard|Standard|Strikt|Opmerking|
|---|:---:|:---:|:---:|---|
|**Phishing-drempelwaarde & beveiliging**|||||
|**Spoof intelligence inschakelen** <p> _EnableSpoofIntelligence_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Acties**|||||
|**Als bericht wordt gedetecteerd als spoof** <p> _AuthenticationFailAction_|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Bericht verplaatsen naar de mappen ongewenste e-mail van de geadresseerden** <p> `MoveToJmf`|**Het bericht in quarantaine plaatsen** <p> `Quarantine`|Deze instelling is van toepassing op vervalste afzenders die automatisch zijn geblokkeerd, zoals wordt weergegeven in het inzicht in spoof [intelligence](learn-about-spoof-intelligence.md) of handmatig is geblokkeerd in de [lijst Tenant Allow/Block](tenant-allow-block-list.md).|
|**Eerste contactpersoon veiligheidstip** <p> _EnableFirstContactSafetyTips_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Zie Eerste contactpersoon voor meer [informatie veiligheidstip.](set-up-anti-phishing-policies.md#first-contact-safety-tip)|
|**Toon (?) voor niet-genauteerde afzenders voor spoofing** <p> _EnableUnauthenticatedSender_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Hiermee wordt een vraagteken (?) toegevoegd aan de foto van de afzender in Outlook voor niet-geïdentificeerde vervalste afzenders. Zie [Niet-genauteerde afzender voor meer informatie.](set-up-anti-phishing-policies.md#unauthenticated-sender)|
|**Tag 'via' tonen** <p> _EnableViaTag_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Hiermee voegt u een via-tag (chris@contoso.com via fabrikam.com) toe aan het Van-adres als deze verschilt van het domein in de DKIM-handtekening of het **MAIL FROM-adres.** <p> Zie [Niet-genauteerde afzender voor meer informatie.](set-up-anti-phishing-policies.md#unauthenticated-sender)|
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
|**Defender voor Office 365 inschakelen voor SharePoint, OneDrive en Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`||
|**Documenten in Safe voor Office-clients** <p> _EnableSafeDocs_|Uit <p> `$false`|Aan <p> `$true`|Aan <p> `$true`|Deze functie is alleen beschikbaar en zinvol met Microsoft 365 E5 of Microsoft 365 E5 Security licenties. Zie voor meer informatie [Safe Documenten in Microsoft Defender voor Office 365.](safe-docs.md)|
|**Toestaan dat personen door de beveiligde weergave kunnen klikken, zelfs Safe documenten het bestand als schadelijk hebben geïdentificeerd** <p> _AllowSafeDocsOpen_|Uit <p> `$false`|Uit <p> `$false`|Uit <p> `$false`|Deze instelling is gerelateerd aan Safe Documenten.|
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
|**Safe Attachments unknown malware response** <p> _Actie_|**Uit** <p> `Block`|**Blokkeren** <p> `Block`|**Blokkeren** <p> `Block`||
|**Bijlage omleiden met gedetecteerde bijlagen** : **Omleiding inschakelen** <p> _Redirect_ <p> _RedirectAddress_|Niet geselecteerd en geen e-mailadres opgegeven. <p> `$true` <p> geen|Selecteer en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Selecteer en geef een e-mailadres op. <p> `$true` <p> een e-mailadres|Berichten omleiden naar een beveiligingsbeheerder voor controle.|
|**De detectiereactie Safe bijlagen toepassen als scannen niet kan worden voltooid (time-out of fouten)** <p> _ActionOnError_|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
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
|**De volgende URL's blokkeren** <p> _ExcludedUrls_|Leeg <p> `$null`|Leeg <p> `$null`|Leeg <p> `$null`|We hebben geen specifieke aanbeveling voor deze instelling. <p> Zie 'De volgende [URL's blokkeren'](safe-links.md#block-the-following-urls-list-for-safe-links)voor meer Safe koppelingen.
|**Koppelingen Safe gebruiken in Office 365 apps** <p> _EnableSafeLinksForO365Clients_|Aan <p> `$true`|Aan <p> `$true`|Aan <p> `$true`|Gebruik Safe Koppelingen in ondersteunde Office 365 desktop- en mobiele apps (iOS en Android). Zie de instellingen voor koppelingen Safe voor Office 365 [voor meer informatie.](safe-links.md#safe-links-settings-for-office-365-apps)|
|**Niet bijhouden wanneer gebruikers klikken op beveiligde koppelingen in Office 365 apps** <p> _TrackClicks_|Aan <p> `$false`|Uit <p> `$true`|Uit <p> `$true`|Als u deze instelling uit schakelen _(trackclicks_ instellen op) worden `$true` gebruikersklikken in ondersteunde Office 365 bij.|
|**Laat gebruikers niet doorklikken naar de oorspronkelijke URL in Office 365 apps** <p> _AllowClickThrough_|Aan <p> `$false`|Aan <p> `$false`|Aan <p> `$false`|Door deze instelling in te stellen _(allowClickThrough_ in te stellen) wordt voorkomen dat doorklikken naar de oorspronkelijke URL in ondersteunde `$false` Office 365 apps.|
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
|**Beveiligingsinstellingen**|||||
|**Selecteer de actie voor onbekende potentieel schadelijke URL's in berichten** <p> _IsEnabled_|**Uit** <p> `$false`|**Aan** <p> `$true`|**Aan** <p> `$true`||
|**Selecteer de actie voor onbekende of potentieel schadelijke URL's binnen Microsoft Teams** <p> _EnableSafeLinksForTeams_|**Uit** <p> `$false`|**Aan** <p> `$true`|**Aan** <p> `$true`|Vanaf maart 2020 is deze functie beschikbaar in Preview en is alleen beschikbaar of alleen voor leden van het Microsoft Teams Technology Adoption Program (TAP).|
|**Realtime URL-scan toepassen op verdachte koppelingen en koppelingen die naar bestanden wijzen** <p> _ScanUrls_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Wacht totdat URL-scannen is voltooid voordat u het bericht bezorgt** <p> _DeliverMessageAfterScan_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Koppelingen Safe toepassen op e-mailberichten die binnen de organisatie zijn verzonden** <p> _EnableForInternalSenders_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`||
|**Gebruikersklikken niet bijhouden** <p> _DoNotTrackUserClicks_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Als u deze instelling uit schakelen _(doNotTrackUserClicks_ instellen `$false` op) worden gebruikersklikken bij de gebruiker bij de muisaanklikken bij het volgen van de muisklikken.|
|**Laat gebruikers niet doorklikken naar de oorspronkelijke URL** <p> _DoNotAllowClickThrough_|Niet geselecteerd <p> `$false`|Geselecteerd <p> `$true`|Geselecteerd <p> `$true`|Door deze instelling in te stellen _(doNotAllowClickThrough_ in te stellen) wordt voorkomen dat u `$true` doorklikt naar de oorspronkelijke URL.|
|**De huisstijl van de organisatie weergeven op meldings- en waarschuwingspagina's** <p> _EnableOrganizationBranding_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$false`|We hebben geen specifieke aanbeveling voor deze instelling. <p> Voordat u deze instelling in gebruikt, moet u de instructies volgen in Het thema [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) voor uw organisatie aanpassen om uw bedrijfslogo te uploaden.|
|**De volgende URL's niet opnieuw schrijven** <p> _DoNotRewriteUrls_|Niet geselecteerd <p> `$false`|Niet geselecteerd <p> `$true`|Niet geselecteerd <p> `$true`|We hebben geen specifieke aanbeveling voor deze instelling. Zie 'De volgende [URL's niet](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)opnieuw schrijven' in Safe Koppelingenbeleid voor meer informatie.|
|**Melding**|||||
|**Hoe wilt u uw gebruikers op de hoogte stellen?**|**De standaardmeldingstekst gebruiken**|**De standaardmeldingstekst gebruiken**|**De standaardmeldingstekst gebruiken**|We hebben geen specifieke aanbeveling voor deze instelling. <p> U kunt Aangepaste **meldingstekst gebruiken** _(CustomNotificationText)_ selecteren om aangepaste meldingstekst in te voeren die u wilt gebruiken. U kunt ook Gebruik Microsoft Translator voor automatische **lokalisatie** _(UseTranslatedNotificationText)_ selecteren om de aangepaste meldingstekst te vertalen naar de taal van de gebruiker.
|

## <a name="related-articles"></a>Verwante artikelen

- Zoekt u best practices voor Exchange regels voor **e-mailstroom (ook** wel transportregels genoemd)? Zie [Best practices for configuring mail flow rules in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Beheerders en gebruikers kunnen fout-positieven (goede e-mail die als slecht is gemarkeerd) en onwaar negatieven (slechte e-mail toegestaan) bij Microsoft indienen voor analyse. Zie voor meer informatie [berichten en bestanden rapporteren aan Microsoft](report-junk-email-messages-to-microsoft.md).

- Gebruik deze koppelingen voor informatie over het instellen **van** uw [EOP-service](/exchange/standalone-eop/set-up-your-eop-service)en **het** configureren van [Microsoft Defender voor Office 365.](defender-for-office-365.md) Vergeet niet de nuttige aanwijzingen in 'Beschermen[tegen bedreigingen in](protect-against-threats.md)Office 365'.

- **Beveiligingslijnlijnen** voor Windows vindt u hier: Waar vind ik de beveiligingslijnlijnen? voor opties voor GPO/on-premises en Gebruik beveiligingslijnlijnen om Windows 10-apparaten te configureren [in Intune](/intune/protect/security-baselines) voor op Intune gebaseerde beveiliging. [](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) Ten slotte is er een vergelijking beschikbaar tussen microsoft Defender voor eindpunten en Microsoft Intune-beveiligingslijnlijnen in Microsoft Defender voor eindpunt vergelijken met de [Windows Intune-beveiligingslijnlijnen.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
