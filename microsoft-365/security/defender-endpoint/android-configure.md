---
title: Microsoft Defender voor Eindpunt voor Android-functies configureren
description: Beschrijft hoe u Microsoft Defender voor Eindpunt voor Android configureert
keywords: microsoft, defender, atp, mde, android, configuratie
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
ms.openlocfilehash: c395aafc8a468cfdeaea973ab02421212870192a
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587213"
---
# <a name="configure-defender-for-endpoint-for-android-features"></a>Defender voor endpoint voor Android-functies configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="conditional-access-with-defender-for-endpoint-for-android"></a>Voorwaardelijke toegang met Defender voor Eindpunt voor Android  
Microsoft Defender voor Eindpunt voor Android, samen met Microsoft Intune en Azure Active Directory, maakt het afdwingen van apparaat compliance en beleid voor voorwaardelijke toegang mogelijk op basis van apparaatrisiconiveaus. Defender for Endpoint is een MTD-oplossing (Mobile Threat Defense) die u kunt implementeren om gebruik te maken van deze mogelijkheid via Intune.

Zie Defender voor Eindpunt en [Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)voor meer informatie over het instellen van Defender voor Eindpunt voor Android en Voorwaardelijke toegang.

## <a name="configure-custom-indicators"></a>Aangepaste indicatoren configureren  

> [!NOTE]
> Defender voor Eindpunt voor Android ondersteunt alleen het maken van aangepaste indicatoren voor IP-adressen en URL's/domeinen.

Met Defender voor Eindpunt voor Android kunnen beheerders aangepaste indicatoren configureren voor ondersteuning van Android-apparaten. Zie Indicatoren beheren voor meer informatie over het configureren van aangepaste [indicatoren.](manage-indicators.md)

## <a name="configure-web-protection"></a>Webbeveiliging configureren
Met Defender voor Eindpunt voor Android kunnen IT-beheerders de webbeveiligingsfunctie configureren. Deze mogelijkheid is beschikbaar in het Microsoft Endpoint Manager-beheercentrum.

> [!NOTE]
> Defender voor Eindpunt voor Android zou een VPN gebruiken om de webbeveiligingsfunctie te bieden. Dit is geen gewone VPN en is een lokale/self-looping VPN die geen verkeer buiten het apparaat neemt. Zie Webbeveiliging configureren op apparaten [met Android voor meer informatie.](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection-manage-android)

## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van Microsoft Defender voor Eindpunt voor Android](microsoft-defender-endpoint-android.md)
- [Microsoft Defender voor Eindpunt voor Android implementeren via Microsoft Intune](android-intune.md)
