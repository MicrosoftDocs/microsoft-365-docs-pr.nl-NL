---
title: Problemen oplossen met eenvoudige mobiliteit en beveiliging
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
description: Voer de volgende stappen uit om eenvoudige problemen met mobiliteit en beveiliging op te sporen
ms.openlocfilehash: 43e7533e598f769dd5f2bcae28c4252f96a9be76
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430131"
---
# <a name="troubleshoot-basic-mobility-and-security"></a><span data-ttu-id="b67b0-103">Problemen oplossen met eenvoudige mobiliteit en beveiliging</span><span class="sxs-lookup"><span data-stu-id="b67b0-103">Troubleshoot Basic Mobility and Security</span></span>

<span data-ttu-id="b67b0-104">Als u problemen ondervindt wanneer u een apparaat wilt registreren bij basis mobiliteit en beveiliging, voert u deze stappen uit om het probleem op te lossen.</span><span class="sxs-lookup"><span data-stu-id="b67b0-104">If you're running into issues when you try to enroll a device in Basic Mobility and Security, try the steps here to track down the problem.</span></span> <span data-ttu-id="b67b0-105">Als het probleem niet is verholpen door de algemene stappen, raadpleegt u een van de volgende gedeelten met specifieke stappen voor uw apparaattype.</span><span class="sxs-lookup"><span data-stu-id="b67b0-105">If the general steps don't fix the issue, see one of the later sections with specific steps for your device type.</span></span>

## <a name="steps-to-try-first"></a><span data-ttu-id="b67b0-106">Stappen om eerst te proberen</span><span class="sxs-lookup"><span data-stu-id="b67b0-106">Steps to try first</span></span>

<span data-ttu-id="b67b0-107">Controleer eerst het volgende:</span><span class="sxs-lookup"><span data-stu-id="b67b0-107">To start, check the following:</span></span>

- <span data-ttu-id="b67b0-108">Controleer of het apparaat niet al is geregistreerd bij een andere provider voor mobiel Apparaatbeheer, zoals intune.</span><span class="sxs-lookup"><span data-stu-id="b67b0-108">Make sure that the device is not already enrolled with another mobile device management provider, such as Intune.</span></span>
    
- <span data-ttu-id="b67b0-109">Controleer of het apparaat is ingesteld op de juiste datum en tijd.</span><span class="sxs-lookup"><span data-stu-id="b67b0-109">Make sure that the device is set to the correct date and time.</span></span>
    
- <span data-ttu-id="b67b0-110">Overschakelen naar een ander WIFI-of mobiel netwerk op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="b67b0-110">Switch to a different WIFI or cellular network on the device.</span></span>
    
- <span data-ttu-id="b67b0-111">Voor Android-of iOS-apparaten verwijdert u de app intune Company portal van het apparaat en installeert u deze opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b67b0-111">For Android or iOS devices, uninstall and reinstall the Intune Company Portal app on the device.</span></span> 

## <a name="ios-phone-or-tablet"></a><span data-ttu-id="b67b0-112">iOS-telefoon of-Tablet</span><span class="sxs-lookup"><span data-stu-id="b67b0-112">iOS phone or tablet</span></span>

- <span data-ttu-id="b67b0-113">Zorg ervoor dat u een APNs-certificaat hebt ingesteld.</span><span class="sxs-lookup"><span data-stu-id="b67b0-113">Make sure that you've set up an APNs certificate.</span></span> <span data-ttu-id="b67b0-114">Zie [een APNs-certificaat voor IOS-apparaten maken](create-an-apns-certificate-for-ios-devices.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b67b0-114">For more info, see [Create an APNs Certificate for iOS devices](create-an-apns-certificate-for-ios-devices.md).</span></span>
    
- <span data-ttu-id="b67b0-115"> *\*Settings**   > Zorg dat in het algemeen profiel van de instelling *\*Algemeen**   >  *\*(of Apparaatbeheer)** een management profiel nog niet is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="b67b0-115">In **Settings** > **General** > **Profile (or Device Management)**, make sure that a Management Profile is not already installed.</span></span> <span data-ttu-id="b67b0-116">Als dat het geval is, verwijdert u het bestand.</span><span class="sxs-lookup"><span data-stu-id="b67b0-116">If it is, remove it.</span></span>
    
