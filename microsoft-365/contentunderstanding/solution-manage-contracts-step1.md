---
title: Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Informatie over het gebruik van SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen met een Microsoft 365 oplossing.
ms.openlocfilehash: b73f7b96a1f1a9159770fb1bfb20bf2718f08c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287351"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen

Uw organisatie heeft een manier nodig om alle contractdocumenten te identificeren en te classificeren van de vele bestanden die u ontvangt. U wilt ook snel verschillende belangrijke elementen kunnen bekijken in elk van de geïdentificeerde contractbestanden (bijvoorbeeld *Client,* *Contractant* en *Kostenbedrag).* U kunt dit doen door een document [SharePoint Syntex](index.md) te maken en toe te passen op een documentbibliotheek.

## <a name="overview-of-the-process"></a>Overzicht van het proces

[Documentkennis](document-understanding-overview.md) maakt gebruik van AI-modellen (Artificial Intelligence) om de classificatie van bestanden en de extractie van informatie te automatiseren. Documentkennismodellen zijn ook optimaal voor het extraheren van informatie uit ongestructureerde en semi-gestructureerde documenten waarin de informatie die u nodig hebt, niet is opgenomen in tabellen of formulieren, zoals contracten. 

Documentbegripmodellen gebruiken Optical Character Recognition- (OCR) technologie om pdf-bestanden, afbeeldingen en tiff-bestanden te scannen wanneer je een model traint met voorbeeldbestanden en wanneer je het model uitvoert op bestanden in een documentbibliotheek.

1. Eerst moet u ten minste vijf voorbeeldbestanden zoeken die u kunt gebruiken om het model te 'trainen' om te zoeken naar kenmerken die specifiek zijn voor het inhoudstype dat u wilt identificeren (een contract). 

