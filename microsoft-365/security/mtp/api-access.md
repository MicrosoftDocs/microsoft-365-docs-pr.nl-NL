---
title: Toegang tot de Microsoft 365 Defender-API's
description: Informatie over toegang tot de Microsoft 365 Defender-API's
keywords: access, apis, toepassingscontext, gebruikerscontext, aad-toepassing, toegang token
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: ea787adfba0afb425da5f6ea0f6609f96e06b378
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932152"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="136b5-104">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="136b5-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="136b5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="136b5-105">**Applies to:**</span></span>

- <span data-ttu-id="136b5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="136b5-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="136b5-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="136b5-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="136b5-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="136b5-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="136b5-109">Microsoft 365 Defender laat veel van zijn gegevens en acties zien via een set programmatische API's.</span><span class="sxs-lookup"><span data-stu-id="136b5-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="136b5-110">Deze API's helpen u werkstromen te automatiseren en volledig gebruik te maken van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="136b5-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="136b5-111">Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="136b5-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="136b5-112">Een Azure Active Directory-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="136b5-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="136b5-113">Een toegangs token krijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="136b5-113">Get an access token using this application</span></span>
- <span data-ttu-id="136b5-114">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender-API</span><span class="sxs-lookup"><span data-stu-id="136b5-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="136b5-115">Voor API-toegang is OAuth2.0-verificatie vereist.</span><span class="sxs-lookup"><span data-stu-id="136b5-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="136b5-116">Zie [OAuth 2.0 Authorization Code Flow voor](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="136b5-116">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="136b5-117">Als u deze stappen hebt voltooid, kunt u de Microsoft 365 Defender-API openen in een bepaalde context.</span><span class="sxs-lookup"><span data-stu-id="136b5-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="136b5-118">Toepassingscontext (aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="136b5-118">Application context (Recommended)</span></span>

<span data-ttu-id="136b5-119">Gebruik deze context voor apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is, zoals achtergrondservices of daemons.</span><span class="sxs-lookup"><span data-stu-id="136b5-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="136b5-120">Maak een Azure Active Directory-webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="136b5-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="136b5-121">Wijs de gewenste machtigingen toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="136b5-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="136b5-122">Maak een sleutel voor de toepassing.</span><span class="sxs-lookup"><span data-stu-id="136b5-122">Create a key for the application.</span></span>
4. <span data-ttu-id="136b5-123">Haal een beveiligings token op met behulp van de toepassing en de sleutel.</span><span class="sxs-lookup"><span data-stu-id="136b5-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="136b5-124">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="136b5-124">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="136b5-125">Zie Een app maken voor toegang **[tot Microsoft 365 Defender zonder gebruiker voor meer informatie.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="136b5-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="136b5-126">Gebruikerscontext</span><span class="sxs-lookup"><span data-stu-id="136b5-126">User context</span></span>

<span data-ttu-id="136b5-127">Gebruik deze context om acties uit te voeren namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="136b5-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="136b5-128">Maak een in azure Active Directory native toepassing.</span><span class="sxs-lookup"><span data-stu-id="136b5-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="136b5-129">Wijs de gewenste machtiging aan de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="136b5-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="136b5-130">Haal een beveiligings token op met behulp van de gebruikersreferenties voor de toepassing.</span><span class="sxs-lookup"><span data-stu-id="136b5-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="136b5-131">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="136b5-131">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="136b5-132">Zie Een app maken voor toegang **[tot Microsoft 365 Defender-API's namens een gebruiker voor meer informatie.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="136b5-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="136b5-133">Partnercontext</span><span class="sxs-lookup"><span data-stu-id="136b5-133">Partner context</span></span>

<span data-ttu-id="136b5-134">Gebruik deze context wanneer u een app moet bieden aan veel gebruikers in [meerdere tenants.](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="136b5-134">Use this context when you need to provide an app to many users across [multiple tenants](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="136b5-135">Maak een Azure Active Directory-toepassing met meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="136b5-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="136b5-136">Wijs de gewenste machtiging aan de toepassing toe.</span><span class="sxs-lookup"><span data-stu-id="136b5-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="136b5-137">Krijg [toestemming van de](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) beheerder voor de app in elke tenant.</span><span class="sxs-lookup"><span data-stu-id="136b5-137">Get [admin consent](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="136b5-138">Haal een beveiligings token op met behulp van gebruikersreferenties op basis van de tenant-id van een klant.</span><span class="sxs-lookup"><span data-stu-id="136b5-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="136b5-139">Gebruik het token om toegang te krijgen tot de Microsoft 365 Defender-API.</span><span class="sxs-lookup"><span data-stu-id="136b5-139">Use the token to access  Microsoft 365 Defender API.</span></span>

<span data-ttu-id="136b5-140">Zie Een app maken met partnertoegang tot **[Microsoft 365 Defender API's voor](api-partner-access.md)** meer informatie.</span><span class="sxs-lookup"><span data-stu-id="136b5-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="136b5-141">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="136b5-141">Related articles</span></span>

- [<span data-ttu-id="136b5-142">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="136b5-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="136b5-143">OAuth 2.0 authorization for user sign in and API access</span><span class="sxs-lookup"><span data-stu-id="136b5-143">OAuth 2.0 authorization for user sign in and API access</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="136b5-144">Geheimen in uw server-apps beheren met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="136b5-144">Manage secrets in your server apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="136b5-145">Een 'Hallo wereld'-toepassing maken voor toegang tot de Microsoft 365-API's</span><span class="sxs-lookup"><span data-stu-id="136b5-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)
