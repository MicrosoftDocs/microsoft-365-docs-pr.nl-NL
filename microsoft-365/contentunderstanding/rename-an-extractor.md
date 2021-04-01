---
title: De naam van een extractor wijzigen in Microsoft SharePoint Syntex.
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: ssquires
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Lees hoe en waarom je de naam van een extractor kunt wijzigen in Microsoft SharePoint Syntex.
ms.openlocfilehash: 4c0db1d0523e30706a2e6ec31286e5e91adb61a6
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445958"
---
# <a name="rename-an-extractor-in-microsoft-sharepoint-syntex"></a>De naam van een extractor wijzigen in Microsoft SharePoint Syntex.

Op een bepaald moment moet je misschien de naam van een extractor wijzigen als je naar een opgehaald gegevensveld wilt verwijzen met een andere naam. Je organisatie besluit bijvoorbeeld wijzigingen aan te brengen in hun contractdocumenten en in hun documenten naar 'klanten' te verwijzen als 'cliënten'. Als je een veld 'Klant' uit je model ophaalde, kunt je de naam wijzigen in 'Cliënt'.

Wanneer je het bijgewerkte model synchroniseert met je SharePoint-documentbibliotheek zie je een nieuwe kolom 'Cliënt' in de documentbibliotheekweergave. De weergave behoudt de kolom 'Klant' voor eerdere activiteiten, maar de nieuwe kolom 'Cliënt' wordt bijgewerkt voor alle nieuwe documenten die door je model worden verwerkt. 

> [!IMPORTANT]
>  Zorg ervoor dat je het bijgewerkte model synchroniseert naar de documentbibliotheken waarin je het eerder hebt toegepast om de nieuwe kolomnaam ook daar weer te geven. 

## <a name="rename-an-extractor"></a>De naam van een extractor wijzigen

Volg deze stappen om de naam van een entiteitsextractor te wijzigen.

1. Selecteer in het inhoudscentrum **Modellen** om de lijst met modellen te zien.

2. Selecteer op pagina **Modellen** in de kolom **Naam** het model waarvoor je de naam van een extractor wilt wijzigen.

3. Selecteer bij **Entiteitsextractors** de naam van de extractor waarvan je de naam wilt wijzigen en selecteer vervolgens **Naam wijzigen**.</br>

    ![Schermafbeelding van de sectie Entiteitsextractors met een geselecteerde extractor waarbij de optie Naam wijzigen is gemarkeerd.](../media/content-understanding/entity-extractor-rename.png) </br>

4. In het deelvenster **Naam van entiteitsextractor wijzigen**:

   a. Voer bij **Nieuwe naam** de nieuwe naam van de extractor in.</br>

    ![Schermafbeelding van het deelvenster Entiteitsextractors.](../media/content-understanding/rename-entity-extractor-panel.png) </br>

   b. (Optioneel) Selecteer bij **Geavanceerde instellingen** of je een bestaande Sitekolom wilt koppelen.

5. Selecteer **Naam wijzigen**.

## <a name="see-also"></a>Zie ook
[Een extractor maken](create-an-extractor.md)

[Een classificatie maken](create-a-classifier.md)

[De naam van een model wijzigen](rename-a-model.md)

[Uitlegtypen](explanation-types-overview.md)

[De taxonomie van een termenarchief benutten bij het maken van een extractor](leverage-term-store-taxonomy.md)

[Overzicht van documentbegrip](document-understanding-overview.md)

[Een model toepassen](apply-a-model.md) 
