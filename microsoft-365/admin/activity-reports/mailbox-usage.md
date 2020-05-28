---
title: Microsoft 365-rapporten in het beheercentrum - Postvakgebruik
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
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Meer informatie over hoe u postvakgebruiksrapport op de hoogte krijgt van de activiteiten van de gebruikers met een gebruikerspostvak.
ms.openlocfilehash: 15da09574b2273e119ba9cf2c132d2e9596e9a64
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387679"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-rapporten in het beheercentrum - Postvakgebruik

Het **postvakgebruiksrapport** bevat informatie over gebruikers met een gebruikerspostvak en het niveau van activiteit door elk op basis van de e-mail verzenden, lezen, afspraak maken, vergadering verzenden, vergadering accepteren, vergadering weigeren en vergaderingsactiviteit annuleren. Het rapport bevat ook informatie over hoeveel opslagruimte in beslag wordt genomen door elk gebruikerspostvak en hoeveel van die postvakken de opslagquota naderen. 
  
> [!NOTE]
> U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-service-, Teams-communicatie- of Skype voor Bedrijven-beheerder om rapporten te bekijken. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Het gebruiksrapport verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **Een rapport** selecteren de optie **Exchange** \> **Exchange-postvakgebruik**.
  
## <a name="interpret-the-mailbox-usage-report"></a>Het rapport Postvakgebruik interpreteren

U krijgt een overzicht van het **Postvakgebruik** in uw organisatie aan de hand van de grafieken **Postvak**, **Opslag** en **Quotum**. 
  
|||
|:-----|:-----|
|1.  <br/> |In het rapport **Postvakgebruik** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De grafiek Postvak toont het totale aantal gebruikerspostvakken in uw organisatie en het totale aantal gebruikerspostvakken dat actief is op een bepaalde dag van de rapportageperiode. Een gebruikerspostvak wordt als actief beschouwd als er een e-mailbericht via het postvak is verzonden of gelezen, een afspraak is gemaakt of een vergadering is verzonden, geaccepteerd, afgewezen of geannuleerd.  <br/> |
|4.  <br/> |De grafiek **Opslag** toont de hoeveelheid gebruikte opslagruimte in uw organisatie. Opslagdiagram bevat geen archiefpostvakken. Zie [Overzicht van onbeperkte archivering in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving)voor meer informatie over het automatisch uitbreiden van archivering.<br/> |
|5.  <br/> | De grafiek **Quotum** toont het aantal gebruikerspostvakken in elke quotumcategorie. Er zijn vier quotumcategorieën:  <br/>  Goed: het aantal gebruikers waarvoor de gebruikte opslagruimte onder het quotum voor Waarschuwing geven ligt.  <br/>  Waarschuwing: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Waarschuwing geven ligt, maar onder het quotum voor Verzenden blokkeren.  <br/>  Kan niet verzenden: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden blokkeren ligt, maar onder het quotum voor Verzenden/ontvangen blokkeren.  <br/>  Kan niet verzenden/ontvangen: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden/ontvangen blokkeren ligt.  <br/> |
|6.  <br/> | In de grafiek **Postvak** bevat de Y-as het aantal gebruikerspostvakken.  <br/>  In de grafiek **Opslag** bevat de Y-as de hoeveelheid opslagruimte die wordt gebruikt door gebruikerspostvakken in uw organisatie.  <br/>  In de grafiek **Quotum** bevat de Y-as het aantal gebruikerspostvakken in elk opslagquotum.  <br/>  De X-as in de grafieken Postvak en Opslag toont het geselecteerde datumbereik voor dit specifieke rapport.  <br/>  De X-as van de grafiek Quotum is de quotumcategorie.  <br/> |
|7.  <br/> |U grafieken filteren die u ziet door een item in de legenda te selecteren.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van het postvakgebruik op gebruikersniveau. U kunt extra kolommen aan de tabel toevoegen.  <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker.  <br/> **Weergavenaam** is de volledige naam van de gebruiker.  <br/> **Verwijderd** verwijst naar een postvak waarvoor de huidige status Verwijderd is, maar dat een deel van de rapportageperiode van het rapport actief was.  <br/> **Verwijderd op** is de datum waarop het postvak is verwijderd.  <br/> **Datum maken** is de datum waarop het postvak is gemaakt.  <br/> **Laatste activiteitsdatum** is de laatste datum waarop via het postvak een e-mailbericht is verzenden of gelezen.  <br/> **Aantal items** verwijst naar het totale aantal items in het postvak.  <br/> **Opslagruimte gebruikt (MB)** verwijst naar de totale gebruikte opslagruimte.  <br/> **Het aantal verwijderde objecten** verwijst naar het totale aantal verwijderde items in het postvak. <br/> **De verwijderde objectgrootte (MB)** verwijst naar de totale grootte van alle verwijderde items in het postvak. <br/> **Quotum Waarschuwing geven (MB)** verwijst naar de opslaglimiet wanneer de eigenaar van het postvak een waarschuwing ontvangt dat het opslagquotum bijna is bereikt.  <br/> **Quotum Verzenden blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden.  <br/> **Quotum Verzenden/ontvangen blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden of ontvangen.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de **gebruikersgegevens verbergen in de** sectie Rapporten in de [activiteitenrapporten in het Microsoft 365-beheercentrum](activity-reports.md).  <br/> |
|9.  <br/> |U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren.  <br/> |
|||
   

