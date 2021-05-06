---
title: Een CSV-bestand voorbereiden voor een inhoudszoekactie in een id-lijst
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 82c97bb4-2b64-4edc-804d-cedbda525d22
ms.custom:
- seo-marvel-apr2020
description: Gebruik CSV-bestanden van een bestaande inhoudszoekfunctie om een zoekopdracht in de lijst met id's te maken die specifieke e-mailberichten retourneert.
ms.openlocfilehash: 7b63a78d34306cf3afcef49276e584bc816c107f
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "52161475"
---
# <a name="prepare-a-csv-file-for-an-id-list-content-search"></a>Een CSV-bestand voorbereiden voor een inhoudszoekactie in een id-lijst

U kunt zoeken naar specifieke postvak-e-mailberichten en andere postvakitems met een lijst met Exchange-ed's. Als u een zoekopdracht naar een id-lijst wilt maken (formeel een gerichte zoekopdracht genoemd), dient u een CSV-bestand (door komma's gescheiden waarde) in dat de specifieke postvakitems identificeert die moeten worden gezocht. Voor dit CSV-bestand gebruikt u het **Results.csv-bestand of** het niet-geïndexeerde **Items.csv-bestand** dat is opgenomen wanneer u de resultaten van Inhoudszoekactie exporteert of een inhoudszoekrapport exporteert van en bestaande inhoudszoekactie. Vervolgens bewerkt u een van deze bestanden om de specifieke items aan te geven die u wilt zoeken. Vervolgens maakt u een nieuwe zoekopdracht in de lijst met id's en verstuurt u het CSV-bestand.

Hier is een kort overzicht van het proces voor het maken van een zoekopdracht naar een lijst met id's.

1. Maak en voer een nieuwe of begeleide inhoudszoekactie uit in het & Compliancecentrum.

2. Exporteert de zoekresultaten voor inhoud of exporteert het inhoudszoekrapport. Zie voor meer informatie:

    - [Inhoudszoekresultaten exporteren](export-search-results.md)

    - [Een inhoudszoekrapport exporteren](export-a-content-search-report.md)

3. Bewerk **hetResults.csv** bestand of de niet-geïndexeerde **Items.csv** en identificeer de specifieke postvakitems die u wilt opnemen in de zoekopdracht in de lijst met id's. Zie de [instructies voor](#prepare-the-csv-file-for-an-id-list-search) het voorbereiden van een CSV-bestand voor het zoeken naar een id-lijst.

