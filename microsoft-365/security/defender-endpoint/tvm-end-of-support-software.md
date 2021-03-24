---
title: Software- en softwareversies voor het einde van de ondersteuning plannen
description: Ontdek en plan voor software- en softwareversies die niet meer worden ondersteund en geen beveiligingsupdates ontvangen.
keywords: threat and vulnerability management, mdatp tvm security recommendation, cyberbeveiligingsaanbeveling, actievolle beveiligingsaanbeveling
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7a1ee326540ec4baab19a266a4e570fd6a364306
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060613"
---
# <a name="plan-for-end-of-support-software-and-software-versions-with-threat-and-vulnerability-management"></a><span data-ttu-id="0c106-104">Plan voor end-of-support software- en softwareversies met bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="0c106-104">Plan for end-of-support software and software versions with threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0c106-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="0c106-105">**Applies to:**</span></span>

- [<span data-ttu-id="0c106-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="0c106-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0c106-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="0c106-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="0c106-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0c106-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0c106-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="0c106-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0c106-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="0c106-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="0c106-111">End-of-support (EOS), ook wel bekend als end-of-life (EOL), voor software- of softwareversies betekent dat ze niet meer worden ondersteund of geserviced en geen beveiligingsupdates ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0c106-111">End-of-support (EOS), otherwise known as end-of-life (EOL), for software or software versions means that they will no longer be supported or serviced, and will not receive security updates.</span></span> <span data-ttu-id="0c106-112">Wanneer u software- of softwareversies met beëindigde ondersteuning gebruikt, wordt uw organisatie blootgelegd aan beveiligingsproblemen, juridische en financiële risico's.</span><span class="sxs-lookup"><span data-stu-id="0c106-112">When you use software or software versions with ended support, you're exposing your organization to security vulnerabilities, legal, and financial risks.</span></span>

<span data-ttu-id="0c106-113">Het is essentieel voor beveiligings- en IT-beheerders om samen te werken en ervoor te zorgen dat de softwarevoorraad van de organisatie is geconfigureerd voor optimale resultaten, naleving en een gezond netwerkecosysteem.</span><span class="sxs-lookup"><span data-stu-id="0c106-113">It's crucial for Security and IT Administrators to work together and ensure that the organization's software inventory is configured for optimal results, compliance, and a healthy network ecosystem.</span></span> <span data-ttu-id="0c106-114">Ze moeten de opties bekijken om apps te verwijderen of te vervangen die einde-of-ondersteunings- en updateversies hebben bereikt die niet meer worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="0c106-114">They should examine the options to remove or replace apps that have reached end-of-support and update versions that are no longer supported.</span></span> <span data-ttu-id="0c106-115">U kunt het beste een  plan maken en implementeren vóór het einde van de ondersteuningsdatum.</span><span class="sxs-lookup"><span data-stu-id="0c106-115">It's best to create and implement a plan **before** the end of support dates.</span></span>

## <a name="find-software-or-software-versions-that-are-no-longer-supported"></a><span data-ttu-id="0c106-116">Software- of softwareversies zoeken die niet meer worden ondersteund</span><span class="sxs-lookup"><span data-stu-id="0c106-116">Find software or software versions that are no longer supported</span></span>

1. <span data-ttu-id="0c106-117">Ga in het menu Bedreigings- en kwetsbaarheidsbeheer naar [**Beveiligingsaanbevelingen.**](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="0c106-117">From the threat and vulnerability management menu, navigate to [**Security recommendations**](tvm-security-recommendation.md).</span></span>
2. <span data-ttu-id="0c106-118">Ga naar het **deelvenster Filters** en zoek naar de sectie Tags.</span><span class="sxs-lookup"><span data-stu-id="0c106-118">Go to the **Filters** panel and look for the tags section.</span></span> <span data-ttu-id="0c106-119">Selecteer een of meer van de EOS-tagopties.</span><span class="sxs-lookup"><span data-stu-id="0c106-119">Select one or more of the EOS tag options.</span></span> <span data-ttu-id="0c106-120">Vervolgens **toepassen.**</span><span class="sxs-lookup"><span data-stu-id="0c106-120">Then **Apply**.</span></span>

    ![Schermafbeeldingen met EOS-software, EOS-versies en toekomstige EOS-versies.](images/tvm-eos-tag.png)

3. <span data-ttu-id="0c106-122">U ziet een lijst met aanbevelingen met betrekking tot software met beëindigde ondersteuning, softwareversies die het einde van de ondersteuning zijn of versies met een binnenkort einde van de ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="0c106-122">You'll see a list of recommendations related to software with ended support, software versions that are end of support, or versions with upcoming end of support.</span></span> <span data-ttu-id="0c106-123">Deze tags zijn ook zichtbaar op de [pagina softwarevoorraad.](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="0c106-123">These tags are also visible in the [software inventory](tvm-software-inventory.md) page.</span></span>

    ![Aanbevelingen met EOS-tag.](images/tvm-eos-tags-column.png)

## <a name="list-of-versions-and-dates"></a><span data-ttu-id="0c106-125">Lijst met versies en datums</span><span class="sxs-lookup"><span data-stu-id="0c106-125">List of versions and dates</span></span>

<span data-ttu-id="0c106-126">Als u een lijst wilt weergeven met versies die het einde van de ondersteuning hebben bereikt, of binnenkort eindigen of ondersteunen, en deze datums, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="0c106-126">To view a list of versions that have reached end of support, or end or support soon, and those dates, follow the below steps:</span></span>

1. <span data-ttu-id="0c106-127">Er wordt een bericht weergegeven in de flyout beveiligingsaanbeveling voor software met versies die het einde van de ondersteuning hebben bereikt of binnenkort het einde van de ondersteuning bereiken.</span><span class="sxs-lookup"><span data-stu-id="0c106-127">A message will appear in the security recommendation flyout for software with versions that have reached end of support, or will reach end of support soon.</span></span>

    ![Schermafbeelding van de koppeling versieverdeling.](images/eos-upcoming-eos.png)

2. <span data-ttu-id="0c106-129">Selecteer de **koppeling versiedistributie** om naar de inzoompagina van de software te gaan.</span><span class="sxs-lookup"><span data-stu-id="0c106-129">Select the **version distribution** link to go to the software drill-down page.</span></span> <span data-ttu-id="0c106-130">Daar ziet u een gefilterde lijst met versies met tags die deze identificeren als einde van de ondersteuning of het aanstaande einde van de ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="0c106-130">There, you can see a filtered list of versions with tags identifying them as end of support, or upcoming end of support.</span></span>

    ![Schermafbeelding van de inzoompagina van de software met het einde van de ondersteuningssoftware.](images/software-drilldown-eos.png)

3. <span data-ttu-id="0c106-132">Selecteer een van de versies in de tabel die u wilt openen.</span><span class="sxs-lookup"><span data-stu-id="0c106-132">Select one of the versions in the table to open.</span></span> <span data-ttu-id="0c106-133">Bijvoorbeeld versie 10.0.18362.1.</span><span class="sxs-lookup"><span data-stu-id="0c106-133">For example, version 10.0.18362.1.</span></span> <span data-ttu-id="0c106-134">Er wordt een flyout weergegeven met het einde van de ondersteuningsdatum.</span><span class="sxs-lookup"><span data-stu-id="0c106-134">A flyout will appear with the end of support date.</span></span>

    ![Schermafbeelding van het einde van de ondersteuningsdatum.](images/version-eos-date.png)

<span data-ttu-id="0c106-136">Nadat u hebt bepaald welke software- en softwareversies kwetsbaar zijn vanwege de status van het einde van de ondersteuning, moet u beslissen of u deze wilt bijwerken of verwijderen uit uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0c106-136">Once you identify which software and software versions are vulnerable due to their end-of-support status, you must decide whether to update or remove them from your organization.</span></span> <span data-ttu-id="0c106-137">Hierdoor worden uw organisaties minder blootgesteld aan beveiligingslekken en geavanceerde permanente bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="0c106-137">Doing so will lower your organizations exposure to vulnerabilities and advanced persistent threats.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0c106-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="0c106-138">Related topics</span></span>

- [<span data-ttu-id="0c106-139">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="0c106-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="0c106-140">Beveiligingsaanbevelingen</span><span class="sxs-lookup"><span data-stu-id="0c106-140">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="0c106-141">Softwarevoorraad</span><span class="sxs-lookup"><span data-stu-id="0c106-141">Software inventory</span></span>](tvm-software-inventory.md)
