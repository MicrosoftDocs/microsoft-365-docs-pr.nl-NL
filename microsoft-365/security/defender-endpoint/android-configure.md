---
title: Microsoft Defender voor Eindpunt in Android-functies configureren
description: Hier wordt beschreven hoe u Microsoft Defender voor Eindpunt configureert op Android
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, mde, android, configuratie
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 462fa6177ee35d5d988efa985422b499e2339ff4
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935315"
---
# <a name="configure-defender-for-endpoint-on-android-features"></a>Defender voor eindpunt configureren op Android-functies

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-on-android"></a>Voorwaardelijke toegang met Defender voor Eindpunt op Android  
Microsoft Defender voor Eindpunt op Android, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus. Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.

Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Defender voor eindpunten op Android en Voorwaardelijke toegang.

## <a name="configure-custom-indicators"></a>Aangepaste indicatoren configureren  

> [!NOTE]
> Defender voor Eindpunt op Android ondersteunt alleen het maken van aangepaste indicatoren voor IP-adressen en URL's/domeinen.

Met Defender voor Eindpunt op Android kunnen beheerders aangepaste indicatoren configureren voor ondersteuning van Android-apparaten. Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](manage-indicators.md)

## <a name="configure-web-protection"></a>Webbeveiliging configureren
Met Defender voor Eindpunt op Android kunnen IT-beheerders de webbeveiligingsfunctie configureren. Deze mogelijkheid is beschikbaar in het Microsoft Endpoint Manager-beheercentrum.

> [!NOTE]
> Defender voor Eindpunt op Android zou een VPN gebruiken om de webbeveiligingsfunctie te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt. Zie Webbeveiliging configureren op apparaten [met Android voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van Microsoft Defender voor Eindpunt op Android](microsoft-defender-endpoint-android.md)
- [Microsoft Defender voor Eindpunt op Android implementeren via Microsoft Intune](android-intune.md)
