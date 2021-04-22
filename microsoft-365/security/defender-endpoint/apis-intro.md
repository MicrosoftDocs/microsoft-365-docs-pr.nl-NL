---
title: Toegang tot de API's voor Microsoft Defender voor Eindpunt
ms.reviewer: ''
description: Meer informatie over hoe u API's kunt gebruiken om werkstromen te automatiseren en te innoveren op basis van de mogelijkheden van Microsoft Defender voor eindpunten
keywords: api's, api, wdatp, open api, microsoft defender voor endpoint api, microsoft defender atp, openbare api, ondersteunde api's, waarschuwingen, apparaat, gebruiker, domein, ip, bestand, geavanceerd zoeken, query
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
ms.openlocfilehash: 843bd953b97f29a5b9c80fc44a9b19fae60a6fa7
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939764"
---
# <a name="access-the-microsoft-defender-for-endpoint-apis"></a><span data-ttu-id="4483b-104">Toegang tot de API's voor Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4483b-104">Access the Microsoft Defender for Endpoint APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4483b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4483b-105">**Applies to:**</span></span>
- [<span data-ttu-id="4483b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4483b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4483b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4483b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="4483b-108">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4483b-108">**Applies to:**</span></span> 
- [<span data-ttu-id="4483b-109">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4483b-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

> <span data-ttu-id="4483b-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4483b-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="4483b-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4483b-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



<span data-ttu-id="4483b-112">In Defender voor Eindpunt worden veel van de gegevens en acties via een set programmatische API's beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="4483b-112">Defender for Endpoint exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="4483b-113">Met deze API's kunt u werkstromen automatiseren en innoveren op basis van De mogelijkheden van Defender voor eindpunten.</span><span class="sxs-lookup"><span data-stu-id="4483b-113">Those APIs will enable you to automate workflows and innovate based on Defender for Endpoint capabilities.</span></span> <span data-ttu-id="4483b-114">Voor de API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="4483b-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="4483b-115">Zie [OAuth 2.0 Autorisatiecodestroom](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4483b-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="4483b-116">Bekijk deze video voor een kort overzicht van de API's van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4483b-116">Watch this video for a quick overview of Defender for Endpoint's APIs.</span></span> 
>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4d73M]

<span data-ttu-id="4483b-117">Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="4483b-117">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="4483b-118">Een AAD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="4483b-118">Create an AAD application</span></span>
- <span data-ttu-id="4483b-119">Een toegangs token krijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="4483b-119">Get an access token using this application</span></span>
- <span data-ttu-id="4483b-120">Het token gebruiken om toegang te krijgen tot Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="4483b-120">Use the token to access Defender for Endpoint API</span></span>


<span data-ttu-id="4483b-121">U hebt toegang tot Defender for Endpoint API met **Toepassingscontext** **of Gebruikerscontext.**</span><span class="sxs-lookup"><span data-stu-id="4483b-121">You can access Defender for Endpoint API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="4483b-122">**Toepassingscontext: (Aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="4483b-122">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="4483b-123">Gebruikt door apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is.</span><span class="sxs-lookup"><span data-stu-id="4483b-123">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="4483b-124">bijvoorbeeld apps die als achtergrondservices of daemons worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4483b-124">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="4483b-125">Stappen die moeten worden genomen om toegang te krijgen tot Defender voor Endpoint API met toepassingscontext:</span><span class="sxs-lookup"><span data-stu-id="4483b-125">Steps that need to be taken to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="4483b-126">Maak een AAD-webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="4483b-126">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="4483b-127">Wijs de gewenste machtiging toe aan de toepassing, bijvoorbeeld 'Leeswaarschuwingen', 'Machines isoleren'.</span><span class="sxs-lookup"><span data-stu-id="4483b-127">Assign the desired permission to the application, for example, 'Read Alerts', 'Isolate Machines'.</span></span> 
  3. <span data-ttu-id="4483b-128">Maak een sleutel voor deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="4483b-128">Create a key for this Application.</span></span>
  4. <span data-ttu-id="4483b-129">Get token using the application with its key.</span><span class="sxs-lookup"><span data-stu-id="4483b-129">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="4483b-130">Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="4483b-130">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="4483b-131">Zie Toegang krijgen met [toepassingscontext voor meer informatie.](exposed-apis-create-app-webapp.md)</span><span class="sxs-lookup"><span data-stu-id="4483b-131">For more information, see [Get access with application context](exposed-apis-create-app-webapp.md).</span></span>


- <span data-ttu-id="4483b-132">**Gebruikerscontext:**</span><span class="sxs-lookup"><span data-stu-id="4483b-132">**User Context:**</span></span> <br>
    <span data-ttu-id="4483b-133">Wordt gebruikt om acties uit te voeren in de API namens een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="4483b-133">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="4483b-134">Stappen die u moet ondernemen om toegang te krijgen tot Defender voor Endpoint API met toepassingscontext:</span><span class="sxs-lookup"><span data-stu-id="4483b-134">Steps to take to access Defender for Endpoint API with application context:</span></span>

  1. <span data-ttu-id="4483b-135">Maak AAD Native-Application.</span><span class="sxs-lookup"><span data-stu-id="4483b-135">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="4483b-136">Wijs de gewenste machtiging toe aan de toepassing, zoals 'Leeswaarschuwingen', 'Isolate Machines' enzovoort.</span><span class="sxs-lookup"><span data-stu-id="4483b-136">Assign the desired permission to the application, e.g 'Read Alerts', 'Isolate Machines' etc.</span></span> 
  3. <span data-ttu-id="4483b-137">Get token using the application with user credentials.</span><span class="sxs-lookup"><span data-stu-id="4483b-137">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="4483b-138">Het token gebruiken om toegang te krijgen tot de Microsoft Defender for Endpoint API</span><span class="sxs-lookup"><span data-stu-id="4483b-138">Use the token to access the Microsoft Defender for Endpoint API</span></span>

     <span data-ttu-id="4483b-139">Zie Toegang krijgen met [gebruikerscontext voor meer informatie.](exposed-apis-create-app-nativeapp.md)</span><span class="sxs-lookup"><span data-stu-id="4483b-139">For more information, see [Get access with user context](exposed-apis-create-app-nativeapp.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="4483b-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4483b-140">Related topics</span></span>
- [<span data-ttu-id="4483b-141">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="4483b-141">Microsoft Defender for Endpoint APIs</span></span>](exposed-apis-list.md)
- [<span data-ttu-id="4483b-142">Toegang tot Microsoft Defender voor eindpunt met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="4483b-142">Access Microsoft Defender for Endpoint with application context</span></span>](exposed-apis-create-app-webapp.md)
- [<span data-ttu-id="4483b-143">Toegang tot Microsoft Defender voor Eindpunt met gebruikerscontext</span><span class="sxs-lookup"><span data-stu-id="4483b-143">Access Microsoft Defender for Endpoint with user context</span></span>](exposed-apis-create-app-nativeapp.md)
