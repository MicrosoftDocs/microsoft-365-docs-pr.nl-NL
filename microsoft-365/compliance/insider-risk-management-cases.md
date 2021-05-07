---
title: Cases voor insiderrisicobeheer
description: Meer informatie over gevallen van insiderrisicobeheer in Microsoft 365
keywords: Microsoft 365, insider risk management, risk management, compliance
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 5b59fb57ebd17050624ce36805558dcd1eef0503
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "52162708"
---
# <a name="insider-risk-management-cases"></a>Cases voor insiderrisicobeheer

Cases vormen het hart van insider-risicobeheer en stellen u in staat om problemen die zijn gegenereerd door risico-indicatoren die in uw beleid zijn gedefinieerd, grondig te onderzoeken en op te lossen. Gevallen worden handmatig gemaakt op het gebied van waarschuwingen in situaties waarin verdere actie nodig is om een complianceprobleem voor een gebruiker aan te pakken. Elk geval is beperkt tot één gebruiker en meerdere waarschuwingen voor de gebruiker kunnen worden toegevoegd aan een bestaand geval of aan een nieuw geval. 

Nadat u de details van een zaak hebt onderzocht, kunt u actie ondernemen door:

- de gebruiker een melding sturen
- het oplossen van de zaak als goedaardig
- het geval delen met uw ServiceNow-exemplaar of met een e-mailontvanger
- de zaak voor een onderzoek Advanced eDiscovery escaleren

