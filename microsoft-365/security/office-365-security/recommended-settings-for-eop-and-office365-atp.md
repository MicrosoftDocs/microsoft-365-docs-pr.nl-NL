---
title: Microsoft-aanbevelingen voor EOP- en Office 365 ATP-beveiligingsinstellingen, aanbevelingen, Sender Policy Framework, domeingebaseerde berichtrapportage en -conformiteit, domainkeys identified mail, stappen, hoe werkt het, beveiligingsbasislijnen, basislijnen voor EOP, basislijnen voor ATP, setup ATP, setup EOP, ATP configureren, EOP configureren, beveiligingsconfiguratie
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
ms.openlocfilehash: b7c98fe4b362a5be72be9e103a2602cd4954e028
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42810450"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Aanbevolen instellingen voor EOP- en Office 365 ATP-beveiliging

**Exchange Online Protection (EOP)** is de kern van beveiliging voor Office 365-abonnementen en helpt voorkomen dat schadelijke e-mails de inboxen van uw werknemer bereiken. Maar met nieuwe, meer geavanceerde aanvallen die elke dag opduiken, zijn er vaak betere beveiligingen nodig. **Office 365 Advanced Threat Protection (ATP)** ATP Plan 1 of ATP Plan 2 bevatten extra functies die beheerders meer beveiliging, controle en onderzoek geven.

Hoewel we beveiligingsbeheerders in staat stellen hun beveiligingsinstellingen aan te passen, zijn er twee beveiligingsniveaus in EOP en Office 365 ATP die we aanbevelen: **Standaard** en **Strikt.** De omgeving en behoeften van elke klant zijn verschillend, maar we zijn van mening dat deze niveaus van e-mailfilteringconfiguraties zullen helpen voorkomen dat ongewenste e-mail in de meeste situaties de inbox van uw werknemers bereikt.

> [!IMPORTANT]
> De configuratie van ongewenste e-mail moet op het postvak worden ingeschakeld om te kunnen filteren om goed te kunnen filteren. Dit is standaard ingeschakeld, maar moet worden gecontroleerd als het filteren niet lijkt te werken. Lees [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) voor meer informatie. 

In dit onderwerp worden deze door Microsoft aanbevolen instellingen beschreven om uw Office 365-gebruikers te beschermen.

> [!TIP]
> Er is een nieuwe PowerShell-module die u downloaden, de Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) die helpt bij het bepalen van een aantal van deze instellingen. Wanneer u wordt uitgevoerd als beheerder in uw tenant, helpt Get-ORCAReport bij het genereren van een beoordeling van de anti-spam-, anti-phish- en andere instellingen voor berichthygiëne. U deze https://www.powershellgallery.com/packages/ORCA/module downloaden op.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Anti-spam, anti-malware en bescherming tegen phishing in EOP

Anti-spam, anti-malware en anti-phishing zijn functies van EOP die door beheerders kunnen worden geconfigureerd. Wij raden de volgende configuraties aan.

### <a name="eop-anti-spam-policy-settings"></a>EOP-beleidsinstellingen voor spam

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Spamdetectieactie|Bericht verplaatsen naar map Ongewenste e-mail|Quarantainebericht||
|Actie voor spamdetectie met hoog vertrouwen|Quarantainebericht|Quarantainebericht||
|Actie voor detectie van phishing-e-mail|Quarantainebericht|Quarantainebericht||
|Hoog vertrouwen Phish e-mail detectie actie|Quarantainebericht|Quarantainebericht||
|Actie voor detectie van bulke-mail|Bericht verplaatsen naar map Ongewenste e-mail|Quarantainebericht||
|Bulk-e-maildrempel instellen op|6|4|De standaardwaarde is momenteel 7, maar we raden u aan deze te wijzigen in 6. Zie Waarden [bulkklachtenniveau](bulk-complaint-level-values.md)voor meer informatie .|
|Bewaartermijn quarantaine|30 dagen|30 dagen||
|Veiligheidstips|Op|Op||
|Toegestane afzenders|Geen|Geen||
|Toegestane afzendersdomeinen|Geen|Geen|Het is niet vereist om domeinen die u bezit (ook wel _geaccepteerde domeinen_genoemd) toe te voegen aan de lijst met toegestane afzenders. In feite wordt het beschouwd als een hoog risico, omdat het kansen creëert voor slechte acteurs om u e-mail te sturen die anders zou worden gefilterd. Gebruik [spoofinformatie](learn-about-spoof-intelligence.md) in het Security & Compliance Center op de pagina **Anti-spam-instellingen** om alle afzenders te controleren die domeinen spoofen die deel uitmaken van uw organisatie of externe domeinen spoofen.|
|Geblokkeerde afzenders|Geen|Geen||
|Geblokkeerde domeinen afzenders|Geen|Geen||
|Frequentie van de melding van spam voor eindgebruikers|Ingeschakeld|Ingeschakeld|3 dagen|
|Zero Hour automatische zuivering|Op|Op|Voor zowel Spam als Phish ZAP|
|MarkasspamBulkMail|Op|Op|Deze instelling is alleen beschikbaar in PowerShell|

