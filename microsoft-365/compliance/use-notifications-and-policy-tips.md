---
title: Send email notifications and show policy tips for DLP policies (E-mailmeldingen verzenden en beleidstips tonen voor DLP-beleid)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleNotifyUser
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.custom: seo-marvel-apr2020
description: Lees hoe u een beleidstip toevoegt aan een DLP-beleid (Data Loss Prevention) om een gebruiker te laten weten dat hij of zij werkt met inhoud die in strijd is met een DLP-beleid.
ms.openlocfilehash: f4a4700f4250289ee3614320499bc7fbaa16d582
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007535"
---
# <a name="send-email-notifications-and-show-policy-tips-for-dlp-policies"></a>Send email notifications and show policy tips for DLP policies (E-mailmeldingen verzenden en beleidstips tonen voor DLP-beleid)

U kunt een DLP-beleid (Data Loss Prevention) gebruiken om gevoelige informatie in Office 365 te identificeren, te bewaken en te beveiligen. U wilt dat personen in uw organisatie die met deze gevoelige informatie werken, voldoen aan uw DLP-beleid, maar u wilt ze niet onnodig blokkeren om hun werk te doen. Hier kunnen e-mailmeldingen en beleidstips u helpen.
  
![Berichtenbalk toont beleidstip in Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
Een beleidstip is een melding of waarschuwing die wordt weergegeven wanneer iemand werkt met inhoud die in strijd is met een DLP-beleid, bijvoorbeeld inhoud zoals een Excel-werkmap op een OneDrive voor Bedrijven-site die persoonlijk identificeerbare informatie (PII) bevat en die wordt gedeeld met een externe gebruiker.
  
U kunt e-mailmeldingen en beleidstips gebruiken om de bekendheid te vergroten en mensen te informeren over het beleid van uw organisatie. U kunt personen ook de optie geven om het beleid te overschrijven, zodat ze niet worden geblokkeerd als ze een geldige zakelijke behoefte hebben of als het beleid een onwaar positief detecteert.
  
Wanneer u in het Compliancecentrum een DLP-beleid maakt, kunt u de gebruikersmeldingen zo configureren dat:
  
- Stuur een e-mailmelding naar de personen die u kiest die het probleem beschrijven.
> [!NOTE]
> Meldingen worden onbeveiligd verzonden.
    
- Een beleidstip weergeven voor inhoud die in strijd is met het DLP-beleid:
    
  - Voor e-mail in de webversie van Outlook en Outlook 2013 en hoger wordt de beleidstip boven aan een bericht boven de geadresseerden weergegeven terwijl het bericht wordt samengesteld.
    
  - Voor documenten in een OneDrive voor Bedrijven-account of SharePoint Online-site wordt de beleidstip aangegeven door een waarschuwingspictogram dat op het item wordt weergegeven. Als u meer informatie wilt weergeven,  kunt u een item selecteren en vervolgens het pictogram Informatiegegevens kiezen in de rechterbovenhoek van de pagina om het ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) detailvenster te openen. 
    
  - Voor Excel-, PowerPoint- en Word-documenten die zijn opgeslagen op een OneDrive voor Bedrijven-site of SharePoint Online-site die is opgenomen in het DLP-beleid, wordt de beleidstip weergegeven op de berichtenbalk en de weergave Backstage ( **Bestandsmenu** \> **Info**).
    
## <a name="add-user-notifications-to-a-dlp-policy"></a>Gebruikersmeldingen toevoegen aan een DLP-beleid

Wanneer u een DLP-beleid maakt, kunt u **gebruikersmeldingen inschakelen.** Wanneer gebruikersmeldingen zijn ingeschakeld, verzendt Microsoft 365 zowel e-mailmeldingen als beleidstips. U kunt aanpassen naar wie e-mailberichten worden verzonden, de e-mailtekst en de tekst van de beleidstip.
  
