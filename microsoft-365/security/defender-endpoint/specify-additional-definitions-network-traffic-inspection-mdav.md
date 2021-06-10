---
title: Geef extra definitiesets op voor netwerkverkeerscontrole voor Microsoft Defender Antivirus
description: Geef extra definitiesets op voor netwerkverkeerscontrole voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, netwerkverkeerscontrole
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300143"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Aanvullende definitiesets opgeven voor netwerkverkeersinspectie

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt extra definitiesets opgeven voor netwerkverkeerscontrole met groepsbeleid.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Groepsbeleid gebruiken om extra definitiesets op te geven voor netwerkverkeerscontrole

1. Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Ga naar **Windows Components**  >  **Microsoft Defender Antivirus**  >  **Network Inspection System**. 

3. Selecteer **Extra definitiesets opgeven voor netwerkverkeerscontrole.** Dit beleid is standaard ingesteld op **Niet geconfigureerd.** 

4. Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.

5. Selecteer **Ingeschakeld en** selecteer vervolgens in de sectie **Opties** de optie **Show...**.

6. Voeg items toe aan de lijst en selecteer **OK.** 

   Elke vermelding moet worden vermeld als een naam-waardepaar, waarbij de naam een tekenreeksweergave is van een GUID-definitieset. De definitieset GUID voor het inschakelen van testbeveiligingsinformatie wordt bijvoorbeeld gedefinieerd als: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . De waarde wordt niet gebruikt, dus wordt u aangeraden deze in te stellen op `0` . 

7. Selecteer **OK** en implementeer het bijgewerkte groepsbeleidsobject. Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Gebruikt u on-premises groepsbeleidsobjecten? Bekijk hoe ze vertalen in de cloud. [Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Aanverwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)