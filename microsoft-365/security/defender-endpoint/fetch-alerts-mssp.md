---
title: Waarschuwingen ophalen van MSSP-klant tenant
description: Informatie over het ophalen van waarschuwingen van een klant tenant
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 456507533265bc085adc1008f3264e123569a6ca
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770767"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a><span data-ttu-id="8124b-104">Waarschuwingen ophalen van MSSP-klant tenant</span><span class="sxs-lookup"><span data-stu-id="8124b-104">Fetch alerts from MSSP customer tenant</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8124b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8124b-105">**Applies to:**</span></span>
- [<span data-ttu-id="8124b-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8124b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="8124b-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8124b-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8124b-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8124b-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!NOTE]
><span data-ttu-id="8124b-109">Deze actie wordt ondernomen door de MSSP.</span><span class="sxs-lookup"><span data-stu-id="8124b-109">This action is taken by the MSSP.</span></span>


<span data-ttu-id="8124b-110">Er zijn twee manieren waarop u waarschuwingen kunt ophalen:</span><span class="sxs-lookup"><span data-stu-id="8124b-110">There are two ways you can fetch alerts:</span></span>
- <span data-ttu-id="8124b-111">De SIEM-methode gebruiken</span><span class="sxs-lookup"><span data-stu-id="8124b-111">Using the SIEM method</span></span>
- <span data-ttu-id="8124b-112">API's gebruiken</span><span class="sxs-lookup"><span data-stu-id="8124b-112">Using APIs</span></span>

## <a name="fetch-alerts-into-your-siem"></a><span data-ttu-id="8124b-113">Waarschuwingen ophalen in uw SIEM</span><span class="sxs-lookup"><span data-stu-id="8124b-113">Fetch alerts into your SIEM</span></span>

<span data-ttu-id="8124b-114">Als u waarschuwingen wilt ophalen in uw SIEM-systeem, moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="8124b-114">To fetch alerts into your SIEM system, you'll need to take the following steps:</span></span>

<span data-ttu-id="8124b-115">Stap 1: Een toepassing van derden maken</span><span class="sxs-lookup"><span data-stu-id="8124b-115">Step 1: Create a third-party application</span></span>

<span data-ttu-id="8124b-116">Stap 2: Toegang krijgen en tokens vernieuwen van de tenant van uw klant</span><span class="sxs-lookup"><span data-stu-id="8124b-116">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
 
<span data-ttu-id="8124b-117">Stap 3: uw toepassing toestaan op Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8124b-117">Step 3: allow your application on Microsoft Defender Security Center</span></span>
 
### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a><span data-ttu-id="8124b-118">Stap 1: Een toepassing maken in Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8124b-118">Step 1: Create an application in Azure Active Directory (Azure AD)</span></span>
 
<span data-ttu-id="8124b-119">U moet een toepassing maken en deze machtigingen verlenen om waarschuwingen op te halen bij de Microsoft Defender voor Eindpunt-tenant van uw klant.</span><span class="sxs-lookup"><span data-stu-id="8124b-119">You'll need to create an application and grant it permissions to fetch alerts from your customer's Microsoft Defender for Endpoint tenant.</span></span>

