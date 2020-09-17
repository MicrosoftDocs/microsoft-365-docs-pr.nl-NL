---
title: Microsoft 365-rapporten in het Beheercentrum-Forms Pro activity
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
description: Leer hoe u een Microsoft Forms Pro-activiteitenrapport maakt met het Microsoft 365-rapporten dashboard in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 58c7a76c49b7c925a4e7851f7e81c7f47d465d3a
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949190"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-pro-activity"></a>Microsoft 365-rapporten in het Beheercentrum-Forms Pro activity

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker in licentie voor het gebruik van Microsoft Forms Pro met behulp van de interacties met Forms Pro. Met deze functie kunt u ook inzicht krijgen in het samenvatting van het niveau van samenwerking door het aantal Pro-enquêtes te zien waarop de gebruikers hebben gereageerd. 
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Toegang tot het rapport Forms pro-activiteit

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **Forms Pro** \> **Activity**.

## <a name="interpret-the-forms-activity-report"></a>Het rapport formulier activiteit interpreteren

Met de grafieken **activiteit** en **gebruikers** kunt u inzicht krijgen in de activiteiten van de Forms pro-activiteit van uw gebruikers. 

![Rapport met formulier activiteiten](../../media/formsproactivity.png)

|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Forms Pro** activity kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).   <br/> |
|2.  <br/> |De gegevens in elk rapport zijn meestal net zo recent als de laatste 48 uur.  <br/> |
|3.  <br/> |De weergave **gebruikers** helpt u inzicht te krijgen in de trend van het aantal actieve Forms Pro-gebruikers. Als een gebruiker een activiteit rond een pro-enquête heeft uitgevoerd (maken, bewerken, weergeven, enzovoort) binnen een specifieke periode, wordt een gebruiker als actief beschouwd.  <br/> |
|4.  <br/> |De weergave **activiteit** helpt u inzicht te krijgen in de trend van het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.<br/> Opmerking: een activiteit kan meerdere keren voor één enquête plaatsvinden, maar wordt slechts als één actieve enquête geteld. U kunt bijvoorbeeld een pro-enquête maken en dezelfde enquête meerdere keren gedurende een bepaalde periode tegelijk bewerken, maar alleen als één enquête tellen. <br>|
|5.<br/>|In de grafiek **gebruikers** is de Y-as het aantal unieke gebruikers. X-as is de datum waarop de unieke gebruikers actief zijn. De legenda zijn:<br/><br/>**Ontwerpers** betekent dat de gebruiker een enquête voor formulieren Pro heeft gemaakt of bewerkt.<br><br>In de grafiek **activiteit** is de Y-as het aantal formulieren Pro-antwoorden per enquête. X-as is de datum waarop de enquête-of antwoord activiteit heeft plaatsgevonden. De legenda zijn:<br/><br/>**Gemaakte enquêtes** is het aantal unieke enquêtes van Forms Pro dat de gebruikers hebben gemaakt<br>**Antwoorden** is het aantal anonieme of niet-anonieme antwoorden dat de gebruikers die de enquête hebben ontvangen, hebben ingediend. |
|zes.<br/>|U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek gebruikers de optie ontwerpers, responders of totale gebruikers als u alleen de gegevens wilt zien die betrekking hebben op deze personen. Door deze selectie te wijzigen, verandert de informatie in de rastertabel eronder niet.|
|7,5.<br/>|De tabel toont een uitsplitsing van de activiteiten op het niveau per gebruiker. De legenda zijn:<br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit heeft uitgevoerd op Microsoft Forms.<br/>**Datum van laatste activiteit (UTC)** is de datum waarop de laatste formulier activiteit is uitgevoerd door de gebruiker voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/>Hiermee wordt de tabel gefilterd en worden gegevens over Bestandsactiviteiten alleen weergegeven voor gebruikers die de activiteit op die bepaalde dag hebben uitgevoerd.<br/><br/>**Aantal gemaakte enquêtes** is het aantal enquêtes dat de gebruiker heeft gemaakt.<br/> Het aantal antwoord op een **enquête** is het aantal antwoorden van de responders aan wie de enquête is gedistribueerd.|
|8:00.<br/>|Selecteer het pictogram **kolommen beheren** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.|
|aanhaling.<br/>|U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee worden gegevens voor alle gebruikers geëxporteerd en kunt u eenvoudige aggregatie, sorteren en filteren voor verdere analyse uitvoeren. Als u minder dan 100 gebruikers hebt, kunt u in de tabel in het rapport zelf sorteren en filteren. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te filteren en sorteren.|