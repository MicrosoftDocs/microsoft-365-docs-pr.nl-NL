---
title: Apparaatgroepen instellen in Jamf Pro
description: Informatie over het instellen van apparaatgroepen in Jamf Pro voor Microsoft Defender voor Endpoint voor macOS
keywords: apparaat, groep, microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 80dcb4ff73edd5e95603b15e097232a43dc0e05e
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861597"
---
# <a name="set-up-microsoft-defender-for-endpoint-on-macos-device-groups-in-jamf-pro"></a>Microsoft Defender voor eindpunt instellen voor macOS-apparaatgroepen in Jamf Pro

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Stel de apparaatgroepen in die lijken op Group policy organizational unite (OUs), de apparaatverzameling van Microsoft Endpoint Configuration Manager en de apparaatgroepen van Intune.

1. **Navigeer naar statische computergroepen.**

2. Selecteer **Nieuw.** 

    ![Afbeelding van Jamf Pro1](images/jamf-pro-static-group.png)

3. Geef een weergavenaam op en selecteer **Opslaan.**

    ![Afbeelding van Jamf Pro2](images/jamfpro-machine-group.png)

4. Nu ziet u de **contoso-machinegroep** onder **Statische computergroepen.**

    ![Afbeelding van Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a>Volgende stap
- [Microsoft Defender voor eindpunt instellen voor macOS-beleid in Jamf Pro](mac-jamfpro-policies.md)
