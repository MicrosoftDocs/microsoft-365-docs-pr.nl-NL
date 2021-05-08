---
title: Microsoft 365 Rapporten in het beheercentrum - OneDrive voor Bedrijven activiteit
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
description: Krijg het OneDrive gebruiksrapport voor uw organisatie en weet de activiteit van elke gebruiker OneDrive, het aantal gedeelde bestanden en het opslaggebruik.
ms.openlocfilehash: 8257d8e85819ff5edae96967fd4a687be3a903a1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244090"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365 Rapporten in het beheercentrum - OneDrive voor Bedrijven activiteit

In Microsoft 365 **dashboard Rapporten** ziet u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van OneDrive heeft door zijn of haar interactie met bestanden op OneDrive te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven-beheerder om rapporten te kunnen zien.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hoe ga ik naar het OneDrive-activiteitenrapport?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>. 
2. Klik op de startpagina van het dashboard op de knop **Meer** weergeven op de OneDrive kaart.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Het OneDrive voor Bedrijven-activiteitenrapport interpreteren

U kunt de activiteiten in het rapport OneDrive door het tabblad **Activiteit te** kiezen.<br/>![Microsoft 365 rapporten - Microsoft OneDrive activiteitsrapport.](../../media/c89df0b0-2611-4acf-9ef7-17cedf7977be.png)

Selecteer **Kolommen kiezen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![OneDrive activiteitsrapport - kolommen kiezen](../../media/252f311f-ffde-4e5a-9158-2b822bf86964.png)

U kunt de rapportgegevens ook exporteren naar een Excel .csv bestand door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren. 
  
|Item|Beschrijving|
|:-----|:-----|
|**Metrische**|**Definitie**|
|Gebruikersnaam  <br/> |De gebruikersnaam van de eigenaar van het OneDrive account.  <br/> |
|Laatste activiteitsdatum (UTC)  <br/> |De laatste datum waarop een bestandsactiviteit is uitgevoerd op het OneDrive account voor het geselecteerde datumbereik. . Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> |
|Bekeken of bewerkte bestanden  <br/> |Het aantal bestanden dat de gebruiker heeft geüpload, gedownload, gewijzigd of bekeken.   <br/> |
|Bestanden gesynchroniseerd  <br/> |Het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker met het OneDrive account. <br/> |
|Bestanden die intern worden gedeeld  <br/> | Het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> |
|Bestanden die extern worden gedeeld  <br/> |Het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie. <br/>|
|Verwijderd  <br/> | Dit geeft aan dat de licentie van de gebruiker is verwijderd.  <br/> OPMERKING: Activiteiten voor een verwijderde gebruiker worden nog steeds weergegeven in een rapport zolang hij of zij een licentie heeft gekregen gedurende de geselecteerde periode. In de kolom **Verwijderd** kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.  <br/> |
|Verwijderde datum  <br/> |De datum waarop de licentie van de gebruiker is verwijderd. <br/>|
|Product toegewezen  <br/> |De Microsoft 365 producten die zijn gelicentieerd aan de gebruiker.|
|||