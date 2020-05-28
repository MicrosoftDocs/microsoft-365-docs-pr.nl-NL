---
title: Microsoft 365-rapporten in het beheercentrum - Activiteit van OneDrive voor Bedrijven
ms.author: pebaum
author: pebaum
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 8bbe4bf8-221b-46d6-99a5-2fb3c8ef9353
description: Download het OneDrive-gebruiksrapport voor uw organisatie en ken de activiteit van elke OneDrive-gebruiker, het aantal gedeelde bestanden en het opslaggebruik.
ms.openlocfilehash: 9de2260049d901b401bd62a9e4d05191222b97a3
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387535"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-rapporten in het beheercentrum - Activiteit van OneDrive voor Bedrijven

Het dashboard Microsoft 365 **Rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van OneDrive heeft door zijn of haar interactie met bestanden op OneDrive te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> Sommige functionaliteiten worden geleidelijk geïntroduceerd. Dit betekent dat u bepaalde functies nog niet kunt zien of dat de functies er anders uit kunnen zien dan beschreven in de Help-artikelen. Maar maak u geen zorgen, ze komen er binnenkort aan! 
  
Raadpleeg het [rapport Gebruik van OneDrive](onedrive-for-business-usage.md) om te begrijpen hoeveel activiteit plaatsvindt op elk OneDrive-account en hoe de opslagruimte wordt gebruikt.
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-service-, Teams-communicatie- of Skype voor Bedrijven-beheerder om rapporten te bekijken.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hoe ga ik naar het OneDrive-activiteitenrapport?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer **OneDrive-activiteit** in de vervolgkeuzelijst **Een rapport** \> **selecteren**.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Het OneDrive voor Bedrijven-activiteitenrapport interpreteren

U krijgt inzicht in de OneDrive voor Bedrijven-activiteit door de weergaven **Bestanden** en **Gebruikers** te bekijken. 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het **OneDrive voor Bedrijven-activiteitenrapport** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur. <br/>|
|3.  <br/> |De weergave **Bestanden** helpt u inzicht te krijgen in het unieke aantal gebruikers met een licentie dat met bestanden werkt binnen een OneDrive-account.  <br/> |
|4.  <br/> |De weergave **Gebruikers** geeft inzicht in aantallen actieve OneDrive-gebruikers. Een gebruiker wordt als actief beschouwd wanneer hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) uitvoert in de opgegeven periode.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren plaatsvinden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens.           |
|5.  <br/> | In de grafiek **Bestanden** geeft de Y-as het aantal unieke bestanden aan dat een gebruiker heeft opgeslagen, gesynchroniseerd, gewijzigd of gedeeld.  <br/>  In de grafiek **Gebruikers** geeft de Y-as het aantal unieke gebruikers aan dat een bestandsactiviteit heeft uitgevoerd (opslaan, synchroniseren, wijzigen of delen) binnen een OneDrive-account.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|6.  <br/> |U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Bestanden** **Bekeken of bewerkt** of **Gesynchroniseerd** om alleen de informatie te zien die betrekking heeft op elke grafiek. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|7.  <br/> | De tabel toont een uitsplitsing van de gegevens per gebruiker. U kunt kolommen toevoegen aan of verwijderen uit de tabel.   <br/>  **Gebruikersnaam** is de gebruikersnaam van de eigenaar van het OneDrive-account.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum binnen het geselecteerde datumbereik waarop de laatste bestandsactiviteit op de OneDrive-account is waargenomen. Als u activiteit voor een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> ![Een specifieke datum in de grafiek selecteren](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Hiermee filtert u de tabel om bestandsactiviteitsgegevens alleen weer te geven voor gebruikers die de activiteit op die specifieke dag hebben uitgevoerd.  <br/> **Weergegeven of bewerkte bestanden** is het aantal bestanden dat door de gebruiker is geüpload, gedownload, gewijzigd of bekeken.  <br/> **Gesynchroniseerde bestanden** is het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker naar het OneDrive-account.  <br/> **Bestanden die intern worden gedeeld,** is het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie of met gebruikers binnen groepen (waaronder mogelijk externe gebruikers).  <br/> **Extern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie.  <br/> **Verwijderd** geeft aan dat de licentie van de gebruiker werd verwijderd.  <br/> OPMERKING: Activiteit voor een verwijderde gebruiker wordt nog steeds weergegeven in een rapport zolang hij of zij op een bepaald moment tijdens de geselecteerde periode een licentie heeft. In de kolom **Verwijderd** kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.<br/>**Datum verwijderd** is de datum waarop de licentie van de gebruiker werd verwijderd.  <br/> **Toegewezen product** zijn de Microsoft 365-producten waarvoor een licentie is verleend aan de gebruiker.  <br/>  Als het beleid van uw organisatie voorkomt dat u rapporten bekijkt waarin gebruikersgegevens identificeerbaar zijn, u de privacyinstelling voor al deze rapporten wijzigen. Bekijk de **sectie Hoe verberg ik de gegevens op gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|8.  <br/> |Selecteer het pictogram **Kolommen beheren** Kolommen beheren om kolommen toe te voegen of te verwijderen uit ![ het ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) rapport.  <br/> |
|9.  <br/> |U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

