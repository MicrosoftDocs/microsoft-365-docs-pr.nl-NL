---
title: Adreslijstsynchronisatie voor Microsoft 365 uitschakelen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: ee5f861e-bd48-4267-83d1-a4ead4b4a00d
description: In dit artikel vindt u informatie over het gebruik van PowerShell om adreslijstsynchronisatie voor Microsoft 365 uit te schakelen.
ms.openlocfilehash: 036130b70382e28ad9d8cb10786ad5e266375c20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909308"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="3f9f6-103">Adreslijstsynchronisatie voor Microsoft 365 uitschakelen</span><span class="sxs-lookup"><span data-stu-id="3f9f6-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="3f9f6-104">U kunt PowerShell gebruiken om adreslijstsynchronisatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="3f9f6-105">Het wordt echter afgeraden om adreslijstsynchronisatie uit te schakelen als een stap voor het oplossen van problemen.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="3f9f6-106">Zie het artikel Problemen oplossen met adreslijstsynchronisatie voor [Microsoft 365](fix-problems-with-directory-synchronization.md) als u hulp nodig hebt bij het oplossen van adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="3f9f6-107">[Neem indien nodig contact](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) op met de ondersteuning voor zakelijke producten.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="3f9f6-108">Adreslijstsynchronisatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="3f9f6-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="3f9f6-109">Adreslijstsynchronisatie uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="3f9f6-110">Installeer eerst de vereiste software en maak verbinding met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="3f9f6-111">Zie Verbinding maken [met de Microsoft Azure Active Directory-module voor Windows PowerShell voor instructies.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="3f9f6-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="3f9f6-112">[Set-MsolDirSyncEnabled gebruiken om](/previous-versions/azure/dn194097(v=azure.100)) adreslijstsynchronisatie uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="3f9f6-112">Use [Set-MsolDirSyncEnabled](/previous-versions/azure/dn194097(v=azure.100)) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="3f9f6-113">Als u deze opdracht gebruikt, moet u 72 uur wachten voordat u adreslijstsynchronisatie weer kunt in- en uit- zetten.</span><span class="sxs-lookup"><span data-stu-id="3f9f6-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
