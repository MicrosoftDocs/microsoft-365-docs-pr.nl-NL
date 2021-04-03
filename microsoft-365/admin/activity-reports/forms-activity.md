---
title: Microsoft 365-rapporten in het beheercentrum - Forms-activiteit
ms.author: kwekua
author: kwekua
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
description: Lees hoe u een Microsoft Forms-activiteitenrapport kunt krijgen met behulp van het microsoft 365-rapportendashboard in het Microsoft 365-beheercentrum.
ms.openlocfilehash: ce1109c6d6d626079794085b4dc742829841d06e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579672"
---
# <a name="microsoft-365-reports-in-the-admin-center---forms-activity"></a>Microsoft 365-rapporten in het beheercentrum - Forms-activiteit

In het dashboard  Microsoft 365-rapporten ziet u het activiteitenoverzicht voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld de activiteit begrijpen van elke gebruiker die een licentie heeft om Microsoft Forms te gebruiken door te kijken naar de interactie met formulieren. Het helpt u ook om het niveau van samenwerking te begrijpen door te kijken naar het aantal formulieren dat is gemaakt en formulieren waarmee de gebruiker heeft gereageerd.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-, Teams-, Teams-, of Skype voor Bedrijven-beheerder om rapporten te kunnen zien. 

## <a name="how-to-get-to-the-forms-activity-report"></a>Het rapport Forms-activiteiten

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in **de vervolgkeuze** een rapport de optie  \> **Formulieractiviteit**.

## <a name="interpret-the-forms-activity-report"></a>Het rapport Formulieractiviteit interpreteren

U kunt de formulierenactiviteit van uw gebruiker bekijken door de grafieken **Activiteit** en **Gebruikers te** bekijken. 

![Rapport Formulierenactiviteit](../../media/adminformsactivity.png)

|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |Het **rapport Formulierenactiviteit** kan worden bekeken voor trends in de afgelopen 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) weer te geven.  <br/> |
|2.  <br/> |De gegevens in elk rapport hebben meestal betrekking op de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De **weergave** Gebruikers helpt u om de trend in het aantal actieve formulieren te begrijpen. Een gebruiker wordt als actief beschouwd als hij of zij een activiteit rond een formulier heeft uitgevoerd (maken, bewerken, weergeven, enzovoort) of een formulier heeft beantwoord binnen de specifieke periode.  <br/> |
|4.  <br/> |Met **de weergave** Activiteit kunt u de trend in het aantal actieve gebruikers begrijpen. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.<br/> OPMERKING: Een activiteit kan meerdere keren voor één formulier plaatsvinden, maar wordt slechts als één actief formulier geteld. U kunt bijvoorbeeld een formulier maken en hetzelfde formulier meerdere keren bewerken gedurende een opgegeven periode, maar het wordt slechts als één formulier geteld. Als een gebruiker echter meerdere antwoorden voor hetzelfde formulier heeft verzonden, is elk antwoord nog steeds een afzonderlijk antwoord en wordt het dus meerdere keren geteld. <br/> |
|5.<br/>|In de **grafiek Gebruikers** is de Y-as het aantal unieke gebruikers. X-as is de datum waarop de unieke gebruikers actief zijn. De legenda's zijn:<br/><br/>**Ontwerpers** betekent dat de gebruiker een formulier heeft gemaakt of bewerkt.<br/>**Responders** betekent dat de gebruiker antwoord(en) heeft verzonden naar een formulier.<br/> **Totale gebruikers** betekent iedereen in het bedrijf die ontwerper of responder is geweest.<br/><br/> In de **grafiek** Activiteit is de Y-as het aantal unieke formulieren of antwoorden. X-as is de datum waarop de formulier- of antwoordactiviteit heeft plaatsgevonden. De legenda's zijn:<br/><br/>**Formulieren die** zijn gemaakt, is het aantal unieke formulieren dat de gebruikers hebben gemaakt.<br/> **Aangemelde antwoorden het** aantal aangemelde in reacties dat de gebruikers in de organisatie hebben ontvangen.<br/> **Anonieme antwoorden** is het aantal anonieme antwoorden dat de gebruikers in de organisatie hebben ontvangen.<br/><br/>|
|6.<br/>|U kunt de reeks filteren die u in de grafiek ziet door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek Gebruikers ontwerpers, responders of totale gebruikers om alleen de informatie te zien die betrekking heeft op elke grafiek. Als u deze selectie wijzigt, worden de gegevens in de rastertabel eronder niet gewijzigd.|
|7.<br/>|In de tabel ziet u een uitsplitsing van de activiteiten op het niveau per gebruiker. De legenda's zijn:<br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit heeft uitgevoerd op Microsoft Forms.<br/>**De laatste activiteitsdatum (UTC)** is de laatste datum waarop een formulieractiviteit is uitgevoerd door de gebruiker voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/><br/>Hiermee filtert u de tabel om alleen bestandsactiviteitsgegevens weer te geven voor gebruikers die de activiteit op die specifieke dag hebben uitgevoerd.<br/><br/>**Het aantal formulieren dat is** gemaakt, is het aantal formulieren dat de gebruiker heeft gemaakt.<br/> **Het aantal formulieren dat is beantwoord,** is het aantal formulieren dat de gebruiker heeft verzonden.|
|8.<br/>|Selecteer het **pictogram Kolommen beheren** om kolommen toe te voegen of te verwijderen uit het rapport.|
|9.<br/>|U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **koppeling Exporteren te** selecteren. Hiermee exporteert u gegevens voor alle gebruikers en kunt u eenvoudige aggregatie, sorteren en filteren voor verdere analyse. Als u minder dan 100 gebruikers hebt, kunt u sorteren en filteren in de tabel in het rapport zelf. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.|