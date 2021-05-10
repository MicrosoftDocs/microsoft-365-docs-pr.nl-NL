---
title: Protocolherkenning in Microsoft Defender Antivirus
description: Schakel protocolherkenning in voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, protocolherkenning
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296469"
---
# <a name="turn-on-protocol-recognition"></a><span data-ttu-id="809db-104">Protocolherkenning in- en uit-</span><span class="sxs-lookup"><span data-stu-id="809db-104">Turn on protocol recognition</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="809db-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="809db-105">**Applies to:**</span></span>

- [<span data-ttu-id="809db-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="809db-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="809db-107">Met deze beleidsinstelling kunt u protocolherkenning configureren voor netwerkbeveiliging tegen misbruik van bekende beveiligingslekken.</span><span class="sxs-lookup"><span data-stu-id="809db-107">This policy setting allows you to configure protocol recognition for network protection against exploits of known vulnerabilities.</span></span> <span data-ttu-id="809db-108">Als u deze instelling in- of configureert, is protocolherkenning ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="809db-108">If you enable or do not configure this setting, protocol recognition will be enabled.</span></span> <span data-ttu-id="809db-109">Als u deze instelling uit schakelt, wordt protocolherkenning uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="809db-109">If you disable this setting, protocol recognition will be disabled.</span></span>

## <a name="use-group-policy-to-configure-protocol-recognition"></a><span data-ttu-id="809db-110">Groepsbeleid gebruiken om protocolherkenning te configureren</span><span class="sxs-lookup"><span data-stu-id="809db-110">Use Group Policy to configure protocol recognition</span></span>

1. <span data-ttu-id="809db-111">Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="809db-111">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="809db-112">Ga naar **Beheersjablonen voor computerconfiguratie**  >    >  **Windows onderdelen**  >  **Microsoft Defender Antivirus**  >  **netwerkcontrolesysteem.**</span><span class="sxs-lookup"><span data-stu-id="809db-112">Go to **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="809db-113">Selecteer **protocolherkenning.**</span><span class="sxs-lookup"><span data-stu-id="809db-113">Select **protocol recognition**.</span></span> <span data-ttu-id="809db-114">Dit beleid is standaard ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="809db-114">By default, this policy is enabled.</span></span> <span data-ttu-id="809db-115">Als niet **geconfigureerd is ingesteld,** is definitie-uittreding ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="809db-115">If set **Not configured**, definition retirement is enabled.</span></span> 

4. <span data-ttu-id="809db-116">Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.</span><span class="sxs-lookup"><span data-stu-id="809db-116">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="809db-117">Selecteer **Ingeschakeld en** selecteer **ok.**</span><span class="sxs-lookup"><span data-stu-id="809db-117">Select **Enabled**, and then select **OK**.</span></span>

6. <span data-ttu-id="809db-118">Implementeer het bijgewerkte groepsbeleidsobject.</span><span class="sxs-lookup"><span data-stu-id="809db-118">Deploy your updated Group Policy Object.</span></span> <span data-ttu-id="809db-119">Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="809db-119">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="809db-120">Gebruikt u on-premises groepsbeleidsobjecten?</span><span class="sxs-lookup"><span data-stu-id="809db-120">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="809db-121">Bekijk hoe ze vertalen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="809db-121">See how they translate in the cloud.</span></span> <span data-ttu-id="809db-122">[Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="809db-122">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="809db-123">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="809db-123">Related articles</span></span>

- [<span data-ttu-id="809db-124">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="809db-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="809db-125">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="809db-125">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="809db-126">Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice</span><span class="sxs-lookup"><span data-stu-id="809db-126">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)