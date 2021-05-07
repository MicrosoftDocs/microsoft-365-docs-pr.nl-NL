---
title: Werken met beoordelingssjablonen in Microsoft Compliance Manager
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
description: Meer informatie over het gebruik en beheren van sjablonen voor het maken van evaluaties in Microsoft Compliance Manager. Sjablonen maken en wijzigen met een opgemaakt Excel bestand.
ms.openlocfilehash: ac5fe5f0a62c3b20021a9829499d8cec9339f72a
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "52162519"
---
# <a name="working-with-assessment-templates-in-compliance-manager"></a>Werken met beoordelingssjablonen in Compliance Manager

**In dit artikel:** Meer **informatie over hoe sjablonen werken** en hoe u deze kunt **beheren** vanaf de pagina beoordelingssjablonen. Instructies voor het **maken van** nieuwe sjablonen, **het** wijzigen van bestaande sjablonen, het opmaken van sjabloongegevens met Excel en het exporteren van **sjabloonrapporten.** 

> [!IMPORTANT]
> De beoordelingssjablonen die beschikbaar zijn voor uw organisatie, zijn afhankelijk van uw licentieovereenkomst. [Bekijk de details.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="templates-overview"></a>Sjablonenoverzicht

Een sjabloon is een kader van besturingselementen voor het maken van een beoordeling in Compliance Manager. Met onze uitgebreide set sjablonen kan uw organisatie voldoen aan nationale, regionale en branchespecifieke vereisten voor het verzamelen en gebruiken van gegevens. We verwijzen naar sjablonen met dezelfde naam als de onderliggende certificering of regelgeving, zoals de AVG-sjabloon van de EU en de ISO 27001:2013-sjabloon.

 Bekijk de [volledige lijst met sjablonen.](compliance-manager-templates-list.md)

## <a name="template-types-included-and-premium-active-and-inactive"></a>Sjabloontypen: inbegrepen en premium, actief en inactief

#### <a name="included-and-premium-templates"></a>Inbegrepen en premiumsjablonen

De sjablonen die beschikbaar zijn voor gebruik, zijn gebaseerd op de licentieovereenkomst van uw organisatie[(bekijk licentiedetails).](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) Er zijn twee categorieën sjablonen: inbegrepen en premium.

1. **Inbegrepen sjablonen** zijn beschikbaar voor gebruik als onderdeel van de licentieovereenkomst van uw organisatie.
2. **Premium sjablonen** moeten worden aangeschaft om er beoordelingen van te maken. Wanneer u de sjabloon hebt aangeschaft, kunt u zo veel mogelijk beoordelingen maken op basis van een sjabloon. [Meer informatie over hoe u premiumsjablonen kunt kopen.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager)

#### <a name="active-and-inactive-templates"></a>Actieve en inactieve sjablonen

Sjablonen geven een activeringsstatus weer als actief of inactief:

- Een sjabloon wordt als **actief beschouwd** wanneer u een evaluatie maakt op basis van die sjabloon.
- Een sjabloon wordt **als inactief beschouwd** als uw organisatie deze niet gebruikt voor een evaluatie.

Wanneer u een premiumsjabloon koopt en er een evaluatie van maakt, is die sjabloon één jaar actief. Uw aankoop wordt automatisch verlengd, tenzij u verlenging annuleert.

**Geactiveerde sjablonenteller**

De pagina beoordelingspagina en beoordelingssjablonen hebben een **geactiveerde** sjablonenteller bovenaan. In de teller wordt het aantal sjablonen weergegeven dat wordt gebruikt buiten het aantal dat in aanmerking komt voor gebruik volgens uw licentieovereenkomst.

Als de teller bijvoorbeeld 2/5 laat zien, betekent dit dat uw organisatie twee sjablonen van de 5 heeft geactiveerd die beschikbaar zijn voor gebruik.

Als de teller 5/2 aangeeft, geeft dit aan dat uw organisatie de limieten overschrijdt en drie van de premiumsjablonen in gebruik moet kopen.

Zie [Richtlijnen voor compliancebeheerlicenties](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#compliance-manager) voor meer informatie.

## <a name="viewing-and-managing-templates-from-the-assessment-templates-page"></a>Sjablonen weergeven en beheren vanaf de pagina beoordelingssjablonen

Op de pagina beoordelingssjablonen in Compliance Manager ziet u een lijst met sjablonen en belangrijke details. De lijst bevat sjablonen die worden geleverd door Compliance Manager en alle sjablonen die uw organisatie heeft gewijzigd of gemaakt. U kunt filters toepassen om een sjabloon te zoeken op basis van certificering, productbereik, land, industrie, wie deze heeft gemaakt en of de sjabloon is ingeschakeld voor het maken van beoordelingen.

Selecteer een sjabloon in de rij om de detailspagina weer te geven. Deze pagina bevat een beschrijving van de sjabloon en meer informatie over certificering, bereik en besturingselementen. Op deze pagina kunt u de juiste knoppen selecteren om een beoordeling te maken, de sjabloongegevens exporteren naar Excel of de sjabloon wijzigen.

## <a name="creating-and-modifying-templates-overview"></a>Overzicht van sjablonen maken en wijzigen

Als u een bestaande sjabloon wilt wijzigen of uw eigen nieuwe sjabloon wilt maken, gebruikt u een speciaal opgemaakt Excel spreadsheet[(download](https://go.microsoft.com/fwlink/?linkid=2124865)een voorbeeld) om de benodigde besturingsgegevens te verzamelen. Nadat u de spreadsheet hebt gemaakt, importeert u deze in Compliance Manager tijdens het maken of wijzigen van een sjabloon.

> [!NOTE]
> De spreadsheet heeft een specifieke indeling en schema die moeten worden gebruikt, anders wordt het niet correct geïmporteerd in Compliance Manager. De [opmaakinstructies](#formatting-your-template-data-with-excel) zijn hieronder.

**Vereiste rollen**

Alleen gebruikers met een rol voor globale beheerder of compliancebeheer kunnen sjablonen maken en wijzigen. Meer informatie over [rollen en machtigingen.](compliance-manager-setup.md#set-user-permissions-and-assign-roles)

## <a name="create-a-new-template"></a>Een nieuwe sjabloon maken

Als u uw eigen nieuwe sjabloon wilt maken (die wordt gebruikt voor het maken van aangepaste beoordelingen), volgt u de onderstaande stappen.

1. Ga naar de pagina **beoordelingssjablonen** in Compliance Manager.
2. Selecteer **Nieuwe sjabloon maken.** Er wordt een wizard voor het maken van een sjabloon geopend.
3. Kies het type sjabloon dat u wilt maken. Selecteer in dit geval **Een aangepaste sjabloon maken** en selecteer vervolgens **Volgende.**
4. Selecteer **op Upload** scherm Bladeren  om het opgemaakte Excel-bestand met alle vereiste sjabloongegevens te zoeken en te uploaden (zie instructies voor het correct opmaken van [het bestand).](#formatting-your-template-data-with-excel)
5. Als er geen problemen zijn met uw bestand, wordt de naam van het geüploade bestand weergegeven. Selecteer **Volgende om** door te gaan. (Als u het bestand wilt wijzigen, selecteert **u Upload een ander bestand**).
    - Als er een fout met het bestand is, wordt in een foutbericht bovenaan uitgelegd wat er mis is. U moet het bestand herstellen en opnieuw uploaden. Er ontstaan fouten als uw spreadsheet onjuist is opgemaakt of als er ongeldige informatie in bepaalde velden staat (raadpleeg nogmaals de [opmaakinstructies).](#formatting-your-template-data-with-excel)  
    
6. In **het scherm Controleren en** voltooien ziet u het aantal verbeteracties en besturingselementen en de maximale score voor de sjabloon. Wanneer u klaar bent om het goed te keuren, **selecteert u Sjabloon maken.** (Als u wijzigingen wilt aanbrengen, selecteert u **Terug**.)
7. Het laatste scherm bevestigt dat er een nieuwe sjabloon is gemaakt. Selecteer **Klaar om** de wizard te sluiten.
8. U komt op de detailspagina van de nieuwe sjabloon, waar u [uw beoordeling kunt maken.](compliance-manager-assessments.md#create-your-own-custom-assessment)

## <a name="formatting-your-template-data-with-excel"></a>Uw sjabloongegevens opmaken met Excel

Het Excel spreadsheet dat wordt gebruikt om sjablonen te maken, bevat vier tabbladen, waarvan er drie vereist zijn:

1. [Sjabloon](#template-tab) (vereist)
2. [ControlFamily](#controlfamily-tab) (vereist)
3. [Acties](#actions-tab) (vereist)
4. [Afmetingen](#dimensions-tab) (optioneel)

Wanneer u uw spreadsheet invult met sjabloongegevens, moet het werkblad de tabbladen in de bovenstaande  **volgorde** bevatten, anders worden uw gegevens niet geïmporteerd in een sjabloon.

##### <a name="template-tab"></a>Tabblad Sjabloon

Het **tabblad** Sjabloon is vereist. De informatie op dit tabblad bevat metagegevens over de sjabloon. Er zijn vier vereiste kolommen. De kolommen moeten de volgorde op het Excel behouden, zoals hieronder wordt vermeld. U kunt na de vier **kolommen** uw eigen kolom toevoegen om uw eigen afmetingen te geven. Als u dit doet, moet u deze toevoegen aan het tabblad **Dimensies** met de [onderstaande instructies.](#dimensions-tab)

- **titel:** dit is de titel voor de sjabloon, die uniek moet zijn. Het kan geen naam delen met een andere sjabloon die u hebt in Compliance Manager, inclusief uw eigen sjablonen of een compliancebeheersjabloon.

- **product:** Dit is een vereiste dimensie. Vermeld het product dat aan de sjabloon is gekoppeld.

- **certificering:** dit is de verordening die u gebruikt voor de sjabloon.

- **inScopeServices:** dit zijn de services binnen het product waar deze beoordeling op is gericht (als u bijvoorbeeld Office 365 als product hebt vermeld, kan Microsoft Teams een service binnen het bereik zijn). U kunt meerdere services op een lijst zetten die zijn gescheiden door twee dubbele punts.

> [!NOTE]
> De gegevens die u  invoegt in **de product-** en certificeringscellen, kunnen niet worden bewerkt nadat u het werkblad hebt geïmporteerd om een sjabloon te maken of aan te passen. Een groep kan ook geen twee beoordelingen bevatten die dezelfde **combinatie van product/certificering** hebben. U kunt meerdere sjablonen met dezelfde product-/certificeringscombinatie hebben.

##### <a name="controlfamily-tab"></a>Tabblad ControlFamily

Het **tabblad ControlFamily** is vereist.  De vereiste kolommen op dit tabblad, die de volgorde moeten volgen die in het voorbeeldblad wordt weergegeven, zijn:

- **controlName:** dit is de naam van het besturingselement van de certificering, standaard of regelgeving, die meestal een bepaald type id is. Besturingselementnamen moeten uniek zijn in een sjabloon. U kunt niet meerdere besturingselementen met dezelfde naam in het spreadsheet hebben.

- **controlFamily:** Geef een woord of woordgroep op voor het besturingselementFamily, waarmee een brede groep besturingselementen wordt geïdentificeerd. Een controlFamily hoeft niet uniek te zijn. het kan meerdere keer in een spreadsheet worden weergegeven. Hetzelfde besturingselementFamily kan ook worden weergegeven in meerdere sjablonen, maar ze hebben geen relatie met elkaar. Elk besturingselementFamily moet aan ten minste één besturingselement zijn toegesneden.

- **controlTitle:** Geef een titel op voor het besturingselement. Terwijl het besturingselementNaam een verwijzingscode is, is de titel een opmaak voor tekst met opmaak die meestal wordt gezien in de regelgeving.

- **controlDescription:** Geef een beschrijving van het besturingselement op.

- **controlActionTitle:** dit is de titel van een actie die u wilt relateren aan dit besturingselement. U kunt meerdere acties toevoegen door twee dubbele punts te scheiden zonder tussenruimte. Elk besturingselement dat u opneemt, moet ten minste één actie bevatten en de  actie moet bestaan (wat betekent dat u een actie kunt weergeven die u op het tabblad Acties van hetzelfde spreadsheet vermeldt, een actie die bestaat in een andere sjabloon of een actie die door Microsoft is gemaakt). Verschillende besturingselementen kunnen verwijzen naar dezelfde actie.

##### <a name="actions-tab"></a>Tabblad Acties

Het **tabblad** Acties is vereist.  Het wijst verbeteracties aan die worden beheerd door uw organisatie en niet die van Microsoft, die al aanwezig zijn in Compliance Manager. De vereiste kolommen voor dit tabblad, die de volgorde moeten volgen die in het voorbeeldblad wordt weergegeven, zijn:

- **actionTitle:** Dit is de titel voor uw actie en is een verplicht veld. De door u op te geven titel moet uniek zijn. **Belangrijk:** als u verwijst naar een actie die al bestaat (zoals in een andere sjabloon) en u een van de elementen in de volgende kolommen wijzigt, worden deze wijzigingen doorgevoerd naar dezelfde actie in andere sjablonen.

- **implementationType:** In dit vereiste veld vermeldt u een van de drie onderstaande implementatietypen:
    - **Operationeel:** acties die worden geïmplementeerd door personen en processen ter bescherming van de vertrouwelijkheid, integriteit en beschikbaarheid van organisatiesystemen, activa, gegevens en personeel (bijvoorbeeld: beveiligingsbewustzijn en training)
    - **Technische** acties die zijn voltooid door het gebruik van technologie en mechanismen in de hardware-, software- of firmwareonderdelen van het informatiesysteem ter bescherming van de vertrouwelijkheid, integriteit en beschikbaarheid van organisatiesystemen en -gegevens (bijvoorbeeld: meervoudige verificatie)
    - **Documentatie:** acties die zijn geïmplementeerd via gedocumenteerd beleid en procedures voor het vaststellen en definiëren van de besturingselementen die nodig zijn om de vertrouwelijkheid, integriteit en beschikbaarheid van organisatiesystemen, activa, gegevens en personeel te beschermen (bijvoorbeeld: een informatiebeveiligingsbeleid)

- **actionScore:** Geef in dit vereiste veld een numerieke scorewaarde op voor uw actie. Het moet een geheel getal zijn van 1 tot 99. het kan niet 0, null of leeg zijn. Hoe hoger het getal, hoe groter de waarde voor het verbeteren van de nalevingsstatus. In de onderstaande afbeelding wordt gedemonstreerd hoe Compliance Manager scores bepaalt:

![Compliance Manager besturingselementen puntwaarden](../media/compliance-score-action-scoring.png "Compliance Manager besturingselementen puntwaarden")

- **actionDescriptionTitle:** Dit is de titel van de beschrijving en is vereist. Met deze beschrijvingstitel kunt u dezelfde actie in meerdere sjablonen hebben en in elke sjabloon een andere beschrijving weergeven.  Met dit veld kunt u verduidelijken welke sjabloon de beschrijving verwijst. In de meeste gevallen kunt u de naam van de sjabloon die u maakt in dit veld zetten.

- **actionDescription:** Geef een beschrijving van de actie op. U kunt opmaak toepassen, zoals vetgedrukte tekst en hyperlinks. Dit is vereist veld.

- **dimensie-actiedoel:** dit is een optioneel veld. Als u deze opvoegt, moet de koptekst het voorvoegsel 'dimensie-' bevatten. Alle dimensies die u hier op neemt, worden gebruikt als filters in Compliance Manager en worden weergegeven op de pagina details van verbeteracties in Compliance Manager.

##### <a name="dimensions-tab"></a>Tabblad Dimensies

Het **tabblad Dimensies** is optioneel. Als u echter ergens anders naar een dimensie verwijst, moet u deze hier opgeven als deze niet aanwezig is in een sjabloon die u al hebt gemaakt of in een Microsoft-sjabloon. De kolommen voor dit tabblad worden hieronder weergegeven:

- **dimensionKey:** lijst als 'product', 'certificeringen', 'actiedoel'
- **dimensieWaarde:** voorbeelden: Office 365, HIPPA, Preventative, Detective

U kunt uw bestaande dimensies weergeven door naar **Tenantbeheer** te gaan en het tabblad **Dimensies te** selecteren. Wanneer u een bestaande sjabloon exporteert, heeft het geëxporteerde werkblad ook het tabblad **Dimensies,** waarin alle dimensies worden vermeld die in de sjabloon worden gebruikt.

## <a name="modify-a-template"></a>Een sjabloon wijzigen

Mogelijk wilt u een sjabloon wijzigen die u al hebt gemaakt, zoals besturingselementen toevoegen of verbeteracties toevoegen of verwijderen. Het proces is vergelijkbaar met het proces voor het maken van sjabloons, omdat u opgemaakte Excel met uw sjabloongegevens uploadt.

Er zijn echter specifieke details waar u rekening mee moet houden wanneer u het bestand opmaak met wijzigingen in bestaande sjabloongegevens. **U wordt aangeraden deze instructies zorgvuldig door te lezen om ervoor te zorgen dat u bestaande gegevens die u wilt behouden, niet overschrijft.**

### <a name="template-modification-process-steps"></a>Processtappen voor het wijzigen van sjabloon

Als u een sjabloon wilt wijzigen, volgt u de onderstaande stappen:

1. Selecteer op **de pagina** beoordelingssjablonen de sjabloon die u wilt wijzigen, waarna de pagina met details wordt weergegeven.
2. Selecteer **Exporteren naar Excel.** Een Excel bestand met al uw sjabloongegevens wordt gedownload. Sla het bestand op uw lokale computer op.
3. Wijzig de sjabloon door [het Excel te wijzigen met de onderstaande instructies.](#formatting-your-excel-file-to-modify-a-template)
4. Wanneer u klaar bent met het aanbrengen van wijzigingen in Excel bestand, kunt u het bestand opslaan.
5. Selecteer op de pagina Details van de sjabloon de optie Sjabloon **wijzigen om** de wijzigingswizard te starten. 
6. Selecteer op **Upload scherm** Bladeren om **uw** bestand te zoeken en Excel uploaden.
7. Als er geen problemen zijn met het bestand, wordt in het volgende scherm de naam van het bestand weergegeven dat is geüpload. Selecteer **Volgende** om door te gaan (als u het bestand wilt wijzigen, **selecteert u Upload een ander bestand**).
    - Als er een probleem is met uw bestand, wordt in een foutbericht bovenaan uitgelegd wat er mis is. U moet het bestand herstellen en opnieuw uploaden. Er ontstaan fouten als uw spreadsheet onjuist is opgemaakt of als er ongeldige informatie in bepaalde velden staat.

8. In **het scherm Controleren en** voltooien ziet u het aantal verbeteracties en besturingselementen en de maximale score voor de sjabloon. Wanneer u klaar bent om het goed te keuren, **selecteert** u Volgende .
9. Het laatste scherm bevestigt dat de sjabloon is gewijzigd. Selecteer **Klaar om** de wizard te sluiten.

De sjabloon bevat nu de wijzigingen die u hebt aangebracht. Alle beoordelingen die gebruikmaken van deze gewijzigde sjabloon, worden nu in behandeling zijnde updates weergegeven en u moet de updates voor de beoordelingen accepteren om de wijzigingen in de sjabloon weer te geven. Meer informatie over [updates voor beoordelingen.](compliance-manager-assessments.md#accepting-updates-to-assessments)

> [!NOTE]
> Als u Compliance Manager gebruikt in een andere taal dan Engels, ziet u dat sommige tekst in het Engels wordt weergegeven wanneer u een sjabloon exporteert naar Excel. De titels van acties (zowel uw verbeteracties als Microsoft-acties) moeten in het Engels zijn om te worden herkend door besturingselementen. Als u wijzigingen aan een actietitel aanneemt, moet u deze in het Engels schrijven, zodat het bestand correct wordt geïmporteerd.

### <a name="formatting-your-excel-file-to-modify-a-template"></a>Uw bestand opmaken Excel een sjabloon te wijzigen

Ga naar een sectie hieronder om snel de instructies te vinden die u nodig hebt:

- [De hoofdsjabloonkenmerken bewerken](#edit-the-main-template-attributes)
- [Een verbeteringsactie toevoegen](#add-an-improvement-action)
- [De informatie van een verbeteringsactie bewerken](#edit-an-improvement-actions-information)
- [De naam van een verbeteringsactie wijzigen](#change-an-improvement-actions-name)
- [Een verbeteringsactie verwijderen](#remove-an-improvement-action)
- [Een besturingselement verwijderen](#remove-a-control)

#### <a name="edit-the-main-template-attributes"></a>De hoofdsjabloonkenmerken bewerken

Op het **tabblad** Sjablonen kunt  u alles bewerken in de titelkolom, **de kolom inScopeServices** en in een andere kolom die u mogelijk hebt toegevoegd. U kunt echter niets bewerken in de **product-** of **certificeringskolommen.**

#### <a name="add-an-improvement-action"></a>Een verbeteringsactie toevoegen

1. Ga naar het **tabblad** Acties. Voeg uw gegevens toe in de vereiste velden in de eerste lege rij onder uw bestaande acties.
2. Ga naar het **tabblad ControlFamily.** Zoek de rij met het besturingselement waar uw verbeteractiekaarten naar zijn opgeslagen. Voeg de nieuwe actie toe aan het **besturingselementActionTitle-kolom** in die rij (onthoud dat u meerdere acties in dit veld moet scheiden met twee dubbele punts, geen spatie ertussen).
3. Sla uw spreadsheet op.

#### <a name="edit-an-improvement-actions-information"></a>De informatie van een verbeteringsactie bewerken

U kunt de informatie van elke verbeteringsactie *wijzigen, behalve de titel.* U kunt elke cel bewerken vanuit kolom B en wanneer u het bestand weer importeert in de sjabloon, bevatten de verbeteracties in die sjabloon nu de bijgewerkte gegevens.

U kunt de **actieTitel** (kolom A) niet bewerken, omdat compliancebeheer dit als een nieuwe verbeteringsactie beschouwt. Als u de naam van een verbeteringsactie wilt wijzigen, bekijkt u de onderstaande instructies.

#### <a name="change-an-improvement-actions-name"></a>De naam van een verbeteringsactie wijzigen

Als u de naam van een verbeteringsactie wilt wijzigen, moet u in het spreadsheet expliciet aanwijzen dat u een bestaande naam vervangt door een nieuwe naam. Volg deze stappen:

1. Voeg op **het** tabblad Acties van uw spreadsheet een nieuwe kolom toe aan het spreadsheet na kolom A.
2. Zet in deze nieuwe kolom, die nu kolom B is, als koptekst in rij 1: **oldActionTitle**.
3. Kopieer de inhoud van kolom A en plak deze in kolom B. Hiermee worden uw bestaande actietitels voor verbetering, die u wilt wijzigen, in kolom B.
4. In kolom A, **actionTitle,** verwijdert u de oude naam en vervangt u deze door de nieuwe naam voor uw verbeteringsactie.

Houd er rekening mee dat actietitels, zowel voor uw verbeteringsacties als voor Microsoft-acties, in het Engels moeten worden geschreven om te worden herkend wanneer in besturingselementen wordt verwezen.

#### <a name="remove-an-improvement-action"></a>Een verbeteringsactie verwijderen

Als u een verbeteringsactie uit een sjabloon wilt verwijderen, moet u deze verwijderen uit elk besturingselement waarnaar wordt verwezen. Volg de onderstaande stappen om uw spreadsheet te wijzigen:

1. Zoek op **het tabblad ControlFamily** naar de titel van de verbeteringsactie die u wilt verwijderen.
2. Verwijder de titel van de verbeteringsactie in de cellen waar deze wordt weergegeven. Als de verbeteringsactie de enige actie in die rij is, verwijdert u de hele rij (waardoor het besturingselement wordt verwijderd).
3. Verwijder op **het** tabblad Acties de rij met de verbeteringsactie die u verwijdert.
4. Sla uw spreadsheet op.

Wanneer u uw spreadsheet weer importeert in de sjabloon, wordt de verbeteringsactie verwijderd uit de sjabloon.

Als u een verbeteringsactie uit een sjabloon verwijdert, wordt de verbeteringsactie niet volledig verwijderd uit Compliance Manager. Er kan nog steeds naar deze actie worden verwezen door een andere sjabloon.

#### <a name="remove-a-control"></a>Een besturingselement verwijderen

Als u een besturingselement wilt verwijderen, wijzigt u uw spreadsheet door de onderstaande stappen te volgen en vervolgens uw spreadsheet opnieuw te importeren:

1. Zoek op **het tabblad ControlFamily** het besturingselement dat u wilt verwijderen in de **kolom ControlName.**
2. Verwijder de rij voor dat besturingselement.
    - Als dit verwijderde besturingselement verbeteracties bevat waarnaar niet door een ander besturingselement wordt verwezen, moet u deze verbeteracties verwijderen van het **tabblad** Acties. Anders krijgt u een validatiefout.

3. Sla uw spreadsheet op.

Wanneer u uw spreadsheet weer importeert in de sjabloon, wordt uw besturingselement verwijderd uit de sjabloon.

## <a name="export-a-template"></a>Een sjabloon exporteren

U kunt een Excel met alle gegevens van een sjabloon exporteren. U moet een sjabloon exporteren om de sjabloon te kunnen wijzigen, aangezien dit het Excel bestand is dat u bewerkt en uploadt in het [wijzigingsproces.](#modify-a-template)

Als u de sjabloon wilt exporteren, gaat u naar de pagina met sjabloondetails en selecteert u de knop **Exporteren naar Excel** sjabloon.

Houd er rekening mee dat wanneer u een sjabloon exporteert die u hebt uitgebreid vanuit een compliancebeheersjabloon, het geëxporteerde bestand alleen de kenmerken bevat die u aan de sjabloon hebt toegevoegd. Het geëxporteerde bestand bevat niet de oorspronkelijke sjabloongegevens van Microsoft. Zie de instructies voor het exporteren van een [beoordelingsrapport](compliance-manager-assessments.md#export-an-assessment-report)voor een dergelijk rapport.