Er zijn verschillende andere parameters in het antispambeleid genaamd Advanced Spam filter (AsF) die in het proces van afgeschaft zijn. Meer informatie over de tijdlijnen voor de afschrijving van deze functies zal worden meegedeeld buiten dit onderwerp.

We raden u aan deze instellingen **uit te** schakelen voor zowel standaard- als strikte niveaus:

|Naam beveiligingsfunctie|Opmerkingen|
|---------|---------|
|VerhogingScoreWithImageLinks||
|IncreaseScorewithNumericIps||
|VerhogingScoreWithRedirecttoOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkasspamJavaScriptinhtml||
|Markasspamframesinhtml||
|Markasspamobjecttagsinhtml||
|Markasspamembedtagsinhtml||
|Markasspamformtagsinhtml||
|MarkasspamWebbugsinhtml||
|MarkasspamSensitiveWordList||
|MarkasspamfromAddressAuthFail||
|MarkAsSpamNdrBackscatter MarkAsSpamNdrBackscatter||
|MarkasspamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>Beleidsinstellingen voor eOP-uitgaande spamfilters

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Limieten voor uitgaande spammeldingen - Externe uurlimiet|500|400||
|Limieten voor uitgaande spam -Ontvangers van uitgaande spam - Interne uurlimiet|1000|800||
|Limieten voor uitgaande spammeldingen ontvangen ontvangers - dagelijkse limiet|1000|800||
|Actie wanneer een gebruiker de limieten overschrijdt|De gebruiker beperken om e-mail te verzenden|De gebruiker beperken om e-mail te verzenden||

### <a name="eop-anti-malware-policy-settings"></a>EOP anti-malware beleidsinstellingen

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Reactie op malwaredetectie|Nee|Nee|Als er malware wordt gedetecteerd in een e-mailbijlage, wordt het bericht in quarantaine geplaatst en kan het alleen door een beheerder worden vrijgegeven.|
|Filter 'Common Attachment Types' voor het blokkeren van verdachte bestandstypen|Op|Op||
|Malware Zero-hour Auto Purge|Op|Op||
|Interne afzenders op de hoogte stellen van het niet-afgeleverde bericht|Handicap|Handicap||
|Externe afzenders op de hoogte stellen van het niet-afgeleverde bericht|Handicap|Handicap||

### <a name="eop-anti-phishing-policy-settings"></a>EOP-beleidsinstellingen tegen phishing

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Anti-spoofing-beveiliging inschakelen|Op|Op||
|Niet-geverifieerde afzender inschakelen (taggen)|Op|Op||
|Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen|Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden|Het bericht in quarantaine plaatsen||

## <a name="office-365-advanced-threat-protection-security"></a>Beveiliging van geavanceerde bedreigingsbeveiliging van Office 365

Extra beveiligingsvoordelen worden geleverd met een ATP-abonnement (Office 365 Advanced Threat Protection). Voor het laatste nieuws en informatie u zien [wat er nieuw is in Office 365 ATP.](whats-new-in-office-365-atp.md)

Office 365 ATP bevat het beleid voor veilige bijlagen en veilige koppelingen om te voorkomen dat e-mail met mogelijk schadelijke bijlagen wordt geleverd en om te voorkomen dat gebruikers op mogelijk onveilige URL's klikken.

> [!IMPORTANT]
> Geavanceerde anti-phishing is een van de voordelen van een Office 365 ATP-abonnement. Hoewel het standaard is ingeschakeld, ***moet*** u ten minste één antiphishingbeleid configureren voordat het e-mail kan filteren. Het vergeten om anti-phishing beleid te configureren kan gebruikers blootstellen aan riskante e-mails. Zorg ervoor dat u uw antiphishingbeleid configureert nadat u een Office 365 ATP-abonnement hebt toegevoegd.

Als u een Office 365 ATP-abonnement aan uw EOP hebt toegevoegd, stelt u de volgende configuraties in.

### <a name="office-atp-anti-phishing-policy-settings"></a>Beleidsinstellingen voor office ATP-antiphishing

EOP-klanten krijgen basisantiphishing zoals eerder beschreven, maar Office 365 ATP bevat meer functies en controle om aanvallen te voorkomen, te detecteren en te saneren.

