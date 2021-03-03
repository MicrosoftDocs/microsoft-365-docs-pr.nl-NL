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
ms.openlocfilehash: 41403bcda1d1485798ac5eefe8f3386a314aea1b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406175"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het beheercentrum - Gebruikersactiviteit in Microsoft Teams

Het Dashboard Microsoft **365-rapporten** toont een overzicht van de activiteiten voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of lezer van rapporten zijn in Microsoft 365 of een beheerder van Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven om rapporten te kunnen zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Klik op de startpagina van het dashboard op **de knop** Meer weergeven op de microsoft Teams-activiteitskaart.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U kunt de gebruikersactiviteit in het Teams-rapport bekijken door het tabblad **Gebruikersactiviteit te** kiezen. <br/>![Microsoft 365-rapporten - Gebruikersactiviteit in Microsoft Teams.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecteer **Kolommen kiezen om** kolommen toe te voegen aan of te verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. De geëxporteerde indeling **voor audiotijd,** **videotijd** en scherm delen **volgt** de ISO8601-duurindeling.

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
|Vergaderingen die ad-hoc hebben deelgenomen   <br/> | Het aantal ad-hocvergaderingen waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Vergaderingen die ad-hoc worden georganiseerd <br/> |Het aantal ad-hocvergaderingen dat een gebruiker heeft georganiseerd tijdens de opgegeven periode. <br/>|
|Totaal aantal georganiseerde vergaderingen  <br/> |De som van eenmalige, terugkerende, ad-hoc en niet-geclassificeerde vergaderingen die een gebruiker tijdens de opgegeven periode heeft georganiseerd.  <br/> |
|Totaal aantal vergaderingen dat heeft deelgenomen aan  <br/> |De som van de eenmalige, terugkerende, ad-hoc en niet-geclassificeerde vergaderingen waarin een gebruiker tijdens de opgegeven periode heeft deelgenomen.  <br/> |
|Geplande vergaderingen in één keer  <br/> |Het aantal een time scheduled meetings a user organized during the specified time period.  <br/> |
|Geplande terugkerende vergaderingen  <br/> |Het aantal terugkerende vergaderingen dat een gebruiker heeft georganiseerd tijdens de opgegeven periode.  <br/> |
|Vergaderingen die een keer zijn gepland  <br/> |Het aantal een time scheduled meetings waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Vergaderingen die zijn deelgenomen aan geplande terugkerende vergaderingen  <br/> |Het aantal terugkerende vergaderingen waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Is in licentie gegeven  <br/> |Geselecteerd als de gebruiker een licentie heeft voor het gebruik van Teams. <br/>|
|Andere activiteit  <br/>|De gebruiker is actief, maar heeft andere activiteiten uitgevoerd dan zichtbare actietypen die in het rapport worden aangeboden (kanaalberichten en chatberichten verzenden of beantwoorden, plannen of deelnemen aan privégesprekken en vergaderingen). Voorbeeldenacties zijn wanneer een gebruiker de Teams-status of het Teams-statusbericht wijzigt of een kanaalberichtbericht opent, maar niet beantwoordt.  <br/>|
|niet-geclassificeerde vergaderingen <br/>|De planning die niet kan worden geclassificeerd als planning of als terugkerend of ad-hoc. Deze zijn kort van groot en kunnen meestal niet worden geïdentificeerd vanwege geknoeid telemetriegegevens. |
|||