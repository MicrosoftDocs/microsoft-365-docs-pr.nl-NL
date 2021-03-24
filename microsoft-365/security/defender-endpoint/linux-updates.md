---
title: Updates implementeren voor Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Hier wordt beschreven hoe u updates voor Microsoft Defender ATP voor Linux implementeert in bedrijfsomgevingen.
keywords: microsoft, defender, atp, linux, updates, deploy
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
ms.openlocfilehash: adc19192764e8c57a20f14cc908be23e8d9bdbc8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057489"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="f2797-104">Updates voor Microsoft Defender voor Eindpunt voor Linux implementeren</span><span class="sxs-lookup"><span data-stu-id="f2797-104">Deploy updates for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f2797-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f2797-105">**Applies to:**</span></span>
- [<span data-ttu-id="f2797-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f2797-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="f2797-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2797-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f2797-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f2797-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f2797-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f2797-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="f2797-110">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="f2797-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="f2797-111">Elke versie van Defender voor Eindpunt voor Linux heeft een vervaldatum, waarna het apparaat niet meer wordt beschermd.</span><span class="sxs-lookup"><span data-stu-id="f2797-111">Each version of Defender for Endpoint for Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="f2797-112">U moet het product vóór deze datum bijwerken.</span><span class="sxs-lookup"><span data-stu-id="f2797-112">You must update the product prior to this date.</span></span> <span data-ttu-id="f2797-113">Voer de volgende opdracht uit om de vervaldatum te controleren:</span><span class="sxs-lookup"><span data-stu-id="f2797-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```

<span data-ttu-id="f2797-114">Als u Defender voor Eindpunt voor Linux handmatig wilt bijwerken, voert u een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="f2797-114">To update Defender for Endpoint for Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="f2797-115">RHEL en varianten (CentOS en Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="f2797-115">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="f2797-116">SLES en varianten</span><span class="sxs-lookup"><span data-stu-id="f2797-116">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="f2797-117">Ubuntu- en Debian-systemen</span><span class="sxs-lookup"><span data-stu-id="f2797-117">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
