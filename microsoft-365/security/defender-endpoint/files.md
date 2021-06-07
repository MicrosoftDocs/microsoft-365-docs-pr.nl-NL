---
title: Bestandsresourcetype
description: Recente waarschuwingen van Microsoft Defender voor eindpunten voor bestanden ophalen.
keywords: api's, graph api, ondersteunde api's, get, waarschuwingen, recent
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: c4d392c9c7777a5ab5435d70e36822e11aa39dae
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771187"
---
# <a name="file-resource-type"></a><span data-ttu-id="f692e-104">Bestandsresourcetype</span><span class="sxs-lookup"><span data-stu-id="f692e-104">File resource type</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f692e-105">**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="f692e-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="f692e-106">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f692e-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f692e-107">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f692e-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


<span data-ttu-id="f692e-108">Vertegenwoordig een bestandsentiteit in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="f692e-108">Represent a file entity in Defender for Endpoint.</span></span>

## <a name="methods"></a><span data-ttu-id="f692e-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="f692e-109">Methods</span></span>
<span data-ttu-id="f692e-110">Methode</span><span class="sxs-lookup"><span data-stu-id="f692e-110">Method</span></span>|<span data-ttu-id="f692e-111">Retourtype</span><span class="sxs-lookup"><span data-stu-id="f692e-111">Return Type</span></span> |<span data-ttu-id="f692e-112">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="f692e-112">Description</span></span>
:---|:---|:---
[<span data-ttu-id="f692e-113">Bestand downloaden</span><span class="sxs-lookup"><span data-stu-id="f692e-113">Get file</span></span>](get-file-information.md) | [<span data-ttu-id="f692e-114">bestand</span><span class="sxs-lookup"><span data-stu-id="f692e-114">file</span></span>](files.md) | <span data-ttu-id="f692e-115">Eén bestand downloaden</span><span class="sxs-lookup"><span data-stu-id="f692e-115">Get a single file</span></span> 
[<span data-ttu-id="f692e-116">Gerelateerde waarschuwingen voor lijstbestand</span><span class="sxs-lookup"><span data-stu-id="f692e-116">List file related alerts</span></span>](get-file-related-alerts.md) | <span data-ttu-id="f692e-117">[waarschuwingsverzameling](alerts.md)</span><span class="sxs-lookup"><span data-stu-id="f692e-117">[alert](alerts.md) collection</span></span> | <span data-ttu-id="f692e-118">Haal [](alerts.md) de waarschuwingsentiteiten op die aan het bestand zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="f692e-118">Get the [alert](alerts.md) entities that are associated with the file.</span></span>
[<span data-ttu-id="f692e-119">Lijstbestandsgerelateerde machines</span><span class="sxs-lookup"><span data-stu-id="f692e-119">List file related machines</span></span>](get-file-related-machines.md) | <span data-ttu-id="f692e-120">[machineverzameling](machine.md)</span><span class="sxs-lookup"><span data-stu-id="f692e-120">[machine](machine.md) collection</span></span> | <span data-ttu-id="f692e-121">De [machine-entiteiten](machine.md) die aan de waarschuwing zijn gekoppeld, krijgen.</span><span class="sxs-lookup"><span data-stu-id="f692e-121">Get the [machine](machine.md) entities associated with the alert.</span></span>
[<span data-ttu-id="f692e-122">bestandsstatistieken</span><span class="sxs-lookup"><span data-stu-id="f692e-122">file statistics</span></span>](get-file-statistics.md) | <span data-ttu-id="f692e-123">Overzicht van statistieken</span><span class="sxs-lookup"><span data-stu-id="f692e-123">Statistics summary</span></span> | <span data-ttu-id="f692e-124">Hiermee wordt de prevalentie voor het opgegeven bestand opgehaald.</span><span class="sxs-lookup"><span data-stu-id="f692e-124">Retrieves the prevalence for the given file.</span></span>


