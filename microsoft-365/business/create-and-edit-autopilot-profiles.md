---
title: AutoPilot-profielen maken en bewerken
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
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Informatie over het maken, bewerken, verwijderen of verwijderen van AutoPilot-profielen. '
ms.openlocfilehash: 8fae8af5e7aa7b866745d0b34a4fe11862de6e9d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287770"
---
# <a name="create-and-edit-autopilot-profiles"></a><span data-ttu-id="c7171-103">AutoPilot-profielen maken en bewerken</span><span class="sxs-lookup"><span data-stu-id="c7171-103">Create and edit AutoPilot profiles</span></span>

## <a name="create-a-profile"></a><span data-ttu-id="c7171-104">Een profiel maken</span><span class="sxs-lookup"><span data-stu-id="c7171-104">Create a profile</span></span>

<span data-ttu-id="c7171-105">Een profiel geldt voor een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="c7171-105">A profile applies to a device, or a group of devices,</span></span>
  
1. <span data-ttu-id="c7171-106">Kies in het Microsoft 365 Business Admin Center **apparaten** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="c7171-106">In the Microsoft 365 Business Admin center, choose **Devices** \> **AutoPilot**.</span></span>
  
2. <span data-ttu-id="c7171-107">Kies op de pagina **stuurautomaat** het \*\*\*\* tabblad \> profielen **profiel maken**.</span><span class="sxs-lookup"><span data-stu-id="c7171-107">On the **AutoPilot** page, choose the **Profiles** tab \> **Create profile**.</span></span>
    
3. <span data-ttu-id="c7171-108">Voer op de pagina **Profiel maken** een naam in voor het profiel waaraan u deze kunt herkennen, bijvoorbeeld Marketing, schakel de gewenste instelling in (zie [Info over AutoPilot-profielinstellingen](autopilot-profile-settings.md) voor meer informatie) en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c7171-108">On the **Create profile** page, enter a name for the profile that helps you identify it, for example Marketing, turn on the setting you want (see [About AutoPilot Profile settings](autopilot-profile-settings.md) for more information), and choose **Save**.</span></span>
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a><span data-ttu-id="c7171-110">Een profiel toepassen op een apparaat</span><span class="sxs-lookup"><span data-stu-id="c7171-110">Apply profile to a device</span></span>

<span data-ttu-id="c7171-p101">Wanneer u een profiel hebt gemaakt, kunt u deze toepassen op een apparaat of een groep apparaten. U kunt een bestaand profiel kiezen in de [stapsgewijze handleiding](add-autopilot-devices-and-profile.md), u kunt dit toepassen op nieuwe apparaten of u kunt een bestaand profiel voor een apparaat of groep apparaten vervangen.</span><span class="sxs-lookup"><span data-stu-id="c7171-p101">After you create a profile you can apply it to a device or a group of devices. You can pick an existing profile in the [step-by-step guide](add-autopilot-devices-and-profile.md), you can apply it to new devices, or you can replace an existing profile for a device or group of devices.</span></span> 
  
1. <span data-ttu-id="c7171-113">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="c7171-113">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="c7171-114">Klik op het selectievakje naast een apparaatnaam en kies in het deelvenster **Apparaat** een profiel in de vervolgkeuzelijst **Toegewezen profiel** \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c7171-114">Click the check-box next to a device name and in the **Device** panel, choose a profile from the **Assigned profile** drop-down \> **Save**.</span></span>
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a><span data-ttu-id="c7171-116">Een profiel bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7171-116">Edit, delete, or remove a profile</span></span>

<span data-ttu-id="c7171-p102">Wanneer u een profiel aan een apparaat hebt toegewezen, kunt u dit bijwerken, zelfs als u het apparaat al aan een gebruiker hebt gegeven. Wanneer het apparaat verbinding maakt met internet, wordt de nieuwste versie van uw profiel gedownload tijdens het installatieproces. Als de gebruiker het apparaat herstelt naar de fabrieksinstellingen, worden de nieuwste updates opnieuw naar uw profiel gedownload.</span><span class="sxs-lookup"><span data-stu-id="c7171-p102">Once you've assigned a profile to a device, you can update it, even if you've already given the device to a user. When the device connects to the internet, it downloads the latest version of your profile during the setup process. If the user restores their device to its factory default settings, the device will again download the latest updates to your profile.</span></span> 
  
### <a name="edit-a-profile"></a><span data-ttu-id="c7171-120">Een profiel bewerken</span><span class="sxs-lookup"><span data-stu-id="c7171-120">Edit a profile</span></span>

1. <span data-ttu-id="c7171-121">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="c7171-121">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="c7171-122">Klik op het selectievakje naast een apparaatnaam en werk in het deelvenster **Profiel** de gewenste beschikbare instellingen bij \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c7171-122">Click the check-box next to a device name and in the **Profile** panel update any of the available settings \> **Save**.</span></span>
    
    <span data-ttu-id="c7171-123">Als u dit doet voordat een gebruiker het apparaat verbindt met internet, wordt het profiel toegepast tijdens het installatieproces.</span><span class="sxs-lookup"><span data-stu-id="c7171-123">If you do this before a user connects the device to the internet, then the profile gets applied to the setup process.</span></span>
    
### <a name="delete-a-profile"></a><span data-ttu-id="c7171-124">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7171-124">Delete a profile</span></span>

1. <span data-ttu-id="c7171-125">Kies op de pagina **Windows voorbereiden** het tabblad **Profielen**.</span><span class="sxs-lookup"><span data-stu-id="c7171-125">On the **Prepare Windows** page, choose the **Profiles** tab.</span></span> 
    
2. <span data-ttu-id="c7171-126">Klik op het selectievakje naast een apparaatnaam en klik in het deelvenster **Profiel** op **Profiel verwijderen** \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c7171-126">Click the check-box next to a device name and in the **Profile** panel click **Delete profile** \> **Save**.</span></span>
    
    <span data-ttu-id="c7171-127">Wanneer u een profiel verwijdert, wordt dit verwijderd van het apparaat of de groep apparaten waaraan dit was toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c7171-127">When you delete a profile, it gets removed from a device or a group of devices it was assigned to.</span></span>
    
### <a name="remove-a-profile"></a><span data-ttu-id="c7171-128">Een profiel verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7171-128">Remove a profile</span></span>

1. <span data-ttu-id="c7171-129">Kies op de pagina **Windows voorbereiden** het tabblad **Apparaten**.</span><span class="sxs-lookup"><span data-stu-id="c7171-129">On the **Prepare Windows** page, choose the **Devices** tab.</span></span> 
    
2. <span data-ttu-id="c7171-130">Klik op het selectievakje naast een apparaatnaam en kies in het deelvenster **Apparaat** de optie **Geen** in de vervolgkeuzelijst **Toegewezen profiel** \> **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c7171-130">Click the check-box next to a device name and in the **Device** panel, choose a **None** from the **Assigned profile** drop-down \> **Save**.</span></span>
    
