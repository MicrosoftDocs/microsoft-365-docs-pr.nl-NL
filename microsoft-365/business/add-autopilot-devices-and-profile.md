---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Informatie over het gebruik Windows AutoPilot om nieuwe Windows 10 voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik door werknemers.
ms.openlocfilehash: e178e7df220e89605502d9ed400265bcd963e57e
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636101"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="0eb1a-103">De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen</span><span class="sxs-lookup"><span data-stu-id="0eb1a-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="0eb1a-104">U kunt Windows AutoPilot gebruiken  om nieuwe Windows 10 voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="0eb1a-105">Apparaatvereisten</span><span class="sxs-lookup"><span data-stu-id="0eb1a-105">Device requirements</span></span>

<span data-ttu-id="0eb1a-106">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="0eb1a-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="0eb1a-107">Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="0eb1a-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="0eb1a-108">Nieuwe apparaten die nog niet zijn Windows-out-of-box-ervaring</span><span class="sxs-lookup"><span data-stu-id="0eb1a-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="0eb1a-109">De installatiehandleiding gebruiken om apparaten en profielen te maken</span><span class="sxs-lookup"><span data-stu-id="0eb1a-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="0eb1a-110">Als u nog geen apparaatgroepen of -profielen hebt gemaakt, kunt u het beste aan de slag met de stapsgewijse handleiding.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-110">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="0eb1a-111">U kunt ook [apparaten toevoegen en](create-and-edit-autopilot-devices.md) er [profielen](create-and-edit-autopilot-profiles.md) aan toewijzen zonder de handleiding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-111">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="0eb1a-112">Ga naar het beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0eb1a-113">Kies in het linkernavigatiedeelvenster de optie **Apparaten** \> **AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-113">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![Kies in het beheercentrum apparaten en vervolgens AutoPilot.](../media/AutoPilot.png)
  
2. <span data-ttu-id="0eb1a-115">Klik of tik **op de pagina AutoPilot** op **Starthandleiding**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-115">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="0eb1a-117">Blader op **Upload .csv pagina met lijst** met apparaten naar een locatie waar u het .CSV hebt en vervolgens **Volgende** \> **openen.**</span><span class="sxs-lookup"><span data-stu-id="0eb1a-117">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="0eb1a-118">Het bestand moet drie kopteksten hebben:</span><span class="sxs-lookup"><span data-stu-id="0eb1a-118">The file must have three headers:</span></span>
    
    - <span data-ttu-id="0eb1a-119">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="0eb1a-119">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="0eb1a-120">Kolom B: Product-id van Windows</span><span class="sxs-lookup"><span data-stu-id="0eb1a-120">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="0eb1a-121">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="0eb1a-121">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="0eb1a-122">U kunt deze informatie krijgen van uw hardwareleverancier of u kunt het [PowerShell-script Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-122">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="0eb1a-p103">Zie [Device list CSV-file](../admin/misc/device-list.md) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-p103">For more information, see [Device list CSV-file](../admin/misc/device-list.md). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="0eb1a-125">In dit script wordt WMI gebruikt om eigenschappen op te halen die nodig zijn voor een klant om een apparaat te registreren met Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-125">This script uses WMI to retrieve properties needed for a customer to register a device with Windows Autopilot.</span></span> <span data-ttu-id="0eb1a-126">Houd er rekening mee dat het normaal is dat het resulterende CSV-bestand geen PKID-waarde (Windows Product ID) verzamelt, aangezien dit niet nodig is om een apparaat te registreren en PKID null is in de uitvoer-CSV is prima.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-126">Note that it is normal for the resulting CSV file to not collect a Windows Product ID (PKID) value since this is not required to register a device and PKID being NULL in the output CSV is totally fine.</span></span> <span data-ttu-id="0eb1a-127">Alleen het serienummer en de hardwarehash worden ingevuld.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-127">Only the serial number and hardware hash will be populated.</span></span>
    
4. <span data-ttu-id="0eb1a-128">Op de **pagina Een profiel** toewijzen kunt u een bestaand profiel kiezen of een nieuw profiel maken.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-128">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="0eb1a-129">Als u er nog geen hebt, wordt u gevraagd er een te maken.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-129">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="0eb1a-130">Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-130">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="0eb1a-131">De standaardfuncties zijn vereist en worden automatisch ingesteld.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-131">The default features are required and are set automatically.</span></span> <span data-ttu-id="0eb1a-132">De standaardfuncties zijn:</span><span class="sxs-lookup"><span data-stu-id="0eb1a-132">The default features are:</span></span>
    
    - <span data-ttu-id="0eb1a-133">Sla Cortana, OneDrive en OEM-registratie over.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-133">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="0eb1a-134">Maak een aanmeldervaring met de huisstijl van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-134">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="0eb1a-135">Verbinding maken uw apparaten Azure Active Directory accounts en schrijf ze automatisch in om te worden beheerd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-135">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business Premium.</span></span>
    
    <span data-ttu-id="0eb1a-136">Zie Over [AutoPilot-profielinstellingen voor meer informatie.](autopilot-profile-settings.md)</span><span class="sxs-lookup"><span data-stu-id="0eb1a-136">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="0eb1a-137">De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-137">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="0eb1a-138">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-138">Choose **Next**.</span></span>
    
6. <span data-ttu-id="0eb1a-139">**U bent klaar, geeft** aan dat het profiel dat u hebt gemaakt (of gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-139">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="0eb1a-140">De instellingen zijn van kracht wanneer de gebruikers van het apparaat zich volgende aanmelden.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-140">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="0eb1a-141">Kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="0eb1a-141">Choose **Close**.</span></span>

## <a name="related-content"></a><span data-ttu-id="0eb1a-142">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0eb1a-142">Related content</span></span>

<span data-ttu-id="0eb1a-143">[Instellingen voor AutoPilot-profiel](autopilot-profile-settings.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0eb1a-143">[About AutoPilot Profile settings](autopilot-profile-settings.md) (article)</span></span>\
<span data-ttu-id="0eb1a-144">[Opties voor het beveiligen van uw apparaten en app-gegevens](../admin/devices/choose-device-security.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="0eb1a-144">[Options for protecting your devices and app data](../admin/devices/choose-device-security.md) (article)</span></span>
