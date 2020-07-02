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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: c2ce12a2-934f-4dd4-ba65-49b02be4703d
description: Meer informatie over hoe u het gebruiksrapport van e-mailapps op de hoogte krijgt van e-mailapps die verbinding maken met Exchange Online en de Outlook-versie die gebruikers gebruiken.
ms.openlocfilehash: bfd8a911652283685486202203d0302479a8270e
ms.sourcegitcommit: 634abe8a237e27dfe82376e6ef32280aab5d4a27
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/01/2020
ms.locfileid: "45005753"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps

Het dashboard Microsoft **365-rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). In het gebruiksrapport voor e-mailapps u zien hoeveel e-mailapps verbinding maken met Exchange Online. Daarnaast kunt u de versiegegevens bekijken van Outlook-apps die gebruikers gebruiken, zodat u weet welke personen niet-ondersteunde versies gebruiken en contact met ze kunt opnemen om ondersteunde versies van Outlook te installeren.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportlezer zijn in Microsoft 365 of een Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven-beheerder om rapporten te kunnen bekijken.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Hoe u naar het rapport e-mailapps gaan

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **Een rapport selecteren** het gebruik van **Exchange** \> **Exchange-e-mail-app**.
  
## <a name="interpret-the-email-apps-report"></a>Het rapport e-mailapps interpreteren

U een overzicht krijgen van de activiteit van e-mailapps door de grafieken **Gebruikers** en **clients te** bekijken. 
  
![E-mailclients gebruikt](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|||
|:-----|:-----|
|1.  <br/> |Het **gebruiksrapport voor e-apps** kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven gedurende maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |In de weergave **Gebruikers** ziet u het aantal unieke gebruikers dat met een willekeurige e-mail-app is verbonden met Exchange Online.  <br/> |
|4.  <br/> |In de weergave **Apps** ziet u het aantal unieke gebruikers per app in de geselecteerde periode.  <br/> |
|5.  <br/> |**In de** weergave Versies ziet u het aantal unieke gebruikers voor elke versie van Outlook in Windows.  <br/> |
|6.  <br/> | In de grafiek **Gebruikers** is de Y-as het totale aantal unieke gebruikers dat op een willekeurige dag van de rapportageperiode is verbonden met een app.  <br/>  In de grafiek **Gebruikers** is de X-as het aantal unieke gebruikers dat die app voor die rapportageperiode heeft gebruikt.  <br/>  In de grafiek **Apps** is de Y-as het totale aantal unieke gebruikers dat gedurende de rapportageperiode een specifieke app heeft gebruikt.  <br/>  In de grafiek **Apps** is de X-as de lijst met apps in uw organisatie.  <br/>  In de grafiek **Versies** is de Y-as het totale aantal unieke gebruikers dat een specifieke versie van de bureaubladversie van Outlook gebruikt. Als het rapport het versienummer van Outlook niet kan oplossen, wordt het aantal weergegeven als **Onbepaald.**  <br/>  In de grafiek **Versies** is de X-as de lijst met apps in uw organisatie.  <br/> |
|7.  <br/> |U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Gebruikers** De optie **Mac-e-mail** of **Outlook** ![ Outlook-lijst met e-mailclients. Selecteer de e-mailclient om meer rapportagegegevens over die client te krijgen.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) om alleen de informatie te zien die betrekking heeft op elk van die gebruikers. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet. Mac Mail, Outlook voor Mac, Outlook Mobile, de bureaubladversie van Outlook en de webversie van Outlook zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/> |
|8.  <br/> | Mogelijk worden de items in de onderstaande lijst pas weergegeven als u ze toevoegt.<br/> **Gebruikersnaam** is de naam van de eigenaar van de e-mailapp.  <br/> **Laatste activiteitsdatum** is de laatste datum waarop de gebruiker een e-mailbericht heeft gelezen of verzonden.  <br/> **Mac Mail**, **Outlook voor Mac**, **Outlook**, **Outlook Mobile** en de **webversie van Outlook** zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de sectie **Hoe verberg ik details op gebruikersniveau?** [Activity Reports in the Microsoft 365 admin center](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen beheren** om kolommen uit het rapport toe te voegen of te verwijderen.  <br/> ![Gebruiksrapport E-mailapps - kies kolommen](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |U de rapportgegevens ook exporteren naar een Excel .csv-bestand door de koppeling **Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   
