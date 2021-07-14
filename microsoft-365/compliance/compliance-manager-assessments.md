---
title: Evaluaties maken en beheren in Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: v-jgriffee
author: jmgriffee
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Maak evaluaties in Microsoft Compliance Manager om u te helpen voldoen aan de vereisten van voorschriften en certificeringen die belangrijk zijn voor uw organisatie.
ms.openlocfilehash: 7014e294454095456acdac8e2c60895c400ced3f
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419605"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Evaluaties maken en beheren in Compliance Manager

**In dit artikel:** Lees hoe u Compliance Manager voor uw organisatie kunt aanpassen door beoordelingen te maken en **te beheren.** In dit artikel wordt beschreven hoe u beoordelingen maakt, hoe u deze in groepen kunt **organiseren,** hoe u werkt met besturingselementen, updates **accepteert** en beoordelingsrapporten **exporteert.**

## <a name="introduction-to-assessments"></a>Inleiding tot evaluaties

Compliance manager helpt u bij het maken van evaluaties waarmee wordt geëvalueerd of u voldoet aan de branche- en regionale regelgeving die van toepassing is op uw organisatie. Beoordelingen zijn gebaseerd op het raamwerk van beoordelingssjablonen, die de benodigde besturingselementen, verbeteracties en, waar van toepassing, Microsoft-acties bevatten voor het voltooien van de beoordeling. Als u de meest relevante beoordelingen voor uw organisatie instelt, kunt u beleidsregels en operationele procedures implementeren om uw compliancerisico te beperken.

