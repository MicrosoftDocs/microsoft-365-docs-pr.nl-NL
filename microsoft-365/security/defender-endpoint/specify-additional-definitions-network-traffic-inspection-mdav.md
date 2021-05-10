---
title: Geef extra definitiesets op voor netwerkverkeerscontrole voor Microsoft Defender Antivirus
description: Geef extra definitiesets op voor netwerkverkeerscontrole voor Microsoft Defender Antivirus.
keywords: Microsoft Defender Antivirus, antimalware, beveiliging, defender, netwerkverkeerscontrole
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300143"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="55b6d-104">Aanvullende definitiesets opgeven voor netwerkverkeersinspectie</span><span class="sxs-lookup"><span data-stu-id="55b6d-104">Specify additional definition sets for network traffic inspection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55b6d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="55b6d-105">**Applies to:**</span></span>

- [<span data-ttu-id="55b6d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="55b6d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="55b6d-107">U kunt extra definitiesets opgeven voor netwerkverkeerscontrole met groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="55b6d-107">You can specify additional definition sets for network traffic inspection using Group Policy.</span></span>

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a><span data-ttu-id="55b6d-108">Groepsbeleid gebruiken om extra definitiesets op te geven voor netwerkverkeerscontrole</span><span class="sxs-lookup"><span data-stu-id="55b6d-108">Use Group Policy to specify additional definition sets for network traffic inspection</span></span>

1. <span data-ttu-id="55b6d-109">Open in het eindpunt Groepsbeleidsbeheer de [console Groepsbeleidsbeheer.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))</span><span class="sxs-lookup"><span data-stu-id="55b6d-109">On your Group Policy management endpoint, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)).</span></span>

2. <span data-ttu-id="55b6d-110">Ga naar **Windows Components**  >  **Microsoft Defender Antivirus**  >  **Network Inspection System**.</span><span class="sxs-lookup"><span data-stu-id="55b6d-110">Go to **Windows Components** > **Microsoft Defender Antivirus** > **Network Inspection System**.</span></span> 

3. <span data-ttu-id="55b6d-111">Selecteer **Extra definitiesets opgeven voor netwerkverkeerscontrole.**</span><span class="sxs-lookup"><span data-stu-id="55b6d-111">Select **Specify additional definition sets for network traffic inspection**.</span></span> <span data-ttu-id="55b6d-112">Dit beleid is standaard ingesteld op **Niet geconfigureerd.**</span><span class="sxs-lookup"><span data-stu-id="55b6d-112">By default, this policy is set to **Not configured**.</span></span> 

4. <span data-ttu-id="55b6d-113">Als u het beleid wilt bewerken, selecteert u de **koppeling Beleidsinstelling** bewerken.</span><span class="sxs-lookup"><span data-stu-id="55b6d-113">To edit the policy, select the **edit policy setting** link.</span></span>

5. <span data-ttu-id="55b6d-114">Selecteer **Ingeschakeld en** selecteer vervolgens in de sectie **Opties** de optie **Show...**.</span><span class="sxs-lookup"><span data-stu-id="55b6d-114">Select **Enabled**, and then in the **Options** section, select **Show...**.</span></span>

6. <span data-ttu-id="55b6d-115">Voeg items toe aan de lijst en selecteer **OK.**</span><span class="sxs-lookup"><span data-stu-id="55b6d-115">Add entries to the list, and then select **OK**.</span></span> 

   <span data-ttu-id="55b6d-116">Elke vermelding moet worden vermeld als een naam-waardepaar, waarbij de naam een tekenreeksweergave is van een GUID-definitieset.</span><span class="sxs-lookup"><span data-stu-id="55b6d-116">Each entry must be listed as a name-value pair, where the name is a string representation of a definition set GUID.</span></span> <span data-ttu-id="55b6d-117">De definitieset GUID voor het inschakelen van testbeveiligingsinformatie wordt bijvoorbeeld gedefinieerd als: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` .</span><span class="sxs-lookup"><span data-stu-id="55b6d-117">As an example, the definition set GUID to enable test security intelligence is defined as: `{b54b6ac9-a737-498e-9120-6616ad3bf590}`.</span></span> <span data-ttu-id="55b6d-118">De waarde wordt niet gebruikt, dus wordt u aangeraden deze in te stellen op `0` .</span><span class="sxs-lookup"><span data-stu-id="55b6d-118">The value is not used, so we recommend setting it to `0`.</span></span> 

7. <span data-ttu-id="55b6d-119">Selecteer **OK** en implementeer het bijgewerkte groepsbeleidsobject.</span><span class="sxs-lookup"><span data-stu-id="55b6d-119">Select **OK**, and then deploy your updated Group Policy Object.</span></span> <span data-ttu-id="55b6d-120">Zie [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span><span class="sxs-lookup"><span data-stu-id="55b6d-120">See [Group Policy Management Console](/windows/win32/srvnodes/group-policy).</span></span>

> [!TIP]
> <span data-ttu-id="55b6d-121">Gebruikt u on-premises groepsbeleidsobjecten?</span><span class="sxs-lookup"><span data-stu-id="55b6d-121">Are you using Group Policy Objects on premises?</span></span> <span data-ttu-id="55b6d-122">Bekijk hoe ze vertalen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="55b6d-122">See how they translate in the cloud.</span></span> <span data-ttu-id="55b6d-123">[Analyseer uw on-premises groepsbeleidsobjecten met groepsbeleidsanalyse in Microsoft Endpoint Manager - Preview.](/mem/intune/configuration/group-policy-analytics)</span><span class="sxs-lookup"><span data-stu-id="55b6d-123">[Analyze your on-premises group policy objects using Group Policy analytics in Microsoft Endpoint Manager - Preview](/mem/intune/configuration/group-policy-analytics).</span></span> 
  
## <a name="related-articles"></a><span data-ttu-id="55b6d-124">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="55b6d-124">Related articles</span></span>

- [<span data-ttu-id="55b6d-125">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="55b6d-125">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
 
- [<span data-ttu-id="55b6d-126">Cloudbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="55b6d-126">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)

- [<span data-ttu-id="55b6d-127">Antimalware-beleid maken en implementeren: Cloudbeveiligingsservice</span><span class="sxs-lookup"><span data-stu-id="55b6d-127">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)