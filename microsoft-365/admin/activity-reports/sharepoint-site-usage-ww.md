---
title: Microsoft 365-rapporten in het Beheercentrum-gebruik van SharePoint-sites
f1.keywords:
- NOCSH
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
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
description: U kunt het rapport gebruik van SharePoint-sites gebruiken om te zien hoeveel bestanden gebruikers opslaan op SharePoint-sites, hoe vaak actief worden gebruikt en de totale gebruikte opslagruimte.
ms.openlocfilehash: bc9345a5e281f1e7343bf62a2dc6832587d0786e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649773"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporten in het Beheercentrum-gebruik van SharePoint-sites

Als Microsoft 365-beheerder toont het dashboard **rapporten** het overzicht van activiteiten voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. U kunt bijvoorbeeld een overzicht op hoog niveau krijgen van de toegevoegde waarde van SharePoint voor wat betreft het totale aantal bestanden die gebruikers in SharePoint-sites opslaan, het aantal bestanden die actief worden gebruikt en de opslagruimte die wordt gebruikt door al deze sites. Vervolgens kunt u inzoomen op het gebruiksrapport voor SharePoint-sites om inzicht te krijgen in de trends en de details op siteniveau voor alle sites. 
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.
Microsoft 365-rapporten in het Beheercentrum wordt niet ondersteund voor GCC High-en DoD-tenants.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
2. Klik op de startpagina van het dashboard op de knop **meer weergeven** op de SharePoint-kaart.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites interpreteren

U kunt het site gebruik in het SharePoint-rapport weergeven door het tabblad **site gebruik** te kiezen.<br/>![Microsoft 365-rapporten-rapport Microsoft SharePoint-site gebruik.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selecteer **kolommen kiezen** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> ![Gebruiksrapport voor SharePoint-sites-Kies kolommen](../../media/639f3cfd-6725-4318-a225-6d5c2f01770c.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. 
  
|Item|Beschrijving|
|:-----|:-----|
|**Gegevens**|**Definitie**|
|Site-URL  <br/> |De volledige URL van de site. <br/> |
|Deleted  <br/> |De status van de verwijdering van de site. Het duurt minimaal zeven dagen voordat sites kunnen worden gemarkeerd als verwijderd.  <br/> |
|Site-eigenaar  <br/> |De gebruikersnaam van de primaire eigenaar van de site.   <br/> |
|Principal-naam van site-eigenaar  <br/> |Het e-mailadres van de eigenaar van de site. <br/> |
|Datum van laatste activiteit (UTC)  <br/> | De datum waarop de laatste Bestandsactiviteit is gedetecteerd of waarop een pagina is bekeken op de site.  <br/> |
|Bestanden  <br/> |Het aantal bestanden op de site. <br/>|
|Actieve bestanden  <br/> | Het aantal actieve bestanden op de site.<br/> Opmerking: als er tijdens de opgegeven periode voor het rapportbestanden zijn verwijderd, is het aantal actieve bestanden dat in het rapport wordt getoond groter dan het huidige aantal bestanden op de site.  <br/> |
|Gebruikte opslagruimte (MB)  <br/> |De hoeveelheid opslagruimte die op dat moment op de site wordt gebruikt.  <br/>|
|Opslag toegewezen (MB)  <br/> |De maximale hoeveelheid opslagruimte die voor de site is toegewezen.  <br/>|
|Paginaweergaven  <br/> |Het aantal keren dat pagina's op de site zijn bekeken.  <br/>|
|Bezochte pagina's  <br/> |Het aantal unieke pagina's dat op de site is bezocht.  <br/>|
|Hoofdwebsite sjabloon  <br/> |De sjabloon die wordt gebruikt voor het maken van de site.  <br/> Opmerking: als u de gegevens wilt filteren op verschillende site typen, exporteert u de gegevens en gebruikt u de kolom hoofd websjabloon. |
|||