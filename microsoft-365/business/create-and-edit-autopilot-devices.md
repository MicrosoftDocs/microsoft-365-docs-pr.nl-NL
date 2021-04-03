---
title: AutoPilot-apparaten maken en bewerken
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met AutoPilot in Microsoft 365 Business Premium. U kunt een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 506ff44e3cb6656b19174e82688b5af141ea2b79
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578482"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="ddc64-104">AutoPilot-apparaten maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="ddc64-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="ddc64-105">Een lijst met apparaten uploaden</span><span class="sxs-lookup"><span data-stu-id="ddc64-105">Upload a list of devices</span></span>

<span data-ttu-id="ddc64-106">U kunt de [stapsgewijse handleiding gebruiken](add-autopilot-devices-and-profile.md) om apparaten te uploaden, maar u kunt ook apparaten uploaden op het **tabblad** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="ddc64-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="ddc64-107">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="ddc64-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="ddc64-108">Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="ddc64-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="ddc64-109">Nieuwe apparaten die niet out-of-box-ervaring met Windows hebben gehad</span><span class="sxs-lookup"><span data-stu-id="ddc64-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="ddc64-110">Kies in het Microsoft 365-beheercentrum de optie **Apparaten** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="ddc64-110">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="ddc64-111">Kies op **de pagina AutoPilot** het tabblad **Apparaten apparaten** \> **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="ddc64-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](../media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="ddc64-113">Blader in **het deelvenster Apparaten** toevoegen naar een [CSV-bestand](../admin/misc/device-list.md) in de lijst Apparaat dat u hebt voorbereid \> **op Sluiten** \> **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="ddc64-113">On the **Add devices** panel, browse to a [Device list CSV file](../admin/misc/device-list.md) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="ddc64-114">U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren.</span><span class="sxs-lookup"><span data-stu-id="ddc64-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="ddc64-115">Een profiel toewijzen aan een apparaat of een groep apparaten</span><span class="sxs-lookup"><span data-stu-id="ddc64-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="ddc64-116">Kies op **de pagina Windows** voorbereiden het tabblad **Apparaten** en schakel het selectievakje naast een of meer apparaten in.</span><span class="sxs-lookup"><span data-stu-id="ddc64-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="ddc64-117">Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**.</span><span class="sxs-lookup"><span data-stu-id="ddc64-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="ddc64-118">Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt.</span><span class="sxs-lookup"><span data-stu-id="ddc64-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
