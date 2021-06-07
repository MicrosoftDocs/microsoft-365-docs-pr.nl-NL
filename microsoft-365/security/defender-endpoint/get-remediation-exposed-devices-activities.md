---
title: Weergegeven apparaten van één herstelactiviteit weergeven
description: Retourneert informatie over blootgestelde apparaten voor de opgegeven hersteltaak.
keywords: api's, herstel, herstel-api, get, hersteltaken, herstel van blootgestelde apparaten
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772159"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="c9d81-104">Weergegeven apparaten van één herstelactiviteit weergeven</span><span class="sxs-lookup"><span data-stu-id="c9d81-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c9d81-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c9d81-105">**Applies to:**</span></span>

- [<span data-ttu-id="c9d81-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="c9d81-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c9d81-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c9d81-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c9d81-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="c9d81-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c9d81-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="c9d81-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c9d81-110">API-beschrijving</span><span class="sxs-lookup"><span data-stu-id="c9d81-110">API Description</span></span>

<span data-ttu-id="c9d81-111">Retourneert informatie over blootgestelde apparaten voor de opgegeven hersteltaak.</span><span class="sxs-lookup"><span data-stu-id="c9d81-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="c9d81-112">[Meer informatie over herstelactiviteiten.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="c9d81-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="c9d81-113">Lijst met blootgestelde apparaten die zijn gekoppeld aan een hersteltaak (id)</span><span class="sxs-lookup"><span data-stu-id="c9d81-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="c9d81-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="c9d81-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="c9d81-115">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="c9d81-115">Permissions</span></span>

<span data-ttu-id="c9d81-116">Een van de volgende machtigingen is vereist om deze API te bellen.</span><span class="sxs-lookup"><span data-stu-id="c9d81-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c9d81-117">Zie Microsoft Defender voor eindpunt-API's gebruiken voor meer informatie, inclusief het kiezen van [machtigingen.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c9d81-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c9d81-118">Machtigingstype</span><span class="sxs-lookup"><span data-stu-id="c9d81-118">Permission type</span></span> | <span data-ttu-id="c9d81-119">Machtiging</span><span class="sxs-lookup"><span data-stu-id="c9d81-119">Permission</span></span> | <span data-ttu-id="c9d81-120">Weergavenaam machtiging</span><span class="sxs-lookup"><span data-stu-id="c9d81-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c9d81-121">Toepassing</span><span class="sxs-lookup"><span data-stu-id="c9d81-121">Application</span></span> | <span data-ttu-id="c9d81-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="c9d81-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="c9d81-123">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="c9d81-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c9d81-124">Gedelegeerd (werk- of schoolaccount)</span><span class="sxs-lookup"><span data-stu-id="c9d81-124">Delegated (work or school account)</span></span> | <span data-ttu-id="c9d81-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="c9d81-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="c9d81-126">\'Informatie over kwetsbaarheidsbeheer en bedreigingsbeheer lezen\'</span><span class="sxs-lookup"><span data-stu-id="c9d81-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="c9d81-127">Eigenschappendetails</span><span class="sxs-lookup"><span data-stu-id="c9d81-127">Properties details</span></span>

<span data-ttu-id="c9d81-128">Eigenschap (id)</span><span class="sxs-lookup"><span data-stu-id="c9d81-128">Property (id)</span></span> | <span data-ttu-id="c9d81-129">Gegevenstype</span><span class="sxs-lookup"><span data-stu-id="c9d81-129">Data type</span></span> | <span data-ttu-id="c9d81-130">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c9d81-130">Description</span></span> | <span data-ttu-id="c9d81-131">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c9d81-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="c9d81-132">id</span><span class="sxs-lookup"><span data-stu-id="c9d81-132">id</span></span> | <span data-ttu-id="c9d81-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9d81-133">String</span></span> | <span data-ttu-id="c9d81-134">Apparaat-id</span><span class="sxs-lookup"><span data-stu-id="c9d81-134">Device ID</span></span> | <span data-ttu-id="c9d81-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="c9d81-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="c9d81-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="c9d81-136">computerDnsName</span></span> | <span data-ttu-id="c9d81-137">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9d81-137">String</span></span> | <span data-ttu-id="c9d81-138">Apparaatnaam</span><span class="sxs-lookup"><span data-stu-id="c9d81-138">Device name</span></span> | <span data-ttu-id="c9d81-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="c9d81-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="c9d81-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="c9d81-140">osPlatform</span></span> | <span data-ttu-id="c9d81-141">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9d81-141">String</span></span> | <span data-ttu-id="c9d81-142">Apparaatbesturingssysteem</span><span class="sxs-lookup"><span data-stu-id="c9d81-142">Device operating system</span></span> | <span data-ttu-id="c9d81-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="c9d81-143">WindowsServer2012R2</span></span>
<span data-ttu-id="c9d81-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c9d81-144">rbacGroupName</span></span> | <span data-ttu-id="c9d81-145">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="c9d81-145">String</span></span> | <span data-ttu-id="c9d81-146">Naam van de apparaatgroep waar dit apparaat aan is gekoppeld</span><span class="sxs-lookup"><span data-stu-id="c9d81-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="c9d81-147">Servers</span><span class="sxs-lookup"><span data-stu-id="c9d81-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="c9d81-148">Voorbeeld</span><span class="sxs-lookup"><span data-stu-id="c9d81-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="c9d81-149">Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="c9d81-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="c9d81-150">Voorbeeld van antwoord</span><span class="sxs-lookup"><span data-stu-id="c9d81-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="c9d81-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c9d81-151">See also</span></span>

- [<span data-ttu-id="c9d81-152">Herstelmethoden en -eigenschappen</span><span class="sxs-lookup"><span data-stu-id="c9d81-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="c9d81-153">Eén herstelactiviteit krijgen op id</span><span class="sxs-lookup"><span data-stu-id="c9d81-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="c9d81-154">Alle herstelactiviteiten weergeven</span><span class="sxs-lookup"><span data-stu-id="c9d81-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="c9d81-155">Risicogebaseerd & vulnerability management</span><span class="sxs-lookup"><span data-stu-id="c9d81-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="c9d81-156">Beveiligingslekken in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="c9d81-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
