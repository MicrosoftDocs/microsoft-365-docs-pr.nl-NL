---
title: Inhoudszoekbewerkingen bulksgewijs bewerken
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/29/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 39e4654a-9588-41f6-892b-c33ab57bfbe2
ms.custom:
- seo-marvel-apr2020
description: Gebruik de bulkzoekeditor in het beveiligings- en compliancecentrum om snel de query- en inhoudslocaties voor een of meer inhoudszoekingen te wijzigen.
ms.openlocfilehash: be7e37ec22966e16dfa3c6d1f37a34e6441e632a
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341030"
---
# <a name="bulk-edit-content-searches"></a>Inhoudszoekbewerkingen bulksgewijs bewerken

U kunt de bulkzoekeditor in het hulpprogramma Inhoud zoeken gebruiken om meerdere zoekopdrachten tegelijk te bewerken. Met dit hulpprogramma kunt u snel de query- en inhoudslocaties wijzigen voor een of meer zoekopdrachten. Vervolgens kunt u de zoekopdrachten opnieuw doen en nieuwe geschatte zoekresultaten voor de gewijzigde zoekopdrachten krijgen. Met de editor kunt u ook query's en inhoudslocaties uit een Microsoft Excel of tekstbestand kopiëren en plakken. Dit betekent dat u het hulpprogramma Zoekstatistieken kunt gebruiken om de statistieken van een of meer zoekopdrachten weer te geven, de statistieken te exporteren naar een CSV-bestand, waar u de query's en inhoudslocaties in Excel. Vervolgens gebruikt u bulkzoekeditor om de gewijzigde query's en inhoudslocaties toe te voegen aan de zoekopdrachten. Nadat u een of meer zoekopdrachten hebt gewijzigd, kunt u deze opnieuw starten en nieuwe geschatte zoekresultaten krijgen.

Zie Trefwoordstatistieken weergeven voor [inhoudszoekresultaten](view-keyword-statistics-for-content-search.md)voor meer informatie over het gebruik van het hulpprogramma Zoekstatistieken.

## <a name="use-the-bulk-search-editor-to-change-queries"></a>De bulkzoekeditor gebruiken om query's te wijzigen

1. Ga naar <https://compliance.microsoft.com> en selecteer vervolgens Inhoud **zoeken.**

