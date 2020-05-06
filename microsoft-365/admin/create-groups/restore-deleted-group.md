---
title: Een verwijderde groep herstellen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Meer informatie over het herstellen van een verwijderde Microsoft 365-groep.
ms.openlocfilehash: 870db3c92cd1f28f91540633a1dce9d0353c2b87
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049153"
---
# <a name="restore-a-deleted-group"></a>Een verwijderde groep herstellen

Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard. Deze periode van 30 dagen wordt beschouwd als een soft-delete omdat u de groep nog steeds herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen ze niet worden hersteld.

Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:
  
- Het object, de eigenschappen en leden van Azure Active Directory (AD) Microsoft 365-groepen.
    
- de e-mailadressen van de groep.
    
- Exchange Online heeft Postvak IN en agenda gedeeld.
    
- SharePoint Online-teamsite en -bestanden.
    
- OneNote-notitieblok
    
- Planner
    
- Teams

- Yammer-groep en groepsinhoud (Als de Microsoft 365-groep is gemaakt vanuit Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Een groep herstellen waarvan u eigenaar bent met Outlook

Als u eigenaar bent van een Microsoft 365-groep, u de groep zelf herstellen in Outlook door de volgende stappen te volgen:

1. Selecteer op de [pagina verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie Groepen **beheren** onder het knooppunt **Groepen** en kies **Vervolgens Verwijderd**.

2. Klik op het tabblad **Herstellen** naast de groep die u wilt herstellen.

Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Een groep herstellen in het Microsoft 365-beheercentrum

Als u een globale beheerder of een groepsbeheerder bent, u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:

1. Ga naar het [beheercentrum](https://admin.microsoft.com).
2. Groepen **Groups**uitvouwen en vervolgens op **Verwijderde groepen**klikken .
3. Selecteer de groep die u wilt herstellen en klik op **Groep herstellen**.
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Een Microsoft 365-groep definitief verwijderen

Soms wilt u een groep permanent zuiveren zonder te wachten tot de periode voor het verwijderen van 30 dagen is verlopen. Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:
  
```
Get-AzureADMSDeletedGroup
```

Let op de object-id van de groep of groepen die u permanent wilt verwijderen.
  
> [!CAUTION]
> Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld. 
  
Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Heb je vragen over Microsoft 365-groepen?

Ga naar de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) om vragen te plaatsen en deel te nemen aan gesprekken over Microsoft 365-groepen. 
  
## <a name="related-articles"></a>Verwante artikelen

[Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)
  
[De teamsite-instellingen beheren die aan de groep zijn gekoppeld](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Een groep verwijderen in Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