|Naam van de functie voor imitatiebeveiliging|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|(Imitatiebeleid bewerken) Gebruikers toevoegen om te beschermen|Op|Op|Is afhankelijk van uw organisatie, maar we raden u aan gebruikers toe te voegen in belangrijke rollen. Intern kunnen dit uw CEO, CFO en andere senior leiders zijn. Extern kunnen dit raadsleden of uw raad van bestuur zijn.|
|(Imitatiebeleid bewerken) Voeg automatisch de domeinen toe die ik bezit|Op|Op||
|(Imitatiebeleid bewerken) Aangepaste domeinen opnemen|Op|Op|Afhankelijk van uw organisatie, maar we raden u aan domeinen toe te voegen waarmee u het meest communiceert en waarvan u niet de eigenaar bent.|
|Als e-mail wordt verzonden door een nagebootste gebruiker die u hebt opgegeven|Het bericht in quarantaine plaatsen|Het bericht in quarantaine plaatsen||
|Als e-mail wordt verzonden door een geïmiteerd domein dat u hebt opgegeven|Het bericht in quarantaine plaatsen|Het bericht in quarantaine plaatsen||
|Tip weergeven voor geïmiteerde gebruikers|Op|Op||
|Tip weergeven voor nagebootste domeinen|Op|Op||
|Tip weergeven voor ongebruikelijke tekens|Op|Op||
|Postvakintelligentie inschakelen|Op|Op||
|Bescherming op basis van postvakintelligentie inschakelen op basis van imitatie|Op|Op||
|Als e-mail wordt verzonden door een nagebootste gebruiker die is beschermd door postvakinformatie|Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden|Het bericht in quarantaine plaatsen||
|(Imitatiebeleid bewerken) Vertrouwde afzenders en domeinen toevoegen|Geen|Geen|Afhankelijk van uw organisatie, maar we raden u aan gebruikers of domeinen toe te voegen die ten onrechte als phish worden gemarkeerd vanwege alleen imitatie en niet andere filters.|

|Naam van de spoofbeveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Anti-spoofing-beveiliging inschakelen|Op|Op||
|Niet-geverifieerde afzender inschakelen (taggen)|Op|Op||
|Als e-mail wordt verzonden door iemand die uw domein niet mag spoofen|Bericht verplaatsen naar de map ongewenste e-mail van de geadresseerden|Het bericht in quarantaine plaatsen||
|Verdachteveiligheidstip inschakelen|Valse|Waar|Deze instelling is alleen beschikbaar in PowerShell|
|TreatSoftPassAsAuthenticated|Waar|Valse|Deze instelling is alleen beschikbaar in PowerShell|


|Naam beveiligingsfunctie voor geavanceerde instellingen|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|Geavanceerde phishingdrempels|2 - Agressief|3 - Agressiever||

### <a name="safe-links-settings"></a>Instellingen voor veilige koppelingen

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|ATP-veilige koppelingen gebruiken in Office 365-apps, Office voor iOS en Android|Ingeschakeld|Ingeschakeld|Dit valt onder het ATP Safe Links-beleid dat van toepassing is op de hele organisatie|
Niet bijhouden wanneer gebruikers op veilige koppelingen klikken|Handicap|Handicap|Dit is voor zowel beleid dat van toepassing is op de hele organisatie als voor alle beleidsregels die van toepassing zijn op specifieke ontvangers|
|Laat gebruikers niet door veilige links naar de oorspronkelijke URL klikken|Ingeschakeld|Ingeschakeld|Dit is voor zowel het beleid dat van toepassing is op de hele organisatie als voor alle beleidsregels die van toepassing zijn op specifieke ontvangers|
|Actie voor onbekende mogelijk schadelijke URL's in berichten|Op|Op||
|Real-time URL scannen toepassen op verdachte links en koppelingen die naar bestanden verwijzen|Ingeschakeld|Ingeschakeld||
|Wachten tot het scannen van url's is voltooid voordat het bericht wordt geleverd|Ingeschakeld|Ingeschakeld||
|Veilige koppelingen toepassen op e-mailberichten die binnen de organisatie worden verzonden|Ingeschakeld|Ingeschakeld||

### <a name="safe-attachments"></a>Veilige bijlagen

|Naam beveiligingsfunctie|Standaard|Strikte|Opmerking|
|---------|---------|---------|---------|
|ATP inschakelen voor SharePoint, OneDrive en Microsoft Teams|Ingeschakeld|Ingeschakeld||
|ATP Safe bijlagen onbekende malware reactie|Blok|Blok||
|Bijlage bij detectie omleiden|Ingeschakeld|Ingeschakeld|Omleiden naar e-mailadres voor een beveiligingsbeheerder die weet hoe te bepalen of de bijlage malware is of niet|
|ATP Safe bijlagen reactie als malware scannen op bijlagen een tijd uit of fout optreedt|Ingeschakeld|Ingeschakeld||


## <a name="related-topics"></a>Verwante onderwerpen

- Bent u op zoek naar best practices met **Exchange Mail Flow / Exchange Transport Rules?** Zie [dit artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) voor meer informatie.

- Stuur verdachte e-mails, vermoedelijke spam, phish of URL's naar Microsoft voor scan. Gebruik de aanwijzingen **voor inzendingen voor beheerders** in dit [artikel](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Gebruik deze koppelingen voor informatie over het **instellen van** uw [EOP-service](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)en **configureren van** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Vergeet niet de nuttige aanwijzingen te zien in['Beschermen tegen bedreigingen in Office 365'.)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)

- **Beveiligingsbasislijnen voor Windows** zijn [hier](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) te vinden voor GPO/on-premises opties en voor Intune-gebaseerde beveiliging, [hier.](https://docs.microsoft.com/intune/protect/security-baselines) Tot slot is [hier](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)een vergelijking te vinden tussen Microsoft Defender Advanced Threat Protection (ATP) en Windows Intune security baselines.
