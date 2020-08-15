---
title: Adreslijstsynchronisatie uitschakelen voor Microsoft 365
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
ms.openlocfilehash: 0bd8591f91dcf20cb1061b3cd93f69511027bab1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688920"
---
# <a name="turn-off-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="49931-103">Adreslijstsynchronisatie uitschakelen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="49931-103">Turn off directory synchronization for Microsoft 365</span></span>
<span data-ttu-id="49931-104">U kunt PowerShell gebruiken om adreslijstsynchronisatie uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="49931-104">You can use PowerShell to turn off directory synchronization.</span></span> <span data-ttu-id="49931-105">U wordt echter niet aangeraden om adreslijstsynchronisatie uit te schakelen als stap bij probleemoplossing.</span><span class="sxs-lookup"><span data-stu-id="49931-105">However, it is not recommended that you turn off directory synchronization as a troubleshooting step.</span></span> <span data-ttu-id="49931-106">Als u hulp nodig hebt bij het oplossen van problemen met adreslijstsynchronisatie, raadpleegt u het artikel [problemen oplossen met adreslijstsynchronisatie voor Microsoft 365](fix-problems-with-directory-synchronization.md) .</span><span class="sxs-lookup"><span data-stu-id="49931-106">If you need assistance with troubleshooting directory synchronization, see the [Fixing problems with directory synchronization for Microsoft 365](fix-problems-with-directory-synchronization.md) article.</span></span> 
  
<span data-ttu-id="49931-107">[Contact opnemen met ondersteuning](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) voor bedrijfsproducten, indien nodig.</span><span class="sxs-lookup"><span data-stu-id="49931-107">[Contact support](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) for business products if needed.</span></span>
  
## <a name="turn-off-directory-synchronization"></a><span data-ttu-id="49931-108">Adreslijstsynchronisatie uitschakelen</span><span class="sxs-lookup"><span data-stu-id="49931-108">Turn off directory synchronization</span></span>  
<span data-ttu-id="49931-109">Adreslijstsynchronisatie uitschakelen:</span><span class="sxs-lookup"><span data-stu-id="49931-109">To turn off Directory synchronization:</span></span>
  
1. <span data-ttu-id="49931-110">Installeer eerst de vereiste software en maak verbinding met uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="49931-110">First, install the required software and connect to your Microsoft 365 subscription.</span></span> <span data-ttu-id="49931-111">Zie [verbinding maken met de Microsoft Azure Active Directory-module voor Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="49931-111">For instructions, see [Connect with the Microsoft Azure Active Directory Module for Windows PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>
    
2. <span data-ttu-id="49931-112">Gebruik [set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) om adreslijstsynchronisatie uit te schakelen:</span><span class="sxs-lookup"><span data-stu-id="49931-112">Use [Set-MsolDirSyncEnabled](https://go.microsoft.com/fwlink/p/?LinkId=821939) to disable directory synchronization:</span></span> 
    
  ```powershell
  Set-MsolDirSyncEnabled -EnableDirSync $false
  ```

>[!Note]
><span data-ttu-id="49931-113">Als u deze opdracht gebruikt, moet u 72 uur wachten voordat u adreslijstsynchronisatie weer kunt inschakelen.</span><span class="sxs-lookup"><span data-stu-id="49931-113">If you use this command, you must wait 72 hours before you can turn directory synchronization back on.</span></span>
>
 
