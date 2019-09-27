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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Meer informatie over het uploaden van apparaten met behulp van AutoPilot in Microsoft 365 Business. U een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: 9ae94266f5a41d8d115fc92f0f080a6fdbdc9f15
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288010"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="f9c2f-104">AutoPilot-apparaten maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="f9c2f-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="f9c2f-105">Een lijst met apparaten uploaden</span><span class="sxs-lookup"><span data-stu-id="f9c2f-105">Upload a list of devices</span></span>

<span data-ttu-id="f9c2f-106">U kunt de [Stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u kunt ook apparaten uploaden op het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="f9c2f-107">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="f9c2f-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="f9c2f-108">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="f9c2f-109">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-109">New devices that have not been through Windows out-of-box experience.</span></span>

1. <span data-ttu-id="f9c2f-110">Kies in het Microsoft 365 Business Admin Center **apparaten** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f9c2f-111">Kies op de pagina **stuurautomaat** het \*\*\*\* tabblad \> apparaten **apparaten toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="f9c2f-113">Ga naar het deelvenster **apparaten toevoegen** en blader naar een [CSV-bestand met Apparaatlijst](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) dat \> u hebt voorbereid **Opslaan** \> **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-113">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="f9c2f-114">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="f9c2f-115">Een profiel toewijzen aan een apparaat of een groep apparaten</span><span class="sxs-lookup"><span data-stu-id="f9c2f-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="f9c2f-116">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten** en schakel het selectievakje in naast een of meer apparaten.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-116">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="f9c2f-117">Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="f9c2f-118">Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt.</span><span class="sxs-lookup"><span data-stu-id="f9c2f-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