2. Selecteer in de lijst met zoekopdrachten een of meer zoekopdrachten en selecteer vervolgens **Bulk Search Editor** Bulk Search Editor button ![ ](../media/1ddb3d18-2f00-4a7b-98a6-817ca5ec7014.png) .

    ![Selecteer een of meer zoekopdrachten en selecteer vervolgens Bulkzoekeditor](../media/600c9716-89a2-4451-b111-fa7cfaad2006.png)

    De volgende informatie wordt weergegeven op de pagina **Query's** van de bulkzoekeditor.

    ![Op de pagina Bulkzoekeditor worden de query's voor de geselecteerde zoekopdrachten weergegeven](../media/189659af-cc78-4479-b0bc-a93decad2f6c.png)

    a. In **de** kolom Zoeken wordt de naam van het zoeken naar inhoud weergegeven. Zoals eerder vermeld, kunt u de query bewerken voor meerdere zoekopdrachten.

    b. In **de kolom** Query wordt de query voor het zoeken naar inhoud weergegeven in de **kolom** Zoeken. Als de query is gemaakt met de functie trefwoordlijst, worden de trefwoorden gescheiden door de **`(c:s)`** tekst. Dit geeft aan dat de trefwoorden zijn verbonden door de **operator OF.** Als de query voorwaarden bevat, worden de trefwoorden en de voorwaarden gescheiden door de **`(c:c)`** tekst. Dit geeft aan dat de trefwoorden (of trefwoordfasen) zijn verbonden met de voorwaarden van de **operator AND.** In de vorige schermafbeelding van de zoekopdracht ContosoSearch1 is de KQL-query bijvoorbeeld gelijk aan `customer (c:s) pricing(c:c)(date=2000-01-01..2016-09-30)`  `(customer OR pricing) AND (date=2002-01-01..2016-09-30)` .

3. Als u een query wilt bewerken, selecteert u in de cel van de query die u wilt wijzigen en doet u een van de volgende dingen. De cel wordt begrensd door een blauw vak wanneer u deze selecteert.

   - Typ de nieuwe query in de cel. U kunt een deel van de query niet bewerken. U moet de hele query typen.

      Of

   - Plak een nieuwe query in de cel. Er wordt ervan uitgenomen dat u de querytekst uit een bestand hebt gekopieerd, zoals een tekstbestand of een Excel bestand.

4. Nadat u een of meer query's  op de pagina Query's hebt bewerkt, selecteert u **Opslaan.**

    De gewijzigde query wordt weergegeven in de **kolom Query** voor de geselecteerde zoekopdracht.

5. Selecteer **Sluiten om** de bulkzoekeditor te sluiten.

6. Selecteer op **de pagina Inhoud** zoeken de zoekopdracht die u hebt bewerkt en selecteer **Zoeken** starten om de zoekopdracht opnieuw te starten met de gewijzigde query.

Hier zijn enkele tips voor het bewerken van query's met de bulkzoekeditor:

- Kopieer de bestaande query (met **Ctrl C)** naar een tekstbestand. Bewerk de query in het tekstbestand en kopieer de gewijzigde query en plak deze (met **Ctrl V)** terug in de cel op de **pagina Query's.**

- U kunt ook query's uit andere toepassingen kopiëren (zoals Microsoft Word of Microsoft Excel). U kunt echter per ongeluk niet-ondersteunde tekens toevoegen aan een query met de bulkzoekeditor. De beste manier om niet-ondersteunde tekens te voorkomen, is door de query in een cel op de pagina **Query's te** typen. U kunt ook een query kopiëren uit Word of Excel en deze vervolgens plakken in een tekst zonder opmaak, zoals Microsoft Kladblok. Sla het tekstbestand op en selecteer **ANSI** in de **vervolgkeuzelijst** Codering. Hiermee worden alle opmaak en niet-ondersteunde tekens verwijderd. Vervolgens kunt u de query kopiëren en plakken van het tekstbestand naar de **pagina Query's.**

## <a name="use-the-bulk-search-editor-to-change-content-locations"></a>De bulkzoekeditor gebruiken om inhoudslocaties te wijzigen

1. Selecteer in de bulkzoekeditor voor een of meer geselecteerde zoekopdrachten  de optie Bulklocatieeditor inschakelen en selecteer vervolgens de koppeling Locaties die op de pagina wordt weergegeven.

    De volgende informatie wordt weergegeven op de pagina **Locaties** van de bulkzoekeditor.

    ![Selecteer Bulklocatieeditor inschakelen en selecteer vervolgens Locaties om inhoudslocaties toe te voegen of te verwijderen](../media/a5a468ce-bd63-4c53-bc37-ff64cf769e59.png)

    a. **Postvakken om te zoeken** In deze sectie ziet u een kolom voor elke geselecteerde inhoudszoekfunctie en een rij voor elk postvak dat is opgenomen in de zoekopdracht. Een vinkje geeft aan dat het postvak is opgenomen in de zoekopdracht. U kunt postvakken toevoegen aan een zoekopdracht door het e-mailadres van het postvak in een lege rij te typen en vervolgens het selectievakje in te selecteren voor het zoeken naar inhoud aan wie u het wilt toevoegen. U kunt ook een postvak uit een zoekopdracht verwijderen door het selectievakje uit te wissen.

    b. **SharePoint sites om te zoeken** In deze sectie wordt een rij weergegeven voor SharePoint en OneDrive site die is opgenomen in elke geselecteerde inhoudszoekfunctie. Een vinkje geeft aan dat de site is opgenomen in de zoekopdracht. U kunt sites toevoegen aan een zoekopdracht door de URL voor de site in een lege rij te typen en vervolgens het selectievakje in te stellen voor de inhoudszoekfunctie aan wie u deze wilt toevoegen. U kunt ook een site verwijderen uit een zoekopdracht door het selectievakje uit te wissen.

    c. **Andere zoekopties** In deze sectie wordt aangegeven of niet-geïndexeerde items en openbare mappen zijn opgenomen in de zoekopdracht. Als u deze wilt opnemen, moet u ervoor zorgen dat het selectievakje is ingeschakeld. Als u ze wilt verwijderen, verwijdert u het selectievakje.

2. Nadat u een of meer secties op  de pagina Locaties hebt bewerkt, selecteert u **Opslaan.**

    De gewijzigde inhoudslocaties worden weergegeven in de juiste sectie voor de geselecteerde zoekopdrachten.

3. Selecteer **Sluiten om** de bulkzoekeditor te sluiten.

4. Selecteer op **de pagina Inhoud** zoeken de zoekopdracht die u hebt bewerkt en selecteer **Zoeken** starten om de zoekopdracht opnieuw op te starten met de gewijzigde inhoudslocaties.

Hier zijn enkele tips voor het bewerken van inhoudslocaties met de bulkzoekeditor:

- U kunt Inhoud zoeken bewerken om in alle postvakken of sites in  de organisatie te zoeken door Alles **in** een lege rij in de **postvakken** te typen om te zoeken SharePoint sites te zoeken en het selectievakje in te selecteren.

- U kunt meerdere inhoudslocaties toevoegen aan een of meer zoekopdrachten door meerdere rijen uit een tekstbestand of een Excel-bestand te kopiëren en deze vervolgens te kopiëren in een sectie op de pagina **Locaties.** Nadat u nieuwe locaties hebt toevoegt, moet u het selectievakje in- of selecteren voor elke zoekopdracht aan wie u de locatie wilt toevoegen.

    > [!TIP]
    > Als u een lijst met e-mailadressen wilt genereren voor alle gebruikers in uw organisatie, moet u de opdracht PowerShell uitvoeren in stap 2 in stap [2: Een](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md#step-2-generate-a-list-of-users)lijst met gebruikers genereren. Of volg de stappen in [Een lijst met](/onedrive/list-onedrive-urls) alle gebruikersgegevens OneDrive in uw organisatie om een lijst te genereren met alle OneDrive voor Bedrijven sites in uw organisatie. Houd er rekening mee dat u de URL voor het MySite-domein van uw organisatie moet toevoegen (bijvoorbeeld aan de OneDrive voor Bedrijven sites die door het https://contoso-my.sharepoint.com) script zijn gemaakt. Nadat u een lijst met e-mailadressen of OneDrive voor Bedrijven sites hebt,  kunt u deze kopiëren en plakken naar de pagina Locaties in de bulkzoekeditor.

- Nadat u Opslaan **hebt geselecteerd om** wijzigingen op te slaan in bulkzoekeditor, wordt het e-mailadres voor postvakken dat u aan een zoekopdracht hebt toegevoegd, gevalideerd. Als het e-mailadres niet bestaat, wordt een foutbericht weergegeven met de melding dat het postvak niet kan worden gevonden. URL's voor sites worden niet gevalideerd.