Al uw beoordelingen worden vermeld op het tabblad Evaluaties van Compliance Manager. Meer informatie over het filteren van uw weergave van uw beoordelingen en [het interpreteren van statusstatussen.](compliance-manager-setup.md#assessments-page)

> [!IMPORTANT]
> De sjablonen die beschikbaar zijn voor uw organisatie voor het maken van evaluaties, zijn afhankelijk van uw licentieovereenkomst. [Controleer licentiedetails.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="data-protection-baseline-default-assessment"></a>Standaardbeoordeling basislijn gegevensbescherming

Om aan de slag te gaan, biedt Microsoft een **standaardbeoordeling** in Compliance Manager voor de Microsoft 365 **basislijn voor gegevensbescherming.** Deze basislijnbeoordeling heeft een reeks besturingselementen voor belangrijke voorschriften en standaarden voor gegevensbescherming en algemeen gegevensbeheer. Deze basislijn haalt hoofdzakelijk elementen uit NIST CSF (National Institute of Standards and Technology Cyberbeveiligingskader) en ISO (International Organization for Standardization), evenals uit FedRAMP (Federal Risk and Authorization Management Program) en GDPR (General Data Protection Regulation of the European Union).

Deze beoordeling wordt gebruikt om de eerste nalevingsscore te berekenen wanneer u voor het eerst bij Compliance Manager bent, voordat u andere beoordelingen configureert. Compliance Manager verzamelt eerste signalen van uw Microsoft 365 oplossingen. U ziet in één oogopslag hoe uw organisatie presteert ten opzichte van belangrijke standaarden en voorschriften voor gegevensbescherming en ziet voorgestelde verbeteracties.

Compliance manager wordt nuttiger wanneer u uw eigen evaluaties maakt en beheert om aan de specifieke behoeften van uw organisatie te voldoen.

## <a name="understand-groups-before-creating-assessments"></a>Groepen begrijpen voordat u evaluaties maakt

Wanneer u een beoordeling maakt, moet u deze toewijzen aan een groep. Groepen zijn containers waarmee u beoordelingen kunt organiseren op een manier die voor u logisch is, zoals op jaar of regelgeving, of op basis van de afdelingen of geografieën van uw organisatie. Daarom raden we u aan een groeperingsstrategie te plannen voordat u evaluaties maakt.

Hieronder vindt u voorbeelden van twee groepen en hun onderliggende beoordelingen:

- **FFIEC IS-evaluatie 2020**
  - FFIEC IS
- **Gegevensbeveiligings- en privacybeoordelingen**
  - ISO 27001:2013
  - ISO 27018:2014

Verschillende beoordelingen binnen een groep of groepen kunnen verbeteringsacties delen. Verbeteracties kunnen wijzigingen zijn die u aan de hand van technische oplossingen aan uw tenant hebt aangebracht, zoals het inschakelen van tweestapsverificatie of niet-technische acties die u buiten het systeem voert, zoals het instellen van een nieuw bedrijfsbeleid. Alle updates in details of status die u aan een actie voor technische verbetering geeft, worden opgehaald door evaluaties in alle groepen. Niet-technische verbeteringsactie-updates worden herkend door evaluaties binnen de groep waarin u deze toe te passen. Op deze manier kunt u één verbeteringsactie implementeren en tegelijkertijd aan verschillende vereisten voldoen.

### <a name="create-a-group"></a>Een groep maken

U kunt een groep maken terwijl u een nieuwe beoordeling maakt. Groepen kunnen niet worden gemaakt als zelfstandige entiteiten.

### <a name="what-to-know-when-working-with-groups"></a>Wat u moet weten wanneer u met groepen werkt

- Een groep moet ten minste één beoordeling bevatten.
- Groepsnamen moeten uniek zijn binnen uw organisatie.
- Groepen hebben geen beveiligingseigenschappen. Alle machtigingen zijn gekoppeld aan beoordelingen.
- Wanneer u een beoordeling aan een groep toevoegt, kan de groepering niet meer worden gewijzigd.
- Als u een nieuwe beoordeling toevoegt aan een bestaande groep, worden algemene gegevens uit beoordelingen in die groep gekopieerd naar de nieuwe beoordeling.
- Gerelateerde beoordelingsbesturingselementen in verschillende beoordelingen binnen dezelfde groep worden automatisch bijgewerkt wanneer deze zijn voltooid.
- Groepen kunnen beoordelingen bevatten voor dezelfde certificering of regelgeving, maar elke groep kan slechts één beoordeling bevatten voor een specifiek productcertificeringspaar. Een groep kan bijvoorbeeld geen twee evaluaties voor Office 365 en NIST-CSF bevatten. Een groep kan alleen meerdere beoordelingen voor hetzelfde product bevatten als de bijbehorende certificering of regelgeving voor elk product anders is.
- Als u een beoordeling verwijderd, wordt de relatie tussen die beoordeling en de groep 100 procent van de groep doorbreekt.
- Groepen kunnen niet handmatig worden verwijderd.

## <a name="create-assessments"></a>Beoordelingen maken

Als u een beoordeling wilt maken, gebruikt u een wizard om de sjabloon te selecteren die deze moet gebruiken en stelt u de eigenschappen van de beoordeling in. Sjablonen bevatten de besturingselementen en actieaanbevelingen voor de beoordeling, op basis van certificeringen voor verschillende privacyregels en -standaarden. De beschikbare sjablonen van uw organisatie kunnen een of meer sjablonen bevatten die zijn opgenomen als onderdeel van uw licentieovereenkomst, samen met eventuele extra premiumsjablonen die u hebt gekocht. Elke sjabloon, inbegrepen of premium, bestaat in twee versies: een sjabloon voor gebruik met Microsoft 365 en een universele versie die kan worden aangepast aan andere producten die u gebruikt. Zie Werken met beoordelingssjablonen voor meer informatie over [sjablonen.](compliance-manager-templates.md)

> [!NOTE]
> Alleen gebruikers die een rol voor globale beheerder, compliancebeheer of compliancemanagers hebben, kunnen beoordelingen maken en wijzigen. Meer informatie over [rollen en machtigingen.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

Als u wilt beginnen met het maken van evaluaties, volgt u deze stappen.

1. Weet aan welke groep u uw beoordeling wilt toewijzen of bereid bent om een nieuwe groep te maken voor deze beoordeling.

2. Open de wizard Beoordeling. U kunt dit flyoutvenster openen vanaf een van de twee locaties:
    - Ga naar uw **beoordelingspagina** in Compliance Manager en selecteer **Beoordeling toevoegen;** of
    - Zoek de sjabloon die u wilt gebruiken op het **tabblad beoordelingssjablonen,** bekijk de details en selecteer **Beoordeling maken.** Hiermee wordt het selectieveld van de wizard voor de sjabloon voor u ingevuld.

3. **Selecteer een sjabloon:** Als u in stap 2 nog geen sjabloon hebt gekozen, kiest u een sjabloon die als basis voor uw beoordeling dient. U ziet de lijst met sjablonen die zijn onderverdeeld in opgenomen en premiumcategorieën (zie [Sjabloontypen](compliance-manager-templates.md#template-availability-and-licensing) voor meer informatie). Selecteer de keuzerondje naast de gekozen sjabloon en selecteer **vervolgens Volgende.**

4. **Product, naam en groep:** Stel deze eigenschappen in om uw beoordeling te identificeren, kies welk product het evalueert en wijs het toe aan een groep.

    - **Product:** Als u een universele sjabloon gebruikt, selecteert u of u deze beoordeling maakt voor een nieuw product of een bestaand aangepast product dat u al hebt gedefinieerd in Compliance Manager. Als u een nieuw product kiest, voert u de naam in. Houd er rekening mee dat u geen Microsoft 365 als product kunt selecteren wanneer u een universele sjabloon gebruikt. Als u een sjabloon voor Microsoft 365 gebruikt, wordt dit veld ingevuld om aan te geven Microsoft 365 en kan niet worden gewijzigd.
    - **Naam:** Voer een naam in voor uw beoordeling in het **veld Beoordelingsnaam.** Beoordelingsnamen moeten uniek zijn in groepen. Als de naam van uw beoordeling overeenkomt met de naam van een andere beoordeling in een bepaalde groep, ontvangt u een foutbericht waarin u wordt gevraagd een andere naam te maken.
    - **Groep:** Wijs uw beoordeling toe aan een groep. U kunt het volgende doen:
        - Selecteer **Bestaande groep gebruiken** om deze toe te wijzen aan een groep die u al hebt gemaakt. of
        - Selecteer **Nieuwe groep maken** om een nieuwe groep te maken en wijs deze beoordeling aan deze groep toe:
            - Bepaal een naam voor uw groep en voer deze in het veld onder de radioknop in.
            - U kunt **gegevens uit een bestaande groep**, zoals implementatie- en testgegevens en documenten, kopiëren door de juiste vakken te selecteren.

    Wanneer u klaar bent, **selecteert** u Volgende .

5. **Controleren en voltooien:** In het laatste scherm van de wizard worden de sjabloon, naam en groep weergegeven die voor de beoordeling zijn gekozen. U kunt een van deze instellingen bewerken via de koppelingen op het scherm, waarmee u terug gaat naar de relevante stappen in de wizard. Wanneer u klaar bent, selecteert u **Beoordeling maken.**

6. In het volgende scherm wordt bevestigd dat u uw nieuwe beoordeling hebt gemaakt. Selecteer **Klaar** om de wizard te sluiten en de pagina met de details van uw nieuwe beoordeling wordt weergegeven op het scherm.

Als u een scherm **Beoordeling mislukt ziet** nadat u Beoordeling maken hebt **geselecteerd,** **selecteert** u Opnieuw proberen om uw beoordeling opnieuw te maken.

U kunt de naam van uw beoordeling wijzigen  nadat u deze hebt gemaakt door de knop Naam bewerken te selecteren in de rechterbovenhoek van de [gegevenspagina van de beoordeling.](#monitor-assessment-progress-and-controls)

## <a name="monitor-assessment-progress-and-controls"></a>Voortgang en besturingselementen controleren

Elke beoordeling heeft een detailpagina die in één oogopslag een overzicht geeft van uw voortgang bij het voltooien van de beoordeling. Op de pagina ziet u uw voortgang bij het voltooien van besturingselementen en de teststatus van belangrijke verbeteracties binnen deze besturingselementen.

### <a name="overview-tab"></a>Tabblad Overzicht

Het tabblad Overzicht bevat een grafiek met uw percentage voor de voltooiing van de beoordeling. Deze grafiek bevat een uitsplitsing van punten uit acties die u zelf hebt en punten van acties die eigendom zijn van Microsoft, zodat u kunt zien hoeveel punten u nog nodig hebt om de beoordeling te voltooien.

De belangrijkste verbeteracties voor besturingselementen in de beoordeling worden weergegeven in volgorde van de grootste potentiële impact om punten te verdienen. De bijbehorende grafiek geeft de statistische teststatus van uw verbeteracties weer, zodat u snel kunt meten wat er is getest en wat er nog moet worden gedaan.

Ga naar het tabblad  Besturingselementen of het tabblad Verbeteracties voor toegang tot afzonderlijke **verbeteracties.**

### <a name="controls-tab"></a>Tabblad Besturingselementen

Op het tabblad Besturingselementen wordt gedetailleerde informatie weergegeven voor elk besturingselement dat aan de beoordeling is toegesneden. Een **overzichtsdiagram met** de status van besturingselementen per gezin, zodat u in één oogopslag kunt zien welke groeperingen van besturingselementen aandacht nodig hebben.

Onder de grafiek bevat een tabel gedetailleerde informatie over elk besturingselement in de beoordeling. Besturingselementen worden gegroepeerd op besturingselementfamilie. Vouw elke familienaam uit om de afzonderlijke besturingselementen weer te geven. De gegevens die voor elk besturingselement worden vermeld, omvatten:

- **Titel van besturingselement**
- **Status:** geeft de teststatus weer van de verbeteracties in het besturingselement 
    - **Geslaagd:** alle verbeteracties hebben een teststatus van 'doorgegeven', of er wordt ten minste één doorgegeven en de rest is 'buiten bereik'
    -  **Mislukt:** ten minste één verbeteringsactie heeft de teststatus 'mislukt'
    - **Geen:** alle verbeteracties zijn niet getest
    - **Buiten bereik:** alle verbeteracties vallen buiten het bereik van deze beoordeling
    - **In uitvoering:** verbeteracties hebben een andere status dan de hierboven genoemde acties, zoals 'in uitvoering', 'gedeeltelijk krediet' of 'niet gedetecteerd'.
- **Besturings-id:** het identificatienummer van het besturingselement, toegewezen aan de bijbehorende regelgeving, standaard of beleid
- **Behaalde punten:** het aantal punten dat wordt verdiend door acties uit te voeren, van het totale aantal haalbare punten 
- **Uw acties:** het aantal acties dat is voltooid buiten het totale aantal acties dat moet worden uitgevoerd
- **Microsoft-acties:** het aantal acties dat door Microsoft is voltooid

Als u de details van een besturingselement wilt bekijken, selecteert u het in de rij in de tabel. Op de pagina met besturingselementdetails ziet u een grafiek die de teststatus aangeeft van de acties binnen dat besturingselement. In een tabel onder de grafiek ziet u belangrijke verbeteracties voor dat besturingselement.

Selecteer een verbeteringsactie in de lijst om in te zoomen op de detailspagina van de verbeteringsactie. Op de pagina details worden teststatus- en implementatienotities weergegeven en wordt de aanbevolen oplossing weergegeven.

### <a name="your-improvement-actions-tab"></a>Het tabblad Verbeteracties

Het tabblad voor uw verbeteracties bevat alle besturingselementen in de beoordeling die door uw organisatie worden beheerd. Op de statusbalk wordt de statistische teststatus van uw verbeteracties in de beoordeling be detaild, zodat u snel kunt meten wat er is getest en wat er nog moet worden gedaan. Onder de balk staat de volledige lijst met verbeteracties en belangrijke details, waaronder: teststatus, het aantal potentiële en verdiende punten, bijbehorende regelgeving en standaarden, toepasselijke oplossing, actietype en beheerfamilie. Meer informatie over [hoe acties bijdragen aan uw nalevingsscore.](compliance-score-calculation.md#action-types-and-points)

Selecteer een verbeteringsactie om de detailspagina te bekijken en selecteer de **koppeling** Nu starten om de oplossing te openen om actie te ondernemen.

### <a name="microsoft-actions-tab"></a>Tabblad Microsoft-acties

Het tabblad Microsoft-acties wordt weergegeven voor evaluaties op basis van de Microsoft 365 versies van de sjablonen. In deze lijst worden alle acties in de beoordeling vermeld die worden beheerd door Microsoft. De lijst bevat belangrijke actiedetails, waaronder: teststatus, punten die bijdragen aan uw algemene nalevingsscore, bijbehorende regelgeving en standaarden, toepasselijke oplossing, actietype en beheerfamilie. Selecteer een verbeteringsactie om de detailspagina te bekijken.

Meer informatie over [hoe besturingselementen en verbeteracties worden bijgeslagen en gescored.](compliance-score-calculation.md)

## <a name="accept-updates-to-assessments"></a>Updates voor beoordelingen accepteren

Wanneer een update beschikbaar is voor een beoordeling, ziet u een melding en hebt u de optie om de update te accepteren of deze later uit te stellen.

### <a name="what-causes-an-update"></a>Wat is de oorzaak van een update

Er treedt een evaluatieupdate op wanneer er onderliggende sjabloonwijzigingen zijn die van invloed zijn op de score. Wijzigingen kunnen betrekking hebben op het aanpassen van beheertoewijzing of andere richtlijnen op basis van wijzigingen in regelgeving of productwijzigingen. Evaluatie-updates kunnen afkomstig zijn van uw organisatie (bijvoorbeeld wanneer een aangepaste [sjabloon wordt gewijzigd)](compliance-manager-templates.md#modify-a-template)en van Microsoft.

Als Microsoft een door u uitgebreide Compliance Manager-sjabloon bij werkt, worden deze updates overgenomen wanneer u deze accepteert. Uw beoordeling behoudt de extra kenmerken die u hebt toegepast op de beoordeling wanneer u deze hebt uitgebreid.

Aangepaste beoordelingen die u maakt, ontvangen geen sjabloonupdates van Microsoft. Aangepaste beoordelingen kunnen verbeteringsactie-updates ontvangen, maar alle Microsoft-updates voor het beheren van toewijzingen tussen beoordelingen en verbeteracties zijn niet van toepassing op aangepaste sjablonen.

> [!NOTE]
> Updates voor beoordelingen zijn alleen van toepassing op groepsniveau. Als u twee evaluaties hebt die zijn gebaseerd op dezelfde sjabloon die in twee verschillende groepen bestaat, krijgt elke beoordeling een melding over de update in behandeling en moet u de update voor elke beoordeling in de desbetreffende groep afzonderlijk accepteren.

#### <a name="where-youll-see-assessment-update-notifications"></a>Waar u meldingen voor evaluatieupdates ziet

Op de pagina beoordelingsdetails ziet **u** naast de beoordeling ook een label voor in behandeling zijnde update met een update. Selecteer die beoordeling om naar de detailspagina te gaan.

Een bericht boven aan de pagina met beoordelingsgegevens laat zien dat er een update beschikbaar is voor die beoordeling. Selecteer de **knop Update controleren** in de banner om de specifieke wijzigingen te bekijken en de update te accepteren of uit te stellen.

Op de pagina met beoordelingsdetails worden mogelijk ook verbeteracties weergegeven met een label **voor** in behandeling zijnde update er naast. Deze updates zijn voor specifieke wijzigingen in de verbeteracties zelf en moeten afzonderlijk worden geaccepteerd. Ga [naar Updates voor verbeteracties accepteren voor](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions) meer informatie.

#### <a name="review-update-to-accept-or-defer"></a>Update controleren om te accepteren of uit te stellen

Nadat u **Update controleren hebt** geselecteerd op de pagina beoordelingsdetails, wordt aan de rechterkant van het scherm een flyoutvenster weergegeven. Het flyout-deelvenster bevat de belangrijkste details hieronder over de update die in behandeling is:

- De sjabloontitel
- Bron van de update (Microsoft, uw organisatie of een specifieke gebruiker)
- De datum waarop de update is gemaakt
- Een overzicht waarin de update wordt uitgelegd
- Specifieke details over de wijzigingen, waaronder het effect op de nalevingsscore, de hoeveelheid voortgang richting voltooiing van de beoordeling en het specifieke aantal wijzigingen in verbeteracties en besturingselementen.

Als u **de koppeling Bijgewerkte** sjabloon selecteert, wordt Excel bestand met besturingselementgegevens gedownload voor de versie van de sjabloon met de in behandeling zijnde updates. Als u de **koppeling Huidige sjabloon** selecteert, wordt een bestand van de bestaande sjabloon gedownload zonder de wijzigingen.

Als u de update wilt accepteren en de wijzigingen in uw beoordeling wilt aanbrengen, selecteert u **Update accepteren.** Geaccepteerde wijzigingen zijn permanent.

Als u **Annuleren selecteert,** wordt de update niet toegepast op de beoordeling. U blijft echter de melding In behandeling bij **de update** zien totdat u de update accepteert.

**Waarom wordt u aangeraden updates te accepteren**

Als u updates accepteert, hebt u de meest bijgewerkte richtlijnen voor het gebruik van oplossingen en kunt u passende verbeteracties uitvoeren om te voldoen aan de vereisten van de certificering.

**Waarom u een update mogelijk wilt uitstellen**

Als u bezig bent met het voltooien van een evaluatie, kunt u ervoor zorgen dat u klaar bent met het werk voordat u een update voor de beoordeling accepteert die de toewijzing van de besturing kan verstoren. U kunt de update voor een later tijdstip uitstellen door Annuleren **te selecteren** in het flyoutvenster revisieupdate.

## <a name="export-an-assessment-report"></a>Een beoordelingsrapport exporteren

U kunt een beoordeling exporteren naar een Excel voor compliance-belanghebbenden in uw organisatie of voor externe auditors en regelgevende instanties. Selecteer op de pagina  beoordelingsgegevens de knop Rapport genereren boven aan de pagina, waarmee een Excel bestand wordt gemaakt dat u kunt opslaan en delen.

Het rapport is een momentopname van de beoordeling vanaf de datum en tijd van de export. Het bevat de details voor besturingselementen die door u en Microsoft worden beheerd, inclusief implementatiestatus, testdatum en testresultaten.

## <a name="delete-an-assessment"></a>Een beoordeling verwijderen

Als u een beoordeling verwijdert, wordt deze verwijderd uit de lijst op uw evaluatiepagina. Let op deze belangrijke punten over het verwijderen van beoordelingen:

- **Het verwijderen van een beoordeling is permanent. u kunt het niet terug krijgen.** Als u dezelfde beoordeling opnieuw wilt gebruiken, moet u deze opnieuw maken.
- Als de verbeteracties in de beoordeling niet worden weergegeven in een andere beoordeling, worden ze verwijderd wanneer de beoordeling wordt verwijderd.
- Het is [raadzaam een rapport van de](#export-an-assessment-report) beoordeling te exporteren voordat u het definitief verwijdert.

Als u een beoordeling wilt verwijderen, volgt u de onderstaande stappen:

1. Selecteer op **uw beoordelingspagina** de beoordeling die u wilt verwijderen om de gegevenspagina van die beoordeling te openen.

2. Selecteer **Beoordeling verwijderen** in de rechterbovenhoek van het scherm.

3. Er wordt een venster weergegeven waarin u wordt gevraagd te bevestigen dat u de beoordeling definitief wilt verwijderen. Selecteer **Evaluatie verwijderen om** het venster te sluiten. U krijgt een bevestigingsvenster dat uw beoordeling is verwijderd uit Compliance Manager.

Als u de enige beoordeling in een groep verwijdert, wordt die groep ook verwijderd uit Compliance Manager.

> [!NOTE]
> U kunt niet al uw beoordelingen verwijderen. Organisaties hebben ten minste één beoordeling nodig om Compliance Manager correct te laten functioneren. Als de beoordeling die u wilt verwijderen de enige is, voegt u een andere beoordeling toe voordat u de andere beoordeling verwijdert.
