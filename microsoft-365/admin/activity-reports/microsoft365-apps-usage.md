---
title: Microsoft 365-rapporten in het beheercentrum - Gebruik van Microsoft 365-apps
ms.author: sirkkuw
author: sirkkuw
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
description: Meer informatie over het downloaden van een rapport over Microsoft 365 Apps voor gebruik met het dashboard Microsoft 365 Rapporten in het Microsoft 365-beheercentrum.
ms.openlocfilehash: eb8978c878b2356c8fe73cb0f9f0021b65fcc333
ms.sourcegitcommit: b8a9994b26a6d9865212f5b1871286e719d1608e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2020
ms.locfileid: "43781437"
---
# <a name="microsoft-365-reports-in-the-admin-center---microsoft-365-apps-usage"></a>Microsoft 365-rapporten in het beheercentrum - Gebruik van Microsoft 365-apps

Het dashboard Microsoft 365 **Rapporten** toont u het activiteitenoverzicht voor de producten in uw organisatie. U kunt inzoomen op rapporten op het niveau van afzonderlijke producten om een gedetailleerder inzicht te krijgen in de activiteiten binnen elk product. Bekijk [het overzichtsonderwerp over rapporten](activity-reports.md).

 U bijvoorbeeld inzicht krijgen in de activiteit van elke gebruiker die een licentie heeft om Microsoft 365 Apps-apps te gebruiken door te kijken naar hun activiteiten in de apps en hoe deze op verschillende platforms worden gebruikt.


 > [!NOTE]
 > U moet een globale beheerder, wereldwijde lezer of rapportenlezer zijn in Microsoft 365 of een Exchange-, SharePoint- of Skype voor Bedrijven-beheerder om rapporten te bekijken.

## <a name="how-to-get-to-the-microsoft-365-apps-usage-report"></a>Het gebruiksrapport van Microsoft 365 Apps

1. Ga in het beheercentrum naar de pagina **Rapporten** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Gebruik</a>.

 2. Selecteer office **365** \> **Microsoft 365 Apps-gebruik** in de vervolgkeuzelijst **Een rapport** selecteren .

## <a name="interpret-the-microsoft-365-apps-usage-report"></a>Het gebruiksrapport van Microsoft 365 Apps interpreteren

U een overzicht krijgen van de Microsoft 365 Apps-activiteit van uw gebruiker door te kijken naar de grafieken **Gebruikers** en **Platform.**

![Gebruiksrapport microsoft 365-apps](../../media/proplususagenumbers.png)

|||
 |:-----|:-----|
 |1. <br/> |Het **gebruiksrapport van Microsoft 365 Apps** kan worden bekeken voor trends in de afgelopen 7 dagen, 30 dagen, 90 dagen of 180 dagen. Als u echter een bepaalde dag in het rapport selecteert, worden in de tabel (7) gegevens weergegeven voor maximaal 28 dagen vanaf de huidige datum (niet de datum waarop het rapport is gegenereerd). <br/> |
 |2. <br/> |De gegevens in elk rapport bestrijken meestal tot de laatste 24 tot 48 uur. <br/> |
 |3. <br/> |De weergave **Gebruikers** toont de trend in het aantal actieve gebruikers voor elke app: Outlook, Word, Excel, PowerPoint, OneNote en Teams. "Actieve gebruikers" zijn iedereen die opzettelijke acties binnen deze apps uitvoert. <br/> |
 |4. <br/> |De weergave **Platforms** toont de trend van actieve gebruikers in alle apps voor elk platform : Windows, Mac, Web en Mobile. <br/> |
 |5.<br/>|In de grafiek **Gebruikers** is de Y-as het aantal unieke actieve gebruikers voor de desbetreffende app. Op de grafiek **Platforms** is de Y-as het aantal unieke gebruikers voor het betreffende platform. X-as op beide grafieken is de datum waarop een app werd gebruikt op een bepaald platform.rm.<br/>|
 6.<br/>|U de reeks die u in de grafiek ziet filteren door een item in de legenda te selecteren. Selecteer bijvoorbeeld in de grafiek **Gebruikers** Outlook, Word, Excel, PowerPoint, OneDrive of Teams om alleen de gegevens te bekijken die betrekking hebben op elke grafiek. Als u deze selectie wijzigt, wordt de informatie in de rastertabel eronder niet gewijzigd.|
 |7.<br/>|De tabel toont een uitsplitsing van de gegevens per gebruiker. U kunt kolommen toevoegen aan of verwijderen uit de tabel. <br/><br/>**Gebruikersnaam** is het e-mailadres van de gebruiker die de activiteit in Microsoft Apps heeft uitgevoerd.<br><br/>**Laatste activeringsdatum (UTC)** is de laatste datum waarop de gebruiker zijn Microsoft 365 Apps-abonnement heeft geactiveerd.<br/><br/>**Laatste activiteitsdatum (UTC)** is de laatste datum waarop een opzettelijke activiteit door de gebruiker is uitgevoerd. Als u de activiteit van een bepaalde datum wilt zien, selecteert u de datum rechtstreeks in de grafiek.<br/><br/>Volg kolommen die overeenkomen met elke app die aangeeft of de gebruiker actief was in die app in de geselecteerde periode:<br> <br>**Outlook** <br>**Word** <br>**Excel**<br>**PowerPoint** <br>**OneNote**<br><br> Volg kolommen die overeenkomen met elk platform die identificeert of de gebruiker actief was op dat platform voor een app (binnen Microsoft 365 Apps) in de geselecteerde periode:<br><br>**Outlook (Windows)**<br>**Outlook (Mac)**<br>**Outlook (web)** <br>**Outlook (mobiel)**<br> **Word (Windows)**<br> **Woord (Mac)**<br> **Word (web)**<br> **Word (mobiel)**<br> **Excel (Windows)**<br> **Excel (Mac)**<br> **Excel (web)**<br> **Excel (mobiel)**<br> **PowerPoint (Windows)**<br> **PowerPoint (Mac)**<br>**PowerPoint (web)**<br> **PowerPoint (mobiel)**<br> **OneNote (Windows)**<br> **OneNote (Mac)**<br> **OneNote (web)**<br>**OneNote (mobiel)**<br> **Teams (Windows)**<br> **Teams (Mac)**<br> **Teams (web)**<br>**Teams (Mobiel)** |
 |8.<br/>|Selecteer het pictogram **Kolommen beheren** om kolommen toe te voegen of te verwijderen uit het rapport.|
 |9.<br/>|U de rapportgegevens ook exporteren naar een CSV-bestand in Excel door de koppeling **Exporteren te** selecteren. Hiermee worden gegevens voor alle gebruikers geëxporteerd en u eenvoudig aggregatie, sortering en filtering uitvoeren voor verdere analyse. Als u minder dan 100 gebruikers hebt, u sorteren en filteren in de tabel in het rapport zelf. Als u meer dan 100 gebruikers hebt, moet u de gegevens exporteren om te filteren en te sorteren.|