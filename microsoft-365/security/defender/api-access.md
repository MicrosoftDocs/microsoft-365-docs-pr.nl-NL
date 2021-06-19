---
title: Toegang tot de Microsoft 365 Defender API's
description: Informatie over het openen van de Microsoft 365 Defender API's
keywords: access, api's, application context, user context, aad application, access token
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 03fd82cd5dc24653b6d67fa47cc225d355bfac45
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028797"
---
# <a name="access-the-microsoft-365-defender-apis"></a><span data-ttu-id="30fa2-104">Toegang tot de Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="30fa2-104">Access the Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="30fa2-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="30fa2-105">**Applies to:**</span></span>

- <span data-ttu-id="30fa2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="30fa2-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30fa2-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="30fa2-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="30fa2-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="30fa2-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="30fa2-109">Microsoft 365 Defender worden veel van de gegevens en acties ervan via een set programmatische API's openbaar.</span><span class="sxs-lookup"><span data-stu-id="30fa2-109">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="30fa2-110">Met deze API's kunt u werkstromen automatiseren en volledig gebruikmaken van Microsoft 365 Defender de mogelijkheden van de Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="30fa2-110">These APIs help you automate workflows and make full use of Microsoft 365 Defender's capabilities.</span></span>

<span data-ttu-id="30fa2-111">Over het algemeen moet u de volgende stappen nemen om de API's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="30fa2-111">In general, you'll need to take the following steps to use the APIs:</span></span>

- <span data-ttu-id="30fa2-112">Een Azure Active Directory maken</span><span class="sxs-lookup"><span data-stu-id="30fa2-112">Create an Azure Active Directory application</span></span>
- <span data-ttu-id="30fa2-113">Een toegangs token krijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="30fa2-113">Get an access token using this application</span></span>
- <span data-ttu-id="30fa2-114">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="30fa2-114">Use the token to access the Microsoft 365 Defender API</span></span>

