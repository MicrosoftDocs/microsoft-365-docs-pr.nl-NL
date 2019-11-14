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
ms.openlocfilehash: 1dd6b1a574166379e29465bf3699e47e3b155e0b
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38320253"
---
# <a name="create-and-edit-autopilot-devices"></a><span data-ttu-id="f4b1e-104">AutoPilot-apparaten maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="f4b1e-104">Create and edit AutoPilot devices</span></span>

## <a name="upload-a-list-of-devices"></a><span data-ttu-id="f4b1e-105">Een lijst met apparaten uploaden</span><span class="sxs-lookup"><span data-stu-id="f4b1e-105">Upload a list of devices</span></span>

<span data-ttu-id="f4b1e-106">U de [Stapsgewijze handleiding](add-autopilot-devices-and-profile.md) gebruiken om apparaten te uploaden, maar u ook apparaten uploaden op het tabblad **apparaten** .</span><span class="sxs-lookup"><span data-stu-id="f4b1e-106">You can use the [Step-by-step guide](add-autopilot-devices-and-profile.md) to upload devices, but you can also upload devices in the **Devices** tab.</span></span> 
  
<span data-ttu-id="f4b1e-107">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="f4b1e-107">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="f4b1e-108">Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="f4b1e-108">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="f4b1e-109">Nieuwe apparaten die niet door Windows zijn out-of-Box-ervaring</span><span class="sxs-lookup"><span data-stu-id="f4b1e-109">New devices that haven't been through Windows out-of-box experience</span></span>

1. <span data-ttu-id="f4b1e-110">Kies in het Microsoft 365 Business Admin Center **apparaten** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-110">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="f4b1e-111">Kies op de pagina **stuurautomaat** het \*\*\*\* tabblad \> apparaten **apparaten toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-111">On the **AutoPilot** page, choose the **Devices** tab \> **Add devices**.</span></span>
    
    ![In the Devices tab, choose Add devices.](media/6ba81e22-c873-40ad-8a72-ce64d15ea6ba.png)
  
3. <span data-ttu-id="f4b1e-113">Blader in het deelvenster **apparaten toevoegen** naar een [CSV-bestand met apparaatlijsten](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) dat \> u hebt voorbereid om het **Opslaan** \> te **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-113">On the **Add devices** panel, browse to a [Device list CSV file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) that you prepared \> **Save** \> **Close**.</span></span>
    
    <span data-ttu-id="f4b1e-114">U deze informatie ophalen van uw hardwareleverancier, of u het [Get-WindowsAutoPilotInfo PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-114">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
## <a name="assign-a-profile-to-a-device-or-a-group-of-devices"></a><span data-ttu-id="f4b1e-115">Een profiel toewijzen aan een apparaat of een groep apparaten</span><span class="sxs-lookup"><span data-stu-id="f4b1e-115">Assign a profile to a device or a group of devices</span></span>

1. <span data-ttu-id="f4b1e-116">Kies op de pagina **Windows voorbereiden** het tabblad **apparaten** en schakel het selectievakje naast een of meer apparaten in.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-116">On the **Prepare Windows** page, choose the **Devices** tab, and select the check box next to one or more devices.</span></span> 
    
2. <span data-ttu-id="f4b1e-117">Selecteer in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel**.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-117">On the **Device** panel, select a profile from the **Assigned profile** drop-down.</span></span> 
    
    <span data-ttu-id="f4b1e-118">Zie [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) (AutoPilot-profielen maken en bewerken) voor instructies als u nog geen profielen hebt.</span><span class="sxs-lookup"><span data-stu-id="f4b1e-118">If you don't have any profiles yet, see [Create and edit AutoPilot profiles](create-and-edit-autopilot-profiles.md) for instructions.</span></span> 
    
