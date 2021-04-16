---
title: Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt voor Mac
description: Problemen met licenties oplossen in Microsoft Defender voor Eindpunt voor Mac.
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
ms.openlocfilehash: 3fb351d9ce8e9beef812e6aaa7d463161a6af8df
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862185"
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

