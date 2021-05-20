---
title: Een verwijderde Microsoft 365 herstellen
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
description: Een verwijderde groep blijft 30 dagen behouden en u kunt de groep nog steeds herstellen. Na 30 dagen worden de groep en de inhoud ervan definitief verwijderd.
ms.openlocfilehash: 285796ec45b1e6d77d46d7a0c39706f566bb8cf6
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582678"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Een verwijderde Microsoft 365 herstellen

Als u een groep hebt verwijderd, wordt deze standaard 30 dagen bewaard. Deze periode van 30 dagen wordt beschouwd als een 'soft-delete' omdat u de groep nog steeds kunt herstellen. Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kan deze niet meer worden hersteld.

Wanneer een groep wordt hersteld, wordt de volgende inhoud hersteld:
  
- Azure Active Directory (AD) Microsoft 365 Groepen object, eigenschappen en leden.
    
- E-mailadressen van de groep.
    
- Exchange Online gedeeld Postvak IN en agenda.
    
- SharePoint Online teamsite en bestanden.
    
- OneNote-notitieblok
    
- Planner
    
- Teams

- Yammer groeps- en groepsinhoud (Als de Microsoft 365 groep is gemaakt op Yammer)

> [!NOTE]
> In dit artikel wordt het herstellen van alleen Microsoft 365 beschreven. Alle andere groepen kunnen niet worden hersteld nadat ze zijn verwijderd.

## <a name="restore-a-group"></a>Een groep herstellen

# <a name="outlook"></a>[Outlook](#tab/outlook)

Als u de eigenaar bent van een Microsoft 365 groep, kunt u de groep zelf herstellen in Outlook web door de volgende stappen uit te voeren:

1. Selecteer op [de pagina Verwijderde](https://outlook.office.com/people/group/deleted)groepen de  optie Groepen **beheren** onder het knooppunt Groepen en kies **vervolgens Verwijderd.**

2. Klik op het **tabblad** Herstellen naast de groep die u wilt herstellen.

Als de verwijderde groep hier niet wordt weergegeven, neemt u contact op met een beheerder.

# <a name="admin-center"></a>[Beheercentrum](#tab/admin-center)

Als u een globale beheerder of een groepsbeheerder bent, kunt u een verwijderde groep herstellen in het Microsoft 365 beheercentrum:

1. Ga naar het [beheercentrum.](https://admin.microsoft.com)
2. Vouw **Groepen** uit en klik vervolgens **op Verwijderde groepen.**
3. Selecteer de groep die u wilt herstellen en klik vervolgens op **Groep herstellen.**

> [!NOTE]
> In sommige gevallen kan het 24 uur duren voordat de groep en alle gegevens zijn hersteld. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Hebt u vragen over Microsoft 365 Groepen?

Ga naar [de Microsoft Tech Community om](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) vragen te posten en deel te nemen aan gesprekken over Microsoft 365 groepen. 
  
## <a name="related-content"></a>Verwante inhoud

[Groepen Microsoft 365 beheren met PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md) (artikel)
  
[Groepen verwijderen met de Remove-UnifiedGroup cmdlet](/powershell/module/exchange/remove-unifiedgroup) (artikel)
  
[Uw teamsite-instellingen met een groep beheren](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42) (artikel)
  
[Een groep verwijderen in Outlook](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f) (artikel)