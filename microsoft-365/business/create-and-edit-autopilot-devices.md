---
title: AutoPilot-apparaten maken en bewerken
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0f7b1d7c-4086-4331-8534-45d7886f9f34
description: Informatie over het laden van apparaten met automatische piloot in Microsoft 365 Business. U kunt een profiel toewijzen aan een apparaat of een groep apparaten.
ms.openlocfilehash: cc1f81e9efd9b16e27b8abfbb0927d241535077e
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "26982932"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="1c773-104">AutoPilot-apparaten maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="1c773-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="1c773-105">Een lijst met apparaten uploaden</span><span class="sxs-lookup"><span data-stu-id="1c773-105">Upload a list of devices</span></span>

<span data-ttu-id="1c773-106">U kunt de [Stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u kunt ook apparaten uploaden op het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="1c773-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload the in the **Devices** tab.</span></span> 
  
<span data-ttu-id="1c773-107">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="1c773-107">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="1c773-108">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="1c773-108">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="1c773-109">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="1c773-109">New devices that have not been through Windows out-of-box experience.</span></span>
    
1. <span data-ttu-id="1c773-110">Kies in het beheercentrum van Microsoft 365 Business de optie **Windows implementeren met AutoPilot** op de kaart **Apparaatacties**.</span><span class="sxs-lookup"><span data-stu-id="1c773-110">In the Microsoft 365 Business Admin center, choose **Deploy Windows with AutoPilot** on the **Device actions** card.</span></span> 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="1c773-112">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten** \> **Apparaten toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1c773-112">On the **Prepare Windows** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="1c773-114">Ga in het venster **apparaten toevoegen** naar een [CSV-bestand lijst met apparaten](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) die u hebt voorbereid \> **Opslaan** \> **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="1c773-114">On the **Add devices** panel, browse to a [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you have prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="1c773-115">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="1c773-115">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a csv file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="1c773-116">Een profiel toewijzen aan een apparaat of een groep apparaten</span><span class="sxs-lookup"><span data-stu-id="1c773-116">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="1c773-117">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten** en schakel het selectievakje in naast een of meer apparaten.</span><span class="sxs-lookup"><span data-stu-id="1c773-117">On the **Prepare Windows** page, choose the **Devices** tab and check the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="1c773-118">Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**.</span><span class="sxs-lookup"><span data-stu-id="1c773-118">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="1c773-119">Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt.</span><span class="sxs-lookup"><span data-stu-id="1c773-119">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
