---
title: 'Fase 4: Microsoft 365-apps voor ondernemingen'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: De stappen om de infrastructuur voor Microsoft 365-apps voor ondernemingen voor Microsoft 365 Enterprise te implementeren.
ms.openlocfilehash: fe29b8025a8ccf5babf2c52cd62ebc72860a8a5c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631427"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="4504b-103">Fase 4: Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4504b-103">Phase 4: Microsoft 365 Apps for enterprise</span></span>

![Fase 4: Microsoft 365-apps voor ondernemingen](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

<span data-ttu-id="4504b-105">*Dit geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise en Microsoft 365 Education*</span><span class="sxs-lookup"><span data-stu-id="4504b-105">*This applies to both the E3 and E5 versions of Microsoft 365 Enterprise and Microsoft 365 Education*</span></span>

<span data-ttu-id="4504b-106">Microsoft 365 Enterprise omvat Microsoft 365-apps voor ondernemingen, de abonnementsversie van Office.</span><span class="sxs-lookup"><span data-stu-id="4504b-106">Microsoft 365 Enterprise includes Microsoft 365 Apps for enterprise, the subscription version of Office.</span></span> <span data-ttu-id="4504b-107">Net als Office 2019 biedt Microsoft 365-apps voor ondernemingen alle Office-toepassingen en worden deze toepassingen rechtstreeks op uw clientapparaten geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="4504b-107">Like Office 2019, Microsoft 365 Apps for enterprise includes all the Office applications, and those applications are installed directly on your client devices.</span></span> <span data-ttu-id="4504b-108">In tegenstelling tot Office 2019 wordt Microsoft 365-apps voor ondernemingen regelmatig bijgewerkt met nieuwe functies en heeft het een licentiemodel voor gebruikers waarmee personen Office kunnen installeren op meerdere apparaten.</span><span class="sxs-lookup"><span data-stu-id="4504b-108">Unlike Office 2019, Microsoft 365 Apps for enterprise is updated with new features on a regular basis and has a user-based licensing model that allows people to install Office on multiple devices.</span></span> <span data-ttu-id="4504b-109">Zie [Over Microsoft 365-apps voor ondernemingen in de onderneming](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4504b-109">For more details, see [About Microsoft 365 Apps for enterprise in the enterprise](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).</span></span>

<span data-ttu-id="4504b-110">In deze fase implementeert u Microsoft 365-apps voor ondernemingen op clientapparaten als onderdeel van Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4504b-110">In this phase, you deploy Microsoft 365 Apps for enterprise to client devices as part of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="4504b-111">Naast deze richtlijnen wordt u aangeraden gebruik te maken van [Microsoft Fastrack](https://fasttrack.microsoft.com/office) voor hulp bij de implementatie.</span><span class="sxs-lookup"><span data-stu-id="4504b-111">In addition to this guidance, we recommend you use [Microsoft Fastrack](https://fasttrack.microsoft.com/office) to help with your deployment.</span></span> 

<span data-ttu-id="4504b-112">Als u Microsoft 365-apps voor ondernemingen al hebt geïmplementeerd, bekijkt u het [afsluitcriterium](office365proplus-exit-criteria.md) voor deze fase om er zeker van te zijn dat deze voldoet aan de vereiste voorwaarden voor Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4504b-112">If you already have Microsoft 365 Apps for enterprise deployed, please see the [exit criteria](office365proplus-exit-criteria.md) for this phase to make sure that it meets the required conditions for Microsoft 365 Enterprise.</span></span>

>[!Note]
><span data-ttu-id="4504b-113">Als u zowel Windows 10 Enterprise als Microsoft 365-apps voor ondernemingen samen wilt implementeren, raadpleegt u het [Desktop Deployment Center](desktop-deployment-center-home.md).</span><span class="sxs-lookup"><span data-stu-id="4504b-113">To deploy both Windows 10 Enterprise and Microsoft 365 Apps for enterprise together, see the [Desktop Deployment Center](desktop-deployment-center-home.md).</span></span>
>

## <a name="step-1-assess-your-environment"></a><span data-ttu-id="4504b-114">Stap 1: Uw omgeving evalueren</span><span class="sxs-lookup"><span data-stu-id="4504b-114">Step 1: Assess your environment</span></span>

<span data-ttu-id="4504b-115">Volg de richtlijnen in [Assess your environment and requirements for deploying Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus) (Uw omgeving en vereisten evalueren voor de implementatie van Microsoft 365-apps voor ondernemingen) voordat u Microsoft 365-apps voor ondernemingen implementeert.</span><span class="sxs-lookup"><span data-stu-id="4504b-115">Before deploying Microsoft 365 Apps for enterprise, follow the guidance in [Assess your environment and requirements for deploying Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus).</span></span> <span data-ttu-id="4504b-116">Deze evaluatie omvat de systeemvereisten, details van uw clientapparaten (zoals architecturen en vereiste talen), licentievereisten, netwerkfunctionaliteit en toepassingscompatibiliteit.</span><span class="sxs-lookup"><span data-stu-id="4504b-116">This assessment includes system requirements, details of your client devices (such as architectures and required languages), licensing requirements, network capability, and application compatibility.</span></span> <span data-ttu-id="4504b-117">Door de beoordeling te voltooien, kunt u belangrijke beslissingen nemen als onderdeel van de planning van uw implementatie.</span><span class="sxs-lookup"><span data-stu-id="4504b-117">Completing the assessment will help you make key decisions as part of planning your deployment.</span></span>

## <a name="step-2-plan-your-deployment"></a><span data-ttu-id="4504b-118">Stap 2: Uw implementatie plannen</span><span class="sxs-lookup"><span data-stu-id="4504b-118">Step 2: Plan your deployment</span></span>

<span data-ttu-id="4504b-119">Volg na het beoordelen van uw omgeving de richtlijnen in [Uw implementatie van Microsoft 365-apps voor ondernemingen plannen](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) voor het maken van een implementatieplan.</span><span class="sxs-lookup"><span data-stu-id="4504b-119">After assessing your environment, follow the guidance in [Plan your deployment of Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) to create a deployment plan.</span></span> <span data-ttu-id="4504b-120">Dit plan omvat de volgende beslissingen:</span><span class="sxs-lookup"><span data-stu-id="4504b-120">This plan includes the following decisions:</span></span> 

- <span data-ttu-id="4504b-121">Het implementeren van Office, met inbegrip van het programma dat u gaat gebruiken (zoals Microsoft Endpoint Configuration Manager of het Office Deployment Tool) en waar u Office vanuit kunt installeren</span><span class="sxs-lookup"><span data-stu-id="4504b-121">How to deploy Office, including what tool to use (such as Microsoft Endpoint Configuration Manager or the Office Deployment Tool) and where to install Office from</span></span>
- <span data-ttu-id="4504b-122">Updates voor Office beheren</span><span class="sxs-lookup"><span data-stu-id="4504b-122">How to manage updates to Office</span></span>
- <span data-ttu-id="4504b-123">Welke updatekanalen te gebruiken (updatekanalen voor Office bepalen hoe vaak uw gebruikers functie-updates ontvangen voor hun Office-toepassingen)</span><span class="sxs-lookup"><span data-stu-id="4504b-123">Which update channels to use (update channels for Office control how frequently your users receive feature updates to their Office applications)</span></span>
- <span data-ttu-id="4504b-124">De Office-installatiepakketten en -implementatiegroepen die u wilt gebruiken, met inbegrip van welke Office-toepassingen en -talen geïnstalleerd moeten worden voor welke gebruikers</span><span class="sxs-lookup"><span data-stu-id="4504b-124">The Office installation packages and deployment groups you want to use, including which Office applications and languages should be installed for which users</span></span>

<span data-ttu-id="4504b-125">Het [planningsartikel](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) bevat aanbevolen procedures voor al deze opties, waaronder het beheren van de implementatie, het beheren van uw updates, het definiëren van installatiepakketten en het maken van implementatiegroepen.</span><span class="sxs-lookup"><span data-stu-id="4504b-125">The [planning article](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) includes best practices for all these options, including managing your deployment, managing your updates, defining installation packages, and creating deployment groups.</span></span> 

## <a name="step-3-deploy"></a><span data-ttu-id="4504b-126">Stap 3: Implementeren</span><span class="sxs-lookup"><span data-stu-id="4504b-126">Step 3: Deploy</span></span>

<span data-ttu-id="4504b-127">Kies op basis van uw implementatieplan hoe u wilt implementeren:</span><span class="sxs-lookup"><span data-stu-id="4504b-127">Based on your deployment plan, choose how you want to deploy:</span></span>

- <span data-ttu-id="4504b-128">**[Microsoft 365-apps voor ondernemingen implementeren met Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Beheer uw implementatie met Configuration Manager en download en implementeer Office vanaf distributiepunten op uw netwerk</span><span class="sxs-lookup"><span data-stu-id="4504b-128">**[Deploy Microsoft 365 Apps for enterprise with Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** Manage your deployment with Configuration Manager, and download and deploy Office from distribution points on your network</span></span>

- <span data-ttu-id="4504b-129">**[Microsoft 365-apps voor ondernemingen implementeren met de ODT uit de Cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Beheer uw implementatie met de ODT en installeer Office rechtstreeks vanuit het Office CDN op clientapparaten</span><span class="sxs-lookup"><span data-stu-id="4504b-129">**[Deploy Microsoft 365 Apps for enterprise with the ODT from the cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** Manage your deployment with the ODT, and install Office on client devices directly from the Office CDN</span></span>
 
- <span data-ttu-id="4504b-130">**[Microsoft 365-apps voor ondernemingen zelf installeren vanuit de Office-portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Beheer uw implementatie vanuit de Office-portal en laat uw gebruikers Office rechtstreeks vanuit de portal installeren op hun clientapparaten</span><span class="sxs-lookup"><span data-stu-id="4504b-130">**[Self-install Microsoft 365 Apps for enterprise from the Office portal](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** Manage your deployment from the Office portal and have your users install Office on their client devices directly from the portal</span></span>

<span data-ttu-id="4504b-131">Veel organisaties gebruiken een combinatie van deze opties voor verschillende gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4504b-131">Many organizations will use a combination of these options for different users.</span></span> <span data-ttu-id="4504b-132">Een organisatie kan bijvoorbeeld voor de meeste gebruikers Configuration Manager gebruiken om Office te implementeren, maar een kleine groep werknemers die niet regelmatig met het interne netwerk verbonden zijn zelf laten installeren.</span><span class="sxs-lookup"><span data-stu-id="4504b-132">For example, an organization might use Configuration Manager to deploy Office to most of their users, but enable self-install for a small group of workers who are not frequently connected to the internal network.</span></span> 

<span data-ttu-id="4504b-133">Als uw organisatie Configuration Manager gebruikt, raden we u aan een upgrade uit te voeren naar de Huidige vertakking en een update uit te voeren naar de huidige versie.</span><span class="sxs-lookup"><span data-stu-id="4504b-133">If your organization uses Configuration Manager, we recommend upgrading to the Current Branch and updating to the current release.</span></span> <span data-ttu-id="4504b-134">Zie [Welke vertakking van Configuration Manager moet ik gebruiken?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="4504b-134">For more details, see [Which branch of Configuration Manager should I use?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)</span></span>

## <a name="how-microsoft-does-microsoft-365-enterprise"></a><span data-ttu-id="4504b-135">Hoe Microsoft omgaat met Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4504b-135">How Microsoft does Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4504b-136">Lees hoe de experts van Microsoft [updates voor Microsoft 365-apps voor ondernemingen implementeren en beheren](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span><span class="sxs-lookup"><span data-stu-id="4504b-136">Learn how the experts at Microsoft are [deploying and managing updates for Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).</span></span>

## <a name="how-contoso-did-microsoft-365-enterprise"></a><span data-ttu-id="4504b-137">Hoe Contoso Microsoft 365 Enterprise gebruikt</span><span class="sxs-lookup"><span data-stu-id="4504b-137">How Contoso did Microsoft 365 Enterprise</span></span>

<span data-ttu-id="4504b-138">Bekijk hoe de Contoso Corporation, een fictieve maar representatieve multinational, [Microsoft 365-apps voor ondernemingen heeft geïmplementeerd](contoso-o365pp.md).</span><span class="sxs-lookup"><span data-stu-id="4504b-138">See how the Contoso Corporation, a fictional but representative multi-national business, [deployed Microsoft 365 Apps for enterprise](contoso-o365pp.md).</span></span>

![De Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a><span data-ttu-id="4504b-140">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="4504b-140">Next step</span></span>

[<span data-ttu-id="4504b-141">Afsluitcriteria voor de infrastructuur voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4504b-141">Microsoft 365 Apps for enterprise infrastructure exit criteria</span></span>](office365proplus-exit-criteria.md)
