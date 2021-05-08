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
ms.openlocfilehash: fc5a64f4be1b782c423c2ae9e2222a1424be97e0
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274722"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="aa42f-104">Updates implementeren voor Microsoft Defender voor Endpoint op Linux</span><span class="sxs-lookup"><span data-stu-id="aa42f-104">Deploy updates for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="aa42f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="aa42f-105">**Applies to:**</span></span>
- [<span data-ttu-id="aa42f-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="aa42f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="aa42f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa42f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="aa42f-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="aa42f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="aa42f-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="aa42f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="aa42f-110">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="aa42f-110">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span>

> [!WARNING]
> <span data-ttu-id="aa42f-111">Elke versie van Defender voor Eindpunt op Linux heeft een vervaldatum, waarna het apparaat niet meer wordt beschermd.</span><span class="sxs-lookup"><span data-stu-id="aa42f-111">Each version of Defender for Endpoint on Linux has an expiration date, after which it will no longer continue to protect your device.</span></span> <span data-ttu-id="aa42f-112">U moet het product vóór deze datum bijwerken.</span><span class="sxs-lookup"><span data-stu-id="aa42f-112">You must update the product prior to this date.</span></span> <span data-ttu-id="aa42f-113">Voer de volgende opdracht uit om de vervaldatum te controleren:</span><span class="sxs-lookup"><span data-stu-id="aa42f-113">To check the expiration date, run the following command:</span></span>
> ```bash
> mdatp health --field product_expiration
> ```


<span data-ttu-id="aa42f-114">Over het algemeen beschikbare Microsoft Defender voor endpoint-mogelijkheden zijn equivalent, ongeacht het updatekanaal dat wordt gebruikt voor een implementatie (Beta (Insider), Preview (Extern), Current (Productie)).</span><span class="sxs-lookup"><span data-stu-id="aa42f-114">Generally available Microsoft Defender for Endpoint capabilities are equivalent regardless update channel used for a deployment (Beta (Insider), Preview (External), Current (Production)).</span></span>


<span data-ttu-id="aa42f-115">Als u Defender voor Eindpunt op Linux handmatig wilt bijwerken, voert u een van de volgende opdrachten uit:</span><span class="sxs-lookup"><span data-stu-id="aa42f-115">To update Defender for Endpoint on Linux manually, execute one of the following commands:</span></span>

## <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="aa42f-116">RHEL en varianten (CentOS en Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="aa42f-116">RHEL and variants (CentOS and Oracle Linux)</span></span>

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a><span data-ttu-id="aa42f-117">SLES en varianten</span><span class="sxs-lookup"><span data-stu-id="aa42f-117">SLES and variants</span></span>

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="aa42f-118">Ubuntu- en Debian-systemen</span><span class="sxs-lookup"><span data-stu-id="aa42f-118">Ubuntu and Debian systems</span></span>

```bash
sudo apt-get install --only-upgrade mdatp
```
