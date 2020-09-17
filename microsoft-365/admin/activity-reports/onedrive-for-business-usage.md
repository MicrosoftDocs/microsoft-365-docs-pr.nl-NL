---
title: Microsoft 365-rapporten in het Beheercentrum-gebruik van OneDrive voor bedrijven
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
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Neem het rapport gebruik van OneDrive voor bedrijven in voor informatie over het totale aantal bestanden en opslagruimte die wordt gebruikt in uw organisatie. '
ms.openlocfilehash: e08dff4e763479afa197377d37e474384492c012
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948914"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporten in het Beheercentrum-gebruik van OneDrive voor bedrijven

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
De OneDrive-kaart op het dashboard geeft u bijvoorbeeld een overzicht op hoog niveau van de toegevoegde waarde van OneDrive voor Bedrijven voor wat betreft het totale aantal bestanden en de totale hoeveelheid opslag die in uw organisatie wordt gebruikt. U kunt vervolgens inzoomen om meer informatie te krijgen over de trends in de actieve OneDrive-accounts, te zien hoeveel bestanden worden gebruikt en hoeveel opslag wordt gebruikt. U vindt hier ook details voor de OneDrive van elke gebruiker.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Hoe ga ik naar het OneDrive-gebruiksrapport?

1. Ga in het Beheercentrum naar het **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">gebruik</a>van rapporten.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **OneDrive** - \> **gebruik**. 
  
## <a name="interpret-the-onedrive-usage-report"></a>Het rapport Gebruik van OneDrive interpreteren

U krijgt inzicht in het gebruik van OneDrive voor Bedrijven door de weergaven **Accounts**, **Bestanden** en **Opslag** te bekijken. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruik van OneDrive** worden trends weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur. <br/>|
|3.  <br/> |In de weergave **Accounts** wordt de trend weergegeven van het totale aantal en het aantal actieve OneDrive-accounts. 'Actieve accounts' zijn accounts waarmee gebruikers bestanden weergeven, wijzigen, uploaden, downloaden, delen of synchroniseren.  <br/> |
|4.  <br/> |In de weergave **bestanden** ziet u het totale aantal en het aantal actieve bestanden. Als het bestand is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in een specifieke periode, wordt dit als actief beschouwd.  <br/> Opmerking: een Bestandsactiviteit kan meerdere keren voor één bestand optreden, maar wordt slechts als één actief bestand geteld. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens.           |
|5.  <br/> |De weergave **Opslag** toont de trend voor de hoeveelheid OneDrive-opslagruimte die u gebruikt. Als u de opslaglimieten wilt controleren, raadpleegt u [controleren of een gebruiker de standaardopslagruimte of een specifieke limiet heeft](https://docs.microsoft.com/onedrive/set-default-storage-space#check-if-a-user-has-the-default-storage-limit-or-a-specific-limit).  <br/> Opmerking: de grootte omvat alle versies en metagegevens die zijn gekoppeld aan de bestanden.           |
|zes.  <br/> | In de grafiek **Accounts** is de Y-as het aantal OneDrive-accounts.  <br/>  In de grafiek **Bestanden** is de Y-as het aantal bestanden dat is opgeslagen in OneDrive.  <br/>  In de grafiek **Opslag** is de Y-as de hoeveelheid OneDrive-opslagruimte die wordt gebruikt.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|7,5.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek **bestanden** de optie **totale bestanden** of **actieve bestanden**. Selecteer in de grafiek **accounts** de optie **totale accounts** of **actieve accounts**. Selecteer in de grafiek **Storage** de optie **gebruikte opslagruimte**. Door deze selectie te wijzigen, wordt de informatie in de tabel niet gewijzigd.  <br/> |
|8:00.  <br/> | De tabel toont een onderverdeling van de gegevens van de OneDrive van elke gebruiker. In de tabel worden alleen gebruikers weergegeven die een toegewezen productlicentie inclusief OneDrive hebben, en die SharePoint Online hebben ingeschakeld. Gebruikers moeten ook zijn aangemeld bij de synchronisatieclient van OneDrive of met een webbrowser naar hun zijn gegaan.  <br/>  Als er bestandsactiviteit op de OneDrive heeft plaatsgevonden, wordt de laatste datum vermeld waarop bestandsactiviteit heeft plaatsgevonden. De rijen in de tabel zijn gesorteerd op **Datum van laatste activiteit**. De OneDrive met de meest recente bestandsactiviteit staat dus bovenaan in de lijst.  <br/>  U kunt kolommen toevoegen aan of verwijderen uit de tabel.  <br/> ![Kolom opties](../../media/onedriveusage-columns.png)  <br/> **URL** is het webadres voor de OneDrive van de gebruiker.  <br/> **Verwijderd** is de verwijderstatus van de OneDrive. Het duurt ten minste zeven dagen voor accounts kunnen worden gemarkeerd als verwijderd.  <br/> **Eigenaar** is de gebruikersnaam van de primaire beheerder van de OneDrive.  <br/> **Principal-naam van eigenaar** is het e-mailadres van de eigenaar van de OneDrive.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum waarop de laatste bestandsactiviteit in de OneDrive is uitgevoerd. Als er geen bestandsactiviteit voor OneDrive heeft plaatsgevonden, is de waarde leeg.  <br/> **Bestanden** is het aantal bestanden in de OneDrive.  <br/> **Actieve bestanden** is het aantal actieve bestanden gedurende de tijdsperiode.<br/> Opmerking: als er tijdens de opgegeven periode voor het rapportbestanden zijn verwijderd, is het aantal actieve bestanden dat in het rapport wordt getoond groter dan het huidige aantal bestanden in de OneDrive. Verwijderde gebruikers kunnen nog steeds worden weergegeven in rapporten voor 180 dagen.<br/>**Opslag gebruikt (MB)** is de hoeveelheid opslagruimte in MB die door de OneDrive wordt gebruikt. <br/>  Als de beleidsregels van uw organisatie rapporten verhinderen waarin gebruikersgegevens kunnen worden weergegeven, kunt u de privacy-instelling voor al deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|aanhaling.  <br/> |Selecteer het pictogram **kolommen beheren** ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> |
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van elke OneDrive en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 OneDrive-accounts hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 OneDrive-accounts hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> Opmerking: wanneer de gegevens worden geëxporteerd naar een Excel-bestand, wordt de datum waarop de Rapportinhoud is gegenereerd in het bestand in de kolom **gegevens vanaf** weergegeven.  <br/> |
|||
   
