---
title: Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF
description: Meer informatie over het gebruik van beleidsregels voor apparaatbeheer met voorbeelden die kunnen worden gebruikt met JAMF.
keywords: microsoft, defender, eindpunt, atp, mac, apparaat, besturingselement, usb, verwisselbaar, media, jamf
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
ms.openlocfilehash: 8990979024c033d4142b595d6fef94f7b872e7c9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187675"
---
# <a name="examples-of-device-control-policies-for-jamf"></a><span data-ttu-id="713a9-104">Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF</span><span class="sxs-lookup"><span data-stu-id="713a9-104">Examples of device control policies for JAMF</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="713a9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="713a9-105">**Applies to:**</span></span>
- [<span data-ttu-id="713a9-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="713a9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="713a9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="713a9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="713a9-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="713a9-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="713a9-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="713a9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="713a9-110">Dit document bevat voorbeelden van beleidsregels voor apparaatbesturingselementen die u kunt aanpassen voor uw eigen organisatie.</span><span class="sxs-lookup"><span data-stu-id="713a9-110">This document contains examples of device control policies that you can customize for your own organization.</span></span> <span data-ttu-id="713a9-111">Deze voorbeelden zijn van toepassing als u JAMF gebruikt om apparaten in uw bedrijf te beheren.</span><span class="sxs-lookup"><span data-stu-id="713a9-111">These examples are applicable if you are using JAMF to manage devices in your enterprise.</span></span>

## <a name="restrict-access-to-all-removable-media"></a><span data-ttu-id="713a9-112">Toegang tot alle verwisselbare media beperken</span><span class="sxs-lookup"><span data-stu-id="713a9-112">Restrict access to all removable media</span></span>

<span data-ttu-id="713a9-113">In het volgende voorbeeld wordt de toegang tot alle verwisselbare media beperkt.</span><span class="sxs-lookup"><span data-stu-id="713a9-113">The following example restricts access to all removable media.</span></span> <span data-ttu-id="713a9-114">Let op de machtiging die wordt toegepast op het hoogste niveau van het beleid, wat betekent `none` dat alle bestandsbewerkingen zijn verboden.</span><span class="sxs-lookup"><span data-stu-id="713a9-114">Note the `none` permission that is applied at the top level of the policy, meaning that all file operations will be prohibited.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>none</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="set-all-removable-media-to-be-read-only"></a><span data-ttu-id="713a9-115">Alle verwisselbare media instellen op alleen-lezen</span><span class="sxs-lookup"><span data-stu-id="713a9-115">Set all removable media to be read-only</span></span>

<span data-ttu-id="713a9-116">In het volgende voorbeeld worden alle verwisselbare media geconfigureerd als alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="713a9-116">The following example configures all removable media to be read-only.</span></span> <span data-ttu-id="713a9-117">Noteer de machtiging die wordt toegepast op het hoogste niveau van het beleid, wat betekent dat alle schrijf- en `read` uitvoerbewerkingen worden afgekeurd.</span><span class="sxs-lookup"><span data-stu-id="713a9-117">Note the `read` permission that is applied at the top level of the policy, meaning that all write and execute operations will be disallowed.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="disallow-program-execution-from-removable-media"></a><span data-ttu-id="713a9-118">Programmauitvoering van verwisselbare media niet meer uitvoeren</span><span class="sxs-lookup"><span data-stu-id="713a9-118">Disallow program execution from removable media</span></span>

<span data-ttu-id="713a9-119">In het volgende voorbeeld ziet u hoe de uitvoering van programma's uit verwisselbare media kan worden afgekeurd.</span><span class="sxs-lookup"><span data-stu-id="713a9-119">The following example shows how program execution from removable media can be disallowed.</span></span> <span data-ttu-id="713a9-120">Noteer de `read` `write` machtigingen en machtigingen die worden toegepast op het hoogste niveau van het beleid.</span><span class="sxs-lookup"><span data-stu-id="713a9-120">Note the `read` and `write` permissions that are applied at the top level of the policy.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string> 
            </array> 
        </dict> 
    </dict> 
</dict> 
</plist>
```

## <a name="restrict-all-devices-from-specific-vendors"></a><span data-ttu-id="713a9-121">Alle apparaten van specifieke leveranciers beperken</span><span class="sxs-lookup"><span data-stu-id="713a9-121">Restrict all devices from specific vendors</span></span>

<span data-ttu-id="713a9-122">In het volgende voorbeeld worden alle apparaten van specifieke leveranciers beperkt (in dit geval geïdentificeerd door `fff0` en `4525` ).</span><span class="sxs-lookup"><span data-stu-id="713a9-122">The following example restricts all devices from specific vendors (in this case identified by `fff0` and `4525`).</span></span> <span data-ttu-id="713a9-123">Alle andere apparaten zijn onbeperkt, omdat de machtiging die is gedefinieerd op het hoogste niveau van het beleid alle mogelijke machtigingen bevat (lezen, schrijven en uitvoeren).</span><span class="sxs-lookup"><span data-stu-id="713a9-123">All other devices will be unrestricted, since the permission defined at the top level of the policy lists all possible permissions (read, write, and execute).</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string> 
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>none</string> 
                    </array> 
                </dict> 
                <key>4525</key> 
                <dict> 
                    <key>permission</key> 
                    <array>                         
                        <string>none</string> 
                    </array> 
                </dict> 
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a><span data-ttu-id="713a9-124">Specifieke apparaten beperken die zijn geïdentificeerd met leveranciers-id, product-id en serienummer</span><span class="sxs-lookup"><span data-stu-id="713a9-124">Restrict specific devices identified by vendor ID, product ID, and serial number</span></span>

<span data-ttu-id="713a9-125">In het volgende voorbeeld worden twee specifieke apparaten beperkt, die zijn geïdentificeerd met leveranciers-id, `fff0` `1000` product-id en `04ZSSMHI2O7WBVOA` serienummers en `04ZSSMHI2O7WBVOB` .</span><span class="sxs-lookup"><span data-stu-id="713a9-125">The following example restricts two specific devices, identified by vendor ID `fff0`, product ID `1000`, and serial numbers `04ZSSMHI2O7WBVOA` and `04ZSSMHI2O7WBVOB`.</span></span> <span data-ttu-id="713a9-126">Op alle andere niveaus van het beleid bevatten de machtigingen alle mogelijke waarden (lezen, schrijven en uitvoeren), wat betekent dat alle andere apparaten onbeperkt zijn.</span><span class="sxs-lookup"><span data-stu-id="713a9-126">At all other levels of the policy the permissions include all possible values (read, write, and execute), meaning that all other devices will be unrestricted.</span></span>

```xml
<?xml version="1.0" encoding="UTF-8"?> 
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd"> 
<plist version="1.0"> 
<dict> 
    <key>deviceControl</key> 
    <dict> 
        <key>removableMediaPolicy</key> 
        <dict> 
            <key>enforcementLevel</key> 
            <string>block</string> 
            <key>permission</key> 
            <array> 
                <string>read</string>
                <string>write</string>
                <string>execute</string>
            </array> 
            <key>vendors</key> 
            <dict> 
                <key>fff0</key> 
                <dict> 
                    <key>permission</key> 
                    <array> 
                        <string>read</string> 
                        <string>write</string>
                        <string>execute</string> 
                    </array> 
                    <key>products</key> 
                    <dict> 
                        <key>1000</key> 
                        <dict> 
                            <key>permission</key> 
                            <array> 
                                <string>read</string> 
                                <string>write</string>
                                <string>execute</string>
                            </array> 
                            <key>serialNumbers</key> 
                            <dict> 
                                <key>04ZSSMHI2O7WBVOA</key> 
                                <array> 
                                  <string>none</string> 
                                </array> 
                                <key>04ZSSMHI2O7WBVOB</key>
                                <array> 
                                  <string>none</string> 
                                </array> 
                            </dict> 
                        </dict> 
                    </dict> 
                </dict>
            </dict> 
        </dict> 
    </dict> 
</dict> 
</plist> 
```

## <a name="related-topics"></a><span data-ttu-id="713a9-127">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="713a9-127">Related topics</span></span>

- [<span data-ttu-id="713a9-128">Overzicht van apparaatbesturingselement voor macOS</span><span class="sxs-lookup"><span data-stu-id="713a9-128">Overview of device control for macOS</span></span>](mac-device-control-overview.md)
