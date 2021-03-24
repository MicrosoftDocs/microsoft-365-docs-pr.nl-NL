---
title: Microsoft Defender voor eindpuntdetecties trekken met REST API
description: Lees hoe u een Microsoft Defender for Endpoint API-eindpunt belt om detecties in JSON-indeling op te halen met behulp van de SIEM REST-API.
keywords: detecties, pulldetecties, rest-api, aanvraag, antwoord
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
ms.openlocfilehash: c8baf74d5f838c583b98fddd7d7d706c6e116a40
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058198"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a><span data-ttu-id="4303c-104">Microsoft Defender voor eindpuntdetecties trekken met behulp van SIEM REST API</span><span class="sxs-lookup"><span data-stu-id="4303c-104">Pull Microsoft Defender for Endpoint detections using SIEM REST API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4303c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="4303c-105">**Applies to:**</span></span>
- [<span data-ttu-id="4303c-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="4303c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4303c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4303c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4303c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="4303c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4303c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="4303c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

>[!Note]
>- <span data-ttu-id="4303c-110">[Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.</span><span class="sxs-lookup"><span data-stu-id="4303c-110">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="4303c-111">[Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="4303c-111">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="4303c-112">-De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="4303c-112">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="4303c-113">Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4303c-113">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="4303c-114">Microsoft Defender voor Eindpunt ondersteunt het OAuth 2.0-protocol om detecties uit de API te halen.</span><span class="sxs-lookup"><span data-stu-id="4303c-114">Microsoft Defender for Endpoint supports the OAuth 2.0 protocol to pull detections from the API.</span></span>

<span data-ttu-id="4303c-115">In het algemeen ondersteunt het OAuth 2.0-protocol vier typen stromen:</span><span class="sxs-lookup"><span data-stu-id="4303c-115">In general, the OAuth 2.0 protocol supports four types of flows:</span></span>
- <span data-ttu-id="4303c-116">Autorisatieverleningsstroom</span><span class="sxs-lookup"><span data-stu-id="4303c-116">Authorization grant flow</span></span>
- <span data-ttu-id="4303c-117">Impliciete stroom</span><span class="sxs-lookup"><span data-stu-id="4303c-117">Implicit flow</span></span>
- <span data-ttu-id="4303c-118">Clientreferentiesstroom</span><span class="sxs-lookup"><span data-stu-id="4303c-118">Client credentials flow</span></span>
- <span data-ttu-id="4303c-119">Stroom resourceeigenaar</span><span class="sxs-lookup"><span data-stu-id="4303c-119">Resource owner flow</span></span>

<span data-ttu-id="4303c-120">Zie de website van OAuth voor meer informatie over de [OAuth-specificaties.](http://www.oauth.net)</span><span class="sxs-lookup"><span data-stu-id="4303c-120">For more information about the OAuth specifications, see the [OAuth Website](http://www.oauth.net).</span></span>

<span data-ttu-id="4303c-121">Microsoft Defender for Endpoint ondersteunt  de _machtigingsstroom_ en de clientreferentiestroom om toegang te krijgen tot detecties voor pull-detecties, met Azure Active Directory (AAD) als autorisatieserver.</span><span class="sxs-lookup"><span data-stu-id="4303c-121">Microsoft Defender for Endpoint supports the _Authorization grant flow_ and _Client credential flow_ to obtain access to pull detections, with Azure Active Directory (AAD) as the authorization server.</span></span>

<span data-ttu-id="4303c-122">De _autorisatieverleningsstroom_ gebruikt gebruikersreferenties om een autorisatiecode te verkrijgen, die vervolgens wordt gebruikt om een toegangs token te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="4303c-122">The _Authorization grant flow_ uses user credentials to get an authorization code, which is then used to obtain an access token.</span></span>

<span data-ttu-id="4303c-123">De _clientreferentiestroom maakt_ gebruik van clientreferenties om te verifiëren tegen de URL van het Eindpunt van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4303c-123">The _Client credential flow_ uses client credentials to authenticate against the Microsoft Defender for Endpoint endpoint URL.</span></span> <span data-ttu-id="4303c-124">Deze stroom is geschikt voor scenario's waarin een OAuth-client aanvragen maakt voor een API waarvoor geen gebruikersreferenties nodig zijn.</span><span class="sxs-lookup"><span data-stu-id="4303c-124">This flow is suitable for scenarios when an OAuth client creates requests to an API that doesn't require user credentials.</span></span>

<span data-ttu-id="4303c-125">Gebruik de volgende methode in de Microsoft Defender for Endpoint API om detecties in JSON-indeling op te halen.</span><span class="sxs-lookup"><span data-stu-id="4303c-125">Use the following method in the Microsoft Defender for Endpoint API to pull detections in JSON format.</span></span>

>[!NOTE]
><span data-ttu-id="4303c-126">In het Microsoft Defender-beveiligingscentrum worden soortgelijke waarschuwingsdetecties samengevoegd tot één waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="4303c-126">Microsoft Defender Security Center merges similar alert detections into a single alert.</span></span> <span data-ttu-id="4303c-127">Deze API haalt waarschuwingsdetecties in de onbewerkte vorm op basis van de queryparameters die u hebt ingesteld, zodat u uw eigen groepering en filtering kunt toepassen.</span><span class="sxs-lookup"><span data-stu-id="4303c-127">This API pulls alert detections in its raw form based on the query parameters you set, enabling you to apply your own grouping and filtering.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="4303c-128">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="4303c-128">Before you begin</span></span>
- <span data-ttu-id="4303c-129">Voordat u het Eindpunt van Microsoft Defender voor Eindpunt belt om detecties op te halen, moet u de SIEM-integratietoepassing inschakelen in Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="4303c-129">Before calling the Microsoft Defender for Endpoint endpoint to pull detections, you'll need to enable the SIEM integration application in Azure Active Directory (AAD).</span></span> <span data-ttu-id="4303c-130">Zie [SiEM-integratie inschakelen in Microsoft Defender voor eindpunt voor meer informatie.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="4303c-130">For more information, see [Enable SIEM integration in Microsoft Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="4303c-131">Noteer de volgende waarden in uw Azure-toepassingsregistratie.</span><span class="sxs-lookup"><span data-stu-id="4303c-131">Take note of the following values in your Azure application registration.</span></span> <span data-ttu-id="4303c-132">U hebt deze waarden nodig om de OAuth-stroom in uw service of daemon-app te configureren:</span><span class="sxs-lookup"><span data-stu-id="4303c-132">You need these values to configure the OAuth flow in your service or daemon app:</span></span>
  - <span data-ttu-id="4303c-133">Toepassings-id (uniek voor uw toepassing)</span><span class="sxs-lookup"><span data-stu-id="4303c-133">Application ID (unique to your application)</span></span>
  - <span data-ttu-id="4303c-134">App-sleutel of geheim (uniek voor uw toepassing)</span><span class="sxs-lookup"><span data-stu-id="4303c-134">App key, or secret (unique to your application)</span></span>
  - <span data-ttu-id="4303c-135">Het OAuth 2.0-token-eindpunt van uw app</span><span class="sxs-lookup"><span data-stu-id="4303c-135">Your app's OAuth 2.0 token endpoint</span></span>
    - <span data-ttu-id="4303c-136">Zoek deze waarde  door onder aan de Azure Management Portal op de pagina van uw app op Eindpunten weergeven te klikken.</span><span class="sxs-lookup"><span data-stu-id="4303c-136">Find this value by clicking **View Endpoints** at the bottom of the Azure Management Portal in your app's page.</span></span> <span data-ttu-id="4303c-137">Het eindpunt ziet eruit als `https://login.microsoftonline.com/{tenantId}/oauth2/token` .</span><span class="sxs-lookup"><span data-stu-id="4303c-137">The endpoint will look like `https://login.microsoftonline.com/{tenantId}/oauth2/token`.</span></span>

## <a name="get-an-access-token"></a><span data-ttu-id="4303c-138">Een toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="4303c-138">Get an access token</span></span>
<span data-ttu-id="4303c-139">Voordat u oproepen naar het eindpunt maakt, moet u een toegangs token krijgen.</span><span class="sxs-lookup"><span data-stu-id="4303c-139">Before creating calls to the endpoint, you'll need to get an access token.</span></span>

<span data-ttu-id="4303c-140">U gebruikt het access-token om toegang te krijgen tot de beveiligde resource, die detecties is in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4303c-140">You'll use the access token to access the protected resource, which is detections in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="4303c-141">Als u een toegangs token wilt krijgen, moet u een POST-aanvraag indienen bij het eindpunt van het tokenuitvaardigingspunt.</span><span class="sxs-lookup"><span data-stu-id="4303c-141">To get an access token, you'll need to do a POST request to the token issuing endpoint.</span></span> <span data-ttu-id="4303c-142">Hier is een voorbeeldaanvraag:</span><span class="sxs-lookup"><span data-stu-id="4303c-142">Here is a sample request:</span></span>

```http

POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```
<span data-ttu-id="4303c-143">Het antwoord bevat een toegangs token en vervaldatumgegevens.</span><span class="sxs-lookup"><span data-stu-id="4303c-143">The response will include an access token and expiry information.</span></span>

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```
<span data-ttu-id="4303c-144">U kunt nu de  waarde in het veld access_token gebruiken in een aanvraag voor de Defender for Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="4303c-144">You can now use the value in the *access_token* field in a request to the Defender for Endpoint API.</span></span>

## <a name="request"></a><span data-ttu-id="4303c-145">Aanvraag</span><span class="sxs-lookup"><span data-stu-id="4303c-145">Request</span></span>
<span data-ttu-id="4303c-146">Met een access-token kan uw app geverifieerde aanvragen indienen bij de Microsoft Defender for Endpoint API.</span><span class="sxs-lookup"><span data-stu-id="4303c-146">With an access token, your app can make authenticated requests to the Microsoft Defender for Endpoint API.</span></span> <span data-ttu-id="4303c-147">De app moet het toegangsken toevoegen aan de autorisatiekoptekst van elke aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4303c-147">Your app must append the access token to the Authorization header of each request.</span></span>

### <a name="request-syntax"></a><span data-ttu-id="4303c-148">Syntaxis aanvragen</span><span class="sxs-lookup"><span data-stu-id="4303c-148">Request syntax</span></span>
<span data-ttu-id="4303c-149">Methode</span><span class="sxs-lookup"><span data-stu-id="4303c-149">Method</span></span> | <span data-ttu-id="4303c-150">URI aanvragen</span><span class="sxs-lookup"><span data-stu-id="4303c-150">Request URI</span></span>
:---|:---|
<span data-ttu-id="4303c-151">Toevoegen</span><span class="sxs-lookup"><span data-stu-id="4303c-151">GET</span></span>| <span data-ttu-id="4303c-152">Gebruik de URI die van toepassing is op uw regio.</span><span class="sxs-lookup"><span data-stu-id="4303c-152">Use the URI applicable for your region.</span></span> <br><br> <span data-ttu-id="4303c-153">**Voor de EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4303c-153">**For EU**: `https://wdatp-alertexporter-eu.windows.com/api/alerts`</span></span> </br> <span data-ttu-id="4303c-154">**Voor ons:**`https://wdatp-alertexporter-us.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4303c-154">**For US**: `https://wdatp-alertexporter-us.windows.com/api/alerts`</span></span> <br> <span data-ttu-id="4303c-155">**Voor Groot-Brittannië:**`https://wdatp-alertexporter-uk.windows.com/api/alerts`</span><span class="sxs-lookup"><span data-stu-id="4303c-155">**For UK**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`</span></span> 

### <a name="request-header"></a><span data-ttu-id="4303c-156">Koptekst aanvragen</span><span class="sxs-lookup"><span data-stu-id="4303c-156">Request header</span></span>
<span data-ttu-id="4303c-157">Koptekst</span><span class="sxs-lookup"><span data-stu-id="4303c-157">Header</span></span> | <span data-ttu-id="4303c-158">Type</span><span class="sxs-lookup"><span data-stu-id="4303c-158">Type</span></span> | <span data-ttu-id="4303c-159">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4303c-159">Description</span></span>|
:--|:--|:--
<span data-ttu-id="4303c-160">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="4303c-160">Authorization</span></span> | <span data-ttu-id="4303c-161">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4303c-161">string</span></span> | <span data-ttu-id="4303c-162">Vereist.</span><span class="sxs-lookup"><span data-stu-id="4303c-162">Required.</span></span> <span data-ttu-id="4303c-163">Het Azure AD access-token in het formulier  &lt; *Bearer-token* &gt; .</span><span class="sxs-lookup"><span data-stu-id="4303c-163">The Azure AD access token in the form **Bearer** &lt;*token*&gt;.</span></span> |

### <a name="request-parameters"></a><span data-ttu-id="4303c-164">Parameters aanvragen</span><span class="sxs-lookup"><span data-stu-id="4303c-164">Request parameters</span></span>

<span data-ttu-id="4303c-165">Gebruik optionele queryparameters om de hoeveelheid gegevens op te geven en te bepalen die in een antwoord worden geretourneerd.</span><span class="sxs-lookup"><span data-stu-id="4303c-165">Use optional query parameters to specify and control the amount of data returned in a response.</span></span> <span data-ttu-id="4303c-166">Als u deze methode zonder parameters noemt, bevat het antwoord alle waarschuwingen in uw organisatie in de afgelopen 2 uur.</span><span class="sxs-lookup"><span data-stu-id="4303c-166">If you call this method without parameters, the response contains all the alerts in your organization in the last 2 hours.</span></span>

<span data-ttu-id="4303c-167">Name</span><span class="sxs-lookup"><span data-stu-id="4303c-167">Name</span></span> | <span data-ttu-id="4303c-168">Value</span><span class="sxs-lookup"><span data-stu-id="4303c-168">Value</span></span>| <span data-ttu-id="4303c-169">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4303c-169">Description</span></span>
:---|:---|:---
<span data-ttu-id="4303c-170">sinceTimeUtc</span><span class="sxs-lookup"><span data-stu-id="4303c-170">sinceTimeUtc</span></span> | <span data-ttu-id="4303c-171">DateTime</span><span class="sxs-lookup"><span data-stu-id="4303c-171">DateTime</span></span> | <span data-ttu-id="4303c-172">Hiermee definieert u de waarschuwingen met een lagere tijd die worden opgehaald op basis van het veld:</span><span class="sxs-lookup"><span data-stu-id="4303c-172">Defines the lower time bound alerts are retrieved from, based on field:</span></span> <br> `LastProcessedTimeUtc` <br> <span data-ttu-id="4303c-173">Het tijdbereik is: van sinceTimeUtc-tijd tot huidige tijd.</span><span class="sxs-lookup"><span data-stu-id="4303c-173">The time range will be: from sinceTimeUtc time to current time.</span></span> <br><br> <span data-ttu-id="4303c-174">**OPMERKING:** Als dit niet is opgegeven, worden alle waarschuwingen die in de afgelopen twee uur zijn gegenereerd, opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4303c-174">**NOTE**: When not specified, all alerts generated in the last two hours are retrieved.</span></span>
<span data-ttu-id="4303c-175">untilTimeUtc</span><span class="sxs-lookup"><span data-stu-id="4303c-175">untilTimeUtc</span></span> | <span data-ttu-id="4303c-176">DateTime</span><span class="sxs-lookup"><span data-stu-id="4303c-176">DateTime</span></span> | <span data-ttu-id="4303c-177">Hiermee definieert u de waarschuwingen voor de hoogste tijdsgebonden waarschuwingen die worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4303c-177">Defines the upper time bound alerts are retrieved.</span></span> <br> <span data-ttu-id="4303c-178">Het tijdbereik is: van `sinceTimeUtc` tijd tot `untilTimeUtc` tijd.</span><span class="sxs-lookup"><span data-stu-id="4303c-178">The time range will be: from `sinceTimeUtc` time to `untilTimeUtc` time.</span></span> <br><br> <span data-ttu-id="4303c-179">**OPMERKING:** Wanneer dit niet is opgegeven, is de standaardwaarde de huidige tijd.</span><span class="sxs-lookup"><span data-stu-id="4303c-179">**NOTE**: When not specified, the default value will be the current time.</span></span>
<span data-ttu-id="4303c-180">geleden</span><span class="sxs-lookup"><span data-stu-id="4303c-180">ago</span></span> | <span data-ttu-id="4303c-181">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4303c-181">string</span></span> | <span data-ttu-id="4303c-182">Haalt waarschuwingen in de volgende tijdsbereik op: van `(current_time - ago)` tijd tot `current_time` tijd.</span><span class="sxs-lookup"><span data-stu-id="4303c-182">Pulls alerts in the following time range: from `(current_time - ago)` time to `current_time` time.</span></span> <br><br> <span data-ttu-id="4303c-183">Waarde moet worden ingesteld op basis van **de ISO 8601-duurnotatie**</span><span class="sxs-lookup"><span data-stu-id="4303c-183">Value should be set according to **ISO 8601** duration format</span></span> <br> <span data-ttu-id="4303c-184">Voorbeeld: in de afgelopen 10 minuten worden waarschuwingen `ago=PT10M` binnengekomen.</span><span class="sxs-lookup"><span data-stu-id="4303c-184">Example: `ago=PT10M` will pull alerts received in the last 10 minutes.</span></span>
<span data-ttu-id="4303c-185">limiet</span><span class="sxs-lookup"><span data-stu-id="4303c-185">limit</span></span> | <span data-ttu-id="4303c-186">int</span><span class="sxs-lookup"><span data-stu-id="4303c-186">int</span></span> | <span data-ttu-id="4303c-187">Hiermee wordt het aantal waarschuwingen definieerd dat moet worden opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4303c-187">Defines the number of alerts to be retrieved.</span></span> <span data-ttu-id="4303c-188">De meest recente waarschuwingen worden opgehaald op basis van het gedefinieerde getal.</span><span class="sxs-lookup"><span data-stu-id="4303c-188">Most recent alerts will be retrieved based on the number defined.</span></span><br><br> <span data-ttu-id="4303c-189">**OPMERKING:** Wanneer dit niet is opgegeven, worden alle beschikbare waarschuwingen in het tijdbereik opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4303c-189">**NOTE**: When not specified, all alerts available in the time range will be retrieved.</span></span>
<span data-ttu-id="4303c-190">machinegroepen</span><span class="sxs-lookup"><span data-stu-id="4303c-190">machinegroups</span></span> | <span data-ttu-id="4303c-191">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4303c-191">string</span></span> | <span data-ttu-id="4303c-192">Hiermee geeft u apparaatgroepen op waar u waarschuwingen vandaan wilt halen.</span><span class="sxs-lookup"><span data-stu-id="4303c-192">Specifies device groups to pull alerts from.</span></span> <br><br> <span data-ttu-id="4303c-193">**OPMERKING:** Wanneer dit niet is opgegeven, worden waarschuwingen van alle apparaatgroepen opgehaald.</span><span class="sxs-lookup"><span data-stu-id="4303c-193">**NOTE**: When not specified, alerts from all device groups will be retrieved.</span></span> <br><br> <span data-ttu-id="4303c-194">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="4303c-194">Example:</span></span> <br><br> ```https://wdatp-alertexporter-eu.securitycenter.windows.com/api/Alerts/?machinegroups=UKMachines&machinegroups=FranceMachines```
<span data-ttu-id="4303c-195">DeviceCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="4303c-195">DeviceCreatedMachineTags</span></span> | <span data-ttu-id="4303c-196">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4303c-196">string</span></span> | <span data-ttu-id="4303c-197">Eén apparaatlabel uit het register.</span><span class="sxs-lookup"><span data-stu-id="4303c-197">Single device tag from the registry.</span></span>
<span data-ttu-id="4303c-198">CloudCreatedMachineTags</span><span class="sxs-lookup"><span data-stu-id="4303c-198">CloudCreatedMachineTags</span></span> | <span data-ttu-id="4303c-199">tekenreeks</span><span class="sxs-lookup"><span data-stu-id="4303c-199">string</span></span> | <span data-ttu-id="4303c-200">Apparaatlabels die zijn gemaakt in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="4303c-200">Device tags that were created in Microsoft Defender Security Center.</span></span>

### <a name="request-example"></a><span data-ttu-id="4303c-201">Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="4303c-201">Request example</span></span>
<span data-ttu-id="4303c-202">In het volgende voorbeeld wordt gedemonstreerd hoe u alle detecties in uw organisatie kunt ophalen.</span><span class="sxs-lookup"><span data-stu-id="4303c-202">The following example demonstrates how to retrieve all the detections in your organization.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

<span data-ttu-id="4303c-203">In het volgende voorbeeld wordt een aanvraag gedemonstreerd voor de laatste 20 detecties sinds 2016-09-12 00:00:00: 00.</span><span class="sxs-lookup"><span data-stu-id="4303c-203">The following example demonstrates a request to get the last 20 detections since 2016-09-12 00:00:00.</span></span>

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a><span data-ttu-id="4303c-204">Antwoord</span><span class="sxs-lookup"><span data-stu-id="4303c-204">Response</span></span>
<span data-ttu-id="4303c-205">De retourwaarde is een matrix met waarschuwingsobjecten in de JSON-indeling.</span><span class="sxs-lookup"><span data-stu-id="4303c-205">The return value is an array of alert objects in JSON format.</span></span>

<span data-ttu-id="4303c-206">Hier is een voorbeeld van de retourwaarde:</span><span class="sxs-lookup"><span data-stu-id="4303c-206">Here is an example return value:</span></span>

```json 
[
{        
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a><span data-ttu-id="4303c-207">Voorbeelden van code</span><span class="sxs-lookup"><span data-stu-id="4303c-207">Code examples</span></span>
### <a name="get-access-token"></a><span data-ttu-id="4303c-208">Toegangs token krijgen</span><span class="sxs-lookup"><span data-stu-id="4303c-208">Get access token</span></span>
<span data-ttu-id="4303c-209">In de volgende codevoorbeelden wordt getoond hoe u een toegangs token kunt verkrijgen voor het bellen met de SIEM-API van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="4303c-209">The following code examples demonstrate how to obtain an access token for calling the Microsoft Defender for Endpoint SIEM API.</span></span>

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials" | cut -d "{" -f2 | cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]} | cut -d "\"" -f2 | cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a><span data-ttu-id="4303c-210">Token gebruiken om verbinding te maken met het eindpunt detecties</span><span class="sxs-lookup"><span data-stu-id="4303c-210">Use token to connect to the detections endpoint</span></span>
<span data-ttu-id="4303c-211">In de volgende codevoorbeelden wordt gedemonstreerd hoe u een access-token gebruikt voor het bellen naar de DEFENDER for Endpoint SIEM API om waarschuwingen te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="4303c-211">The following code examples demonstrate how to use an access token for calling the Defender for Endpoint SIEM API to get alerts.</span></span>

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{ 
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token" 
}

#Send the webrequest and get the results. 
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results.  This works for SIEM API:
$alerts =  $response.Content | ConvertFrom-Json | ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o | foreach {$_ -replace ":", "."}    

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"     
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw | ConvertFrom-Json | Select-Object -ExpandProperty value | Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token" | cut -d "[" -f2 | cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a><span data-ttu-id="4303c-212">Foutcodes</span><span class="sxs-lookup"><span data-stu-id="4303c-212">Error codes</span></span>
<span data-ttu-id="4303c-213">De REST-API van Microsoft Defender voor eindpunt retourneert de volgende foutcodes die zijn veroorzaakt door een ongeldige aanvraag.</span><span class="sxs-lookup"><span data-stu-id="4303c-213">The Microsoft Defender for Endpoint REST API returns the following error codes caused by an invalid request.</span></span>

<span data-ttu-id="4303c-214">HTTP-foutcode</span><span class="sxs-lookup"><span data-stu-id="4303c-214">HTTP error code</span></span> | <span data-ttu-id="4303c-215">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="4303c-215">Description</span></span>
:---|:---
<span data-ttu-id="4303c-216">401</span><span class="sxs-lookup"><span data-stu-id="4303c-216">401</span></span> | <span data-ttu-id="4303c-217">Ongeldige aanvraag of ongeldig token.</span><span class="sxs-lookup"><span data-stu-id="4303c-217">Malformed request or invalid token.</span></span>
<span data-ttu-id="4303c-218">403</span><span class="sxs-lookup"><span data-stu-id="4303c-218">403</span></span> | <span data-ttu-id="4303c-219">Niet-geautoriseerde uitzondering: een van de domeinen wordt niet beheerd door de tenantbeheerder of tenantstaat wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="4303c-219">Unauthorized exception - any of the domains is not managed by the tenant administrator or tenant state is deleted.</span></span>
<span data-ttu-id="4303c-220">500</span><span class="sxs-lookup"><span data-stu-id="4303c-220">500</span></span> | <span data-ttu-id="4303c-221">Fout in de service.</span><span class="sxs-lookup"><span data-stu-id="4303c-221">Error in the service.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4303c-222">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4303c-222">Related topics</span></span>
- [<span data-ttu-id="4303c-223">SIEM-integratie inschakelen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="4303c-223">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="4303c-224">ArcSight configureren om Microsoft Defender te gebruiken voor eindpuntdetecties</span><span class="sxs-lookup"><span data-stu-id="4303c-224">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="4303c-225">Detecties naar uw SIEM-hulpprogramma's trekken</span><span class="sxs-lookup"><span data-stu-id="4303c-225">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="4303c-226">Microsoft Defender voor eindpuntdetectievelden</span><span class="sxs-lookup"><span data-stu-id="4303c-226">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="4303c-227">Problemen met de integratie van SIEM-hulpprogramma's oplossen</span><span class="sxs-lookup"><span data-stu-id="4303c-227">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
