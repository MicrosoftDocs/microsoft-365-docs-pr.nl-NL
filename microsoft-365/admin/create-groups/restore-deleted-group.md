---
title: Een verwijderde Office 365-groep herstellen
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
description: Meer informatie over het herstellen van een verwijderde Office 365-groep.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2020
ms.locfileid: "42810288"
---
# <a name="restore-a-deleted-office-365-group"></a>Een verwijderde Office 365-groep herstellen

Als u een groep hebt verwijderd, blijft deze standaard 30 dagen behouden. Deze periode van 30 dagen wordt beschouwd als een soft-delete, omdat u de groep nog steeds herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.

Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:
  
- Azure Active Directory (AD) Office 365 groepeert object, eigenschappen en leden.
    
- E-mailadressen van de groep.
    
- Exchange Online heeft Inbox en agenda gedeeld.
    
- SharePoint Online-teamsite en -bestanden.
    
- OneNote-notitieblok
    
- Planner
    
- Teams

- Yammer-groeps- en groepsinhoud (als de Office 365-groep is gemaakt vanuit Yammer)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Een groep herstellen die u bezit met Outlook

Als u de eigenaar bent van een Office 365-groep, u de groep zelf herstellen in Outlook door de volgende stappen te volgen:

1. Selecteer op de [pagina Verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie Groepen **beheren** onder het knooppunt **Groepen** en kies Vervolgens **Verwijderd**.
2. Klik op het tabblad **Herstellen** naast de groep die u wilt herstellen.

Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Een groep herstellen in het Microsoft 365-beheercentrum

Als u een globale beheerder of een groepsbeheerder bent, u een verwijderde groep herstellen in het Microsoft 365-beheercentrum:

1. Ga naar het beheercentrum via [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).
2. Groepen **Groups**uitvouwen en klik vervolgens op **Verwijderde groepen**.
3. Selecteer de groep die u wilt herstellen en klik op **Groep herstellen**.
  
## <a name="permanently-delete-an-office-365-group"></a>Een Office 365-groep permanent verwijderen

Soms wilt u een groep permanent verwijderen zonder te wachten tot de periode van 30 dagen soft-deletion is verstreken. Hiervoor start u PowerShell en voert u deze opdracht uit om de object-id van de groep op te vragen:
  
```
Get-AzureADMSDeletedGroup
```

Noteer de object-id van de groep of groepen die u permanent wilt verwijderen.
  
> [!CAUTION]
> Als u een groep permanent verwijdert, kunnen de groep en de bijbehorende gegevens niet meer worden hersteld. 
  
Voer deze opdracht uit in PowerShell om de groep permanent te verwijderen:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

U kunt controleren dat de groep definitief is verwijderd door de cmdlet  *Get-AzureADMSDeletedGroup*  opnieuw uit te voeren en te kijken of de groep niet meer wordt vermeld in de lijst met voorlopig verwijderde groepen. In sommige gevallen duurt het wel 24 uur voordat de groep en alle bijbehorende gegevens permanent zijn verwijderd. 
  
## <a name="got-questions-about-office-365-groups"></a>Hebt u vragen over Office 365 Groepen?

Ga naar de [Microsoft Tech-community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) om vragen te plaatsen en deel te nemen aan gesprekken over Office 365-groepen. 
  
## <a name="related-articles"></a>Verwante artikelen

[Manage Office 365 Groups with PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)
  
[De teamsite-instellingen beheren die aan de groep zijn gekoppeld](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Een groep verwijderen in Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
