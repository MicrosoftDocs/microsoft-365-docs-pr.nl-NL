---
title: Microsoft 365-rapporten in het Beheercentrum-Microsoft 365-groepen
ms.author: sirkkuw
author: Sirkkuw
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
ms.assetid: a27f1a99-3557-4f85-9560-a28e3d822a40
description: Vraag een Microsoft 365-groepsrapport om te weten over de groepen en hun activiteiten.
ms.openlocfilehash: 1d329efa4fe7cdf12b6c7452b6480d237fb3d5c1
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948986"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-groups"></a>Microsoft 365-rapporten in het Beheercentrum-Microsoft 365-groepen

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). In het rapport Microsoft 365-groepen kunt u inzicht krijgen in de activiteiten van de groepen in uw organisatie en zien hoeveel groepen er worden gemaakt en gebruikt.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
  
## <a name="how-to-get-to-the-groups-report"></a>Naar het rapportgroepen gaan

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **Office 365** \> **groepen-activiteit**.
  
## <a name="interpret-the-groups-report"></a>Het groepsrapport interpreteren

U krijgt inzicht in de groepsactiviteit door te kijken naar de grafieken **groepen**, **activiteit**, **bestanden**en **opslag** . 
  
![Microsoft 365-rapporten-groepsactiviteiten](../../media/852027a4-8eab-47d1-b770-2bb874bdc403.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |Het rapport **Microsoft 365-groepen** kan worden bekeken om trends te zien over de laatste 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |In de weergave **groepen** ziet u het totale aantal groepen dat op een bepaalde dag bestaat, en de actieve groepen op die dag op basis van e-mail gesprekken, Yammer-berichten en SharePoint-bestanden en SharePoint-pagina's weergegeven.  <br/> |
|4.  <br/> |In de weergave **Activiteit** ziet u het aantal groepsactiviteiten voor groepswerkbelastingen. U kunt voor een willekeurige dag tijdens de rapportageperiode de Exchange-e-mails bekijken die in de postvakken van alle groepen zijn ontvangen. U kunt ook berichten weergeven die zijn gepost, gelezen en leuk vinden in de Yammer-groepen die zijn gekoppeld aan een groep. <br/> |
|5.  <br/> |In de weergave **bestanden** ziet u het totale aantal en het aantal actieve bestanden voor alle groeps sites die zijn gekoppeld aan een groep.  <br/> |
|zes.  <br/> |In de weergave **Opslag** ziet u voor alle groepspostvakken en groepssites de totale opslagruimte die wordt gebruikt.  <br/> |
|7,5.  <br/> | Op de grafiek **Groepen** is de y-as het aantal groepen (dat kan worden gezien als totaal of actief).  <br/>  Op de grafiek **activiteit** is de Y-as het aantal keren dat een activiteit heeft plaatsgevonden in groepen.  <br/>  In de grafiek **Bestanden** is de Y-as het totale aantal bestanden of het aantal actieve bestanden.  <br/>  In de grafiek **Opslag** is de Y-as de totale opslagruimte die door het postvak of de site van de groep wordt gebruikt.  <br/>  De X-as in alle drie de grafieken toont het geselecteerde datumbereik voor het specifieke rapport.  <br/> |
|8:00.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek **groepen** de optie **totaal** of **actief** ![ totaal en actief aantal groepen ](../../media/8eebd496-5955-4419-8d53-5f3ba1ad1c88.png) om alleen de gegevens weer te geven die betrekking hebben op een groep. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet.  <br/> |
|aanhaling.  <br/> | Welke lijst met groepen wordt weergegeven, wordt bepaald door de reeks groepen die bestond (niet zijn verwijderd) in de ruimste rapportageperiode (180 dagen). Het aantal activiteiten (e-mailgesprekken, Yammer-berichten en SharePoint-bestandsactiviteiten) is afhankelijk van de datumselectie.  <br/> Opmerking: u kunt alle items in de onderstaande lijst in de kolommen niet zien totdat u ze toevoegt.<br/>**Groepsnaam** is de naam van de groep.  <br/> **Verwijderd** is het aantal verwijderde groepen. Als de groep wordt verwijderd maar voor de groep activiteiten zijn uitgevoerd in de rapportageperiode, wordt de groep weergegeven in het raster waarbij deze vlag wordt ingesteld op 'waar'.  <br/> **Groepseigenaar** is de naam van de eigenaar van de groep.  <br/> **Datum van laatste activiteit** is de datum waarop voor het laatst een bericht is ontvangen door de groep. Dit is de meest recente datum waarop een activiteit heeft plaatsgevonden in een e-mailgesprek, Yammer of de Site.  <br/> **Type** is het type groep. Dit kan een persoonlijke of openbare groep zijn.  <br/> **Leden** is het aantal leden in de groep.  <br/> **Externe leden** is het aantal externe gebruikers in de groep.  <br/> **Exchange** <br/> **Ontvangen e-mails** is het aantal berichten dat door de groep is ontvangen.  <br/> **Totaal aantal items in postvak** is het totaal aantal items in het postvak van de groep.  <br/> **Gebruikte opslagruimte postvak** is de opslagruimte die wordt gebruikt door het postvak van de groep.  <br/> **SharePoint-bestanden** <br/> **Totaal aantal bestanden** is het aantal bestanden dat is opgeslagen op sites van SharePoint-groepen.  <br/> **Actieve bestanden** is het aantal bestanden in de SharePoint-groepssite waarvoor acties hebben plaatsgevonden (zijn bekeken of gewijzigd, gesynchroniseerd, intern of extern gedeeld) tijdens de rapportageperiode  <br/> **Gebruikte site-opslagruimte (MB)** is de hoeveelheid opslagruimte in MB die tijdens de rapportageperiode is gebruikt.  <br/> **Yammer-berichten** <br/> **Gepost** is het aantal berichten dat gedurende de rapportageperiode is gepost in de Yammer-groep.  <br/> **Gelezen** is het aantal gesprekken dat gedurende de rapportageperiode is gelezen in de Yammer-groep.  <br/> **Leuk gevonden** is het aantal berichten dat gedurende de rapportageperiode is leuk gevonden in de Yammer-groep.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|10  <br/> |Selecteer of tik op de knop **meer acties** op de knop meer acties ![ ](../../media/80044eef-2368-4c7e-8d31-7155b029e0cf.png) naast een kolomkop om kolommen toe te voegen aan of te verwijderen uit het rapport.  <br/> ![Groepsrapport-kolommen kiezen](../../media/d7fb95d6-2a2e-4144-b80d-581223e48043.png)|
|23:00  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

