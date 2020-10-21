---
title: Microsoft 365-rapporten in het Beheercentrum-SharePoint-activiteit
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
description: U kunt het rapport gebruik van SharePoint-activiteit weergeven voor informatie over de activiteiten van elke SharePoint-gebruiker, het aantal gedeelde bestanden en het gebruik van de opslagruimte.
ms.openlocfilehash: 1d4b288fed9e15139c92bc7e43795393d03ba2fb
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649776"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-rapporten in het Beheercentrum-SharePoint-activiteit

Als Microsoft 365-beheerder wordt in het dashboard **rapporten** het overzicht van de activiteiten weergegeven voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. Bekijk de [activiteitenoverzichten in het Microsoft 365-Beheercentrum](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van SharePoint heeft door zijn of haar interactie met bestanden te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien. 
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hoe kom ik aan het rapport met SharePoint-activiteiten?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
2. Klik op de startpagina van het dashboard op de knop **meer weergeven** op de SharePoint-kaart.
  
## <a name="interpret-the-sharepoint-activity-report"></a>Het SharePoint-activiteitenrapport interpreteren

U kunt de activiteiten in het SharePoint-rapport weergeven door het tabblad **activiteit** te kiezen.<br/>![Microsoft 365-rapporten-rapport Microsoft SharePoint-activiteit.](../../media/5a0a96f-0e4f-4fb9-8baa-3262275b3d1f.png)

Selecteer **kolommen kiezen** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> ![SharePoint-activiteitenrapport-kolommen kiezen](../../media/3c396cd1-9701-4712-8eaa-eb7bba702aa8.png)

U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. 
  
|Item|Beschrijving|
|:-----|:-----|
|**Gegevens**|**Definitie**|
|Gebruikersnaam  <br/> |Het e-mailadres van de gebruiker die de activiteit op de SharePoint-site heeft uitgevoerd.  <br/> |
|Datum van laatste activiteit (UTC)  <br/> |De datum waarop de laatste Bestandsactiviteit is uitgevoerd of er is een pagina voor het geselecteerde datumbereik bezocht. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> |
|Weergegeven of bewerkte bestanden  <br/> |Het aantal bestanden dat door de gebruiker is geüpload, gedownload, gewijzigd of bekeken.   <br/> |
|Gesynchroniseerde bestanden  <br/> |Het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker naar de SharePoint-site. <br/> |
|Intern gedeelde bestanden  <br/> | Het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie, of met gebruikers in groepen (die mogelijk zijn van externe gebruikers).  <br/> |
|Extern gedeelde bestanden  <br/> |Het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie. <br/>|
|Bezochte pagina's  <br/> |De bezoeken van de gebruiker naar unieke pagina's. <br/>|
|Deleted  <br/> | Hiermee wordt aangegeven dat de licentie van de gebruiker is verwijderd.  <br/>  **Opmerking:** Activiteiten voor een verwijderde gebruiker worden nog steeds weergegeven in het rapport, mits hij of zij op een bepaald moment in de geselecteerde periode een licentie heeft. In de kolom Verwijderd kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.  <br/> |
|Datum verwijderd  <br/> |De datum waarop de licentie van de gebruiker is verwijderd. <br/>|
|Product toegewezen  <br/> |De Microsoft 365-producten waarvoor de gebruiker een licentie heeft.|
|||