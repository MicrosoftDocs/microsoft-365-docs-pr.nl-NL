---
title: Microsoft 365-rapporten in het Beheercentrum-activiteit formulieren
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
description: Leer hoe u een Microsoft 365-rapport van activiteiten ontvangt in het Microsoft 365-Beheercentrum.
ms.openlocfilehash: 78b09edfbfeb83c056af16787085b7c4cfe93fc6
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47949202"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporten in het Beheercentrum-activiteit formulieren

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker in licentie voor het gebruik van Microsoft Forms door hun interactie met formulieren te bekijken. U kunt er ook voor zorgen dat u het samenwerkings niveau begrijpt door te kijken naar het aantal formulieren dat de gebruiker heeft gereageerd en de formulieren waarop de gebruiker heeft gereageerd.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Naar het rapport met formulier activiteiten gaan

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **formulieren** \> **activiteit**.

## <a name="interpret-the-forms-activity-report"></a>Het rapport formulier activiteit interpreteren

U kunt inzicht krijgen in de formulier activiteiten van uw gebruikers door de grafieken **activiteit** en **gebruikers** te bekijken. 

![Rapport met formulier activiteiten](../../media/adminformsactivity.png)

|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport met **formulier activiteiten** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De weergave **gebruikers** helpt u inzicht te krijgen in de trend van het aantal actieve formulier gebruikers. Wanneer hij of zij een activiteit rond een formulier heeft uitgevoerd (maken, bewerken, weergeven, enzovoort) of een formulier in een specifieke periode heeft gereageerd, wordt een gebruiker als actief beschouwd.  <br/> |
|4.  <br/> |De weergave **activiteit** helpt u inzicht te krijgen in de trend van het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.<br/> Opmerking: een activiteit kan meerdere keren voor één formulier plaatsvinden, maar wordt slechts als één actief formulier geteld. U kunt bijvoorbeeld een formulier maken en hetzelfde formulier meerdere keren gedurende een bepaalde periode tegelijk bewerken, maar alleen als één formulier tellen. Als een gebruiker echter meerdere antwoorden voor hetzelfde formulier heeft ingediend, zou elk antwoord nog een persoonlijk antwoord zijn en worden ze meerdere keren geteld. <br/> |
|5.<br/>|In de grafiek **gebruikers** is de Y-as het aantal unieke gebruikers. X-as is de datum waarop de unieke gebruikers actief zijn. De legenda zijn:<br/><br/>**Ontwerpers** betekent dat de gebruiker een formulier heeft gemaakt of bewerkt.<br/>**Responders** betekent dat de gebruiker een antwoord (s) heeft ingediend voor een formulier.<br/> **Totaal aantal gebruikers** houdt in dat iedereen in het bedrijf een ontwerper of beantwoording heeft.<br/><br/> In de grafiek **activiteit** is de Y-as het aantal unieke formulieren of antwoorden. X-as is de datum waarop de formulier-of antwoord activiteit heeft plaatsgevonden. De legenda zijn:<br/><br/>**Formulieren gemaakt** is het aantal unieke formulieren dat de gebruiker heeft gemaakt.<br/> **Antwoord met** de status van het aantal aangemelde antwoorden de gebruikers in de organisatie hebben ontvangen.<br/> **Anonieme antwoorden** is het aantal anonieme antwoorden dat de gebruikers in de organisatie hebben ontvangen.<br/><br/>|
|zes.<br/>|U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek gebruikers de optie ontwerpers, responders of totale gebruikers als u alleen de gegevens wilt zien die betrekking hebben op deze personen. Door deze selectie te wijzigen, verandert de informatie in de rastertabel eronder niet.|
|7,5.<br/>|De tabel toont een uitsplitsing van de activiteiten op het niveau per gebruiker. De legenda zijn:<br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit heeft uitgevoerd op Microsoft Forms.<br/>**Datum van laatste activiteit (UTC)** is de datum waarop de laatste formulier activiteit is uitgevoerd door de gebruiker voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/><br/>Hiermee wordt de tabel gefilterd en worden gegevens over Bestandsactiviteiten alleen weergegeven voor gebruikers die de activiteit op die bepaalde dag hebben uitgevoerd.<br/><br/>Het **aantal gemaakte formulieren** is het aantal formulieren dat de gebruiker heeft gemaakt.<br/> Het aantal door de gebruiker **geantwoordte formulieren** is het aantal formulieren waarop de gebruiker antwoord heeft ingediend.|
|8:00.<br/>|Selecteer het pictogram **kolommen beheren** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.|
|aanhaling.<br/>|U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee worden gegevens voor alle gebruikers geëxporteerd en kunt u eenvoudige aggregatie, sorteren en filteren voor verdere analyse uitvoeren. Als u minder dan 100 gebruikers hebt, kunt u in de tabel in het rapport zelf sorteren en filteren. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te filteren en sorteren.|