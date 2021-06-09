---
title: Problemen met basismobiliteit en beveiliging oplossen
f1.keywords: NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
description: Probeer deze stappen om problemen met basismobiliteit en beveiliging op te sporen
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876850"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="26530-103">Problemen met basismobiliteit en beveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="26530-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="26530-104">Als u problemen hebt wanneer u probeert een apparaat in te schrijven in Basismobiliteit en Beveiliging, probeert u de stappen hier om het probleem op te sporen.</span><span class="sxs-lookup"><span data-stu-id="26530-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="26530-105">Als het probleem niet wordt opgelost met de algemene stappen, bekijkt u een van de latere secties met specifieke stappen voor uw apparaattype.</span><span class="sxs-lookup"><span data-stu-id="26530-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="26530-106">Stappen om het eerst te proberen</span><span class="sxs-lookup"><span data-stu-id="26530-106">Steps to try first</span></span>

<span data-ttu-id="26530-107">Ga als volgt te werk om te beginnen:</span><span class="sxs-lookup"><span data-stu-id="26530-107">To start, check the following:</span></span>

- <span data-ttu-id="26530-108">Zorg ervoor dat het apparaat nog niet is geregistreerd bij een andere provider voor mobiel apparaatbeheer, zoals Intune.</span><span class="sxs-lookup"><span data-stu-id="26530-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>

- <span data-ttu-id="26530-109">Zorg ervoor dat het apparaat is ingesteld op de juiste datum en tijd.</span><span class="sxs-lookup"><span data-stu-id="26530-109">Make sure that the device is set to the correct date and time.</span></span>

- <span data-ttu-id="26530-110">Schakel over naar een ander WIFI- of mobiel netwerk op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="26530-110">Switch to a different WIFI or cellular network on the device.</span></span>

- <span data-ttu-id="26530-111">Voor Android- of iOS-apparaten verwijdert en installeert u de Intune-bedrijfsportal app op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="26530-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="26530-112">iOS-telefoon of -tablet</span><span class="sxs-lookup"><span data-stu-id="26530-112">iOS phone or tablet</span></span>

- <span data-ttu-id="26530-113">Zorg ervoor dat u een APN-certificaat hebt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="26530-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="26530-114">Zie Een APN-certificaat maken voor [iOS-apparaten](create-an-apns-certificate-for-ios-devices.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="26530-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>

- <span data-ttu-id="26530-115">In **Instellingen**   >  **Algemeen**   >  **profiel (of Apparaatbeheer)** moet u ervoor zorgen dat een beheerprofiel nog niet is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="26530-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="26530-116">Als dit het is, verwijdert u het.</span><span class="sxs-lookup"><span data-stu-id="26530-116">If it is, remove it.</span></span>

- <span data-ttu-id="26530-117">Als u het foutbericht 'Apparaat kan zich niet registreren' ziet, meld u zich aan bij Microsoft 365 en zorg er dan voor dat er een licentie met Exchange Online is toegewezen aan de gebruiker die is aangemeld bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="26530-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="26530-118">Als u het foutbericht 'Profiel is niet geïnstalleerd' ziet, probeert u een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="26530-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>

    - <span data-ttu-id="26530-119">Zorg ervoor dat Safari de standaardbrowser op het apparaat is en dat cookies niet zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="26530-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>

    - <span data-ttu-id="26530-120">Start het apparaat opnieuw op en navigeer naar portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="26530-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="26530-121">Meld u aan met uw Microsoft 365 en wachtwoord en probeer het profiel handmatig te installeren.</span><span class="sxs-lookup"><span data-stu-id="26530-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>

## <a name="windows-rt"></a><span data-ttu-id="26530-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="26530-122">Windows RT</span></span>

- <span data-ttu-id="26530-123">Zorg ervoor dat uw domein is ingesteld in Microsoft 365 om te werken met Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="26530-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="26530-124">Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="26530-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="26530-125">Zorg ervoor dat de gebruiker **In-aan** kiest   in plaats van **Deelnemen.**</span><span class="sxs-lookup"><span data-stu-id="26530-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>

## <a name="windows-10-pc"></a><span data-ttu-id="26530-126">Windows 10 Pc</span><span class="sxs-lookup"><span data-stu-id="26530-126">Windows 10 PC</span></span>

- <span data-ttu-id="26530-127">Zorg ervoor dat uw domein is ingesteld in Microsoft 365 om te werken met Basismobiliteit en Beveiliging.</span><span class="sxs-lookup"><span data-stu-id="26530-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="26530-128">Zie Basismobiliteit en beveiliging instellen voor [meer informatie.](set-up.md)</span><span class="sxs-lookup"><span data-stu-id="26530-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="26530-129">Tenzij u Azure Active Directory Premium hebt, moet u ervoor zorgen dat de gebruiker Alleen registreren **voor Apparaatbeheer** kiest in plaats van dat   u Verbinding maken. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="26530-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="26530-130">Android-telefoon of -tablet</span><span class="sxs-lookup"><span data-stu-id="26530-130">Android phone or tablet</span></span>

- <span data-ttu-id="26530-131">Zorg ervoor dat het apparaat Android 4.4 of hoger gebruikt.</span><span class="sxs-lookup"><span data-stu-id="26530-131">Make sure the device is running Android 4.4 or later.</span></span>

- <span data-ttu-id="26530-132">Zorg ervoor dat Chrome up-to-date is en is ingesteld als de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="26530-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>

- <span data-ttu-id="26530-133">Als u het foutbericht 'We kunnen dit apparaat niet registreren' ziet, meld u dan aan bij Microsoft 365 en zorg ervoor dat er een licentie met Exchange Online is toegewezen aan de gebruiker die is aangemeld bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="26530-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>

- <span data-ttu-id="26530-134">Controleer het systeemsysteemgebied op het apparaat om te zien of er vereiste acties van eindgebruikers in behandeling zijn en als dat het geval is, voltooit u de acties.</span><span class="sxs-lookup"><span data-stu-id="26530-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>