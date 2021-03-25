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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198775"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="ca270-104">Nieuwe functies in Microsoft Defender voor Endpoint voor Linux</span><span class="sxs-lookup"><span data-stu-id="ca270-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="ca270-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="ca270-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="ca270-106">Prestatieverbetering voor de situatie waarin een volledig bevestigingspunt wordt toegevoegd aan de lijst met antivirusuitsluitingen.</span><span class="sxs-lookup"><span data-stu-id="ca270-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="ca270-107">Vóór deze versie is de bestandsactiviteit die afkomstig is van het bevestigingspunt, nog steeds verwerkt door het product.</span><span class="sxs-lookup"><span data-stu-id="ca270-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="ca270-108">Vanaf deze versie wordt bestandsactiviteit voor uitgesloten bevestigingspunten onderdrukt, wat leidt tot betere productprestaties</span><span class="sxs-lookup"><span data-stu-id="ca270-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="ca270-109">Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ca270-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="ca270-110">Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="ca270-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="ca270-111">Andere prestatieverbeteringen & bug fixes</span><span class="sxs-lookup"><span data-stu-id="ca270-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="ca270-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="ca270-112">101.18.53</span></span>

- <span data-ttu-id="ca270-113">EDR voor Linux is nu [algemeen beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="ca270-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="ca270-114">Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="ca270-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="ca270-115">Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst</span><span class="sxs-lookup"><span data-stu-id="ca270-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="ca270-116">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ca270-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="ca270-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="ca270-117">101.12.99</span></span>

- <span data-ttu-id="ca270-118">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ca270-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="ca270-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="ca270-119">101.04.76</span></span>

- <span data-ttu-id="ca270-120">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="ca270-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="ca270-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="ca270-121">101.03.48</span></span>

- <span data-ttu-id="ca270-122">Bug fixes</span><span class="sxs-lookup"><span data-stu-id="ca270-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="ca270-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="ca270-123">101.02.55</span></span>

- <span data-ttu-id="ca270-124">Er is een probleem opgelost waarbij het product soms niet begint na een herstart/upgrade</span><span class="sxs-lookup"><span data-stu-id="ca270-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="ca270-125">Er is een probleem opgelost waarbij proxy-instellingen niet worden gebruikt voor productupgrades</span><span class="sxs-lookup"><span data-stu-id="ca270-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="ca270-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="ca270-126">101.00.75</span></span>

- <span data-ttu-id="ca270-127">Ondersteuning toegevoegd voor de volgende bestandssysteemtypen: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` en `vfat`</span><span class="sxs-lookup"><span data-stu-id="ca270-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="ca270-128">Nieuwe syntaxis voor het [opdrachtregelhulpmiddel](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="ca270-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="ca270-129">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ca270-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="ca270-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="ca270-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="ca270-131">Bij het upgraden van het geïnstalleerde pakket van een productversie eerder dan 100.90.70, kan de update mislukken in de distributies Red Hat en SLES.</span><span class="sxs-lookup"><span data-stu-id="ca270-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="ca270-132">Dit komt door een belangrijke wijziging in een bestandspad.</span><span class="sxs-lookup"><span data-stu-id="ca270-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="ca270-133">Een tijdelijke oplossing is om het oudere pakket te verwijderen en vervolgens het nieuwere pakket te installeren.</span><span class="sxs-lookup"><span data-stu-id="ca270-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="ca270-134">Dit probleem bestaat niet in nieuwere versies.</span><span class="sxs-lookup"><span data-stu-id="ca270-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="ca270-135">[Antivirusuitsluitingen ondersteunen nu jokertekens](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="ca270-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="ca270-136">De mogelijkheid toegevoegd om [prestatieproblemen op te lossen](linux-support-perf.md) via het `mdatp` opdrachtregelhulpmiddel</span><span class="sxs-lookup"><span data-stu-id="ca270-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="ca270-137">Verbeteringen om de installatie van het pakket krachtiger te maken</span><span class="sxs-lookup"><span data-stu-id="ca270-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="ca270-138">Prestatieverbeteringen & oplossingen voor fouten</span><span class="sxs-lookup"><span data-stu-id="ca270-138">Performance improvements & bug fixes</span></span>
