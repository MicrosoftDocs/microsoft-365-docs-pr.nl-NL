---
title: Microsoft Security-richtlijnen - Politieke campagnes en non-profitorganisaties
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MET150
ms.custom:
- Strat_O365_Enterprise
- seo-marvel-apr2020
ms.assetid: 10d1004b-42b6-4e2b-aaa2-18ddd9118f64
description: 'Samenvatting: Planning en implementatie begeleiding voor snel bewegende organisaties met een verhoogd risicoprofiel.'
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f8ed01d2c41529782c5c714bfe66096b97300712
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287399"
---
# <a name="microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-organizations"></a><span data-ttu-id="6c503-103">Microsoft-beveiligingsrichtlijnen voor politieke campagnes, non-profitorganisaties en andere wendbare organisaties</span><span class="sxs-lookup"><span data-stu-id="6c503-103">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6c503-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="6c503-104">**Applies to**</span></span>
- [<span data-ttu-id="6c503-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="6c503-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="6c503-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6c503-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="6c503-107">**Samenvatting:** Planning en implementatie begeleiding voor snel bewegende organisaties met een verhoogd risicoprofiel.</span><span class="sxs-lookup"><span data-stu-id="6c503-107">**Summary:** Planning and implementation guidance for fast-moving organizations that have an increased threat profile.</span></span>

<span data-ttu-id="6c503-108">Als uw organisatie wendbaar is, u een klein IT-team heeft en uw risicoprofiel hoger is dan gemiddeld, is deze begeleiding voor u ontworpen.</span><span class="sxs-lookup"><span data-stu-id="6c503-108">If your organization is agile, you have a small IT team, and your threat profile is higher than average, this guidance is designed for you.</span></span> <span data-ttu-id="6c503-109">In deze oplossing wordt gedemonstreerd hoe u snel een omgeving kunt bouwen met essentiële cloudservices die vanaf het begin beveiligde besturingselementen bevatten.</span><span class="sxs-lookup"><span data-stu-id="6c503-109">This solution demonstrates how to quickly build an environment with essential cloud services that include secure controls from the start.</span></span> <span data-ttu-id="6c503-110">Deze richtlijnen bevatten beveiligingsaanbevelingen voor het beschermen van gegevens, identiteiten, e-mail en toegang vanaf mobiele apparaten.</span><span class="sxs-lookup"><span data-stu-id="6c503-110">This guidance includes prescriptive security recommendations for protecting data, identities, email, and access from mobile devices.</span></span>

## <a name="security-solution-guidance"></a><span data-ttu-id="6c503-111">Richtlijnen voor beveiligingsoplossingen</span><span class="sxs-lookup"><span data-stu-id="6c503-111">Security solution guidance</span></span>

<span data-ttu-id="6c503-112">Deze richtlijn beschrijft hoe u een veilige cloudomgeving implementeert.</span><span class="sxs-lookup"><span data-stu-id="6c503-112">This guidance describes how to implement a secure cloud environment.</span></span> <span data-ttu-id="6c503-113">De oplossingsrichtlijn kan door elke organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6c503-113">The solution guidance can be used by any organization.</span></span> <span data-ttu-id="6c503-114">Het bevat extra hulp voor wendbare organisaties met BYOD-toegang en gastaccounts.</span><span class="sxs-lookup"><span data-stu-id="6c503-114">It includes extra help for agile organizations with BYOD access and guest accounts.</span></span> <span data-ttu-id="6c503-115">U kunt deze richtlijnen gebruiken als uitgangspunt voor het ontwerpen van uw eigen omgeving.</span><span class="sxs-lookup"><span data-stu-id="6c503-115">You can use this guidance as a starting-point for designing your own environment.</span></span> <span data-ttu-id="6c503-116">We verwelkomen uw feedback op [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6c503-116">We welcome your feedback at [CloudAdopt@microsoft.com](mailto:CloudAdopt@microsoft.com).</span></span>

****

|<span data-ttu-id="6c503-117">Item</span><span class="sxs-lookup"><span data-stu-id="6c503-117">Item</span></span>|<span data-ttu-id="6c503-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="6c503-118">Description</span></span>|
|---|---|
|<span data-ttu-id="6c503-119">**Microsoft Security-richtlijnen voor politieke campagnes**</span><span class="sxs-lookup"><span data-stu-id="6c503-119">**Microsoft Security Guidance for Political Campaigns**</span></span> <br> <span data-ttu-id="6c503-120">[![Miniatuur voor miniposterserie.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span><span class="sxs-lookup"><span data-stu-id="6c503-120">[![Thumbnail for mini poster set.](../../media/d370ce28-ca40-4930-9a2c-907312aa06c8.png)](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf)</span></span> <br> <span data-ttu-id="6c503-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span><span class="sxs-lookup"><span data-stu-id="6c503-121">[PDF](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.pdf) \| [Visio](https://download.microsoft.com/download/B/4/D/B4D520C3-4D0C-4B4D-BFB9-09F0651C2775/MSFT_Cloud_architecture_security%20for%20political%20campaigns.vsdx)</span></span>|<span data-ttu-id="6c503-122">In deze instructies wordt een politieke campagne organisatie als voorbeeld gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6c503-122">This guidance uses a political campaign organization as an example.</span></span> <span data-ttu-id="6c503-123">U kunt deze richtlijnen gebruiken als uitgangspunt voor het ontwerpen van uw eigen omgeving.</span><span class="sxs-lookup"><span data-stu-id="6c503-123">Use this guidance as a starting point for any environment.</span></span>|
|<span data-ttu-id="6c503-124">**Microsoft Security-richtlijnen voor non-profitorganisaties**</span><span class="sxs-lookup"><span data-stu-id="6c503-124">**Microsoft Security Guidance for Nonprofits**</span></span> <br> <span data-ttu-id="6c503-125">[![Miniatuurafbeelding voor downloadbaar bestand](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span><span class="sxs-lookup"><span data-stu-id="6c503-125">[![Thumbnail image for downloadable file](../../media/e4784889-1c69-4067-9a8f-31d31d1eceea.png)](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf)</span></span> <br> <span data-ttu-id="6c503-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span><span class="sxs-lookup"><span data-stu-id="6c503-126">[PDF](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.pdf) \| [Visio](https://download.microsoft.com/download/9/4/3/94389612-C679-4061-8DF2-D9A15D72B65F/Microsoft_Cloud%20Architecture_Security%20for%20Nonprofits.vsdx)</span></span>|<span data-ttu-id="6c503-127">Deze handleiding is enigszins gewijzigd voor non-profit organisaties.</span><span class="sxs-lookup"><span data-stu-id="6c503-127">This guide is slightly revised for nonprofit organizations.</span></span> <span data-ttu-id="6c503-128">Er wordt bijvoorbeeld verwezen naar Office 365 Non-profit-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="6c503-128">For example, it references Office 365 Nonprofit plans.</span></span> <span data-ttu-id="6c503-129">De technische richtlijnen zijn dezelfde als in de handleiding voor politieke campagnes.</span><span class="sxs-lookup"><span data-stu-id="6c503-129">The technical guidance is the same as the political campaign solution guide.</span></span>|
|

## <a name="test-lab-guides"></a><span data-ttu-id="6c503-130">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="6c503-130">Test Lab Guides</span></span>

<span data-ttu-id="6c503-131">Als u een ontwikkel- of testomgeving voor deze oplossing wilt maken, gebruikt u de volgende testlabrichtlijnen:</span><span class="sxs-lookup"><span data-stu-id="6c503-131">To create a dev/test environment for this solution, use the following test lab guides:</span></span>

- [<span data-ttu-id="6c503-132">Configureer groepen en gebruikers voor een ontwikkel-/testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="6c503-132">Configure groups and users for a political campaign dev/test environment</span></span>](configure-groups-and-users-for-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="6c503-133">Maak proefabonnementen voor Office 365 en EMS en maak vervolgens groepen en gebruikers voor een representatieve politieke campagne.</span><span class="sxs-lookup"><span data-stu-id="6c503-133">Create trial subscriptions for Office 365 and EMS and then create groups and users for a representative political campaign.</span></span>

- [<span data-ttu-id="6c503-134">Maak teamsites in een ontwikkel- en testomgeving voor politieke campagnes</span><span class="sxs-lookup"><span data-stu-id="6c503-134">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

  <span data-ttu-id="6c503-135">Maak vier SharePoint Online-teamsites met interne, privé, vertrouwelijke en zeer vertrouwelijke beveiligingsniveaus.</span><span class="sxs-lookup"><span data-stu-id="6c503-135">Create four SharePoint Online team sites with Internal, Private, Sensitive, and Highly Confidential levels of security.</span></span>

<span data-ttu-id="6c503-136">Als u extra beveiligingsfuncties voor demonstratie of proof-of-concept wilt, raadpleegt u [Office 365-testlab-richtlijnen](https://aka.ms/o365tlgs).</span><span class="sxs-lookup"><span data-stu-id="6c503-136">For additional security features for demonstration or proof of concept, see [Office 365 Test Lab Guides](https://aka.ms/o365tlgs).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c503-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6c503-137">See Also</span></span>

[<span data-ttu-id="6c503-138">Testlabrichtlijnen voor cloudacceptatie (TLG's)</span><span class="sxs-lookup"><span data-stu-id="6c503-138">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="6c503-139">Bronnen over IT-architectuur voor de Microsoft-cloud</span><span class="sxs-lookup"><span data-stu-id="6c503-139">Microsoft Cloud IT architecture resources</span></span>](../../solutions/cloud-architecture-models.md)
