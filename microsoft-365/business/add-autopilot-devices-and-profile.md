---
title: De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Informatie over automatische piloot Windows gebruiken voor het instellen van nieuwe Windows 10-apparaten voor uw bedrijf.
ms.openlocfilehash: e0802ddcc0964d0b8d102f7dbdb9116b33cdcf58
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277090"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a><span data-ttu-id="3c436-103">De stapsgewijze handleiding gebruiken om Autopilot-apparaten en -profielen toe te voegen</span><span class="sxs-lookup"><span data-stu-id="3c436-103">Use the step-by-step guide to add Autopilot devices and profile</span></span>

<span data-ttu-id="3c436-104">U kunt de WIndows Autopilot gebruiken om nieuwe Windows 10-apparaten voor uw bedrijf in te stellen, zodat deze klaar zijn voor gebruik zodra u ze aan uw werknemers geeft.</span><span class="sxs-lookup"><span data-stu-id="3c436-104">You can use Windows AutoPilot to set up new Windows 10 devices for your business so they are ready for productive use as soon as you give them to your employees.</span></span>
  
## <a name="device-requirements"></a><span data-ttu-id="3c436-105">Apparaatvereisten</span><span class="sxs-lookup"><span data-stu-id="3c436-105">Device requirements</span></span>

<span data-ttu-id="3c436-106">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="3c436-106">Devices need to meet these requirements:</span></span>
  
- <span data-ttu-id="3c436-107">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="3c436-107">Windows 10, version 1703 or later.</span></span>
    
- <span data-ttu-id="3c436-108">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="3c436-108">New devices that have not been through Windows out-of-box experience.</span></span>
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a><span data-ttu-id="3c436-109">De installatiehandleiding gebruiken om apparaten en profielen te maken</span><span class="sxs-lookup"><span data-stu-id="3c436-109">Use the setup guide to create devices and profiles</span></span>

<span data-ttu-id="3c436-110">Als u nog geen apparaatgroepen of profielen hebt gemaakt, kunt u het beste aan de slag gaan met de stapsgewijze handleiding, maar u kunt ook [apparaten toevoegen](create-and-edit-autopilot-devices.md) en hieraan [profielen toewijzen](create-and-edit-autopilot-profiles.md) zonder de handleiding te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3c436-110">If you have no device groups or profiles created yet, the best way to get started is by using the step-by-step guide, but you can also [add devices](create-and-edit-autopilot-devices.md) and [assign profiles](create-and-edit-autopilot-profiles.md) to them without using the guide.</span></span> 
  
