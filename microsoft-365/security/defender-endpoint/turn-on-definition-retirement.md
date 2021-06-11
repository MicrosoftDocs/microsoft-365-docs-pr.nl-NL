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
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903802"
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
  
