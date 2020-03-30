---
title: Microsoft 365-rapporten in het beheercentrum - SharePoint-activiteit
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- SPO160
- BSA160
ms.assetid: a91c958f-1279-499d-9959-12f0de08dc8f
description: Laat het sharepoint-activiteitengebruiksrapport weten over de activiteit van elke SharePoint-gebruiker, het aantal gedeelde bestanden en het opslaggebruik.
ms.openlocfilehash: a3c8d73707ef09c3702450ebddab6e43c159638c
ms.sourcegitcommit: 2b626a7924b4be08f6eb21181453b778e6fde418
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/30/2020
ms.locfileid: "43047045"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-activity"></a>Microsoft 365-rapporten in het beheercentrum - SharePoint-activiteit

Als Microsoft 365-beheerder toont het dashboard **Rapporten** u het activiteitenoverzicht van verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. Bekijk de [activiteitenrapporten in het Microsoft 365-beheercentrum](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van SharePoint heeft door zijn of haar interactie met bestanden te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> Sommige functionaliteit wordt geleidelijk geïntroduceerd. Dit betekent dat u bepaalde functies nog niet kunt zien of dat de functies er anders uit kunnen zien dan beschreven in de Help-artikelen. Maar maak u geen zorgen. Ze komen er binnenkort aan! 
  
Als u wilt begrijpen hoeveel activiteit plaatsvindt op elke SharePoint-site en hoe de opslagruimte wordt gebruikt, bekijkt u het [rapport Gebruik van SharePoint-site](sharepoint-site-usage.md).
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-service-, Teams-communicatie- of Skype voor Bedrijven-beheerder om rapporten te bekijken.  
 
## <a name="how-do-i-get-to-the-to-the-sharepoint-activity-report"></a>Hoe kom ik aan het rapport met SharePoint-activiteiten?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer **SharePoint-activiteit** \> in de vervolgkeuzelijst **Een rapport** **selecteren**.
  
## <a name="interpreting-the-sharepoint-activity-report"></a>Het rapport SharePoint-activiteit interpreteren

U kunt inzicht van SharePoint-activiteit krijgen door de weergaven **Bestanden** en **Gebruikers** te bekijken.<br/> ![SharePoint Activity Report](../../media/96ee85af-f213-499b-9e2b-22912bd0b8c2.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het **SharePoint-activiteitenrapport** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De weergave **Bestanden** helpt u inzicht te krijgen in het unieke aantal gebruikers met een licentie dat bestandsinteracties uitvoert met bestanden die zijn opgeslagen op SharePoint-sites.  <br/> |
|4.  <br/> |Op de weergave **Pagina's** ziet u het aantal unieke pagina's dat door gebruikers is bezocht.  <br/> |
|5.  <br/> |De weergave **Gebruikers** geeft inzicht in de trend van het aantal actieve gebruikers. Een gebruiker wordt als actief beschouwd als hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) heeft uitgevoerd of een pagina bezocht in de opgegeven periode.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren plaatsvinden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens           |
|6.  <br/> | In de grafiek **Bestanden** geeft de Y-as het aantal unieke bestanden aan dat een gebruiker heeft opgeslagen, gesynchroniseerd, gewijzigd of gedeeld.  <br/>  In de grafiek **Gebruikers** geeft de Y-as het aantal unieke gebruikers aan dat een bestandsinteractie heeft uitgevoerd (opslaan, synchroniseren, wijzigen of delen) op een site.  <br/>  In het diagram **Pagina's** geeft de X-as het aantal unieke pagina's weer dat door gebruikers is bezocht.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|7.  <br/> |U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Bestanden** **Bekeken of bewerkt,** **Gesynchroniseerd**, **Intern gedeeld**of **Extern gedeeld** om alleen de informatie te zien die betrekking heeft op elke map. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van de activiteiten per site.  <br/>  <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit op de SharePoint-site heeft uitgevoerd.  <br/> **Datum van laatste activiteit (UTC)** is de datum waarop de laatste bestandsactiviteit voor het geselecteerde datumbereik heeft plaatsgevonden of een pagina is bezocht. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> ![Een specifieke datum in de grafiek selecteren](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png) <br/> Hiermee filtert u de tabel om bestandsactiviteitsgegevens alleen weer te geven voor gebruikers die de activiteit op die specifieke dag hebben uitgevoerd.  <br/>  **Weergegeven of bewerkte bestanden** is het aantal bestanden dat door de gebruiker is geüpload, gedownload, gewijzigd of bekeken.  <br/>  **Bestanden die zijn gesynchroniseerd,** is het aantal bestanden dat is gesynchroniseerd van het lokale apparaat van een gebruiker naar de SharePoint-site.  <br/>  **Bestanden die intern worden gedeeld,** is het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/>  **Extern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie.  <br/>  **Bezochte pagina's** zijn de bezoeken aan unieke pagina's door de gebruiker.  <br/>  **Verwijderd** geeft aan dat de licentie van de gebruiker werd verwijderd.  <br/>  **LET OP:** Activiteit voor een verwijderde gebruiker wordt nog steeds weergegeven in het rapport zolang hij of zij op een bepaald moment tijdens de geselecteerde periode een licentie heeft. In de kolom Verwijderd kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.  <br/> **Datum verwijderd** is de datum waarop de licentie van de gebruiker werd verwijderd.  <br/>  **Toegewezen product** zijn de Microsoft 365-producten waarvoor een licentie is verleend aan de gebruiker.  <br/> |
|9.  <br/> |Selecteer **Manage columns** het pictogram ![Kolommen](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) beheren Kolommen beheren om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> |
|10.  <br/> |U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u deze eenvoudig sorteren en filteren voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

