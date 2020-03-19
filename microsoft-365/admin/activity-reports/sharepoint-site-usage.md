---
title: Microsoft 365-rapporten in het beheercentrum - SharePoint-sitegebruik
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
ms.assetid: 4ecfb843-e5d5-464d-8bf6-7ed512a9b213
description: 'Laat het rapport SharePoint-sitegebruik weten hoeveel bestanden gebruikers opslaan op SharePoint-sites, hoeveel er actief worden gebruikt en de totale opslagruimte wordt verbruikt. '
ms.openlocfilehash: c60d33ce299d63edafc4ce996bb4ba07ce9b7fa0
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42811012"
---
# <a name="microsoft-365-reports-in-the-admin-center---sharepoint-site-usage"></a>Microsoft 365-rapporten in het beheercentrum - SharePoint-sitegebruik

Als Microsoft 365-beheerder toont het dashboard **Rapporten** u het activiteitenoverzicht voor verschillende producten in uw organisatie. Hiermee kunt u inzoomen om meer inzicht te krijgen in de activiteiten die specifiek zijn voor elk product. U kunt bijvoorbeeld een overzicht op hoog niveau krijgen van de toegevoegde waarde van SharePoint voor wat betreft het totale aantal bestanden die gebruikers in SharePoint-sites opslaan, het aantal bestanden die actief worden gebruikt en de opslagruimte die wordt gebruikt door al deze sites. Vervolgens kunt u inzoomen op het gebruiksrapport voor SharePoint-sites om inzicht te krijgen in de trends en de details op siteniveau voor alle sites. 
  
> OPMERKING: U moet een globale beheerder, globale lezer of rapportenlezer in Microsoft 365 of een Exchange-, SharePoint- of Skype voor Bedrijven-beheerder zijn om rapporten te kunnen bekijken. 
 
## <a name="how-to-get-to-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer \> **sharepoint-sitegebruik in** **SharePoint** de vervolgkeuzelijst **Een rapport selecteren.**
  
## <a name="interpreting-the-sharepoint-site-usage-report"></a>Het gebruiksrapport voor SharePoint-sites interpreteren

![SharePoint Site Usage Report](../../media/4f88fb7d-9aa8-470e-9e23-e31caaf77d78.png)
  
|||
|:-----|:-----|
|1.  <br/> |In het rapport **Gebruik van SharePoint-sites** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven gedurende maximaal 28 dagen na de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur. <br/> |
|3.  <br/> |De grafiek **Sites** toont het totale aantal en het aantal actieve sites. Elke site waarop gebruikers in de rapportageperiode een bestand hebben bekeken, gewijzigd, geüpload, gedownload, gedeeld of gesynchroniseerd of een pagina hebben bekeken.  <br/> |
|4.  <br/> |De grafiek **Bestanden** toont het totale aantal bestanden in alle sites en het aantal actieve bestanden. Het totale aantal bestanden bestaat uit zowel de gebruikersbestanden als de systeembestanden. Een bestand wordt als actief beschouwd als het is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in de specifieke periode.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren optreden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens.           |
|5.  <br/> |De grafiek **Opslag** toont de trend voor toegewezen en gebruikte opslagruimte tijdens de rapportageperiode.  <br/> |
|6.  <br/> |In de grafiek **Pagina's** ziet u het aantal bekeken pagina's voor alle sites.  <br/> |
|7.  <br/> |U grafieken filteren die u ziet door een item in de legenda te selecteren. Selecteer bijvoorbeeld **Bestanden** of **Actieve bestanden**in het **grafiekbestand.** In het diagram **Sites** u **Totaalsites** of **Actieve sites**selecteren. In de **opslaggrafiek** u **Opslag toegewezen** of opslagruimte selecteren **die is verbruikt.** Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van de activiteiten per site.  <br/> ![Kolomopties voor gebruiksrapport](../../media/sharepointsite-usage.png)           <br/> **Site-URL** is de volledige URL van de site.  <br/> **Verwijderd** is de verwijderstatus van de site. Het duurt minimaal zeven dagen voordat sites kunnen worden gemarkeerd als verwijderd.  <br/> **Site-eigenaar** is de gebruikersnaam van de primaire eigenaar van de site.  <br/>**Hoofdnaam site-eigenaar** is het e-mailadres van de eigenaar van de site.  <br/> **Datum van laatste activiteit (UTC)** verwijst naar de datum waarop de laatste bestandsactiviteit is gedetecteerd of waarop een pagina is bekeken op de site.  <br/> **Bestanden** is het aantal bestanden op de site.  <br/> **Actieve bestanden** is het aantal actieve bestanden op de site. Een bestand wordt als actief beschouwd als het is opgeslagen, gesynchroniseerd, gewijzigd of gedeeld in de specifieke periode.  <br/> OPMERKING: Een bestandsactiviteit kan meerdere keren optreden voor één bestand, maar telt slechts als één actief bestand. Zo kunt u bijvoorbeeld hetzelfde bestand meerdere malen opslaan en synchroniseren in een bepaalde periode, maar dit wordt als één actief bestand en één gesynchroniseerd bestand meegeteld in de gegevens. >  Als er bestanden zijn verwijderd tijdens de opgegeven periode voor het rapport, is het aantal actieve bestanden dat in het rapport wordt getoond mogelijk groter dan het huidige aantal bestanden op de site.<br/>**Opslag gebruikt (MB)** is de hoeveelheid opslagruimte die op dat moment op de site wordt gebruikt.  <br/> **Opslag toegewezen (MB)** is de maximale hoeveelheid opslagruimte die voor de site is toegewezen.  <br/> **Paginaweergaven** is het aantal keer dat pagina's op de site zijn bekeken.  <br/> **Pagina's bezocht** is het aantal unieke pagina's dat op de site is bezocht.  <br/> **Basiswebsjabloon** is de sjabloon die wordt gebruikt voor het maken van de site.  <br/> OPMERKING: Als u de gegevens wilt filteren op verschillende sitetypen, exporteert u de gegevens en gebruikt u de kolom Basiswebsjabloon. <br/>Als het beleid van uw organisatie u belet rapporten te bekijken waar gebruikersinformatie identificeerbaar is, u de privacyinstelling voor al deze rapporten wijzigen. Bekijk de details van het **gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen**![beheren](../../media/13d2e536-de88-4db3-80c7-7a3a57298eb4.png) Kolommen beheren om kolommen uit het rapport toe te voegen of te verwijderen.    <br/> |
|10.  <br/> |U de rapportgegevens ook exporteren naar een Csv-bestand van Excel door de koppeling **Exporteren** ![](../../media/4dc548cc-8061-48d5-9240-6793affca43a.png) te selecteren. Hiermee exporteert u de gegevens voor alle sites en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 sites hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 sites hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> OPMERKING: Wanneer de gegevens naar een Excel-bestand worden geëxporteerd, moet u er rekening mee houden dat de datum waarop het inhoudsrapport is gegenereerd, wordt weergegeven in het bestand in de kolom **Gegevens.**      <br/>   |
|||
   

