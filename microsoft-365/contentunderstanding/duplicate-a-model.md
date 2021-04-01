---
title: Een model dupliceren in Microsoft SharePoint Syntex
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
description: Lees hoe en waarom je een model kunt dupliceren in Microsoft SharePoint Syntex.
ms.openlocfilehash: 501c33b5309ca4af264a361c80fb0409c08c92e3
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445977"
---
# <a name="duplicate-a-model-in-microsoft-sharepoint-syntex"></a>Een model dupliceren in Microsoft SharePoint Syntex

Als je een model met documentbegrip dupliceert, kun je tijd en moeite besparen bij het maken van een nieuw model als je weet dat een bestaand model sterk lijkt op wat je nodig hebt.

Een bestaand model met de naam 'Contracten' classificeert bijvoorbeeld dezelfde bestanden waarmee je moet werken. Het nieuwe model haalt een deel van de bestaande gegevens op, maar moet worden bijgewerkt om extra gegevens op te halen. In plaats van een nieuw model helemaal opnieuw zelf te maken en te trainen, kun je met de functie Model dupliceren een kopie van het model Contracten maken, waarbij ook alle bijbehorende trainingsitems worden gekopieerd, zoals voorbeeldbestanden en entiteitsextractoren.

Wanneer je het model dupliceert en de naam van het model hebt gewijzigd (bijvoorbeeld in 'Contractverlengingen'), kun je het model vervolgens bijwerken. Je kunt bijvoorbeeld sommige bestaande opgehaalde velden verwijderen die je niet nodig hebt en het model vervolgens trainen om een nieuw veld op te halen (bijvoorbeeld 'Verlengingsdatum').

## <a name="duplicate-a-model"></a>Een model dupliceren

Volg deze stappen om een model met documentbegrip te dupliceren.

1. Selecteer in het inhoudscentrum **Modellen** om de lijst met modellen te zien.

2. Selecteer op de pagina **Modellen** het model dat je wilt dupliceren.

3. Gebruik het lint of de knop **Acties weergeven** (naast de modelnaam) om **Dupliceren** te selecteren.</br>

    ![Schermafbeelding van de pagina Modellen met een geselecteerd model waarbij de opties voor dupliceren zijn gemarkeerd.](../media/content-understanding/select-model-duplicate-both.png) </br>

4. In het deelvenster **Model dupliceren**:

   a. Voer bij **Naam** de nieuwe naam in van het model dat je wilt dupliceren.</br>

    ![Schermafbeelding van het deelvenster Model dupliceren.](../media/content-understanding/duplicate-model-panel.png) </br>

   b. Voeg bij **Beschrijving** een beschrijving van het nieuwe model toe.

   c. (Optioneel) Selecteer bij **Geavanceerde instellingen** of je een bestaand [inhoudstype](/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) wilt koppelen.

5. Selecteer **Dupliceren**.

## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[De naam van een model wijzigen](rename-a-model.md)

[Een extractor maken](create-an-extractor.md)

[Overzicht van documentbegrip](document-understanding-overview.md)

[Uitlegtypen](explanation-types-overview.md)

[Een model toepassen](apply-a-model.md) 

[SharePoint Syntex toegankelijkheidsmodus](accessibility-mode.md)