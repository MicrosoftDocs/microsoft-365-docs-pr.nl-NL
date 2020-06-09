---
title: Threat Explorer en real-time detecties
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
description: Meer informatie over het gebruik van Explorer en realtime detecties in het Security &amp; Compliance Center om bedreigingen effectief en efficiënt te onderzoeken en erop te reageren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1aaff0662e549de3ea27db01df02ff34d192a96d
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613442"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer en real-time detecties

Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) heeft en u de [benodigde machtigingen](#required-licenses-and-permissions)hebt, hebt u **Explorer-** of **realtime detecties** (voorheen *realtime rapporten* - zie wat er [nieuw is!).](#new-features-in-threat-explorer-and-real-time-detections) Ga in het Security & Compliance Center naar **Bedreigingsbeheer**en kies **vervolgens Explorer-** _of_ **Real-time detecties**.

|||
|---|---|
|**Met ATP Plan 2 ziet u:**|**Met ATP Plan 1 ziet u:**|
|![Dreiging ontdekkingsreiziger](../../media/threatmgmt-explorer.png)|![Realtime detectie](../../media/threatmgmt-realtimedetections.png)|
|

Met Explorer (of real-time detecties) beschikt u over een krachtig rapport waarmee uw Security Operations-team bedreigingen effectief en efficiënt kan onderzoeken en erop kan reageren. Het rapport lijkt op de volgende afbeelding:

![Ga naar Threat management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Met dit rapport u:

- [Zie malware gedetecteerd door Microsoft 365 beveiligingsfuncties](#see-malware-detected-in-email-by-technology)
- [Gegevens over phishing-URL's weergeven en op vonnis klikken](#view-data-about-phishing-urls-and-click-verdict)
- [Een geautomatiseerd onderzoek- en reactieproces](#start-automated-investigation-and-response) starten vanuit een weergave in Explorer (alleen ATP-abonnement)
- ... [Onderzoek kwaadaardige e-mail, en meer!](#more-ways-to-use-explorer-or-real-time-detections)

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Nieuwe functies in Threat Explorer en real-time detecties

Drie nieuwe functies toegevoegd aan Threat Explorer en real-time detecties:

- [Voorbeeld van e-mailkoptekst en e-mailtekst downloaden](#preview-email-header-and-download-email-body)
- [Tijdlijn per e-mail](#email-timeline)
- [URL-klikgegevens exporteren](#export-url-click-data)

Deze nieuwe functies worden hieronder beschreven.

### <a name="preview-email-header-and-download-email-body"></a>Voorbeeld van e-mailkoptekst en e-mailtekst downloaden

De mogelijkheid om een voorbeeld van een e-mailkoptekst te bekijken en de e-mailbody te downloaden, zijn nieuwe functies die beschikbaar zijn in Threat Explorer. Beheerders kunnen gedownloade kopteksten/e-mailberichten analyseren op bedreigingen. Omdat het downloaden van e-mailberichten de blootstelling van informatie in gevaar kan brengen, wordt dit proces beheerd door roles-based access control (RBAC). Een nieuwe rol, *Preview,* moet worden toegevoegd aan een andere rolgroep (zoals Beveiligingsbewerkingen of Beveiligingsbeheerder) om de mogelijkheid te bieden om e-mails te downloaden en kopteksten te bekijken in de weergave alle e-mailberichten.

Maar Explorer (en real-time detecties) voegt ook nieuwe velden toe die zijn ontworpen om u een vollediger beeld te geven van waar uw e-mailberichten landen. Een deel van het doel van deze verandering is om de jacht gemakkelijker te maken voor Security Ops mensen, maar het netto resultaat is het kennen van de locatie van probleem e-mailberichten in een oogopslag.

Hoe wordt dit gedaan? De leveringsstatus is nu onderverdeeld in twee kolommen:

- **Leveringsactie** - Wat is de status van deze e-mail?
- **Leveringslocatie** - Waar is deze e-mail als gevolg hiervan doorgestuurd?

Leveringsactie is de actie die wordt ondernomen op een e-mail vanwege bestaand beleid of detecties. Dit zijn de mogelijke acties die een e-mail kan ondernemen:

|||||
|---|---|---|---|
|**Geleverd**|**Junked**|**Geblokkeerd**|**Vervangen**|
|E-mail is geleverd aan de inbox van de gebruiker of een andere map en de gebruiker heeft er rechtstreeks toegang toe.| E-mail is verzonden naar de map Ongewenste e-mail of de map Verwijderde gebruiker en de gebruiker heeft toegang tot e-mailberichten in die mappen.| E-mailberichten die in quarantaine zijn geplaatst, die zijn mislukt of zijn verwijderd en die niet toegankelijk zijn voor de gebruiker.| Alle e-mailberichten waar kwaadaardige bijlagen werden vervangen door .txt-bestanden waarin de bijlagen staan, waren schadelijk.|
|

En hier is wat de gebruiker kan zien, en wat ze niet kunnen:

|||
|---|---|
|**Toegankelijk voor eindgebruikers**|**Ontoegankelijk voor eindgebruikers**|
|Geleverd|Geblokkeerd|
|Junked|Vervangen|
|

De leveringslocatie toont de resultaten van beleid en detecties die na levering worden uitgevoerd. Het is gekoppeld aan een leveringsactie. Dit veld is toegevoegd om inzicht te geven in de actie die is ondernomen wanneer een probleemmail wordt gevonden. Hier zijn de mogelijke waarden van de levering locatie:

- **Postvak IN of map**: De e-mail staat in de postvak IN of in een map (volgens uw e-mailregels).
- **On-prem of extern**: De mailbox bestaat niet in de cloud, maar is on-premises.
- **Ongewenste map:** de e-mail bevindt zich in de map Ongewenste e-mail van een gebruiker.
- **Map Verwijderde items**: de e-mail in de map Verwijderde items van een gebruiker.
- **Quarantaine**: de e-mail in quarantaine en bevindt zich niet in het postvak van een gebruiker.
- **Mislukt:** de e-mail kan het postvak niet bereiken.
- **Verwijderd**: De e-mail gaat ergens verloren in de e-mailstroom.

### <a name="email-timeline"></a>Tijdlijn per e-mail

De **tijdlijn van e-mail** is een andere nieuwe Explorer-functie die gericht is op het verbeteren van de jachtervaring voor beheerders. Het vermindert op randomisatie omdat er minder tijd besteed aan het controleren van verschillende locaties om te proberen de gebeurtenis te begrijpen. Wanneer meerdere gebeurtenissen plaatsvinden op of in de buurt van hetzelfde tijdstip in een e-mail, worden deze gebeurtenissen weergegeven in een tijdlijnweergave. In feite worden sommige gebeurtenissen die plaatsvinden na de levering aan uw e-mail vastgelegd in de kolom 'Speciale actie'. Het combineren van de informatie uit de tijdlijn van die e-mail met de speciale actie die wordt ondernomen op de post nabezorging geeft beheerders inzicht in hoe hun beleid werkt, waar de e-mail uiteindelijk werd gerouteerd en, in sommige gevallen, wat de uiteindelijke beoordeling was.

Zie [Schadelijke e-mail die is geleverd in Office 365 voor](investigate-malicious-email-that-was-delivered.md)meer discussie over het onderzoeken van schadelijke e-mailberichten.

### <a name="export-url-click-data"></a>URL-klikgegevens exporteren

U nu ook rapporten voor URL-klikken exporteren naar Microsoft Excel om zowel hun netwerkbericht-id als hun Klik-uitspraak weer te geven, waardoor de taak om te begrijpen waar uw URL-klikverkeer vandaan komt, gemakkelijker is geworden. Dit is hoe het werkt. Klik vanaf bedreigingsbeheer bij de quick-launch van Office 365 door deze keten:

**Explorer** \> **Bekijk Phish** \> **Klikken** \> **Top-URL's of topklikken met URL's** \> **Klik op een record om URL-flyout te openen**

Wanneer u op een URL in de lijst klikt, ziet u een nieuwe knop Exporteren in het deelvenster Fly-out. Gebruik deze knop om gegevens naar een Excel-spreadsheet te verplaatsen voor eenvoudigere rapportage.

U als volgt op dezelfde locatie komen in het rapport real-time detecties:

**Explorer** \> **Real-time detecties** \> **Bekijk Phish** \> **URL's** \> **Top-URL's of topklikken** \> **Klik op een record om URL-flyout te openen** \> **Navigeer naar het tabblad Klikken.**

> [!TIP]
> Network Message ID brengt de klik terug naar specifieke e-mails wanneer u zoekt via Explorer of bijbehorende hulpprogramma's van derden via Network Message ID. Als u zoekt via de netwerkbericht-id, krijgen beheerders de specifieke e-mail die is gekoppeld aan een klikresultaat. Bij export zorgt de correlerende identificatie van Network Message ID voor een snellere en krachtigere analyse.

![tp_ExportClickResultAndNetworkID.p.](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Zie malware gedetecteerd in e-mail door technologie

Stel dat u malware wilt zien die in e-mail wordt gedetecteerd, door Microsoft 365-technologie. Gebruik hiervoor de [weergave E-mail > malware](threat-explorer-views.md#email--malware) van Explorer (of realtime detecties).

1. Kies in het Security & Compliance Center [https://protection.office.com](https://protection.office.com) ( ) de optie Threat **management**  >  **Explorer** (of **Real-time detecties).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies in het menu **Weergave** de optie **Malware e-mailen.**  >  **Malware**

   ![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klik **op Afzender**en kies **vervolgens**  >  **Basisdetectietechnologie**.

   Uw detectietechnologieën zijn nu beschikbaar als filters voor het rapport.

   ![Malwaredetectietechnologieën](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Selecteer een optie en klik op de knop **Vernieuwen** om dat filter toe te passen.

   ![Geselecteerde detectietechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Het rapport wordt vernieuwd om de resultaten te tonen die malware in e-mail heeft gedetecteerd, met behulp van de technologieoptie die u hebt geselecteerd. Vanaf hier u verdere analyse uitvoeren.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Gegevens over phishing-URL's weergeven en op vonnis klikken

Stel dat u phishingpogingen via URL's in e-mail wilt zien, inclusief een lijst met URL's die zijn toegestaan, geblokkeerd en overschreven. Voor het identificeren van URL's waarop is geklikt, moeten [ATP Safe-koppelingen](atp-safe-links.md) worden geconfigureerd. Zorg ervoor dat u [atp-beleid](set-up-atp-safe-links-policies.md) voor veilige koppelingen hebt ingesteld voor tijd-van-klikbeveiliging en het registreren van klikvonnissen door ATP Safe Links.

Als u phish-URL's in berichten en klikken op URL's in phish-berichten wilt bekijken, gebruikt u de [weergave E-> Phish](threat-explorer-views.md#email--phish) van Explorer (of realtime detecties).

1. Kies in het Security & Compliance Center [https://protection.office.com](https://protection.office.com) ( ) de optie Threat **management**  >  **Explorer** (of **Real-time detecties).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies **in het** menu Weergave **e-mail**  >  **Phish**.

   ![Menu Weergeven voor Explorer](../../media/ExplorerViewEmailPhishMenu.png)

3. Klik op **Afzender**en kies **URL's**  >  **Klik op verdict**.

4. Selecteer een of meer opties, zoals **Geblokkeerd** en **Overschreven blokkeren,** en klik op de knop **Vernieuwen** die zich op dezelfde regel bevindt als de opties om dat filter toe te passen. (Vernieuw uw browservenster niet.)

   ![URL's en klik op vonnissen](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    Het rapport wordt vernieuwd om twee verschillende URL-tabellen weer te geven op het tabblad URL onder het rapport:

   - **De belangrijkste URL's** zijn de URL's in de berichten die u hebt gefilterd en de actie voor e-mailbezorging telt voor elke URL. In de phish e-mailweergave bevat deze lijst meestal legitieme URL's. Aanvallers nemen een mix van goede en slechte URL's in hun berichten om te proberen om ze geleverd, maar ze zullen de kwaadaardige links interessanter voor de gebruiker om te klikken. De tabel met URL's wordt gesorteerd op het totale aantal e-mail (maar houd er rekening mee dat deze kolom is verborgen om de weergave te vereenvoudigen).

   - **De belangrijkste klikken** zijn de ingepakte URL's voor veilige koppelingen waarop is geklikt, gesorteerd op totale kliktelling (deze kolom wordt ook niet weergegeven om de weergave te vereenvoudigen). Totaal aantal tellingen per kolom geeft het aantal klikken op veilige koppelingen aan voor elke geklikte URL. In de phish e-mailweergave zijn dit vaker verdachte of kwaadaardige URL's, maar kunnen URL's zijn die geen bedreigingen zijn, maar in phish-berichten. URL-klikken op onverpakte koppelingen worden hier niet weergegeven.

   De twee URL-tabellen tonen de belangrijkste URL's in phishing-e-mailberichten op basis van leveringsactie en locatie, en ze tonen URL-klikken die zijn geblokkeerd (of bezocht ondanks een waarschuwing), zodat u begrijpen welke potentiële slechte links door gebruikers zijn ontvangen en waarmee gebruikers zijn gebruikt. Vanaf hier u verdere analyse uitvoeren. Onder de grafiek ziet u bijvoorbeeld de belangrijkste URL's in e-mailberichten die zijn geblokkeerd in de omgeving van uw organisatie.

   ![Explorer-URL's die zijn geblokkeerd](../../media/ExplorerPhishClickVerdictURLs.png)

   Selecteer een URL om meer gedetailleerde informatie weer te geven.
   
   > [!NOTE]
   > In het dialoogvenster URL-flyout wordt het filteren op e-mailberichten verwijderd om u de volledige weergave van de blootstelling van de URL in uw omgeving weer te geven. Hiermee u e-mailberichten in Explorer filteren op berichten waar u zich zorgen over maakt, specifieke URL's vinden die potentiële bedreigingen zijn en vervolgens uw begrip van de URL-belichting in uw omgeving (via het dialoogvenster URL-details) uitbreiden zonder URL-filters toe te voegen aan de Explorer-weergave zelf.

## <a name="review-email-messages-reported-by-users"></a>E-mailberichten bekijken die door gebruikers zijn gerapporteerd

Stel dat u e-mailberichten wilt zien die gebruikers in uw organisatie hebben gerapporteerd als ongewenste e-mail, geen ongewenste e-mail of phishing met behulp van de [invoegtoepassing Rapportbericht voor Outlook en Outlook in de web.](enable-the-report-message-add-in.md) Gebruik hiervoor de weergave [E-mail > Inzendingen](threat-explorer-views.md#email--submissions) van Explorer (of realtime detecties).

1. Kies in het Security & Compliance Center [https://protection.office.com](https://protection.office.com) ( ) de optie Threat **management**  >  **Explorer** (of **Real-time detecties).** (In dit voorbeeld wordt Explorer gebruikt.)

2. Kies **in het** menu Weergave de optie **E-mailinzendingen**  >  **Submissions**.

   ![Menu Weergeven voor Explorer](../../media/explorer-view-menu-email-user-reported.png)

3. Klik op **Afzender**en kies **vervolgens**  >  **Basisrapporttype**.

4. Selecteer een optie, zoals **Phish,** en klik op de knop **Vernieuwen.**

   ![Door de gebruiker gerapporteerde phish](../../media/EmailUserReportedReportType.png)

Het rapport wordt vernieuwd om gegevens weer te geven over e-mailberichten die mensen in uw organisatie hebben gerapporteerd als een phishingpoging. U deze informatie gebruiken om verdere analyse uit te voeren en indien nodig uw [ATP-anti-phishingbeleid](configure-atp-anti-phishing-policies.md)aan te passen.

## <a name="start-automated-investigation-and-response"></a>Automatisch onderzoek en reactie starten

> [!NOTE]
> Geautomatiseerde onderzoeks- en reactiemogelijkheden zijn beschikbaar in **Office 365 ATP Plan 2** en **Office 365 E5**.

(NIEUW!) [Geautomatiseerd onderzoek en respons](automated-investigation-response-office.md) kan uw beveiligingsteam veel tijd en moeite besparen bij het onderzoeken en beperken van cyberaanvallen. Naast het configureren van waarschuwingen die een beveiligingsspeelboek kunnen activeren, u een geautomatiseerd onderzoek- en reactieproces starten vanuit een weergave in Explorer.

Zie [Voorbeeld: Een beveiligingsbeheerder activeert een onderzoek vanuit Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)voor meer informatie hierover.

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Meer manieren om Explorer (of realtime detecties) te gebruiken

Naast de scenario's die in dit artikel worden beschreven, hebt u nog veel meer rapportageopties beschikbaar met Explorer (of realtime detecties).

- [Kwaadaardige e-mail zoeken en onderzoeken die is bezorgd](investigate-malicious-email-that-was-delivered.md)
- [Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)
- [Krijg een overzicht van de weergaven in Threat Explorer (en realtime detecties)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Vereiste licenties en machtigingen

U moet [office 365 ATP](office-365-atp.md) hebben om Explorer- of realtime detecties te krijgen.

- Explorer is opgenomen in Office 365 ATP-abonnement 2.
- Het rapport realtime detecties is opgenomen in Office 365 ATP Plan 1.
- Ben van plan licenties toe te wijzen voor alle gebruikers die moeten worden beschermd door Office 365 ATP. (Explorer- of realtimedetecties tonen detectiegegevens voor gelicentieerde gebruikers.)

Als u Explorer- of realtimedetecties wilt weergeven en gebruiken, moet u over de juiste machtigingen beschikken, zoals die welke zijn verleend aan een beveiligingsbeheerder of beveiligingslezer.

- Voor het Security &amp; Compliance Center moet u een van de volgende rollen toegewezen hebben:

  - Organisatiebeheer
  - Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligingslezer

- Voor Exchange Online moet u een van de volgende rollen hebben toegewezen in het Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Organisatiebeheer
  - Alleen-weergeven organisatiebeheer
  - Rol alleen weergeven ontvangers
  - Compliance Management

Zie de volgende bronnen voor meer informatie over rollen en machtigingen:

- [Machtigingen in het Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Enkele verschillen tussen Threat Explorer en real-time detecties

- Het **realtime detectierapport** is beschikbaar in Office 365 ATP Plan 1, terwijl **Threat Explorer** beschikbaar is in Office 365 ATP Plan 2.
- Met **het real-time detectierapport** u detecties in realtime bekijken. **Threat Explorer** doet dit ook, maar stelt u ook in staat om extra details voor een bepaalde aanval te bekijken.
- Een **e-mailweergave alle** is beschikbaar in **Threat Explorer** (en staat niet in het rapport **realtime detecties).**
- Meer filtermogelijkheden en beschikbare acties zijn opgenomen in **Threat Explorer**.

Zie [Office 365 ATP-servicebeschrijving: Beschikbaarheid van functies voor ATP-abonnementen (Advanced Threat Protection).](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)
