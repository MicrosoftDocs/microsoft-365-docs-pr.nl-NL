---
title: Microsoft 365-rapporten in het Beheercentrum-activiteit van OneDrive voor bedrijven
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
description: U ontvangt het OneDrive-gebruiksrapport voor uw organisatie en weet de activiteit van elke OneDrive-gebruiker, het aantal gedeelde bestanden en het gebruik van de opslagruimte.
ms.openlocfilehash: dd5ac1c52d2226b12c75dc92c3407012251a90da
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948923"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-activity"></a>Microsoft 365-rapporten in het Beheercentrum-activiteit van OneDrive voor bedrijven

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
U kunt bijvoorbeeld inzicht krijgen in de activiteiten van elke gebruiker die een licentie voor het gebruik van OneDrive heeft door zijn of haar interactie met bestanden op OneDrive te bekijken. U kunt ook beter begrijpen in hoeverre gebruikers samenwerken door het aantal gedeelde bestanden te bekijken.
  
> [!NOTE]
> Sommige functionaliteiten worden geleidelijk geïntroduceerd. Dit betekent dat u bepaalde functies nog niet kunt zien of dat de functies er anders uit kunnen zien dan beschreven in de Help-artikelen. Maar maak u geen zorgen, ze komen er binnenkort aan! 
  
Raadpleeg het [rapport Gebruik van OneDrive](onedrive-for-business-usage.md) om te begrijpen hoeveel activiteit plaatsvindt op elk OneDrive-account en hoe de opslagruimte wordt gebruikt.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-do-i-get-to-the-onedrive-activity-report"></a>Hoe ga ik naar het OneDrive-activiteitenrapport?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **OneDrive** - \> **activiteit**.
  
## <a name="interpret-the-onedrive-for-business-activity-report"></a>Het OneDrive voor Bedrijven-activiteitenrapport interpreteren

U krijgt inzicht in de OneDrive voor Bedrijven-activiteit door de weergaven **Bestanden** en **Gebruikers** te bekijken. 
  
![OneDrive Activity Report](../../media/316b2a03-8e42-447c-aae8-080813eebe84.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het **OneDrive voor Bedrijven-activiteitenrapport** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur. <br/>|
|3.  <br/> |De weergave **Bestanden** helpt u inzicht te krijgen in het unieke aantal gebruikers met een licentie dat met bestanden werkt binnen een OneDrive-account.  <br/> |
|4.  <br/> |De weergave **Gebruikers** geeft inzicht in aantallen actieve OneDrive-gebruikers. Een gebruiker wordt als actief beschouwd wanneer hij of zij een bestandsactiviteit (opslaan, synchroniseren, wijzigen of delen) uitvoert in de opgegeven periode.  <br/> Opmerking: een Bestandsactiviteit kan meerdere keren voor één bestand optreden, maar wordt slechts als één actief bestand geteld. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens.           |
|5.  <br/> | In de grafiek **Bestanden** geeft de Y-as het aantal unieke bestanden aan dat een gebruiker heeft opgeslagen, gesynchroniseerd, gewijzigd of gedeeld.  <br/>  In de grafiek **Gebruikers** geeft de Y-as het aantal unieke gebruikers aan dat een bestandsactiviteit heeft uitgevoerd (opslaan, synchroniseren, wijzigen of delen) binnen een OneDrive-account.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|zes.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer in de grafiekbestanden de optie **weergegeven of bewerkte** of **gesynchroniseerde** **bestanden** om alleen de gegevens weer te geven die betrekking hebben op elk item. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|7,5.  <br/> | De tabel toont een uitsplitsing van de gegevens per gebruiker. U kunt kolommen toevoegen aan of verwijderen uit de tabel.   <br/>  **Gebruikers** naam is de gebruikersnaam van de eigenaar van het OneDrive-account.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum binnen het geselecteerde datumbereik waarop de laatste bestandsactiviteit op de OneDrive-account is waargenomen. Als u activiteit voor een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.  <br/> ![Een specifieke datum in de grafiek selecteren](../../media/29e54c4b-8dc2-4ed8-9367-1f66f2988fac.png)  <br/>  Hiermee wordt de tabel gefilterd en worden gegevens over Bestandsactiviteiten alleen weergegeven voor gebruikers die de activiteit op die bepaalde dag hebben uitgevoerd.  <br/> **Weergegeven of bewerkte bestanden** is het aantal bestanden dat door de gebruiker is geüpload, gedownload, gewijzigd of bekeken.  <br/> **Gesynchroniseerde bestanden** is het aantal bestanden dat is gesynchroniseerd vanaf het lokale apparaat van een gebruiker naar het OneDrive-account.  <br/> **Intern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers binnen de organisatie, of met gebruikers in groepen (die mogelijk zijn van externe gebruikers).  <br/> **Extern gedeelde bestanden** is het aantal bestanden dat is gedeeld met gebruikers buiten de organisatie.  <br/> **Verwijderd** geeft aan dat de licentie van de gebruiker werd verwijderd.  <br/> Opmerking: activiteiten voor een verwijderde gebruiker worden nog steeds weergegeven in een rapport, zolang deze op een bepaald moment in de geselecteerde tijdsperiode is toegestaan. In de kolom **Verwijderd** kunt u zien dat de gebruiker niet meer actief is, maar wel heeft bijgedragen aan de gegevens in het rapport.<br/>**Datum verwijderd** is de datum waarop de licentie van de gebruiker werd verwijderd.  <br/> **Toegewezen producten** zijn de microsoft 365-producten waarvoor de gebruiker een licentie heeft.  <br/>  Als de beleidsregels van uw organisatie rapporten verhinderen waarin gebruikersgegevens kunnen worden weergegeven, kunt u de privacy-instelling voor al deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|8:00.  <br/> |Selecteer het pictogram **kolommen beheren** ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> |
|aanhaling.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

