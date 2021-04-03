---
title: Microsoft 365-rapporten in het beheercentrum - Microsoft Teams-gebruikersactiviteit
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
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Lees hoe u het gebruikersactiviteitsrapport van Microsoft Teams krijgt en inzicht krijgt in de Teams-activiteit in uw organisatie.
ms.openlocfilehash: 1f45cd380813a843ad54e6552578941a9741138e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579600"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het beheercentrum - Microsoft Teams-gebruikersactiviteit

In het dashboard  Microsoft 365-rapporten ziet u het activiteitenoverzicht voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-, Teams-, Teams-, of Skype voor Bedrijven-beheerder om rapporten te kunnen zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in **de vervolgkeuze** een rapport de optie **Gebruikersactiviteit van Microsoft** \> Teams.
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U krijgt inzicht in de gebruikersactiviteit in Microsoft Teams door te kijken naar de grafieken **Activiteit** en **Gebruikers**.<br/>![Microsoft 365-rapporten - Microsoft Teams-gebruikersactiviteit.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruikersactiviteit in Microsoft Teams** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) weer te geven.  <br/> |
|2.  <br/> |De gegevens in elk rapport hebben meestal betrekking op de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |Om de gegevenskwaliteit te waarborgen, voeren we de afgelopen vijf dagen dagelijkse controles uit voor gegevensvalidatie en worden eventuele gedetecteerde hiaten opgevuld. Mogelijk ziet u tijdens het proces verschillen in historische gegevens.  <br/> |
|4.  <br/> |In de weergave **Activiteit** ziet u het aantal Microsoft Teams-activiteiten per activiteitstype. De activiteitstypen zijn het aantal teamchatberichten, privéchatberichten, gesprekken en vergaderingen.  <br/> |
|5.  <br/> |In de weergave **Gebruikers** ziet u het aantal gebruikers per activiteitstype. De activiteitstypen zijn het aantal teamchatberichten, privéchatberichten, gesprekken en vergaderingen.  <br/> |
|6.  <br/> | In de **grafiek** Activiteit is de Y-as het aantal opgegeven activiteiten.  <br/>  In de **grafiek** Bestanden is de Y-as het aantal gebruikers dat deelneemt aan teamschats, privéchats, oproepen of vergaderingen.  <br/>  De X-as in de grafieken is het geselecteerde datumbereik voor het specifieke rapport.  <br/> |
|7.  <br/> |U kunt de reeks filteren die u in de grafiek ziet door een item in de legenda te selecteren. Selecteer in de grafiek **Activiteit** bijvoorbeeld **Kanaalberichten,** **Chatberichten,** Oproepen of Vergaderingen om alleen de informatie te zien die betrekking heeft op elk bericht.   Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> ![De activiteitendiagrammen van Microsoft Teams filteren](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8.  <br/> | Welke lijst met groepen wordt weergegeven, wordt bepaald door de groepen die bestaan (niet zijn verwijderd) in de ruimste rapportageperiode (180 dagen). Het aantal activiteiten is afhankelijk van de datumselectie.  <br/> OPMERKING: Mogelijk ziet u niet alle items in de onderstaande lijst in de kolommen totdat u ze toevoegt.<br/>**Gebruikersnaam** is het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft Teams-activiteit.  <br/> **Kanaalberichten** is het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een teamchat heeft geplaatst.  <br/> **Chatberichten** is het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een privéchat heeft geplaatst.  <br/> **Gesprekken** is het aantal gesprekken waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> **Vergaderingen** is het aantal onlinevergaderingen waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> **Andere activiteiten** is het aantal andere teamactiviteiten van de gebruiker.  <br/> **Verwijderd** geeft aan of het team is verwijderd. Als het team is verwijderd maar activiteiten had in de rapportageperiode, wordt het weergegeven in het raster met Verwijderd ingesteld op Waar.  <br/> **Verwijderd op** is de datum waarop het team is verwijderd.  <br/> **Toegewezen producten** is de lijst met producten die zijn toegewezen aan de gebruiker.  <br/>  Als u door het beleid van uw organisatie geen rapporten kunt bekijken waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacyinstelling voor al deze rapporten wijzigen. Bekijk de sectie **Details op gebruikersniveau** verbergen in de [activiteitenrapporten in het Microsoft 365-beheercentrum.](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

