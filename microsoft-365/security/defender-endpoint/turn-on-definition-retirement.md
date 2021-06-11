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
# <a name="turn-on-definition-retirement"></a><span data-ttu-id="e6267-104">Definitie-uittreding in-/uit-</span><span class="sxs-lookup"><span data-stu-id="e6267-104">Turn on definition retirement</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e6267-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e6267-105">**Applies to:**</span></span>

- [<span data-ttu-id="e6267-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e6267-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e6267-107">U kunt definitie-uittreding configureren met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="e6267-107">You can configure definition retirement using Group Policy.</span></span> <span data-ttu-id="e6267-108">Er wordt gecontroleerd of een computer over de vereiste beveiligingsupdates beschikt om deze te beschermen tegen een bepaald beveiligingsprobleem.</span><span class="sxs-lookup"><span data-stu-id="e6267-108">Definition retirement checks to see if a computer has the required security updates necessary to protect it against a particular vulnerability.</span></span> <span data-ttu-id="e6267-109">Als het systeem niet kwetsbaar is voor de exploit die door een definitie wordt gedetecteerd, is deze definitie 'buiten gebruik'.</span><span class="sxs-lookup"><span data-stu-id="e6267-109">If the system is not vulnerable to the exploit detected by a definition, then that definition is "retired".</span></span> <span data-ttu-id="e6267-110">Als alle beveiligingsinformatie voor een bepaald protocol wordt ingetrokken, wordt dat protocol niet meer geparseerd.</span><span class="sxs-lookup"><span data-stu-id="e6267-110">If all security intelligence for a given protocol are retired then that protocol is no longer parsed.</span></span> <span data-ttu-id="e6267-111">Als u deze functie inschakelen, kunt u de prestaties verbeteren.</span><span class="sxs-lookup"><span data-stu-id="e6267-111">Enabling this feature helps to improve performance.</span></span> <span data-ttu-id="e6267-112">Op een computer die up-to-date is met de nieuwste beveiligingsupdates, heeft netwerkbeveiliging geen invloed op de netwerkprestaties.</span><span class="sxs-lookup"><span data-stu-id="e6267-112">On a computer that is up-to-date with all the latest security updates, network protection will have no impact on network performance.</span></span>

## <a name="use-group-policy-to-configure-definition-retirement"></a><span data-ttu-id="e6267-113">Groepsbeleid gebruiken om definitie-uittreding te configureren</span><span class="sxs-lookup"><span data-stu-id="e6267-113">Use Group Policy to configure definition retirement</span></span>

1. <span data-ttu-id="e6267-114">Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="e6267-114">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="e6267-115">Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**  >  **netwerkcontrolesysteem.**</span><span class="sxs-lookup"><span data-stu-id="e6267-115">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="e6267-116">Selecteer **Definitie-uittreding in- en uit-/uit- zetten.**</span><span class="sxs-lookup"><span data-stu-id="e6267-116">Select **Turn on definition retirement**.</span></span> <span data-ttu-id="e6267-117">Dit beleid is standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6267-117">By default, this policy is enabled.</span></span> <span data-ttu-id="e6267-118">Als niet **geconfigureerd is ingesteld,** is definitie-uittreding ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e6267-118">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="e6267-119">Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.</span><span class="sxs-lookup"><span data-stu-id="e6267-119">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="e6267-120">Selecteer **Ingeschakeld en** selecteer **ok.**</span><span class="sxs-lookup"><span data-stu-id="e6267-120">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="e6267-121">Implementeer het bijgewerkte groepsbeleidsobject.</span><span class="sxs-lookup"><span data-stu-id="e6267-121">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="e6267-122">Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="e6267-122">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="e6267-123">Gebruikt u on-premises groepsbeleidsobjecten?</span><span class="sxs-lookup"><span data-stu-id="e6267-123">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="e6267-124">Bekijk hoe ze vertalen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="e6267-124">See how they translate in the cloud.</span></span> <span data-ttu-id="e6267-125">[Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="e6267-125">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
