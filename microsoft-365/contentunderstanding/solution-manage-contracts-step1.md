---
title: Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen met een Microsoft 365 oplossing.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281129"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Stap 1. Gebruik SharePoint Syntex om contractbestanden te identificeren en gegevens op te halen

Uw organisatie heeft een manier nodig om alle contractdocumenten te identificeren en te classificeren van de vele bestanden die u ontvangt. U wilt ook snel verschillende belangrijke elementen kunnen bekijken in elk van de geïdentificeerde contractbestanden (bijvoorbeeld *Client,* *Contractant* en *Kostenbedrag).* U kunt dit doen met behulp [SharePoint Syntex](index.md) om een documentkennismodel te maken en toe te passen op een documentbibliotheek.

[Documentkennis](document-understanding-overview.md) maakt gebruik van AI-modellen (Artificial Intelligence) om de classificatie van bestanden en de extractie van informatie te automatiseren. Documentkennismodellen zijn ook optimaal voor het extraheren van informatie uit ongestructureerde en semi-gestructureerde documenten waarin de informatie die u nodig hebt, niet is opgenomen in tabellen of formulieren, zoals contracten.

1. Eerst moet u ten minste vijf voorbeeldbestanden zoeken die u kunt gebruiken om het model te 'trainen' om te zoeken naar kenmerken die specifiek zijn voor het inhoudstype dat u wilt identificeren (een contract). 

2. Met SharePoint Syntex maakt u een nieuw documentkennismodel. Als u uw voorbeeldbestanden gebruikt, moet u [een classificatie maken.](create-a-classifier.md) Door de classificatie te trainen met uw voorbeeldbestanden, leert u deze om te zoeken naar kenmerken die specifiek zijn voor wat u zou zien in de contracten van uw bedrijf. Maak bijvoorbeeld [een 'uitleg'](create-a-classifier.md#create-an-explanation) waarin wordt gezocht naar specifieke tekenreeksen die in uw contracten staan, zoals *Serviceovereenkomst,* Overeenkomstsvoorwaarden en  *Compensatie.* U kunt zelfs uw uitleg trainen om te zoeken naar deze tekenreeksen in specifieke secties van het document of naast andere tekenreeksen. Wanneer u denkt dat u uw classificatie hebt opgeleid met de informatie die het nodig heeft, kunt u uw model testen op een voorbeeldset met voorbeeldbestanden om te zien hoe efficiënt het is. Na het testen kunt u indien nodig wijzigingen aanbrengen in uw uitleg om ze efficiënter te maken. 

3. In uw model kunt u [een extractor](create-an-extractor.md) maken om specifieke gegevens uit elk contract te halen. Voor elk contract is de informatie waar u zich het meest zorgen over maakt bijvoorbeeld wie de klant is, de naam van de contractant en de totale kosten.

4. Nadat u het model hebt gemaakt, kunt u het toepassen [op een SharePoint documentbibliotheek.](apply-a-model.md) Wanneer u documenten uploadt naar de documentbibliotheek, wordt uw documentkennismodel uitgevoerd en worden alle bestanden die overeenkomen met het inhoudstype contracten dat u in uw model hebt gedefinieerd, identificeren en classificeren. Alle bestanden die als contracten zijn geclassificeerd, worden weergegeven in een aangepaste bibliotheekweergave. In de bestanden worden ook de waarden weergegeven van elk contract dat u hebt gedefinieerd in de extractor.

   ![Contracten in documentbibliotheek](../media/content-understanding/doc-lib-solution.png)

5. Als u bewaarvereisten voor uw contracten hebt, kunt u [](apply-a-retention-label-to-a-model.md) uw model ook gebruiken om een bewaarlabel toe te passen dat voorkomt dat uw contracten voor een bepaalde periode worden verwijderd.

## <a name="next-step"></a>Volgende stap

[Stap 2. Gebruik Microsoft Teams om uw contractbeheerkanaal te maken](solution-manage-contracts-step2.md)