1. Ga naar [https://protection.office.com](https://protection.office.com).
    
2. Meld u aan met uw werk- of schoolaccount. U bent nu in het Beveiligings &amp; compliancecentrum.
    
3. In het linkernavigatienavigatiecentrum van het Beveiligings &amp; compliancecentrum \> wordt het \>  \> **preventiebeleid** \> **voor gegevensverlies + Een beleid maken.**
    
    ![Knop Beleid maken](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Kies de DLP-beleidssjabloon die de typen gevoelige informatie beschermt die u volgende \> **nodig hebt.**
    
    Als u wilt beginnen met een lege sjabloon, kiest **u Aangepast** \> **aangepast beleid** \> **Volgende.**
    
5. Noem het beleid \> **Volgende**.
    
6. Als u de locaties wilt kiezen die u wilt beveiligen met het DLP-beleid, gaat u op een van de volgende gebieden te werk:
    
   - Kies **Alle locaties in Office 365** \> **Volgende.**
    
   - Kies **Laat me specifieke locaties kiezen** \> **Volgende.**
    
   Als u een hele locatie wilt opnemen of uitsluiten, zoals alle Exchange-e-mail- of alle OneDrive-accounts, schakelt u de **status** van die locatie in of uit. 
    
   Als u alleen specifieke SharePoint-sites of OneDrive-accounts wilt opnemen, schakelt u de **status** in en klikt u op de koppelingen **onder** Opnemen om specifieke sites of accounts te kiezen. 
    
7. Kies **Volgende geavanceerde instellingen** \> **gebruiken.**
    
8. Kies **+ Nieuwe regel**.
    
9. Schakel in de regeleditor onder **Gebruikersmeldingen** de status in.
    
    ![Sectie Gebruikersmeldingen van regeleditor](../media/47705927-c60b-4054-a072-ab914f33d15d.png)

> [!NOTE]
> DLP-beleid is van toepassing op alle documenten die overeenkomen met het beleid, ongeacht of deze documenten nieuw of bestaand zijn. Een e-mailmelding wordt echter alleen gegenereerd wanneer nieuwe inhoud overeenkomt met een bestaand DLP-beleid. Bestaande inhoud is beveiligd, maar genereert geen gebruikersmelding via e-mail.
  
## <a name="options-for-configuring-email-notifications"></a>Opties voor het configureren van e-mailmeldingen

Voor elke regel in een DLP-beleid kunt u het volgende doen:
  
- Stuur de melding naar de personen die u kiest. Deze personen kunnen de eigenaar van de inhoud zijn, de persoon die de inhoud het laatst heeft gewijzigd, de eigenaar van de site waar de inhoud is opgeslagen of een specifieke gebruiker.
    
- Pas de tekst aan die in de melding is opgenomen met HTML of tokens. Zie de onderstaande sectie voor meer informatie.
    
> [!NOTE]
>  E-mailmeldingen kunnen alleen worden verzonden naar afzonderlijke geadresseerden, niet naar groepen of distributielijsten. Alleen nieuwe inhoud activeert een e-mailmelding. Als u bestaande inhoud bewerkt, worden beleidstips in gang gezet, maar geen e-mailmelding. 
  
![Opties voor e-mailmeldingen](../media/4e7b9500-2a78-44e6-9067-09f4bfd50301.png)
  
### <a name="default-email-notification"></a>Standaardmelding voor e-mail

Meldingen hebben een onderwerpregel die begint met de actie die is ondernomen, zoals 'Melding', 'Bericht geblokkeerd' voor e-mail of 'Access Blocked' voor documenten. Als de melding over een document gaat, bevat de berichtgedeelte van het bericht een koppeling naar de site waar het document is opgeslagen en wordt de beleidstip voor het document geopend, waar u eventuele problemen kunt oplossen (zie de onderstaande sectie over beleidstips). Als de melding over een bericht gaat, bevat de melding als bijlage het bericht dat overeenkomt met een DLP-beleid.
  
![Meldingsbericht](../media/35813d40-5fd8-425f-9624-55655e74fa6b.png)
  
In meldingen wordt standaard tekst weergegeven die lijkt op het volgende voor een item op een site. De meldingstekst wordt afzonderlijk geconfigureerd voor elke regel, zodat de weergegeven tekst verschilt, afhankelijk van de regel die is afgestemd.

|**Als de DLP-beleidsregel dit doet...**|**In de standaardmelding voor SharePoint- of OneDrive voor Bedrijven-documenten staat dit...**|**In de standaardmelding voor Outlook-berichten staat dit...**|
|:-----|:-----|:-----|
|Hiermee verzendt u een melding, maar is overschrijven niet toegestaan  <br/> |Dit item is in strijd met een beleid in uw organisatie.  <br/> |Uw e-mailbericht is in strijd met een beleid in uw organisatie.  <br/> |
|Blokkeert toegang, verzendt een melding en staat overschrijven toe  <br/> |Dit item is in strijd met een beleid in uw organisatie. Als u dit conflict niet op kunt lossen, is de toegang tot dit bestand mogelijk geblokkeerd.  <br/> |Uw e-mailbericht is in strijd met een beleid in uw organisatie. Het bericht is niet bij alle geadresseerden bezorgd.  <br/> |
|Blokkeert toegang en verzendt een melding  <br/> |Dit item is in strijd met een beleid in uw organisatie. Toegang tot dit item is geblokkeerd voor iedereen, behalve de eigenaar, de laatste modifier en de beheerder van de primaire siteverzameling.  <br/> |Uw e-mailbericht is in strijd met een beleid in uw organisatie. Het bericht is niet bij alle geadresseerden bezorgd.  <br/> |
   
### <a name="custom-email-notification"></a>Aangepaste e-mailmelding

U kunt een aangepaste e-mailmelding maken in plaats van de standaardmelding naar uw eindgebruikers of beheerders te verzenden. De aangepaste e-mailmelding ondersteunt HTML en heeft een limiet van 5.000 tekens. U kunt HTML gebruiken om afbeeldingen, opmaak en andere huisstijl op te nemen in de melding.
  
U kunt ook de volgende tokens gebruiken om de e-mailmelding aan te passen. Deze tokens zijn variabelen die worden vervangen door specifieke informatie in de melding die wordt verzonden.

|**Token**|**Beschrijving**|
|:-----|:-----|
|%%AppliedActions%%  <br/> |De acties die zijn toegepast op de inhoud.  <br/> |
|%%ContentURL%%  <br/> |De URL van het document op de SharePoint Online-site of OneDrive voor Bedrijven-site.  <br/> |
|%%MatchedConditions%%  <br/> |De voorwaarden die zijn afgestemd op de inhoud. Gebruik dit token om personen te informeren over mogelijke problemen met de inhoud.  <br/> |
   
![Meldingsbericht waarin wordt weergegeven waar tokens worden weergegeven](../media/cd3f36b3-40db-4f30-99e4-190750bd1955.png)
  
## <a name="options-for-configuring-policy-tips"></a>Opties voor het configureren van beleidstips

Voor elke regel in een DLP-beleid kunt u beleidstips configureren voor:
  
- Laat de persoon weten dat de inhoud strijdig is met een DLP-beleid, zodat deze actie kan ondernemen om het conflict op te lossen. U kunt de standaardtekst gebruiken (zie de onderstaande tabellen) of aangepaste tekst invoeren over het specifieke beleid van uw organisatie.
    
- Sta de persoon toe het DLP-beleid te overschrijven. Desgewenst kunt u het volgende doen:
    
  - De persoon verplicht een zakelijke rechtvaardiging in te voeren voor het overschrijven van het beleid. Deze informatie wordt vastgelegd en u kunt deze weergeven in de DLP-rapporten in **de sectie Rapporten** van het Beveiligings &amp; compliancecentrum. 
    
  - Sta de persoon toe een fout-positief te melden en het DLP-beleid te overschrijven. Deze informatie wordt ook geregistreerd voor rapportage, zodat u false positives kunt gebruiken om uw regels aan te passen.
    
![Opties voor beleidstips](../media/0d2f2c68-028a-4900-afe6-1d9fce5303ef.png)
  
U hebt bijvoorbeeld mogelijk een DLP-beleid toegepast op OneDrive voor Bedrijven-sites die persoonlijke identificeerbare gegevens (PII) detecteren en dit beleid heeft drie regels:
  
1. Eerste regel: Als er minder dan vijf exemplaren van deze gevoelige informatie worden gedetecteerd in een  document en het document wordt gedeeld met personen binnen de organisatie, wordt met de actie Een melding verzenden een beleidstip weergegeven. Voor beleidstips zijn geen opties voor overschrijven nodig, omdat deze regel alleen personen op de hoogte stelt en de toegang niet blokkeert. 
    
2. Tweede regel: Als er meer dan vijf exemplaren van deze gevoelige informatie worden gedetecteerd in  een document en het document wordt gedeeld met  personen binnen de organisatie, worden met de actie Toegang tot inhoud blokkeren de machtigingen voor het bestand beperkt en kunnen personen met de actie Een melding verzenden de acties in deze regel overschrijven door een zakelijke rechtvaardiging te geven. Het bedrijf van uw organisatie vereist soms interne personen om PII-gegevens te delen en u wilt niet dat uw DLP-beleid dit werk blokkeert. 
    
3. Derde regel: Als er meer dan vijf exemplaren van deze gevoelige informatie worden gedetecteerd in  een document en het document wordt gedeeld met  personen buiten de organisatie, worden met de actie Toegang tot inhoud blokkeren de machtigingen voor het bestand beperkt en kunnen personen met de actie Een melding verzenden de acties in deze regel niet overschrijven omdat de gegevens extern worden gedeeld. In geen geval mogen personen in uw organisatie PII-gegevens delen buiten de organisatie. 
    
Hier zijn enkele goede punten om te begrijpen over het gebruik van een beleidstip om een regel te overschrijven:
  
- De optie om te overschrijven is per regel en overschrijven alle acties in de regel (behalve het verzenden van een melding, die niet kan worden overgenomen).
    
- Het is mogelijk dat inhoud aan verschillende regels in een DLP-beleid kan voldoen, maar alleen de beleidstip van de meest beperkende regel met de hoogste prioriteit wordt weergegeven. Een beleidstip van een regel die toegang tot inhoud blokkeert, wordt bijvoorbeeld weergegeven via een beleidstip van een regel die alleen een melding verzendt. Dit voorkomt dat personen een trapsgepunt met beleidstips zien.
    
- Als de beleidstips in de meest beperkende regel toestaan dat personen de regel overschrijven, worden ook andere regels overgenomen die overeenkomen met de inhoud door deze regel te vervangen.
    
## <a name="policy-tips-on-onedrive-for-business-sites-and-sharepoint-online-sites"></a>Beleidstips op OneDrive voor Bedrijven-sites en SharePoint Online-sites

Wanneer een document op een OneDrive voor Bedrijven-site of SharePoint Online-site overeenkomt met een regel in een DLP-beleid en voor die regel beleidstips worden gebruikt, worden in de beleidstips speciale pictogrammen weergegeven in het document:
  
1. Als met de regel een melding over het bestand wordt weergegeven, wordt het waarschuwingspictogram weergegeven.
    
2. Als de regel de toegang tot het document blokkeert, wordt het geblokkeerde pictogram weergegeven.
    
   ![Pictogrammen voor beleidstips voor documenten in een OneDrive-account](../media/d3e9f772-03f9-4d28-82f8-3064784332a2.png)
  
Als u actie wilt ondernemen voor een document, kunt u een item selecteren met het pictogram Informatiegegevens in de rechterbovenhoek van de pagina om het \>  ![ ](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) detailvenster \> **Beleidstip weergeven te openen.**
  
De beleidstip bevat de problemen met de inhoud en als de beleidstips met  deze opties zijn geconfigureerd, kunt u Oplossen kiezen **en** vervolgens de beleidstip of Fout-positief rapporteren overschrijven.  
  
![Informatievenster met beleidstip](../media/0a191e70-80f0-4702-90f4-7a5b7aabcaab.png)
  
![Beleidstip met optie om over te gaan](../media/e250bff9-41d5-4ce4-82ea-1dc2d043fab1.png)
  
DLP-beleid wordt gesynchroniseerd met sites en inhoud wordt regelmatig en asynchroon geëvalueerd, dus er kan een korte vertraging zijn tussen de tijd dat u het DLP-beleid maakt en de tijd dat u beleidstips begint te zien. Er kan een soortgelijke vertraging zijn vanaf het moment dat u een beleidstip opsleed of overschrijven tot wanneer het pictogram op het document op de site verdwijnt.
  
### <a name="default-text-for-policy-tips-on-sites"></a>Standaardtekst voor beleidstips op sites

In beleidstips wordt standaard tekst weergegeven die lijkt op de volgende tekst voor een item op een site. De meldingstekst wordt afzonderlijk geconfigureerd voor elke regel, zodat de weergegeven tekst verschilt, afhankelijk van de regel die is afgestemd.

|**Als de DLP-beleidsregel dit doet...**|**In de standaard beleidstip wordt dit weergegeven...**|
|:-----|:-----|
|Hiermee verzendt u een melding, maar is overschrijven niet toegestaan  <br/> |Dit item is in strijd met een beleid in uw organisatie.  <br/> |
|Blokkeert toegang, verzendt een melding en staat overschrijven toe  <br/> |Dit item is in strijd met een beleid in uw organisatie. Als u dit conflict niet op kunt lossen, is de toegang tot dit bestand mogelijk geblokkeerd.  <br/> |
|Blokkeert toegang en verzendt een melding  <br/> |Dit item is in strijd met een beleid in uw organisatie. Toegang tot dit item is geblokkeerd voor iedereen, behalve de eigenaar, de laatste modifier en de beheerder van de primaire siteverzameling.  <br/> |
   
### <a name="custom-text-for-policy-tips-on-sites"></a>Aangepaste tekst voor beleidstips op sites

U kunt de tekst voor beleidstips afzonderlijk aanpassen van de e-mailmelding. In tegenstelling tot aangepaste tekst voor e-mailmeldingen (zie bovenstaande sectie), accepteert aangepaste tekst voor beleidstips geen HTML of tokens. In plaats daarvan is aangepaste tekst voor beleidstips alleen tekst zonder tekst met een limiet van 256 tekens.
  
## <a name="policy-tips-in-outlook-on-the-web-and-outlook-2013-and-later"></a>Beleidstips in de webversie van Outlook en Outlook 2013 en hoger

Wanneer u een nieuw e-mailbericht opmaakt in de webversie van Outlook en Outlook 2013 en hoger, ziet u een beleidstip als u inhoud toevoegt die overeenkomt met een regel in een DLP-beleid. Deze regel gebruikt beleidstips. De beleidstip wordt boven aan het bericht boven de geadresseerden weergegeven terwijl het bericht wordt samengesteld.
  
![Beleidstip boven aan een bericht dat wordt samengesteld](../media/9b3b6b74-17c5-4562-82d5-d17ecaaa8d95.png)
  
Beleidstips werken of de gevoelige informatie wordt weergegeven in de berichtbewerker, onderwerpregel of zelfs een berichtbijlage zoals hier wordt weergegeven.
  
![Beleidstip waaruit blijkt dat een bijlage strijdig is met een DLP-beleid](../media/59ae6655-215f-47d9-ad1d-39c0d1e61740.png)
  
Als de beleidstips zijn geconfigureerd om overschrijven  toe te staan, kunt u Details overschrijven tonen kiezen door een zakelijke rechtvaardiging in te voeren of een fout-positieve \>  \> \> **overschrijven te rapporteren.**
  
![Beleidstip in bericht uitgebreid om optie Overschrijven weer te geven](../media/28bfb997-48a6-41f0-8682-d5e62488458a.png)
  
![Dialoogvenster Beleidstip waarin u de beleidstip kunt overschrijven](../media/f97e836c-04bd-44b4-aec6-ed9526ea31f8.png)
  
Houd er rekening mee dat wanneer u gevoelige informatie aan een e-mailbericht toevoegt, er mogelijk latentie is tussen wanneer de gevoelige informatie wordt toegevoegd en wanneer de beleidstip wordt weergegeven.

### <a name="outlook-2013-and-later-supports-showing-policy-tips-for-only-some-conditions"></a>Outlook 2013 en hoger ondersteunt het weergeven van beleidstips voor slechts enkele voorwaarden

Momenteel worden in Outlook 2013 en hoger alleen beleidstips weergegeven voor deze voorwaarden:

- Inhoud bevat
- Inhoud wordt gedeeld

Uitzonderingen worden beschouwd als voorwaarden en al deze voorwaarden werken in Outlook, waar ze overeenkomen met inhoud en beschermende acties voor inhoud afdwingen. Maar het weergeven van beleidstips voor gebruikers wordt nog niet ondersteund. 
  
### <a name="policy-tips-in-the-exchange-admin-center-vs-the-security-amp-compliance-center"></a>Beleidstips in het Exchange-beheercentrum versus het Beveiligings &amp; compliancecentrum

Beleidstips kunnen werken met DLP-beleid en e-mailstroomregels die zijn gemaakt in het Exchange-beheercentrum of met DLP-beleid dat is gemaakt in het Beveiligings &amp; compliancecentrum, maar niet beide. Dit komt omdat deze beleidsregels op verschillende locaties worden opgeslagen, maar beleidstips kunnen slechts op één locatie worden gebruikt.
  
Als u beleidstips hebt geconfigureerd in het Exchange-beheercentrum, worden beleidstips die u configureert in het Beveiligings compliancecentrum niet weergegeven voor gebruikers in de webversie van Outlook en Outlook 2013 en hoger totdat u de tips in het Exchange-beheercentrum &amp; uitwisselt. Dit zorgt ervoor dat uw huidige Exchange-regels voor e-mailstroom (ook wel transportregels genoemd) blijven werken totdat u ervoor kiest om over te schakelen naar het Beveiligings &amp; compliancecentrum.
  
Hoewel beleidstips slechts vanaf één locatie kunnen worden gebruikt, worden er altijd e-mailmeldingen verzonden, zelfs als u DLP-beleid gebruikt in zowel het Beveiligings compliancecentrum als het &amp; Exchange-beheercentrum.
  
### <a name="default-text-for-policy-tips-in-email"></a>Standaardtekst voor beleidstips in e-mail

In beleidstips wordt standaard tekst weergegeven die lijkt op de volgende tekst voor e-mail.

|**Als de DLP-beleidsregel dit doet...**|**In de standaard beleidstip wordt dit weergegeven...**|
|:-----|:-----|
|Hiermee verzendt u een melding, maar is overschrijven niet toegestaan  <br/> |Uw e-mail is in strijd met een beleid in uw organisatie.  <br/> |
|Blokkeert toegang, verzendt een melding en staat overschrijven toe  <br/> |Uw e-mail is in strijd met een beleid in uw organisatie.  <br/> |
|Blokkeert toegang en verzendt een melding  <br/> |Uw e-mail is in strijd met een beleid in uw organisatie.  <br/> |
   
## <a name="policy-tips-in-excel-powerpoint-and-word"></a>Beleidstips in Excel, PowerPoint en Word

Wanneer personen werken met gevoelige inhoud in de bureaubladversies van Excel, PowerPoint en Word, kunnen beleidstips hen in realtime laten weten dat de inhoud strijdig is met een DLP-beleid. Hiervoor moet u het volgende doen:
  
- Het Office-document wordt opgeslagen op een OneDrive voor Bedrijven-site of SharePoint Online-site.
    
- De site is opgenomen in een DLP-beleid dat is geconfigureerd voor het gebruik van beleidstips.
    
Office-bureaubladprogramma's synchroniseren DLP-beleid automatisch rechtstreeks vanuit Office 365 en scannen vervolgens uw documenten om ervoor te zorgen dat ze niet in strijd zijn met uw DLP-beleid en beleidstips in realtime weergeven.

> [!NOTE]
> Office-bureaublad-apps scannen documenten zelf om te bepalen of DLP-beleidstips moeten worden weergegeven. er worden geen beleidstips weergegeven die sharePoint Online-sites of OneDrive voor Bedrijven-sites al hebben vastgesteld, moeten worden weergegeven in een bestand. Hierdoor ziet u mogelijk niet altijd een DLP-beleidstip in de bureaublad-apps die u ziet op de SharePoint Online-sites of OneDrive voor Bedrijven-sites. In de webtoepassingen van Office worden echter alleen DLP-beleidstips weergegeven die sharePoint Online-sites of OneDrive voor Bedrijven-sites al hebben vastgesteld.
  
Afhankelijk van hoe u de beleidstips in het DLP-beleid configureert, kunnen personen ervoor kiezen om de beleidstip te negeren, het beleid te negeren met of zonder zakelijke rechtvaardiging, of een onwaar positief rapport te rapporteren.
  
Beleidstips worden weergegeven op de berichtenbalk.
  
![Berichtenbalk toont beleidstip in Excel 2016](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)
  
En beleidstips worden ook weergegeven in de weergave Backstage (op het **tabblad** Bestand). 
  
![Backstage toont beleidstip in Excel 2016](../media/44c561f6-8f3f-4878-b1b0-b7543f8a4120.png)
  
Als beleidstips in het DLP-beleid met deze  opties zijn geconfigureerd, kunt u Oplossen kiezen om **een** beleidstip te overschrijven of **Een** onwaar positief melden. 
  
![Opties voor beleidstip in Backstage in Excel 2016](../media/5b3857ba-907e-456e-ae43-888b594c049c.png)
  
In elk van deze Office-bureaubladprogramma's kunnen personen ervoor kiezen beleidstips uit te schakelen. Als dit is uitgeschakeld, worden beleidstips die eenvoudige meldingen zijn, niet weergegeven in de weergave Berichtenbalk of Backstage (op het **tabblad** Bestand). Beleidstips over blokkeren en overschrijven worden echter nog steeds weergegeven en ze ontvangen nog steeds de e-mailmelding. Bovendien wordt het document niet vrijgesteld van DLP-beleid dat is toegepast op het document als beleidstips worden uitgeschakeld. 
  
### <a name="default-text-for-policy-tips-in-excel-2016-powerpoint-2016-and-word-2016"></a>Standaardtekst voor beleidstips in Excel 2016, PowerPoint 2016 en Word 2016

In beleidstips wordt standaard tekst weergegeven die lijkt op het volgende in de berichtenbalk en backstage-weergave van een geopend document. De meldingstekst wordt afzonderlijk geconfigureerd voor elke regel, zodat de weergegeven tekst verschilt, afhankelijk van de regel die is afgestemd.

|**Als de DLP-beleidsregel dit doet...**|**In de standaard beleidstip wordt dit weergegeven...**|
|:-----|:-----|
|Hiermee verzendt u een melding, maar is overschrijven niet toegestaan  <br/> |Dit bestand is in strijd met een beleid in uw organisatie. Ga naar het **menu** Bestand voor meer informatie.  <br/> |
|Blokkeert toegang, verzendt een melding en staat overschrijven toe  <br/> |Dit bestand is in strijd met een beleid in uw organisatie. Als u dit conflict niet op kunt lossen, is de toegang tot dit bestand mogelijk geblokkeerd. Ga naar het **menu** Bestand voor meer informatie.  <br/> |
|Blokkeert toegang en verzendt een melding  <br/> |Dit bestand is in strijd met een beleid in uw organisatie. Als u dit conflict niet op kunt lossen, is de toegang tot dit bestand mogelijk geblokkeerd. Ga naar het **menu** Bestand voor meer informatie.  <br/> |
   
### <a name="custom-text-for-policy-tips-in-excel-powerpoint-and-word"></a>Aangepaste tekst voor beleidstips in Excel, PowerPoint en Word

U kunt de tekst voor beleidstips afzonderlijk aanpassen van de e-mailmelding. In tegenstelling tot aangepaste tekst voor e-mailmeldingen (zie bovenstaande sectie), accepteert aangepaste tekst voor beleidstips geen HTML of tokens. In plaats daarvan is aangepaste tekst voor beleidstips alleen tekst zonder tekst met een limiet van 256 tekens.
  
## <a name="more-information"></a>Meer informatie

- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)    
- [Een DLP-beleid maken vanuit een sjabloon](create-a-dlp-policy-from-a-template.md)
- [DLP-beleidsvoorwaarden, uitzonderingen en acties (voorbeeld)](./dlp-microsoft-teams.md) 
- [Een DLP-beleid maken om documenten te beveiligen met FCI of andere eigenschappen](protect-documents-that-have-fci-or-other-properties.md)
- [Wat zijn de DLP-beleidssjablonen?](what-the-dlp-policy-templates-include.md)
- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)