---
title: Toegang tot de Microsoft Threat Protection-Api's
description: Lees hoe u toegang krijgt tot de Microsoft Threat Protection-Api's
keywords: Access, api's, toepassingscontext, gebruikerscontext, Aad-toepassing, toegangstoken
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bccf36f46121caceeb6dc6d97c126f48149d9426
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197879"
---
# <a name="access-the-microsoft-threat-protection-apis"></a><span data-ttu-id="0ee14-104">Toegang tot de Microsoft Threat Protection-Api's</span><span class="sxs-lookup"><span data-stu-id="0ee14-104">Access the Microsoft Threat Protection APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0ee14-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0ee14-105">**Applies to:**</span></span>
- <span data-ttu-id="0ee14-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0ee14-106">Microsoft Threat Protection</span></span>

>[!IMPORTANT] 
><span data-ttu-id="0ee14-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="0ee14-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="0ee14-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="0ee14-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


 <span data-ttu-id="0ee14-109">Microsoft Threat Protection geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="0ee14-109">Microsoft Threat Protection exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="0ee14-110">Met deze Api's kunt u werkstromen en innoveren automatiseren op basis van de mogelijkheden van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="0ee14-110">Those APIs will enable you to automate workflows and innovate based on  Microsoft Threat Protection capabilities.</span></span> <span data-ttu-id="0ee14-111">Voor API-toegang is OAuth 2.0-authenticatie vereist.</span><span class="sxs-lookup"><span data-stu-id="0ee14-111">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="0ee14-112">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="0ee14-112">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>


<span data-ttu-id="0ee14-113">In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="0ee14-113">In general, you'll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="0ee14-114">Een AAD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="0ee14-114">Create an AAD application</span></span>
- <span data-ttu-id="0ee14-115">Een toegangstoken verkrijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="0ee14-115">Get an access token using this application</span></span>
- <span data-ttu-id="0ee14-116">Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="0ee14-116">Use the token to access  Microsoft Threat Protection API</span></span>


<span data-ttu-id="0ee14-117">U kunt de Microsoft Threat Protection API met context van de **toepassing** of de **gebruikerscontext**openen.</span><span class="sxs-lookup"><span data-stu-id="0ee14-117">You can access  Microsoft Threat Protection API with **Application Context** or **User Context**.</span></span>

- <span data-ttu-id="0ee14-118">**Toepassings context: (aanbevolen)**</span><span class="sxs-lookup"><span data-stu-id="0ee14-118">**Application Context: (Recommended)**</span></span> <br>
    <span data-ttu-id="0ee14-119">Dit wordt gebruikt door apps die zonder een aangemelde gebruiker worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0ee14-119">Used by apps that run without a signed-in user present.</span></span> <span data-ttu-id="0ee14-120">apps die als achtergrondservice of demon worden uitgevoerd, bijvoorbeeld apps.</span><span class="sxs-lookup"><span data-stu-id="0ee14-120">for example, apps that run as background services or daemons.</span></span>

    <span data-ttu-id="0ee14-121">Stappen die u moet uitvoeren om de API Microsoft Threat Protection met toepassingscontext te openen:</span><span class="sxs-lookup"><span data-stu-id="0ee14-121">Steps that need to be taken to access  Microsoft Threat Protection API with application context:</span></span>

  1. <span data-ttu-id="0ee14-122">Maak een AAD-webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="0ee14-122">Create an AAD Web-Application.</span></span>
  2. <span data-ttu-id="0ee14-123">Wijs de gewenste machtiging toe aan het applicationFor-voorbeeld, **incident. Read. all**, **AdvancedHunting. Read. all**.</span><span class="sxs-lookup"><span data-stu-id="0ee14-123">Assign the desired permission to the applicationFor example, **Incident.Read.All**, **AdvancedHunting.Read.All**.</span></span> 
  3. <span data-ttu-id="0ee14-124">Maak een sleutel voor deze toepassing.</span><span class="sxs-lookup"><span data-stu-id="0ee14-124">Create a key for this Application.</span></span>
  4. <span data-ttu-id="0ee14-125">Token verkrijgen met behulp van de toepassing met de sleutel.</span><span class="sxs-lookup"><span data-stu-id="0ee14-125">Get token using the application with its key.</span></span>
  5. <span data-ttu-id="0ee14-126">Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="0ee14-126">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="0ee14-127">Zie voor meer informatie [toegang krijgen tot de context](api-create-app-web.md)van de toepassing.</span><span class="sxs-lookup"><span data-stu-id="0ee14-127">For more information, see [Get access with application context](api-create-app-web.md).</span></span>


- <span data-ttu-id="0ee14-128">**Gebruikers context:**</span><span class="sxs-lookup"><span data-stu-id="0ee14-128">**User Context:**</span></span> <br>
    <span data-ttu-id="0ee14-129">Wordt gebruikt voor het uitvoeren van acties in de API namens een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0ee14-129">Used to perform actions in the API on behalf of a user.</span></span>

    <span data-ttu-id="0ee14-130">Stappen die u moet uitvoeren om de API Microsoft Threat Protection met toepassingscontext te verkrijgen:</span><span class="sxs-lookup"><span data-stu-id="0ee14-130">Steps that needs to be taken to access  Microsoft Threat Protection API with application context:</span></span>
  1. <span data-ttu-id="0ee14-131">Maak een ingebouwde AAD-toepassing.</span><span class="sxs-lookup"><span data-stu-id="0ee14-131">Create AAD Native-Application.</span></span>
  2. <span data-ttu-id="0ee14-132">Wijs de gewenste machtiging voor de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="0ee14-132">Assign the desired permission to the application.</span></span> <span data-ttu-id="0ee14-133">Bijvoorbeeld **incident. Read**, **AdvancedHunting. Read**.</span><span class="sxs-lookup"><span data-stu-id="0ee14-133">For example, **Incident.Read**, **AdvancedHunting.Read**.</span></span>
  3. <span data-ttu-id="0ee14-134">Token verkrijgen met behulp van de toepassing met gebruikersreferenties.</span><span class="sxs-lookup"><span data-stu-id="0ee14-134">Get token using the application with user credentials.</span></span>
  4. <span data-ttu-id="0ee14-135">Het token gebruiken om toegang te krijgen tot de Microsoft Threat Protection API</span><span class="sxs-lookup"><span data-stu-id="0ee14-135">Use the token to access  Microsoft Threat Protection API</span></span>

     <span data-ttu-id="0ee14-136">Zie [toegang krijgen met gebruikerscontext](api-create-app-user-context.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0ee14-136">For more information, see [Get access with user context](api-create-app-user-context.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="0ee14-137">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0ee14-137">Related topics</span></span>
- [<span data-ttu-id="0ee14-138">Api's voor Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="0ee14-138">Microsoft Threat Protection APIs</span></span>](api-supported.md)
- [<span data-ttu-id="0ee14-139">Toegang tot Microsoft Threat Protection met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="0ee14-139">Access  Microsoft Threat Protection with application context</span></span>](api-create-app-web.md)
- [<span data-ttu-id="0ee14-140">Microsoft Threat Protection met gebruikerscontext openen</span><span class="sxs-lookup"><span data-stu-id="0ee14-140">Access  Microsoft Threat Protection with user context</span></span>](api-create-app-user-context.md)
