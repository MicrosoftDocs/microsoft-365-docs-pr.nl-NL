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
description: Meer informatie over het kiezen en implementeren van de juiste Teams spraakoplossing voor uw organisatie.
ms.openlocfilehash: ede8075767e9d0a80123ac742403f8a4d171392e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918380"
---
# <a name="plan-and-deploy-a-teams-voice-solution"></a><span data-ttu-id="d9f1a-103">Een Teams-spraakoplossing plannen en implementeren</span><span class="sxs-lookup"><span data-stu-id="d9f1a-103">Plan and deploy a Teams voice solution</span></span>

<span data-ttu-id="d9f1a-104">Met Teams spraakoplossing kunnen personen in uw organisatie zowel binnen als buiten uw organisatie bellen.</span><span class="sxs-lookup"><span data-stu-id="d9f1a-104">A Teams voice solution enables people in your organization to make calls both within and outside your organization.</span></span> <span data-ttu-id="d9f1a-105">Een volledige spraakoplossing bestaat uit Teams, Microsoft Telefoon Systeem en een keuze uit opties voor het maken van verbinding met het PsTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="d9f1a-105">A complete voice solution consists of Teams, Microsoft Phone System, and a choice of options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

![Teams overzicht van spraakoplossingen](..\media\solutions-architecture-center\voice-concepts.png)

<span data-ttu-id="d9f1a-107">Telefoonsysteem biedt volledige mogelijkheden voor Private Branch Exchange (PBX) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d9f1a-107">Phone System provides complete Private Branch Exchange (PBX) capabilities for your organization.</span></span> <span data-ttu-id="d9f1a-108">Oproepen tussen gebruikers in uw organisatie, ongeacht hun geografische locatie, worden intern afgehandeld binnen Telefoonsysteem waardoor kosten over lange afstand voor deze interne gesprekken worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d9f1a-108">Calls between users in your organization--no matter their geographic location--are handled internally within Phone System thereby removing long-distance costs on these internal calls.</span></span>  

<span data-ttu-id="d9f1a-109">Door verbinding te Telefoonsysteem met het PSTN (Public Switched Telephone Network) kunnen uw Teams ook buiten uw organisatie bellen.</span><span class="sxs-lookup"><span data-stu-id="d9f1a-109">By connecting Phone System to the Public Switched Telephone Network (PSTN), your Teams users can make calls outside your organization as well.</span></span>

<span data-ttu-id="d9f1a-110">Met deze richtlijnen voor oplossingen kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="d9f1a-110">This solution guidance helps you to:</span></span>

- <span data-ttu-id="d9f1a-111">Kies de spraakoplossing die bij uw organisatie hoort</span><span class="sxs-lookup"><span data-stu-id="d9f1a-111">Choose the voice solution that is right for your organization</span></span>
- <span data-ttu-id="d9f1a-112">De spraakoplossing implementeren die u hebt geselecteerd</span><span class="sxs-lookup"><span data-stu-id="d9f1a-112">Deploy the voice solution you selected</span></span>

<span data-ttu-id="d9f1a-113">Volg de volgende stappen om uw spraakoplossing te kiezen, te plannen en te configureren:</span><span class="sxs-lookup"><span data-stu-id="d9f1a-113">Follow these steps to choose, plan, and configure your voice solution:</span></span>

![Kies uw voice oplossing](..\media\solutions-architecture-center\voice-solutions-overview-1.png)

1. [<span data-ttu-id="d9f1a-115">Kies uw voice oplossing</span><span class="sxs-lookup"><span data-stu-id="d9f1a-115">Choose your voice solution</span></span>](/MicrosoftTeams/cloud-voice-landing-page?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

2. [<span data-ttu-id="d9f1a-116">Een Telefoonsysteem</span><span class="sxs-lookup"><span data-stu-id="d9f1a-116">Set up Phone System</span></span>](/microsoftteams/setting-up-your-phone-system?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)

3. <span data-ttu-id="d9f1a-117">Stel PSTN-connectiviteit in door een van de volgende opties of een combinatie te kiezen:</span><span class="sxs-lookup"><span data-stu-id="d9f1a-117">Set up PSTN connectivity by choosing one, or a combination, of the following:</span></span>
   - <span data-ttu-id="d9f1a-118">[Abonnement voor](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) bellen - Microsoft's all-in-the-cloud-oplossing met Microsoft als uw PSTN-provider</span><span class="sxs-lookup"><span data-stu-id="d9f1a-118">[Calling Plan](/microsoftteams/set-up-calling-plans?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Microsoft's all-in-the-cloud solution with Microsoft as your PSTN carrier</span></span>
   - <span data-ttu-id="d9f1a-119">[Directe routering:](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) gebruik Direct Routering om uw eigen PSTN-provider te verbinden met Teams</span><span class="sxs-lookup"><span data-stu-id="d9f1a-119">[Direct Routing](/microsoftteams/direct-routing-configure?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json) - Use Direct Routing to connect your own PSTN carrier to Teams</span></span> 

<span data-ttu-id="d9f1a-120">Daarnaast wilt u misschien lezen hoe een groot, multi-nationaal bedrijf is gemigreerd naar een Teams spraakoplossing in de [contoso-casestudie.](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="d9f1a-120">In addition, you might want read about how a large, multi-national corporation migrated to a Teams voice solution in the [Contoso case study](/MicrosoftTeams/voice-case-study-overview?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoft-365%2fsolutions%2ftoc.json).</span></span>

<span data-ttu-id="d9f1a-121">Zie de volgende informatie over vereiste licenties:</span><span class="sxs-lookup"><span data-stu-id="d9f1a-121">For information about required licenses, see the following:</span></span>

- [<span data-ttu-id="d9f1a-122">Teams invoeglicenties</span><span class="sxs-lookup"><span data-stu-id="d9f1a-122">Teams add-on licenses</span></span>](/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json&tabs=enterprise#what-voice-features-are-available-with-my-plan/toc.json)

- [<span data-ttu-id="d9f1a-123">Vereisten voor directe routeringslicenties</span><span class="sxs-lookup"><span data-stu-id="d9f1a-123">Direct Routing licensing requirements</span></span>](/microsoftteams/direct-routing-plan?bc=%2fmicrosoft-365%2fsolutions%2fbreadcrumb%2ftoc.json#licensing-and-other-requirements/toc.json)