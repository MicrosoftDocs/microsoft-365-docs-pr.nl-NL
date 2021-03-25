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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059477"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt voor Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt voor Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Terwijl u microsoft Defender voor eindpunt voor [](mac-install-manually.md) [Mac](microsoft-defender-endpoint-mac.md) en handmatige implementatietests of een Proof Of Concept (PoC) doormaakt, krijgt u mogelijk de volgende foutmelding:

![Afbeelding van licentiefout](images/no-license-found.png)

**Bericht:** 

Geen licentie gevonden

Het lijkt erop dat uw organisatie geen licentie voor Microsoft 365 Enterprise-abonnement heeft.

Neem contact op met uw beheerder voor hulp.

**Oorzaak:** 

U hebt het Microsoft Defender for Endpoint for macOS-pakket ("Installatiepakket downloaden") geïmplementeerd en/of geïnstalleerd, maar mogelijk hebt u het configuratiescript ("Onboarding-pakket downloaden") uitgevoerd.

**Oplossing:**

Volg de MicrosoftDefenderATPOnboardingMacOs.py instructies die hier worden beschreven: [Clientconfiguratie](mac-install-manually.md#client-configuration)
