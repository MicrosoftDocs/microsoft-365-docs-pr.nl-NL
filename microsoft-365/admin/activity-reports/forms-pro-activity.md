---
title: Microsoft 365-rapporten in het beheercentrum - Forms Pro-activiteit
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: Meer informatie over het maken van een Microsoft Forms Pro-activiteitenrapport met het dashboard Microsoft 365 Reports in het Microsoft 365-beheercentrum.
ms.openlocfilehash: 69938124b1aeb996afd52c119ac61e2e607f871e
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781611"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporten in het beheercentrum - Formulierenactiviteit

Het dashboard Microsoft 365 **Rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U bijvoorbeeld de activiteit begrijpen van elke gebruiker die microsoft Forms Pro mag gebruiken door te kijken naar hun interacties met Forms Pro. Het helpt u ook om het niveau van samenwerking te begrijpen dat aan de hand is door te kijken naar het aantal Pro-enquêtes dat is gemaakt en Pro-enquêtes waarop de gebruikers hebben gereageerd. 
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-service-, Teams-communicatie- of Skype voor Bedrijven-beheerder om rapporten te bekijken. 

## <a name="how-to-get-to-the-forms-pro-activity-report"></a>Naar het activiteitenrapport Formulieren Pro gaan

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **Een rapport** selecteren de optie **Forms Pro-activiteit** \> **activity**.

## <a name="interpret-the-forms-activity-report"></a>Het activiteitenrapport formulieren interpreteren

U een beeld krijgen van de Forms Pro-activiteit van uw gebruiker door te kijken naar de grafieken **Activiteit** en **Gebruikers.** 

![Activiteitenrapport Formulieren](../../media/formsproactivity.png)

|||
|:-----|:-----|
|1.  <br/> |Het activiteitenrapport **Forms Pro** kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).   <br/> |
|2.  <br/> |De gegevens in elk rapport zijn meestal net zo recent als de afgelopen 48 uur.  <br/> |
|3.  <br/> |De weergave **Gebruikers** helpt u inzicht te krijgen in de trend in het aantal actieve Forms Pro-gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij binnen de specifieke periode een activiteit rond een Pro-enquête heeft uitgevoerd (maken, bewerken, bekijken, enz.).  <br/> |
|4.  <br/> |De **activiteitsweergave** helpt u inzicht te krijgen in de trend in het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.<br/> OPMERKING: Een activiteit kan meerdere keren plaatsvinden voor één enquête, maar telt slechts als één actieve enquête. U bijvoorbeeld een Pro-enquête maken en dezelfde enquête meerdere keren gedurende een bepaalde periode blijven bewerken, deze telt slechts als één enquête. <br>|
|5.<br/>|In de grafiek **Gebruikers** is de Y-as het aantal unieke gebruikers. X-as is de datum waarop de unieke gebruikers actief zijn. De legendes zijn:<br/><br/>**Ontwerpers** betekent dat de gebruiker een Forms Pro Survey heeft gemaakt of bewerkt.<br><br>In de **grafiek Activiteit** is de Y-as het aantal Antwoorden van Formulieren Pro per enquête. X-as is de datum waarop de activiteit Enquête of Respons heeft plaatsgevonden. De legendes zijn:<br/><br/>**Enquêtes die** zijn gemaakt, zijn het aantal unieke Forms Pro-enquêtes dat de gebruikers hebben gemaakt<br>**Reacties** is het aantal anonieme of niet-anonieme reacties dat de gebruikers die de enquête hebben ontvangen, hebben ingediend. |
|6.<br/>|U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek Gebruikers ontwerpers, responders of totaalgebruikers om alleen de informatie te zien die betrekking heeft op elke kaart. Als u deze selectie wijzigt, wordt de informatie in de rastertabel eronder niet gewijzigd.|
|7.<br/>|De tabel toont u een uitsplitsing van de activiteiten op het niveau per gebruiker. De legendes zijn:<br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit op Microsoft Forms heeft uitgevoerd.<br/>**Laatste activiteitsdatum (UTC)** is de laatste datum waarop een formulieractiviteit door de gebruiker is uitgevoerd voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/>Hiermee filtert u de tabel om bestandsactiviteitsgegevens alleen weer te geven voor gebruikers die de activiteit op die specifieke dag hebben uitgevoerd.<br/><br/>**Het aantal aangemaakte enquêtes** is het aantal enquêtes dat de gebruiker heeft gemaakt.<br/> Aantal antwoorden op de **enquête** is het aantal reacties van responders aan wie de enquête is verspreid.|
|8.<br/>|Selecteer het pictogram **Kolommen beheren** om kolommen toe te voegen of te verwijderen uit het rapport.|
|9.<br/>|U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee worden gegevens voor alle gebruikers geëxporteerd en u eenvoudig aggregatie, sortering en filtering uitvoeren voor verdere analyse. Als u minder dan 100 gebruikers hebt, u sorteren en filteren in de tabel in het rapport zelf. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te filteren en te sorteren.|