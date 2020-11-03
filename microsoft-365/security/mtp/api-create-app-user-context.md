---
title: Toegang verkrijgen via Microsoft 365 Defender-Api's met behulp van gebruikersnamen
description: Meer informatie over het openen van Microsoft 365 Defender-Api's met behulp van gebruikersnamen
keywords: toegang, in naam van gebruiker, API, toepassing, gebruiker, toegangstoken, token,
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
ms.openlocfilehash: a72bc7648045e5cc37a1d899f9e15237ce29ed37
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847354"
---
# <a name="access-microsoft-365-defender-apis-on-behalf-of-user"></a><span data-ttu-id="1890e-104">Toegang tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="1890e-104">Access Microsoft 365 Defender APIs on behalf of user</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1890e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1890e-105">**Applies to:**</span></span>
- <span data-ttu-id="1890e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1890e-106">Microsoft 365 Defender</span></span>

>[!IMPORTANT] 
><span data-ttu-id="1890e-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="1890e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="1890e-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="1890e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


<span data-ttu-id="1890e-109">Op deze pagina wordt beschreven hoe u een toepassing maakt voor het toegankelijk maken van toegang tot Microsoft 365 Defender namens een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1890e-109">This page describes how to create an application to get programmatic access to Microsoft 365 Defender on behalf of a user.</span></span>

<span data-ttu-id="1890e-110">Als u toegang wilt hebben tot Microsoft 365 Defender zonder een gebruiker, raadpleegt u [een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker](api-create-app-web.md).</span><span class="sxs-lookup"><span data-stu-id="1890e-110">If you need programmatic access Microsoft 365 Defender without a user, refer to [Create an app to access Microsoft 365 Defender without a user](api-create-app-web.md).</span></span>

