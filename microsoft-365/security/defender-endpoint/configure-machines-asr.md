---
title: Asr-regelimplementatie en -detecties optimaliseren
description: Optimaliseer de ASR-regels (Attack Surface Reduction) om typische malware-exploits te identificeren en te voorkomen.
keywords: onboard, Intune management, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, attack surface reduction, ASR, security baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841556"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="6cfbf-104">Asr-regelimplementatie en -detecties optimaliseren</span><span class="sxs-lookup"><span data-stu-id="6cfbf-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6cfbf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="6cfbf-105">**Applies to:**</span></span>
- [<span data-ttu-id="6cfbf-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6cfbf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6cfbf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6cfbf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6cfbf-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="6cfbf-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="6cfbf-109">[Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="6cfbf-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="6cfbf-110">[Asr-regels (Attack Surface Reduction)](./attack-surface-reduction.md) identificeren en voorkomen typische malware-exploits.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="6cfbf-111">Ze bepalen wanneer en hoe potentieel schadelijke code kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="6cfbf-112">Ze kunnen bijvoorbeeld voorkomen dat JavaScript of VBScript een gedownloade uitvoerbare start, Win32 API-oproepen van Office-macro's blokkeren en processen blokkeren die worden uitgevoerd via USB-stations.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="6cfbf-113">![Surface-beheerkaart voor aanvallen](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="6cfbf-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="6cfbf-114">*Surface-beheerkaart voor aanvallen*</span><span class="sxs-lookup"><span data-stu-id="6cfbf-114">*Attack surface management card*</span></span>

<span data-ttu-id="6cfbf-115">De *Surface Management-kaart Attack* is een toegangspunt voor hulpmiddelen in Microsoft 365 beveiligingscentrum waarmee u het volgende kunt doen:</span><span class="sxs-lookup"><span data-stu-id="6cfbf-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="6cfbf-116">Meer inzicht in de manier waarop ASR-regels momenteel worden geïmplementeerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="6cfbf-117">Controleer ASR-detecties en identificeer mogelijke onjuiste detecties.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="6cfbf-118">Analyseer de impact van uitsluitingen en genereer de lijst met bestandspaden die u wilt uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="6cfbf-119">Selecteer **Ga naar aanval op surface management** Monitoring & rapporten > Attack surface reduction rules > Add  >  **exclusions**.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="6cfbf-120">Hier kunt u naar andere secties van het Microsoft 365 gaan.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="6cfbf-121">![Tabblad Uitsluitingen toevoegen op de pagina Surface-regels voor aanvallen in Microsoft 365 beveiligingscentrum](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="6cfbf-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="6cfbf-122">Het ***tabblad Uitsluitingen toevoegen** op de pagina Surface-regels voor aanvallen in Microsoft 365 beveiligingscentrum*</span><span class="sxs-lookup"><span data-stu-id="6cfbf-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="6cfbf-123">Als u Microsoft 365 beveiligingscentrum wilt openen, hebt u een Microsoft 365 E3 of E5-licentie en een account met bepaalde rollen in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6cfbf-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="6cfbf-124">[Lees meer over vereiste licenties en machtigingen.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="6cfbf-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="6cfbf-125">Zie ASR-regelimplementatie en -detecties bewaken en beheren voor meer informatie over de implementatie van ASR-regels in Microsoft 365 [beveiligingscentrum.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)</span><span class="sxs-lookup"><span data-stu-id="6cfbf-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="6cfbf-126">**Verwante onderwerpen**</span><span class="sxs-lookup"><span data-stu-id="6cfbf-126">**Related topics**</span></span>

* [<span data-ttu-id="6cfbf-127">Controleren of uw apparaten juist zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="6cfbf-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="6cfbf-128">Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="6cfbf-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="6cfbf-129">Naleving van de beveiligingslijn van Microsoft Defender voor eindpunt controleren</span><span class="sxs-lookup"><span data-stu-id="6cfbf-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