4. Maak een nieuwe id-lijst zoeken (zie de [instructies)](#create-an-id-list-search)en verzend het CSV-bestand dat u hebt voorbereid. De zoekquery die is gemaakt, zoekt alleen naar de items die zijn geselecteerd in het CSV-bestand.

> [!NOTE]
> Zoekopdrachten in id-lijst worden alleen ondersteund voor postvakitems. U kunt niet zoeken naar SharePoint en OneDrive zoeken in een id-lijst.

 **Waarom een id-lijst zoeken?** Als u niet kunt bepalen of een item reageert op een eDiscovery-aanvraag op basis van de metagegevens in **deResults.csv-** of Niet-geïndexeerde **Items.csv-bestanden,** kunt u een zoekopdracht naar een id-lijst gebruiken om dat item te zoeken, een voorbeeld te bekijken en vervolgens te exporteren om te bepalen of het reageert op de zaak die u onderzoekt. Zoekopdrachten in id-lijst worden meestal gebruikt om een specifieke set niet-geïndexeerde items te zoeken en te retourneren.

## <a name="prepare-the-csv-file-for-an-id-list-search"></a>Het CSV-bestand voorbereiden voor een zoekopdracht in een id-lijst

Nadat u de zoekresultaten of het rapport voor een inhoudszoekactie hebt geëxporteerd, kunt u de volgende stappen uitvoeren om het CSV-bestand voor te bereiden op een zoekopdracht naar een id-lijst. Dit CSV-bestand identificeert elk item in de zoekopdracht id-lijst.

Houd er rekening mee dat u een CSV-bestand kunt gebruiken uit een zoekopdracht die  SharePoint sites en OneDrive-accounts bevat, maar u kunt alleen postvakitems selecteren voor een zoekopdracht in een id-lijst. Als u een document selecteert in SharePoint of OneDrive, mislukt de validatie van het CSV-bestand wanneer u een zoekopdracht naar een id-lijst maakt.

1. Open het **Results.csv** **of niet-geïndexeerd Items.csv** bestand in Excel.

2. Typ **ja** **in** de kolom Geselecteerd in de cel die overeenkomt met het item dat u wilt zoeken. Herhaal deze stap voor elk item dat u wilt zoeken.

    > [!IMPORTANT]
    > Wanneer u het CSV-bestand in Excel opent, wordt de gegevensindeling voor de **kolom Document-id** gewijzigd in **Algemeen.** Dit resulteert in het weergeven van de document-id voor een item in wetenschappelijke notatie. De document-id van '481037338205' wordt bijvoorbeeld weergegeven als '4.81037E+11'. U moet de volgende stappen  uitvoeren om de gegevensindeling van de **kolom Document-id** te wijzigen in Getal om de juiste notatie voor de document-id te herstellen. Als u dit niet doet, mislukt de zoekopdracht id-lijst met het CSV-bestand.

3. Klik met de rechtermuisknop op de hele **kolom Document-id** en selecteer **Cellen opmaken.**

4. Klik in **het** vak Categorie op **Getal**.

5. Wijzig het aantal decimalen in **0** en klik vervolgens op **OK** om de wijzigingen op te slaan. U ziet dat de waarden in de kolom Document-id worden gewijzigd in getallen.

    Hier is een voorbeeld van het CSV-bestand dat klaar is om te worden verzonden voor een zoekopdracht naar inhoud in de lijst met id's.

    ![Voorbeeld van een CSV-bestand voor een gerichte inhoudszoekactie](../media/8371b8cb-1638-496e-9be1-fe1565757d67.png)

6. Sla het CSV-bestand op of gebruik **Opslaan als** om het bestand met een andere bestandsnaam op te slaan. In beide gevallen moet u het bestand opslaan met de CSV-indeling.

## <a name="create-an-id-list-search"></a>Zoeken naar een id-lijst maken

De volgende stap is het maken van een nieuwe id-lijst Inhoud zoeken en het CSV-bestand indienen dat u in de vorige stap hebt voorbereid.

> [!IMPORTANT]
> U moet niet meer dan twee dagen na het exporteren van de resultaten of het rapport vanuit een inhoudszoekactie een zoekactie voor een id-lijst maken. Als de zoekresultaten of het rapport meer dan 2 dagen geleden zijn geëxporteerd, moet u de zoekresultaten of het rapport opnieuw exporteren om bijgewerkte CSV-bestanden te genereren. Vervolgens kunt u een van de bijgewerkte CSV-bestanden voorbereiden en deze gebruiken om een zoekopdracht naar een id-lijst te maken.

1. Ga in het & Compliancecentrum naar **Zoeken naar** inhoud \> **zoeken.**

2. Klik op **de pagina** Zoeken op de pijl naast Pictogram Nieuw ![ zoeken ](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **toevoegen** en klik vervolgens op Zoeken **op id-lijst.**

    ![Klik op Zoeken op id-lijst in de vervolgkeuzelijst Nieuwe zoekopdracht](../media/e65f9942-09b2-4127-865e-e64029a590df.png)

3. In het **flyout** Zoeken op id-lijst geeft u de zoekfunctie een naam (en beschrijft u deze desgewenst) en klikt u op Bladeren en selecteert u het CSV-bestand dat u in de vorige stap hebt voorbereid. 

    Microsoft 365 probeert het CSV-bestand te valideren. Als de validatie mislukt, wordt een foutbericht weergegeven dat u kan helpen bij het oplossen van de validatiefouten. Het CSV-bestand moet worden gevalideerd om een zoekopdracht in een id-lijst te maken.

4. Nadat het CSV-bestand is gevalideerd, klikt u **op Zoeken om** de zoekopdracht in de lijst met id's te maken.

    Hier volgen een voorbeeld van de geschatte zoekresultaten en de query die wordt gegenereerd voor een zoekopdracht in een lijst met id's.

    ![Zoekquery voor een gerichte inhoudszoekactie in het detailvenster](../media/dbd9e570-c04b-4056-a8a7-37e9916ec683.png)

    Het aantal geschatte items dat wordt weergegeven in statistieken voor het zoeken naar id's, moet overeenkomen met het aantal items dat u hebt geselecteerd in het CSV-bestand.

5. Bekijk of exporteert de items die worden geretourneerd door de zoekactie naar de lijst met id's.

> [!NOTE]
> Als u een postvak verplaatst na het maken van een zoekopdracht naar de lijst met id's, worden de opgegeven items niet door de query voor de zoekopdracht retourneerd. De eigenschap **DocumentId** voor postvakitems wordt namelijk gewijzigd wanneer een postvak wordt verplaatst. In het zeldzame geval dat een postvak wordt verplaatst nadat u een zoekopdracht naar een id-lijst hebt gemaakt, moet u een nieuwe inhoudszoekactie maken (of de zoekresultaten bijwerken voor de bestaande inhoudszoekactie) en vervolgens de zoekresultaten of het rapport exporteren om bijgewerkte CSV-bestanden te genereren die kunnen worden gebruikt om een nieuwe zoekopdracht in de lijst met id's te maken.
