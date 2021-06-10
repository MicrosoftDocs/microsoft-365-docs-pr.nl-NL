---
title: Definitie-uittreding in Microsoft Defender Antivirus
description: Schakel definitieaftreding in voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, definition retirement
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
ms.openlocfilehash: 66b2e882a0f6de21e27dabb3a4bfe2fe113bcb32
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296470"
---
# <a name="turn-on-definition-retirement"></a>Definitie-uittreding in-/uit-

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt definitie-uittreding configureren met groepsbeleid. Er wordt gecontroleerd of een computer over de vereiste beveiligingsupdates beschikt om deze te beschermen tegen een bepaald beveiligingsprobleem. Als het systeem niet kwetsbaar is voor de exploit die door een definitie wordt gedetecteerd, is deze definitie 'buiten gebruik'. Als alle beveiligingsinformatie voor een bepaald protocol wordt ingetrokken, wordt dat protocol niet meer geparseerd. Als u deze functie inschakelen, kunt u de prestaties verbeteren. Op een computer die up-to-date is met de nieuwste beveiligingsupdates, heeft netwerkbeveiliging geen invloed op de netwerkprestaties.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Groepsbeleid gebruiken om definitie-uittreding te configureren

1. Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**  >  **netwerkcontrolesysteem.** 

3. Selecteer **Definitie-uittreding in- en uit-/uit- zetten.** Dit beleid is standaard ingeschakeld. Als niet **geconfigureerd is ingesteld,** is definitie-uittreding ingeschakeld. 

4. Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.

5. Selecteer **Ingeschakeld en** selecteer **ok.**

6. Implementeer het bijgewerkte groepsbeleidsobject. Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).

> [!TIP]
> Gebruikt u on-premises groepsbeleidsobjecten? Bekijk hoe ze vertalen in de cloud. [Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>Aanverwante artikelen

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Cloudbeveiliging inschakelen](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)