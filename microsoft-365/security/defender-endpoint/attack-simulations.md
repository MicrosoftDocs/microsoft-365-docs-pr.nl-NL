---
title: Microsoft Defender ATP ervaren via gesimuleerde aanvallen
description: Voer de meegeleverde scenariosimulaties uit om te ervaren hoe Microsoft Defender ATP inbreuken kan detecteren, onderzoeken en beantwoorden.
keywords: wdatp, test, scenario, aanval, simulatie, gesimuleerd, doe-het-zelf, Microsoft Defender voor eindpunt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498306"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="fef4a-104">Microsoft Defender voor eindpunt ervaren via gesimuleerde aanvallen</span><span class="sxs-lookup"><span data-stu-id="fef4a-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fef4a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="fef4a-105">**Applies to:**</span></span>
- [<span data-ttu-id="fef4a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="fef4a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="fef4a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fef4a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="fef4a-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fef4a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fef4a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fef4a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="fef4a-110">Meer informatie over de nieuwste verbeteringen in Microsoft Defender ATP: [Wat is er nieuw in Defender voor Eindpunt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="fef4a-110">Learn about the latest enhancements in Microsoft Defender ATP: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="fef4a-111">Defender for Endpoint heeft in de recente MITRE-evaluatie de toonaangevende mogelijkheden voor optica en detectie gedemonstreerd.</span><span class="sxs-lookup"><span data-stu-id="fef4a-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="fef4a-112">Lees: [Inzichten uit de MITRE-ATT-&op CK gebaseerde evaluatie](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="fef4a-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="fef4a-113">Mogelijk wilt u Defender voor Eindpunt ervaren voordat u meer dan een paar apparaten aan boord van de service aan boord gaat.</span><span class="sxs-lookup"><span data-stu-id="fef4a-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="fef4a-114">Hiervoor kunt u gecontroleerde aanvalssimulaties uitvoeren op een paar testapparaten.</span><span class="sxs-lookup"><span data-stu-id="fef4a-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="fef4a-115">Nadat u de gesimuleerde aanvallen hebt uitgevoerd, kunt u bekijken hoe in Defender voor Eindpunt schadelijke activiteiten worden aan het licht gekomen en kunt u bekijken hoe dit een efficiënte reactie mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="fef4a-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="fef4a-116">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="fef4a-116">Before you begin</span></span>

<span data-ttu-id="fef4a-117">Als u een van de meegeleverde simulaties wilt uitvoeren, hebt u ten minste [één apparaat met onboarding nodig.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="fef4a-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="fef4a-118">Lees het walkthrough-document dat bij elk aanvalsscenario wordt geleverd.</span><span class="sxs-lookup"><span data-stu-id="fef4a-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="fef4a-119">Elk document bevat besturingssysteem- en toepassingsvereisten, evenals gedetailleerde instructies die specifiek zijn voor een aanvalsscenario.</span><span class="sxs-lookup"><span data-stu-id="fef4a-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="fef4a-120">Een simulatie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="fef4a-120">Run a simulation</span></span>

1. <span data-ttu-id="fef4a-121">Selecteer **in**  >  **Help-& zelfstudies** welke van de beschikbare aanvalsscenario's u wilt simuleren:</span><span class="sxs-lookup"><span data-stu-id="fef4a-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="fef4a-122">**Scenario 1: Document dropt backdoor-** simuleert de bezorging van een sociaal ontworpen lokmiddeldocument.</span><span class="sxs-lookup"><span data-stu-id="fef4a-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="fef4a-123">Het document start een speciaal ontworpen backdoor die aanvallers controle geeft.</span><span class="sxs-lookup"><span data-stu-id="fef4a-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="fef4a-124">**Scenario 2: PowerShell-script in bestandsloze** aanval : simuleert een bestandsloze aanval die afhankelijk is van PowerShell, waarbij de surface reduction van de aanval wordt belicht en de detectie van schadelijke geheugenactiviteit op apparaten wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="fef4a-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="fef4a-125">**Scenario 3: Geautomatiseerde reactie** op incidenten : activeert automatisch onderzoek, waarmee automatisch wordt gejaagd naar en herstelt van inbreukartefacten om de reactiecapaciteit voor incidenten te vergroten.</span><span class="sxs-lookup"><span data-stu-id="fef4a-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="fef4a-126">Download en lees het bijbehorende doorloopdocument dat bij het geselecteerde scenario is geleverd.</span><span class="sxs-lookup"><span data-stu-id="fef4a-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="fef4a-127">Download het simulatiebestand of kopieer het simulatiescript door naar  >  **Help-& navigeren.**</span><span class="sxs-lookup"><span data-stu-id="fef4a-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="fef4a-128">U kunt ervoor kiezen om het bestand of script te downloaden op het testapparaat, maar dit is niet verplicht.</span><span class="sxs-lookup"><span data-stu-id="fef4a-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="fef4a-129">Voer het simulatiebestand of script uit op het testapparaat, zoals wordt geïnstrueerd in het doorloopdocument.</span><span class="sxs-lookup"><span data-stu-id="fef4a-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="fef4a-130">Simulatiebestanden of scripts bootsen aanvalsactiviteit na, maar zijn in feite goedaardig en kunnen het testapparaat niet schaden of in gevaar brengen.</span><span class="sxs-lookup"><span data-stu-id="fef4a-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="fef4a-131">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="fef4a-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="fef4a-132">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="fef4a-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="fef4a-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fef4a-133">Related topics</span></span>

- [<span data-ttu-id="fef4a-134">Onboard-apparaten</span><span class="sxs-lookup"><span data-stu-id="fef4a-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="fef4a-135">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="fef4a-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
