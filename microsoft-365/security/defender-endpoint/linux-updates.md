---
title: Updates implementeren voor Microsoft Defender voor Endpoint op Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u updates voor Microsoft Defender voor Eindpunt op Linux implementeert in bedrijfsomgevingen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, updates, deploy
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
ms.openlocfilehash: 9cb0c7375b538f502cf6165f13c68fd4b2fdcc64
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934751"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Updates implementeren voor Microsoft Defender voor Endpoint op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.

> [!WARNING]
> Elke versie van Defender voor Eindpunt op Linux heeft een vervaldatum, waarna het apparaat niet meer wordt beschermd. U moet het product vóór deze datum bijwerken. Voer de volgende opdracht uit om de vervaldatum te controleren:
> ```bash
> mdatp health --field product_expiration
> ```

Als u Defender voor Eindpunt op Linux handmatig wilt bijwerken, voert u een van de volgende opdrachten uit:

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL en varianten (CentOS en Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES en varianten

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu- en Debian-systemen

```bash
sudo apt-get install --only-upgrade mdatp
```