- <span data-ttu-id="b67b0-117">Als u het foutbericht "apparaat niet geregistreerd" ziet, meldt u zich aan bij Microsoft 365 en controleert u of een licentie voor Exchange Online is toegewezen aan de gebruiker die zich bij het apparaat heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="b67b0-117">If you see the error message, "Device failed to enroll," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="b67b0-118">Als het volgende foutbericht wordt weergegeven: "profiel kan niet worden geïnstalleerd", kunt u een van de volgende oplossingen proberen:</span><span class="sxs-lookup"><span data-stu-id="b67b0-118">If you see the error message, "Profile failed to install," try one of the following:</span></span>
    
    - <span data-ttu-id="b67b0-119">Zorg ervoor dat Safari de standaardbrowser is op het apparaat en dat cookies niet zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="b67b0-119">Make sure that Safari is the default browser on the device, and that cookies are not disabled.</span></span>
    
    - <span data-ttu-id="b67b0-120">Start het apparaat opnieuw op en ga naar portal.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="b67b0-120">Reboot the device, and then navigate to portal.manage.microsoft.com.</span></span> <span data-ttu-id="b67b0-121">Meld u aan met uw gebruikers-ID en wachtwoord voor Microsoft 365 en installeer het profiel handmatig.</span><span class="sxs-lookup"><span data-stu-id="b67b0-121">Sign in with your Microsoft 365 user ID and password, and attempt to install the profile manually.</span></span>    

## <a name="windows-rt"></a><span data-ttu-id="b67b0-122">Windows RT</span><span class="sxs-lookup"><span data-stu-id="b67b0-122">Windows RT</span></span>

- <span data-ttu-id="b67b0-123">Zorg ervoor dat uw domein is ingesteld in Microsoft 365, zodat dit werkt met basis mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="b67b0-123">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="b67b0-124">Zie [eenvoudige mobiliteit en beveiliging instellen](set-up.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b67b0-124">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="b67b0-125">Zorg ervoor dat de gebruiker inschakelen kiest **Turn On**   in plaats van deel te **nemen**.</span><span class="sxs-lookup"><span data-stu-id="b67b0-125">Make sure that the user is choosing **Turn On** rather than choosing **Join**.</span></span>    

## <a name="windows-10-pc"></a><span data-ttu-id="b67b0-126">PC met Windows 10</span><span class="sxs-lookup"><span data-stu-id="b67b0-126">Windows 10 PC</span></span>

- <span data-ttu-id="b67b0-127">Zorg ervoor dat uw domein is ingesteld in Microsoft 365, zodat dit werkt met basis mobiliteit en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="b67b0-127">Make sure that your domain is set up in Microsoft 365 to work with Basic Mobility and Security.</span></span> <span data-ttu-id="b67b0-128">Zie [eenvoudige mobiliteit en beveiliging instellen](set-up.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b67b0-128">For more info, see [Set up Basic Mobility and Security](set-up.md).</span></span>
    
- <span data-ttu-id="b67b0-129">Tenzij u Azure Active Directory Premium hebt, moet u ervoor zorgen dat de gebruiker **alleen registreren in Apparaatbeheer**kiest in   plaats van **verbinding maken**te kiezen.</span><span class="sxs-lookup"><span data-stu-id="b67b0-129">Unless you have Azure Active Directory Premium, make sure that the user is choosing **Enroll in Device Management only** rather than choosing **Connect**.</span></span>

## <a name="android-phone-or-tablet"></a><span data-ttu-id="b67b0-130">Android-telefoon of-Tablet</span><span class="sxs-lookup"><span data-stu-id="b67b0-130">Android phone or tablet</span></span>

- <span data-ttu-id="b67b0-131">Controleer of op het apparaat Android 4,4 of hoger wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="b67b0-131">Make sure the device is running Android 4.4 or later.</span></span>
    
- <span data-ttu-id="b67b0-132">Zorg dat chroom up-to-date is en is ingesteld als de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="b67b0-132">Make sure that Chrome is up to date and is set as the default browser.</span></span>
    
- <span data-ttu-id="b67b0-133">Als u het foutbericht "dit apparaat kan niet worden geregistreerd" ziet, meldt u zich aan bij Microsoft 365 en controleert u of een licentie voor Exchange Online is toegewezen aan de gebruiker die zich bij het apparaat heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="b67b0-133">If you see the error message, "We couldn't enroll this device," sign in to Microsoft 365 and make sure that a license that includes Exchange Online has been assigned to the user who is signed in to the device.</span></span>
    
- <span data-ttu-id="b67b0-134">Controleer het systeemvak op het apparaat om te zien of de vereiste taken voor eindgebruikers in behandeling zijn en of ze de acties kunnen voltooien.</span><span class="sxs-lookup"><span data-stu-id="b67b0-134">Check the Notification Area on the device to see if any required end-user actions are pending, and if they are, complete the actions.</span></span>