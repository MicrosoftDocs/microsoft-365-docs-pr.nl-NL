---
title: Microsoft 365-rapporten in het Beheercentrum-Dynamics 365 voor spraak activiteiten klant
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Leer hoe u een Microsoft Dynamics 365-rapport voor spraak activiteiten van klanten ontvangt met behulp van het dashboard Microsoft 365-rapporten in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: de03067197c80634f02318b35a79eb84e33c4b86
ms.sourcegitcommit: 82d8be71c5861a501ac62a774b306a3fc1d4e627
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/10/2020
ms.locfileid: "48988550"
---
# <a name="microsoft-365-reports-in-the-admin-center---dynamics-365-customer-voice-activity"></a>Microsoft 365-rapporten in het Beheercentrum-Dynamics 365 voor spraak activiteiten klant

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker in licentie voor het gebruik van Microsoft Dynamics 365 Customer Voice door te kijken naar de interacties met een klant spraak van Dynamics 365. Met deze functie kunt u ook inzicht krijgen in het samenvatting van het niveau van samenwerking door het aantal Pro-enquêtes te zien waarop de gebruikers hebben gereageerd. 
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Toegang tot het rapport Forms pro-activiteit

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **Dynamics 365 Customer Voice** \> **Activity**.

## <a name="interpret-the-dynamics-365-customer-voice-activity-report"></a>Het rapport Dynamics 365 voor spraak activiteiten van klant interpreteren

Met de grafieken **activiteit** en **gebruikers** kunt u inzicht krijgen in de facturerings activiteiten van uw gebruikers voor Dynamics 365. 

![Rapport met formulier activiteiten](../../media/formsproactivity.png)

|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Dynamics 365 Customer Voice** activity kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).   <br/> |
|2.  <br/> |De gegevens in elk rapport zijn meestal net zo recent als de laatste 48 uur.  <br/> |
|3.  <br/> |De weergave **gebruikers** helpt u inzicht te krijgen in de trend van het aantal actieve gebruikers van de gebruikers van Dynamics 365. Als een gebruiker een activiteit rond een pro-enquête heeft uitgevoerd (maken, bewerken, weergeven, enzovoort) binnen een specifieke periode, wordt een gebruiker als actief beschouwd.  <br/> |
|4.  <br/> |De weergave **activiteit** helpt u inzicht te krijgen in de trend van het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.<br/> Opmerking: een activiteit kan meerdere keren voor één enquête plaatsvinden, maar wordt slechts als één actieve enquête geteld. U kunt bijvoorbeeld een pro-enquête maken en dezelfde enquête meerdere keren gedurende een bepaalde periode tegelijk bewerken, maar alleen als één enquête tellen. <br>|
|5.<br/>|In de grafiek **gebruikers** is de Y-as het aantal unieke gebruikers. X-as is de datum waarop de unieke gebruikers actief zijn. De legenda zijn:<br/><br/>**Ontwerpers** betekent dat de gebruiker een Dynamics 365 voor spraak onderzoek voor de klant heeft gemaakt of bewerkt.<br><br>In de grafiek **activiteit** is de Y-as het aantal aanvragen voor de Voice 365 van de klant van een enquête. X-as is de datum waarop de enquête-of antwoord activiteit heeft plaatsgevonden. De legenda zijn:<br/><br/>**Gemaakte enquêtes** is het aantal unieke spraak enquêtes voor een klant van 365 dat de gebruikers hebben gemaakt.<br>**Antwoorden** is het aantal anonieme of niet-anonieme antwoorden dat de gebruikers die de enquête hebben ontvangen, hebben ingediend. |
|zes.<br/>|U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek gebruikers de optie ontwerpers, responders of totale gebruikers als u alleen de gegevens wilt zien die betrekking hebben op deze personen. Door deze selectie te wijzigen, verandert de informatie in de rastertabel eronder niet.|
|7,5.<br/>|De tabel toont een uitsplitsing van de activiteiten op het niveau per gebruiker. De legenda zijn:<br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit heeft uitgevoerd op Microsoft Forms.<br/>**Datum van laatste activiteit (UTC)** is de datum waarop de laatste formulier activiteit is uitgevoerd door de gebruiker voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/>Hiermee wordt de tabel gefilterd en worden gegevens over Bestandsactiviteiten alleen weergegeven voor gebruikers die de activiteit op die bepaalde dag hebben uitgevoerd.<br/><br/>**Aantal gemaakte enquêtes** is het aantal enquêtes dat de gebruiker heeft gemaakt.<br/> Het aantal antwoord op een **enquête** is het aantal antwoorden van de responders aan wie de enquête is gedistribueerd.|
|8:00.<br/>|Selecteer het pictogram **kolommen beheren** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.|
|aanhaling.<br/>|U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee worden gegevens voor alle gebruikers geëxporteerd en kunt u eenvoudige aggregatie, sorteren en filteren voor verdere analyse uitvoeren. Als u minder dan 100 gebruikers hebt, kunt u in de tabel in het rapport zelf sorteren en filteren. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te filteren en sorteren.|