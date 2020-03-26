---
title: Threat Explorer en real-time detecties, nieuw in Threat Explorer, wijzigingen in Threat Explorer, nieuw in Office 365, Beveiliging, Cloud Security, nieuw voor beveiliging in ATP, nieuwe ATP-functies
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Meer informatie over Explorer- en realtime &amp; detecties in het Security Compliance Center.
ms.openlocfilehash: 47dd871a385613c08ad5b4c02a7be8701e4b93a8
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955601"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer en real-time detecties

Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) heeft en u over de [benodigde machtigingen](#required-licenses-and-permissions)beschikt, hebt u **Explorer-** of **real-time detecties** (voorheen *realtime rapporten* - zie wat er nieuw [is](#new-features-in-threat-explorer-and-real-time-detections)!). Ga in het Security & Compliance Center naar **Bedreigingsbeheer**en kies **vervolgens Explorer** OF **realtime detecties.** 

|Met ATP Plan 2 zie je:  |Met ATP Plan 1 zie je:  |
|---------|---------|
|![Bedreigingsverkenner](../../media/threatmgmt-explorer.png)      |![Real-time detecties](../../media/threatmgmt-realtimedetections.png)         |

Met Explorer (of real-time detecties) beschikt u over een krachtig rapport waarmee uw Security Operations-team bedreigingen effectief en efficiënt kan onderzoeken en erop kunnen reageren. Het rapport lijkt op de volgende afbeelding: 

![Ga naar \> Threat management Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Met dit rapport u:
- [Bekijk malware gedetecteerd door office 365-beveiligingsfuncties](#see-malware-detected-in-email-by-technology)
- [Gegevens over phishing-URL's en klikvonnis weergeven](#view-data-about-phishing-urls-and-click-verdict)
- [Een geautomatiseerd onderzoeks- en reactieproces starten vanuit een weergave in Explorer](#start-automated-investigation-and-response) (alleen ATP-abonnement 2)
- ... [Onderzoek kwaadaardige e-mail, en meer!](#more-ways-to-use-explorer-or-real-time-detections)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nieuwe functies in Threat Explorer en real-time detecties

Drie nieuwe functies toegevoegd aan Threat Explorer en real-time detecties:
- [Voorbeeld van e-mailheader en e-mailhoofd downloaden](#preview-email-header-and-download-email-body)
- [Tijdlijn e-mail](#email-timeline)
- [URL-klikgegevens exporteren](#export-url-click-data)

Deze nieuwe functies worden hieronder beschreven.

### <a name="preview-email-header-and-download-email-body"></a>Voorbeeld van e-mailheader en e-mailhoofd downloaden

De mogelijkheid om een voorbeeld van een e-mailheader te bekijken en de e-mailbody te downloaden, zijn nieuwe functies die beschikbaar zijn in Threat Explorer. Beheerders kunnen gedownloade headers/e-mailberichten analyseren op bedreigingen. Omdat het downloaden van e-mailberichten de blootstelling van informatie kan riskeren, wordt dit proces gecontroleerd door op rollen gebaseerde toegangscontrole (RBAC). Een nieuwe rol, *Preview,* moet worden toegevoegd aan een andere Office 365-rolgroep (zoals Beveiligingsbewerkingen of beveiligingsbeheerder) om de mogelijkheid te bieden om e-mails te downloaden en kopteksten te bekijken in de weergave alle e-mailberichten.

Maar Explorer (en real-time detecties) voegt ook nieuwe velden toe die zijn ontworpen om u een vollediger beeld te geven van waar uw e-mailberichten landen. Een deel van het doel van deze verandering is om de jacht gemakkelijker te maken voor Security Ops mensen, maar het netto resultaat is het kennen van de locatie van probleem e-mailberichten in een oogopslag.

Hoe wordt dit gedaan? De leveringsstatus is nu opgesplitst in twee kolommen:

- **Delivery Action** - Wat is de status van deze e-mail?
- **Leveringslocatie** - Waar is deze e-mail naartoe gerouteerd?

Delivery Action is de actie die wordt ondernomen op een e-mail als gevolg van bestaande beleidsregels of detecties. Hier zijn de mogelijke acties die een e-mail kan ondernemen:

|Geleverd  |Junked Junked  |Geblokkeerd  |Vervangen  |
|---------|---------|---------|---------|
|E-mail is bezorgd in de inbox van de gebruiker of een andere map, en de gebruiker heeft er rechtstreeks toegang toe.    | E-mail is verzonden naar de map Ongewenste e-mail of de map Verwijderd en de gebruiker heeft toegang tot e-mailberichten in die mappen.       | E-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd en die niet toegankelijk zijn voor de gebruiker.     | Alle e-mailberichten waarbij schadelijke bijlagen zijn vervangen door .txt-bestanden waarin staat dat de bijlagen schadelijk waren.     |

En hier is wat de gebruiker kan zien, en wat ze niet kunnen:

|Toegankelijk voor eindgebruikers  |Ontoegankelijk voor eindgebruikers  |
|---------|---------|
|Geleverd     | Geblokkeerd        |
|Junked Junked     | Vervangen        |

De leveringslocatie toont de resultaten van beleid en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een bezorgactie. Dit veld is toegevoegd om inzicht te geven in de actie die wordt ondernomen wanneer een probleemmail wordt gevonden. Hier zijn de mogelijke waarden van de levering locatie:

- **Postvak IN of map**: De e-mail bevindt zich in de inbox of een map (volgens uw e-mailregels).
- **On-prem of extern**: Het postvak bestaat niet in de cloud, maar is on-premises.
- **Map ongewenste e-mail:** de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
- **Map Verwijderde items :** de e-mail in de map Verwijderde items van een gebruiker.
- **Quarantaine:** de e-mail in quarantaine en bevindt zich niet in het postvak van een gebruiker.
- **Mislukt:** de e-mail kan het postvak niet bereiken.
- **Gedropt**: De e-mail gaat ergens verloren in de e-mailstroom.

### <a name="email-timeline"></a>Tijdlijn e-mail

De **e-mailtijdlijn** is een andere nieuwe Explorer-functie die is gericht op het beter maken van de jachtervaring voor beheerders. Het vermindert op randomisatie omdat er minder tijd besteed aan het controleren van verschillende locaties om te proberen om de gebeurtenis te begrijpen. Wanneer meerdere gebeurtenissen op of in de buurt van een e-mail tegelijkertijd plaatsvinden, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. In feite worden sommige gebeurtenissen die gebeuren na de levering van uw e-mail vastgelegd in de kolom 'Speciale actie'. Door de informatie uit de tijdlijn van die e-mail te combineren met de speciale actie die wordt ondernomen op de postpost van de e-mail, krijgen beheerders inzicht in hoe hun beleid werkt, waar de e-mail uiteindelijk is gerouteerd en, in sommige gevallen, wat de uiteindelijke beoordeling was.

Zie [Schadelijke e-mailberichten zoeken en onderzoeken die in Office 365 is bezorgd voor](https://docs.microsoft.com/office365/securitycompliance/investigate-malicious-email-that-was-delivered)meer discussie over het onderzoeken van schadelijke e-mailberichten.

### <a name="export-url-click-data"></a>URL-klikgegevens exporteren

U nu ook rapporten exporteren voor URL-klikken naar Microsoft Excel om zowel hun netwerkbericht-id als hun klikvonnis weer te geven, zodat u begrijpen waar uw URL-klikverkeer gemakkelijker is ontstaan. Zo werkt het. Klik vanaf de snellancering van Office 365 in Op Threat Management in de snellancering van Office 365:

**Explorer** > **View Phish** > **Clicks** > **Top URL's of URL Top Clicks** > **Klik op een record om URL flyout te openen**

Wanneer u op een URL in de lijst klikt, ziet u een nieuwe knop Exporteren in het fly-outpaneel. Gebruik deze knop om gegevens naar een Excel-spreadsheet te verplaatsen voor eenvoudigere rapportage.

U in het realtime detectierapport als volgt naar dezelfde locatie gaan:

**Explorer** > **Real-time detecties** > **Bekijk Phish** > URL's Top**URL's** > **of Top Clicks** > **Klik op een record om URL flyout** > te openen**Navigeer naar het tabblad Klikken.**

> [!TIP]
> Netwerkbericht-ID brengt de klik terug naar specifieke e-mails wanneer u via Explorer of bijbehorende hulpprogramma's van derden via Network Message ID zoekt. Als u door de netwerkbericht-id zoekt, geven beheerders de specifieke e-mail die is gekoppeld aan een klikresultaat. Bij export met, de correleren identificatie van Network Message ID zorgt voor een snellere en krachtigere analyse.

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Bekijk malware gedetecteerd in e-mail door technologie

Stel dat u malware wilt zien gedetecteerd in e-mail, door Office 365-technologie. Gebruik hiervoor de [weergave E-mail > malware](threat-explorer-views.md#email--malware) van Explorer (of realtime detecties).

1. Kies in het Security[https://protection.office.com](https://protection.office.com)& Compliance Center ( ) De optie **Threat management** > **Explorer** (of **Real-time detections).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies **in het** menu Weergave de optie **Malware e-mailen.** > **Malware**<br/>![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailMalwareMenu.png)<br/>

3. Klik op **Afzender**en kies vervolgens**Basisdetectietechnologie** **Basic** > .<br/>Uw detectietechnologieën zijn nu beschikbaar als filters voor het rapport.<br/>![Malwaredetectietechnologieën](../../media/ExplorerEmailMalwareDetectionTech.png)<br/> 

4. Selecteer een optie en klik op de knop **Vernieuwen** om dat filter toe te passen.<br/>![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)<br/> 

Het rapport wordt vernieuwd om de resultaten weer te geven die malware in e-mail heeft gedetecteerd, met behulp van de technologieoptie die u hebt geselecteerd. Vanaf hier u verdere analyse uitvoeren.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Gegevens over phishing-URL's en klikvonnis weergeven

Stel dat u phishing-pogingen via URL's in e-mail wilt zien, inclusief een lijst met URL's die zijn toegestaan, geblokkeerd en overschreven. Als u URL's identificeert waarop is geklikt, moeten [ATP Safe-koppelingen](atp-safe-links.md) worden geconfigureerd. Zorg ervoor dat u [ATP Safe Links-beleidsregels](set-up-atp-safe-links-policies.md) hebt ingesteld voor time-of-click-beveiliging en het loggen van klikvonnissen door ATP Safe Links. 

Als u phish-URL's wilt controleren in berichten en wilt klikken op URL's in phish-berichten, gebruikt u de [Phish-weergave e-mail > van](threat-explorer-views.md#email--phish) Explorer (of realtime detecties).

1. Kies in het Security[https://protection.office.com](https://protection.office.com)& Compliance Center ( ) De optie **Threat management** > **Explorer** (of **Real-time detections).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies**Phish** **e-mail** > en in het menu **Weergave** .<br/>![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailPhishMenu.png)<br/>

3. Klik **op Afzender**en kies **URL's** > **Klik op het vonnis**.

4. Selecteer een of meer opties, zoals **Geblokkeerd** en **Overschreven blokkeren,** en klik op de knop **Vernieuwen** die zich op dezelfde lijn bevindt als de opties om dat filter toe te passen. (Vernieuw uw browservenster niet.)<br/>![URL's en klikvonnissen](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)<br/>

    Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **De belangrijkste URL's** zijn de URL's in de berichten waarnaar u hebt gefilterd en de actie voor e-mailbezorging telt voor elke URL. In de phish-e-mailweergave bevat deze lijst doorgaans legitieme URL's. Aanvallers bevatten een mix van goede en slechte URL's in hun berichten om te proberen om ze geleverd, maar ze zullen de kwaadaardige links interessanter voor de gebruiker om te klikken. De tabel met URL's wordt gesorteerd op het totale aantal e-mail (LET OP: deze kolom wordt niet weergegeven om de weergave te vereenvoudigen).

   - **De hoogste klikken** zijn de in veilige koppelingen verpakte URL's waarop is geklikt, gesorteerd op totaal aantal klikken (deze kolom wordt ook niet weergegeven om de weergave te vereenvoudigen). Het totaal aantal tellingen per kolom geeft het aantal klikken op veilige koppelingen aan op het aantal klikken voor elke klik-URL. In de phish-e-mailweergave zijn dit vaker verdachte of schadelijke URL's, maar kunnen URL's bevatten die geen bedreigingen zijn, maar in phish-berichten staan. URL-klikken op onverpakte links worden hier niet weergegeven.
   
   De twee URL-tabellen tonen de belangrijkste URL's in phishing-e-mailberichten op basis van leveringsactie en locatie, en ze tonen URL-klikken die zijn geblokkeerd (of bezocht ondanks een waarschuwing), zodat u begrijpen welke potentiële slechte koppelingen door gebruikers zijn ontvangen en waarmee gebruikers hebben samengewerkt. Vanaf hier u verdere analyse uitvoeren. Onder de grafiek ziet u bijvoorbeeld de bovenste URL's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.
   
   ![Explorer-URL's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)
   
   Selecteer een URL om meer gedetailleerde informatie weer te geven. **Opmerking:** In het dialoogvenster URL-flyout wordt het filteren op e-mailberichten verwijderd om u de volledige weergave van de blootstelling van de URL in uw omgeving te laten zien. Hiermee u e-mailberichten in Explorer filteren op berichten waar u zich zorgen over maakt, specifieke URL's vinden die potentiële bedreigingen zijn en vervolgens uw begrip van de URL-blootstelling in uw omgeving uitbreiden (via het dialoogvenster URL-details) zonder URL-filters toe te voegen aan de Explorer-weergave zelf.

## <a name="review-email-messages-reported-by-users"></a>E-mailberichten controleren die door gebruikers worden gerapporteerd

Stel dat u e-mailberichten wilt zien die gebruikers in uw organisatie hebben gerapporteerd als Ongewenste e-mail, niet ongewenste e-mail of phishing met behulp van de [invoegtoepassing Bericht melden voor Outlook en Outlook op de web.](enable-the-report-message-add-in.md) Gebruik hiervoor de weergave [E-mail > inzendingen](threat-explorer-views.md#email--submissions) van Explorer (of realtime detecties).

1. Kies in het Security[https://protection.office.com](https://protection.office.com)& Compliance Center ( ) De optie **Threat management** > **Explorer** (of **Real-time detections).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies **E-mailinzendingen** > **Submissions**in het menu **Weergave** .<br/>![Menu Weergeven voor Explorer](../../media/ExplorerViewMenuEmailUserReported.png)<br/>

3. Klik **op Afzender**en kies vervolgens Het type **Basisrapport** > **Report type**.

4. Selecteer een optie, zoals **Phish,** en klik op de knop **Vernieuwen.** <br/>![Door de gebruiker gerapporteerde phish](../../media/EmailUserReportedReportType.png)<br/> 

Het rapport wordt vernieuwd om gegevens over e-mailberichten weer te geven die mensen in uw organisatie hebben gerapporteerd als een phishing-poging. U deze informatie gebruiken om verdere analyses uit te voeren en indien nodig uw [ATP-antiphishingbeleid](set-up-anti-phishing-policies.md)aan te passen.

## <a name="start-automated-investigation-and-response"></a>Start geautomatiseerd onderzoek en respons

> [!NOTE]
> Geautomatiseerde mogelijkheden voor onderzoek en respons zijn beschikbaar in **Office 365 ATP Plan 2** en Office **365 E5.**

(NIEUW!) [Geautomatiseerd onderzoek en reactie](automated-investigation-response-office.md) kan uw security operations team veel tijd en moeite besparen in het onderzoeken en beperken van cyberaanvallen. Naast het configureren van waarschuwingen die een beveiligingsplaybook kunnen activeren, u een geautomatiseerd onderzoeks- en reactieproces starten vanuit een weergave in Explorer. 

Zie [Voorbeeld: een beveiligingsbeheerder activeert een onderzoek vanuit Explorer voor](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)meer informatie hierover.

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Meer manieren om Explorer (of realtime detecties) te gebruiken

Naast de scenario's die in dit artikel worden beschreven, hebt u veel meer rapportageopties beschikbaar met Explorer (of realtime detecties). 
- [Schadelijke e-mail zoeken en onderzoeken die is bezorgd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Een overzicht krijgen van de weergaven in Threat Explorer (en realtime detecties)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet [office 365 ATP](office-365-atp.md) hebben om Explorer- of realtimedetecties te kunnen detecteren.
- Explorer is opgenomen in Office 365 ATP Plan 2. 
- Het realtime detectierapport is opgenomen in Office 365 ATP Plan 1.
- Plan licenties toe te wijzen voor alle gebruikers die moeten worden beschermd door Office 365 ATP. (Explorer of real-time detecties toont detectiegegevens voor gelicentieerde gebruikers.)

Als u Explorer- of realtimedetecties wilt bekijken en gebruiken, moet u over de juiste machtigingen beschikken, zoals die welke zijn verleend aan een beveiligingsbeheerder of beveiligingslezer. 

- Voor het &amp; Security Compliance Center moet u een van de volgende rollen toegewezen hebben:
    - Organisatiebeheer
    - Beveiligingsbeheerder (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ( ))
    - Beveiligingslezer

- Voor Exchange Online moet u een van de volgende rollen[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)hebben toegewezen in het Exchange-beheercentrum ( ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)
    - Organisatiebeheer
    - Organisatiebeheer alleen weergeven
    - Functie Alleen-weergaveontvangers
    - Compliance Management

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Enkele verschillen tussen Threat Explorer en real-time detecties

 - Het **realtime detectierapport** is beschikbaar in Office 365 ATP Plan 1, terwijl **Threat Explorer** beschikbaar is in Office 365 ATP Plan 2.
 - Met **het realtime detectierapport** u detecties in realtime bekijken. **Threat Explorer** doet dit ook, maar stelt u ook in staat om extra details voor een bepaalde aanval te bekijken.
