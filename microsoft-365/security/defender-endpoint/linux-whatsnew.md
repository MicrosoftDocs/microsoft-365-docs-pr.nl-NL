---
title: Nieuwe functies in Microsoft Defender voor Endpoint op Linux
description: Lijst met belangrijke wijzigingen voor Microsoft Defender voor Eindpunt op Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
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
ms.openlocfilehash: 6aaf370ef0222c6c4a7f920a2a5ed8951f988839
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933563"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="ef01e-104">Nieuwe functies in Microsoft Defender voor Endpoint op Linux</span><span class="sxs-lookup"><span data-stu-id="ef01e-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="ef01e-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ef01e-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ef01e-106">Microsoft Defender voor Eindpunt op Linux is nu beschikbaar in preview voor klanten van de Amerikaanse overheid.</span><span class="sxs-lookup"><span data-stu-id="ef01e-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="ef01e-107">Zie Microsoft [Defender for Endpoint voor klanten](gov.md)van de Amerikaanse overheid voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ef01e-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="ef01e-108">Er is een probleem opgelost waarbij het gebruik van Microsoft Defender voor Eindpunt op Linux op systemen met FUSE-bestandssystemen leidde tot vastloper van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="ef01e-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="ef01e-109">Prestatieverbeteringen & andere oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="ef01e-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="ef01e-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="ef01e-111">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="ef01e-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="ef01e-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="ef01e-113">Prestatieverbetering voor de situatie waarin een volledig bevestigingspunt wordt toegevoegd aan de lijst met antivirusuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="ef01e-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="ef01e-114">Vóór deze versie is de bestandsactiviteit die afkomstig is van het bevestigingspunt, nog steeds verwerkt door het product.</span><span class="sxs-lookup"><span data-stu-id="ef01e-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="ef01e-115">Vanaf deze versie wordt bestandsactiviteit voor uitgesloten bevestigingspunten onderdrukt, wat leidt tot betere productprestaties</span><span class="sxs-lookup"><span data-stu-id="ef01e-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="ef01e-116">Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ef01e-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="ef01e-117">Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="ef01e-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="ef01e-118">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="ef01e-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="ef01e-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="ef01e-119">101.18.53</span></span>

- <span data-ttu-id="ef01e-120">EDR voor Linux is nu [algemeen beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="ef01e-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="ef01e-121">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="ef01e-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="ef01e-122">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="ef01e-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="ef01e-123">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="ef01e-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="ef01e-124">101.12.99</span></span>

- <span data-ttu-id="ef01e-125">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="ef01e-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="ef01e-126">101.04.76</span></span>

- <span data-ttu-id="ef01e-127">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="ef01e-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="ef01e-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="ef01e-128">101.03.48</span></span>

- <span data-ttu-id="ef01e-129">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="ef01e-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="ef01e-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="ef01e-130">101.02.55</span></span>

- <span data-ttu-id="ef01e-131">Er is een probleem opgelost waarbij het product soms niet begint na een herstart/upgrade</span><span class="sxs-lookup"><span data-stu-id="ef01e-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="ef01e-132">Er is een probleem opgelost waarbij proxy-instellingen niet worden gebruikt voor productupgrades</span><span class="sxs-lookup"><span data-stu-id="ef01e-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="ef01e-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="ef01e-133">101.00.75</span></span>

- <span data-ttu-id="ef01e-134">Ondersteuning toegevoegd voor de volgende bestandssysteemtypen: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` en `vfat`</span><span class="sxs-lookup"><span data-stu-id="ef01e-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="ef01e-135">Nieuwe syntaxis voor het [opdrachtregelhulpmiddel](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ef01e-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="ef01e-136">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="ef01e-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="ef01e-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="ef01e-138">Bij het upgraden van het geïnstalleerde pakket van een productversie eerder dan 100.90.70, kan de update mislukken in de distributies Red Hat en SLES.</span><span class="sxs-lookup"><span data-stu-id="ef01e-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="ef01e-139">Dit komt door een belangrijke wijziging in een bestandspad.</span><span class="sxs-lookup"><span data-stu-id="ef01e-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="ef01e-140">Een tijdelijke oplossing is om het oudere pakket te verwijderen en vervolgens het nieuwere pakket te installeren.</span><span class="sxs-lookup"><span data-stu-id="ef01e-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="ef01e-141">Dit probleem bestaat niet in nieuwere versies.</span><span class="sxs-lookup"><span data-stu-id="ef01e-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="ef01e-142">[Antivirusuitsluitingen ondersteunen nu jokertekens](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="ef01e-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="ef01e-143">De mogelijkheid toegevoegd om [prestatieproblemen op te lossen](linux-support-perf.md) via het `mdatp` opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="ef01e-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="ef01e-144">Verbeteringen om de installatie van het pakket krachtiger te maken</span><span class="sxs-lookup"><span data-stu-id="ef01e-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="ef01e-145">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ef01e-145">Performance improvements & bug fixes</span></span>
