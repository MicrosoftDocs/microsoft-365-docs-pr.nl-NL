---
title: Microsoft 365-rapporten in het Beheercentrum-postvakgebruik
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
description: Meer informatie over het gebruik van het rapport postvak bijhouden voor de activiteiten van de gebruikers met een postvak van de gebruiker.
ms.openlocfilehash: 988f6e638e01cb5929e2ad9dd74e3d08f8e51c97
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561457"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Microsoft 365-rapporten in het Beheercentrum-postvakgebruik

Het **rapport postvakgebruik** biedt informatie over gebruikers met het postvak van een gebruiker en het niveau van de activiteit op basis van het e-mailbericht verzenden, lezen, afspraak maken, vergadering verzenden, vergadering accepteren, vergadering afwijzen en Vergader activiteit annuleren. Het rapport bevat ook informatie over hoeveel opslagruimte in beslag wordt genomen door elk gebruikerspostvak en hoeveel van die postvakken de opslagquota naderen. 
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Het gebruiksrapport verkrijgen

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Selecteer **meer weergeven** onder **actieve gebruikers: Microsoft 365-Services**. 
3. Selecteer in de vervolgkeuzelijst met **actieve gebruikers** de optie **Exchange** - \> **postvakgebruik**.

  
## <a name="interpret-the-mailbox-usage-report"></a>Het rapport Postvakgebruik interpreteren

U krijgt een overzicht van het **Postvakgebruik** in uw organisatie aan de hand van de grafieken **Postvak**, **Opslag** en **Quotum**. 
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **Postvakgebruik** kunnen trends worden weergegeven voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden de gegevens in de tabel weergegeven gedurende een periode van 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |De grafiek Postvak toont het totale aantal gebruikerspostvakken in uw organisatie en het totale aantal gebruikerspostvakken dat actief is op een bepaalde dag van de rapportageperiode. Een gebruikerspostvak wordt als actief beschouwd als er een e-mailbericht via het postvak is verzonden of gelezen, een afspraak is gemaakt of een vergadering is verzonden, geaccepteerd, afgewezen of geannuleerd.  <br/> |
|4.  <br/> |De grafiek **Opslag** toont de hoeveelheid gebruikte opslagruimte in uw organisatie. Het opslagschema bevat geen archief postvakken. Zie voor meer informatie over het automatisch uitbreiden van archivering een [overzicht van onbeperkt archivering in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving).<br/> |
|5.  <br/> | De grafiek **Quotum** toont het aantal gebruikerspostvakken in elke quotumcategorie. Er zijn vier quotumcategorieën:  <br/>  Goed: het aantal gebruikers waarvoor de gebruikte opslagruimte onder het quotum voor Waarschuwing geven ligt.  <br/>  Waarschuwing: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Waarschuwing geven ligt, maar onder het quotum voor Verzenden blokkeren.  <br/>  Kan niet verzenden: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden blokkeren ligt, maar onder het quotum voor Verzenden/ontvangen blokkeren.  <br/>  Kan niet verzenden/ontvangen: het aantal gebruikers waarvoor de gebruikte opslagruimte op of boven het quotum voor Verzenden/ontvangen blokkeren ligt.  <br/> |
|zes.  <br/> | In de grafiek **Postvak** bevat de Y-as het aantal gebruikerspostvakken.  <br/>  In de grafiek **Opslag** bevat de Y-as de hoeveelheid opslagruimte die wordt gebruikt door gebruikerspostvakken in uw organisatie.  <br/>  In de grafiek **Quotum** bevat de Y-as het aantal gebruikerspostvakken in elk opslagquotum.  <br/>  De X-as in de grafieken Postvak en Opslag toont het geselecteerde datumbereik voor dit specifieke rapport.  <br/>  De X-as van de grafiek Quotum is de quotumcategorie.  <br/> |
|7,5.  <br/> |U kunt grafieken die u ziet, filteren door een item te selecteren in de legenda.  <br/> |
|8:00.  <br/> | De tabel toont een onderverdeling van het postvakgebruik op gebruikersniveau. U kunt extra kolommen aan de tabel toevoegen.  <br/> **Gebruikersnaam** is het e-mailadres van de gebruiker.  <br/> **Weergavenaam** is de volledige naam van de gebruiker.  <br/> **Verwijderd** verwijst naar een postvak waarvoor de huidige status Verwijderd is, maar dat een deel van de rapportageperiode van het rapport actief was.  <br/> **Verwijderd op** is de datum waarop het postvak is verwijderd.  <br/> **Datum maken** is de datum waarop het postvak is gemaakt.  <br/> **Laatste activiteitsdatum** is de laatste datum waarop via het postvak een e-mailbericht is verzenden of gelezen.  <br/> **Aantal items** verwijst naar het totale aantal items in het postvak.  <br/> **Opslagruimte gebruikt (MB)** verwijst naar de totale gebruikte opslagruimte.  <br/> **Aantal verwijderde** items verwijst naar het totale aantal verwijderde items in het postvak. <br/> De grootte van de **Verwijderde items (MB)** verwijst naar de totale grootte van alle verwijderde items in het postvak. <br/> **Quotum Waarschuwing geven (MB)** verwijst naar de opslaglimiet wanneer de eigenaar van het postvak een waarschuwing ontvangt dat het opslagquotum bijna is bereikt.  <br/> **Quotum Verzenden blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden.  <br/> **Quotum Verzenden/ontvangen blokkeren (MB)** verwijst naar de opslaglimiet wanneer het postvak geen e-mailberichten meer kan verzenden of ontvangen.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Raadpleeg het gedeelte **Gebruikersgegevens verbergen in de sectie rapporten** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|aanhaling.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren.  <br/> |
|||
   
