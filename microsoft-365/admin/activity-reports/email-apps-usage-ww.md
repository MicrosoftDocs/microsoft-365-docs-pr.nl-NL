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
description: Lees hoe u een rapport over het gebruik van e-mailapps krijgt om te weten te komen over e-mailapps die verbinding maken met Exchange Online en de Outlook-versie die gebruikers gebruiken.
ms.openlocfilehash: f2a7b79a00b47896dac4427c532f85dccb931c60
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921951"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van e-mailapps

Het Dashboard Microsoft 365 **Rapporten** toont een overzicht van de activiteiten voor alle producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). In het gebruiksrapport voor e-mail-apps kunt u zien hoeveel e-mailapps verbinding maken met Exchange Online. Daarnaast kunt u de versiegegevens bekijken van Outlook-apps die gebruikers gebruiken, zodat u weet welke personen niet-ondersteunde versies gebruiken en contact met ze kunt opnemen om ondersteunde versies van Outlook te installeren.
  
> [!NOTE]
> U moet een globale beheerder, globale lezer of rapportenlezer in Microsoft 365 of een beheerder van Exchange, SharePoint, Teams Service, Teams Communications of Skype voor Bedrijven zijn om rapporten te kunnen zien.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Hoe u naar het rapport met e-mail-apps gaat

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.
2. Selecteer **Meer weergeven onder** **E-mailactiviteit.** 
3. Selecteer in **de vervolgkeuzelijst** E-mailactiviteit het **gebruik van** \> **Exchange-e-mailapps.**
  
## <a name="interpret-the-email-apps-report"></a>Het rapport met e-mail-apps interpreteren

U krijgt inzicht in de activiteit van e-mail-apps door de **grafieken Gebruikers** en **Clients te** bekijken. 
  
![Gebruikte e-mail clients](../../media/d78af7db-2b41-4d37-8b6e-bc7e47edd1dd.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In **het gebruiksrapport voor** e-mail-apps kunnen trends worden bekeken voor de laatste 7, 30, 90 of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens voor een datum tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd) tonen.  <br/> |
|2.  <br/> |De gegevens in elk rapport zijn meestal tot de laatste 24 tot 48 uur bestrijkt.  <br/> |
|3.  <br/> |In de weergave **Gebruikers** ziet u het aantal unieke gebruikers dat met een willekeurige e-mail-app is verbonden met Exchange Online.  <br/> |
|4.  <br/> |In de weergave **Apps** ziet u het aantal unieke gebruikers per app in de geselecteerde periode.  <br/> |
|5.  <br/> |In **de weergave Versies** ziet u het aantal unieke gebruikers voor elke versie van Outlook in Windows.  <br/> |
|6.  <br/> | In de grafiek **Gebruikers** is de Y-as het totale aantal unieke gebruikers dat op een willekeurige dag van de rapportageperiode is verbonden met een app.  <br/>  In de grafiek **Gebruikers** is de X-as het aantal unieke gebruikers dat die app voor die rapportageperiode heeft gebruikt.  <br/>  In de grafiek **Apps** is de Y-as het totale aantal unieke gebruikers dat gedurende de rapportageperiode een specifieke app heeft gebruikt.  <br/>  In de grafiek **Apps** is de X-as de lijst met apps in uw organisatie.  <br/>  In de grafiek **Versies** is de Y-as het totale aantal unieke gebruikers dat een specifieke versie van de bureaubladversie van Outlook gebruikt. Als het versienummer van Outlook niet kan worden bepaald in het rapport, wordt Onbepaald voor de hoeveelheid **als onbepaald aangezien.**  <br/>  In de grafiek **Versies** is de X-as de lijst met apps in uw organisatie.  <br/> |
|7.  <br/> |U kunt de reeks filteren die u in de grafiek ziet door een item in de legenda te selecteren.  <br/> |
|8.  <br/> | Mogelijk worden de items in de onderstaande lijst pas weergegeven als u ze toevoegt.<br/> **Gebruikersnaam** is de naam van de eigenaar van de e-mailapp.  <br/> **Laatste activiteitsdatum** is de laatste datum waarop de gebruiker een e-mailbericht heeft gelezen of verzonden.  <br/> **Mac Mail**, **Outlook voor Mac**, **Outlook**, **Outlook Mobile** en de **webversie van Outlook** zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Bekijk de sectie **Hoe verberg ik gebruikersniveaudetails?** in de activiteitenrapporten [in het Microsoft 365-beheercentrum.](activity-reports.md)  <br/> |
|9.  <br/> |Selecteer **Kolommen kiezen om** kolommen toe te voegen aan of te verwijderen uit het rapport.  <br/> ![Gebruiksrapport voor e-mail-apps - kolommen kiezen](../../media/041bd6ff-27e8-409d-9608-282edcfa2316.png)|
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de **koppeling Exporteren te** selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   
