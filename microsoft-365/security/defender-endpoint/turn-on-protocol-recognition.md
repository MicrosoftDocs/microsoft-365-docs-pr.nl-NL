---
title: Protocolherkenning in Microsoft Defender Antivirus
description: Schakel protocolherkenning in voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, protocolherkenning
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296469"
---
# <a name="turn-on-protocol-recognition"></a>Protocolherkenning in- en uit- 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Met deze beleidsinstelling kunt u protocolherkenning configureren voor netwerkbeveiliging tegen misbruik van bekende beveiligingslekken. Als u deze instelling in- of configureert, is protocolherkenning ingeschakeld. Als u deze instelling uit schakelt, wordt protocolherkenning uitgeschakeld.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Groepsbeleid gebruiken om protocolherkenning te configureren

1. Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**  >  **netwerkcontrolesysteem.** 

3. Selecteer **protocolherkenning.** Dit beleid is standaard ingeschakeld. Als niet **geconfigureerd is ingesteld,** is definitie-uittreding ingeschakeld. 

4. Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.

5. Selecteer **Ingeschakeld en** selecteer **ok.**

6. Implementeer het bijgewerkte groepsbeleidsobject. Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Gebruikt u on-premises groepsbeleidsobjecten? Bekijk hoe ze vertalen in de cloud. [Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Verwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)