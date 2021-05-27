---
title: De Microsoft Defender Antivirus configureren met Microsoft Endpoint Manager
description: Gebruik Microsoft Endpoint Manager en Microsoft Intune voor het configureren van Microsoft Defender AV en Endpoint Protection
keywords: scep, intune, endpointbeveiliging, configuratie
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683749"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Gebruik Microsoft Endpoint Manager voor het configureren en beheren van Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt [de](/mem/endpoint-manager-overview) Microsoft Endpoint Manager gebruiken om de Microsoft Defender Antivirus configureren. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) en [Configuration Manager](/mem/configmgr/core/understand/introduction) maken nu deel uit van Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configureer Microsoft Defender Antivirus scans in Endpoint Manager

1. Ga naar het Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.

2. Ga naar **Endpoint-beveiliging.**

3. Kies **onder Beheren** de optie **Antivirus.**

4. Selecteer uw Microsoft Defender Antivirus beleid. 

5. Klik onder **Beheren** op **Eigenschappen**.

6. Kies na **Configuratie-instellingen** de optie **Bewerken**.

7. Vouw de **sectie Scannen** uit en bekijk of bewerk uw scaninstellingen.

8. Kies **Controleren + opslaan**


> [!TIP]
> Hulp nodig? Zie [Beveiliging van eindpunten beheren in Microsoft Intune.](/mem/intune/protect/endpoint-security)


## <a name="related-articles"></a>Aanverwante artikelen

- [Naslagartikelen voor beheer- en configuratiehulpmiddelen](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)