---
title: AutoPilot-profielen maken en bewerken
f1.keywords:
- NOCSH
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Meer informatie over het maken, bewerken, verwijderen of verwijderen van AutoPilot-profielen.
ms.openlocfilehash: 35967cb1f6e2cdeea9d7c42a529526410fa8b586
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593986"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="89a29-103">AutoPilot-profielen maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="89a29-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="89a29-104">Een profiel maken</span><span class="sxs-lookup"><span data-stu-id="89a29-104">Create a profile</span></span>

<span data-ttu-id="89a29-105">Een profiel geldt voor een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="89a29-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="89a29-106">Kies In het Microsoft 365 Business Admin Center de optie **Apparaten** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="89a29-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="89a29-107">Kies op de pagina **AutoPilot** het tabblad **Profielen** \> **maken**.</span><span class="sxs-lookup"><span data-stu-id="89a29-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="89a29-108">Voer op de pagina **Profiel maken** een naam in voor het profiel waarmee u deze identificeren, bijvoorbeeld Marketing.</span><span class="sxs-lookup"><span data-stu-id="89a29-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="89a29-109">Schakel de gewenste instelling in en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="89a29-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="89a29-110">Zie [Instellingen voor AutoPilot-profiel voor](autopilot-profile-settings.md)meer informatie over de profielinstellingen van AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="89a29-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="89a29-112">Een profiel toepassen op een apparaat</span><span class="sxs-lookup"><span data-stu-id="89a29-112">Apply profile to a device</span></span>

<span data-ttu-id="89a29-113">Nadat u een profiel hebt gemaakt, u het toepassen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="89a29-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="89a29-114">U een bestaand profiel kiezen in de [stapsgewijze handleiding](add-autopilot-devices-and-profile.md) en het toepassen op nieuwe apparaten of een bestaand profiel vervangen voor een apparaat of groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="89a29-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="89a29-115">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="89a29-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="89a29-116">Schakel het selectievakje naast een apparaatnaam in en kies in het deelvenster **Apparaat** \> een profiel in de vervolgkeuzelijst **Toegewezen profiel** **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="89a29-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="89a29-118">Een profiel bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="89a29-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="89a29-p103">Wanneer u een profiel aan een apparaat hebt toegewezen, kunt u dit bijwerken, zelfs als u het apparaat al aan een gebruiker hebt gegeven. Wanneer het apparaat verbinding maakt met internet, wordt de nieuwste versie van uw profiel gedownload tijdens het installatieproces. Als de gebruiker het apparaat herstelt naar de fabrieksinstellingen, worden de nieuwste updates opnieuw naar uw profiel gedownload.</span><span class="sxs-lookup"><span data-stu-id="89a29-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="89a29-122">Een profiel bewerken</span><span class="sxs-lookup"><span data-stu-id="89a29-122">Edit a profile</span></span>

1. <span data-ttu-id="89a29-123">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="89a29-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="89a29-124">Schakel het selectievakje naast een apparaatnaam \*\*\*\* in en werk in het \> deelvenster Profiel een van de beschikbare instellingen **Opslaan**bij.</span><span class="sxs-lookup"><span data-stu-id="89a29-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="89a29-125">Als u dit doet voordat een gebruiker het apparaat verbindt met internet, wordt het profiel toegepast tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="89a29-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="89a29-126">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="89a29-126">Delete a profile</span></span>

1. <span data-ttu-id="89a29-127">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="89a29-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="89a29-128">Schakel het selectievakje naast een apparaatnaam in en selecteer in het deelvenster **Profiel** **profiel** \> **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="89a29-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="89a29-129">Wanneer u een profiel verwijdert, wordt dit verwijderd van het apparaat of de groep apparaten waaraan dit was toegewezen.</span><span class="sxs-lookup"><span data-stu-id="89a29-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="89a29-130">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="89a29-130">Remove a profile</span></span>

1. <span data-ttu-id="89a29-131">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="89a29-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="89a29-132">Schakel het selectievakje naast een apparaatnaam \*\*\*\* in en kies in het deelvenster Apparaat \> **Geen** in de vervolgkeuzelijst **Toegewezen profiel** **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="89a29-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