## <a name="properties"></a><span data-ttu-id="f692e-125">Eigenschappen</span><span class="sxs-lookup"><span data-stu-id="f692e-125">Properties</span></span>
|<span data-ttu-id="f692e-126">Eigenschap</span><span class="sxs-lookup"><span data-stu-id="f692e-126">Property</span></span> | <span data-ttu-id="f692e-127">Type</span><span class="sxs-lookup"><span data-stu-id="f692e-127">Type</span></span>    |   <span data-ttu-id="f692e-128">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="f692e-128">Description</span></span> |
|:---|:---|:---|
|<span data-ttu-id="f692e-129">sha1</span><span class="sxs-lookup"><span data-stu-id="f692e-129">sha1</span></span> | <span data-ttu-id="f692e-130">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-130">String</span></span> | <span data-ttu-id="f692e-131">Sha1 hash van de bestandsinhoud</span><span class="sxs-lookup"><span data-stu-id="f692e-131">Sha1 hash of the file content</span></span> |
|<span data-ttu-id="f692e-132">sha256</span><span class="sxs-lookup"><span data-stu-id="f692e-132">sha256</span></span> | <span data-ttu-id="f692e-133">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-133">String</span></span> | <span data-ttu-id="f692e-134">Sha256-hash van de bestandsinhoud</span><span class="sxs-lookup"><span data-stu-id="f692e-134">Sha256 hash of the file content</span></span> |
|<span data-ttu-id="f692e-135">globalPrevalence</span><span class="sxs-lookup"><span data-stu-id="f692e-135">globalPrevalence</span></span> | <span data-ttu-id="f692e-136">Nullable long</span><span class="sxs-lookup"><span data-stu-id="f692e-136">Nullable long</span></span> | <span data-ttu-id="f692e-137">Bestandspresentpresies in de hele organisatie</span><span class="sxs-lookup"><span data-stu-id="f692e-137">File prevalence across organization</span></span> |
|<span data-ttu-id="f692e-138">globalFirstObserved</span><span class="sxs-lookup"><span data-stu-id="f692e-138">globalFirstObserved</span></span> | <span data-ttu-id="f692e-139">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f692e-139">DateTimeOffset</span></span> | <span data-ttu-id="f692e-140">De eerste keer dat het bestand is waargenomen</span><span class="sxs-lookup"><span data-stu-id="f692e-140">First time the file was observed</span></span> |
|<span data-ttu-id="f692e-141">globalLastObserved</span><span class="sxs-lookup"><span data-stu-id="f692e-141">globalLastObserved</span></span> | <span data-ttu-id="f692e-142">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="f692e-142">DateTimeOffset</span></span> | <span data-ttu-id="f692e-143">De laatste keer dat het bestand is waargenomen</span><span class="sxs-lookup"><span data-stu-id="f692e-143">Last time the file was observed</span></span> |
|<span data-ttu-id="f692e-144">grootte</span><span class="sxs-lookup"><span data-stu-id="f692e-144">size</span></span> | <span data-ttu-id="f692e-145">Nullable long</span><span class="sxs-lookup"><span data-stu-id="f692e-145">Nullable long</span></span> | <span data-ttu-id="f692e-146">Grootte van het bestand</span><span class="sxs-lookup"><span data-stu-id="f692e-146">Size of the file</span></span> |
|<span data-ttu-id="f692e-147">fileType</span><span class="sxs-lookup"><span data-stu-id="f692e-147">fileType</span></span> | <span data-ttu-id="f692e-148">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-148">String</span></span> | <span data-ttu-id="f692e-149">Type van het bestand</span><span class="sxs-lookup"><span data-stu-id="f692e-149">Type of the file</span></span> |
|<span data-ttu-id="f692e-150">isPeFile</span><span class="sxs-lookup"><span data-stu-id="f692e-150">isPeFile</span></span> | <span data-ttu-id="f692e-151">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="f692e-151">Boolean</span></span> | <span data-ttu-id="f692e-152">waar als het bestand draagbaar is (bijvoorbeeld 'DLL', 'EXE', enz.)</span><span class="sxs-lookup"><span data-stu-id="f692e-152">true if the file is portable executable (e.g. "DLL", "EXE", etc.)</span></span> |
|<span data-ttu-id="f692e-153">filePublisher</span><span class="sxs-lookup"><span data-stu-id="f692e-153">filePublisher</span></span> | <span data-ttu-id="f692e-154">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-154">String</span></span> | <span data-ttu-id="f692e-155">Bestandsuitgever</span><span class="sxs-lookup"><span data-stu-id="f692e-155">File publisher</span></span> |
|<span data-ttu-id="f692e-156">fileProductName</span><span class="sxs-lookup"><span data-stu-id="f692e-156">fileProductName</span></span> | <span data-ttu-id="f692e-157">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-157">String</span></span> | <span data-ttu-id="f692e-158">Productnaam</span><span class="sxs-lookup"><span data-stu-id="f692e-158">Product name</span></span> |
|<span data-ttu-id="f692e-159">ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="f692e-159">signer</span></span> | <span data-ttu-id="f692e-160">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-160">String</span></span> | <span data-ttu-id="f692e-161">Bestands ondertekenaar</span><span class="sxs-lookup"><span data-stu-id="f692e-161">File signer</span></span> |
|<span data-ttu-id="f692e-162">uitgevende gever</span><span class="sxs-lookup"><span data-stu-id="f692e-162">issuer</span></span> | <span data-ttu-id="f692e-163">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-163">String</span></span> | <span data-ttu-id="f692e-164">Bestands issuer</span><span class="sxs-lookup"><span data-stu-id="f692e-164">File issuer</span></span> |
|<span data-ttu-id="f692e-165">signerHash</span><span class="sxs-lookup"><span data-stu-id="f692e-165">signerHash</span></span> | <span data-ttu-id="f692e-166">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-166">String</span></span> | <span data-ttu-id="f692e-167">Hash van het handtekeningcertificaat</span><span class="sxs-lookup"><span data-stu-id="f692e-167">Hash of the signing certificate</span></span> |
|<span data-ttu-id="f692e-168">isValidCertificate</span><span class="sxs-lookup"><span data-stu-id="f692e-168">isValidCertificate</span></span> | <span data-ttu-id="f692e-169">Booleaanse waarde</span><span class="sxs-lookup"><span data-stu-id="f692e-169">Boolean</span></span> | <span data-ttu-id="f692e-170">Is het ondertekenen van certificaat geverifieerd door Microsoft Defender voor Endpoint-agent</span><span class="sxs-lookup"><span data-stu-id="f692e-170">Was signing certificate successfully verified by Microsoft Defender for Endpoint agent</span></span> |
|<span data-ttu-id="f692e-171">determinationType</span><span class="sxs-lookup"><span data-stu-id="f692e-171">determinationType</span></span> | <span data-ttu-id="f692e-172">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-172">String</span></span> | <span data-ttu-id="f692e-173">Het bepalingstype van het bestand</span><span class="sxs-lookup"><span data-stu-id="f692e-173">The determination type of the file</span></span> |
|<span data-ttu-id="f692e-174">bepalingWaarde</span><span class="sxs-lookup"><span data-stu-id="f692e-174">determinationValue</span></span> | <span data-ttu-id="f692e-175">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="f692e-175">String</span></span> | <span data-ttu-id="f692e-176">Bepalingswaarde</span><span class="sxs-lookup"><span data-stu-id="f692e-176">Determination value</span></span> |


## <a name="json-representation"></a><span data-ttu-id="f692e-177">Json-representatie</span><span class="sxs-lookup"><span data-stu-id="f692e-177">Json representation</span></span>

```json
{
    "sha1": "4388963aaa83afe2042a46a3c017ad50bdcdafb3",
    "sha256": "413c58c8267d2c8648d8f6384bacc2ae9c929b2b96578b6860b5087cd1bd6462",
    "globalPrevalence": 180022,
    "globalFirstObserved": "2017-09-19T03:51:27.6785431Z",
    "globalLastObserved": "2020-01-06T03:59:21.3229314Z",
    "size": 22139496,
    "fileType": "APP",
    "isPeFile": true,
    "filePublisher": "CHENGDU YIWO Tech Development Co., Ltd.",
    "fileProductName": "EaseUS MobiSaver for Android",
    "signer": "CHENGDU YIWO Tech Development Co., Ltd.",
    "issuer": "VeriSign Class 3 Code Signing 2010 CA",
    "signerHash": "6c3245d4a9bc0244d99dff27af259cbbae2e2d16",
    "isValidCertificate": false,
    "determinationType": "Pua",
    "determinationValue": "PUA:Win32/FusionCore"
}
```