2. Met SharePoint Syntex maakt u een nieuw documentkennismodel. Als u uw voorbeeldbestanden gebruikt, moet u [een classificatie maken.](create-a-classifier.md) Door de classificatie te trainen met uw voorbeeldbestanden, leert u deze om te zoeken naar kenmerken die specifiek zijn voor wat u zou zien in de contracten van uw bedrijf. Maak bijvoorbeeld [een 'uitleg'](create-a-classifier.md#create-an-explanation) waarin wordt gezocht naar specifieke tekenreeksen die in uw contracten staan, zoals *Serviceovereenkomst,* Overeenkomstsvoorwaarden en  *Compensatie.* U kunt zelfs uw uitleg trainen om te zoeken naar deze tekenreeksen in specifieke secties van het document of naast andere tekenreeksen. Wanneer u denkt dat u uw classificatie hebt opgeleid met de informatie die het nodig heeft, kunt u uw model testen op een voorbeeldset met voorbeeldbestanden om te zien hoe efficiënt het is. Na het testen kunt u indien nodig wijzigingen aanbrengen in uw uitleg om ze efficiënter te maken. 

3. In uw model kunt u [een extractor](create-an-extractor.md) maken om specifieke gegevens uit elk contract te halen. Voor elk contract is de informatie waar u zich het meest zorgen over maakt bijvoorbeeld wie de klant is, de naam van de contractant en de totale kosten.

4. Nadat u het model hebt gemaakt, kunt u het toepassen [op een SharePoint documentbibliotheek.](apply-a-model.md) Wanneer u documenten uploadt naar de documentbibliotheek, wordt uw documentkennismodel uitgevoerd en worden alle bestanden die overeenkomen met het inhoudstype contracten dat u in uw model hebt gedefinieerd, identificeren en classificeren. Alle bestanden die als contracten zijn geclassificeerd, worden weergegeven in een aangepaste bibliotheekweergave. In de bestanden worden ook de waarden weergegeven van elk contract dat u hebt gedefinieerd in de extractor.

   ![Contracten in documentbibliotheek](../media/content-understanding/doc-lib-solution.png)

5. Als u bewaar- of beveiligingsvereisten voor uw contracten hebt, [](apply-a-retention-label-to-a-model.md) kunt u [](apply-a-sensitivity-label-to-a-model.md) uw model ook gebruiken om een bewaarlabel of een gevoeligheidslabel toe te passen waardoor uw contracten niet voor een bepaalde periode worden verwijderd of om te beperken wie toegang heeft tot de contracten.

## <a name="steps-to-create-and-train-your-model"></a>Stappen voor het maken en trainen van uw model

> [!NOTE]
> Voor deze stappen kunt u de voorbeeldbestanden gebruiken in de [opslagplaats Voor oplossingsactiva voor contractenbeheer.](https://github.com/pnp/syntex-samples/tree/main/scenario%20assets/Contracts%20Management) De voorbeelden in deze opslagplaats bevatten zowel de documentkennis van modelbestanden als de bestanden die worden gebruikt om het model te trainen.

### <a name="create-a-contract-model"></a>Een contractmodel maken

De eerste stap is het maken van uw contractmodel.

1. Selecteer in het Inhoudscentrum **Nieuw** en klik vervolgens **Maak een model**.

2. Typ in **het deelvenster Nieuw documenttypemodel** in het veld **Naam** de naam van het model. Voor deze oplossing voor contractbeheer kunt u het modelContract een naam *geven.*

4. Kies **Create**. Hiermee maa je een startpagina voor het model.</br>

    ![Schermafbeelding van de startpagina contract.](../media/content-understanding/models-contract-home-page.png)


### <a name="train-your-model-to-classify-a-type-of-file"></a>Uw model trainen om een type bestand te classificeren

#### <a name="add-example-files-for-your-model"></a>Voorbeeldbestanden voor uw model toevoegen

U moet ten minste vijf voorbeeldbestanden toevoegen die contractdocumenten zijn en één voorbeeldbestand dat geen contractdocument is (bijvoorbeeld een werkoverzicht). 

1. Selecteer op **de pagina > Contract** onder Belangrijke **acties**  >  **Voorbeeldbestanden** toevoegen de optie **Bestanden toevoegen.**

   ![Schermafbeelding met de pagina Contracten met de optie Voorbeeldbestanden toevoegen gemarkeerd.](../media/content-understanding/key-actions-add-example-files.png)

2. Open op **de pagina Voorbeeldbestanden selecteren** voor uw model de map Contract, selecteer bestanden die u wilt gebruiken en selecteer vervolgens **Toevoegen.** Als u daar geen voorbeeldbestanden hebt, selecteert **u Upload** om ze toe te voegen.

#### <a name="label-the-files-as-positive-or-negative-examples"></a>De bestanden labelen als positieve of negatieve voorbeelden

1. Selecteer op **de pagina > Contract** onder Belangrijke **acties** Bestanden classificeren en  >  **training** uitvoeren de optie **Train classifier**.

   ![Schermafbeelding met de pagina Contracten met Bestanden classificeren en trainingsoptie uitvoeren gemarkeerd.](../media/content-understanding/key-actions-classify-files.png)

2. Op de pagina > **Contract > Contract classifier** ziet u in de viewer boven aan het eerste voorbeeldbestand tekst met de vraag of het bestand een voorbeeld is van het contractmodel dat u hebt gemaakt. Als het om een positief voorbeeld gaat, selecteer je **Ja**. Als het om een negatief voorbeeld gaat, selecteer je **Nee**.

3. Selecteer in **de lijst Gelabelde** voorbeelden aan de linkerkant andere bestanden die u als voorbeelden wilt gebruiken en label ze. 

    ![Startpagina voor classificatie](../media/content-understanding/models-contract-classifier.png) 

#### <a name="add-at-least-one-explanation-to-train-the-classifier"></a>Voeg ten minste één uitleg toe om de classificatie te trainen 

1. Selecteer op **de pagina > contract > de pagina Contractclassifier** het **tabblad** Trein.

2. In de **sectie Getrainde** bestanden ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld. Selecteer een van de positieve bestanden in de lijst om deze weer te geven in de viewer.

3. Selecteer in **de sectie Uitleg** de optie **Nieuw** en vervolgens **Leeg.**

4. Op de pagina **Maak een uitleg**:

    a. Typ in **het** veld Naam de naam van de uitleg (zoals 'Overeenkomst').

    b. Selecteer in **het veld Uitlegtype** de optie **Lijst Woordgroep** omdat u een tekenreeks toevoegt.

    c. Typ in **de lijst Woordgroep** de tekenreeks (zoals 'OVEREENKOMST'). U kunt Case **sensitive selecteren** als de tekenreeks case-sensitive moet zijn.

    d. Selecteer **Opslaan en trainen.**

    ![Schermafbeelding van het deelvenster Uitleg maken.](../media/content-understanding/contract-classifier-create-explanation.png) 

#### <a name="test-your-model"></a>Test je model.

U kunt uw contractmodel testen op voorbeeldbestanden die u nog niet eerder hebt gezien. Dit is optioneel, maar kan handig zijn.

1. Selecteer op **de pagina > Contract > contractclassifier** het **tabblad** Testen. Hiermee wordt het model uitgevoerd op uw voorbeeldbestanden zonder label.

2. In de **lijst Testbestanden** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model voorspelde dat ze positief of negatief waren. Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.

    ![Schermafbeelding van de niet-gemarkeerde bestanden in de lijst Tekstbestanden](../media/content-understanding/test-on-files.png) 

3. Wanneer u klaar bent, **selecteert u Training afsluiten.**

### <a name="create-and-train-an-extractor"></a>Een extractor maken en trainen

1. Selecteer op **de pagina >** contract onder Belangrijke acties Extractoren maken en trainen de optie  >   **Extractor maken.**

   ![Schermafbeelding met de pagina Contracten met de optie Extractoren maken en trainen gemarkeerd.](../media/content-understanding/key-actions-create-extractors.png)

2. Typ in **het deelvenster Nieuwe entiteitsextractor** in het veld **Nieuwe** naam de naam van de extractor. Noem de client bijvoorbeeld *Client als* u de naam van de client uit elk contract wilt oppakken.

3. Wanneer u klaar bent, selecteert u **Maken.**

#### <a name="label-the-entity-you-want-to-extract"></a>Label de entiteit die u wilt oppakken

Wanneer u de extractor maakt, wordt de extractorpagina geopend. Hier zie je een lijst met je voorbeeldbestanden, met het eerste bestand in de lijst die wordt weergegeven in de viewer.

![Schermafbeelding van de pagina Voorbeelden van clientextractor Labeled.](../media/content-understanding/client-extractor-labeled-examples.png) 

De entiteit een label geven:

1. Selecteer in de viewer de gegevens die je wilt ophalen uit de bestanden. Als u bijvoorbeeld de client wilt extraheren, markeert u de clientwaarde in het eerste bestand (in dit voorbeeld *Best For You Organics)* en selecteert u **Opslaan.** U ziet de waardeweergave van het bestand in de lijst **Gelabelde** voorbeelden, onder de **kolom** Label.

2. Selecteer **Volgende bestand** om het volgende bestand in de lijst in de viewer automatisch op te geven en te openen. Of selecteer **Opslaan** en selecteer vervolgens een ander bestand in de **lijst Gelabelde** voorbeelden.

3. Herhaal in de viewer stap 1 en 2 en herhaal dit totdat u het label in alle bestanden hebt opgeslagen.

Nadat u de bestanden hebt gelabeld, wordt er een meldingsbanner weergegeven met de mededeling dat u naar de training moet gaan. U kunt ervoor kiezen om meer documenten te labelen of door te gaan naar de training.

#### <a name="add-an-explanation"></a>Voeg een uitleg toe

U kunt een uitleg maken waarin een hint wordt gegeven over de entiteitsindeling zelf en variaties in de voorbeeldbestanden. Een datumwaarde kan bijvoorbeeld in veel verschillende indelingen zijn, zoals:

- 10/14/2019
- 14 oktober 2019
- Maandag 14 oktober 2019

Als u de begindatum *van het contract wilt identificeren,* kunt u een patroonverklaring maken.

1. Selecteer in **de sectie Uitleg** de optie **Nieuw** en vervolgens **Leeg.**

2. Op de pagina **Maak een uitleg**:

    a. Typ in **het** veld Naam de naam van de uitleg (zoals *Datum).*

    b. Selecteer in **het veld Uitlegtype** **de optie Patroonlijst**.

    c. Geef in **het** veld Waarde de datumvariatie op zoals deze worden weergegeven in de voorbeeldbestanden. Als je bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, geef je de variaties op die worden weergegeven in je documenten, zoals:

    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000

4. Selecteer **Opslaan en trainen.**

#### <a name="test-your-model-again"></a>Test uw model opnieuw

U kunt uw contractmodel testen op voorbeeldbestanden die u nog niet eerder hebt gezien. Dit is optioneel, maar kan handig zijn.

1. Selecteer op **de pagina > Contract > contractclassifier** het **tabblad** Testen. Hiermee wordt het model uitgevoerd op uw voorbeeldbestanden zonder label.

2. In de **lijst Testbestanden** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model de gegevens kan oppakken die u nodig hebt. Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.

3. Wanneer u klaar bent, **selecteert u Training afsluiten.**

### <a name="apply-your-model-to-a-document-library"></a>Uw model toepassen op een documentbibliotheek

Als u uw model wilt toepassen op een SharePoint documentbibliotheek:

1. Selecteer op **de pagina > Contract** onder Sleutelacties Model toepassen op   >  **bibliotheken** de optie Model **toepassen.**

   ![Schermafbeelding met de pagina Contracten met de optie Model toepassen op bibliotheken gemarkeerd.](../media/content-understanding/key-actions-apply-model.png)

2. Selecteer in **het deelvenster Contract** toevoegen de SharePoint site met de documentbibliotheek waarin u het model wilt toepassen. Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om de site te vinden. Kies **Toevoegen**.

    > [!NOTE]
    > U moet beschikken over de machtiging *Lijst beheren* of *Machtiging voor bewerken* voor de documentbibliotheek waarop u het model toepast.

3. Nadat u de site hebt geselecteerd, selecteert u de documentbibliotheek waarop u het model wilt toepassen.

4. Omdat het model is gekoppeld aan een inhoudstype, wordt het inhoudstype en de weergave ervan toegevoegd wanneer u dit op de bibliotheek toevoegt, met de labels die u hebt geëxtraheerd en die als kolommen worden weergegeven. Deze weergave is standaard de standaardweergave van de bibliotheek, maar u kunt er  desgewenst voor kiezen deze weergave niet de standaardweergave te laten zijn door Geavanceerde instellingen te selecteren en het selectievakje Deze nieuwe weergave als standaard instellen uit **te** sluiten.

5. Selecteer **Toevoegen** om het model toe te passen op de bibliotheek.

6. Op de **pagina > contract** ziet u in de sectie Bibliotheken met dit **model** de URL naar de SharePoint site.

    ![Schermafbeelding van de startpagina Contract met de sectie Bibliotheken met dit model.](../media/content-understanding/contract-libraries-with-this-model.png)

7. Onder **Instellingen**  >  **Bibliotheekinstellingen:**

   - Voeg een kolom met de naam **Status** toe en **selecteer Keuze** als kolomtype.
   - Pas de **waarden In revisie,** **Goedgekeurd** en **Geweigerd** toe.

Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.

## <a name="next-step"></a>Volgende stap

[Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken](solution-manage-contracts-step2.md)