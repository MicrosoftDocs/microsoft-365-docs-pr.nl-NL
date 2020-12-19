---
title: Toegang tot de Microsoft 365 Defender-Api's
description: Meer informatie over het openen van de Microsoft 365 Defender-Api's
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
ms.openlocfilehash: 5e01aaf2ee9255fd909b26278346fd4ccf54729a
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719236"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="7dd17-104">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="7dd17-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="7dd17-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7dd17-105">**Applies to:**</span></span>

- <span data-ttu-id="7dd17-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7dd17-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7dd17-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="7dd17-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7dd17-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="7dd17-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7dd17-109">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="7dd17-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="7dd17-110">Met deze Api's kunt u werkstromen automatiseren en volledig gebruik maken van de mogelijkheden van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7dd17-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="7dd17-111">In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="7dd17-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="7dd17-112">Een Azure Active Directory-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="7dd17-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="7dd17-113">Een toegangstoken verkrijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="7dd17-113">Get an access token using this application</span></span>
- <span data-ttu-id="7dd17-114">Het token gebruiken voor toegang tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="7dd17-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="7dd17-115">Voor API-toegang is OAuth 2.0-authenticatie vereist.</span><span class="sxs-lookup"><span data-stu-id="7dd17-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="7dd17-116">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="7dd17-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="7dd17-117">Wanneer u deze stappen hebt uitgevoerd, bent u klaar om toegang te krijgen tot de Microsoft 365 Defender-API met een bepaalde context.</span><span class="sxs-lookup"><span data-stu-id="7dd17-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="7dd17-118">Toepassingscontext (aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="7dd17-118">Application context (Recommended)</span></span>

<span data-ttu-id="7dd17-119">Gebruik deze context voor apps die zonder een aangemelde gebruiker worden uitgevoerd, zoals Achtergrondservices of demonies.</span><span class="sxs-lookup"><span data-stu-id="7dd17-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="7dd17-120">Maak een Azure Active Directory-webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="7dd17-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="7dd17-121">Wijs de gewenste machtigingen voor de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="7dd17-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="7dd17-122">Een sleutel voor de toepassing maken.</span><span class="sxs-lookup"><span data-stu-id="7dd17-122">Create a key for the application.</span></span>
4. <span data-ttu-id="7dd17-123">U ontvangt een beveiligingstoken met behulp van de toepassing en de bijbehorende sleutel.</span><span class="sxs-lookup"><span data-stu-id="7dd17-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="7dd17-124">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7dd17-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7dd17-125">Zie **[een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md)** voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7dd17-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="7dd17-126">Gebruikerscontext</span><span class="sxs-lookup"><span data-stu-id="7dd17-126">User context</span></span>

<span data-ttu-id="7dd17-127">Gebruik deze context om acties uit te voeren namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="7dd17-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="7dd17-128">Maak een native Azure Active Directory-toepassing.</span><span class="sxs-lookup"><span data-stu-id="7dd17-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="7dd17-129">Wijs de gewenste machtiging voor de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="7dd17-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="7dd17-130">U ontvangt een beveiligingstoken met de gebruikersreferenties voor de toepassing.</span><span class="sxs-lookup"><span data-stu-id="7dd17-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="7dd17-131">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7dd17-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7dd17-132">Zie voor meer informatie **[een app maken om toegang te krijgen tot Microsoft 365-api's voor een gebruiker](api-create-app-user-context.md)**.</span><span class="sxs-lookup"><span data-stu-id="7dd17-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="7dd17-133">Partner context</span><span class="sxs-lookup"><span data-stu-id="7dd17-133">Partner context</span></span>

<span data-ttu-id="7dd17-134">Gebruik deze context wanneer u een app moet verlenen aan veel gebruikers in [meerdere tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span><span class="sxs-lookup"><span data-stu-id="7dd17-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="7dd17-135">Maak een Azure Active Directory-multi-tenant toepassing.</span><span class="sxs-lookup"><span data-stu-id="7dd17-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="7dd17-136">Wijs de gewenste machtiging voor de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="7dd17-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="7dd17-137">Neem de [beheerder toestemming](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) voor de app van elke Tenant.</span><span class="sxs-lookup"><span data-stu-id="7dd17-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="7dd17-138">U ontvangt een beveiligingstoken met behulp van gebruikersreferenties op basis van de Tenant-ID van een klant.</span><span class="sxs-lookup"><span data-stu-id="7dd17-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="7dd17-139">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="7dd17-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="7dd17-140">Zie voor meer informatie **[een app met partner toegang maken voor Microsoft 365 Defender-api's](api-partner-access.md)**.</span><span class="sxs-lookup"><span data-stu-id="7dd17-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7dd17-141">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="7dd17-141">Related articles</span></span>

- [<span data-ttu-id="7dd17-142">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="7dd17-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="7dd17-143">OAuth 2,0-autorisatie voor gebruikersaanmelding en API-toegang</span><span class="sxs-lookup"><span data-stu-id="7dd17-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="7dd17-144">Geheimen in uw server-apps beheren met Azure-sleutel kluis</span><span class="sxs-lookup"><span data-stu-id="7dd17-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="7dd17-145">Een ' Hallo wereld '-toepassing maken waarmee de Microsoft 365-Api's worden geopend</span><span class="sxs-lookup"><span data-stu-id="7dd17-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