> [!NOTE]
> <span data-ttu-id="30fa2-115">Api-toegang vereist OAuth2.0-verificatie.</span><span class="sxs-lookup"><span data-stu-id="30fa2-115">API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="30fa2-116">Zie [OAuth 2.0 Autorisatiecode](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)voor Flow.</span><span class="sxs-lookup"><span data-stu-id="30fa2-116">For more information, see [OAuth 2.0 Authorization Code Flow](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="30fa2-117">Nadat u deze stappen hebt voltooid, bent u klaar om toegang te krijgen tot de Microsoft 365 Defender API met een bepaalde context.</span><span class="sxs-lookup"><span data-stu-id="30fa2-117">Once you've accomplished these steps, you're ready to access the Microsoft 365 Defender API using a particular context.</span></span>

## <a name="application-context-recommended"></a><span data-ttu-id="30fa2-118">Toepassingscontext (aanbevolen)</span><span class="sxs-lookup"><span data-stu-id="30fa2-118">Application context (Recommended)</span></span>

<span data-ttu-id="30fa2-119">Gebruik deze context voor apps die worden uitgevoerd zonder dat een aangemelde gebruiker aanwezig is, zoals achtergrondservices of daemons.</span><span class="sxs-lookup"><span data-stu-id="30fa2-119">Use this context for apps that run without a signed-in user present, such as background services or daemons.</span></span>

1. <span data-ttu-id="30fa2-120">Maak een Azure Active Directory webtoepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-120">Create an Azure Active Directory web application.</span></span>
2. <span data-ttu-id="30fa2-121">Wijs de gewenste machtigingen toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-121">Assign the desired permissions to the application.</span></span>
3. <span data-ttu-id="30fa2-122">Maak een sleutel voor de toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-122">Create a key for the application.</span></span>
4. <span data-ttu-id="30fa2-123">Krijg een beveiligings-token met behulp van de toepassing en de sleutel.</span><span class="sxs-lookup"><span data-stu-id="30fa2-123">Get a security token using the application and its key.</span></span>
5. <span data-ttu-id="30fa2-124">Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="30fa2-124">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="30fa2-125">Zie Een app maken voor toegang tot Microsoft 365 Defender **[zonder gebruiker voor meer informatie.](api-create-app-web.md)**</span><span class="sxs-lookup"><span data-stu-id="30fa2-125">For more information, see **[Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md)**.</span></span>

## <a name="user-context"></a><span data-ttu-id="30fa2-126">Context van gebruiker</span><span class="sxs-lookup"><span data-stu-id="30fa2-126">User context</span></span>

<span data-ttu-id="30fa2-127">Gebruik deze context om acties uit te voeren namens één gebruiker.</span><span class="sxs-lookup"><span data-stu-id="30fa2-127">Use this context to perform actions on behalf of a single user.</span></span>

1. <span data-ttu-id="30fa2-128">Maak een Azure Active Directory eigen toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-128">Create an Azure Active Directory native application.</span></span>
2. <span data-ttu-id="30fa2-129">Wijs de gewenste machtiging toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-129">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="30fa2-130">Krijg een beveiligings-token met de gebruikersreferenties voor de toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-130">Get a security token using the user credentials for the application.</span></span>
4. <span data-ttu-id="30fa2-131">Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="30fa2-131">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="30fa2-132">Zie Een app maken voor toegang tot Microsoft 365 Defender **[API's namens een gebruiker voor meer informatie.](api-create-app-user-context.md)**</span><span class="sxs-lookup"><span data-stu-id="30fa2-132">For more information, see **[Create an app to access Microsoft 365 Defender APIs on behalf of a user](api-create-app-user-context.md)**.</span></span>

## <a name="partner-context"></a><span data-ttu-id="30fa2-133">Partnercontext</span><span class="sxs-lookup"><span data-stu-id="30fa2-133">Partner context</span></span>

<span data-ttu-id="30fa2-134">Gebruik deze context wanneer u een app moet bieden aan veel gebruikers in [meerdere tenants.](/azure/active-directory/develop/single-and-multi-tenant-apps)</span><span class="sxs-lookup"><span data-stu-id="30fa2-134">Use this context when you need to provide an app to many users across [multiple tenants](/azure/active-directory/develop/single-and-multi-tenant-apps).</span></span>

1. <span data-ttu-id="30fa2-135">Maak een Azure Active Directory multi-tenanttoepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-135">Create an Azure Active Directory multi-tenant application.</span></span>
2. <span data-ttu-id="30fa2-136">Wijs de gewenste machtiging toe aan de toepassing.</span><span class="sxs-lookup"><span data-stu-id="30fa2-136">Assign the desired permission to the application.</span></span>
3. <span data-ttu-id="30fa2-137">Ontvang [toestemming van de](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) beheerder voor de app van elke tenant.</span><span class="sxs-lookup"><span data-stu-id="30fa2-137">Get [admin consent](/azure/active-directory/develop/v2-permissions-and-consent#requesting-consent-for-an-entire-tenant) for the app from each tenant.</span></span>
4. <span data-ttu-id="30fa2-138">Krijg een beveiligings-token met gebruikersreferenties op basis van de tenant-id van een klant.</span><span class="sxs-lookup"><span data-stu-id="30fa2-138">Get a security token using user credentials based on a customer's tenant ID.</span></span>
5. <span data-ttu-id="30fa2-139">Gebruik het token om toegang te krijgen tot Microsoft 365 Defender API.</span><span class="sxs-lookup"><span data-stu-id="30fa2-139">Use the token to access Microsoft 365 Defender API.</span></span>

<span data-ttu-id="30fa2-140">Zie Een app maken met partnertoegang tot Microsoft 365 Defender **[API's voor meer informatie.](api-partner-access.md)**</span><span class="sxs-lookup"><span data-stu-id="30fa2-140">For more information, see **[Create an app with partner access to Microsoft 365 Defender APIs](api-partner-access.md)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="30fa2-141">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="30fa2-141">Related articles</span></span>

- [<span data-ttu-id="30fa2-142">Microsoft 365 Defender OVERZICHT VAN API's</span><span class="sxs-lookup"><span data-stu-id="30fa2-142">Microsoft 365 Defender APIs overview</span></span>](api-overview.md)
- [<span data-ttu-id="30fa2-143">OAuth 2.0-autorisatie voor gebruikers aanmelden en API-toegang</span><span class="sxs-lookup"><span data-stu-id="30fa2-143">OAuth 2.0 authorization for user sign in and API access</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
- [<span data-ttu-id="30fa2-144">Geheimen beheren in uw server-apps met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="30fa2-144">Manage secrets in your server apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/)
- [<span data-ttu-id="30fa2-145">Een 'Hello world'-toepassing maken die toegang heeft tot de Microsoft 365 API's</span><span class="sxs-lookup"><span data-stu-id="30fa2-145">Create a 'Hello world' application that accesses the Microsoft 365 APIs</span></span>](api-hello-world.md)