1. <span data-ttu-id="8124b-120">Meld u aan bij de [Azure AD-portal.](https://aad.portal.azure.com/)</span><span class="sxs-lookup"><span data-stu-id="8124b-120">Sign in to the [Azure AD portal](https://aad.portal.azure.com/).</span></span>

2. <span data-ttu-id="8124b-121">Selecteer **Azure Active Directory**  >  **app-registraties**.</span><span class="sxs-lookup"><span data-stu-id="8124b-121">Select **Azure Active Directory** > **App registrations**.</span></span>
 
3. <span data-ttu-id="8124b-122">Klik **op Nieuwe registratie.**</span><span class="sxs-lookup"><span data-stu-id="8124b-122">Click **New registration**.</span></span>

4. <span data-ttu-id="8124b-123">Geef de volgende waarden op:</span><span class="sxs-lookup"><span data-stu-id="8124b-123">Specify the following values:</span></span>

    - <span data-ttu-id="8124b-124">Naam: \<Tenant_name\> SIEM MSSP Connector (vervangen door Tenant_name tenantweergavenaam)</span><span class="sxs-lookup"><span data-stu-id="8124b-124">Name: \<Tenant_name\> SIEM MSSP Connector (replace Tenant_name with the tenant display name)</span></span>
 
    - <span data-ttu-id="8124b-125">Ondersteunde accounttypen: Alleen account in deze organisatiemap</span><span class="sxs-lookup"><span data-stu-id="8124b-125">Supported account types: Account in this organizational directory only</span></span> 
    - <span data-ttu-id="8124b-126">Redirect URI: Web selecteren en typen `https://<domain_name>/SiemMsspConnector` (<domain_name> vervangen door de tenantnaam)</span><span class="sxs-lookup"><span data-stu-id="8124b-126">Redirect URI: Select Web and type `https://<domain_name>/SiemMsspConnector`(replace <domain_name> with the tenant name)</span></span>

5. <span data-ttu-id="8124b-127">Klik **op Registreren.**</span><span class="sxs-lookup"><span data-stu-id="8124b-127">Click **Register**.</span></span> <span data-ttu-id="8124b-128">De toepassing wordt weergegeven in de lijst met toepassingen die u bezit.</span><span class="sxs-lookup"><span data-stu-id="8124b-128">The application is displayed in the list of applications you own.</span></span>

6. <span data-ttu-id="8124b-129">Selecteer de toepassing en klik vervolgens op **Overzicht.**</span><span class="sxs-lookup"><span data-stu-id="8124b-129">Select the application, then click **Overview**.</span></span>

7. <span data-ttu-id="8124b-130">Kopieer de waarde van het **veld Toepassings-id (client-id)** naar een veilige plaats, u hebt deze in de volgende stap nodig.</span><span class="sxs-lookup"><span data-stu-id="8124b-130">Copy the value from the **Application (client) ID** field to a safe place, you will need this in the next step.</span></span>

8. <span data-ttu-id="8124b-131">Selecteer **Certificaat & in** het nieuwe toepassingsvenster.</span><span class="sxs-lookup"><span data-stu-id="8124b-131">Select **Certificate & secrets** in the new application panel.</span></span>

9. <span data-ttu-id="8124b-132">Klik **op Nieuw clientgeheim.**</span><span class="sxs-lookup"><span data-stu-id="8124b-132">Click **New client secret**.</span></span>

    - <span data-ttu-id="8124b-133">Beschrijving: Voer een beschrijving voor de sleutel in.</span><span class="sxs-lookup"><span data-stu-id="8124b-133">Description: Enter a description for the key.</span></span>
    - <span data-ttu-id="8124b-134">Verloopt: Selecteren **in 1 jaar**</span><span class="sxs-lookup"><span data-stu-id="8124b-134">Expires: Select **In 1 year**</span></span>

 
10. <span data-ttu-id="8124b-135">Klik **op Toevoegen,** kopieer de waarde van het clientgeheim naar een veilige plaats, u hebt dit nodig in de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="8124b-135">Click **Add**, copy the value of the client secret to a safe place, you will need this in the next step.</span></span>
 

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a><span data-ttu-id="8124b-136">Stap 2: Toegang krijgen en tokens vernieuwen van de tenant van uw klant</span><span class="sxs-lookup"><span data-stu-id="8124b-136">Step 2: Get access and refresh tokens from your customer's tenant</span></span>
<span data-ttu-id="8124b-137">In deze sectie vindt u informatie over het gebruik van een PowerShell-script om de tokens van de tenant van uw klant op te halen.</span><span class="sxs-lookup"><span data-stu-id="8124b-137">This section guides you on how to use a PowerShell script to get the tokens from your customer's tenant.</span></span> <span data-ttu-id="8124b-138">In dit script wordt de toepassing uit de vorige stap gebruikt om toegangs- en vernieuwingstokens te verkrijgen met behulp van de OAuth Autorisatiecode Flow.</span><span class="sxs-lookup"><span data-stu-id="8124b-138">This script uses the application from the previous step to get the access and refresh tokens using the OAuth Authorization Code Flow.</span></span>

<span data-ttu-id="8124b-139">Nadat u uw referenties hebt ingediend, moet u toestemming verlenen voor de toepassing, zodat de toepassing is ingericht in de tenant van de klant.</span><span class="sxs-lookup"><span data-stu-id="8124b-139">After providing your credentials, you'll need to grant consent to the application so that the application is provisioned in the customer's tenant.</span></span>


1. <span data-ttu-id="8124b-140">Een nieuwe map maken en deze een naam geven: `MsspTokensAcquisition` .</span><span class="sxs-lookup"><span data-stu-id="8124b-140">Create a new folder and name it: `MsspTokensAcquisition`.</span></span>

2. <span data-ttu-id="8124b-141">Download de [module LoginBrowser.psm1](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) en sla deze op in de `MsspTokensAcquisition` map.</span><span class="sxs-lookup"><span data-stu-id="8124b-141">Download the [LoginBrowser.psm1 module](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1) and save it in the `MsspTokensAcquisition` folder.</span></span>

    >[!NOTE]
    ><span data-ttu-id="8124b-142">Vervang in regel 30 `authorzationUrl` door `authorizationUrl` .</span><span class="sxs-lookup"><span data-stu-id="8124b-142">In line 30, replace `authorzationUrl` with `authorizationUrl`.</span></span>

3. <span data-ttu-id="8124b-143">Maak een bestand met de volgende inhoud en sla het op met de naam `MsspTokensAcquisition.ps1` in de map:</span><span class="sxs-lookup"><span data-stu-id="8124b-143">Create a file with the following content and save it with the name `MsspTokensAcquisition.ps1` in the folder:</span></span>
    ```
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " -----------------------------------  TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " -----------------------------------  REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken 
    ```
4. <span data-ttu-id="8124b-144">Open een verhoogde PowerShell-opdrachtprompt in de `MsspTokensAcquisition` map.</span><span class="sxs-lookup"><span data-stu-id="8124b-144">Open an elevated PowerShell command prompt in the `MsspTokensAcquisition` folder.</span></span>

5. <span data-ttu-id="8124b-145">Voer de volgende opdracht uit: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span><span class="sxs-lookup"><span data-stu-id="8124b-145">Run the following command: `Set-ExecutionPolicy -ExecutionPolicy Bypass`</span></span>

6. <span data-ttu-id="8124b-146">Voer de volgende opdrachten in: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span><span class="sxs-lookup"><span data-stu-id="8124b-146">Enter the following commands: `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`</span></span>
 
    - <span data-ttu-id="8124b-147">Vervang \<client_id\> de **toepassings-id (client-id)** die u hebt van de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="8124b-147">Replace \<client_id\> with the **Application (client) ID** you got from the previous step.</span></span>
    - <span data-ttu-id="8124b-148">Vervang \<app_key\> het **clientgeheim dat** u hebt gemaakt op de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="8124b-148">Replace \<app_key\> with the **Client Secret** you created from the previous step.</span></span>
    - <span data-ttu-id="8124b-149">Vervangen \<customer_tenant_id\> door de **tenant-id van uw klant.**</span><span class="sxs-lookup"><span data-stu-id="8124b-149">Replace \<customer_tenant_id\> with your customer's **Tenant ID**.</span></span> 
 

7. <span data-ttu-id="8124b-150">U wordt gevraagd uw referenties en toestemming te geven.</span><span class="sxs-lookup"><span data-stu-id="8124b-150">You'll be asked to provide your credentials and consent.</span></span> <span data-ttu-id="8124b-151">Negeer de omleiding van de pagina.</span><span class="sxs-lookup"><span data-stu-id="8124b-151">Ignore the page redirect.</span></span>

8. <span data-ttu-id="8124b-152">In het PowerShell-venster ontvangt u een toegangs-token en een vernieuwings-token.</span><span class="sxs-lookup"><span data-stu-id="8124b-152">In the PowerShell window, you'll receive an access token and a refresh token.</span></span> <span data-ttu-id="8124b-153">Sla het vernieuwingsken op om de SIEM-connector te configureren.</span><span class="sxs-lookup"><span data-stu-id="8124b-153">Save the refresh token to configure your SIEM connector.</span></span> 
 
### <a name="step-3-allow-your-application-on-microsoft-defender-security-center"></a><span data-ttu-id="8124b-154">Stap 3: Uw toepassing toestaan op Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8124b-154">Step 3: Allow your application on Microsoft Defender Security Center</span></span>
<span data-ttu-id="8124b-155">U moet de toepassing toestaan die u hebt gemaakt in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="8124b-155">You'll need to allow the application you created in Microsoft Defender Security Center.</span></span>
 
<span data-ttu-id="8124b-156">U moet de machtiging Portalsysteeminstellingen **beheren** hebben om de toepassing toe te staan.</span><span class="sxs-lookup"><span data-stu-id="8124b-156">You'll need to have **Manage portal system settings** permission to allow the application.</span></span> <span data-ttu-id="8124b-157">Anders moet u uw klant vragen om de toepassing voor u toe te staan.</span><span class="sxs-lookup"><span data-stu-id="8124b-157">Otherwise, you'll need to request your customer to allow the application for you.</span></span>

1. <span data-ttu-id="8124b-158">Ga naar `https://securitycenter.windows.com?tid=<customer_tenant_id>` (vervangen \<customer_tenant_id\> door de tenant-id van de klant.</span><span class="sxs-lookup"><span data-stu-id="8124b-158">Go to `https://securitycenter.windows.com?tid=<customer_tenant_id>` (replace \<customer_tenant_id\> with the customer's tenant ID.</span></span>

2. <span data-ttu-id="8124b-159">Klik **Instellingen**  >  **SIEM**.</span><span class="sxs-lookup"><span data-stu-id="8124b-159">Click **Settings** > **SIEM**.</span></span> 

3. <span data-ttu-id="8124b-160">Selecteer het **tabblad MSSP.**</span><span class="sxs-lookup"><span data-stu-id="8124b-160">Select the **MSSP** tab.</span></span>

4. <span data-ttu-id="8124b-161">Voer de **toepassings-id** in van de eerste stap en uw **tenant-id.**</span><span class="sxs-lookup"><span data-stu-id="8124b-161">Enter the **Application ID** from the first step and your **Tenant ID**.</span></span>

5. <span data-ttu-id="8124b-162">Klik **op Toepassing autoreren.**</span><span class="sxs-lookup"><span data-stu-id="8124b-162">Click **Authorize application**.</span></span> 

 
<span data-ttu-id="8124b-163">U kunt nu het relevante configuratiebestand voor uw SIEM downloaden en verbinding maken met de Defender for Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="8124b-163">You can now download the relevant configuration file for your SIEM and connect to the Defender for Endpoint API.</span></span> <span data-ttu-id="8124b-164">Zie Waarschuwingen naar uw [SIEM-hulpprogramma's trekken voor meer informatie.](configure-siem.md)</span><span class="sxs-lookup"><span data-stu-id="8124b-164">For more information, see, [Pull alerts to your SIEM tools](configure-siem.md).</span></span>
 

- <span data-ttu-id="8124b-165">Schrijf de toepassingssleutel handmatig in het configuratiebestand ArcSight / Splunk Authentication Properties door de geheime waarde in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8124b-165">In the ArcSight configuration file / Splunk Authentication Properties file, write your application key manually by setting the secret value.</span></span>
- <span data-ttu-id="8124b-166">In plaats van een vernieuwingsken in de portal te kopen, gebruikt u het script uit de vorige stap om een vernieuwings-token te verkrijgen (of op een andere manier te verkrijgen).</span><span class="sxs-lookup"><span data-stu-id="8124b-166">Instead of acquiring a refresh token in the portal, use the script from the previous step to acquire a refresh token (or acquire it by other means).</span></span>

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a><span data-ttu-id="8124b-167">Waarschuwingen ophalen bij de tenant van MSSP-klanten met API's</span><span class="sxs-lookup"><span data-stu-id="8124b-167">Fetch alerts from MSSP customer's tenant using APIs</span></span>
 
<span data-ttu-id="8124b-168">Zie Waarschuwingen ophalen met REST API voor informatie over het ophalen van waarschuwingen met BEHULP van [REST API.](pull-alerts-using-rest-api.md)</span><span class="sxs-lookup"><span data-stu-id="8124b-168">For information on how to fetch alerts using REST API, see [Pull alerts using REST API](pull-alerts-using-rest-api.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="8124b-169">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8124b-169">See also</span></span>
- [<span data-ttu-id="8124b-170">MSSP-toegang verlenen tot de portal</span><span class="sxs-lookup"><span data-stu-id="8124b-170">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="8124b-171">Toegang tot de MSSP-klantportal</span><span class="sxs-lookup"><span data-stu-id="8124b-171">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8124b-172">Waarschuwingsmeldingen configureren</span><span class="sxs-lookup"><span data-stu-id="8124b-172">Configure alert notifications</span></span>](configure-mssp-notifications.md)
