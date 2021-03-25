---
title: Waarschuwing maken via gebeurtenis-API
description: Meer informatie over het gebruik van de WAARSCHUWINGS-API maken om een nieuwe waarschuwing te maken boven aan Gebeurtenis in Microsoft Defender voor Eindpunt.
keywords: api's, graph api, ondersteunde api's, get, alert, information, id
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166673"
---
# <a name="create-alert-api"></a><span data-ttu-id="e159f-104">Waarschuwings-API maken</span><span class="sxs-lookup"><span data-stu-id="e159f-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e159f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e159f-105">**Applies to:**</span></span>
- [<span data-ttu-id="e159f-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="e159f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e159f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e159f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="e159f-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e159f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e159f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e159f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="e159f-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="e159f-110">API description</span></span>
<span data-ttu-id="e159f-111">Hiermee maakt [u een nieuwe](alerts.md) waarschuwing boven op **Gebeurtenis.**</span><span class="sxs-lookup"><span data-stu-id="e159f-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="e159f-112">**Microsoft Defender voor eindpuntgebeurtenis** is vereist voor het maken van waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="e159f-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="e159f-113">U moet 3 parameters uit de gebeurtenis opgeven in de aanvraag: **Gebeurtenistijd,** **Machine-id** en **Rapport-id.**</span><span class="sxs-lookup"><span data-stu-id="e159f-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="e159f-114">Zie het onderstaande voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="e159f-114">See example below.</span></span>
<br><span data-ttu-id="e159f-115">U kunt een gebeurtenis gebruiken die is gevonden in Advanced Hunting API of Portal.</span><span class="sxs-lookup"><span data-stu-id="e159f-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="e159f-116">Als er een geopende waarschuwing bestaat op hetzelfde apparaat met dezelfde titel, wordt de nieuwe gemaakte waarschuwing samengevoegd.</span><span class="sxs-lookup"><span data-stu-id="e159f-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="e159f-117">Er wordt automatisch een onderzoek gestart naar waarschuwingen die zijn gemaakt via de API.</span><span class="sxs-lookup"><span data-stu-id="e159f-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="e159f-118">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="e159f-118">Limitations</span></span>
1. <span data-ttu-id="e159f-119">Tariefbeperkingen voor deze API zijn 15 oproepen per minuut.</span><span class="sxs-lookup"><span data-stu-id="e159f-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="e159f-120">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="e159f-120">Permissions</span></span>

<span data-ttu-id="e159f-121">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="e159f-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="e159f-122">Zie Microsoft Defender voor [eindpunt-API's](apis-intro.md) gebruiken voor meer informatie, inclusief het kiezen van machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e159f-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="e159f-123">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="e159f-123">Permission type</span></span> |   <span data-ttu-id="e159f-124">Machtiging</span><span class="sxs-lookup"><span data-stu-id="e159f-124">Permission</span></span>  |   <span data-ttu-id="e159f-125">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="e159f-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="e159f-126">Toepassing</span><span class="sxs-lookup"><span data-stu-id="e159f-126">Application</span></span> |   <span data-ttu-id="e159f-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="e159f-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="e159f-128">'Alle waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="e159f-128">'Read and write all alerts'</span></span>
<span data-ttu-id="e159f-129">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="e159f-129">Delegated (work or school account)</span></span> | <span data-ttu-id="e159f-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="e159f-130">Alert.ReadWrite</span></span> | <span data-ttu-id="e159f-131">'Waarschuwingen lezen en schrijven'</span><span class="sxs-lookup"><span data-stu-id="e159f-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="e159f-132">Bij het verkrijgen van een token met gebruikersreferenties:</span><span class="sxs-lookup"><span data-stu-id="e159f-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="e159f-133">De gebruiker moet ten minste de volgende rolmachtiging hebben: 'Alerts investigation' (Zie Rollen maken [en](user-roles.md) beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="e159f-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="e159f-134">De gebruiker moet toegang hebben tot het apparaat dat aan de waarschuwing is gekoppeld, op basis van apparaatgroepinstellingen (Zie [Apparaatgroepen](machine-groups.md) maken en beheren voor meer informatie)</span><span class="sxs-lookup"><span data-stu-id="e159f-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="e159f-135">HTTP-aanvraag</span><span class="sxs-lookup"><span data-stu-id="e159f-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="e159f-136">Kopteksten aanvragen</span><span class="sxs-lookup"><span data-stu-id="e159f-136">Request headers</span></span>

<span data-ttu-id="e159f-137">Naam</span><span class="sxs-lookup"><span data-stu-id="e159f-137">Name</span></span> | <span data-ttu-id="e159f-138">Type</span><span class="sxs-lookup"><span data-stu-id="e159f-138">Type</span></span> | <span data-ttu-id="e159f-139">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e159f-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="e159f-140">Autorisatie</span><span class="sxs-lookup"><span data-stu-id="e159f-140">Authorization</span></span> | <span data-ttu-id="e159f-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-141">String</span></span> | <span data-ttu-id="e159f-142">Bearer {token}.</span><span class="sxs-lookup"><span data-stu-id="e159f-142">Bearer {token}.</span></span> <span data-ttu-id="e159f-143">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-143">**Required**.</span></span>
<span data-ttu-id="e159f-144">Inhoudstype</span><span class="sxs-lookup"><span data-stu-id="e159f-144">Content-Type</span></span> | <span data-ttu-id="e159f-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-145">String</span></span> | <span data-ttu-id="e159f-146">toepassing/json.</span><span class="sxs-lookup"><span data-stu-id="e159f-146">application/json.</span></span> <span data-ttu-id="e159f-147">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="e159f-148">Body aanvragen</span><span class="sxs-lookup"><span data-stu-id="e159f-148">Request body</span></span>

<span data-ttu-id="e159f-149">In de aanvraag-body moet u de volgende waarden leveren (alle waarden zijn vereist):</span><span class="sxs-lookup"><span data-stu-id="e159f-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="e159f-150">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="e159f-150">Property</span></span> | <span data-ttu-id="e159f-151">Type</span><span class="sxs-lookup"><span data-stu-id="e159f-151">Type</span></span> | <span data-ttu-id="e159f-152">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="e159f-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="e159f-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="e159f-153">eventTime</span></span> | <span data-ttu-id="e159f-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="e159f-154">DateTime(UTC)</span></span> | <span data-ttu-id="e159f-155">De exacte tijd van de gebeurtenis als tekenreeks, zoals verkregen uit geavanceerde jacht.</span><span class="sxs-lookup"><span data-stu-id="e159f-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="e159f-156">bijvoorbeeld Vereist ```2018-08-03T16:45:21.7115183Z``` .</span><span class="sxs-lookup"><span data-stu-id="e159f-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="e159f-157">reportId</span><span class="sxs-lookup"><span data-stu-id="e159f-157">reportId</span></span> | <span data-ttu-id="e159f-158">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-158">String</span></span> | <span data-ttu-id="e159f-159">Het rapportId of the event, as obtained from advanced hunting.</span><span class="sxs-lookup"><span data-stu-id="e159f-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="e159f-160">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-160">**Required**.</span></span>
<span data-ttu-id="e159f-161">machineId</span><span class="sxs-lookup"><span data-stu-id="e159f-161">machineId</span></span> | <span data-ttu-id="e159f-162">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-162">String</span></span> | <span data-ttu-id="e159f-163">Id van het apparaat waarop de gebeurtenis is geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="e159f-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="e159f-164">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-164">**Required**.</span></span>
<span data-ttu-id="e159f-165">ernst</span><span class="sxs-lookup"><span data-stu-id="e159f-165">severity</span></span> | <span data-ttu-id="e159f-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-166">String</span></span> | <span data-ttu-id="e159f-167">Ernst van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e159f-167">Severity of the alert.</span></span> <span data-ttu-id="e159f-168">De eigenschapswaarden zijn: 'Laag', 'Gemiddeld' en 'Hoog'.</span><span class="sxs-lookup"><span data-stu-id="e159f-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="e159f-169">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-169">**Required**.</span></span>
<span data-ttu-id="e159f-170">titel</span><span class="sxs-lookup"><span data-stu-id="e159f-170">title</span></span> | <span data-ttu-id="e159f-171">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-171">String</span></span> | <span data-ttu-id="e159f-172">Titel voor de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e159f-172">Title for the alert.</span></span> <span data-ttu-id="e159f-173">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-173">**Required**.</span></span>
<span data-ttu-id="e159f-174">beschrijving</span><span class="sxs-lookup"><span data-stu-id="e159f-174">description</span></span> | <span data-ttu-id="e159f-175">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-175">String</span></span> | <span data-ttu-id="e159f-176">Beschrijving van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e159f-176">Description of the alert.</span></span> <span data-ttu-id="e159f-177">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-177">**Required**.</span></span>
<span data-ttu-id="e159f-178">aanbevolenActie</span><span class="sxs-lookup"><span data-stu-id="e159f-178">recommendedAction</span></span>| <span data-ttu-id="e159f-179">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-179">String</span></span> | <span data-ttu-id="e159f-180">Actie die wordt aanbevolen door de beveiligingsmedewerker bij het analyseren van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e159f-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="e159f-181">**Vereist**.</span><span class="sxs-lookup"><span data-stu-id="e159f-181">**Required**.</span></span>
<span data-ttu-id="e159f-182">categorie</span><span class="sxs-lookup"><span data-stu-id="e159f-182">category</span></span>| <span data-ttu-id="e159f-183">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="e159f-183">String</span></span> | <span data-ttu-id="e159f-184">Categorie van de waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="e159f-184">Category of the alert.</span></span> <span data-ttu-id="e159f-185">De eigenschapswaarden zijn: "Algemeen", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistent", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="e159f-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="e159f-186">Antwoord</span><span class="sxs-lookup"><span data-stu-id="e159f-186">Response</span></span>

<span data-ttu-id="e159f-187">Als dit is gelukt, retourneert deze methode 200 OK en een nieuw [waarschuwingsobject](alerts.md) in de antwoord body.</span><span class="sxs-lookup"><span data-stu-id="e159f-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="e159f-188">Als gebeurtenis met de opgegeven eigenschappen _(reportId_, _eventTime_ en _machineId)_ niet is gevonden - 404 Niet gevonden.</span><span class="sxs-lookup"><span data-stu-id="e159f-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="e159f-189">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="e159f-189">Example</span></span>

<span data-ttu-id="e159f-190">**Aanvraag**</span><span class="sxs-lookup"><span data-stu-id="e159f-190">**Request**</span></span>

<span data-ttu-id="e159f-191">Hier is een voorbeeld van de aanvraag.</span><span class="sxs-lookup"><span data-stu-id="e159f-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
