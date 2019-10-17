---
title: AutoPilot-apparaten maken en bewerken
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met behulp van AutoPilot in Microsoft 365 Business. U een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 4eadaa800aa174bcd9cac50375f68c8471e1684e
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/17/2019
ms.locfileid: "37575403"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="490a3-104">AutoPilot-apparaten maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="490a3-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="490a3-105">Een lijst met apparaten uploaden</span><span class="sxs-lookup"><span data-stu-id="490a3-105">Upload a list of devices</span></span>

<span data-ttu-id="490a3-106">U kunt de [Stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u kunt ook apparaten uploaden op het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="490a3-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="490a3-107">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="490a3-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="490a3-108">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="490a3-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="490a3-109">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="490a3-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="490a3-110">Kies in het Microsoft 365 Business Admin Center **apparaten** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="490a3-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="490a3-111">Kies op de pagina **stuurautomaat** het \*\*\*\* tabblad \> apparaten **apparaten toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="490a3-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="490a3-113">Ga naar het deelvenster **apparaten toevoegen** en blader naar een [CSV-bestand met Apparaatlijst](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) dat \> u hebt voorbereid **Opslaan** \> **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="490a3-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="490a3-114">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="490a3-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="490a3-115">Een profiel toewijzen aan een apparaat of een groep apparaten</span><span class="sxs-lookup"><span data-stu-id="490a3-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="490a3-116">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten** en schakel het selectievakje in naast een of meer apparaten.</span><span class="sxs-lookup"><span data-stu-id="490a3-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="490a3-117">Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**.</span><span class="sxs-lookup"><span data-stu-id="490a3-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="490a3-118">Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt.</span><span class="sxs-lookup"><span data-stu-id="490a3-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
