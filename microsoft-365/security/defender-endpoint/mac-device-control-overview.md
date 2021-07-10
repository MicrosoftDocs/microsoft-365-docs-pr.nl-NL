---
title: Apparaatbesturingselement voor macOS
description: Meer informatie over het configureren van Microsoft Defender voor Eindpunt op Mac om bedreigingen van verwisselbare opslag, zoals USB-apparaten, te beperken.
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, Mac, apparaat, besturingselement, usb, verwisselbaar, media
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5cb819daa11a50ef54c758a6aa696a5fc645029c
ms.sourcegitcommit: 7dc3b4dec05299abb4290a6e3d1ebe0fdc622ed7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/10/2021
ms.locfileid: "53363977"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="ee8a3-104">Apparaatbesturingselement voor macOS</span><span class="sxs-lookup"><span data-stu-id="ee8a3-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ee8a3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-105">**Applies to:**</span></span>
- [<span data-ttu-id="ee8a3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="ee8a3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ee8a3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ee8a3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ee8a3-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ee8a3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ee8a3-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="requirements"></a><span data-ttu-id="ee8a3-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="ee8a3-110">Requirements</span></span>

<span data-ttu-id="ee8a3-111">Apparaatbesturingselement voor macOS heeft de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="ee8a3-112">Microsoft Defender for Endpoint entitlement (can be trial)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="ee8a3-113">Minimale os-versie: macOS 11 of hoger</span><span class="sxs-lookup"><span data-stu-id="ee8a3-113">Minimum OS version: macOS 11 or higher</span></span>
> - <span data-ttu-id="ee8a3-114">Minimale productversie: 101.34.20</span><span class="sxs-lookup"><span data-stu-id="ee8a3-114">Minimum product version: 101.34.20</span></span>

## <a name="device-control-policy"></a><span data-ttu-id="ee8a3-115">Apparaatbeheerbeleid</span><span class="sxs-lookup"><span data-stu-id="ee8a3-115">Device control policy</span></span>

<span data-ttu-id="ee8a3-116">Als u apparaatbesturingselement voor macOS wilt configureren, moet u een beleid maken waarin de beperkingen worden beschreven die u binnen uw organisatie wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-116">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="ee8a3-117">Het apparaatbeheerbeleid is opgenomen in het configuratieprofiel dat wordt gebruikt om alle andere productinstellingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-117">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="ee8a3-118">Zie Configuratieprofielstructuur [voor meer informatie.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-118">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="ee8a3-119">In het configuratieprofiel wordt het beleid voor apparaatbesturingselementen gedefinieerd in de volgende sectie:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-119">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="ee8a3-120">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-120">Section</span></span>|<span data-ttu-id="ee8a3-121">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-121">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-122">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-122">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-123">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-123">**Key**</span></span> | <span data-ttu-id="ee8a3-124">deviceControl</span><span class="sxs-lookup"><span data-stu-id="ee8a3-124">deviceControl</span></span> |
| <span data-ttu-id="ee8a3-125">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-125">**Data type**</span></span> | <span data-ttu-id="ee8a3-126">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-126">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee8a3-127">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-127">**Comments**</span></span> | <span data-ttu-id="ee8a3-128">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-128">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="ee8a3-129">Het apparaatbesturingselementbeleid kan worden gebruikt om:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-129">The device control policy can be used to:</span></span>

- [<span data-ttu-id="ee8a3-130">Het URL-doel aanpassen voor meldingen die door apparaatbesturingselementen worden opgehaald</span><span class="sxs-lookup"><span data-stu-id="ee8a3-130">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="ee8a3-131">Verwisselbare apparaten toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee8a3-131">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="ee8a3-132">URL-doel aanpassen voor meldingen die door apparaatbesturingselement worden opgehaald</span><span class="sxs-lookup"><span data-stu-id="ee8a3-132">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="ee8a3-133">Wanneer het beleid voor apparaatbesturingselement dat u hebt toegepast, wordt afgedwongen op een apparaat (bijvoorbeeld de toegang tot een verwisselbaar mediaapparaat is beperkt), wordt er een melding weergegeven voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-133">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Melding apparaatbesturingselement](images/mac-device-control-notification.png)

<span data-ttu-id="ee8a3-135">Wanneer eindgebruikers op deze melding klikken, wordt er een webpagina geopend in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-135">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="ee8a3-136">U kunt de URL configureren die wordt geopend wanneer eindgebruikers op de melding klikken.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-136">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="ee8a3-137">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-137">Section</span></span>|<span data-ttu-id="ee8a3-138">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-138">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-139">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-139">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-140">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-140">**Key**</span></span> | <span data-ttu-id="ee8a3-141">navigatieTarget</span><span class="sxs-lookup"><span data-stu-id="ee8a3-141">navigationTarget</span></span> |
| <span data-ttu-id="ee8a3-142">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-142">**Data type**</span></span> | <span data-ttu-id="ee8a3-143">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ee8a3-143">String</span></span> |
| <span data-ttu-id="ee8a3-144">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-144">**Comments**</span></span> | <span data-ttu-id="ee8a3-145">Als het product niet is gedefinieerd, wordt een standaard-URL gebruikt die verwijst naar een algemene pagina waarin de actie van het product wordt uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-145">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="ee8a3-146">Verwisselbare apparaten toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="ee8a3-146">Allow or block removable devices</span></span>

<span data-ttu-id="ee8a3-147">De sectie verwisselbare media van het apparaatbesturingselementbeleid wordt gebruikt om de toegang tot verwisselbare media te beperken.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-147">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="ee8a3-148">De volgende typen verwisselbare media worden momenteel ondersteund en kunnen worden opgenomen in het beleid: USB-opslagapparaten.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-148">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="ee8a3-149">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-149">Section</span></span>|<span data-ttu-id="ee8a3-150">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-150">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-151">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-151">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-152">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-152">**Key**</span></span> | <span data-ttu-id="ee8a3-153">verwisselbaarMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="ee8a3-153">removableMediaPolicy</span></span> |
| <span data-ttu-id="ee8a3-154">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-154">**Data type**</span></span> | <span data-ttu-id="ee8a3-155">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-155">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="ee8a3-156">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-156">**Comments**</span></span> | <span data-ttu-id="ee8a3-157">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-157">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="ee8a3-158">Deze sectie van het beleid is hiërarchisch, waardoor maximale flexibiliteit mogelijk is en een groot aantal gebruiksgevallen wordt beslaat.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-158">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="ee8a3-159">Op het hoogste niveau zijn leveranciers, geïdentificeerd door een leverancier-id.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-159">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="ee8a3-160">Voor elke leverancier zijn er producten die zijn geïdentificeerd met een product-id.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-160">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="ee8a3-161">Ten slotte zijn er voor elk product serienummers met specifieke apparaten.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-161">Finally, for each product there are serial numbers denoting specific devices.</span></span>

```
|-- policy top level 
    |-- vendor 1 
        |-- product 1 
            |-- serial number 1 
            ...
            |-- serial number N 
        ...
        |-- product N 
    ...
    |-- vendor N
```

<span data-ttu-id="ee8a3-162">Zie Apparaataanduidingen op zoeken voor informatie over het vinden van [apparaataanduidingen.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-162">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="ee8a3-163">Het beleid wordt geëvalueerd vanaf de meest specifieke vermelding tot de meest algemene.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-163">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="ee8a3-164">Dit betekent dat wanneer een apparaat is aangesloten, het product probeert de meest specifieke overeenkomst te vinden in het beleid voor elk verwisselbaar mediaapparaat en de machtigingen op dat niveau toe te passen.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-164">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="ee8a3-165">Als er geen overeenkomst is, wordt de volgende beste overeenkomst toegepast, helemaal tot aan de machtiging die is opgegeven op het hoogste niveau, wat de standaardwaarde is wanneer een apparaat niet overeen komt met een andere vermelding in het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-165">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="ee8a3-166">Beleidshandhavingsniveau</span><span class="sxs-lookup"><span data-stu-id="ee8a3-166">Policy enforcement level</span></span>

<span data-ttu-id="ee8a3-167">Onder de sectie verwisselbare media is er een optie om het afdwingingsniveau in te stellen, dat een van de volgende waarden kan bevatten:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-167">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="ee8a3-168">`audit` - Als de toegang tot een apparaat is beperkt, wordt onder dit handhavingsniveau een melding weergegeven voor de gebruiker, maar het apparaat kan nog steeds worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-168">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="ee8a3-169">Dit handhavingsniveau kan handig zijn om de effectiviteit van een beleid te evalueren.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-169">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="ee8a3-170">`block` - Onder dit handhavingsniveau zijn de bewerkingen die de gebruiker op het apparaat kan uitvoeren, beperkt tot wat is gedefinieerd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-170">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="ee8a3-171">Bovendien wordt er een melding naar de gebruiker getrokken.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-171">Furthermore, a notification is raised to the user.</span></span> 

> [!NOTE] 
> <span data-ttu-id="ee8a3-172">Standaard is het afdwingingsniveau ingesteld op `audit` .</span><span class="sxs-lookup"><span data-stu-id="ee8a3-172">By default, the enforcement level is set to `audit`.</span></span> 

|<span data-ttu-id="ee8a3-173">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-173">Section</span></span>|<span data-ttu-id="ee8a3-174">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-174">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-175">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-175">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-176">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-176">**Key**</span></span> | <span data-ttu-id="ee8a3-177">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="ee8a3-177">enforcementLevel</span></span> |
| <span data-ttu-id="ee8a3-178">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-178">**Data type**</span></span> | <span data-ttu-id="ee8a3-179">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="ee8a3-179">String</span></span> |
| <span data-ttu-id="ee8a3-180">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-180">**Possible values**</span></span> | <span data-ttu-id="ee8a3-181">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-181">audit (default)</span></span> <br/> <span data-ttu-id="ee8a3-182">blokkering</span><span class="sxs-lookup"><span data-stu-id="ee8a3-182">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="ee8a3-183">Standaardmachtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="ee8a3-183">Default permission level</span></span>

<span data-ttu-id="ee8a3-184">Op het hoogste niveau van de sectie verwisselbare media kunt u het standaardmachtigingsniveau configureren voor apparaten die niet overeenkomen met iets anders in het beleid.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-184">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="ee8a3-185">Deze instelling kan worden ingesteld op:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-185">This setting can be set to:</span></span>

- <span data-ttu-id="ee8a3-186">`none` - Er kunnen geen bewerkingen worden uitgevoerd op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ee8a3-186">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="ee8a3-187">Een combinatie van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-187">A combination of the following values:</span></span>
    - <span data-ttu-id="ee8a3-188">`read` - Leesbewerkingen zijn toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ee8a3-188">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="ee8a3-189">`write` - Schrijfbewerkingen zijn toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ee8a3-189">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="ee8a3-190">`execute` - Bewerkingen uitvoeren is toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="ee8a3-190">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="ee8a3-191">Als het machtigingsniveau aanwezig is, worden andere `none` machtigingen ( `read` of ) `write` `execute` genegeerd.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-191">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="ee8a3-192">De `execute` machtiging verwijst alleen naar de uitvoering van Binaries van Mach-O.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-192">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="ee8a3-193">Het omvat geen uitvoering van scripts of andere soorten payloads.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-193">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="ee8a3-194">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-194">Section</span></span>|<span data-ttu-id="ee8a3-195">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-195">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-196">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-196">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-197">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-197">**Key**</span></span> | <span data-ttu-id="ee8a3-198">machtiging</span><span class="sxs-lookup"><span data-stu-id="ee8a3-198">permission</span></span> |
| <span data-ttu-id="ee8a3-199">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-199">**Data type**</span></span> | <span data-ttu-id="ee8a3-200">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-200">Array of strings</span></span> |
| <span data-ttu-id="ee8a3-201">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-201">**Possible values**</span></span> | <span data-ttu-id="ee8a3-202">geen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-202">none</span></span> <br/> <span data-ttu-id="ee8a3-203">gelezen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-203">read</span></span> <br/> <span data-ttu-id="ee8a3-204">schrijven</span><span class="sxs-lookup"><span data-stu-id="ee8a3-204">write</span></span> <br/> <span data-ttu-id="ee8a3-205">uitvoeren</span><span class="sxs-lookup"><span data-stu-id="ee8a3-205">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="ee8a3-206">Verwisselbare media beperken op leverancier, product en serienummer</span><span class="sxs-lookup"><span data-stu-id="ee8a3-206">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="ee8a3-207">Zoals beschreven in [Verwisselbare](#allow-or-block-removable-devices)apparaten toestaan of blokkeren, kunnen verwisselbare media, zoals USB-apparaten, worden geïdentificeerd met de leverancier-id, product-id en serienummer.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-207">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="ee8a3-208">Op het hoogste niveau van het verwisselbare mediabeleid kunt u desgewenst meer gedetailleerde beperkingen definiëren op leveranciersniveau.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-208">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="ee8a3-209">De `vendors` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door de leverancier-id.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-209">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="ee8a3-210">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-210">Section</span></span>|<span data-ttu-id="ee8a3-211">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-211">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-212">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-212">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-213">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-213">**Key**</span></span> | <span data-ttu-id="ee8a3-214">leveranciers</span><span class="sxs-lookup"><span data-stu-id="ee8a3-214">vendors</span></span> |
| <span data-ttu-id="ee8a3-215">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-215">**Data type**</span></span> | <span data-ttu-id="ee8a3-216">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-216">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ee8a3-217">Voor elke leverancier kunt u het gewenste machtigingsniveau opgeven voor apparaten van die leverancier.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-217">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="ee8a3-218">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-218">Section</span></span>|<span data-ttu-id="ee8a3-219">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-220">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-221">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-221">**Key**</span></span> | <span data-ttu-id="ee8a3-222">machtiging</span><span class="sxs-lookup"><span data-stu-id="ee8a3-222">permission</span></span> |
| <span data-ttu-id="ee8a3-223">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-223">**Data type**</span></span> | <span data-ttu-id="ee8a3-224">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-224">Array of strings</span></span> |
| <span data-ttu-id="ee8a3-225">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-225">**Possible values**</span></span> | <span data-ttu-id="ee8a3-226">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-226">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="ee8a3-227">Bovendien kunt u desgewenst de set producten opgeven die behoren tot die leverancier waarvoor gedetailleerdere machtigingen zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-227">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="ee8a3-228">De `products` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door de product-id.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-228">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="ee8a3-229">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-229">Section</span></span>|<span data-ttu-id="ee8a3-230">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-230">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-231">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-231">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-232">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-232">**Key**</span></span> | <span data-ttu-id="ee8a3-233">producten</span><span class="sxs-lookup"><span data-stu-id="ee8a3-233">products</span></span> |
| <span data-ttu-id="ee8a3-234">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-234">**Data type**</span></span> | <span data-ttu-id="ee8a3-235">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-235">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ee8a3-236">Voor elk product kunt u het gewenste machtigingsniveau voor dat product opgeven.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-236">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="ee8a3-237">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-237">Section</span></span>|<span data-ttu-id="ee8a3-238">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-239">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-240">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-240">**Key**</span></span> | <span data-ttu-id="ee8a3-241">machtiging</span><span class="sxs-lookup"><span data-stu-id="ee8a3-241">permission</span></span> |
| <span data-ttu-id="ee8a3-242">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-242">**Data type**</span></span> | <span data-ttu-id="ee8a3-243">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-243">Array of strings</span></span> |
| <span data-ttu-id="ee8a3-244">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-244">**Possible values**</span></span> | <span data-ttu-id="ee8a3-245">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-245">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="ee8a3-246">Bovendien kunt u een optionele set seriële getallen opgeven waarvoor gedetailleerdere machtigingen zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-246">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="ee8a3-247">De `serialNumbers` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door het serienummer.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-247">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="ee8a3-248">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-248">Section</span></span>|<span data-ttu-id="ee8a3-249">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-249">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-250">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-250">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-251">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-251">**Key**</span></span> | <span data-ttu-id="ee8a3-252">seriëlegetalen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-252">serialNumbers</span></span> |
| <span data-ttu-id="ee8a3-253">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-253">**Data type**</span></span> | <span data-ttu-id="ee8a3-254">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-254">Dictionary (nested preference)</span></span> |

<span data-ttu-id="ee8a3-255">Voor elk serienummer kunt u het gewenste machtigingsniveau opgeven.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-255">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="ee8a3-256">Sectie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-256">Section</span></span>|<span data-ttu-id="ee8a3-257">Waarde</span><span class="sxs-lookup"><span data-stu-id="ee8a3-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="ee8a3-258">**Domein**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="ee8a3-259">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-259">**Key**</span></span> | <span data-ttu-id="ee8a3-260">machtiging</span><span class="sxs-lookup"><span data-stu-id="ee8a3-260">permission</span></span> |
| <span data-ttu-id="ee8a3-261">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-261">**Data type**</span></span> | <span data-ttu-id="ee8a3-262">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-262">Array of strings</span></span> |
| <span data-ttu-id="ee8a3-263">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-263">**Possible values**</span></span> | <span data-ttu-id="ee8a3-264">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-264">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="ee8a3-265">Voorbeeld van apparaatbesturingselementbeleid</span><span class="sxs-lookup"><span data-stu-id="ee8a3-265">Example device control policy</span></span>

<span data-ttu-id="ee8a3-266">In het volgende voorbeeld ziet u hoe alle bovenstaande concepten kunnen worden gecombineerd tot een apparaatbesturingselementbeleid.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-266">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="ee8a3-267">Let in het volgende voorbeeld op de hiërarchische aard van het verwisselbare mediabeleid.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-267">In the following example, note the hierarchical nature of the removable media policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>navigationTarget</key> 
        <string>[custom URL for notifications]</string> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>[enforcement level]</string> <!-- audit / block --> 
            <key>permission</key> 
            <array> 
                <string>[permission]</string> <!-- none / read / write / execute --> 
                <!-- other permissions -->
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>[vendor id]</key> 
                <dict>
                    <key>permission</key> 
                    <array> 
                        <string>[permission]</string> <!-- none / read / write / execute --> 
                        <!-- other permissions -->
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>[product id]</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>[permission]</string> <!-- none / read / write / execute --> 
                                <!-- other permissions -->
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>[serial-number]</key> 
                                <array> 
                                    <string>[permission]</string> <!-- none / read / write / execute --> 
                                    <!-- other permissions -->
                                </array> 
                                <!-- other serial numbers --> 
                            </dict> 
                        </dict> 
                        <!-- other products --> 
                    </dict> 
                </dict> 
                <!-- other vendors --> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

<span data-ttu-id="ee8a3-268">We hebben meer voorbeelden van beleidsregels voor apparaatbeheer opgenomen in de volgende documenten:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-268">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="ee8a3-269">Voorbeelden van beleidsregels voor apparaatbesturingselementen voor Intune</span><span class="sxs-lookup"><span data-stu-id="ee8a3-269">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="ee8a3-270">Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF</span><span class="sxs-lookup"><span data-stu-id="ee8a3-270">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="ee8a3-271">Apparaat-id's zoeken</span><span class="sxs-lookup"><span data-stu-id="ee8a3-271">Look up device identifiers</span></span>

<span data-ttu-id="ee8a3-272">De leverancier-id, product-id en het serienummer van een USB-apparaat zoeken:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-272">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="ee8a3-273">Meld u aan bij een Mac-apparaat.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-273">Log into a Mac device.</span></span>
1. <span data-ttu-id="ee8a3-274">Sluit het USB-apparaat aan waarvoor u de id's wilt op zoeken.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-274">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="ee8a3-275">Selecteer In het menu op het hoogste niveau van macOS de optie **Over deze Mac.**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-275">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Over deze Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="ee8a3-277">Selecteer **Systeemrapport**.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-277">Select **System Report**.</span></span>

    ![Systeemrapport](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="ee8a3-279">Selecteer USB in de **linkerkolom.**</span><span class="sxs-lookup"><span data-stu-id="ee8a3-279">From the left column, select **USB**.</span></span>

    ![Weergave van alle USB-apparaten](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="ee8a3-281">Ga **onder USB-apparaatstructuur** naar het USB-apparaat dat u hebt aangesloten.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-281">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Details van een USB-apparaat](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="ee8a3-283">De leverancier-id, product-id en serienummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-283">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="ee8a3-284">Wanneer u de leverancier-id en product-id toevoegt aan het verwisselbare mediabeleid, hoeft u het onderdeel alleen daarna toe te `0x` voegen.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-284">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="ee8a3-285">In de onderstaande afbeelding is leverancier-id bijvoorbeeld `1000` en product-id. `090c`</span><span class="sxs-lookup"><span data-stu-id="ee8a3-285">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="ee8a3-286">USB-apparaten in uw organisatie ontdekken</span><span class="sxs-lookup"><span data-stu-id="ee8a3-286">Discover USB devices in your organization</span></span>

<span data-ttu-id="ee8a3-287">U kunt gebeurtenissen in de mount, unmount en volumewijziging bekijken die afkomstig zijn van USB-apparaten in Microsoft Defender for Endpoint advanced hunting.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-287">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="ee8a3-288">Deze gebeurtenissen kunnen handig zijn om verdachte gebruiksactiviteiten te identificeren of interne onderzoeken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-288">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMounted" or ActionType == "UsbDriveUnmounted" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="ee8a3-289">Apparaatbeheerbeleidsimplementatie</span><span class="sxs-lookup"><span data-stu-id="ee8a3-289">Device control policy deployment</span></span>

<span data-ttu-id="ee8a3-290">Het apparaatbesturingselementbeleid moet worden opgenomen naast de andere productinstellingen, zoals beschreven in Voorkeuren instellen voor Microsoft Defender voor Eindpunt [op macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-290">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="ee8a3-291">Dit profiel kan worden geïmplementeerd met de instructies die worden vermeld in [configuratieprofielimplementatie.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="ee8a3-291">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="ee8a3-292">Tips voor probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="ee8a3-292">Troubleshooting tips</span></span>

<span data-ttu-id="ee8a3-293">Nadat u het configuratieprofiel door Intune of JAMF hebt gedrenkt, kunt u controleren of het is opgehaald door het product door de volgende opdracht uit te voeren vanaf de Terminal:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-293">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="ee8a3-294">Deze opdracht wordt afgedrukt op standaarduitvoer van het apparaatbesturingselementbeleid dat het product gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-294">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="ee8a3-295">Als dit wordt afgedrukt, controleert u of (a) het configuratieprofiel inderdaad vanaf de beheerconsole naar uw apparaat is gedrenkt en (b) het een geldig apparaatbesturingselementbeleid is, zoals beschreven in dit `Policy is empty` document.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-295">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="ee8a3-296">Op een apparaat waarop het beleid is geleverd en waar een of meer apparaten zijn aangesloten, kunt u de volgende opdracht uitvoeren om alle apparaten en de effectieve machtigingen op te geven die op deze apparaten zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-296">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="ee8a3-297">Voorbeeld van uitvoer:</span><span class="sxs-lookup"><span data-stu-id="ee8a3-297">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="ee8a3-298">In het bovenstaande voorbeeld is er slechts één verwisselbaar mediaapparaat aangesloten en het heeft en machtigingen, volgens het beleid voor apparaatbesturingselement dat is geleverd `read` `execute` aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ee8a3-298">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ee8a3-299">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ee8a3-299">Related topics</span></span>

- [<span data-ttu-id="ee8a3-300">Voorbeelden van beleidsregels voor apparaatbesturingselementen voor Intune</span><span class="sxs-lookup"><span data-stu-id="ee8a3-300">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="ee8a3-301">Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF</span><span class="sxs-lookup"><span data-stu-id="ee8a3-301">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
