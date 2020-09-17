---
title: Microsoft 365-rapporten in het Beheercentrum-SharePoint-activiteit
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: U kunt het rapport gebruik van SharePoint-activiteit weergeven voor informatie over de activiteiten van elke SharePoint-gebruiker, het aantal gedeelde bestanden en het gebruik van de opslagruimte.
ms.openlocfilehash: b0c628300647e83889e273268bef7abd9e337ed4
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948866"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-rapporten in het Beheercentrum-SharePoint-activiteit

Als Microsoft 365-beheerder wordt in het dashboard **rapporten** het overzicht van de activiteiten weergegeven voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. Bekijk de [activiteitenoverzichten in het Microsoft 365-Beheercentrum](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van SharePoint heeft door zijn of haar interactie met bestanden te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> Sommige functionaliteit wordt geleidelijk geïntroduceerd. Dit betekent dat u bepaalde functies nog niet kunt zien of dat de functies er anders uit kunnen zien dan beschreven in de Help-artikelen. Maar maak u geen zorgen. Ze komen er binnenkort aan! 
  
Als u wilt begrijpen hoeveel activiteit plaatsvindt op elke SharePoint-site en hoe de opslagruimte wordt gebruikt, bekijkt u het [rapport Gebruik van SharePoint-site](sharepoint-site-usage.md).
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hoe kom ik aan het rapport met SharePoint-activiteiten?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **SharePoint** - \> **activiteit**.
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Het rapport SharePoint-activiteit interpreteren

U kunt inzicht van SharePoint-activiteit krijgen door de weergaven **Bestanden** en **Gebruikers** te bekijken.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het **SharePoint-activiteitenrapport** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De weergave **Bestanden** helpt u inzicht te krijgen in het unieke aantal gebruikers met een licentie dat bestandsinteracties uitvoert met bestanden die zijn opgeslagen op SharePoint-sites.  <br/> |
|4.  <br/> |Op de weergave **Pagina's** ziet u het aantal unieke pagina's dat door gebruikers is bezocht.  <br/> |
|5.  <br/> |De weergave **Gebruikers** geeft inzicht in de trend van het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.  <br/> Opmerking: een Bestandsactiviteit kan meerdere keren voor één bestand optreden, maar wordt slechts als één actief bestand geteld. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens           |
|zes.  <br/> | In de grafiek **Bestanden** geeft de Y-as het aantal unieke bestanden aan dat een gebruiker heeft opgeslagen, gesynchroniseerd, gewijzigd of gedeeld.  <br/>  In de grafiek **Gebruikers** geeft de Y-as het aantal unieke gebruikers aan dat een bestandsinteractie heeft uitgevoerd (opslaan, synchroniseren, wijzigen of delen) op een site.  <br/>  In het diagram **Pagina's** geeft de X-as het aantal unieke pagina's weer dat door gebruikers is bezocht.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|7,5.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek **bestanden** de optie **weergegeven of bewerkt**, **gesynchroniseerd**, **intern**of extern gedeeld of **extern gedeeld** om alleen de gegevens weer te geven die betrekking hebben op elk item. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|8:00.  <br/> | De tabel toont een onderverdeling van de activiteiten per site.  <br/>  <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit op de SharePoint-site heeft uitgevoerd.  <br/> **Datum van laatste activiteit (UTC)** is de datum waarop de laatste bestandsactiviteit voor het geselecteerde datumbereik heeft plaatsgevonden of een pagina is bezocht. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> ![Een specifieke datum in de grafiek selecteren](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> Hiermee wordt de tabel gefilterd en worden gegevens over Bestandsactiviteiten alleen weergegeven voor gebruikers die de activiteit op die bepaalde dag hebben uitgevoerd.  <br/>  **Weergegeven of bewerkte bestanden** is het aantal bestanden dat door de gebruiker is geüpload, gedownload, gewijzigd of bekeken.  <br/>  **Gesynchroniseerde bestanden** is het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker naar de SharePoint-site.  <br/>  **Intern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie, of met gebruikers in groepen (die mogelijk zijn voor externe gebruikers).  <br/>  **Extern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie.  <br/>  **Pagina's** die u hebt bezocht, zijn de bezoekers van de gebruiker naar unieke pagina's.  <br/>  **Verwijderd** geeft aan dat de licentie van de gebruiker werd verwijderd.  <br/>  **Opmerking:** Activiteiten voor een verwijderde gebruiker worden nog steeds weergegeven in het rapport, mits hij of zij op een bepaald moment in de geselecteerde periode een licentie heeft. In de kolom Verwijderd kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.  <br/> **Datum verwijderd** is de datum waarop de licentie van de gebruiker werd verwijderd.  <br/>  **Toegewezen producten** zijn de microsoft 365-producten waarvoor de gebruiker een licentie heeft.  <br/> |
|aanhaling.  <br/> |Selecteer het pictogram **kolommen beheren** ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> |
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u deze eenvoudig sorteren en filteren voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

