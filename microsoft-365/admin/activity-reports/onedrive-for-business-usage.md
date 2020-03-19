---
title: Microsoft 365-rapporten in het beheercentrum - Gebruik van OneDrive voor Bedrijven
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
- ODB150
- ODB160
ms.assetid: 0de3b312-c4e8-4e4b-a02d-32b2f726a680
description: 'Laat het gebruiksrapport van OneDrive voor Bedrijven weten over het totale aantal bestanden en opslag dat in uw organisatie wordt gebruikt. '
ms.openlocfilehash: 8bbf904faf1afe28f4a8a83209f681a44eaa932f
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811372"
---
# <a name="microsoft-365-reports-in-the-admin-center---onedrive-for-business-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van OneDrive voor Bedrijven

Het dashboard Microsoft 365 **Rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).
  
De OneDrive-kaart op het dashboard geeft u bijvoorbeeld een overzicht op hoog niveau van de toegevoegde waarde van OneDrive voor Bedrijven voor wat betreft het totale aantal bestanden en de totale hoeveelheid opslag die in uw organisatie wordt gebruikt. U kunt vervolgens inzoomen om meer informatie te krijgen over de trends in de actieve OneDrive-accounts, te zien hoeveel bestanden worden gebruikt en hoeveel opslag wordt gebruikt. U vindt hier ook details voor de OneDrive van elke gebruiker.
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint- of Skype voor Bedrijven-beheerder om rapporten te bekijken. 
 
## <a name="how-do-i-get-to-the-onedrive-usage-report"></a>Hoe ga ik naar het OneDrive-gebruiksrapport?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer **onedrive-gebruik** \> in de vervolgkeuzelijst **Een rapport** **selecteren**. 
  
## <a name="interpret-the-onedrive-usage-report"></a>Het rapport Gebruik van OneDrive interpreteren

U krijgt inzicht in het gebruik van OneDrive voor Bedrijven door de weergaven **Accounts**, **Bestanden** en **Opslag** te bekijken. 
  
![OneDrive Usage Report](../../media/49c5b93b-d081-436e-8992-236343a6d46b.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruik van OneDrive** worden trends weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur. <br/>|
|3.  <br/> |In de weergave **Accounts** wordt de trend weergegeven van het totale aantal en het aantal actieve OneDrive-accounts. 'Actieve accounts' zijn accounts waarmee gebruikers bestanden weergeven, wijzigen, uploaden, downloaden, delen of synchroniseren.  <br/> |
|4.  <br/> |De weergave **Bestanden** toont het totale aantal bestanden en het aantal actieve bestanden. Een bestand wordt als actief beschouwd als het is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in de specifieke periode.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren plaatsvinden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens.           |
|5.  <br/> |De weergave **Opslag** toont de trend voor de hoeveelheid OneDrive-opslagruimte die u gebruikt.  <br/> > OPMERKING: De grootte bevat alle versies en metagegevens die aan de bestanden zijn gekoppeld.           |
|6.  <br/> | In de grafiek **Accounts** is de Y-as het aantal OneDrive-accounts.  <br/>  In de grafiek **Bestanden** is de Y-as het aantal bestanden dat is opgeslagen in OneDrive.  <br/>  In de grafiek **Opslag** is de Y-as de hoeveelheid OneDrive-opslagruimte die wordt gebruikt.  <br/>  De X-as in alle grafieken is het geselecteerde datumbereik voor dit specifieke rapport.  <br/> |
|7.  <br/> |U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Bestanden** de optie **Totaalaantal bestanden** of **Actieve bestanden**. Selecteer **in** de grafiek Accounts de optie **Totale accounts** of **Actieve accounts**. Of selecteer **Opslag gebruikt**in de **grafiek Opslag** . Door deze selectie te wijzigen, wordt de informatie in de tabel niet gewijzigd.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van de gegevens van de OneDrive van elke gebruiker. In de tabel worden alleen gebruikers weergegeven die een toegewezen productlicentie inclusief OneDrive hebben, en die SharePoint Online hebben ingeschakeld. Gebruikers moeten ook zijn aangemeld bij de synchronisatieclient van OneDrive of met een webbrowser naar hun zijn gegaan.  <br/>  Als er bestandsactiviteit op de OneDrive heeft plaatsgevonden, wordt de laatste datum vermeld waarop bestandsactiviteit heeft plaatsgevonden. De rijen in de tabel zijn gesorteerd op **Datum van laatste activiteit**. De OneDrive met de meest recente bestandsactiviteit staat dus bovenaan in de lijst.  <br/>  U kunt kolommen toevoegen aan of verwijderen uit de tabel.  <br/> ![Kolomopties](../../media/onedriveusage-columns.png)  <br/> **URL** is het webadres voor de OneDrive van de gebruiker.  <br/> **Verwijderd** is de verwijderstatus van de OneDrive. Het duurt ten minste zeven dagen voor accounts kunnen worden gemarkeerd als verwijderd.  <br/> **Eigenaar** is de gebruikersnaam van de primaire beheerder van de OneDrive.  <br/> **De hoofdnaam** van de eigenaar is het e-mailadres van de eigenaar van de OneDrive.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum waarop de laatste bestandsactiviteit in de OneDrive is uitgevoerd. Als er geen bestandsactiviteit voor OneDrive heeft plaatsgevonden, is de waarde leeg.  <br/> **Bestanden** is het aantal bestanden in de OneDrive.  <br/> **Actieve bestanden** is het aantal actieve bestanden gedurende de tijdsperiode. Een bestand wordt als actief beschouwd als het in de geselecteerde periode is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren plaatsvinden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens. >  Als er bestanden zijn verwijderd tijdens de opgegeven periode voor het rapport, is het aantal actieve bestanden dat in het rapport wordt getoond, mogelijk groter dan het huidige aantal bestanden in de OneDrive. >  Verwijderde gebruikers kunnen nog 180 dagen nadat ze zijn verwijderd in rapporten worden vermeld.<br/>**Opslag gebruikt (MB)** is de hoeveelheid opslagruimte in MB die door de OneDrive wordt gebruikt. Dit omvat alle versies en metagegevens die zijn gekoppeld aan de bestanden.  <br/>  Als het beleid van uw organisatie voorkomt dat u rapporten bekijkt waarin gebruikersgegevens identificeerbaar zijn, u de privacyinstelling voor al deze rapporten wijzigen. Bekijk de **sectie Hoe verberg ik de gegevens op gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center Preview](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Manage columns** het pictogram ![Kolommen](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) beheren Kolommen beheren om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> |
|10.  <br/> |U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee exporteert u de gegevens van elke OneDrive en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 OneDrive-accounts hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 OneDrive-accounts hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> OPMERKING: Wanneer de gegevens naar een Excel-bestand worden geëxporteerd, moet u er rekening mee houden dat de datum waarop het inhoudsrapport is gegenereerd, wordt weergegeven in het bestand in de kolom **Gegevens.**  <br/> |
|||
   

