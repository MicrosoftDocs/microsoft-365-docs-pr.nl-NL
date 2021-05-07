---
title: Evaluaties maken en beheren in Microsoft Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
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
ms.openlocfilehash: b8051a036f2ffda2f3a2840880318466a2ec71af
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "52162521"
---
# <a name="build-and-manage-assessments-in-compliance-manager"></a>Evaluaties maken en beheren in Compliance Manager

**In dit artikel:** Lees hoe u Compliance Manager voor uw organisatie kunt aanpassen door beoordelingen te maken en **te beheren.** In dit artikel wordt beschreven hoe u beoordelingen maakt, hoe u deze in groepen kunt **organiseren,** hoe u werkt met besturingselementen, updates **accepteert** en beoordelingsrapporten **exporteert.**

> [!IMPORTANT]
> De beoordelingen die beschikbaar zijn voor uw organisatie, zijn afhankelijk van uw licentieovereenkomst. [Bekijk de details.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="introduction-to-assessments"></a>Inleiding tot evaluaties

Compliance manager helpt u bij het beheren van naleving van beoordelingen voor de voorschriften en certificeringen die van toepassing zijn op uw organisatie. Beoordelingen zijn groeperingen van besturingselementen uit een specifieke regelgeving, standaard of beleid. Met Compliance Manager kunt u eenvoudig uw naleving bijhouden door vooraf gebouwde evaluaties te leveren die betrekking hebben op diverse branche- en regionale voorschriften en certificeringen.

Elke beoordeling wordt gemaakt op basis van een [beoordelingssjabloon.](compliance-manager-templates.md) Sjablonen dienen als een framework met de benodigde besturingselementen, verbeteracties en Microsoft-acties voor het voltooien van de beoordeling. Als u de meest relevante beoordelingen voor uw organisatie instelt, kunt u beleidsregels en operationele procedures implementeren om uw compliancerisico te beperken.

Al uw beoordelingen worden weergegeven op de evaluatiepagina. Meer informatie over het filteren van uw weergave van uw beoordelingen en [het interpreteren van statusstatussen.](compliance-manager-setup.md#assessments-page)

## <a name="data-protection-baseline-default-assessment"></a>Standaardbeoordeling basislijn gegevensbescherming

Om aan de slag te gaan, biedt Microsoft een **standaardbeoordeling** in Compliance Manager voor de Microsoft 365 **basislijn voor gegevensbescherming.** Deze basislijnbeoordeling heeft een reeks besturingselementen voor belangrijke voorschriften en standaarden voor gegevensbescherming en algemeen gegevensbeheer. Deze basislijn haalt hoofdzakelijk elementen uit NIST CSF (National Institute of Standards and Technology Cyberbeveiligingskader) en ISO (International Organization for Standardization), evenals uit FedRAMP (Federal Risk and Authorization Management Program) en GDPR (General Data Protection Regulation of the European Union).

Deze beoordeling wordt gebruikt om de eerste nalevingsscore te berekenen wanneer u voor het eerst bij Compliance Manager bent, voordat u andere beoordelingen configureert. Compliance Manager verzamelt eerste signalen van uw Microsoft 365 oplossingen. U ziet in één oogopslag hoe uw organisatie presteert ten opzichte van belangrijke standaarden en voorschriften voor gegevensbescherming en ziet voorgestelde verbeteracties.

Compliance manager wordt nuttiger wanneer u uw eigen evaluaties maakt en beheert om aan de specifieke behoeften van uw organisatie te voldoen.

## <a name="assessment-creation-overview"></a>Overzicht van het maken van beoordelingen

Er zijn drie manieren waarop u beoordelingen kunt instellen:

1. [Gebruik een vooraf gebouwde beoordeling.](#use-a-pre-built-assessment)
2. [Breid een vooraf gebouwde evaluatie uit naar uw eigen behoeften.](#extend-a-pre-built-assessment)
3. [Maak uw eigen aangepaste beoordeling.](#create-your-own-custom-assessment)

> [!NOTE]
> Alleen gebruikers die een rol voor globale beheerder, compliancebeheer of compliancemanagers hebben, kunnen beoordelingen maken en wijzigen. Meer informatie over [rollen en machtigingen.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

**Een vooraf gebouwde evaluatie gebruiken**

Start uw compliancetraject door een beoordeling te kiezen die al is ingesteld door Compliance Manager. We bieden een uitgebreide selectie van [sjablonen](compliance-manager-templates.md) voor regelgeving en certificeringen die zijn afgestemd op bedrijfstakken, regio's en algemene gegevensbeschermingsstandaarden, zoals AVG en ISO 27001. Sjablonen bevatten de besturingselementen en verbeteracties om u te helpen voldoen aan de vereisten van een bepaalde certificering. U wordt gevraagd een sjabloon te kiezen wanneer u begint met [het maken van een evaluatie.](#use-a-pre-built-assessment)

**Een vooraf gebouwde evaluatie uitbreiden naar uw behoeften**

U kunt een compliancebeheerbeoordeling wijzigen( een proces dat we 'uitbreiden' noemen) door uw eigen besturingselementen en acties toe te voegen die beter aan de behoeften van uw organisatie voldoen. Als u bijvoorbeeld over het algemeen moet voldoen aan HIPAA, maar extra gegevensbescherming of beveiligingsbesturingselementen nodig hebt, kunt u onze HIPAA-sjabloon uitbreiden door er uw eigen besturingselementen aan toe te voegen. Zie de instructies voor [het uitbreiden van een vooraf gebouwde evaluatie.](#extend-a-pre-built-assessment)

**Uw eigen aangepaste beoordeling maken**

U kunt uw eigen beoordeling helemaal zelf maken om precies bij te houden wat uw organisatie nodig heeft. Als u uw eigen beoordeling maakt, moet u eerst uw eigen sjabloon maken voor de beoordeling in Compliance Manager. Zie de instructies voor [het maken van uw eigen aangepaste beoordeling.](#create-your-own-custom-assessment)

## <a name="understand-groups-before-creating-assessments"></a>Groepen begrijpen voordat u evaluaties maakt

Voordat u beoordelingen maakt of wijzigt, is het belangrijk om te weten hoe groepen werken. Wanneer u een beoordeling maakt, moet u deze tijdens het proces toewijzen aan een groep. Daarom raden we u aan een groeperingsstrategie voor uw beoordelingen te plannen voordat u beoordelingen maakt.

### <a name="what-are-groups"></a>Wat zijn groepen

Groepen zijn containers waarmee u beoordelingen kunt organiseren. U kunt beoordelingen groepeert op een voor u logische manier, bijvoorbeeld op jaar of regelgeving, of op basis van de afdelingen of geografische gebieden van uw organisatie. Hieronder vindt u voorbeelden van twee groepen en hun onderliggende beoordelingen:

- **FFIEC IS-evaluatie 2020**
  - FFIEC IS
- **Gegevensbeveiligings- en privacybeoordelingen**
  - ISO 27001:2013
  - ISO 27018:2014

Wanneer twee verschillende beoordelingen in dezelfde groep verbeteracties delen die door u worden beheerd, worden eventuele updates die u aan de implementatiedetails of status van een actie aanneemt, automatisch gesynchroniseerd met dezelfde actie in een andere beoordeling in de groep. Met deze synchronisatie kunt u één verbeteringsactie implementeren en aan verschillende vereisten in meerdere voorschriften voldoen.

### <a name="how-to-create-a-group"></a>Een groep maken

U maakt een groep tijdens het maken [van een nieuwe beoordeling.](#to-create-an-assessment)

Groepen kunnen niet worden gemaakt als zelfstandige entiteiten. Een groep moet ten minste één beoordeling bevatten. Als u een groep wilt maken, moet u eerst een beoordeling maken die u in de groep wilt plaatsen.

### <a name="what-to-know-when-working-with-groups"></a>Wat u moet weten wanneer u met groepen werkt

- Groepsnamen moeten uniek zijn binnen uw organisatie.
- Groepen hebben geen beveiligingseigenschappen. Alle machtigingen zijn gekoppeld aan beoordelingen.
- Wanneer u een beoordeling aan een groep toevoegt, kan de groepering niet meer worden gewijzigd.
- Gerelateerde beoordelingsbesturingselementen in verschillende beoordelingen binnen dezelfde groep worden automatisch bijgewerkt wanneer deze zijn voltooid.
- Als u een nieuwe beoordeling toevoegt aan een bestaande groep, worden algemene gegevens uit beoordelingen in die groep gekopieerd naar de nieuwe beoordeling.
- Groepen kunnen beoordelingen bevatten voor dezelfde certificering of regelgeving, maar elke groep kan slechts één beoordeling bevatten voor een specifiek productcertificeringspaar. Een groep kan bijvoorbeeld geen twee evaluaties voor Office 365 en NIST-CSF bevatten. Een groep kan alleen meerdere beoordelingen voor hetzelfde product bevatten als de bijbehorende certificering of regelgeving voor elk product anders is.
- Als u een beoordeling verwijderd, wordt de relatie tussen die beoordeling en de groep 100 procent van de groep doorbreekt.
- Groepen kunnen niet worden verwijderd.
- Wanneer een wijziging wordt aangebracht in een verbetering die in meerdere groepen wordt weergegeven, wordt deze wijziging in alle gevallen van die verbeteringsactie weerspiegeld.

## <a name="use-a-pre-built-assessment"></a>Een vooraf gebouwde evaluatie gebruiken

Er zijn twee uitgangspunten voor het maken van een beoordeling op basis van een compliancemanagersjabloon.

U kunt het proces starten vanaf uw  evaluatiepagina door de knop Beoordeling toevoegen te selecteren en vervolgens door de wizard voor het maken van beoordelingen te werken. De stappen voor dit proces vindt u hieronder.

U kunt ook beginnen vanaf de pagina met beoordelingssjablonen door de sjablonen te zoeken die u wilt gebruiken en deze te selecteren in de lijst om bij de pagina met details te komen. Selecteer op de pagina Sjabloondetails de optie **Beoordeling maken.** Vervolgens voert u de wizard in met de sjabloon die al is geselecteerd.

### <a name="to-create-an-assessment"></a>Een beoordeling maken

1. Weet aan welke groep u uw beoordeling wilt toewijzen of bereid bent om een nieuwe groep te maken voor deze beoordeling. [Meer informatie over groepen.](#understand-groups-before-creating-assessments)  

2. Ga naar uw **beoordelingspagina** in Compliance Manager en selecteer **Beoordeling toevoegen.** Er wordt een evaluatiewizard weergegeven in een groot flyoutvenster.

3. **Selecteer een sjabloon:** kies een sjabloon om als basis voor uw beoordeling te dienen. U ziet de lijst met sjablonen die zijn onderverdeeld in opgenomen en premiumcategorieën (zie [Sjabloontypen](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) voor meer informatie). Selecteer de keuzerondje naast de gekozen sjabloon en selecteer **vervolgens Volgende.**

4. **Naam en groep:** Voer een naam voor uw beoordeling in het **veld Beoordelingsnaam** in. Beoordelingsnamen moeten uniek zijn in groepen. Als de naam van uw beoordeling overeenkomt met de naam van een andere beoordeling in een bepaalde groep, ontvangt u een foutbericht waarin u wordt gevraagd een andere naam te maken.

5. Wijs uw beoordeling toe aan een groep. U kunt het volgende doen:
    - Selecteer **Bestaande groep gebruiken** om deze toe te wijzen aan een groep die u al hebt gemaakt. of
    - Selecteer **Nieuwe groep maken** om een nieuwe groep te maken en wijs deze beoordeling aan deze groep toe:
        - Bepaal een naam voor uw groep en voer deze in het veld onder de radioknop in.
        - U kunt **gegevens uit een bestaande groep**, zoals implementatie- en testgegevens en documenten, kopiëren door de juiste vakken te selecteren.

    Wanneer u klaar bent, **selecteert** u Volgende .

6. **Controleren en voltooien:** In het laatste scherm van de wizard worden de sjabloon, naam en groep weergegeven die voor de beoordeling zijn gekozen. U kunt een van deze instellingen bewerken via de koppelingen op het scherm, waarmee u terug gaat naar de relevante stappen in de wizard. Wanneer u klaar bent, selecteert u **Beoordeling maken.**

7. In het volgende scherm wordt bevestigd dat u uw nieuwe beoordeling hebt gemaakt. Selecteer **Klaar** om de wizard te sluiten en de pagina met de details van uw nieuwe beoordeling wordt weergegeven op het scherm.

Als u een scherm **Beoordeling mislukt ziet** nadat u Beoordeling maken hebt **geselecteerd,** **selecteert** u Opnieuw proberen om uw beoordeling opnieuw te maken.

U kunt de naam van uw beoordeling wijzigen  nadat u deze hebt gemaakt door de knop Naam bewerken te selecteren in de rechterbovenhoek van de [gegevenspagina van de beoordeling.](#monitor-assessment-progress-and-controls)

## <a name="extend-a-pre-built-assessment"></a>Een vooraf gebouwde evaluatie uitbreiden

U kunt een vooraf gebouwde beoordeling wijzigen door uw eigen besturingselementen en verbeteracties toe te voegen aan de sjabloon van de beoordeling. Dit proces wordt 'uitbreiding van een Microsoft-sjabloon' genoemd in Compliance Manager. Wanneer u de sjabloon van een beoordeling uitbreidt, worden alle updates ontvangen die door Microsoft zijn uitgebracht, wat kan gebeuren wanneer er wijzigingen zijn in de gerelateerde regelgeving of het bijbehorende product (zie Updates voor beoordelingen [accepteren).](#accepting-updates-to-assessments)

U voltooit dit proces door te beginnen op de pagina met **de beoordelingssjablonen** in plaats van op **uw beoordelingspagina.**

**Before you begin**

Als u zich wilt voorbereiden op dit proces, moet u eerst een speciaal opgemaakt werkblad Excel om de benodigde sjabloongegevens te importeren. Er zijn speciale vereisten voor de [opgemaakte Excel bestanden](compliance-manager-templates.md#formatting-your-template-data-with-excel) die in het uitbreidingsproces worden gebruikt. Zie deze extra punten om fouten in het importproces te voorkomen:

- Uw spreadsheet mag alleen de acties en besturingselementen bevatten die u aan de beoordeling wilt toevoegen. 
- Het werkblad mag geen besturingselementen of acties bevatten die al aanwezig zijn in de beoordeling die u wilt wijzigen.
- Overweeg om 'extensie' in de titel van uw sjabloon op te nemen, bijvoorbeeld 'GDPR – [uw bedrijfsnaam] extensie'. Hierdoor kunt u gemakkelijker in de  lijst op de pagina beoordelingssjablonen worden onderscheiden van de standaardsjabloon van Microsoft of een aangepaste sjabloon met een vergelijkbare naam.

Nadat u de spreadsheet hebt opgemaakt, volgt u de onderstaande stappen.

**Stappen voor het uitbreiden van een compliancebeheersjabloon**

1. Ga naar de pagina **Beoordelingssjablonen** en selecteer **Nieuwe sjabloon maken.** Er wordt een wizard voor het maken van een sjabloon geopend.

2. Kies het type sjabloon dat u wilt maken. Selecteer in dit geval **Een Microsoft-sjabloon uitbreiden** en selecteer **vervolgens Microsoft-sjabloon**.

3. Aan de rechterkant van het scherm wordt een sjabloonselectievenster weergegeven, met een lijst met alle sjablonen en de status van actief of inactief. De **teller voor** geactiveerde sjablonen laat zien hoeveel sjablonen momenteel worden gebruikt buiten het totale aantal beschikbare sjablonen. Als u uw limiet hebt overschreden, wordt een berichtbalk weergegeven. Zie [Sjabloontypen](compliance-manager-templates.md#template-types-included-and-premium-active-and-inactive) voor meer informatie.

4. Aan de rechterkant van het scherm wordt een sjabloonselectievenster weergegeven. Gebruik **Zoeken** om filters toe te passen voor het vinden van de gezochte sjabloon

5. Wanneer u de sjabloon hebt gevonden, selecteert u de keuzerondje links van de naam en selecteert u **Opslaan.**

6. In het volgende scherm ziet u de sjabloon die u hebt geselecteerd. Als dit juist is, **selecteert** u Volgende . (Als dit onjuist is, **kiest u Een andere sjabloon selecteren om** opnieuw te kiezen.)

7. Selecteer op **Upload scherm** Bladeren  om uw opgemaakte Excel met alle vereiste sjabloongegevens te zoeken en te uploaden.

8. Als er geen problemen zijn met het bestand, wordt in het volgende scherm de naam van het bestand weergegeven dat is geüpload. Selecteer **Volgende** om door te gaan (als u het bestand wilt wijzigen, **selecteert u Upload een ander bestand**).

    - Als er een probleem is met uw bestand, wordt in een foutbericht bovenaan uitgelegd wat er mis is. U moet het bestand herstellen en opnieuw uploaden. Er ontstaan fouten als uw spreadsheet onjuist is opgemaakt of als er ongeldige informatie in bepaalde velden staat.
 
9. In **het scherm Controleren en** voltooien ziet u het aantal verbeteracties en besturingselementen en de maximale score voor de sjabloon. Wanneer u klaar bent om het goed te keuren, **selecteert** u Volgende . (Als u wijzigingen wilt aanbrengen, selecteert **u Upload een ander bestand**.)

10. Het laatste scherm bevestigt dat er een nieuwe sjabloon is gemaakt. Selecteer **Klaar om** de wizard te sluiten.

11. U komt op de detailspagina van de nieuwe sjabloon. Hier kunt u uw beoordeling maken door Beoordeling **maken te selecteren.** Voor richtlijnen begint u bij stap #4 in de [bovenstaande instructies voor het maken van beoordelingen.](#to-create-an-assessment)

## <a name="create-your-own-custom-assessment"></a>Uw eigen aangepaste beoordeling maken

Als u een aangepaste beoordeling maakt in Compliance Manager, moet u uw eigen sjabloon maken. Als u uw eigen sjabloon wilt maken, maakt u eerst een opgemaakte Excel spreadsheet om de benodigde sjabloongegevens te importeren. Het helpt ook om van tevoren te bepalen aan welke groep u uw beoordeling toewijst wanneer u deze maakt (meer informatie over [groepen).](#what-are-groups)

**Volg de onderstaande stappen om uw aangepaste beoordeling te maken:**

1. **Maak uw Excel op.** Begin met het opmaken van de sjabloongegevens in een Excel spreadsheet met [deze instructies.](compliance-manager-templates.md#formatting-your-template-data-with-excel)

2. **Maak de sjabloon door** deze [instructies te volgen.](compliance-manager-templates.md#create-a-new-template)

3. **Maak uw beoordeling** op basis van de sjabloon. U kunt beginnen door de pagina met details van de sjabloon te openen en Beoordeling **maken** te selecteren of naar de **beoordelingspagina** te gaan en **Beoordeling maken te selecteren.**

4. Er wordt een wizard voor het maken van beoordelingen weergegeven in een groot flyoutvenster. Hier kunt u de richtlijnen volgen die beginnen bij stap #3 van de instructies voor het maken van [beoordelingen,](#to-create-an-assessment)met behulp van uw nieuwe aangepaste sjabloon voor uw beoordeling.

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

Selecteer een verbeteringsactie in de lijst om in te zoomen op de detailspagina van de verbeteringsactie. Op de detailspagina's ziet u de teststatus, implementatienotities en start u de aanbevolen oplossing.

### <a name="your-improvement-actions-tab"></a>Het tabblad Verbeteracties

Het tabblad voor uw verbeteracties bevat alle besturingselementen in de beoordeling die door uw organisatie worden beheerd. Op de statusbalk wordt de statistische teststatus van uw verbeteracties in de beoordeling be detaild, zodat u snel kunt meten wat er is getest en wat er nog moet worden gedaan. Onder de balk staat de volledige lijst met verbeteracties en belangrijke details, waaronder: teststatus, het aantal potentiële en verdiende punten, bijbehorende regelgeving en standaarden, toepasselijke oplossing, actietype en beheerfamilie. Meer informatie over [hoe acties bijdragen aan uw nalevingsscore.](compliance-score-calculation.md#action-types-and-points)

Selecteer een verbeteringsactie om de detailspagina te bekijken en selecteer de **koppeling** Nu starten om de oplossing te openen om actie te ondernemen.

### <a name="microsoft-actions-tab"></a>Tabblad Microsoft-acties

Het tabblad Microsoft-acties bevat alle acties in de beoordeling die worden beheerd door Microsoft. De lijst bevat belangrijke actiedetails, waaronder: teststatus, punten die bijdragen aan uw algemene nalevingsscore, bijbehorende regelgeving en standaarden, toepasselijke oplossing, actietype en beheerfamilie. Selecteer een verbeteringsactie om de detailspagina te bekijken.

Meer informatie over [hoe besturingselementen en verbeteracties worden bijgeslagen en gescored.](compliance-score-calculation.md)

## <a name="accepting-updates-to-assessments"></a>Updates voor beoordelingen accepteren

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