1. <span data-ttu-id="3c436-111">Zoek in het beheercentrum van Microsoft 365 Business naar de kaart **Apparaatacties** en kies **Windows implementeren met AutoPilot**.</span><span class="sxs-lookup"><span data-stu-id="3c436-111">In the Microsoft 365 Business admin center, locate the **Device actions** card, and choose **Deploy Windows with Autopilot**.</span></span>
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. <span data-ttu-id="3c436-113">Klik of tik op de pagina **Windows voorbereiden** op **Handleiding starten**.</span><span class="sxs-lookup"><span data-stu-id="3c436-113">On the **Prepare Windows** page, click or tap **Start guide**.</span></span>
    
    ![Click Start guide for step-by-step instructions for Autopilot.](media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. <span data-ttu-id="3c436-p101">Blader op de pagina **CSV-bestand met lijst met apparaten uploaden** naar de locatie van het voorbereide CSV-bestand en klik op **Openen** \> **Volgende**. Het bestand moet drie kopteksten bevatten:</span><span class="sxs-lookup"><span data-stu-id="3c436-p101">On the **Upload .csv file with list of devices** page, browse to a locations where you have the prepared .CSV file, then **Open** \> **Next**. The file should have three headers:</span></span>
    
  - <span data-ttu-id="3c436-117">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="3c436-117">Column A: Device Serial Number</span></span>
    
  - <span data-ttu-id="3c436-118">Kolom B: Product-id van Windows</span><span class="sxs-lookup"><span data-stu-id="3c436-118">Column B: Windows Product ID</span></span>
    
  - <span data-ttu-id="3c436-119">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="3c436-119">Column C: Hardware Hash</span></span>
    
    <span data-ttu-id="3c436-120">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="3c436-120">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 
    
    <span data-ttu-id="3c436-p102">Zie [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e) (CSV-bestand met lijst met apparaten) voor meer informatie. U kunt ook een voorbeeldbestand downloaden op de pagina **CSV-bestand met lijst met apparaten uploaden**.</span><span class="sxs-lookup"><span data-stu-id="3c436-p102">For more information, see [Device list CSV-file](https://support.office.com/article/932e3676-2491-49f0-9177-d893d2f5276e). You can also download a sample file on the **Upload .csv file with list of devices** page.</span></span> 
    
4. <span data-ttu-id="3c436-p103">Op de pagina **Profiel toewijzen** kunt u een bestaand profiel kiezen of een nieuw profiel maken. Als u nog geen profiel hebt, wordt u gevraagd om een nieuw profiel te maken.</span><span class="sxs-lookup"><span data-stu-id="3c436-p103">On the **Assign a profile** page, you can either pick an existing profile, or create a new one. If you don't have one yet, you will be prompted to create a new one.</span></span> 
    
    <span data-ttu-id="3c436-125">Een profiel bestaat uit een reeks instellingen die op één apparaat of op een groep apparaten kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="3c436-125">A profile is a collection of settings that can be applied to a single device or to a group of devices.</span></span>
    
    <span data-ttu-id="3c436-p104">De standaardfuncties zijn vereist en worden automatisch ingesteld. De standaardfuncties zijn:</span><span class="sxs-lookup"><span data-stu-id="3c436-p104">The default features are required and will be set automatically. The default features are:</span></span>
    
  - <span data-ttu-id="3c436-128">Cortana-, OneDrive- en OEM-registratie wordt overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3c436-128">Cortana, OneDrive and OEM registration is skipped.</span></span>
    
  - <span data-ttu-id="3c436-129">Maak een aanmeldervaring met de huisstijl van uw bedrijf.</span><span class="sxs-lookup"><span data-stu-id="3c436-129">Create sign-in experience with your company brand.</span></span>
    
  - <span data-ttu-id="3c436-130">De apparaten worden verbonden met Azure Active Directory-accounts en worden automatisch geregistreerd om te worden beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3c436-130">Your devices are going to be connected to Azure Active Directory accounts and automatically enrolled to be managed by Microsoft 365 Business.</span></span>
    
    <span data-ttu-id="3c436-131">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="3c436-131">For more information, see</span></span>
    
    <span data-ttu-id="3c436-132">[Info over AutoPilot-profielinstellingen](autopilot-profile-settings.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c436-132">[About AutoPilot Profile settings](autopilot-profile-settings.md) .</span></span> 
    
5. <span data-ttu-id="3c436-133">De andere instellingen zijn **Privacy-instellingen overslaan** en **Niet toestaan dat gebruiker de lokale beheerder wordt**. Deze zijn beide standaard **uitgeschakeld**.</span><span class="sxs-lookup"><span data-stu-id="3c436-133">The other settings are **Skip privacy settings** and **Don't allow user to become the local admin**. These are both set to **Off** by default.</span></span> 
    
    <span data-ttu-id="3c436-134">Kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="3c436-134">Choose **Next**.</span></span>
    
6. <span data-ttu-id="3c436-p105">Op de pagina **U bent klaar** wordt aangegeven dat het profiel dat u hebt gemaakt (of gekozen), wordt toegepast op de apparaatgroep die u hebt gemaakt door de lijst met apparaten te uploaden. Deze instellingen worden van kracht wanneer de gebruiker van het apparaat zich de volgende keer aanmeldt. Kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3c436-p105">**You're done** page indicates that the profile you created (or chose) will be applied to the device group you created by uploading the list of devices. These settings will be in effect when the device users sign in next. Choose **Close**.</span></span>
    