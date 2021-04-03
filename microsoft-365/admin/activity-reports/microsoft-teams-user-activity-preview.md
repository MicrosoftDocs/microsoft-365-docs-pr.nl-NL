---
title: Microsoft 365-rapporten in het beheercentrum - Microsoft Teams-gebruikersactiviteit
ms.author: kwekua
author: kwekua
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
description: Lees hoe u het gebruikersactiviteitsrapport van Microsoft Teams krijgt en inzicht krijgt in de Teams-activiteit in uw organisatie.
ms.openlocfilehash: a4f8cd995d1559da3846fbb38cc5a9441358da72
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579612"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-teams-user-activity"></a>Microsoft 365-rapporten in het beheercentrum - Microsoft Teams-gebruikersactiviteit

In het dashboard  Microsoft 365-rapporten ziet u het activiteitenoverzicht voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). Met het rapport Gebruikersactiviteit in Microsoft Teams kunt u meer inzicht krijgen in de Microsoft Teams-activiteiten in uw organisatie.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-, Teams-, Teams-, of Skype voor Bedrijven-beheerder om rapporten te kunnen zien.  
 
## <a name="how-to-get-to-the-microsoft-teams-user-activity-report"></a>Zo gaat u naar het rapport Gebruikersactiviteit in Microsoft Teams

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Klik op de startpagina van het dashboard op **de knop Meer** weergeven op de Microsoft Teams-activiteitenkaart.

## <a name="interpret-the-microsoft-teams-user-activity-report"></a>Het rapport Gebruikersactiviteit in Microsoft Teams interpreteren

U kunt de gebruikersactiviteit weergeven in het Teams-rapport door het tabblad **Gebruikersactiviteit te** kiezen. <br/>![Microsoft 365-rapporten - Microsoft Teams-gebruikersactiviteit.](../../media/1011877f-3cf0-4417-9447-91d0b2312aab.png)

Selecteer **Kolommen kiezen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![Teams user activity report - choose columns](../../media/6d3c013e-2c5e-4d66-bb41-998aa4bd1c20.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. De geëxporteerde indeling voor **audiotijd,** **videotijd** en **scherm** delen volgt iso8601 duurnotatie.

In het rapport **Gebruikersactiviteit in Microsoft Teams** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) weer te geven.

Om de gegevenskwaliteit te waarborgen, voeren we de afgelopen drie dagen dagelijkse controles uit voor gegevensvalidatie en worden eventuele gedetecteerde hiaten opgevuld. Mogelijk ziet u tijdens het proces verschillen in historische gegevens.

|Item|Beschrijving|
|:-----|:-----|
|**Metrische**|**Definitie**|
|Gebruikersnaam  <br/> |Het e-mailadres van de gebruiker. U kunt het feitelijke e-mailadres weergeven of dit veld anoniem maken.   <br/> |
|Kanaalberichten   <br/> |Het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een teamchat heeft gepost.  <br/> |
|Chatberichten   <br/> |Het aantal unieke berichten dat de gebruiker tijdens de opgegeven periode in een privéchat heeft gepost.  <br/> |
|Totaal aantal vergaderingen   <br/> |Het aantal onlinevergaderingen waar de gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|1:1-oproepen   <br/> | Het aantal 1:1 oproepen waar de gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Laatste activiteitsdatum (UTC)  <br/> |De laatste datum waarop de gebruiker heeft deelgenomen aan een Microsoft Teams-activiteit.<br/> |
|Vergaderingen hebben ad hoc deelgenomen   <br/> | Het aantal ad-hocvergaderingen waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Vergaderingen ad hoc georganiseerd <br/> |Het aantal ad-hocvergaderingen dat een gebruiker tijdens de opgegeven periode heeft georganiseerd. <br/>|
|Totaal georganiseerde vergaderingen  <br/> |De som van eenmalige geplande, terugkerende, ad-hoc en niet-geclassificeerde vergaderingen die een gebruiker tijdens de opgegeven periode heeft georganiseerd.  <br/> |
|Totaal aantal deelnemende vergaderingen  <br/> |De som van de eenmalige geplande, terugkerende, ad-hoc en niet-geclassificeerde vergaderingen aan een gebruiker tijdens de opgegeven periode.  <br/> |
|Vergaderingen die één keer zijn gepland  <br/> |Het aantal eentijds geplande vergaderingen dat een gebruiker tijdens de opgegeven periode heeft georganiseerd.  <br/> |
|Geplande terugkerende vergaderingen  <br/> |Het aantal terugkerende vergaderingen dat een gebruiker tijdens de opgegeven periode heeft georganiseerd.  <br/> |
|Vergaderingen hebben een een keer deelgenomen  <br/> |Het aantal eentijds geplande vergaderingen waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Vergaderingen hebben deelgenomen aan geplande terugkerende vergaderingen  <br/> |Het aantal terugkerende vergaderingen waar een gebruiker aan heeft deelgenomen tijdens de opgegeven periode.  <br/> |
|Is gelicentieerd  <br/> |Geselecteerd als de gebruiker een licentie heeft voor het gebruik van Teams. <br/>|
|Andere activiteit  <br/>|De gebruiker is actief, maar heeft andere activiteiten uitgevoerd dan blootgestelde actietypen die in het rapport worden aangeboden (het verzenden of beantwoorden van kanaalberichten en chatberichten, het plannen of deelnemen aan 1:1-oproepen en vergaderingen). Voorbeelden van acties zijn wanneer een gebruiker de Teams-status of het statusbericht teams wijzigt of een bericht met een kanaalbericht opent, maar niet beantwoordt.  <br/>|
|niet-geclassificeerde vergaderingen <br/>|Degene die niet kan worden geclassificeerd als planning of terugkerende of ad-hoc. Deze zijn kort van getal en kunnen meestal niet worden geïdentificeerd vanwege gemanipuleerde telemetriegegevens. |
|||