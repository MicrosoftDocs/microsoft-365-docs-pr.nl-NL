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
# <a name="examples-of-device-control-policies-for-jamf"></a>Voorbeelden van beleidsregels voor apparaatbeheer voor JAMF

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Dit document bevat voorbeelden van beleidsregels voor apparaatbesturingselementen die u kunt aanpassen voor uw eigen organisatie. Deze voorbeelden zijn van toepassing als u JAMF gebruikt om apparaten in uw bedrijf te beheren.

## <a name="restrict-access-to-all-removable-media"></a>Toegang tot alle verwisselbare media beperken

In het volgende voorbeeld wordt de toegang tot alle verwisselbare media beperkt. Let op de machtiging die wordt toegepast op het hoogste niveau van het beleid, wat betekent `none` dat alle bestandsbewerkingen zijn verboden.

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

## <a name="set-all-removable-media-to-be-read-only"></a>Alle verwisselbare media instellen op alleen-lezen

In het volgende voorbeeld worden alle verwisselbare media geconfigureerd als alleen-lezen. Noteer de machtiging die wordt toegepast op het hoogste niveau van het beleid, wat betekent dat alle schrijf- en `read` uitvoerbewerkingen worden afgekeurd.

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

## <a name="disallow-program-execution-from-removable-media"></a>Programmauitvoering van verwisselbare media niet meer uitvoeren

In het volgende voorbeeld ziet u hoe de uitvoering van programma's uit verwisselbare media kan worden afgekeurd. Noteer de `read` `write` machtigingen en machtigingen die worden toegepast op het hoogste niveau van het beleid.

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

## <a name="restrict-all-devices-from-specific-vendors"></a>Alle apparaten van specifieke leveranciers beperken

In het volgende voorbeeld worden alle apparaten van specifieke leveranciers beperkt (in dit geval geïdentificeerd door `fff0` en `4525` ). Alle andere apparaten zijn onbeperkt, omdat de machtiging die is gedefinieerd op het hoogste niveau van het beleid alle mogelijke machtigingen bevat (lezen, schrijven en uitvoeren).

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

## <a name="restrict-specific-devices-identified-by-vendor-id-product-id-and-serial-number"></a>Specifieke apparaten beperken die zijn geïdentificeerd met leveranciers-id, product-id en serienummer

In het volgende voorbeeld worden twee specifieke apparaten beperkt, die zijn geïdentificeerd met leveranciers-id, `fff0` `1000` product-id en `04ZSSMHI2O7WBVOA` serienummers en `04ZSSMHI2O7WBVOB` . Op alle andere niveaus van het beleid bevatten de machtigingen alle mogelijke waarden (lezen, schrijven en uitvoeren), wat betekent dat alle andere apparaten onbeperkt zijn.

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

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van apparaatbesturingselement voor macOS](mac-device-control-overview.md)
