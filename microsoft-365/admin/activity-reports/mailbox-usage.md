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
description: Meer informatie over hoe u het rapport Postvakgebruik leert kennen over de activiteiten van de gebruikers met een gebruikerspostvak.
ms.openlocfilehash: 13a2d2382799052423300f72e8af0df1ca596bb6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904562"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-rapporten in het beheercentrum - Postvakgebruik

Het **rapport** Postvakgebruik bevat informatie over gebruikers met een gebruikerspostvak en het activiteitsniveau van elke gebruiker op basis van het e-mailbericht verzenden, lezen, afspraak maken, vergadering verzenden, vergadering accepteren, vergadering weigeren en vergaderactiviteit annuleren. Het rapport bevat ook informatie over hoeveel opslagruimte in beslag wordt genomen door elk gebruikerspostvak en hoeveel van die postvakken de opslagquota naderen. 
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange-, SharePoint-, Teams-, Teams-, Teams-, of Skype voor Bedrijven-beheerder om rapporten te kunnen zien. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Het gebruiksrapport verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Selecteer **Meer weergeven onder** **E-mailactiviteit.** 
3. Selecteer in **de vervolgkeuzelijst** E-mailactiviteit de optie  \> **Exchange-postvakgebruik.**

## <a name="interpret-the-mailbox-usage-report"></a>Het rapport Postvakgebruik interpreteren

U krijgt een overzicht van het **Postvakgebruik** in uw organisatie aan de hand van de grafieken **Postvak**, **Opslag** en **Quotum**. 
  
![Rapport Postvakgebruik](../../media/9f610e91-cbc1-4e59-b824-7b1ddd84b738.png)

|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Postvakgebruik** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel gegevens voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) weer te geven.  <br/> |
|2.  <br/> |De gegevens in elk rapport hebben meestal betrekking op de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De grafiek Postvak toont het totale aantal gebruikerspostvakken in uw organisatie en het totale aantal gebruikerspostvakken dat actief is op een bepaalde dag van de rapportageperiode. Een gebruikerspostvak wordt als actief beschouwd als er een e-mailbericht via het postvak is verzonden of gelezen, een afspraak is gemaakt of een vergadering is verzonden, geaccepteerd, afgewezen of geannuleerd.  <br/> |
|4.  <br/> |De grafiek **Opslag** toont de hoeveelheid gebruikte opslagruimte in uw organisatie. Opslagdiagram bevat geen archiefpostvakken. Zie Overzicht van onbeperkt archiveren [in Microsoft 365](../../compliance/unlimited-archiving.md)voor meer informatie over het automatisch uitbreiden van archivering.<br/> |
|5.  <br/> | De grafiek **Quotum** toont het aantal gebruikerspostvakken in elke quotumcategorie. Er zijn vier quotumcategorieën:  <br/>  Goed: het aantal gebruikers waarvoor de gebruikte opslagruimte onder het quotum voor Waarschuwing geven ligt.  <br/>  Waarschuwing: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Waarschuwing geven ligt, maar onder het quotum voor Verzenden blokkeren.  <br/>  Kan niet verzenden: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden blokkeren ligt, maar onder het quotum voor Verzenden/ontvangen blokkeren.  <br/>  Kan niet verzenden/ontvangen: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden/ontvangen blokkeren ligt.  <br/> |
|6.  <br/> | In de grafiek **Postvak** bevat de Y-as het aantal gebruikerspostvakken.  <br/>  In de grafiek **Opslag** bevat de Y-as de hoeveelheid opslagruimte die wordt gebruikt door gebruikerspostvakken in uw organisatie.  <br/>  In de grafiek **Quotum** bevat de Y-as het aantal gebruikerspostvakken in elk opslagquotum.  <br/>  De X-as in de grafieken Postvak en Opslag toont het geselecteerde datumbereik voor dit specifieke rapport.  <br/>  De X-as van de grafiek Quotum is de quotumcategorie.  <br/> |
|7.  <br/> |U kunt grafieken filteren die u ziet door een item in de legenda te selecteren.  <br/> |
|8.  <br/> | De tabel toont een onderverdeling van het postvakgebruik op gebruikersniveau. U kunt extra kolommen aan de tabel toevoegen.  <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker.  <br/> **Weergavenaam** is de volledige naam van de gebruiker.  <br/> **Verwijderd** verwijst naar een postvak waarvoor de huidige status Verwijderd is, maar dat een deel van de rapportageperiode van het rapport actief was.  <br/> **Verwijderd op** is de datum waarop het postvak is verwijderd.  <br/> **Datum maken** is de datum waarop het postvak is gemaakt.  <br/> **Laatste activiteitsdatum** is de laatste datum waarop via het postvak een e-mailbericht is verzenden of gelezen.  <br/> **Aantal items** verwijst naar het totale aantal items in het postvak.  <br/> **Opslagruimte gebruikt (MB)** verwijst naar de totale gebruikte opslagruimte.  <br/> **Verwijderd aantal items verwijst** naar het totale aantal verwijderde items in het postvak. <br/> **Verwijderde itemgrootte (MB)** verwijst naar de totale grootte van alle verwijderde items in het postvak. <br/> **Quotum Waarschuwing geven (MB)** verwijst naar de opslaglimiet wanneer de eigenaar van het postvak een waarschuwing ontvangt dat het opslagquotum bijna is bereikt.  <br/> **Quotum Verzenden blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden.  <br/> **Quotum Verzenden/ontvangen blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden of ontvangen.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de sectie **Gebruikersgegevens verbergen in de sectie** Rapporten in de [activiteitenrapporten in het Microsoft 365-beheercentrum.](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen kiezen** om kolommen toe te voegen of te verwijderen uit het rapport.  <br/> ![Rapport Postvakgebruik : kies kolommen](../../media/ea3d0b18-6ac6-41b0-9bb9-4844f040ea75.png)|
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling Exporteren **te** selecteren.  <br/> |
|||
