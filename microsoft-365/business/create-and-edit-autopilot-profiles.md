---
title: AutoPilot-profielen maken en bewerken
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: Informatie over het maken van een AutoPilot-profiel en het toepassen op een apparaat, evenals het bewerken of verwijderen van een profiel of het verwijderen van een profiel van een apparaat.
ms.openlocfilehash: 414243da88fb6f39f8e6067d19d49ffe955f725f
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580249"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="cf410-103">AutoPilot-profielen maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="cf410-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="cf410-104">Een profiel maken</span><span class="sxs-lookup"><span data-stu-id="cf410-104">Create a profile</span></span>

<span data-ttu-id="cf410-105">Een profiel geldt voor een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="cf410-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="cf410-106">Kies in het Microsoft 365-beheercentrum de optie **Apparaten** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="cf410-106">In the Microsoft 365 admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="cf410-107">Kies op **de pagina AutoPilot** het tabblad **Profielen** profiel \> **maken.**</span><span class="sxs-lookup"><span data-stu-id="cf410-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="cf410-108">Voer op **de pagina** Profiel maken een naam in voor het profiel waarmee u het kunt identificeren, bijvoorbeeld Marketing.</span><span class="sxs-lookup"><span data-stu-id="cf410-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing.</span></span> <span data-ttu-id="cf410-109">Schakel de beste instelling in en kies **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="cf410-109">Turn on the setting you want, and then choose **Save**.</span></span> <span data-ttu-id="cf410-110">Zie Over AutoPilot-profielinstellingen voor meer informatie over [autoPilot-profielinstellingen.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cf410-110">For more information about AutoPilot profile settings, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](../media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="cf410-112">Een profiel toepassen op een apparaat</span><span class="sxs-lookup"><span data-stu-id="cf410-112">Apply profile to a device</span></span>

<span data-ttu-id="cf410-113">Nadat u een profiel hebt gemaakt, kunt u dit toepassen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="cf410-113">After you create a profile, you can apply it to a device or a group of devices.</span></span> <span data-ttu-id="cf410-114">U kunt een bestaand profiel kiezen in de [stapsgewijse](add-autopilot-devices-and-profile.md) handleiding en dit toepassen op nieuwe apparaten, of een bestaand profiel vervangen voor een apparaat of groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="cf410-114">You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md) and apply it to new devices, or replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="cf410-115">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="cf410-115">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="cf410-116">Schakel het selectievakje naast een apparaatnaam  in en kies in  het deelvenster Apparaat een profiel in de vervolgkeuzelijst Toegewezen profiel \> **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="cf410-116">Select the check box next to a device name, and in the **Device** panel, choose a profile from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](../media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="cf410-118">Een profiel bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="cf410-118">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="cf410-p103">Wanneer u een profiel aan een apparaat hebt toegewezen, kunt u dit bijwerken, zelfs als u het apparaat al aan een gebruiker hebt gegeven. Wanneer het apparaat verbinding maakt met internet, wordt de nieuwste versie van uw profiel gedownload tijdens het installatieproces. Als de gebruiker het apparaat herstelt naar de fabrieksinstellingen, worden de nieuwste updates opnieuw naar uw profiel gedownload.</span><span class="sxs-lookup"><span data-stu-id="cf410-p103">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="cf410-122">Een profiel bewerken</span><span class="sxs-lookup"><span data-stu-id="cf410-122">Edit a profile</span></span>

1. <span data-ttu-id="cf410-123">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="cf410-123">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="cf410-124">Schakel het selectievakje naast een apparaatnaam  in en werk in het deelvenster Profiel een van de beschikbare instellingen \> **Opslaan bij.**</span><span class="sxs-lookup"><span data-stu-id="cf410-124">Select the check box next to a device name, and in the **Profile** panel, update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="cf410-125">Als u dit doet voordat een gebruiker het apparaat verbindt met internet, wordt het profiel toegepast tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="cf410-125">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="cf410-126">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="cf410-126">Delete a profile</span></span>

1. <span data-ttu-id="cf410-127">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="cf410-127">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="cf410-128">Schakel het selectievakje naast een apparaatnaam in en  selecteer profiel opslaan in het **deelvenster** \> **Profiel verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="cf410-128">Select the check box next to a device name, and in the **Profile** panel, select **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="cf410-129">Wanneer u een profiel verwijdert, wordt dit verwijderd van het apparaat of de groep apparaten waaraan dit was toegewezen.</span><span class="sxs-lookup"><span data-stu-id="cf410-129">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="cf410-130">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="cf410-130">Remove a profile</span></span>

1. <span data-ttu-id="cf410-131">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="cf410-131">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="cf410-132">Schakel het selectievakje naast een apparaatnaam  in en kies in  het deelvenster Apparaat de optie **Geen** in de vervolgkeuzelijst Toegewezen profiel \> **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="cf410-132">Select the check box next to a device name, and in the **Device** panel, choose **None** from the **Assigned profile** drop-down list \> **Save**.</span></span>
    
