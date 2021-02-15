---
title: Microsoft 365-rapporten in het beheercentrum - Gebruikersactiviteit in Microsoft Teams
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
description: Lees hoe u het rapport Gebruikersactiviteit in Microsoft Teams krijgt en inzicht krijgt in de Teams-activiteit in uw organisatie.
ms.openlocfilehash: e8e4ab6fd78fb290243d8fdc780b5a7a14ca2ee0
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233408"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het beheercentrum - Gebruikersactiviteit in Microsoft Teams

Het Dashboard Microsoft **365-rapporten** toont een overzicht van de activiteiten voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportenlezer in Microsoft 365 of een beheerder van Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven zijn om rapporten te kunnen zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Klik op de startpagina van het dashboard op **de knop** Meer weergeven op de microsoft Teams-activiteitskaart.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U kunt de gebruikersactiviteit in het Teams-rapport bekijken door het tabblad **Gebruikersactiviteit te** kiezen. <br/>![Microsoft 365-rapporten - Gebruikersactiviteit in Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecteer **Kolommen kiezen om** kolommen toe te voegen aan of te verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/a1513028-cf09-4186-93a6-8a203cd22475.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **exportkoppeling te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. De geëxporteerde indeling **voor audiotijd,** **videotijd** en scherm delen **volgt** de ISO8601-duurindeling.

In het rapport **Gebruikersactiviteit in Microsoft Teams** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens voor een datum tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) tonen.

Om ervoor te zorgen dat de gegevenskwaliteit wordt gecontroleerd, voeren we de afgelopen drie dagen dagelijkse controles uit op gegevensvalidatie en voeren we alle hiaten uit die worden gedetecteerd. U ziet mogelijk verschillen in historische gegevens tijdens het proces.

|Item|Beschrijving|
|:-----|:-----|
|**Metrisch**|**Definitie**|
|Gebruikersnaam  <br/> |Het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.   <br/> |
|Kanaalberichten   <br/> |Het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een teamchat heeft geplaatst.  <br/> |
|Chatberichten   <br/> |Het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een privéchat heeft geplaatst.  <br/> |
|Totaal aantal vergaderingen   <br/> |Het aantal onlinevergaderingen waar de gebruiker in de opgegeven periode aan heeft deelgenomen.  <br/> |
|1:1-oproepen   <br/> | Het aantal 1:1-oproepen waar de gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Datum van laatste activiteit (UTC)  <br/> |De laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft Teams-activiteit.<br/> |
|Vergaderingen hebben deelgenomen aan adhoc   <br/> | Het aantal vergaderingen dat niet is gepland in de agenda waar de gebruiker in de opgegeven periode aan heeft deelgenomen.  <br/> |
|Vergaderingen georganiseerd adhoc <br/> |Het aantal vergaderingen dat niet is gepland in de agenda die de gebruiker heeft georganiseerd in de opgegeven periode. <br/>|
|Geplande vergaderingen  <br/> |Het aantal geplande vergaderingen dat een gebruiker heeft georganiseerd tijdens de opgegeven periode.  <br/> |
|Is in licentie gegeven |Geselecteerd als de gebruiker een licentie heeft voor het gebruik van Teams.|
|Andere activiteit|De gebruiker is actief, maar heeft andere activiteiten uitgevoerd dan zichtbare actietypen die in het rapport worden aangeboden (kanaalberichten en chatberichten verzenden of beantwoorden, plannen of deelnemen aan privégesprekken en vergaderingen). Voorbeeldenacties zijn wanneer een gebruiker de Teams-status of het Teams-statusbericht wijzigt of een kanaalberichtbericht opent, maar niet beantwoordt. |
|||