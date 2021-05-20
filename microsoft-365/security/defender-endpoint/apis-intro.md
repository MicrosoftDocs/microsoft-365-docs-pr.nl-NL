---
title: Toegang tot de API's voor Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Meer informatie over hoe u API's kunt gebruiken om workflows te automatiseren en te innoveren op basis van Microsoft Defender for Endpoint-mogelijkheden
keywords: api's, api, wdatp, open api, microsoft defender voor endpoint api, microsoft defender atp, public api, ondersteunde api's, alerts, device, user, domain, ip, file, advanced hunting, query
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a91a401d5d57c7757bc043178c95dc42e7733b41
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571827"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="c8f50-104">Toegang tot de API's voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c8f50-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c8f50-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c8f50-105">**Applies to:**</span></span>
- [<span data-ttu-id="c8f50-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c8f50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c8f50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8f50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="c8f50-108">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c8f50-108">**Applies to:**</span></span> 
- [<span data-ttu-id="c8f50-109">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c8f50-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="c8f50-110">Wilt u Microsoft Defender voor Endpoint ervaren?</span><span class="sxs-lookup"><span data-stu-id="c8f50-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c8f50-111">Meld je aan voor een gratis proefperiode.</span><span class="sxs-lookup"><span data-stu-id="c8f50-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="c8f50-112">Defender for Endpoint legt veel van zijn gegevens en acties bloot via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="c8f50-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="c8f50-113">Met deze API's kunt u workflows automatiseren en innoveren op basis van Defender for Endpoint-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="c8f50-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="c8f50-114">Voor de API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="c8f50-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="c8f50-115">Zie [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8f50-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="c8f50-116">Bekijk deze video voor een snel overzicht van de API's van Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="c8f50-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="c8f50-117">Over het algemeen moet u de volgende stappen uitvoeren om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c8f50-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="c8f50-118">Een [AAD-toepassing maken](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span><span class="sxs-lookup"><span data-stu-id="c8f50-118">Create an [AAD application](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-nativeapp)</span></span>
- <span data-ttu-id="c8f50-119">Een toegangs token ophalen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="c8f50-119">Get an access token using this application</span></span>
- <span data-ttu-id="c8f50-120">Het token gebruiken om toegang te krijgen tot Defender voor Endpoint API</span><span class="sxs-lookup"><span data-stu-id="c8f50-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="c8f50-121">U hebt toegang tot Defender for Endpoint API met **toepassingscontext** of **gebruikerscontext**.</span><span class="sxs-lookup"><span data-stu-id="c8f50-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="c8f50-122">**Toepassingscontext: (Aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="c8f50-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="c8f50-123">Wordt gebruikt door apps die worden uitgevoerd zonder dat er een aangemelde gebruiker aanwezig is.</span><span class="sxs-lookup"><span data-stu-id="c8f50-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="c8f50-124">bijvoorbeeld apps die worden uitgevoerd als achtergrondservices of daemons.</span><span class="sxs-lookup"><span data-stu-id="c8f50-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="c8f50-125">Stappen die moeten worden uitgevoerd om toegang te krijgen tot Defender for Endpoint API met toepassings context:</span><span class="sxs-lookup"><span data-stu-id="c8f50-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="c8f50-126">Maak een AAD-webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="c8f50-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="c8f50-127">Wijs de gewenste machtiging toe aan de toepassing, bijvoorbeeld 'Lees waarschuwingen', 'Isolate Machines'.</span><span class="sxs-lookup"><span data-stu-id="c8f50-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="c8f50-128">Maak een sleutel voor deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="c8f50-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="c8f50-129">Token ophalen met behulp van de toepassing met de sleutel.</span><span class="sxs-lookup"><span data-stu-id="c8f50-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="c8f50-130">Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="c8f50-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="c8f50-131">Zie [Toegang krijgen met toepassings context voor](exposed-apis-create-app-webapp.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8f50-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="c8f50-132">**Gebruikerscontext:**</span><span class="sxs-lookup"><span data-stu-id="c8f50-132">**User Context:**</span></span> <br>
    <span data-ttu-id="c8f50-133">Wordt gebruikt om acties uit te voeren in de API namens een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c8f50-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="c8f50-134">Stappen die u moet nemen om toegang te krijgen tot Defender for Endpoint API met toepassings context:</span><span class="sxs-lookup"><span data-stu-id="c8f50-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="c8f50-135">Maak een AAD-native toepassing.</span><span class="sxs-lookup"><span data-stu-id="c8f50-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="c8f50-136">Wijs de gewenste toestemming toe aan de applicatie, bijvoorbeeld 'Leeswaarschuwingen', 'Isolate Machines' enz.</span><span class="sxs-lookup"><span data-stu-id="c8f50-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="c8f50-137">Token ophalen met behulp van de toepassing met gebruikers referenties.</span><span class="sxs-lookup"><span data-stu-id="c8f50-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="c8f50-138">Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="c8f50-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="c8f50-139">Zie [Toegang krijgen met gebruikerscontext voor](exposed-apis-create-app-nativeapp.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c8f50-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="c8f50-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c8f50-140">Related topics</span></span>
- [<span data-ttu-id="c8f50-141">Microsoft Defender voor endpoint-API's</span><span class="sxs-lookup"><span data-stu-id="c8f50-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="c8f50-142">Toegang tot Microsoft Defender voor eindpunt met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="c8f50-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="c8f50-143">Toegang tot Microsoft Defender voor eindpunt met gebruikerscontext</span><span class="sxs-lookup"><span data-stu-id="c8f50-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
