---
title: Installatie Intune-bedrijfsportal op apparaten
description: Informatie over het installeren van de bedrijfsportal-app op Microsoft Managed Desktop apparaten
keywords: Microsoft Managed Desktop, Microsoft 365, Bedrijfsportal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086683"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="7e5f7-104">Installatie Intune-bedrijfsportal op apparaten</span><span class="sxs-lookup"><span data-stu-id="7e5f7-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="7e5f7-105">Microsoft Managed Desktop vereist dat IT-beheerders Intune-bedrijfsportal hun gebruikers installeren met Microsoft Managed Desktop apparaten.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="7e5f7-106">Hier zijn enkele voordelen voor uw organisatie:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="7e5f7-107">Gebruikers hebben één plek om te bladeren en beschikbare toepassingen te installeren.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="7e5f7-108">IT-beheerders kunnen toepassingen organiseren op categorieën voor hun gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="7e5f7-109">Sommige toepassingen (zoals Microsoft Project en Microsoft Visio) moeten Bedrijfsportal implementeren met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="7e5f7-110">IT-beheerders kunnen de Bedrijfsportal voor hun organisatie aanpassen.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="7e5f7-111">Dit omvat merkweergave, het toevoegen van lokale ondersteuningscontactcontacten en meer.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="7e5f7-112">Zie De app Configureren [Microsoft Intune Bedrijfsportal voor meer informatie.](/intune/company-portal-app)</span><span class="sxs-lookup"><span data-stu-id="7e5f7-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="7e5f7-113">In dit onderwerp wordt het proces voor het implementeren van de Intune-bedrijfsportal uw gebruikers Microsoft Managed Desktop documenten.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="7e5f7-114">Het totale proces ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="7e5f7-115">Aankoop Bedrijfsportal van Microsoft Store voor Bedrijven en synchroniseren met Intune</span><span class="sxs-lookup"><span data-stu-id="7e5f7-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="7e5f7-116">Uw Bedrijfsportal aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="7e5f7-117">Wijziging communiceren naar uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="7e5f7-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="7e5f7-118">Stap 1 - Koop Bedrijfsportal van Microsoft Store voor Bedrijven en synchroniseer met Intune</span><span class="sxs-lookup"><span data-stu-id="7e5f7-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="7e5f7-119">Zie voor meer informatie over hoe u de apps aanschaft en synchroniseert met Intune Microsoft Store voor Bedrijven [apps](deploy-apps.md#msfb-apps) implementeren naar *Microsoft Managed Desktop apparaten.*</span><span class="sxs-lookup"><span data-stu-id="7e5f7-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="7e5f7-120">In dit onderwerp vindt u informatie over het volgende:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="7e5f7-121">Aankoop Bedrijfsportal bij Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="7e5f7-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="7e5f7-122">Synchronisatie tussen Intune en Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="7e5f7-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="7e5f7-123">Actieve synchronisatie tussen Intune en Microsoft Store voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="7e5f7-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="7e5f7-124">Stap 2 - Een Bedrijfsportal aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="7e5f7-125">Na uw inschrijving in Microsoft Managed Desktop, implementeren we automatisch Bedrijfsportal tenant en installeren we de app op Microsoft Managed Desktop apparaten in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="7e5f7-126">Stap 3 - Wijziging communiceren naar uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="7e5f7-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="7e5f7-127">Als IT-beheerder voor uw organisatie is het belangrijk om uw gebruikers te laten weten hoe ze Bedrijfsportal gebruiken in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="7e5f7-128">Microsoft Managed Desktop raadt het volgende aan:</span><span class="sxs-lookup"><span data-stu-id="7e5f7-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="7e5f7-129">Stappen voor het installeren van toepassingen vanaf de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="7e5f7-130">Zie Apps installeren en delen op uw apparaat voor [meer informatie.](/intune-user-help/install-apps-cpapp-windows)</span><span class="sxs-lookup"><span data-stu-id="7e5f7-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="7e5f7-131">Aanvragen verzenden naar IT-beheerders voor toepassingen die momenteel niet beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="7e5f7-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="7e5f7-132">Zie Een app aanvragen voor werk of school voor [meer informatie.](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)</span><span class="sxs-lookup"><span data-stu-id="7e5f7-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="7e5f7-133">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="7e5f7-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="7e5f7-134">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="7e5f7-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="7e5f7-135">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="7e5f7-136">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="7e5f7-137">Implementatie Intune-bedrijfsportal (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="7e5f7-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="7e5f7-138">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="7e5f7-139">Apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="7e5f7-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="7e5f7-140">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="7e5f7-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="7e5f7-141">Apps implementeren</span><span class="sxs-lookup"><span data-stu-id="7e5f7-141">Deploy apps</span></span>](deploy-apps.md)
