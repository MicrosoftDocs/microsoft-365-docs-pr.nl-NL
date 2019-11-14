---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informatie over het gebruik van Windows AutoPilot voor het instellen van nieuwe Windows 10-apparaten voor uw bedrijf.
ms.openlocfilehash: 5f40dac57285b83da57d4506bac58e562475522c
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323090"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="0a077-103">De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen</span><span class="sxs-lookup"><span data-stu-id="0a077-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="0a077-104">U Windows AutoPilot gebruiken om **nieuwe** Windows 10-apparaten voor uw bedrijf in te stellen, zodat ze klaar zijn voor gebruik wanneer u ze aan uw werknemers geeft.</span><span class="sxs-lookup"><span data-stu-id="0a077-104">You can use Windows AutoPilot to set up **new** Windows 10 devices for your business so they're ready for use when you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="0a077-105">Apparaatvereisten</span><span class="sxs-lookup"><span data-stu-id="0a077-105">Device requirements</span></span>

<span data-ttu-id="0a077-106">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="0a077-106">Devices must meet these requirements:</span></span>
  
- <span data-ttu-id="0a077-107">Windows 10, versie 1703 of hoger</span><span class="sxs-lookup"><span data-stu-id="0a077-107">Windows 10, version 1703 or later</span></span>
    
- <span data-ttu-id="0a077-108">Nieuwe apparaten die niet door Windows zijn out-of-Box-ervaring</span><span class="sxs-lookup"><span data-stu-id="0a077-108">New devices that haven't been through Windows out-of-box experience</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="0a077-109">De installatiehandleiding gebruiken om apparaten en profielen te maken</span><span class="sxs-lookup"><span data-stu-id="0a077-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="0a077-110">[![Etiket om u te laten weten dat het beheercentrum wordt gewijzigd en meer informatie vindt u op aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="0a077-110">[![Label to let you know the admin center is changing and you can find more details at aka.ms/aboutM365preview.](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span></span>

<span data-ttu-id="0a077-111">Als u nog geen apparaatgroepen of profielen hebt gemaakt, u de beste manier om aan de slag te gaan door de stapsgewijze handleiding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a077-111">If you haven't created device groups or profiles yet, the best way to get started is by using the step-by-step guide.</span></span> <span data-ttu-id="0a077-112">U ook [apparaten toevoegen](create-and-edit-autopilot-devices.md) en hieraan [profielen toewijzen](create-and-edit-autopilot-profiles.md) zonder de Guide te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0a077-112">You can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="0a077-113">Ga naar het Admin Center op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="0a077-113">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="0a077-114">Kies in het linkernavigatievenster **apparaten** \> **Autopilot**.</span><span class="sxs-lookup"><span data-stu-id="0a077-114">On the left navigation pane, choose **Devices** \> **AutoPilot**.</span></span>

    ![In het Admin Center, kiest u apparaten en vervolgens AutoPilot.](media/AutoPilot.png)
  
2. <span data-ttu-id="0a077-116">Klik of tik op de pagina **stuurautomaat** op **start gids**.</span><span class="sxs-lookup"><span data-stu-id="0a077-116">On the **AutoPilot** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="0a077-118">Op de **Upload. CSV-bestand met lijst met apparaten** pagina, bladert u naar een locatie waar u de voorbereide. CSV-bestand en **Open** \> vervolgens **de volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a077-118">On the **Upload .csv file with list of devices** page, browse to a location where you have the prepared .CSV file, then **Open** \> **Next**.</span></span> <span data-ttu-id="0a077-119">Het bestand moet drie koppen hebben:</span><span class="sxs-lookup"><span data-stu-id="0a077-119">The file must have three headers:</span></span>
    
    - <span data-ttu-id="0a077-120">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="0a077-120">Column A: Device Serial Number</span></span>
    
    - <span data-ttu-id="0a077-121">Kolom B: Product-id van Windows</span><span class="sxs-lookup"><span data-stu-id="0a077-121">Column B: Windows Product ID</span></span>
    
    - <span data-ttu-id="0a077-122">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="0a077-122">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="0a077-123">U deze informatie ophalen van uw hardwareleverancier, of u het [Get-WindowsAutoPilotInfo PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken om een CSV-bestand te genereren.</span><span class="sxs-lookup"><span data-stu-id="0a077-123">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) to generate a CSV file.</span></span> 
    
    <span data-ttu-id="0a077-p103">Zie [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**.</span><span class="sxs-lookup"><span data-stu-id="0a077-p103">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="0a077-126">Op de pagina **een profiel toewijzen** u een bestaand profiel kiezen of een nieuwe maken.</span><span class="sxs-lookup"><span data-stu-id="0a077-126">On the **Assign a profile** page, you can either pick an existing profile or create a new one.</span></span> <span data-ttu-id="0a077-127">Als u er nog geen hebt, wordt u gevraagd er een te maken.</span><span class="sxs-lookup"><span data-stu-id="0a077-127">If you don't have one yet, you'll be prompted to create one.</span></span> 
    
    <span data-ttu-id="0a077-128">Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="0a077-128">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="0a077-129">De standaardfuncties zijn vereist en worden automatisch ingesteld.</span><span class="sxs-lookup"><span data-stu-id="0a077-129">The default features are required and are set automatically.</span></span> <span data-ttu-id="0a077-130">De standaardfuncties zijn:</span><span class="sxs-lookup"><span data-stu-id="0a077-130">The default features are:</span></span>
    
    - <span data-ttu-id="0a077-131">Sla Cortana, OneDrive en OEM-registratie over.</span><span class="sxs-lookup"><span data-stu-id="0a077-131">Skip Cortana, OneDrive, and OEM registration.</span></span>
    
    - <span data-ttu-id="0a077-132">Maak een aanmeldervaring met de huisstijl van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="0a077-132">Create sign-in experience with your company brand.</span></span>
    
    - <span data-ttu-id="0a077-133">Verbind uw apparaten met Azure Active Directory-accounts en registreer ze automatisch om te worden beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="0a077-133">Connect your devices to Azure Active Directory accounts, and automatically enroll them to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="0a077-134">Zie over de instellingen van het [Autopilot-profiel](autopilot-profile-settings.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0a077-134">For more information, see [About AutoPilot Profile settings](autopilot-profile-settings.md).</span></span> 
    
5. <span data-ttu-id="0a077-135">De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="0a077-135">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="0a077-136">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="0a077-136">Choose **Next**.</span></span>
    
6. <span data-ttu-id="0a077-137">**U bent klaar** geeft aan dat het profiel dat u hebt gemaakt (of gekozen) wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden.</span><span class="sxs-lookup"><span data-stu-id="0a077-137">**You're done** indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices.</span></span> <span data-ttu-id="0a077-138">De instellingen zijn van kracht wanneer de apparaatgebruikers zich vervolgens aanmelden.</span><span class="sxs-lookup"><span data-stu-id="0a077-138">The settings will be in effect when the device users sign in next.</span></span> <span data-ttu-id="0a077-139">Kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="0a077-139">Choose **Close**.</span></span>
    