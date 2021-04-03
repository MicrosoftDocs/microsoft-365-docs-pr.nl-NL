---
title: Nieuwe functies in Microsoft Defender voor Endpoint voor Linux
description: Lijst met belangrijke wijzigingen voor Microsoft Defender ATP voor Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581000"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="47410-104">Nieuwe functies in Microsoft Defender voor Endpoint voor Linux</span><span class="sxs-lookup"><span data-stu-id="47410-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="47410-105">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="47410-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="47410-106">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="47410-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="47410-107">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="47410-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="47410-108">Prestatieverbetering voor de situatie waarin een volledig bevestigingspunt wordt toegevoegd aan de lijst met antivirusuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="47410-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="47410-109">Vóór deze versie is de bestandsactiviteit die afkomstig is van het bevestigingspunt, nog steeds verwerkt door het product.</span><span class="sxs-lookup"><span data-stu-id="47410-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="47410-110">Vanaf deze versie wordt bestandsactiviteit voor uitgesloten bevestigingspunten onderdrukt, wat leidt tot betere productprestaties</span><span class="sxs-lookup"><span data-stu-id="47410-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="47410-111">Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="47410-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="47410-112">Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="47410-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="47410-113">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="47410-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="47410-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="47410-114">101.18.53</span></span>

- <span data-ttu-id="47410-115">EDR voor Linux is nu [algemeen beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="47410-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="47410-116">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="47410-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="47410-117">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="47410-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="47410-118">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="47410-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="47410-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="47410-119">101.12.99</span></span>

- <span data-ttu-id="47410-120">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="47410-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="47410-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="47410-121">101.04.76</span></span>

- <span data-ttu-id="47410-122">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="47410-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="47410-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="47410-123">101.03.48</span></span>

- <span data-ttu-id="47410-124">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="47410-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="47410-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="47410-125">101.02.55</span></span>

- <span data-ttu-id="47410-126">Er is een probleem opgelost waarbij het product soms niet begint na een herstart/upgrade</span><span class="sxs-lookup"><span data-stu-id="47410-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="47410-127">Er is een probleem opgelost waarbij proxy-instellingen niet worden gebruikt voor productupgrades</span><span class="sxs-lookup"><span data-stu-id="47410-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="47410-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="47410-128">101.00.75</span></span>

- <span data-ttu-id="47410-129">Ondersteuning toegevoegd voor de volgende bestandssysteemtypen: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` en `vfat`</span><span class="sxs-lookup"><span data-stu-id="47410-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="47410-130">Nieuwe syntaxis voor het [opdrachtregelhulpmiddel](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="47410-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="47410-131">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="47410-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="47410-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="47410-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="47410-133">Bij het upgraden van het geïnstalleerde pakket van een productversie eerder dan 100.90.70, kan de update mislukken in de distributies Red Hat en SLES.</span><span class="sxs-lookup"><span data-stu-id="47410-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="47410-134">Dit komt door een belangrijke wijziging in een bestandspad.</span><span class="sxs-lookup"><span data-stu-id="47410-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="47410-135">Een tijdelijke oplossing is om het oudere pakket te verwijderen en vervolgens het nieuwere pakket te installeren.</span><span class="sxs-lookup"><span data-stu-id="47410-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="47410-136">Dit probleem bestaat niet in nieuwere versies.</span><span class="sxs-lookup"><span data-stu-id="47410-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="47410-137">[Antivirusuitsluitingen ondersteunen nu jokertekens](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="47410-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="47410-138">De mogelijkheid toegevoegd om [prestatieproblemen op te lossen](linux-support-perf.md) via het `mdatp` opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="47410-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="47410-139">Verbeteringen om de installatie van het pakket krachtiger te maken</span><span class="sxs-lookup"><span data-stu-id="47410-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="47410-140">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="47410-140">Performance improvements & bug fixes</span></span>
