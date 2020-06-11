---
title: Microsoft 365-rapporten in het beheercentrum - Gebruik van SharePoint-site
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
description: 'Download het SharePoint-sitegebruiksrapport om te weten hoeveel bestanden gebruikers opslaan in SharePoint-sites, hoeveel er actief worden gebruikt en hoeveel opslagruimte er zijn verbruikt. '
ms.openlocfilehash: b39f1588f5c0c68a5972aab3039a8d7d901f9dc5
ms.sourcegitcommit: efd4dd29af0ea2b71b674534de3b2dcbfd7482db
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689298"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van SharePoint-site

Als Microsoft 365-beheerder toont het dashboard **Rapporten** u het activiteitenoverzicht voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. U kunt bijvoorbeeld een overzicht op hoog niveau krijgen van de toegevoegde waarde van SharePoint voor wat betreft het totale aantal bestanden die gebruikers in SharePoint-sites opslaan, het aantal bestanden die actief worden gebruikt en de opslagruimte die wordt gebruikt door al deze sites. Vervolgens kunt u inzoomen op het gebruiksrapport voor SharePoint-sites om inzicht te krijgen in de trends en de details op siteniveau voor alle sites. 
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven-beheerder om rapporten te kunnen bekijken.
Microsoft 365-rapporten in het beheercentrum worden niet ondersteund voor GCC High- en DoD-tenants.
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites verkrijgen

1. Ga in het beheercentrum naar **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Rapportgebruik</a>.

    
2. Selecteer **in** de vervolgkeuzelijst Een rapport selecteren de optie **SharePoint** \> **SharePoint-sitegebruik**.
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites interpreteren

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruik van SharePoint-sites** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven gedurende maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur. <br/> |
|3.  <br/> |In de grafiek **Sites** wordt het aantal totale en actieve sites weergegeven, inclusief een site waarin gebruikers een bestand hebben bekeken, gewijzigd, geüpload, gedownload, gedeeld of gesynchroniseerd of een pagina hebben bekeken binnen de rapportageperiode.  <br/> |
|4.  <br/> |De grafiek **Bestanden** toont het totale aantal bestanden in alle sites en het aantal actieve bestanden. Het totale aantal bestanden bestaat uit zowel de gebruikersbestanden als de systeembestanden. Een bestand wordt als actief beschouwd als het is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in de specifieke periode.  |
|5.  <br/> |De grafiek **Opslag** toont de trend voor toegewezen en gebruikte opslagruimte tijdens de rapportageperiode.  <br/> |
|6.  <br/> |In de grafiek **Pagina's** ziet u het aantal bekeken pagina's voor alle sites.  <br/> |
|7.  <br/> |U grafieken filteren die u ziet door een item in de legenda te selecteren. **Selecteer** bijvoorbeeld bestanden of **actieve bestanden**in de grafiek **Bestanden** . In het diagram **Sites** u **Totaalsites** of **Actieve sites**selecteren. In het **grafiek Opslag** u **opslag** toegewezen of **verbruikte opslag selecteren.** Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van de activiteiten per site.  <br/> ![Kolomopties voor gebruiksrapport](../../media/sharepointsite-usage.png)           <br/> **Site-URL** is de volledige URL van de site.  <br/> **Verwijderd** is de verwijderstatus van de site. Het duurt minimaal zeven dagen voordat sites kunnen worden gemarkeerd als verwijderd.  <br/> **Site-eigenaar** is de gebruikersnaam van de primaire eigenaar van de site.  <br/>**De hoofdnaam van de site-eigenaar** is het e-mailadres van de eigenaar van de site.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum waarop de laatste bestandsactiviteit is gedetecteerd of waarop een pagina is bekeken op de site.  <br/> **Bestanden** is het aantal bestanden op de site.  <br/> **Actieve bestanden** is het aantal actieve bestanden op de site.<br/> OPMERKING: Als bestanden zijn verwijderd tijdens de opgegeven periode voor het rapport, kan het aantal actieve bestanden in het rapport groter zijn dan het huidige aantal bestanden op de site.<br/>**Opslag gebruikt (MB)** is de hoeveelheid opslagruimte die op dat moment op de site wordt gebruikt.  <br/> **Opslag toegewezen (MB)** is de maximale hoeveelheid opslagruimte die voor de site is toegewezen.  <br/> **Paginaweergaven** is het aantal keer dat pagina's op de site zijn bekeken.  <br/> **Pagina's bezocht** is het aantal unieke pagina's dat op de site is bezocht.  <br/> **Basiswebsjabloon** is de sjabloon die wordt gebruikt voor het maken van de site.  <br/> OPMERKING: Als u de gegevens wilt filteren op verschillende sitetypen, exporteert u de gegevens en gebruikt u de kolom Hoofdwebsjabloon. <br/>Als het beleid van uw organisatie voorkomt dat u rapporten bekijkt waarin gebruikersgegevens identificeerbaar zijn, u de privacyinstelling voor al deze rapporten wijzigen. Bekijk de sectie **Hoe verberg ik details op gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen** ![ beheren Kolommen beheren om kolommen uit het rapport toe te voegen of ](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) te verwijderen.    <br/> |
|10.  <br/> |U de rapportgegevens ook exporteren naar een Excel **Export** .csv-bestand door de ![ koppeling Exporteren exporteren te ](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) selecteren. Hiermee exporteert u de gegevens voor alle sites en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 sites hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 sites hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> OPMERKING: Wanneer de gegevens naar een Excel-bestand worden geëxporteerd, wordt er rekening mee dat de datum waarop het inhoudsrapport is gegenereerd, wordt weergegeven in het bestand in de **kolom Gegevens.**      <br/>   |
|||
