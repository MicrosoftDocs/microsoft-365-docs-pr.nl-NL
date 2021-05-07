---
title: Microsoft 365 Rapporten in het beheercentrum - SharePoint sitegebruik
f1.keywords:
- NOCSH
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
description: Vraag het rapport SharePoint sitegebruik om te weten hoeveel bestanden gebruikers opslaan in SharePoint sites, hoeveel er actief worden gebruikt en de totale hoeveelheid opslagruimte die wordt verbruikt.
ms.openlocfilehash: 62bf01c867b7e9217d25e655af6633a72773caa1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241866"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365 Rapporten in het beheercentrum - SharePoint sitegebruik

Als een Microsoft 365 beheerder, toont het dashboard **Rapporten** u het activiteitenoverzicht voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. U kunt bijvoorbeeld een overzicht op hoog niveau krijgen van de toegevoegde waarde van SharePoint voor wat betreft het totale aantal bestanden die gebruikers in SharePoint-sites opslaan, het aantal bestanden die actief worden gebruikt en de opslagruimte die wordt gebruikt door al deze sites. Vervolgens kunt u inzoomen op het gebruiksrapport voor SharePoint-sites om inzicht te krijgen in de trends en de details op siteniveau voor alle sites. 
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven-beheerder om rapporten te kunnen zien.
Microsoft 365 Rapporten in het beheercentrum worden niet ondersteund voor GCC High- en DoD-tenants.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
2. Klik op de startpagina van het dashboard op de knop **Meer** weergeven op de SharePoint kaart.
  
## <a name="interpret-the-sharepoint-site-usage-report"></a>Het rapport SharePoint sitegebruik interpreteren

U kunt het sitegebruik weergeven in het SharePoint rapport door het **tabblad Sitegebruik te** kiezen.<br/>![Microsoft 365 rapporten - Rapport SharePoint microsoft-sitegebruik.](../../media/d1cb6200-e81c-460b-9d05-53f4bd7cf5ee.png)

Selecteer **Kolommen kiezen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![SharePoint rapport sitegebruik : kies kolommen](../../media/71ac3195-c494-40c1-9346-a858125ef6df.png)

U kunt de rapportgegevens ook exporteren naar een Excel .csv bestand door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. 
  
|Item|Beschrijving|
|:-----|:-----|
|**Metrische**|**Definitie**|
|Site-URL  <br/> |De volledige URL van de site. <br/> |
|Verwijderd  <br/> |De verwijderingsstatus van de site. Het duurt minimaal zeven dagen voordat sites kunnen worden gemarkeerd als verwijderd.  <br/> |
|Site-eigenaar  <br/> |De gebruikersnaam van de primaire eigenaar van de site.   <br/> |
|De hoofdnaam van de site-eigenaar  <br/> |Het e-mailadres van de eigenaar van de site. <br/> |
|Laatste activiteitsdatum (UTC)  <br/> | De datum van de laatste bestandsactiviteit is gedetecteerd of er is een pagina op de site bekeken.  <br/> |
|Label-id sitegevoeligheid  <br/> | Het gevoeligheidslabel op de site.  <br/> |
|Extern delen  <br/> | De externe sharable-instellingen op de site.  <br/> |
|Beleid voor niet-gemanageerd apparaat  <br/> | Het beleid voor sitetoegang voor niet-bemande apparaten.  <br/> |
|Geolocatie  <br/> | De geografische locatie van de site.  <br/> |
|Bestanden  <br/> |Het aantal bestanden op de site. <br/>|
|Actieve bestanden  <br/> | Het aantal actieve bestanden op de site.<br/> OPMERKING: Als bestanden zijn verwijderd tijdens de opgegeven periode voor het rapport, kan het aantal actieve bestanden in het rapport groter zijn dan het huidige aantal bestanden op de site.  <br/> |
|Storage gebruikt (MB)  <br/> |De hoeveelheid opslagruimte die momenteel op de site wordt gebruikt.  <br/>|
|Storage toegewezen (MB)  <br/> |De maximale hoeveelheid opslagruimte die voor de site is toegewezen.  <br/>|
|Paginaweergaven  <br/> |Het aantal keren dat pagina's op de site zijn bekeken.  <br/>|
|Bezochte pagina's  <br/> |Het aantal unieke pagina's dat op de site is bezocht.  <br/>|
|Anonieme koppelingstelling  <br/> |Het aantal keren dat documenten of mappen worden gedeeld met 'Iedereen met de koppeling' op de site.  <br/>|
|Aantal bedrijfskoppelingen  <br/> |Het aantal keren dat documenten of mappen worden gedeeld met behulp van 'Personen in organisatie met de koppeling' op de site.  <br/>|
|Beveiligde koppeling voor aantal gasten  <br/> |Het aantal keren dat documenten of mappen worden gedeeld met behulp van 'specifieke personen' op de site.  <br/>|
|Beveiligde koppeling voor aantal leden  <br/> |Het aantal keren dat documenten of mappen worden gedeeld met behulp van 'specifieke personen' op de site.  <br/>|
|Hoofdwebsjabloon  <br/> |De sjabloon die wordt gebruikt voor het maken van de site.  <br/> OPMERKING: Als u de gegevens wilt filteren op verschillende sitetypen, exporteert u de gegevens en gebruikt u de kolom Hoofdwebsjabloon. |
|||