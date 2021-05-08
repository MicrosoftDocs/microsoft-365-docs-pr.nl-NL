---
title: Microsoft 365 Rapporten in het beheercentrum - SharePoint activiteit
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
description: Het rapport SharePoint activiteitsgebruik laten weten over de activiteiten van elke gebruiker SharePoint, het aantal gedeelde bestanden en het opslaggebruik.
ms.openlocfilehash: f049a67e8444654e05cfe3dc72a8d4fe39792cb2
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244078"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365 Rapporten in het beheercentrum - SharePoint activiteit

Als een Microsoft 365 beheerder, toont het dashboard **Rapporten** u het activiteitenoverzicht voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. Bekijk de [activiteitenrapporten in het Microsoft 365 beheercentrum.](activity-reports.md)
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van SharePoint heeft door zijn of haar interactie met bestanden te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven-beheerder om rapporten te kunnen zien. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hoe kom ik aan het rapport met SharePoint-activiteiten?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
2. Klik op de startpagina van het dashboard op de knop **Meer** weergeven op de SharePoint kaart.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Het rapport SharePoint activiteiten interpreteren

U kunt de activiteiten in het SharePoint bekijken door het tabblad **Activiteit te** kiezen.<br/>![Microsoft 365 rapporten - Microsoft SharePoint activiteitsrapport.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Selecteer **Kolommen kiezen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![SharePoint activiteitsrapport : kies kolommen](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

U kunt de rapportgegevens ook exporteren naar een Excel .csv bestand door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. 
  
|Item|Beschrijving|
|:-----|:-----|
|**Metrische**|**Definitie**|
|Gebruikersnaam  <br/> |Het e-mailadres van de gebruiker die de activiteit heeft uitgevoerd op de SharePoint Site.  <br/> |
|Laatste activiteitsdatum (UTC)  <br/> |De laatste datum waarop een bestandsactiviteit is uitgevoerd of een pagina is bezocht voor het geselecteerde datumbereik. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> |
|Bekeken of bewerkte bestanden  <br/> |Het aantal bestanden dat de gebruiker heeft geüpload, gedownload, gewijzigd of bekeken.   <br/> |
|Bestanden gesynchroniseerd  <br/> |Het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker met de SharePoint site. <br/> |
|Bestanden die intern worden gedeeld  <br/> | Het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> |
|Bestanden die extern worden gedeeld  <br/> |Het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie. <br/>|
|Bezochte pagina's  <br/> |De bezoeken aan unieke pagina's door de gebruiker. <br/>|
|Verwijderd  <br/> | Dit geeft aan dat de licentie van de gebruiker is verwijderd.  <br/>  **OPMERKING:** Activiteit voor een verwijderde gebruiker wordt nog steeds weergegeven in het rapport zolang hij of zij een licentie heeft gekregen gedurende de geselecteerde periode. In de kolom Verwijderd kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.  <br/> |
|Verwijderde datum  <br/> |De datum waarop de licentie van de gebruiker is verwijderd. <br/>|
|Product toegewezen  <br/> |De Microsoft 365 producten die zijn gelicentieerd aan de gebruiker.|
|||