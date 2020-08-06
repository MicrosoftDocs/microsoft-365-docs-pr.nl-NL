---
title: Bedreigings Verkenner en real-time ontdekken
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
description: Meer informatie over het gebruik van de Verkenner en de real-time detectie van beveiligings &amp; compliance om bedreigingen effectiever en efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 42cb7d2ef4fd04875c4bedc5f783e87cc99c13f5
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577525"
---
# <a name="threat-explorer-and-real-time-detections"></a>Bedreigings Verkenner en real-time ontdekken

Als uw organisatie [office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) heeft en u de [benodigde machtigingen](#required-licenses-and-permissions)hebt, hebt u de keuze uit de **Verkenner** of de **realtime** (voorheen *realtime-rapporten* ), [Zie wat is er nieuw](#new-features-in-threat-explorer-and-real-time-detections)!. Ga in het beveiligings & nalevings centrum naar **Threat Management**en kies vervolgens **Verkenner** _of_ **realtime-detecties**.

|Met ATP abonnement 2 ziet u het volgende:|Met ATP abonnement 1 ziet u het volgende:|
|---|---|
|![Bedreigings Verkenner](../../media/threatmgmt-explorer.png)|![Realtime detectie](../../media/threatmgmt-realtimedetections.png)|
|

Met de Verkenner (of realtime detectie) hebt u een krachtig rapport waarmee uw beveiligingsactiviteiten team op hun eigen en efficiënte manier kunnen onderzoeken en beantwoorden. Het rapport is vergelijkbaar met de volgende afbeelding:

![Ga naar Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Met dit rapport kunt u:

- [Zie malware die door Microsoft 365 beveiligingsfuncties is gedetecteerd.](#see-malware-detected-in-email-by-technology)
- [Bekijk gegevens over phishingberichten en klik op Verdict](#view-data-about-phishing-urls-and-click-verdict)
- [Een automatisch onderzoek en antwoord proces starten vanuit een weergave in Verkenner (alleen voor het](#start-automated-investigation-and-response) ATP-abonnement 2)
- ... [Onderzoek kwaadaardige e-mail en nog veel meer](#more-ways-to-use-explorer-or-real-time-detections).

## <a name="experience-improvements-to-threat-explorer-and-real-time-detections"></a>Ervaar verbeteringen in de weergave van de bedreiging en de real-time detectie

Als onderdeel van de verbetering van de jacht, hebben we enkele updates gemaakt voor de bedreigings Verkenner en de realtime detectie. Dit zijn de verbeteringen van de ervaring, met de focus op de beleving van de jacht consistent. Hieronder ziet u een overzicht van deze wijzigingen:

- [Tijdzone verbeteringen](#timezone-improvements)
- [Bijwerken in het vernieuwingsproces](#update-in-the-refresh-process)
- [DrillDown voor de grafiek om toe te voegen aan filters](#chart-drilldown-to-add-to-filters)
- [Updates voor productgegevens](#in-product-information-updates)

### <a name="timezone-improvements"></a>Tijdzone verbeteringen

We tonen de tijdzone voor de e-mail records binnen de portal en voor de geëxporteerde gegevens. De tijdzone is zichtbaar in functies zoals E-mail raster, Details flyout, e-mail tijdlijn en soortgelijke E-mail, zodat de tijdzone voor de resultatenset duidelijk is voor de gebruiker.

![Tijdzone weergeven in Verkenner](../../media/TimezoneImprovements.png)

### <a name="update-in-the-refresh-process"></a>Bijwerken in het vernieuwingsproces

We hebben uw feedback om verwarring met automatisch vernieuwen (bijvoorbeeld voor datum nadat u de datum hebt gewijzigd nadat u de pagina hebt gewijzigd) en handmatig vernieuwen (voor andere filters). Evenzo verwijdert filters potentiële klanten naar automatisch vernieuwen, dan wordt er een situatie waarbij het wijzigen van de verschillende filters tijdens het wijzigen van de query inconsistentie van de zoekfuncties kan veroorzaken. Om dit op te lossen, gaan we overstappen op een handmatig filtermechanisme.
Vanuit het oogpunt van de ervaring kan de gebruiker een verschillend bereik van filters (uit de filtersset en datum) toepassen en verwijderen en vervolgens op de knop Vernieuwen klikken om de resultaten te filteren nadat deze zijn uitgevoerd met het definiëren van de query. De knop Vernieuwen is ook bijgewerkt, zodat deze duidelijk op het scherm wordt weergegeven. We hebben ook Scherminfo en documentatie ter informatie bijgewerkt.

![Klik op vernieuwen om resultaten te filteren](../../media/ManualRefresh.png)

### <a name="chart-drilldown-to-add-to-filters"></a>DrillDown voor de grafiek om toe te voegen aan filters

U kunt nu op de waarden van de grafieklegenda klikken om deze waarde als een filter toe te voegen. Houd er rekening mee dat u altijd op de knop Vernieuwen hoeft te klikken om de resultaten te filteren als onderdeel van de hierboven beschreven wijziging.

![DrillDown via grafieken om te filteren](../../media/ChartDrilldown.png)

### <a name="in-product-information-updates"></a>Updates voor productgegevens

U moet ook aanvullende informatie binnen het product zien. Bijvoorbeeld het totale aantal zoekresultaten in het raster (zie hieronder), en verbeteringen rond labels, foutberichten en Scherminfo, voor meer informatie over filters, zoekervaring en resultatensets.

![Info over product weergeven](../../media/ProductInfo.png)


## <a name="new-features-in-real-time-detections"></a>Nieuwe functies in real-time ontdekken

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nieuwe functies in de bedreigings Verkenner en de real-time detectie

Drie nieuwe functies toegevoegd aan de bedreigings Verkenner en de real-time detecties:

- [Voorbeeld van e-mailkop tekst](#preview-email-header-and-download-email-body)
- [E-mail tijdlijn](#email-timeline)
- [URL exporteren Klik op gegevens](#export-url-click-data)

Hieronder ziet u een overzicht van de nieuwe functies.

### <a name="preview-email-header-and-download-email-body"></a>Voorbeeld van e-mailkop tekst

De mogelijkheid om een voorbeeld van een e-mailbericht te bekijken en de tekst van het bericht te downloaden zijn nieuwe functies die beschikbaar zijn in de Threat Explorer Beheerders kunnen gedownloade berichtkoppen/e-mailberichten analyseren voor bedreigingen. Aangezien het downloaden van e-mailberichten de blootstelling van gegevens kan betekenen, wordt dit proces bepaald door toegangsbeheer op basis van rollen. Een nieuwe rol, *Preview*, moet worden toegevoegd aan een andere rolgroep (zoals beveiligingsactiviteiten of beveiligingsbeheerder) om de mogelijkheid om e-mailberichten te downloaden en voorbeelden van kopteksten weer te geven in de weergave alle e-mailberichten.

Maar in de Verkenner (en realtime-detectie) worden ook nieuwe velden toegevoegd waarmee u een beter beeld kunt krijgen van de locatie van uw e-mailberichten. Onderdeel van het doel van deze wijziging is om de jacht eenvoudiger te maken voor mensen met een hoeveelheid werk, maar het resultaat van de e-mail is in één oogopslag de locatie van de problematische e-mailberichten.

Hoe is dit gebeurd? De bezorgings status is nu uitgebroken in twee kolommen:

- **Bezorgings actie** : wat is de status van dit e-mailbericht?
- **Bezorgingslocatie** : waar werd dit e-mailbericht rondgestuurd als resultaat?

De bezorgings actie is de actie die op een e-mail is uitgevoerd vanwege bestaande beleidsregels of detecties. Dit zijn de mogelijke acties waarmee een e-mail kan worden verzonden:

|Aflevering|Ongewenst|Blokkeert|Gekomen|
|---|---|---|---|
|E-mail is bezorgd in het postvak in of de map van een gebruiker en de gebruiker kan deze rechtstreeks openen.|E-mail verzonden naar de map Ongewenste E-mail van de gebruiker of de map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in die mappen.|Alle e-mailberichten die zijn gequarantined, dat niet is gelukt of zijn verwijderd. Dit is helemaal niet toegankelijk voor de gebruiker.|Alle e-mailberichten waarin schadelijke bijlagen worden vervangen door txt-bestanden die aangeven dat de bijlage schadelijk is.|

|Aflevering|Ongewenst|Blokkeert|Gekomen|
|---|---|---|---|
|E-mail is bezorgd in het postvak in van de gebruiker of een andere map, en de gebruiker kan deze rechtstreeks openen.|E-mail is verzonden naar de map Ongewenste E-mail van de gebruiker of de map die is verwijderd, en de gebruiker heeft toegang tot e-mailberichten in die mappen.|Alle e-mailberichten die zijn overgezet, die niet kunnen worden verwijderd en die niet toegankelijk zijn voor de gebruiker.|Alle e-mailberichten waarin schadelijke bijlagen zijn vervangen door txt-bestanden, waarbij de bijlage is beschadigd.|
|

En wat ze niet kan zien en wat ze niet kan doen:

|Toegankelijk voor eindgebruikers|Niet toegankelijk voor eindgebruikers|
|---|---|
|Aflevering|Blokkeert|
|Ongewenst|Gekomen|

Locatie van levering toont de resultaten van beleidsregels en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een bezorgings actie. Dit veld is toegevoegd om inzicht te krijgen in de actie die optreedt wanneer er een probleem met de e-mail is gevonden. Dit zijn de mogelijke waarden van de lever locatie:

- **Postvak in of map**: het e-mailbericht bevindt zich in het postvak in of een map (volgens uw e-mail regels).
- **On-premises of extern**: het postvak bestaat niet in de Cloud, maar is on-premises.
- **Map Ongewenste e-mail**: de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
- **Map Verwijderde items**: het e-mailbericht in de map Verwijderde items van een gebruiker.
- **Quarantine**: het e-mailbericht in quarantaine, dat zich niet in het postvak van een gebruiker bevindt.
- **Mislukt**: het e-mailadres is niet bereikbaar voor het postvak.
- **Neergezet**: de e-mail wordt ergens in de e-mail stroom verwijderd.

### <a name="email-timeline"></a>E-mail tijdlijn

De **e-mail tijdlijn** is een andere nieuwe Explorer-functie, die bedoeld is voor een betere beleving van de jacht van de beheerder. Dit houdt in dat u een willekeurige functie uitvoert omdat er minder tijd is besteed aan het controleren van verschillende locaties om de gebeurtenis te leren kennen. Wanneer meerdere gebeurtenissen plaatsvinden aan of sluiten op een e-mail, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. In werkelijkheid worden bepaalde gebeurtenissen die plaatsvinden na levering van uw e-mail, vastgelegd in de kolom ' speciale actie '. Als u de gegevens van de tijdlijn van dat e-mailbericht combineert met de speciale actie die u hebt uitgevoerd voor de bezorging van e-mail, geven beheerders beheerders inzicht in hoe hun beleidsregels werken, waarbij de e-mail uiteindelijk is gerouteerd, en in sommige gevallen, wat de laatste beoordeling was.

Zie voor meer informatie over het onderzoeken van kwaadaardige e-mailberichten een [kwaadaardige e-mailbericht dat is bezorgd in Office 365](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>URL exporteren Klik op gegevens

Daarnaast is het ook mogelijk om rapporten voor URL-klikken te exporteren naar Microsoft Excel, zodat u de netwerkbericht-ID kunt bekijken, en ze klikken op Verdict, zodat u kunt zien waar de URL op het verkeer verloopt. Dit werkt als volgt: Vanaf de werkbalk Snel starten van Office 365 kunt u op de volgende keten klikken:

**Verkenner** \> **Phishing** \> weergeven **Klikken op** \> **Belangrijkste url's of URL-klikken** \> **Klik op een record om de URL-flyout te openen**

Wanneer u op een URL in de lijst klikt, ziet u in het deelvenster uitvullen een nieuwe knop exporteren. Gebruik deze knop om gegevens te verplaatsen naar een Excel-spreadsheet, zodat u deze eenvoudiger kunt rapporteren.

U kunt in het rapport realtime detecties de volgende keer naar dezelfde locatie gaan:

**Verkenner** \> **Detectie** \> van realtime **Phishing** \> weergeven **Url's** \> **Belangrijkste url's of bovenste klikken** \> **Klik op een record om de URL-flyout** \> te openen **Ga naar het tabblad klikken.**

> [!TIP]
> Netwerkbericht-ID Hiermee wijst u de Klik op terug naar specifieke e-mailberichten wanneer u in Verkenner of aan hulpmiddelen van een andere leverancier zoekt via netwerkbericht-ID. Door de netwerkbericht-ID te zoeken, leveren beheerders de specifieke e-mail die is gekoppeld aan een klik resultaat. Bij export met de correlatie-id van de netwerkbericht-ID is een snellere en krachtige analyse.

![tp_ExportClickResultAndNetworkID.png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Malware van de malware van een e-mail weergeven

U wilt malware van de malware in een e-mail weergeven, door Microsoft 365-technologie. Als u dit wilt doen, gebruikt u de [e-mail >](threat-explorer-views.md#email--malware) weergave voor malware van Explorer (of realtime gedetecteerde).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **malware**.

   ![Menu Beeld voor Verkenner](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klik op **afzender**en kies vervolgens **Basic**  >  **Detection Technology**.

   Uw detectie technologieën zijn nu beschikbaar als filters voor het rapport.

   ![Detectie technologieën voor malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Selecteer een optie en klik vervolgens op de knop **vernieuwen** om het filter toe te passen.

   ![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Het rapport wordt vernieuwd om de resultaten van malware in een e-mail te tonen met behulp van de technologie optie die u hebt geselecteerd. U kunt hier verdere analyses uitvoeren.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Bekijk gegevens over phishingberichten en klik op Verdict

Stel dat u phishingberichten via Url's wilt weergeven in een e-mail, waaronder een lijst met Url's die zijn toegestaan, geblokkeerd en genegeerd. Voor het identificeren van Url's waarop u hebt geklikt, moeten [veilige koppelingen](atp-safe-links.md) van minimaal zijn geconfigureerd. Zorg ervoor dat u [beleidsregels voor veilige verbindingen](set-up-atp-safe-links-policies.md) van 5000 hebt ingesteld voor de tijd van de bescherming en logboekregistratie van Verdicts met behulp van ATP.

Als u de Url's van de phishing in berichten en op Url's in phishingberichten wilt bekijken, gebruikt u de [e-mail > phishing-](threat-explorer-views.md#email--phish) weergave van Explorer (of realtime-detecties).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **phishing**.

   ![Menu Beeld voor Verkenner](../../media/ExplorerViewEmailPhishMenu.png)

3. Klik op **afzender**en kies vervolgens **url's**  >  **op Verdict**.

4. Selecteer een of meer opties, zoals **geblokkeerde** en **geblokkeerde overschreven**, en klik vervolgens op de knop **vernieuwen** die zich op dezelfde regel bevindt als de opties om dat filter toe te passen. (Vernieuw het browservenster niet.)

   ![Url's en klik op Verdicts](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **Url's** voor de bovenkant zijn de url's in de berichten waarop u hebt gefilterd en de actie voor de bezorging van de e-mail telt voor elke URL. In de weergave phishing-e-mail bevat deze lijst meestal geldige Url's. Hackers bestaan uit een combinatie van goede en onjuiste Url's in hun berichten om te proberen ze te ontvangen, maar ze maken de kwaadwillende koppelingen interessanter voor de gebruiker. De tabel met Url's wordt gesorteerd op totaal aantal e-mailberichten (maar deze kolom is verborgen om de weergave te vereenvoudigen).

   - Met de rechter **muisknop zijn de** gewrappte url's voor de beveiligde koppelingen waarop u hebt geklikt, gesorteerd op totale aantal klikken (deze kolom wordt ook niet weergegeven om de weergave te vereenvoudigen). Het totaal aantal per kolom geeft de veilige koppelingen aan voor elke geklikt URL. In de weergave phishing-e-mail zijn deze vaak verdachte of schadelijke Url's, maar mogelijk ook Url's die geen bedreiging zijn maar wel in phishingberichten. URL-klikken op niet-vastgemaakte koppelingen worden hier niet weergegeven.

   De twee URL-tabellen bevatten Url's voor e-mailberichten op de bezorgings actie en de locatie van de geadresseerde, en de getoonde URL-geblokte (of een waarschuwing ondanks een waarschuwing), zodat u kunt zien welke onjuiste koppelingen zijn ontvangen door gebruikers en door gebruikers te gebruiken. U kunt hier verdere analyses uitvoeren. Onder de grafiek ziet u bijvoorbeeld de belangrijkste Url's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.

   ![Verkenner-Url's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecteer een URL om meer gedetailleerde informatie weer te geven.

   > [!NOTE]
   > In het dialoogvenster URL-flyout worden de filters voor e-mailberichten verwijderd om de volledige weergave van de belichtings van de URL in uw omgeving te zien. Hiermee kunt u e-mailberichten in Explorer filteren, zodat u specifieke Url's kunt zoeken die potentiële bedreigingen zijn en vervolgens uw inzicht krijgen in de URL-belichting in uw omgeving (via het dialoogvenster URL-details) zonder dat u URL-filters hoeft toe te voegen aan de Verkenner-weergave.

## <a name="review-email-messages-reported-by-users"></a>Door gebruikers verzonden e-mailberichten bekijken

Stel dat u e-mailberichten wilt zien die gebruikers in uw organisatie als ongewenste E-mail hebben gerapporteerd, geen ongewenste E-mail of phishing via de [invoegtoepassing bericht rapporteren voor Outlook en de webversie van Outlook](enable-the-report-message-add-in.md). Als u dit wilt doen, gebruikt u de bewerkingsweergave voor [e-mail > ingediend](threat-explorer-views.md#email--submissions) van Explorer (of realtime-detecties).

1. Kies in het beveiligings & conformiteitscentrum ( [https://protection.office.com](https://protection.office.com) ) de optie **Threat Management**  >  **Explorer** (of **realtime-detectie**). (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **weergave** de optie **e-mail**  >  **inzendingen**.

   ![Menu Beeld voor Verkenner](../../media/explorer-view-menu-email-user-reported.png)

3. Klik op **afzender**en kies type **basis**  >  **rapport**.

4. Selecteer een optie, zoals **phishing**, en klik vervolgens op de knop **vernieuwen** .

   ![Door de gebruiker gerapporteerde phishing](../../media/EmailUserReportedReportType.png)

Het rapport wordt vernieuwd om gegevens weer te geven over e-mailberichten die gebruikers in uw organisatie hebben gerapporteerd als een phishing-poging. U kunt deze gegevens gebruiken om verdere analyse uit te voeren, en zo nodig uw [ATP anti-phishingfilter-beleid](configure-atp-anti-phishing-policies.md)aanpassen.

## <a name="start-automated-investigation-and-response"></a>Automatisch onderzoek en antwoord starten

> [!NOTE]
> Automatisch onderzoek en antwoord mogelijkheden zijn beschikbaar in **office 365 ATP-abonnement 2** en **Office 365 E5**.

(Nieuw!) Met [geautomatiseerd onderzoek en reactie](automated-investigation-response-office.md) kunnen uw beveiligingsactiviteiten team veel tijd in beslag houden en te zorgen voor een onderzoek en beperking van cyberattacks. U kunt niet alleen waarschuwingen configureren die een beveiligings Playbook, maar u kunt wel een automatisch onderzoek en antwoord proces starten vanuit een weergave in Explorer.

Zie voor meer informatie [: een beveiligingsbeheerder activeert een onderzoek vanuit Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Meer manieren om Explorer te gebruiken (of realtime-detecties)

Naast de scenario's die in dit artikel worden beschreven, hebt u veel meer opties voor het rapporteren van de Verkenner (of realtime-detectie).

- [Schadelijke e-mailberichten zoeken en onderzoeken die zijn afgeleverd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gevonden in SharePoint Online, OneDrive en Microsoft teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Een overzicht van de weergaven in het bedreigings Verkenner-object (en realtime-detectie)](threat-explorer-views.md)
- [Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet beschikken over de [ATP van Office 365](office-365-atp.md) om Explorer of realtime-detectie te krijgen.

- Explorer is opgenomen in Office 365 ATP-abonnement 2.
- Het rapport realtime detectie is opgenomen in Office 365 ATP (abonnement 1).
- Het toewijzen van licenties aan alle gebruikers die moet worden beveiligd door Office 365 ATP. (Verkenner of realtime-detectie laat detectiegegevens zien voor gebruikers met een licentie.)

Als u Verkenner of realtime-detectie wilt weergeven en gebruiken, moet u de juiste machtigingen hebben, zoals de machtigingen die zijn toegewezen aan een beveiligingsbeheerder of beveiligings lezer.

- Voor het beveiligings &amp; conformiteitscentrum moet een van de volgende rollen zijn toegewezen:

  - Organisatiebeheer
  - Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligings lezer

- Voor Exchange Online moet u beschikken over een van de volgende rollen die zijn toegewezen in het Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Organisatiebeheer
  - Organisatiebeheer alleen weergeven
  - Alleen-lezen functie geadresseerden
  - Nalevings beheer

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Machtigingen in het beveiligings &amp; Conformiteitscentrum](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Enkele verschillen tussen de bedreigings Verkenner en de real-time detectie

- Het rapport **realtime-detecties** is beschikbaar in Office 365 ATP, abonnement 1, terwijl de **bedreigings Verkenner** beschikbaar is in Office 365 ATP-abonnement 2.
- Met het rapport **realtime detectie** kunt u detecties in realtime weergeven. U kunt dit ook doen met **risico Verkenner** , maar u kunt ook aanvullende Details voor een bepaalde aanval weergeven.
- De weergave **alle e-mail** is beschikbaar in de **Threat Explorer** (en komt niet voor in het rapport **realtime detectie** ).
- U vindt meer filterfuncties en de beschikbare acties in de **Threat Explorer**.

Zie het artikel over de [beschikbaarheid van functies in Office 365 ATP-service beschrijving](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)voor meer informatie.

