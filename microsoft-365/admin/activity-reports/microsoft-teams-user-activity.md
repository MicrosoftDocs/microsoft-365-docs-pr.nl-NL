---
title: Microsoft 365-rapporten in het Beheercentrum-gebruikersactiviteit in Microsoft teams
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 07f67fc4-c0a4-4d3f-ad20-f40c7f6db524
description: Meer informatie over het verkrijgen van het Rapportgebruikers activiteit in Microsoft teams en het verkrijgen van inzichten aan de activiteiten van teams in uw organisatie.
ms.openlocfilehash: b2b01371872d0a4b2ebbfb6b011cf8bd4299a90b
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611374"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het Beheercentrum-gebruikersactiviteit in Microsoft teams

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie gebruikersactiviteit in **Microsoft teams** \> .
  
## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U krijgt inzicht in de gebruikersactiviteit in Microsoft Teams door te kijken naar de grafieken **Activiteit** en **Gebruikers**.<br/>![Microsoft 365-rapporten-gebruikersactiviteit in Microsoft teams.](../../media/40359f81-25f7-416d-bb1e-37289133ef6b.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruikersactiviteit in Microsoft Teams** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |Om ervoor te zorgen dat de gegevenskwaliteit gegarandeerd is, kunnen we de afgelopen vijf dagen eerst controleren of er geen leemtes zijn gevonden. U merkt mogelijk dat er verschillen zijn in historische gegevens tijdens dit proces.  <br/> |
|4.  <br/> |In de weergave **Activiteit** ziet u het aantal Microsoft Teams-activiteiten per activiteitstype. De activiteitstypen zijn het aantal teamchatberichten, privéchatberichten, gesprekken en vergaderingen.  <br/> |
|5.  <br/> |In de weergave **Gebruikers** ziet u het aantal gebruikers per activiteitstype. De activiteitstypen zijn het aantal teamchatberichten, privéchatberichten, gesprekken en vergaderingen.  <br/> |
|zes.  <br/> | In de grafiek **activiteit** is de Y-as het aantal opgegeven activiteiten.  <br/>  In de grafiek **bestanden** is de Y-as het aantal gebruikers dat deelneemt aan teams-chats, persoonlijke chats, oproepen of vergaderingen.  <br/>  De X-as in de grafieken is het geselecteerde datumbereik voor het specifieke rapport.  <br/> |
|7,5.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek **activiteit** de optie **kanaalberichten**, **Chat berichten**, **oproepen** of **vergaderingen** om alleen de informatie te zien die voor elk item wordt weergegeven. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> ![De activiteiten grafieken van Microsoft teams filteren](../../media/c819c4ea-6e9a-4411-a0dd-9f800d64ce38.png)|
|8:00.  <br/> | Welke lijst met groepen wordt weergegeven, wordt bepaald door de groepen die bestaan (niet zijn verwijderd) in de ruimste rapportageperiode (180 dagen). Het aantal activiteiten is afhankelijk van de datumselectie.  <br/> Opmerking: u kunt alle items in de onderstaande lijst in de kolommen niet zien totdat u ze toevoegt.<br/>**Gebruikersnaam** is het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft Teams-activiteit.  <br/> **Kanaalberichten** is het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een teamchat heeft geplaatst.  <br/> **Chatberichten** is het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een privéchat heeft geplaatst.  <br/> **Gesprekken** is het aantal gesprekken waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> **Vergaderingen** is het aantal onlinevergaderingen waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> **Andere activiteiten** is het aantal andere teamactiviteiten van de gebruiker.  <br/> **Verwijderd** geeft aan of het team is verwijderd. Als het team is verwijderd maar activiteiten had in de rapportageperiode, wordt het weergegeven in het raster met Verwijderd ingesteld op Waar.  <br/> **Verwijderd op** is de datum waarop het team is verwijderd.  <br/> **Toegewezen producten** is de lijst met producten die zijn toegewezen aan de gebruiker.  <br/>  Als de beleidsregels van uw organisatie rapporten verhinderen waarin gebruikersgegevens kunnen worden weergegeven, kunt u de privacy-instelling voor al deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|aanhaling.  <br/> |Selecteer **kolommen** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/eb5fbcee-e371-4d36-a0c6-fa54732311ec.png)|
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

