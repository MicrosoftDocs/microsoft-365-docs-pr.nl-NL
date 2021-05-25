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
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651126"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="007fd-104">Nieuwe functies in Microsoft Defender voor Endpoint op Linux</span><span class="sxs-lookup"><span data-stu-id="007fd-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="007fd-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="007fd-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="007fd-106">Vanaf deze versie worden bedreigingen die zijn gedetecteerd tijdens on-demand antivirusscans die worden geactiveerd via de opdrachtregelclient, automatisch verwijderd.</span><span class="sxs-lookup"><span data-stu-id="007fd-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="007fd-107">Bedreigingen die zijn gedetecteerd tijdens scans die via de gebruikersinterface worden geactiveerd, vereisen nog steeds handmatige actie.</span><span class="sxs-lookup"><span data-stu-id="007fd-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="007fd-108">`mdatp diagnostic real-time-protection-statistics` ondersteunt nu twee extra schakelopties:</span><span class="sxs-lookup"><span data-stu-id="007fd-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="007fd-109">`--sort`: sorteert de uitvoer aflopend op het totale aantal gescande bestanden</span><span class="sxs-lookup"><span data-stu-id="007fd-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="007fd-110">`--top N`: geeft de hoogste N-resultaten weer (werkt alleen als `--sort` deze ook is opgegeven)</span><span class="sxs-lookup"><span data-stu-id="007fd-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="007fd-111">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="007fd-112">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="007fd-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="007fd-113">Microsoft Defender voor Eindpunt op Linux is nu beschikbaar in preview voor klanten van de Amerikaanse overheid.</span><span class="sxs-lookup"><span data-stu-id="007fd-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="007fd-114">Zie Microsoft [Defender for Endpoint voor klanten](gov.md)van de Amerikaanse overheid voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="007fd-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="007fd-115">Er is een probleem opgelost waarbij het gebruik van Microsoft Defender voor Eindpunt op Linux op systemen met FUSE-bestandssystemen leidde tot vastloper van besturingssysteem</span><span class="sxs-lookup"><span data-stu-id="007fd-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="007fd-116">Prestatieverbeteringen & andere oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="007fd-117">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="007fd-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="007fd-118">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="007fd-119">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="007fd-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="007fd-120">Prestatieverbetering voor de situatie waarin een volledig bevestigingspunt wordt toegevoegd aan de lijst met antivirusuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="007fd-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="007fd-121">Vóór deze versie is de bestandsactiviteit die afkomstig is van het bevestigingspunt, nog steeds verwerkt door het product.</span><span class="sxs-lookup"><span data-stu-id="007fd-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="007fd-122">Vanaf deze versie wordt bestandsactiviteit voor uitgesloten bevestigingspunten onderdrukt, wat leidt tot betere productprestaties</span><span class="sxs-lookup"><span data-stu-id="007fd-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="007fd-123">Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="007fd-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="007fd-124">Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="007fd-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="007fd-125">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="007fd-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="007fd-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="007fd-126">101.18.53</span></span>

- <span data-ttu-id="007fd-127">EDR voor Linux is nu [algemeen beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="007fd-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="007fd-128">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="007fd-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="007fd-129">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="007fd-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="007fd-130">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="007fd-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="007fd-131">101.12.99</span></span>

- <span data-ttu-id="007fd-132">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="007fd-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="007fd-133">101.04.76</span></span>

- <span data-ttu-id="007fd-134">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="007fd-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="007fd-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="007fd-135">101.03.48</span></span>

- <span data-ttu-id="007fd-136">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="007fd-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="007fd-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="007fd-137">101.02.55</span></span>

- <span data-ttu-id="007fd-138">Er is een probleem opgelost waarbij het product soms niet begint na een herstart/upgrade</span><span class="sxs-lookup"><span data-stu-id="007fd-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="007fd-139">Er is een probleem opgelost waarbij proxy-instellingen niet worden gebruikt voor productupgrades</span><span class="sxs-lookup"><span data-stu-id="007fd-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="007fd-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="007fd-140">101.00.75</span></span>

- <span data-ttu-id="007fd-141">Ondersteuning toegevoegd voor de volgende bestandssysteemtypen: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` en `vfat`</span><span class="sxs-lookup"><span data-stu-id="007fd-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="007fd-142">Nieuwe syntaxis voor het [opdrachtregelhulpmiddel](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="007fd-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="007fd-143">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="007fd-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="007fd-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="007fd-145">Bij het upgraden van het geïnstalleerde pakket van een productversie eerder dan 100.90.70, kan de update mislukken in de distributies Red Hat en SLES.</span><span class="sxs-lookup"><span data-stu-id="007fd-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="007fd-146">Dit komt door een belangrijke wijziging in een bestandspad.</span><span class="sxs-lookup"><span data-stu-id="007fd-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="007fd-147">Een tijdelijke oplossing is om het oudere pakket te verwijderen en vervolgens het nieuwere pakket te installeren.</span><span class="sxs-lookup"><span data-stu-id="007fd-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="007fd-148">Dit probleem bestaat niet in nieuwere versies.</span><span class="sxs-lookup"><span data-stu-id="007fd-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="007fd-149">[Antivirusuitsluitingen ondersteunen nu jokertekens](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="007fd-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="007fd-150">De mogelijkheid toegevoegd om [prestatieproblemen op te lossen](linux-support-perf.md) via het `mdatp` opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="007fd-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="007fd-151">Verbeteringen om de installatie van het pakket krachtiger te maken</span><span class="sxs-lookup"><span data-stu-id="007fd-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="007fd-152">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="007fd-152">Performance improvements & bug fixes</span></span>
