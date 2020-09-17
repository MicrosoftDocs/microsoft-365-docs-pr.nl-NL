---
title: Microsoft 365-rapporten in het Beheercentrum-gebruik van SharePoint-sites
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
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'U kunt het rapport gebruik van SharePoint-sites gebruiken om te zien hoeveel bestanden gebruikers opslaan op SharePoint-sites, hoe vaak actief worden gebruikt en de totale gebruikte opslagruimte. '
ms.openlocfilehash: 8c2428a49a42a1d259c69297feff13e5c00a9b8e
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948854"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporten in het Beheercentrum-gebruik van SharePoint-sites

Als Microsoft 365-beheerder toont het dashboard **rapporten** het overzicht van activiteiten voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. U kunt bijvoorbeeld een overzicht op hoog niveau krijgen van de toegevoegde waarde van SharePoint voor wat betreft het totale aantal bestanden die gebruikers in SharePoint-sites opslaan, het aantal bestanden die actief worden gebruikt en de opslagruimte die wordt gebruikt door al deze sites. Vervolgens kunt u inzoomen op het gebruiksrapport voor SharePoint-sites om inzicht te krijgen in de trends en de details op siteniveau voor alle sites. 
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.
Microsoft 365-rapporten in het Beheercentrum wordt niet ondersteund voor GCC High-en DoD-tenants.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites verkrijgen

1. Ga in het Beheercentrum naar het **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">gebruik</a>van rapporten.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **SharePoint-** \> **site gebruik**.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites interpreteren

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruik van SharePoint-sites** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur. <br/> |
|3.  <br/> |In **het grafiek** gebied ziet u het totale aantal en het aantal actieve sites, inclusief de site waarin gebruikers een bestand hebben bekeken, gewijzigd, geüpload, gedownload, gedeeld of gesynchroniseerd, of een pagina binnen de rapportageperiode hebben weergegeven.  <br/> |
|4.  <br/> |De grafiek **Bestanden** toont het totale aantal bestanden in alle sites en het aantal actieve bestanden. Het totale aantal bestanden bestaat uit zowel de gebruikersbestanden als de systeembestanden. Een bestand wordt als actief beschouwd als het is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in de specifieke periode.  |
|5.  <br/> |De grafiek **Opslag** toont de trend voor toegewezen en gebruikte opslagruimte tijdens de rapportageperiode.  <br/> |
|zes.  <br/> |In de grafiek **Pagina's** ziet u het aantal bekeken pagina's voor alle sites.  <br/> |
|7,5.  <br/> |U kunt grafieken die u ziet, filteren door een item te selecteren in de legenda. Selecteer in de grafiek **files** bijvoorbeeld **files** of **Active files**. In het diagram **sites** kunt u **totale sites** of **actieve sites**selecteren. In de grafiek **opslag** kunt u de **toegewezen opslagruimte** en gebruikte **opslagruimte selecteren.** Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|8:00.  <br/> | De tabel toont een onderverdeling van de activiteiten per site.  <br/> ![Kolom opties voor gebruiksrapport](../../media/sharepointsite-usage.png)           <br/> **Site-URL** is de volledige URL van de site.  <br/> **Verwijderd** is de verwijderstatus van de site. Het duurt minimaal zeven dagen voordat sites kunnen worden gemarkeerd als verwijderd.  <br/> **Site-eigenaar** is de gebruikersnaam van de primaire eigenaar van de site.  <br/>**Principal-naam van site-eigenaar** is het e-mailadres van de eigenaar van de site.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum waarop de laatste bestandsactiviteit is gedetecteerd of waarop een pagina is bekeken op de site.  <br/> **Bestanden** is het aantal bestanden op de site.  <br/> **Actieve bestanden** is het aantal actieve bestanden op de site.<br/> Opmerking: als er tijdens de opgegeven periode voor het rapportbestanden zijn verwijderd, is het aantal actieve bestanden dat in het rapport wordt getoond groter dan het huidige aantal bestanden op de site.<br/>**Opslag gebruikt (MB)** is de hoeveelheid opslagruimte die op dat moment op de site wordt gebruikt.  <br/> **Opslag toegewezen (MB)** is de maximale hoeveelheid opslagruimte die voor de site is toegewezen.  <br/> **Paginaweergaven** is het aantal keer dat pagina's op de site zijn bekeken.  <br/> **Pagina's bezocht** is het aantal unieke pagina's dat op de site is bezocht.  <br/> **Basiswebsjabloon** is de sjabloon die wordt gebruikt voor het maken van de site.  <br/> Opmerking: als u de gegevens wilt filteren op verschillende site typen, exporteert u de gegevens en gebruikt u de kolom hoofd websjabloon. <br/>Als de beleidsregels van uw organisatie rapporten verhinderen waarin gebruikersgegevens kunnen worden weergegeven, kunt u de privacy-instelling voor al deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|aanhaling.  <br/> |Selecteer **kolommen beheren** ![ ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Als u kolommen wilt toevoegen aan of verwijderen uit het rapport.    <br/> |
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel **door de export koppeling exporteren te** selecteren ![ ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) . Hiermee exporteert u de gegevens voor alle sites en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 sites hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 sites hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> Opmerking: wanneer de gegevens worden geëxporteerd naar een Excel-bestand, wordt de datum waarop de Rapportinhoud is gegenereerd in het bestand in de kolom **gegevens vanaf** weergegeven.      <br/>   |
|||
