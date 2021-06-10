---
title: Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op Mac
description: Problemen met de installatie in Microsoft Defender voor Eindpunt op Mac oplossen.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, install
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
ms.openlocfilehash: 5166de3a7c7017979a93ac7026636ba24671892e
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935147"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt op macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a>Installatie mislukt

Voor handmatige installatie staat op de pagina Overzicht van de installatiewizard: 'Er is een fout opgetreden tijdens de installatie. Bij het installatieprogramma is een fout opgetreden waardoor de installatie is mislukt. Neem contact op met de softwarefabrikant voor hulp. Voor MDM-implementaties wordt deze ook weergegeven als een algemene installatiefout.

Hoewel er geen exacte fout wordt weergegeven aan de eindgebruiker, houden we een logboekbestand bij met de voortgang van de installatie in `/Library/Logs/Microsoft/mdatp/install.log` . Elke installatiesessie wordt toegevoegd aan dit logboekbestand. U kunt de `sed` laatste installatiesessie alleen uitvoeren:

```bash
sed -n 'H; /^preinstall com.microsoft.wdav begin/h; ${g;p;}' /Library/Logs/Microsoft/mdatp/install.log
```
```Output
preinstall com.microsoft.wdav begin [2020-03-11 13:08:49 -0700] 804
INSTALLER_SECURE_TEMP=/Library/InstallerSandboxes/.PKInstallSandboxManager/CB509765-70FC-4679-866D-8A14AD3F13CC.activeSandbox/89FA879B-971B-42BF-B4EA-7F5BB7CB5695
correlation id=CB509765-70FC-4679-866D-8A14AD3F13CC
[ERROR] Downgrade from 100.88.54 to 100.87.80 is not permitted
preinstall com.microsoft.wdav end [2020-03-11 13:08:49 -0700] 804 => 1
```

In dit voorbeeld wordt de werkelijke reden voorafgevoegd met `[ERROR]` .
De installatie is mislukt omdat een downgrade tussen deze versies niet wordt ondersteund.

## <a name="mdatp-install-log-missing-or-not-updated"></a>MDATP logboek installeren ontbreekt of niet wordt bijgewerkt

In zeldzame gevallen laat de installatie geen spoor achter in MDATP /Library/Logs/Microsoft/mdatp/install.log-bestand.
U kunt controleren of er een installatie is uitgevoerd en mogelijke fouten analyseren door macOS-logboeken te query's uit te voeren (dit is handig in de MDM-implementatie, wanneer er geen client-gebruikersinterface is). U wordt aangeraden een smal tijdvenster te gebruiken om een query uit te voeren en te filteren op de naam van het logboekregistratieproces, omdat er een grote hoeveelheid informatie beschikbaar is.

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
