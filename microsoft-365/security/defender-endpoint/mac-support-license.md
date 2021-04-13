---
title: Problemen met licenties oplossen voor Microsoft Defender ATP voor Mac
description: Problemen met licenties oplossen in Microsoft Defender ATP voor Mac.
keywords: microsoft, defender, atp, mac, performance
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689111"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt op macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Terwijl u door Microsoft Defender voor Eindpunt [](mac-install-manually.md) op [macOS](microsoft-defender-endpoint-mac.md) en Handmatige implementatietests of een Proof Of Concept (PoC) gaat, krijgt u mogelijk de volgende foutmelding:

![Afbeelding van licentiefout](images/no-license-found.png)

**Bericht:** 

Geen licentie gevonden

Het lijkt erop dat uw organisatie geen licentie voor Microsoft 365 Enterprise-abonnement heeft.

Neem contact op met uw beheerder voor hulp.

**Oorzaak:** 

U hebt het Microsoft Defender for Endpoint op macOS-pakket ('Installatiepakket downloaden') geïmplementeerd en/of geïnstalleerd, maar mogelijk hebt u het configuratiescript ("Onboarding-pakket downloaden") uitgevoerd.

**Oplossing:**

Volg de MicrosoftDefenderATPOnboardingMacOs.py instructies die hier worden beschreven: [Clientconfiguratie](mac-install-manually.md#client-configuration)