Bekijk de [video Insider Risk Management Investigation and Escalation](https://www.youtube.com/watch?v=UONUSmkRC8s) voor een overzicht van hoe zaken worden onderzocht en beheerd in insider risk management.

## <a name="cases-dashboard"></a>Cases dashboard

Met het dashboard Cases **voor insiderrisicobeheer** kunt u zaken bekijken en handelen. Elke rapportwidget op het dashboard bevat gegevens van de afgelopen 30 dagen.

- **Actieve zaken:** Het totale aantal actieve zaken dat wordt onderzocht.
- **Zaken in de afgelopen 30 dagen:** het totale aantal zaken dat is gemaakt, gesorteerd op *actieve* en *gesloten* status.
- **Statistieken:** Gemiddelde tijd van actieve gevallen, weergegeven in uren, dagen of maanden.

De hoofdwachtrij bevat alle actieve en gesloten zaken voor uw organisatie, naast de huidige status van de volgende hoofdzakenkenmerken:

- **Naam van zaak:** de naam van de zaak, gedefinieerd wanneer een waarschuwing wordt bevestigd en de zaak wordt gemaakt.  
- **Status:** De status van de zaak, *actief* of *gesloten.*
- **Gebruiker:** De gebruiker voor de zaak. Als anonimisatie voor gebruikersnamen is ingeschakeld, worden geanonimiseerde gegevens weergegeven.
- **Geopende** tijdscase: de tijd die is verstreken sinds de zaak is geopend.
- **Totaalbeleidswaarschuwingen:** het aantal beleidswedstrijden dat in de zaak is opgenomen. Dit aantal kan toenemen als er nieuwe waarschuwingen aan de zaak worden toegevoegd.
- **Case laatst bijgewerkt:** De tijd die is verstreken sinds er een toegevoegde notitie of wijziging is toegevoegd in de case state.
- **Laatst bijgewerkt door**: De naam van de insider-risicobeheeranalist of onderzoeker die de zaak het laatst heeft bijgewerkt.

![Insider risk management Cases dashboard](../media/insider-risk-cases-dashboard.png)

Gebruik het **besturingselement** Zoeken om naam van een zaak te zoeken naar specifieke tekst en gebruik het casefilter om zaken te sorteren op de volgende kenmerken:

- Status
- Geopende tijdscase, begindatum en einddatum
- Laatst bijgewerkt, begindatum en einddatum

## <a name="filter-cases"></a>Filter cases

Afhankelijk van het aantal en het type actief beleid voor insiderrisicobeheer in uw organisatie, kan het controleren van een grote wachtrij met zaken lastig zijn. Met behulp van hoofdzakenfilters kunnen analisten en onderzoekers zaken op verschillende kenmerken sorteren. Als u waarschuwingen wilt filteren op het **dashboard Cases,** selecteert u het **besturingselement** Filter. U kunt zaken filteren op een of meer kenmerken:

- **Status:** Selecteer een of meer statuswaarden om de lijst met zaken te filteren. De opties zijn *Actief* en *Gesloten.*
- **Geopende** tijdscase: Selecteer de begin- en einddatums voor wanneer de zaak is geopend.
- **Laatst bijgewerkt:** Selecteer de begin- en einddatums voor wanneer de zaak is bijgewerkt.

## <a name="investigate-a-case"></a>Een zaak onderzoeken

Nader onderzoek naar waarschuwingen voor insiderrisicobeheer is essentieel voor het nemen van juiste corrigerende acties. Insider risk management cases zijn het centrale beheerhulpmiddel om dieper in te gaan op de geschiedenis van gebruikersrisicoactiviteit, waarschuwingsdetails, de reeks risicogebeurtenissen en om de inhoud en berichten te verkennen die aan risico's worden blootgesteld. Risicoanalisten en -onderzoeker gebruiken ook cases om feedback en notities te centraliseren en case-resolutie te verwerken.

Als u een zaak selecteert, worden de hulpprogramma's voor casebeheer geopend en kunnen analisten en onderzoekers de details van zaken bekijken.

### <a name="case-overview"></a>Overzicht van zaak

Het **tabblad Overzicht van** zaak bevat een overzicht van de casedetails voor risicoanalisten en -onderzoeker. Het bevat de volgende informatie in het **gebied Over dit geval**

- **Status:** De huidige status van de zaak, actief of gesloten.
- **Case gemaakt op**: De datum en tijd waarop de zaak is gemaakt.
- **De risicoscore van de gebruiker:** het huidige berekende risiconiveau van de gebruiker voor de zaak. Deze score wordt elke 24 uur berekend en gebruikt waarschuwingsrisicoscores van alle actieve waarschuwingen die aan de gebruiker zijn gekoppeld.
- **E-mail:** De e-mailalias van de gebruiker voor de zaak.
- **Organisatie of afdeling:** de organisatie of afdeling aan de gebruiker.
- **Managernaam:** De naam van de manager van de gebruiker.
- **E-mail van Manager:** de e-mailalias van de manager van de gebruiker.

Het **tabblad Overzicht van** zaak bevat ook een sectie **Waarschuwingen** met de volgende informatie over waarschuwingen voor beleidsmatchen die aan de zaak zijn gekoppeld:

- **Beleid komt overeen:** de naam van het beleid voor insiderrisicobeheer dat is gekoppeld aan de overeenkomende waarschuwingen voor gebruikersactiviteit.
- **Status:** Status van de waarschuwing.
- **Ernst:** Ernst van de waarschuwing.
- **Tijd gedetecteerd:** de tijd die is verstreken sinds de waarschuwing is gegenereerd.

![Insider-casedetails voor risicobeheer](../media/insider-risk-case-details.png)

### <a name="alerts"></a>Waarschuwingen

Het **tabblad Waarschuwingen** bevat een overzicht van de huidige waarschuwingen die in de case zijn opgenomen. Nieuwe waarschuwingen kunnen worden toegevoegd aan een bestaand  geval en ze worden toegevoegd aan de waarschuwingswachtrij wanneer ze worden toegewezen. De volgende waarschuwingskenmerken worden weergegeven in de wachtrij:

- Status
- Ernst
- Tijd gedetecteerd

Selecteer een waarschuwing in de wachtrij om de detailpagina **Waarschuwing weer te** geven.

Gebruik het zoekbesturingselement om waarschuwingsnamen te zoeken naar specifieke tekst en gebruik het waarschuwingsfilter om zaken te sorteren op de volgende kenmerken:

- Status
- Ernst
- Tijd gedetecteerd, begindatum en einddatum

Gebruik het filterbesturingselement om waarschuwingen te filteren op verschillende kenmerken, waaronder:

- **Status:** Selecteer een of meer statuswaarden om de lijst met waarschuwingen te filteren. De opties *zijn Bevestigd*, *Afgewezen*, *Behoeften controleren* en *Opgelost*.
- **Ernst:** Selecteer een of meer ernstsniveaus voor waarschuwingsrisico's om de lijst met waarschuwingen te filteren. De opties zijn *Hoog,* *Gemiddeld* en *Laag.*
- **Tijd gedetecteerd:** Selecteer de begin- en einddatums voor wanneer de waarschuwing is gemaakt.
- **Beleid:** Selecteer een of meer beleidsregels om de waarschuwingen te filteren die worden gegenereerd door het geselecteerde beleid.

### <a name="user-activity"></a>Gebruikersactiviteit

Het **tabblad Gebruikersactiviteit** is een van de krachtigste hulpmiddelen voor interne risicoanalyse en -onderzoek voor gevallen in de insider-oplossing voor risicobeheer. Dit tabblad is zo gestructureerd dat een zaak snel kan worden gecontroleerd, inclusief een historische tijdlijn met alle waarschuwingen, waarschuwingsdetails, de huidige risicoscore voor de gebruiker in het geval, de reeks risicogebeurtenissen en besturingselementen om effectieve actie te ondernemen om de risico's in het geval te bevatten.

![Insider-gebruikersactiviteit voor risicobeheer](../media/insider-risk-user-activities.png)

1. **Tijdfilters:** Standaard worden de laatste zes maanden van waarschuwingen die in het geval zijn bevestigd, weergegeven in de grafiek Gebruikersactiviteit. U kunt de grafiekweergave eenvoudig filteren door de tabbladen *6 maanden,* *3* maanden of *1 maand in* het bellendiagram te selecteren.
2. **Activiteit en details van risicowaarschuwing:** Risicoactiviteiten worden visueel weergegeven als gekleurde bellen in de grafiek Gebruikersactiviteit. Bellen worden gemaakt voor verschillende categorieën risico's en de grootte van bellen is evenredig met het aantal risicoactiviteiten voor de categorie. Selecteer een bel om de details voor elke risicoactiviteit weer te geven. Details zijn:
    - **Datum** van de risicoactiviteit.
    - De **categorie risicoactiviteit**. *E-mail(en)* met bijlagen die buiten de organisatie zijn verzonden of Bestanden die zijn gedownload van *SharePoint Online.*
    - **Risicoscore** voor de waarschuwing. Deze score is de numerieke score voor het ernstsniveau van het waarschuwingsrisico.
    - Het aantal gebeurtenissen dat aan de waarschuwing is gekoppeld. Koppelingen naar elk bestand of e-mailbericht dat aan de risicoactiviteit is gekoppeld, zijn ook beschikbaar.
3. **Risicoreeks (voorbeeld)**: De chronologische volgorde van risicovolle activiteiten is een belangrijk aspect van risicoonderzoek en het identificeren van deze gerelateerde activiteiten is een belangrijk onderdeel van het evalueren van het totale risico voor uw organisatie. Waarschuwingsactiviteiten die gerelateerd zijn, worden weergegeven met verbindingslijnen om te benadrukken dat deze activiteiten zijn gekoppeld aan een groter risicogebied. Met deze weergave van activiteiten kunnen onderzoekers letterlijk 'de puntjes verbinden' voor risicoactiviteiten die als eenmalige of eenmalige gebeurtenissen hadden kunnen worden bekeken. Selecteer een bellen in de reeks om details weer te geven voor alle bijbehorende risicoactiviteiten. Details zijn:

    - **Naam** van de reeks.
    - **Datum** of **datumbereik** van de reeks.
    - **Risicoscore** voor de reeks. Deze score is de numerieke score voor de reeks van de gecombineerde ernst van het waarschuwingsrisico voor elke gerelateerde activiteit in de reeks.
    - **Het aantal gebeurtenissen dat aan elke waarschuwing in de reeks is gekoppeld.** Koppelingen naar elk bestand of e-mailbericht dat aan elke risicoactiviteit is gekoppeld, zijn ook beschikbaar.
    - **Activiteiten in de juiste volgorde laten zien.** Hiermee wordt de volgorde weergegeven als een markeringslijn in het bellendiagram en worden de waarschuwingsdetails uitgebreid om alle gerelateerde waarschuwingen in de volgorde weer te geven.

4. **Legenda risicoactiviteit:** aan de onderkant van de grafiek met gebruikersactiviteit kunt u met een legenda met kleurcode snel de risicocategorie voor elke waarschuwing bepalen.
5. **Risicoactiviteitschronologie:** De volledigechronologie van alle risicowaarschuwingen die aan de zaak zijn gekoppeld, worden weergegeven, inclusief alle details die beschikbaar zijn in de bijbehorende waarschuwingsballon.
6. **Caseacties:** Opties voor het oplossen van de zaak staan op de werkbalk caseactie. U kunt een zaak oplossen, een e-mailbericht naar de gebruiker verzenden of de zaak escaleren voor een gegevens- of gebruikersonderzoek.

### <a name="activity-explorer-preview"></a>Activiteitsverkenner (voorbeeld)

>[!IMPORTANT]
>Het tabblad Activiteitsverkenner is beschikbaar in het gebied voor casebeheer voor gebruikers met triggeringgebeurtenissen nadat deze functie beschikbaar is in uw organisatie.

Op **het tabblad Activiteitsverkenner** kunnen risicoanalisten en -onderzoeker activiteitendetails bekijken die zijn gekoppeld aan risicowaarschuwingen. Als onderdeel van de casemanagementacties moeten de onderzoekers en analisten bijvoorbeeld mogelijk alle risicoactiviteiten die aan de zaak zijn gekoppeld, bekijken voor meer informatie. Met de **Activiteitsverkenner** kunnen revisoren snel een tijdlijn bekijken van gedetecteerde riskante activiteiten en alle risicoactiviteiten identificeren en filteren die aan waarschuwingen zijn gekoppeld.

Zie het artikel Waarschuwingen voor [Insider-risicobeheer](insider-risk-management-alerts.md#activity-explorer-preview) voor meer informatie over de Activiteitenverkenner.

### <a name="content-explorer"></a>Inhoudsverkenner

Op **het tabblad Inhoudverkenner** kunnen risicoanalisten en -onderzoekers kopieën bekijken van alle afzonderlijke bestanden en e-mailberichten die zijn gekoppeld aan risicowaarschuwingen. Als er bijvoorbeeld een waarschuwing wordt gemaakt wanneer een gebruiker honderden bestanden downloadt van SharePoint Online en de activiteit een beleidsmelding activeert, worden alle gedownloade bestanden voor de waarschuwing vastgelegd en gekopieerd naar de insider risk management case uit oorspronkelijke opslagbronnen.

De Inhoudsverkenner is een krachtig hulpmiddel met eenvoudige en geavanceerde zoek- en filterfuncties. Zie Insider risk management Content [explorer](insider-risk-management-content-explorer.md)voor meer informatie over het gebruik van de Inhoudsverkenner.

![Insider risk management case Content explorer](../media/insider-risk-content-explorer.png)

### <a name="case-notes"></a>Notitie van zaak

Op **het tabblad** Case-notities in de zaak delen risicoanalisten en -onderzoeker opmerkingen, feedback en inzichten over hun werk voor de zaak. Notities zijn permanente toevoegingen aan een zaak en kunnen niet worden bewerkt of verwijderd nadat de notitie is opgeslagen. Wanneer een zaak wordt gemaakt op basis  van een waarschuwing, worden de opmerkingen die zijn ingevoerd in het dialoogvenster Waarschuwing bevestigen en insiderrisico's maken, automatisch toegevoegd als een notitie.

In het dashboard met notitienotities worden notities weergegeven van de gebruiker die de notitie heeft gemaakt en de tijd die is verstreken sinds de notitie is opgeslagen. Als u in het tekstveld met hoofdteksten naar een specifiek trefwoord wilt zoeken, gebruikt u de knop Zoeken op het hoofdvak en voert u een specifiek trefwoord in. 

Een notitie toevoegen aan een zaak:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gevallen.**
2. Selecteer een hoofd zaak en selecteer vervolgens het **tabblad Notitie** van zaak.
3. Selecteer **Notitie van de zaak toevoegen**.
4. Typ in **het dialoogvenster Notitie** toevoegen uw notitie voor de zaak. Selecteer **Opslaan** om de notitie aan de zaak toe te voegen of selecteer **Sluiten** annuleren zonder de notitie op te slaan in de zaak.

### <a name="contributors"></a>Inzenders

Op **het tabblad Inzenders** in de zaak kunnen risicoanalisten en -onderzoekers andere revisoren aan de zaak toevoegen. Wees standaard, alle gebruikers  die de insiderrisicobeheeranalisten en de rollen insiderrisicobeheeronderzoekers hebben toegewezen, worden vermeld als bijdragers voor elke actieve en gesloten zaak.  Alleen gebruikers die de rol **Insider Risk Management-onderzoeker** hebben toegewezen, hebben toestemming om bestanden en berichten weer te geven in de Inhoudsverkenner.

Tijdelijke toegang tot een zaak kan worden verleend door een gebruiker toe te voegen als inzender. Inzenders hebben alle beheersbesturingselementen voor het specifieke geval, behalve:

- Machtiging voor het bevestigen of afwijzen van waarschuwingen
- Machtiging voor het bewerken van de inzenders voor zaken
- Machtiging voor het weergeven van bestanden en berichten in de Inhoudsverkenner

Een inzender toevoegen aan een zaak:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gevallen.**
2. Selecteer een zaak en selecteer vervolgens het **tabblad Inzenders.**
3. Selecteer **Inzender toevoegen.**
4. Typ in **het dialoogvenster Inzender** toevoegen de naam van de gebruiker die u wilt toevoegen en selecteer de gebruiker in de voorgestelde gebruikerslijst. Deze lijst wordt gegenereerd op basis van Azure Active Directory van uw tenantabonnement.
5. Selecteer **Toevoegen om** de gebruiker toe te voegen als inzender of selecteer **Het** dialoogvenster annuleren sluiten zonder de gebruiker toe te voegen als inzender.

## <a name="case-actions"></a>Caseacties

Risicoanalisten en -onderzoeker kunnen actie ondernemen op een zaak in een van de verschillende methoden, afhankelijk van de ernst van de zaak, de geschiedenis van het risico van de gebruiker en de risicorichtlijnen van uw organisatie. In sommige situaties moet u mogelijk een zaak escaleren naar een gebruiker of gegevensonderzoek om samen te werken met andere gebieden van uw organisatie en om dieper in te gaan op risicoactiviteiten. Insider risk management is nauw geïntegreerd met andere Microsoft 365 compliance-oplossingen om u te helpen met end-to-end oplossingsbeheer.

### <a name="send-email-notice"></a>E-mailbericht verzenden

In de meeste gevallen zijn gebruikersacties die insiderrisicowaarschuwingen maken onbedoeld of per ongeluk. Het verzenden van een herinneringsbericht naar de gebruiker via e-mail is een effectieve methode voor het documenteren van case review en actie, en is een methode om gebruikers te herinneren aan bedrijfsbeleid of hen aan te wijzen op bijscholing. Kennisgevingen worden gegenereerd op basis [van kennisgevingssjablonen die u maakt](insider-risk-management-notices.md) voor uw insider-infrastructuur voor risicobeheer.

Het is belangrijk om te onthouden dat het verzenden van een e-mailbericht naar een gebruiker ***** het probleem niet kan oplossen als _Closed*. In sommige gevallen wilt u mogelijk een zaak open laten nadat u een melding naar een gebruiker hebt verzonden om te zoeken naar meer risicoactiviteiten zonder een nieuwe zaak te openen. Als u een zaak wilt oplossen nadat u  een melding hebt verzonden, moet u de zaak Oplossen selecteren als een vervolgstap na het verzenden van een kennisgeving.

Een melding verzenden naar de gebruiker die aan een zaak is toegewezen:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gevallen.**
2. Selecteer een zaak en selecteer vervolgens de **knop Bericht per e-mail** verzenden op de werkbalk actie voor het geval.
3. Selecteer in **het dialoogvenster E-mailbericht verzenden** het vervolgkeuzevenster Een kennisgevingssjabloon kiezen om de aankondigingssjabloon voor de melding te selecteren.  Met deze selectie worden de andere velden in de melding vooraf gevuld.
4. Controleer de kennisgevingsvelden en werk deze zo nodig bij. De waarden die hier worden ingevoerd, overschrijven de waarden op de sjabloon.
5. Selecteer **Verzenden** om de melding naar de gebruiker te verzenden of selecteer **Het** dialoogvenster annuleren sluiten zonder de melding naar de gebruiker te verzenden. Alle verzonden kennisgevingen worden toegevoegd aan de wachtrij met casenotities op het dashboard **Case notes.**

### <a name="escalate-for-investigation"></a>Escaleren voor onderzoek

Escaleert de zaak voor gebruikersonderzoek in situaties waarin aanvullende juridische controle nodig is voor de risicoactiviteit van de gebruiker. Deze escalatie opent een nieuw Advanced eDiscovery in uw Microsoft 365 organisatie. Advanced eDiscovery biedt een end-to-end werkstroom voor het bewaren, verzamelen, controleren, analyseren en exporteren van inhoud die reageert op interne en externe juridische onderzoeken van uw organisatie. Het is ook mogelijk dat uw juridische team de volledige werkstroom voor de melding van de wettelijke bewaarstatus beheert om te communiceren met bewaarders die betrokken zijn bij een zaak. Als u een revisor toewijst als voogd in een Advanced eDiscovery geval dat is gemaakt op basis van een insiderrisicobeheerzaak, kan uw juridische team passende actie ondernemen en inhoudsbewaaring beheren. Zie Overzicht van Advanced eDiscovery in Microsoft 365 voor meer informatie over Advanced eDiscovery [gevallen.](overview-ediscovery-20.md)

Een zaak escaleren naar een gebruikersonderzoek:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gevallen.**
2. Selecteer een zaak en selecteer vervolgens de **knop Escaleren voor onderzoek** op de werkbalk actie van het geval.
3. Voer in **het dialoogvenster Escaleren voor onderzoek** een naam in voor het nieuwe gebruikersonderzoek. Typ indien nodig notities over de zaak en selecteer **Escaleren.**
4. Controleer de kennisgevingsvelden en werk deze zo nodig bij. De waarden die hier worden ingevoerd, overschrijven de waarden op de sjabloon.
5. Selecteer **Bevestigen** om de zaak voor het gebruikersonderzoek te maken of selecteer **Annuleren** om het dialoogvenster te sluiten zonder een nieuwe zaak voor gebruikersonderzoek te maken.

Nadat de zaak voor insiderrisicobeheer is geëscaleerd naar een nieuwe zaak voor gebruikersonderzoek, kunt u de nieuwe zaak bekijken in het **gebied eDiscovery**  >  **Advanced** in het Microsoft 365 compliancecentrum.

### <a name="run-automated-tasks-with-power-automate-flows-for-the-case"></a>Geautomatiseerde taken uitvoeren met Power Automate voor de zaak

Met aanbevolen Power Automate kunnen risicoonderzoekers en analisten snel actie ondernemen om:

- Informatie aanvragen bij HR of business over een gebruiker in een insider risk case
- Manager op de hoogte stellen wanneer een gebruiker een insiderrisicowaarschuwing heeft
- Een record maken voor een insider risk management case in ServiceNow
- Gebruikers op de hoogte stellen wanneer ze worden toegevoegd aan een insiderrisicobeleid

Voer, beheer of maak Power Automate voor een insiderrisicobeheercase:

1. Selecteer **Automatiseren op** de werkbalk voor de actie voor de zaak. 
2. Kies de Power Automate stroom die u wilt uitvoeren en selecteer **vervolgens Stroom uitvoeren.** 
3. Nadat de stroom is voltooid, selecteert u **Gereed**.

Zie Aan de slag met instellingen voor insider-risicobeheer voor meer Power Automate voor [insiderrisicobeheer.](insider-risk-management-settings.md#power-automate-flows-preview)

### <a name="view-or-create-a-microsoft-teams-team-for-the-case"></a>Een team voor het Microsoft Teams voor de zaak weergeven of maken

Wanneer Microsoft Teams voor insider risk management is ingeschakeld in instellingen, wordt er automatisch een Microsoft Teams team gemaakt telkens wanneer een waarschuwing wordt bevestigd en er een zaak wordt gemaakt. Risicoonderzoekers en -analisten kunnen snel Microsoft Teams en rechtstreeks naar het team voor een zaak navigeren door **Weergave Microsoft Teams team** te selecteren op de werkbalk voor de actie van de zaak.

Voor zaken die zijn geopend voordat ze de integratie van microsoft-team inschakelen, kunnen risicoonderzoekers en -analisten een nieuw Microsoft Teams-team voor een zaak maken door Microsoft Teams **team maken** te selecteren op de werkbalk caseactie.

Wanneer een zaak is opgelost, wordt het bijbehorende Microsoft-team automatisch gearchiveerd (verborgen en omgezet in alleen-lezen).

Zie Aan de slag met instellingen voor insiderrisicobeheer voor meer Microsoft Teams voor [insiderrisicobeheer.](insider-risk-management-settings.md#microsoft-teams-preview)

### <a name="resolve-the-case"></a>De zaak oplossen

Nadat risicoanalisten en -onderzoeker hun onderzoek en onderzoek hebben voltooid, kan een zaak worden opgelost om te reageren op alle waarschuwingen die momenteel in de zaak zijn opgenomen. Bij het oplossen van een zaak wordt een resolutieclassificatie toegevoegd, wordt de status van de zaak gewijzigd in *Gesloten* en worden de redenen voor de oplossingsactie automatisch toegevoegd aan de wachtrij met casenotities op het dashboard **Case notes.** Zaken worden als een van de volgende zaken opgelost:

- **Goedaardig:** De classificatie voor gevallen waarin waarschuwingen voor beleidsmatchen worden geëvalueerd als laag risico, niet-ernstig of onwaar positief.
- **Bevestigd beleidsovertreding:** de classificatie voor gevallen waarin waarschuwingen voor beleidsovertredingen worden geëvalueerd als riskant, ernstig of het resultaat van kwaadaardige bedoelingen.

Een probleem oplossen:

1. Ga in [Microsoft 365 compliancecentrum](https://compliance.microsoft.com)naar **Insider-risicobeheer** en selecteer het **tabblad Gevallen.**
2. Selecteer een zaak en selecteer vervolgens de **knop Hoofd zaak oplossen** op de werkbalk voor de actie van het hoofdgeval.
3. Selecteer in **het dialoogvenster Zaak oplossen** de vervolgkeuzelijst Oplossen **als** om de resolutieclassificatie voor de zaak te selecteren. De opties zijn **Goedaardig** **of Bevestigd beleidsovertreding.**
4. Voer in **het dialoogvenster Zaak oplossen** de redenen voor de resolutieclassificatie in het **tekstveld Actie ondernomen** in.
5. Selecteer **Oplossen** om de zaak te sluiten of selecteer **Het** dialoogvenster annuleren sluiten zonder de zaak op te lossen.
