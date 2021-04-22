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
ms.openlocfilehash: 39f8367c34e98c5e9dd11e9716f08e6c9e7fd9c0
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935123"
---
# <a name="device-control-for-macos"></a><span data-ttu-id="8a3c1-104">Apparaatbesturingselement voor macOS</span><span class="sxs-lookup"><span data-stu-id="8a3c1-104">Device control for macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8a3c1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-105">**Applies to:**</span></span>
- [<span data-ttu-id="8a3c1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8a3c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8a3c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8a3c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8a3c1-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8a3c1-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8a3c1-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="requirements"></a><span data-ttu-id="8a3c1-110">Vereisten</span><span class="sxs-lookup"><span data-stu-id="8a3c1-110">Requirements</span></span>

<span data-ttu-id="8a3c1-111">Apparaatbesturingselement voor macOS heeft de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-111">Device control for macOS has the following prerequisites:</span></span>

>[!div class="checklist"]
> - <span data-ttu-id="8a3c1-112">Microsoft Defender for Endpoint entitlement (can be trial)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-112">Microsoft Defender for Endpoint entitlement (can be trial)</span></span>
> - <span data-ttu-id="8a3c1-113">Minimale os-versie: macOS 10.15.4 of hoger</span><span class="sxs-lookup"><span data-stu-id="8a3c1-113">Minimum OS version: macOS 10.15.4 or higher</span></span>
> - <span data-ttu-id="8a3c1-114">Minimale productversie: 101.24.59</span><span class="sxs-lookup"><span data-stu-id="8a3c1-114">Minimum product version: 101.24.59</span></span>
> - <span data-ttu-id="8a3c1-115">Uw apparaat moet worden uitgevoerd met systeemextensies (dit is de standaardinstelling voor macOS 11 Big Sur).</span><span class="sxs-lookup"><span data-stu-id="8a3c1-115">Your device must be running with system extensions (this is the default on macOS 11 Big Sur).</span></span> 
> 
>   <span data-ttu-id="8a3c1-116">U kunt controleren of uw apparaat wordt uitgevoerd op systeemextensies door de volgende opdracht uit te voeren en te controleren of het wordt afgedrukt `endpoint_security_extension` op de console:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-116">You can check if your device is running on system extensions by running the following command and verify that it is printing `endpoint_security_extension` to the console:</span></span> 
> 
>   ```bash
>   mdatp health --field real_time_protection_subsystem 
>   ```
> - <span data-ttu-id="8a3c1-117">Uw apparaat moet zich in `Beta` het updatekanaal van `InsiderFast` Microsoft AutoUpdate (voorheen ) hebben.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-117">Your device must be in `Beta` (previously called `InsiderFast`) Microsoft AutoUpdate update channel.</span></span> <span data-ttu-id="8a3c1-118">Zie Updates implementeren [voor Microsoft Defender voor Eindpunt op Mac voor meer informatie.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-118">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>
> 
>   <span data-ttu-id="8a3c1-119">U kunt het updatekanaal controleren met de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-119">You can check the update channel using the following command:</span></span> 
> 
>    ```bash
>    mdatp health --field release_ring 
>    ```
>
>    <span data-ttu-id="8a3c1-120">Als de bovenstaande opdracht niet wordt afgedrukt `Beta` `InsiderFast` of, voert u de volgende opdracht uit vanaf de Terminal.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-120">If the above command does not print either `Beta` or `InsiderFast`, execute the following command from the Terminal.</span></span> <span data-ttu-id="8a3c1-121">De kanaalupdate wordt van kracht wanneer het product de volgende keer wordt gestart (wanneer de volgende productupdate is geïnstalleerd of wanneer het apparaat opnieuw wordt opgestart).</span><span class="sxs-lookup"><span data-stu-id="8a3c1-121">The channel update takes effect next time the product starts (when the next product update is installed or when the device is rebooted).</span></span> 
> 
>    ```bash
>    defaults write com.microsoft.autoupdate2 ChannelName -string Beta
>    ```
>
>    <span data-ttu-id="8a3c1-122">Als u zich in een beheerde omgeving (JAMF of Intune) hebt, kunt u het updatekanaal ook op afstand configureren.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-122">Alternatively, if you are in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="8a3c1-123">Zie Updates implementeren [voor Microsoft Defender voor Eindpunt op Mac voor meer informatie.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-123">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span> 

## <a name="device-control-policy"></a><span data-ttu-id="8a3c1-124">Apparaatbeheerbeleid</span><span class="sxs-lookup"><span data-stu-id="8a3c1-124">Device control policy</span></span>

<span data-ttu-id="8a3c1-125">Als u apparaatbesturingselement voor macOS wilt configureren, moet u een beleid maken waarin de beperkingen worden beschreven die u binnen uw organisatie wilt instellen.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-125">To configure device control for macOS, you must create a policy that describes the restrictions you want to put in place within your organization.</span></span>

<span data-ttu-id="8a3c1-126">Het apparaatbeheerbeleid is opgenomen in het configuratieprofiel dat wordt gebruikt om alle andere productinstellingen te configureren.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-126">The device control policy is included in the configuration profile used to configure all other product settings.</span></span> <span data-ttu-id="8a3c1-127">Zie Configuratieprofielstructuur [voor meer informatie.](mac-preferences.md#configuration-profile-structure)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-127">For more information, see [Configuration profile structure](mac-preferences.md#configuration-profile-structure).</span></span>

<span data-ttu-id="8a3c1-128">In het configuratieprofiel wordt het beleid voor apparaatbesturingselementen gedefinieerd in de volgende sectie:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-128">Within the configuration profile, the device control policy is defined in the following section:</span></span>

|<span data-ttu-id="8a3c1-129">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-129">Section</span></span>|<span data-ttu-id="8a3c1-130">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-130">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-131">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-131">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-132">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-132">**Key**</span></span> | <span data-ttu-id="8a3c1-133">deviceControl</span><span class="sxs-lookup"><span data-stu-id="8a3c1-133">deviceControl</span></span> |
| <span data-ttu-id="8a3c1-134">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-134">**Data type**</span></span> | <span data-ttu-id="8a3c1-135">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-135">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8a3c1-136">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-136">**Comments**</span></span> | <span data-ttu-id="8a3c1-137">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-137">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="8a3c1-138">Het apparaatbesturingselementbeleid kan worden gebruikt om:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-138">The device control policy can be used to:</span></span>

- [<span data-ttu-id="8a3c1-139">Het URL-doel aanpassen voor meldingen die door apparaatbesturingselementen worden opgehaald</span><span class="sxs-lookup"><span data-stu-id="8a3c1-139">Customize the URL target for notifications raised by device control</span></span>](#customize-url-target-for-notifications-raised-by-device-control)
- [<span data-ttu-id="8a3c1-140">Verwisselbare apparaten toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="8a3c1-140">Allow or block removable devices</span></span>](#allow-or-block-removable-devices)

### <a name="customize-url-target-for-notifications-raised-by-device-control"></a><span data-ttu-id="8a3c1-141">URL-doel aanpassen voor meldingen die door apparaatbesturingselement worden opgehaald</span><span class="sxs-lookup"><span data-stu-id="8a3c1-141">Customize URL target for notifications raised by device control</span></span>

<span data-ttu-id="8a3c1-142">Wanneer het beleid voor apparaatbesturingselement dat u hebt toegepast, wordt afgedwongen op een apparaat (bijvoorbeeld de toegang tot een verwisselbaar mediaapparaat is beperkt), wordt er een melding weergegeven voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-142">When the device control policy that you have put in place is enforced on a device (for example, access to a removable media device is restricted), a notification is displayed to the user.</span></span>

![Melding apparaatbesturingselement](images/mac-device-control-notification.png)

<span data-ttu-id="8a3c1-144">Wanneer eindgebruikers op deze melding klikken, wordt er een webpagina geopend in de standaardbrowser.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-144">When end users click this notification, a web page is opened in the default browser.</span></span> <span data-ttu-id="8a3c1-145">U kunt de URL configureren die wordt geopend wanneer eindgebruikers op de melding klikken.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-145">You can configure the URL that is opened when end users click the notification.</span></span>

|<span data-ttu-id="8a3c1-146">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-146">Section</span></span>|<span data-ttu-id="8a3c1-147">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-147">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-148">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-148">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-149">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-149">**Key**</span></span> | <span data-ttu-id="8a3c1-150">navigatieTarget</span><span class="sxs-lookup"><span data-stu-id="8a3c1-150">navigationTarget</span></span> |
| <span data-ttu-id="8a3c1-151">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-151">**Data type**</span></span> | <span data-ttu-id="8a3c1-152">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a3c1-152">String</span></span> |
| <span data-ttu-id="8a3c1-153">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-153">**Comments**</span></span> | <span data-ttu-id="8a3c1-154">Als het product niet is gedefinieerd, wordt een standaard-URL gebruikt die verwijst naar een algemene pagina waarin de actie van het product wordt uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-154">If not defined, the product uses a default URL pointing to a generic page explaining the action taken by the product.</span></span> |

### <a name="allow-or-block-removable-devices"></a><span data-ttu-id="8a3c1-155">Verwisselbare apparaten toestaan of blokkeren</span><span class="sxs-lookup"><span data-stu-id="8a3c1-155">Allow or block removable devices</span></span>

<span data-ttu-id="8a3c1-156">De sectie verwisselbare media van het apparaatbesturingselementbeleid wordt gebruikt om de toegang tot verwisselbare media te beperken.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-156">The removable media section of the device control policy is used to restrict access to removable media.</span></span> 

> [!NOTE]
> <span data-ttu-id="8a3c1-157">De volgende typen verwisselbare media worden momenteel ondersteund en kunnen worden opgenomen in het beleid: USB-opslagapparaten.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-157">The following types of removable media are currently supported and can be included in the policy: USB storage devices.</span></span>

|<span data-ttu-id="8a3c1-158">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-158">Section</span></span>|<span data-ttu-id="8a3c1-159">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-159">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-160">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-160">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-161">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-161">**Key**</span></span> | <span data-ttu-id="8a3c1-162">verwisselbaarMediaPolicy</span><span class="sxs-lookup"><span data-stu-id="8a3c1-162">removableMediaPolicy</span></span> |
| <span data-ttu-id="8a3c1-163">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-163">**Data type**</span></span> | <span data-ttu-id="8a3c1-164">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-164">Dictionary (nested preference)</span></span> |
| <span data-ttu-id="8a3c1-165">**Opmerkingen**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-165">**Comments**</span></span> | <span data-ttu-id="8a3c1-166">Zie de volgende secties voor een beschrijving van de inhoud van de woordenlijst.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-166">See the following sections for a description of the dictionary contents.</span></span> |

<span data-ttu-id="8a3c1-167">Deze sectie van het beleid is hiërarchisch, waardoor maximale flexibiliteit mogelijk is en een groot aantal gebruiksgevallen wordt beslaat.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-167">This section of the policy is hierarchical, allowing for maximum flexibility and covering a wide range of use cases.</span></span> <span data-ttu-id="8a3c1-168">Op het hoogste niveau zijn leveranciers, geïdentificeerd door een leverancier-id.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-168">At the top level are vendors, identified by a vendor ID.</span></span> <span data-ttu-id="8a3c1-169">Voor elke leverancier zijn er producten die zijn geïdentificeerd met een product-id.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-169">For each vendor, there are products, identified by a product ID.</span></span> <span data-ttu-id="8a3c1-170">Ten slotte zijn er voor elk product serienummers met specifieke apparaten.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-170">Finally, for each product there are serial numbers denoting specific devices.</span></span>

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

<span data-ttu-id="8a3c1-171">Zie Apparaataanduidingen op zoeken voor informatie over het vinden van [apparaataanduidingen.](#look-up-device-identifiers)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-171">For information on how to find the device identifiers, see [Look up device identifiers](#look-up-device-identifiers).</span></span>

<span data-ttu-id="8a3c1-172">Het beleid wordt geëvalueerd vanaf de meest specifieke vermelding tot de meest algemene.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-172">The policy is evaluated from the most specific entry to the most general one.</span></span> <span data-ttu-id="8a3c1-173">Dit betekent dat wanneer een apparaat is aangesloten, het product probeert de meest specifieke overeenkomst te vinden in het beleid voor elk verwisselbaar mediaapparaat en de machtigingen op dat niveau toe te passen.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-173">Meaning, when a device is plugged in, the product tries to find the most specific match in the policy for each removable media device and apply the permissions at that level.</span></span> <span data-ttu-id="8a3c1-174">Als er geen overeenkomst is, wordt de volgende beste overeenkomst toegepast, helemaal tot aan de machtiging die is opgegeven op het hoogste niveau, wat de standaardwaarde is wanneer een apparaat niet overeen komt met een andere vermelding in het beleid.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-174">If there is no match, then the next best match is applied, all the way to the permission specified at the top level, which is the default when a device does not match any other entry in the policy.</span></span>

#### <a name="policy-enforcement-level"></a><span data-ttu-id="8a3c1-175">Beleidshandhavingsniveau</span><span class="sxs-lookup"><span data-stu-id="8a3c1-175">Policy enforcement level</span></span>

<span data-ttu-id="8a3c1-176">Onder de sectie verwisselbare media is er een optie om het afdwingingsniveau in te stellen, dat een van de volgende waarden kan bevatten:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-176">Under the removable media section, there is an option to set the enforcement level, which can take one of the following values:</span></span>

- <span data-ttu-id="8a3c1-177">`audit` - Als de toegang tot een apparaat is beperkt, wordt onder dit handhavingsniveau een melding weergegeven voor de gebruiker, maar het apparaat kan nog steeds worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-177">`audit` - Under this enforcement level, if access to a device is restricted, a notification is displayed to the user, however the device can still be used.</span></span> <span data-ttu-id="8a3c1-178">Dit handhavingsniveau kan handig zijn om de effectiviteit van een beleid te evalueren.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-178">This enforcement level can be useful to evaluate the effectiveness of a policy.</span></span>
- <span data-ttu-id="8a3c1-179">`block` - Onder dit handhavingsniveau zijn de bewerkingen die de gebruiker op het apparaat kan uitvoeren, beperkt tot wat is gedefinieerd in het beleid.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-179">`block` - Under this enforcement level, the operations that the user can perform on the device are limited to what is defined in the policy.</span></span> <span data-ttu-id="8a3c1-180">Bovendien wordt er een melding naar de gebruiker getrokken.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-180">Furthermore, a notification is raised to the user.</span></span> 

|<span data-ttu-id="8a3c1-181">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-181">Section</span></span>|<span data-ttu-id="8a3c1-182">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-182">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-183">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-183">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-184">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-184">**Key**</span></span> | <span data-ttu-id="8a3c1-185">enforcementLevel</span><span class="sxs-lookup"><span data-stu-id="8a3c1-185">enforcementLevel</span></span> |
| <span data-ttu-id="8a3c1-186">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-186">**Data type**</span></span> | <span data-ttu-id="8a3c1-187">Tekenreeks</span><span class="sxs-lookup"><span data-stu-id="8a3c1-187">String</span></span> |
| <span data-ttu-id="8a3c1-188">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-188">**Possible values**</span></span> | <span data-ttu-id="8a3c1-189">audit (standaard)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-189">audit (default)</span></span> <br/> <span data-ttu-id="8a3c1-190">blokkering</span><span class="sxs-lookup"><span data-stu-id="8a3c1-190">block</span></span> |

#### <a name="default-permission-level"></a><span data-ttu-id="8a3c1-191">Standaardmachtigingsniveau</span><span class="sxs-lookup"><span data-stu-id="8a3c1-191">Default permission level</span></span>

<span data-ttu-id="8a3c1-192">Op het hoogste niveau van de sectie verwisselbare media kunt u het standaardmachtigingsniveau configureren voor apparaten die niet overeenkomen met iets anders in het beleid.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-192">At the top level of the removable media section, you can configure the default permission level for devices that do not match anything else in the policy.</span></span>

<span data-ttu-id="8a3c1-193">Deze instelling kan worden ingesteld op:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-193">This setting can be set to:</span></span>

- <span data-ttu-id="8a3c1-194">`none` - Er kunnen geen bewerkingen worden uitgevoerd op het apparaat</span><span class="sxs-lookup"><span data-stu-id="8a3c1-194">`none` - No operations can be performed on the device</span></span>
- <span data-ttu-id="8a3c1-195">Een combinatie van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-195">A combination of the following values:</span></span>
    - <span data-ttu-id="8a3c1-196">`read` - Leesbewerkingen zijn toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="8a3c1-196">`read` - Read operations are permitted on the device</span></span>
    - <span data-ttu-id="8a3c1-197">`write` - Schrijfbewerkingen zijn toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="8a3c1-197">`write` - Write operations are permitted on the device</span></span>
    - <span data-ttu-id="8a3c1-198">`execute` - Bewerkingen uitvoeren is toegestaan op het apparaat</span><span class="sxs-lookup"><span data-stu-id="8a3c1-198">`execute` - Execute operations are permitted on the device</span></span>

> [!NOTE]
> <span data-ttu-id="8a3c1-199">Als het machtigingsniveau aanwezig is, worden andere `none` machtigingen ( `read` of ) `write` `execute` genegeerd.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-199">If `none` is present in the permission level, any other permissions (`read`, `write`, or `execute`) will be ignored.</span></span>

> [!NOTE]
> <span data-ttu-id="8a3c1-200">De `execute` machtiging verwijst alleen naar de uitvoering van Binaries van Mach-O.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-200">The `execute` permission only refers to execution of Mach-O binaries.</span></span> <span data-ttu-id="8a3c1-201">Het omvat geen uitvoering van scripts of andere soorten payloads.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-201">It does not include execution of scripts or other types of payloads.</span></span>

|<span data-ttu-id="8a3c1-202">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-202">Section</span></span>|<span data-ttu-id="8a3c1-203">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-203">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-204">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-204">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-205">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-205">**Key**</span></span> | <span data-ttu-id="8a3c1-206">machtiging</span><span class="sxs-lookup"><span data-stu-id="8a3c1-206">permission</span></span> |
| <span data-ttu-id="8a3c1-207">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-207">**Data type**</span></span> | <span data-ttu-id="8a3c1-208">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-208">Array of strings</span></span> |
| <span data-ttu-id="8a3c1-209">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-209">**Possible values**</span></span> | <span data-ttu-id="8a3c1-210">geen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-210">none</span></span> <br/> <span data-ttu-id="8a3c1-211">gelezen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-211">read</span></span> <br/> <span data-ttu-id="8a3c1-212">schrijven</span><span class="sxs-lookup"><span data-stu-id="8a3c1-212">write</span></span> <br/> <span data-ttu-id="8a3c1-213">uitvoeren</span><span class="sxs-lookup"><span data-stu-id="8a3c1-213">execute</span></span> |

#### <a name="restrict-removable-media-by-vendor-product-and-serial-number"></a><span data-ttu-id="8a3c1-214">Verwisselbare media beperken op leverancier, product en serienummer</span><span class="sxs-lookup"><span data-stu-id="8a3c1-214">Restrict removable media by vendor, product, and serial number</span></span>

<span data-ttu-id="8a3c1-215">Zoals beschreven in [Verwisselbare](#allow-or-block-removable-devices)apparaten toestaan of blokkeren, kunnen verwisselbare media, zoals USB-apparaten, worden geïdentificeerd met de leverancier-id, product-id en serienummer.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-215">As described in [Allow or block removable devices](#allow-or-block-removable-devices), removable media such as USB devices can be identified by the vendor ID, product ID, and serial number.</span></span>

<span data-ttu-id="8a3c1-216">Op het hoogste niveau van het verwisselbare mediabeleid kunt u desgewenst meer gedetailleerde beperkingen definiëren op leveranciersniveau.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-216">At the top level of the removable media policy, you can optionally define more granular restrictions at the vendor level.</span></span> 

<span data-ttu-id="8a3c1-217">De `vendors` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door de leverancier-id.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-217">The `vendors` dictionary contains one or more entries, with each entry being identified by the vendor ID.</span></span>

|<span data-ttu-id="8a3c1-218">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-218">Section</span></span>|<span data-ttu-id="8a3c1-219">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-219">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-220">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-220">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-221">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-221">**Key**</span></span> | <span data-ttu-id="8a3c1-222">leveranciers</span><span class="sxs-lookup"><span data-stu-id="8a3c1-222">vendors</span></span> |
| <span data-ttu-id="8a3c1-223">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-223">**Data type**</span></span> | <span data-ttu-id="8a3c1-224">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-224">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8a3c1-225">Voor elke leverancier kunt u het gewenste machtigingsniveau opgeven voor apparaten van die leverancier.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-225">For each vendor, you can specify the desired permission level for devices from that vendor.</span></span>

|<span data-ttu-id="8a3c1-226">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-226">Section</span></span>|<span data-ttu-id="8a3c1-227">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-227">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-228">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-228">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-229">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-229">**Key**</span></span> | <span data-ttu-id="8a3c1-230">machtiging</span><span class="sxs-lookup"><span data-stu-id="8a3c1-230">permission</span></span> |
| <span data-ttu-id="8a3c1-231">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-231">**Data type**</span></span> | <span data-ttu-id="8a3c1-232">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-232">Array of strings</span></span> |
| <span data-ttu-id="8a3c1-233">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-233">**Possible values**</span></span> | <span data-ttu-id="8a3c1-234">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-234">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="8a3c1-235">Bovendien kunt u desgewenst de set producten opgeven die behoren tot die leverancier waarvoor gedetailleerdere machtigingen zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-235">Furthermore, you can optionally specify the set of products belonging to that vendor for which more granular permissions are defined.</span></span> <span data-ttu-id="8a3c1-236">De `products` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door de product-id.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-236">The `products` dictionary contains one or more entries, with each entry being identified by the product ID.</span></span> 

|<span data-ttu-id="8a3c1-237">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-237">Section</span></span>|<span data-ttu-id="8a3c1-238">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-238">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-239">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-239">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-240">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-240">**Key**</span></span> | <span data-ttu-id="8a3c1-241">producten</span><span class="sxs-lookup"><span data-stu-id="8a3c1-241">products</span></span> |
| <span data-ttu-id="8a3c1-242">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-242">**Data type**</span></span> | <span data-ttu-id="8a3c1-243">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-243">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8a3c1-244">Voor elk product kunt u het gewenste machtigingsniveau voor dat product opgeven.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-244">For each product, you can specify the desired permission level for that product.</span></span>

|<span data-ttu-id="8a3c1-245">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-245">Section</span></span>|<span data-ttu-id="8a3c1-246">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-246">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-247">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-247">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-248">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-248">**Key**</span></span> | <span data-ttu-id="8a3c1-249">machtiging</span><span class="sxs-lookup"><span data-stu-id="8a3c1-249">permission</span></span> |
| <span data-ttu-id="8a3c1-250">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-250">**Data type**</span></span> | <span data-ttu-id="8a3c1-251">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-251">Array of strings</span></span> |
| <span data-ttu-id="8a3c1-252">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-252">**Possible values**</span></span> | <span data-ttu-id="8a3c1-253">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-253">Same as [Default permission level](#default-permission-level)</span></span> |

<span data-ttu-id="8a3c1-254">Bovendien kunt u een optionele set seriële getallen opgeven waarvoor gedetailleerdere machtigingen zijn gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-254">Furthermore, you can specify an optional set of serial numbers for which more granular permissions are defined.</span></span>

<span data-ttu-id="8a3c1-255">De `serialNumbers` woordenlijst bevat een of meer vermeldingen, met elk item dat wordt geïdentificeerd door het serienummer.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-255">The `serialNumbers` dictionary contains one or more entries, with each entry being identified by the serial number.</span></span>

|<span data-ttu-id="8a3c1-256">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-256">Section</span></span>|<span data-ttu-id="8a3c1-257">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-257">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-258">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-258">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-259">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-259">**Key**</span></span> | <span data-ttu-id="8a3c1-260">seriëlegetalen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-260">serialNumbers</span></span> |
| <span data-ttu-id="8a3c1-261">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-261">**Data type**</span></span> | <span data-ttu-id="8a3c1-262">Woordenlijst (geneste voorkeur)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-262">Dictionary (nested preference)</span></span> |

<span data-ttu-id="8a3c1-263">Voor elk serienummer kunt u het gewenste machtigingsniveau opgeven.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-263">For each serial number, you can specify the desired permission level.</span></span>

|<span data-ttu-id="8a3c1-264">Sectie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-264">Section</span></span>|<span data-ttu-id="8a3c1-265">Waarde</span><span class="sxs-lookup"><span data-stu-id="8a3c1-265">Value</span></span>|
|:---|:---|
| <span data-ttu-id="8a3c1-266">**Domein**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-266">**Domain**</span></span> | `com.microsoft.wdav` |
| <span data-ttu-id="8a3c1-267">**Sleutel**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-267">**Key**</span></span> | <span data-ttu-id="8a3c1-268">machtiging</span><span class="sxs-lookup"><span data-stu-id="8a3c1-268">permission</span></span> |
| <span data-ttu-id="8a3c1-269">**Gegevenstype**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-269">**Data type**</span></span> | <span data-ttu-id="8a3c1-270">Matrix met tekenreeksen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-270">Array of strings</span></span> |
| <span data-ttu-id="8a3c1-271">**Mogelijke waarden**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-271">**Possible values**</span></span> | <span data-ttu-id="8a3c1-272">Hetzelfde als [standaardmachtigingsniveau](#default-permission-level)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-272">Same as [Default permission level](#default-permission-level)</span></span> |

#### <a name="example-device-control-policy"></a><span data-ttu-id="8a3c1-273">Voorbeeld van apparaatbesturingselementbeleid</span><span class="sxs-lookup"><span data-stu-id="8a3c1-273">Example device control policy</span></span>

<span data-ttu-id="8a3c1-274">In het volgende voorbeeld ziet u hoe alle bovenstaande concepten kunnen worden gecombineerd tot een apparaatbesturingselementbeleid.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-274">The following example shows how all of the above concepts can be combined into a device control policy.</span></span> <span data-ttu-id="8a3c1-275">Let in het volgende voorbeeld op de hiërarchische aard van het verwisselbare mediabeleid.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-275">In the following example, note the hierarchical nature of the removable media policy.</span></span>

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

<span data-ttu-id="8a3c1-276">We hebben meer voorbeelden van beleidsregels voor apparaatbeheer opgenomen in de volgende documenten:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-276">We have included more examples of device control policies in the following documents:</span></span>

- [<span data-ttu-id="8a3c1-277">Voorbeelden van beleidsregels voor apparaatbesturingselementen voor Intune</span><span class="sxs-lookup"><span data-stu-id="8a3c1-277">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="8a3c1-278">Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF</span><span class="sxs-lookup"><span data-stu-id="8a3c1-278">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)

#### <a name="look-up-device-identifiers"></a><span data-ttu-id="8a3c1-279">Apparaat-id's zoeken</span><span class="sxs-lookup"><span data-stu-id="8a3c1-279">Look up device identifiers</span></span>

<span data-ttu-id="8a3c1-280">De leverancier-id, product-id en het serienummer van een USB-apparaat zoeken:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-280">To find the vendor ID, product ID, and serial number of a USB device:</span></span>

1. <span data-ttu-id="8a3c1-281">Meld u aan bij een Mac-apparaat.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-281">Log into a Mac device.</span></span>
1. <span data-ttu-id="8a3c1-282">Sluit het USB-apparaat aan waarvoor u de id's wilt op zoeken.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-282">Plug in the USB device for which you want to look up the identifiers.</span></span>
1. <span data-ttu-id="8a3c1-283">Selecteer In het menu op het hoogste niveau van macOS de optie **Over deze Mac.**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-283">In the top-level menu of macOS, select **About This Mac**.</span></span>

    ![Over deze Mac](images/mac-device-control-lookup-1.png)

1. <span data-ttu-id="8a3c1-285">Selecteer **Systeemrapport**.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-285">Select **System Report**.</span></span>

    ![Systeemrapport](images/mac-device-control-lookup-2.png)

1. <span data-ttu-id="8a3c1-287">Selecteer USB in de **linkerkolom.**</span><span class="sxs-lookup"><span data-stu-id="8a3c1-287">From the left column, select **USB**.</span></span>

    ![Weergave van alle USB-apparaten](images/mac-device-control-lookup-3.png)

1. <span data-ttu-id="8a3c1-289">Ga **onder USB-apparaatstructuur** naar het USB-apparaat dat u hebt aangesloten.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-289">Under **USB Device Tree**, navigate to the USB device that you plugged in.</span></span>

    ![Details van een USB-apparaat](images/mac-device-control-lookup-4.png)

1. <span data-ttu-id="8a3c1-291">De leverancier-id, product-id en serienummer worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-291">The vendor ID, product ID, and serial number are displayed.</span></span> <span data-ttu-id="8a3c1-292">Wanneer u de leverancier-id en product-id toevoegt aan het verwisselbare mediabeleid, hoeft u het onderdeel alleen daarna toe te `0x` voegen.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-292">When adding the vendor ID and product ID to the removable media policy, you must only add the part after `0x`.</span></span> <span data-ttu-id="8a3c1-293">In de onderstaande afbeelding is leverancier-id bijvoorbeeld `1000` en product-id. `090c`</span><span class="sxs-lookup"><span data-stu-id="8a3c1-293">For example, in the below image, vendor ID is `1000` and product ID is `090c`.</span></span>

#### <a name="discover-usb-devices-in-your-organization"></a><span data-ttu-id="8a3c1-294">USB-apparaten in uw organisatie ontdekken</span><span class="sxs-lookup"><span data-stu-id="8a3c1-294">Discover USB devices in your organization</span></span>

<span data-ttu-id="8a3c1-295">U kunt gebeurtenissen in de mount, unmount en volumewijziging bekijken die afkomstig zijn van USB-apparaten in Microsoft Defender for Endpoint advanced hunting.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-295">You can view mount, unmount, and volume change events originating from USB devices in Microsoft Defender for Endpoint advanced hunting.</span></span> <span data-ttu-id="8a3c1-296">Deze gebeurtenissen kunnen handig zijn om verdachte gebruiksactiviteiten te identificeren of interne onderzoeken uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-296">These events can be helpful to identify suspicious usage activity or perform internal investigations.</span></span>

```
DeviceEvents 
    | where ActionType == "UsbDriveMount" or ActionType == "UsbDriveUnmount" or ActionType == "UsbDriveDriveLetterChanged"
    | where DeviceId == "<device ID>"
```

## <a name="device-control-policy-deployment"></a><span data-ttu-id="8a3c1-297">Apparaatbeheerbeleidsimplementatie</span><span class="sxs-lookup"><span data-stu-id="8a3c1-297">Device control policy deployment</span></span>

<span data-ttu-id="8a3c1-298">Het apparaatbesturingselementbeleid moet worden opgenomen naast de andere productinstellingen, zoals beschreven in Voorkeuren instellen voor Microsoft Defender voor Eindpunt [op macOS.](mac-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-298">The device control policy must be included next to the other product settings, as described in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="8a3c1-299">Dit profiel kan worden geïmplementeerd met de instructies die worden vermeld in [configuratieprofielimplementatie.](mac-preferences.md#configuration-profile-deployment)</span><span class="sxs-lookup"><span data-stu-id="8a3c1-299">This profile can be deployed using the instructions listed in [Configuration profile deployment](mac-preferences.md#configuration-profile-deployment).</span></span>

## <a name="troubleshooting-tips"></a><span data-ttu-id="8a3c1-300">Tips voor probleemoplossing</span><span class="sxs-lookup"><span data-stu-id="8a3c1-300">Troubleshooting tips</span></span>

<span data-ttu-id="8a3c1-301">Nadat u het configuratieprofiel door Intune of JAMF hebt gedrenkt, kunt u controleren of het is opgehaald door het product door de volgende opdracht uit te voeren vanaf de Terminal:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-301">After pushing the configuration profile through Intune or JAMF, you can check if it was successfully picked up by the product by running the following command from the Terminal:</span></span>

```bash
mdatp device-control removable-media policy list
```

<span data-ttu-id="8a3c1-302">Deze opdracht wordt afgedrukt op standaarduitvoer van het apparaatbesturingselementbeleid dat het product gebruikt.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-302">This command will print to standard output the device control policy that the product is using.</span></span> <span data-ttu-id="8a3c1-303">Als dit wordt afgedrukt, controleert u of (a) het configuratieprofiel inderdaad vanaf de beheerconsole naar uw apparaat is gedrenkt en (b) het een geldig apparaatbesturingselementbeleid is, zoals beschreven in dit `Policy is empty` document.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-303">In case this prints `Policy is empty`, make sure that (a) the configuration profile has indeed been pushed to your device from the management console, and (b) it is a valid device control policy, as described in this document.</span></span>

<span data-ttu-id="8a3c1-304">Op een apparaat waarop het beleid is geleverd en waar een of meer apparaten zijn aangesloten, kunt u de volgende opdracht uitvoeren om alle apparaten en de effectieve machtigingen op te geven die op deze apparaten zijn toegepast.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-304">On a device where the policy has been delivered successfully and where there are one or more devices plugged in, you can run the following command to list all devices and the effective permissions applied to them.</span></span>

```bash
mdatp device-control removable-media devices list
```

<span data-ttu-id="8a3c1-305">Voorbeeld van uitvoer:</span><span class="sxs-lookup"><span data-stu-id="8a3c1-305">Example of output:</span></span>

```Output
.Device(s)
|-o Name: Untitled 1, Permission ["read", "execute"]
| |-o Vendor: General "fff0"
| |-o Product: USB Flash Disk "1000"
| |-o Serial number: "04ZSSMHI2O7WBVOA"
| |-o Mount point: "/Volumes/TESTUSB"
```

<span data-ttu-id="8a3c1-306">In het bovenstaande voorbeeld is er slechts één verwisselbaar mediaapparaat aangesloten en het heeft en machtigingen, volgens het beleid voor apparaatbesturingselement dat is geleverd `read` `execute` aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="8a3c1-306">In the above example, there is only one removable media device plugged in and it has `read` and `execute` permissions, according to the device control policy that was delivered to the device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8a3c1-307">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8a3c1-307">Related topics</span></span>

- [<span data-ttu-id="8a3c1-308">Voorbeelden van beleidsregels voor apparaatbesturingselementen voor Intune</span><span class="sxs-lookup"><span data-stu-id="8a3c1-308">Examples of device control policies for Intune</span></span>](mac-device-control-intune.md)
- [<span data-ttu-id="8a3c1-309">Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF</span><span class="sxs-lookup"><span data-stu-id="8a3c1-309">Examples of device control policies for JAMF</span></span>](mac-device-control-jamf.md)
