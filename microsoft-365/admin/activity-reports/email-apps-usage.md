---
title: Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Meer informatie over het gebruiksrapport e-mailapps om te weten over e-mailapps die verbinding maken met Exchange Online en de Outlook-versie die gebruikers gebruiken.
ms.openlocfilehash: bb75b28e41de37d4f21acedd4705db71f6c2c303
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812477"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps

Het dashboard Microsoft 365 **Reports** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). In het gebruiksrapport van e-mailapps u zien hoeveel e-mailapps verbinding maken met Exchange Online. Daarnaast kunt u de versiegegevens bekijken van Outlook-apps die gebruikers gebruiken, zodat u weet welke personen niet-ondersteunde versies gebruiken en contact met ze kunt opnemen om ondersteunde versies van Outlook te installeren.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportenlezer in Microsoft 365 of een Exchange-, SharePoint- of Skype voor Bedrijven-beheerder zijn om rapporten te kunnen bekijken. 
 
## <a name="how-to-get-to-the-email-apps-report"></a>Het rapport e-mailapps ontvangen?

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **Een rapport selecteren** de optie Gebruik van **Exchange-e-mail-apps**. **Exchange** \>
  
## <a name="interpret-the-email-apps-report"></a>Het rapport e-mailapps interpreteren

U een overzicht krijgen van de activiteit van e-mailapps door de grafieken **gebruikers** en **clients** te bekijken. 
  
![E-mailclients die worden gebruikt](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |Het **gebruiksrapport e-mailapps** kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven gedurende maximaal 28 dagen na de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |In de weergave **Gebruikers** ziet u het aantal unieke gebruikers dat met een willekeurige e-mail-app is verbonden met Exchange Online.  <br/> |
|4.  <br/> |In de weergave **Apps** ziet u het aantal unieke gebruikers per app in de geselecteerde periode.  <br/> |
|5.  <br/> |In de weergave **Versies** ziet u het aantal unieke gebruikers voor elke versie van Outlook in Windows.  <br/> |
|6.  <br/> | In de grafiek **Gebruikers** is de Y-as het totale aantal unieke gebruikers dat op een willekeurige dag van de rapportageperiode is verbonden met een app.  <br/>  In de grafiek **Gebruikers** is de X-as het aantal unieke gebruikers dat die app voor die rapportageperiode heeft gebruikt.  <br/>  In de grafiek **Apps** is de Y-as het totale aantal unieke gebruikers dat gedurende de rapportageperiode een specifieke app heeft gebruikt.  <br/>  In de grafiek **Apps** is de X-as de lijst met apps in uw organisatie.  <br/>  In de grafiek **Versies** is de Y-as het totale aantal unieke gebruikers dat een specifieke versie van de bureaubladversie van Outlook gebruikt. Als het versienummer van Outlook niet kan worden bepaald in het rapport, wordt Onbepaald voor de hoeveelheid weergegeven.  <br/>  In de grafiek **Versies** is de X-as de lijst met apps in uw organisatie.  <br/> |
|7.  <br/> |U de reeksen die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in het diagram **Gebruikers** de optie **Mac-e-mail** of **Outlook-lijst** ![met e-mailclients. Selecteer de e-mailclient om meer rapportagegegevens over die client te ontvangen.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) om alleen de informatie te zien die betrekking heeft op elk van die gebruikers. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet. Mac Mail, Outlook voor Mac, Outlook Mobile, de bureaubladversie van Outlook en de webversie van Outlook zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/> |
|8.  <br/> | Mogelijk worden de items in de onderstaande lijst pas weergegeven als u ze toevoegt.<br/> **Gebruikersnaam** is de naam van de eigenaar van de e-mailapp.  <br/> **De laatste activiteitsdatum** is de laatste datum waarop de gebruiker een e-mailbericht heeft gelezen of verzonden.  <br/> **Mac Mail**, **Outlook voor Mac**, **Outlook**, **Outlook Mobile** en de **webversie van Outlook** zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de details van het **gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen** beheren om kolommen uit het rapport toe te voegen of te verwijderen.  <br/> ![Gebruiksrapport e-mailapps - kolommen kiezen](../../media/c17b2a5c-db41-474a-8334-0e5a621b2f16.png)|
|10.  <br/> |U de rapportgegevens ook exporteren naar een Csv-bestand van Excel door de koppeling **Exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   

