---
title: Microsoft 365-rapporten in het beheercentrum - Apparaatgebruik van Microsoft Teams
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 917b3e1d-203e-4439-8539-634e80196687
description: Krijg inzicht in de Microsoft Teams-apps die in uw organisatie worden gebruikt door het gebruiksrapport van Microsoft Teams-apps op te halen uit Microsoft 365-rapporten.
ms.openlocfilehash: 9c79f83d90905470c56fd62489f1439b3383841f
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43621208"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-device-usage"></a>Microsoft 365-rapporten in het beheercentrum - Apparaatgebruik van Microsoft Teams

Het dashboard Microsoft 365 **Rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport App-gebruik in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-apps die in uw organisatie worden gebruikt.
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-service-, Teams-communicatie- of Skype voor Bedrijven-beheerder om rapporten te bekijken.  
 
## <a name="how-to-get-to-the-microsoft-teams-app-usage-report"></a>Zo gaat u naar het rapport App-gebruik in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **Een rapport** selecteren de optie Microsoft **Teams-apparaatgebruik** **Microsoft Teams** \> .
  
## <a name="interpret-the-microsoft-teams-app-usage-report"></a>Het rapport App-gebruikt in Microsoft Teams interpreteren

U kunt inzicht krijgen in het app-gebruik in Microsoft Teams door de grafieken **Gebruikers** en **Distributie** te bekijken. 
  
![Microsoft 365-rapporten - Gebruik van Microsoft Teams-apps](../../media/de35c4de-76b4-4109-a806-66774665499b.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het rapport **Apparaatgebruik in Microsoft Teams** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |In de weergave **Gebruikers** ziet u het aantal unieke gebruikers per app per dag.  <br/> |
|4.  <br/> |In de weergave **Distributie** ziet u het aantal unieke gebruikers per app in de geselecteerde periode.  <br/> |
|5.  <br/> | In de grafiek **Gebruikers** geeft de Y-as het aantal gebruikers per app aan.  <br/>  In de grafiek **Distributie** geeft de Y-as het aantal gebruikers aan dat de opgegeven app heeft gebruikt.  <br/>  De X-as in de grafieken toont het geselecteerde datumbereik voor het specifieke rapport.  <br/> |
|6.  <br/> |U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Gebruikers** **Windows,** **Mac,** **Gesprekken,** **Web,** **Android-telefoon**of **Windows-telefoon** om alleen de informatie te zien die betrekking heeft op elke telefoon. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> ![U de gebruiksgrafieken van Microsoft Teams-apps filteren door het app-type te selecteren.](../../media/64ee1cb1-ca80-4964-8234-7fc671135c3d.png)|
|7.  <br/> | Welke lijst met groepen wordt weergegeven, wordt bepaald door de groepen die bestaan (niet zijn verwijderd) in de ruimste rapportageperiode (180 dagen). Het aantal activiteiten is afhankelijk van de datumselectie.  <br/> OPMERKING: mogelijk ziet u niet alle items in de onderstaande lijst in de kolommen totdat u ze toevoegt.<br/> **Gebruikersnaam** is het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft Teams-activiteit in een app.  <br/> **Verwijderd** geeft aan of het team is verwijderd. Als het team is verwijderd maar activiteiten had in de rapportageperiode, wordt het weergegeven in het raster met Verwijderd ingesteld op Waar.  <br/> **Verwijderd op** is de datum waarop het team is verwijderd.  <br/> **Windows** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in de Windows-app.  <br/> **Mac** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in een Mac-app.  <br/> **Web** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in een web-app.  <br/> **iOS** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in een iOS-app.  <br/> **Android-telefoon** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in een Android-telefoon-app.  <br/> **Windows-telefoon** is ingeschakeld als de gebruiker in de opgegeven periode actief is geweest in een Windows Phone-app.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de **sectie Hoe verberg ik de gegevens op gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|8.  <br/> |Selecteer **Kolommen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![Teams uapp usage report - choose columns](../../media/333f3077-696d-4829-b0a7-1046b3822222.png)|
|9.  <br/> |U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   
  

