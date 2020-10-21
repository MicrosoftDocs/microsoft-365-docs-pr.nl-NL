---
title: Microsoft 365-rapporten in het Beheercentrum-gebruikersactiviteit in Microsoft teams
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
description: Meer informatie over het verkrijgen van het Rapportgebruikers activiteit in Microsoft teams en het verkrijgen van inzichten aan de activiteiten van teams in uw organisatie.
ms.openlocfilehash: 8ce29b43e6238883470d1159ad1d22fefca88792
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637065"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het Beheercentrum-gebruikersactiviteit in Microsoft teams

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Klik op de startpagina van het dashboard op de knop **meer weergeven** op de activiteiten kaart van Microsoft teams.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U kunt de activiteit van gebruikers weergeven in het rapport teams door het tabblad **User Activity** te kiezen. <br/>![Microsoft 365-rapporten-gebruikersactiviteit in Microsoft teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecteer **kolommen kiezen** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. De geëxporteerde indeling voor **Audio**-en **video** tijd en **scherm delen** volgt de iso8601-tijdsindeling.

|Item|Beschrijving|
|:-----|:-----|
|**Gegevens**|**Definitie**|
|Gebruikersnaam  <br/> |Het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.   <br/> |
|Kanaalberichten   <br/> |Het aantal unieke berichten dat de gebruiker heeft geplaatst tijdens de opgegeven periode in een team gesprek.  <br/> |
|Chat berichten   <br/> |Het aantal unieke berichten dat de gebruiker heeft geplaatst tijdens de opgegeven periode in een privégesprek.  <br/> |
|Totaal aantal vergaderingen   <br/> |Het aantal onlinevergaderingen waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> |
|1:1-gesprekken   <br/> | Het aantal 1:1-gesprekken waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> |
|Datum van laatste activiteit (UTC)  <br/> |De laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft teams-activiteit.<br/> |
|Deelnemers aan de vergadering   <br/> | Het aantal vergaderingen dat niet is gepland in de agenda waaraan de gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> |
|Vergaderingen geordend in de adhoc <br/> |Het aantal vergaderingen dat niet is gepland in de agenda die de gebruiker heeft georganiseerd in de opgegeven periode. <br/>|
|Geplande vergaderingen  <br/> |Het aantal geplande vergaderingen dat een gebruiker heeft georganiseerd in de opgegeven periode.  <br/> |
|Is een licentie |Geselecteerd als de gebruiker een licentie heeft om teams te gebruiken.|
|Overige activiteiten|de gebruiker wordt als actief beschouwd maar heeft een nulwaarde voor de chat berichten, 1:1-gesprekken, Kanaalberichten, totale vergaderingen en vergaderingen georganiseerde metrische waarden. Voorbeelden van acties zijn een bericht wanneer een gebruiker een bericht bericht post opent, maar geen antwoord ontvangt of wanneer een privébericht wordt ontvangen en wordt gelezen, maar er wordt niet gereageerd. |
|||