---
title: Een verwijderde Microsoft 365-groep herstellen
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Lees hoe u een verwijderde Microsoft 365-groep kunt herstellen.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753241"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Een verwijderde Microsoft 365-groep herstellen

Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard. Deze periode van 30 dagen wordt als ' zacht verwijderen ' beschouwd omdat u de groep toch kunt herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud permanent verwijderd en kunnen ze niet worden hersteld.

Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:
  
- Objecten, eigenschappen en leden van Azure Active Directory (AD) Microsoft 365 groepen.
    
- De e-mailadressen van de groep.
    
- Gedeeld postvak in en agenda van Exchange Online.
    
- Team site en bestanden van SharePoint Online.
    
- OneNote-notitieblok
    
- Planner
    
- Teams

- Inhoud van Yammer-groepen en-groepen (als de groep Microsoft 365 is gemaakt van Yammer)

> [!NOTE]
> In dit artikel wordt beschreven hoe u alleen Microsoft 365 groepen herstelt. Alle overige groepen kunnen na verwijdering niet worden hersteld.

## <a name="restore-a-group"></a>Een groep herstellen

# <a name="outlook"></a>[Outlook](#tab/outlook)

Als u de eigenaar bent van een Microsoft 365-groep, kunt u de groep zelf herstellen in de webversie van Outlook door de volgende stappen uit te voeren:

1. Selecteer op de [pagina verwijderde groepen](https://outlook.office.com/people/group/deleted)de optie **groepen beheren** onder het knooppunt **groepen** en kies vervolgens **verwijderen**.

2. Klik op het tabblad **herstellen** naast de groep die u wilt herstellen.

Neem contact op met een beheerder als de verwijderde groep hier niet wordt weergegeven.

# <a name="admin-center"></a>[Beheercentrum](#tab/admin-center)

Als u een globale beheerder of een groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365-Beheercentrum:

1. Ga naar het [Beheercentrum](https://admin.microsoft.com).
2. Vouw **groepen**uit en klik vervolgens op **Verwijderde groepen**.
3. Selecteer de groep die u wilt herstellen en klik op **groep herstellen**.

> [!NOTE]
> In sommige gevallen kan het tot 24 uur duren voordat de groepsgegevens worden hersteld. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Hebt u vragen over Microsoft 365-groepen?

Bezoek de [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) voor het plaatsen van vragen en deelnemen aan gesprekken over microsoft 365 groepen. 
  
## <a name="related-articles"></a>Verwante artikelen

[Microsoft 365-groepen beheren met PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Delete groups using the Remove-UnifiedGroup cmdlet](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx) (Groepen verwijderen met de cmdlet Remove-UnifiedGroup)
  
[De teamsite-instellingen beheren die aan de groep zijn gekoppeld](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Een groep verwijderen in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
