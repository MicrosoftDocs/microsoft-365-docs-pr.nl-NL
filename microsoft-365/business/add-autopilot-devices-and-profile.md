---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
localization_priority: Normal
ms.custom:
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
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Lees hoe u Windows AutoPilot gebruikt om nieuwe Windows 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik door werknemers.
ms.openlocfilehash: 75cc51b889f8673de8dba2357c777de47fd0d296
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913497"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="cc5cf-103">De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen</span><span class="sxs-lookup"><span data-stu-id="cc5cf-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="cc5cf-104">U kunt Windows AutoPilot gebruiken om nieuwe **Windows** 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="cc5cf-105">Apparaatvereisten</span><span class="sxs-lookup"><span data-stu-id="cc5cf-105">Device requirements</span></span>

<span data-ttu-id="cc5cf-106">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="cc5cf-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="cc5cf-107">Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="cc5cf-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="cc5cf-108">Nieuwe apparaten die niet out-of-box-ervaring met Windows hebben gehad</span><span class="sxs-lookup"><span data-stu-id="cc5cf-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="cc5cf-109">De installatiehandleiding gebruiken om apparaten en profielen te maken</span><span class="sxs-lookup"><span data-stu-id="cc5cf-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="cc5cf-110">[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="cc5cf-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](../media/m365admincenterchanging.png)](/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="cc5cf-111">Als u nog geen apparaatgroepen of -profielen hebt gemaakt, kunt u het beste aan de slag met de stapsgewijse handleiding.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="cc5cf-112">U kunt ook [apparaten toevoegen en](create-and-edit-autopilot-devices.md) er [profielen](create-and-edit-autopilot-profiles.md) aan toewijzen zonder de handleiding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="cc5cf-113">Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="cc5cf-114">Kies in het linkernavigatiedeelvenster de optie **Apparaten** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Kies in het beheercentrum apparaten en vervolgens AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="cc5cf-116">Klik of tik **op de pagina AutoPilot** op **Starthandleiding**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="cc5cf-118">Blader op **de pagina Csv-bestand uploaden met lijst met apparaten** naar een locatie waar u de voorbereidingen hebt getroffen. CSV-bestand en vervolgens **Volgende** \> **openen.**</span><span class="sxs-lookup"><span data-stu-id="cc5cf-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="cc5cf-119">Het bestand moet drie kopteksten hebben:</span><span class="sxs-lookup"><span data-stu-id="cc5cf-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="cc5cf-120">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="cc5cf-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="cc5cf-121">Kolom B: Product-id van Windows</span><span class="sxs-lookup"><span data-stu-id="cc5cf-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="cc5cf-122">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="cc5cf-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="cc5cf-123">U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="cc5cf-p103">Zie [Device list CSV-file](../admin/misc/device-list.md) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="cc5cf-126">In dit script wordt WMI gebruikt om eigenschappen op te halen die een klant nodig heeft om een apparaat te registreren bij Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-126">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="cc5cf-127">Houd er rekening mee dat het normaal is dat het resulterende CSV-bestand geen PKID-waarde (Windows Product ID) verzamelt, omdat dit niet nodig is om een apparaat te registreren en PKID null is in de uitvoer-CSV is helemaal prima.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-127">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="cc5cf-128">Alleen het serienummer en de hardwarehash worden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-128">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="cc5cf-129">Op de **pagina Een profiel** toewijzen kunt u een bestaand profiel kiezen of een nieuw profiel maken.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-129">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="cc5cf-130">Als u er nog geen hebt, wordt u gevraagd er een te maken.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-130">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="cc5cf-131">Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-131">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="cc5cf-132">De standaardfuncties zijn vereist en worden automatisch ingesteld.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-132">The default features are required and are set automatically.</span></span> <span data-ttu-id="cc5cf-133">De standaardfuncties zijn:</span><span class="sxs-lookup"><span data-stu-id="cc5cf-133">The default features are:</span></span>
    
    - <span data-ttu-id="cc5cf-134">Sla Cortana, OneDrive en OEM-registratie over.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-134">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="cc5cf-135">Maak een aanmeldervaring met de huisstijl van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-135">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="cc5cf-136">Verbind uw apparaten met Azure Active Directory-accounts en schrijf ze automatisch in om te worden beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-136">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="cc5cf-137">Zie Over [AutoPilot-profielinstellingen voor meer informatie.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="cc5cf-137">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="cc5cf-138">De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-138">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="cc5cf-139">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-139">Choose **Next**.</span></span>
    
6. <span data-ttu-id="cc5cf-140">**U bent klaar, geeft** aan dat het profiel dat u hebt gemaakt (of gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-140">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="cc5cf-141">De instellingen zijn van kracht wanneer de gebruikers van het apparaat zich volgende aanmelden.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-141">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="cc5cf-142">Kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="cc5cf-142">Choose **Close**.</span></span>
