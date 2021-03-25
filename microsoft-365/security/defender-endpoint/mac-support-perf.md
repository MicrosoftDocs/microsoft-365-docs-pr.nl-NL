---
title: Prestatieproblemen oplossen voor Microsoft Defender ATP voor Mac
description: Problemen met de prestaties oplossen in Microsoft Defender ATP voor Mac.
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
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185907"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Prestatieproblemen oplossen voor Microsoft Defender voor Eindpunt voor Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt voor Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Dit onderwerp bevat enkele algemene stappen die kunnen worden gebruikt om prestatieproblemen met betrekking tot Microsoft Defender voor Eindpunt voor Mac te beperken.

Realtimebeveiliging (RTP) is een functie van Microsoft Defender voor Endpoint voor Mac waarmee uw apparaat continu wordt bewaakt en beschermd tegen bedreigingen. Het bestaat uit bestands- en procescontrole en andere heuristieken.

Afhankelijk van de toepassingen die u gebruikt en de kenmerken van uw apparaat, kunt u suboptimale prestaties ervaren bij het uitvoeren van Microsoft Defender voor Eindpunt voor Mac. Met name toepassingen of systeemprocessen die over een korte periode toegang hebben tot veel resources, kunnen leiden tot prestatieproblemen in Microsoft Defender voor Eindpunt voor Mac.

De volgende stappen kunnen worden gebruikt om deze problemen op te lossen en te beperken:

1. Schakel realtimebeveiliging uit met behulp van een van de volgende methoden en kijk of de prestaties verbeteren. Met deze methode kunt u bepalen of Microsoft Defender voor Eindpunt voor Mac bijdraagt aan de prestatieproblemen.

    Als uw apparaat niet wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld met behulp van een van de volgende opties:

    - Vanuit de gebruikersinterface. Open Microsoft Defender voor Eindpunt voor Mac en ga naar **Instellingen beheren.**

      ![Schermopname van realtimebeveiliging beheren](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - Vanuit de Terminal. Voor beveiligingsdoeleinden is voor deze bewerking hoogte vereist.

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    Als uw apparaat wordt beheerd door uw organisatie, kan realtimebeveiliging worden uitgeschakeld door uw beheerder met behulp van de instructies in Voorkeuren instellen voor [Microsoft Defender voor Eindpunt voor Mac.](mac-preferences.md)

2. Open Finder en navigeer naar **Applications**  >  **Utilities.** Open **Activiteitsmonitor** en analyseer welke toepassingen de resources op uw systeem gebruiken. Voorbeelden hiervan zijn software-updaters en compilers.

3. Configureer Microsoft Defender voor Eindpunt voor Mac met uitsluitingen voor de processen of schijflocaties die bijdragen aan de prestatieproblemen en realtime beveiliging opnieuw inschakelen.

    Zie [Uitsluitingen configureren en valideren voor Microsoft Defender voor Eindpunt voor Mac](mac-exclusions.md) voor meer informatie.
