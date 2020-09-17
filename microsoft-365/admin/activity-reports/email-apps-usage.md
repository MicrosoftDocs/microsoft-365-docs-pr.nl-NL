---
title: Microsoft 365-rapporten in het Beheercentrum-gebruik van e-mail-apps
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
description: Meer informatie over het gebruik van het rapport e-mail-apps gebruiken om te weten te komen over e-mail-apps die verbinding maken met Exchange Online en de Outlook-versie gebruikers.
ms.openlocfilehash: c6ee72390f0b9e9ead0f07c41d64bf5b7264fc1b
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948242"
---
# <a name="microsoft-365-reports-in-the-admin-center---email-apps-usage"></a>Microsoft 365-rapporten in het Beheercentrum-gebruik van e-mail-apps

Het dashboard Microsoft 365 **rapporten** toont u het overzicht van de activiteiten in de producten van uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md). In het rapport gebruik van de e-mail-apps kunt u zien hoeveel e-mail-apps verbinding maken met Exchange Online. Daarnaast kunt u de versiegegevens bekijken van Outlook-apps die gebruikers gebruiken, zodat u weet welke personen niet-ondersteunde versies gebruiken en contact met ze kunt opnemen om ondersteunde versies van Outlook te installeren.
  
> [!NOTE]
> U moet een globale beheerder, algemene lezer of rapporten lezer zijn in Microsoft 365 of een Exchange-, SharePoint-, teams-service, teams-communicatie of Skype voor bedrijven-beheerder om rapporten te zien.  
 
## <a name="how-to-get-to-the-email-apps-report"></a>Naar het rapport met e-mail-apps gaan

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

    
2. Selecteer in de vervolgkeuzelijst **een rapport selecteren** de optie **Exchange** \> **-app gebruiken**.
  
## <a name="interpret-the-email-apps-report"></a>Het rapport met e-mail-apps interpreteren

U kunt inzicht krijgen in de activiteiten van de e-mailapps door de grafieken **gebruikers** en **cliënten** te bekijken. 
  
![Gebruikte e-mailclients](../../media/2a775e46-750f-4fa6-8197-de4b24614bd7.png)
  
|Item|Beschrijving|
|:-----|:-----|
|1.  <br/> |In het rapport **gebruik van e-mail-apps** kunnen trends worden weergegeven voor de laatste 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag selecteert in het rapport, worden in de tabel (7) gegevens weergegeven voor tot 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd).  <br/> |
|2.  <br/> |De gegevens in de rapporten liggen meestal binnen de laatste 24 tot 48 uur.  <br/> |
|3.  <br/> |In de weergave **Gebruikers** ziet u het aantal unieke gebruikers dat met een willekeurige e-mail-app is verbonden met Exchange Online.  <br/> |
|4.  <br/> |In de weergave **Apps** ziet u het aantal unieke gebruikers per app in de geselecteerde periode.  <br/> |
|5.  <br/> |In de weergave **versies** ziet u het aantal unieke gebruikers voor elke versie van Outlook in Windows.  <br/> |
|zes.  <br/> | In de grafiek **Gebruikers** is de Y-as het totale aantal unieke gebruikers dat op een willekeurige dag van de rapportageperiode is verbonden met een app.  <br/>  In de grafiek **Gebruikers** is de X-as het aantal unieke gebruikers dat die app voor die rapportageperiode heeft gebruikt.  <br/>  In de grafiek **Apps** is de Y-as het totale aantal unieke gebruikers dat gedurende de rapportageperiode een specifieke app heeft gebruikt.  <br/>  In de grafiek **Apps** is de X-as de lijst met apps in uw organisatie.  <br/>  In de grafiek **Versies** is de Y-as het totale aantal unieke gebruikers dat een specifieke versie van de bureaubladversie van Outlook gebruikt. Als het versienummer van Outlook niet kan worden omgezet in het rapport, wordt de hoeveelheid weergegeven als **onbepaald**.  <br/>  In de grafiek **Versies** is de X-as de lijst met apps in uw organisatie.  <br/> |
|7,5.  <br/> |U kunt de reeks die u in de grafiek ziet, filteren door een item te selecteren in de legenda. Selecteer bijvoorbeeld in de grafiek **gebruikers** de optie **Mac mail** of **Outlook** ![ lijst met e-mailclients. Selecteer de e-mailclient om meer rapportagegegevens te ontvangen op die klant.](../../media/19b9da1b-7b69-4a04-8527-38349f859e84.png) om alleen de informatie te zien die betrekking heeft op elk van die gebruikers. Door deze selectie te wijzigen, verandert de informatie in de rastertabel niet. Mac Mail, Outlook voor Mac, Outlook Mobile, de bureaubladversie van Outlook en de webversie van Outlook zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/> |
|8:00.  <br/> | Mogelijk worden de items in de onderstaande lijst pas weergegeven als u ze toevoegt.<br/> **Gebruikers** naam is de naam van de eigenaar van de e-mail app.  <br/> **Datum van laatste activiteit** is de laatste datum waarop de gebruiker een e-mailbericht heeft gelezen of verzonden.  <br/> **Mac Mail**, **Outlook voor Mac**, **Outlook**, **Outlook Mobile** en de **webversie van Outlook** zijn voorbeelden van e-mail-apps die in uw organisatie kunnen worden gebruikt.  <br/>  Als het beleid van uw organisatie verhindert dat u rapporten weergeeft waarin gebruikersgegevens kunnen worden geïdentificeerd, kunt u de privacy-instelling voor elk van deze rapporten wijzigen. Kijk eens naar de sectie **Hoe kan ik Details van gebruikersniveau verbergen?** in de [activiteitsrapporten in het Microsoft 365-Beheercentrum](activity-reports.md).  <br/> |
|aanhaling.  <br/> |Selecteer **kolommen beheren** als u kolommen wilt toevoegen aan of verwijderen uit het rapport.  <br/> ![Gebruiksrapport voor e-mail-apps-Kies kolommen](../../media/82008680-cd28ab00-9686-11ea-8692-b3d72117c20b.png)|
|10.  <br/> |U kunt de rapportgegevens ook exporteren naar een CSV-bestand van Excel door de koppeling **exporteren** te selecteren. Hiermee exporteert u de gegevens van alle gebruikers en kunt u eenvoudige sortering en filtering toepassen voor verdere analyse. Als u minder dan 2000 gebruikers hebt, kunt u de tabel in het rapport zelf sorteren en filteren. Als u meer dan 2000 gebruikers hebt, moet u de gegevens exporteren om te kunnen filteren en sorteren.  <br/> |
|||
   