<span data-ttu-id="1890e-111">Als u niet zeker weet welke toegang u nodig hebt, raadpleegt u de [Access-api's van Microsoft 365 Defender](api-access.md).</span><span class="sxs-lookup"><span data-stu-id="1890e-111">If you are not sure which access you need, read the [Access the Microsoft 365 Defender APIs](api-access.md).</span></span>

<span data-ttu-id="1890e-112">Microsoft 365 Defender geeft veel van zijn gegevens en acties getoond via een set programmeer Api's.</span><span class="sxs-lookup"><span data-stu-id="1890e-112">Microsoft 365 Defender exposes much of its data and actions through a set of programmatic APIs.</span></span> <span data-ttu-id="1890e-113">Met deze Api's kunt u werkstromen en innoveren automatiseren op basis van de mogelijkheden van Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="1890e-113">Those APIs will enable you to automate work flows and innovate based on Microsoft 365 Defender capabilities.</span></span> <span data-ttu-id="1890e-114">Voor API-toegang is OAuth 2.0-authenticatie vereist.</span><span class="sxs-lookup"><span data-stu-id="1890e-114">The API access requires OAuth2.0 authentication.</span></span> <span data-ttu-id="1890e-115">Voor meer informatie raadpleegt u [OAuth 2,0 Authorization code flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="1890e-115">For more information, see [OAuth 2.0 Authorization Code Flow](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code).</span></span>

<span data-ttu-id="1890e-116">In het algemeen dient u de volgende stappen uit te voeren om de Api's te gebruiken:</span><span class="sxs-lookup"><span data-stu-id="1890e-116">In general, you’ll need to take the following steps to use the APIs:</span></span>
- <span data-ttu-id="1890e-117">Een AAD-toepassing maken</span><span class="sxs-lookup"><span data-stu-id="1890e-117">Create an AAD application</span></span>
- <span data-ttu-id="1890e-118">Een toegangstoken verkrijgen met deze toepassing</span><span class="sxs-lookup"><span data-stu-id="1890e-118">Get an access token using this application</span></span>
- <span data-ttu-id="1890e-119">Het token gebruiken om toegang te krijgen tot de Microsoft 365 Defender API</span><span class="sxs-lookup"><span data-stu-id="1890e-119">Use the token to access Microsoft 365 Defender API</span></span>

<span data-ttu-id="1890e-120">Op deze pagina wordt uitgelegd hoe u een AAD-toepassing maakt, een toegangstoken krijgt voor Microsoft 365 Defender en het token valideert.</span><span class="sxs-lookup"><span data-stu-id="1890e-120">This page explains how to create an AAD application, get an access token to Microsoft 365 Defender and validate the token.</span></span>

>[!NOTE]
> <span data-ttu-id="1890e-121">Wanneer u de Microsoft 365-API-API opent namens een gebruiker, hebt u de juiste machtigingen voor de toepassing en de gebruikersmachtigingen nodig.</span><span class="sxs-lookup"><span data-stu-id="1890e-121">When accessing Microsoft 365 Defender API on behalf of a user, you will need the correct Application permission and user permission.</span></span>


>[!TIP]
> <span data-ttu-id="1890e-122">Als u gemachtigd bent om een actie uit te voeren in de portal, hebt u de machtiging om de actie uit te voeren in de API.</span><span class="sxs-lookup"><span data-stu-id="1890e-122">If you have the permission to perform an action in the portal, you have the permission to perform the action in the API.</span></span>

## <a name="create-an-app"></a><span data-ttu-id="1890e-123">Een app maken</span><span class="sxs-lookup"><span data-stu-id="1890e-123">Create an app</span></span>

1. <span data-ttu-id="1890e-124">Meld u aan bij [Azure](https://portal.azure.com) met een gebruiker die de rol van **globale beheerder** heeft.</span><span class="sxs-lookup"><span data-stu-id="1890e-124">Log on to [Azure](https://portal.azure.com) with user that has **Global Administrator** role.</span></span>

2. <span data-ttu-id="1890e-125">Ga naar de **Azure Active Directory** -  >  **app registraties**  >  **nieuwe registratie**.</span><span class="sxs-lookup"><span data-stu-id="1890e-125">Navigate to **Azure Active Directory** > **App registrations** > **New registration**.</span></span> 

   ![Afbeelding van Microsoft Azure en navigatie naar toepassing registreren](../../media/atp-azure-new-app2.png)

3. <span data-ttu-id="1890e-127">Voer in de registratie van de volgende gegevens in en klik vervolgens op **registeren**.</span><span class="sxs-lookup"><span data-stu-id="1890e-127">In the registration from, enter the following information then click **Register**.</span></span>

   ![Afbeelding van het venster toepassing maken](../../media/nativeapp-create2.PNG)

   - <span data-ttu-id="1890e-129">**Naam:** Naam van de toepassing</span><span class="sxs-lookup"><span data-stu-id="1890e-129">**Name:** Your application name</span></span>
   - <span data-ttu-id="1890e-130">**Type toepassing:** Openbare client</span><span class="sxs-lookup"><span data-stu-id="1890e-130">**Application type:** Public client</span></span>
   - <span data-ttu-id="1890e-131">**URI omleiden:**https://portal.azure.com</span><span class="sxs-lookup"><span data-stu-id="1890e-131">**Redirect URI:** https://portal.azure.com</span></span>

4. <span data-ttu-id="1890e-132">Als u wilt dat de app toegang kan krijgen tot Microsoft 365 Defender en machtigingen toewijzen, selecteert u op de pagina toepassing de optie **API-machtigingen**  >  **toevoegen** aan  >  **Mijn organisatie** de optie >, typt u **Microsoft 365 Defender** en selecteert u vervolgens **Microsoft 365 Defender**.</span><span class="sxs-lookup"><span data-stu-id="1890e-132">To enable your app to access Microsoft 365 Defender and assign it permissions, on your application page, select **API Permissions** > **Add permission** > **APIs my organization uses** >, type **Microsoft 365 Defender** , and then select **Microsoft 365 Defender**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="1890e-133">Microsoft 365 Defender wordt niet weergegeven in de oorspronkelijke lijst.</span><span class="sxs-lookup"><span data-stu-id="1890e-133">Microsoft 365 Defender does not appear in the original list.</span></span> <span data-ttu-id="1890e-134">U moet de naam ervan beginnen te schrijven in het tekstvak om de naam weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1890e-134">You need to start writing its name in the text box to see it appear.</span></span>

      ![Afbeelding van API-toegang en API-selectie](../../media/apis-in-my-org-tab.PNG)

    - <span data-ttu-id="1890e-136">Kies **gedelegeerde machtigingen** > Kies de relevante machtigingen voor uw scenario, bijvoorbeeld **incident. Read** , en selecteer vervolgens **machtigingen toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="1890e-136">Choose **Delegated permissions** > Choose the relevant permissions for your scenario, e.g. **Incident.Read** , and then select **Add permissions**.</span></span>

      ![Afbeelding van API-toegang en API-selectie](../../media/request-api-permissions-delegated.PNG)

     >[!IMPORTANT]
     ><span data-ttu-id="1890e-138">U moet de relevante machtigingen selecteren.</span><span class="sxs-lookup"><span data-stu-id="1890e-138">You need to select the relevant permissions.</span></span> 

    -  <span data-ttu-id="1890e-139">Om te bepalen welke machtigingen u nodig hebt, raadpleegt u de sectie **machtigingen** in de API die u wilt bellen.</span><span class="sxs-lookup"><span data-stu-id="1890e-139">To determine which permission you need, please look at the **Permissions** section in the API you are interested to call.</span></span>

    - <span data-ttu-id="1890e-140">Klik op **toestemming verlenen**</span><span class="sxs-lookup"><span data-stu-id="1890e-140">Click **Grant consent**</span></span>

      >[!NOTE]
      ><span data-ttu-id="1890e-141">Telkens wanneer u toestemming toevoegt, moet u op **toestemming verlenen** om de nieuwe machtiging van kracht te laten worden.</span><span class="sxs-lookup"><span data-stu-id="1890e-141">Every time you add permission you must click on **Grant consent** for the new permission to take effect.</span></span>

      ![Afbeelding van machtiging verlenen](../../media/grant-consent-delegated.PNG)

6. <span data-ttu-id="1890e-143">Noteer de toepassings-ID en uw Tenant-ID:</span><span class="sxs-lookup"><span data-stu-id="1890e-143">Write down your application ID and your tenant ID:</span></span>

   - <span data-ttu-id="1890e-144">Ga op de pagina toepassing naar **overzicht** en kopieer de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="1890e-144">On your application page, go to **Overview** and copy the following:</span></span>

   ![Afbeelding van gemaakte app-id](../../media/app-and-tenant-ids.png)


## <a name="get-an-access-token-using-powershell"></a><span data-ttu-id="1890e-146">Een toegangstoken verkrijgen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="1890e-146">Get an access token using PowerShell</span></span>

```
#Install the ADAL.PS package if it's not installed.
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps }

$authority = "https://login.windows.net/{tenant-id}" # replace {tenant-id} with your tenant ID.

$clientId = "{application-id}" #replace {application-id} with your application ID.

$redirectUri = "{redirect-uri}" # replace {redirect-uri} with your application redirect URI.

$resourceUrl = "https://api.security.microsoft.com"

$response = Get-ADALToken -Resource $resourceUrl -ClientId $clientId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip
$response.AccessToken
```

## <a name="related-topics"></a><span data-ttu-id="1890e-147">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1890e-147">Related topics</span></span>
- [<span data-ttu-id="1890e-148">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="1890e-148">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="1890e-149">Toegang tot Microsoft 365 Defender met toepassingscontext</span><span class="sxs-lookup"><span data-stu-id="1890e-149">Access  Microsoft 365 Defender with application context</span></span>](api-create-app-web.md)
