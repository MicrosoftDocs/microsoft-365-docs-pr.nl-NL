---
title: Spraak implementeren in Microsoft 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-overview
- m365solution-voice
- M365-voice
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Leer hoe u de juiste spraak oplossing voor teams kiest en implementeert voor uw organisatie.
ms.openlocfilehash: b5dda0ed3d9310c3c43052b9bac4996802e0ed2f
ms.sourcegitcommit: e53234b1f64ebca00e121da1706c02b3337c35f0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/05/2020
ms.locfileid: "49580891"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="766e6-103">Een spraak oplossing voor teams plannen en implementeren</span><span class="sxs-lookup"><span data-stu-id="766e6-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="766e6-104">Met een oplossing voor spraak oplossing kunnen personen binnen en buiten uw organisatie gesprekken voeren.</span><span class="sxs-lookup"><span data-stu-id="766e6-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="766e6-105">Een volledige spraak oplossing bestaat uit teams, Microsoft-telefoonsysteem en een optie voor het maken van verbinding met het Public Switched Telephone Network (PSTN).</span><span class="sxs-lookup"><span data-stu-id="766e6-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Overzicht van spraak oplossingen voor teams](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="766e6-107">Telefoonsysteem biedt uitgebreide functies voor Private Branch Exchange (PBX) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="766e6-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="766e6-108">Gesprekken tussen gebruikers in uw organisatie, ongeacht hun geografische locatie, worden intern binnen het telefoonsysteem verwerkt, zodat de lange afstands kosten voor deze interne gesprekken worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="766e6-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="766e6-109">Door telefoonsysteem te verbinden met het Public Switched Telephone Network (PSTN), kunnen uw teams-gebruikers ook oproepen doen buiten uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="766e6-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="766e6-110">Met deze oplossing kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="766e6-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="766e6-111">Kies de stem oplossing die geschikt is voor uw organisatie</span><span class="sxs-lookup"><span data-stu-id="766e6-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="766e6-112">De geselecteerde spraak oplossing implementeren</span><span class="sxs-lookup"><span data-stu-id="766e6-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="766e6-113">Voer de volgende stappen uit om uw spraak oplossing te kiezen, te plannen en te configureren:</span><span class="sxs-lookup"><span data-stu-id="766e6-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Uw stem oplossing kiezen](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="766e6-115">Uw stem oplossing kiezen</span><span class="sxs-lookup"><span data-stu-id="766e6-115">Choose your voice solution</span></span>](https://docs.microsoft.com/MicrosoftTeams/cloud-voice-landing-page?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

2. [<span data-ttu-id="766e6-116">Telefoonsysteem instellen</span><span class="sxs-lookup"><span data-stu-id="766e6-116">Set up Phone System</span></span>](https://docs.microsoft.com/microsoftteams/setting-up-your-phone-system?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

3. <span data-ttu-id="766e6-117">Stel een PSTN-verbinding in door een of meer van de volgende opties te kiezen:</span><span class="sxs-lookup"><span data-stu-id="766e6-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="766e6-118">[Abonnement voor gesprekken](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) : Microsoft de all-in-the-in-the-Cloud oplossing van Microsoft als uw PSTN-provider</span><span class="sxs-lookup"><span data-stu-id="766e6-118">[Calling Plan](https://docs.microsoft.com/microsoftteams/set-up-calling-plans?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="766e6-119">[Directe routering](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) : gebruik directe routering om uw eigen PSTN-provider te verbinden met teams</span><span class="sxs-lookup"><span data-stu-id="766e6-119">[Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="766e6-120">Daarnaast kunt u informatie lezen over hoe een grote, meervoudige nationale vennootschap gemigreerd naar een teams-spraak oplossing in het [Contoso](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)casestudy.</span><span class="sxs-lookup"><span data-stu-id="766e6-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](https://docs.microsoft.com/MicrosoftTeams/voice-case-study-overview?toc=/microsoft-365/solutions/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json).</span></span>

<span data-ttu-id="766e6-121">Zie de volgende informatie over de vereiste licenties:</span><span class="sxs-lookup"><span data-stu-id="766e6-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="766e6-122">Add-on-licenties voor teams</span><span class="sxs-lookup"><span data-stu-id="766e6-122">Teams add-on licenses</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)

- [<span data-ttu-id="766e6-123">Licentievereisten voor direct routeren</span><span class="sxs-lookup"><span data-stu-id="766e6-123">Direct Routing licensing requirements</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan#licensing-and-other-requirements/toc.json&bc=/microsoft-365/solutions/breadcrumb/toc.json)
