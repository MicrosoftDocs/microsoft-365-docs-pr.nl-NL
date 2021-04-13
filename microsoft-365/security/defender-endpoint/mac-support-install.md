---
title: Installatieproblemen oplossen voor Microsoft Defender ATP voor Mac
description: Problemen met de installatie in Microsoft Defender ATP voor Mac oplossen.
keywords: microsoft, defender, atp, mac, install
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
ms.openlocfilehash: 754f389f37bce3be1c5a636f1911b5d0fb3fd29c
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689615"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="e5e9b-104">Installatieproblemen oplossen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="e5e9b-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e5e9b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e5e9b-105">**Applies to:**</span></span>

- [<span data-ttu-id="e5e9b-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="e5e9b-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="e5e9b-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e5e9b-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e5e9b-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e5e9b-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e5e9b-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e5e9b-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e5e9b-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="installation-failed"></a><span data-ttu-id="e5e9b-111">Installatie mislukt</span><span class="sxs-lookup"><span data-stu-id="e5e9b-111">Installation failed</span></span>

<span data-ttu-id="e5e9b-112">Voor handmatige installatie staat op de pagina Overzicht van de installatiewizard: 'Er is een fout opgetreden tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-112">For manual installation, the Summary page of the installation wizard says, "An error occurred during installation.</span></span> <span data-ttu-id="e5e9b-113">Bij het installatieprogramma is een fout opgetreden waardoor de installatie is mislukt.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-113">The Installer encountered an error that caused the installation to fail.</span></span> <span data-ttu-id="e5e9b-114">Neem contact op met de softwarefabrikant voor hulp.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-114">Contact the software manufacturer for assistance."</span></span> <span data-ttu-id="e5e9b-115">Voor MDM-implementaties wordt deze ook weergegeven als een algemene installatiefout.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-115">For MDM deployments, it displays as a generic installation failure as well.</span></span>

<span data-ttu-id="e5e9b-116">Hoewel er geen exacte fout wordt weergegeven aan de eindgebruiker, houden we een logboekbestand bij met de voortgang van de installatie in `/Library/Logs/Microsoft/mdatp/install.log` .</span><span class="sxs-lookup"><span data-stu-id="e5e9b-116">While we do not display an exact error to the end user, we keep a log file with installation progress in `/Library/Logs/Microsoft/mdatp/install.log`.</span></span> <span data-ttu-id="e5e9b-117">Elke installatiesessie wordt toegevoegd aan dit logboekbestand.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-117">Each installation session appends to this log file.</span></span> <span data-ttu-id="e5e9b-118">U kunt de `sed` laatste installatiesessie alleen uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e5e9b-118">You can use `sed` to output the last installation session only:</span></span>

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

<span data-ttu-id="e5e9b-119">In dit voorbeeld wordt de werkelijke reden voorafgevoegd met `[ERROR]` .</span><span class="sxs-lookup"><span data-stu-id="e5e9b-119">In this example, the actual reason is prefixed with `[ERROR]`.</span></span>
<span data-ttu-id="e5e9b-120">De installatie is mislukt omdat een downgrade tussen deze versies niet wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-120">The installation failed because a downgrade between these versions is not supported.</span></span>

## <a name="mdatp-install-log-missing-or-not-updated"></a><span data-ttu-id="e5e9b-121">MDATP-installatielogboek ontbreekt of wordt niet bijgewerkt</span><span class="sxs-lookup"><span data-stu-id="e5e9b-121">MDATP install log missing or not updated</span></span>

<span data-ttu-id="e5e9b-122">In zeldzame gevallen laat de installatie geen spoor achter in het bestand /Library/Logs/Microsoft/mdatp/install.log van MDATP.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-122">In rare cases, installation leaves no trace in MDATP's /Library/Logs/Microsoft/mdatp/install.log file.</span></span>
<span data-ttu-id="e5e9b-123">U kunt controleren of er een installatie is uitgevoerd en mogelijke fouten analyseren door macOS-logboeken te query's uit te voeren (dit is handig in de MDM-implementatie, wanneer er geen client-gebruikersinterface is).</span><span class="sxs-lookup"><span data-stu-id="e5e9b-123">You can verify that an installation happened and analyze possible errors by querying macOS logs (this is helpful in MDM deployment, when there is no client UI).</span></span> <span data-ttu-id="e5e9b-124">U wordt aangeraden een smal tijdvenster te gebruiken om een query uit te voeren en te filteren op de naam van het logboekregistratieproces, omdat er een grote hoeveelheid informatie beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="e5e9b-124">We recommend that you use a narrow time window to run a query, and that you filter by the logging process name, as there will be a huge amount of information.</span></span>

```bash
grep '^2020-03-11 13:08' /var/log/install.log
```
```Output
log show --start '2020-03-11 13:00:00' --end '2020-03-11 13:08:50' --info --debug --source --predicate 'processImagePath CONTAINS[C] "install"' --style syslog
```
