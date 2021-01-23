---
title: InTune-bedrijfs portal installeren op apparaten
description: Info over het installeren van de bedrijfsportal-app op Microsoft beheerde bureaublad apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Company Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939282"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="2d67c-104">InTune-bedrijfs portal installeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="2d67c-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="2d67c-105">Voor Microsoft Managed Desktop moet de IT-beheerder intune Company Portal installeren voor hun gebruikers met Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="2d67c-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="2d67c-106">Hier volgen enkele voordelen voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="2d67c-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="2d67c-107">Gebruikers hebben één locatie om de beschikbare toepassingen te zoeken en te installeren.</span><span class="sxs-lookup"><span data-stu-id="2d67c-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="2d67c-108">IT-beheerders kunnen toepassingen organiseren op basis van categorieën voor hun gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2d67c-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="2d67c-109">Voor sommige toepassingen (zoals Microsoft Project en Microsoft Visio) is bedrijfs portal vereist voor de implementatie met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="2d67c-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="2d67c-110">IT-beheerders kunnen de bedrijfs portal voor hun organisatie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="2d67c-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="2d67c-111">Dit omvat merk afbeelding, toevoegen in lokale ondersteunings contactpersonen, en meer.</span><span class="sxs-lookup"><span data-stu-id="2d67c-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="2d67c-112">Zie [de Microsoft intune Company Portal-app configureren](https://docs.microsoft.com/intune/company-portal-app)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2d67c-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="2d67c-113">In dit onderwerp worden de stappen beschreven voor de implementatie van de intune-bedrijfs portal naar Microsoft beheerde bureaubladgebruikers.</span><span class="sxs-lookup"><span data-stu-id="2d67c-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="2d67c-114">Het algehele proces ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="2d67c-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="2d67c-115">Bedrijfs portal in Microsoft Store voor bedrijven kopen en synchroniseren met intune</span><span class="sxs-lookup"><span data-stu-id="2d67c-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="2d67c-116">Bedrijfs portal aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="2d67c-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="2d67c-117">Wijziging communiceren met uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="2d67c-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="2d67c-118">Stap 1: de bedrijfs portal van Microsoft Store voor bedrijven kopen en synchroniseren met intune</span><span class="sxs-lookup"><span data-stu-id="2d67c-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="2d67c-119">Voor informatie over het aanschaffen van de apps en het synchroniseren met intune raadpleegt u [Microsoft Store for Business-Apps](deploy-apps.md#msfb-apps) in *apps implementeren voor Microsoft Managed Desktop devices*.</span><span class="sxs-lookup"><span data-stu-id="2d67c-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="2d67c-120">Dit onderwerp bevat informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="2d67c-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="2d67c-121">Bedrijfs portal kopen via Microsoft Store voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="2d67c-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="2d67c-122">Synchronisatie tussen intune en Microsoft Store voor bedrijven afdwingen</span><span class="sxs-lookup"><span data-stu-id="2d67c-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="2d67c-123">Actieve synchronisatie tussen intune en Microsoft Store voor bedrijven controleren</span><span class="sxs-lookup"><span data-stu-id="2d67c-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="2d67c-124">Stap 2-de bedrijfs portal aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="2d67c-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="2d67c-125">Als u de registratie volgt in Microsoft Managed Desktop, wordt de bedrijfs portal automatisch geïmplementeerd voor uw Tenant en installeert u de app op Microsoft beheerde bureaublad apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2d67c-125">Following your enrollment in Microsoft Managed Desktop, Microsoft Managed Desktop Operations will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="2d67c-126">Stap 3: de wijziging doorgeven aan uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="2d67c-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="2d67c-127">Als IT-beheerder voor uw organisatie, is het belangrijk om uw gebruikers te laten weten hoe ze de bedrijfs portal in uw organisatie kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2d67c-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="2d67c-128">Microsoft Managed Desktop adviseert:</span><span class="sxs-lookup"><span data-stu-id="2d67c-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="2d67c-129">Stappen voor het installeren van toepassingen vanuit de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="2d67c-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="2d67c-130">Zie [apps op uw apparaat installeren en delen](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2d67c-130">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="2d67c-131">Hoe u aanvragen naar IT-beheerders verzendt voor toepassingen die momenteel niet beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="2d67c-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="2d67c-132">Zie [een app voor werk of school aanvragen](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2d67c-132">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2d67c-133">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="2d67c-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="2d67c-134">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="2d67c-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="2d67c-135">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="2d67c-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="2d67c-136">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="2d67c-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="2d67c-137">InTune Company Portal (dit onderwerp) implementeren</span><span class="sxs-lookup"><span data-stu-id="2d67c-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="2d67c-138">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="2d67c-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="2d67c-139">Apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="2d67c-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2d67c-140">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="2d67c-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="2d67c-141">Apps implementeren</span><span class="sxs-lookup"><span data-stu-id="2d67c-141">Deploy apps</span></span>](deploy-apps.md)
