---
title: Stap 4. Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
ms.custom: ''
description: Gebruik Microsoft Endpoint Manager om uw apparaten, pc's en andere eindpunten te beheren.
ms.openlocfilehash: 0f13d36a2943367e751123c724cda28b503a51d2
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521539"
---
# <a name="step-4-deploy-endpoint-management-for-your-devices-pcs-and-other-endpoints"></a><span data-ttu-id="c2115-104">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="c2115-104">Step 4.</span></span> <span data-ttu-id="c2115-105">Eindpuntbeheer voor uw apparaten, pc's en andere eindpunten implementeren</span><span class="sxs-lookup"><span data-stu-id="c2115-105">Deploy endpoint management for your devices, PCs, and other endpoints</span></span>

<span data-ttu-id="c2115-106">Als u externe medewerkers hebt, moet u steeds meer persoonlijke apparaten ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="c2115-106">With remote workers, you need to support a growing number of personal devices.</span></span> <span data-ttu-id="c2115-107">Eindpuntbeheer biedt op beleid gebaseerde beveiliging waarbij apparaten moeten voldoen aan specifieke criteria voordat ze toegang krijgen tot bronnen.</span><span class="sxs-lookup"><span data-stu-id="c2115-107">Endpoint management is a policy-based approach to security that requires devices to comply with specific criteria before they are granted access to resources.</span></span> <span data-ttu-id="c2115-108">Microsoft Endpoint Manager biedt moderne beheermogelijkheden om uw gegevens in de cloud en on-premises veilig te houden.</span><span class="sxs-lookup"><span data-stu-id="c2115-108">Microsoft Endpoint Manager delivers modern management capabilities to keep your data secure in the cloud and on-premises.</span></span> 

<span data-ttu-id="c2115-109">Endpoint Manager biedt services en hulpprogramma‘s voor het beheer van mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers door enkele services te combineren die u mogelijk al kent en gebruikt:</span><span class="sxs-lookup"><span data-stu-id="c2115-109">Endpoint Manager provides services and tools for managing mobile devices, desktop computers, virtual machines, embedded devices, and servers by combining the following services you may already know and be using.</span></span>

![De onderdelen voor eindpuntbeheer](../media/empower-people-to-work-remotely/endpoint-managment-step-grid.png)

## <a name="microsoft-intune"></a><span data-ttu-id="c2115-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c2115-111">Microsoft Intune</span></span>

<span data-ttu-id="c2115-112">Microsoft Intune is een cloudservice die gericht is op Mobile Device Management (MDM) en Mobile Application Management (MAM) dat deel uitmaakt van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c2115-112">Microsoft Intune is a cloud-based service that focuses on mobile device management (MDM) and mobile application management (MAM) that is included with Microsoft 365.</span></span> 

- <span data-ttu-id="c2115-113">**MDM:** geeft u volledige controle over apparaten die eigendom zijn van de organisatie, inclusief het bewerken van instellingen, functies en beveiliging.</span><span class="sxs-lookup"><span data-stu-id="c2115-113">**MDM:** For organization-owned devices, you can exercise full control including settings, features, and security.</span></span> <span data-ttu-id="c2115-114">Apparaten zijn 'geregistreerd' in Intune waar ze Intune-beleid met regels en instellingen ontvangen.</span><span class="sxs-lookup"><span data-stu-id="c2115-114">Devices are "enrolled" in Intune where they receive Intune policies with rules and settings.</span></span> <span data-ttu-id="c2115-115">U kunt bijvoorbeeld wachtwoord- en PIN-vereisten instellen, een VPN-verbinding aanmaken, bedreigingsbeveiliging instellen en meer.</span><span class="sxs-lookup"><span data-stu-id="c2115-115">For example, you can set password and PIN requirements, create a VPN connection, set up threat protection, and more.</span></span>

- <span data-ttu-id="c2115-116">**MAM:** externe werknemers willen misschien niet dat u volledige controle hebt over hun persoonlijke apparaten, ook wel bekend als Bring-Your-Own-Device (BYOD).</span><span class="sxs-lookup"><span data-stu-id="c2115-116">**MAM:** Remote workers might not want you to have full control on their personal devices, also known as bring-your-own device (BYOD) devices.</span></span> <span data-ttu-id="c2115-117">U kunt voor externe werknemers opties beschikbaar maken en toch uw organisatie beschermen.</span><span class="sxs-lookup"><span data-stu-id="c2115-117">You can give your remote workers options and still protect your organization.</span></span> <span data-ttu-id="c2115-118">Zo kunnen externe werknemers hun apparaten registreren voor volledige toegang tot de resources van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c2115-118">For example, remote workers can enroll their devices if they want full access to your organization resources.</span></span> <span data-ttu-id="c2115-119">Als deze gebruikers alleen toegang willen tot e-mail of Microsoft Teams, kunt u app-beveiligingsbeleid gebruiken waarvoor meervoudige verificatie (MFA) vereist is om deze apps te kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c2115-119">Or, if these users only want access to email or Microsoft Teams, then use app protection policies that require multi-factor authentication (MFA) to use these apps.</span></span>

<span data-ttu-id="c2115-120">Zie voor meer informatie dit [overzicht van Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span><span class="sxs-lookup"><span data-stu-id="c2115-120">For more information, see this [overview of Microsoft Intune](https://docs.microsoft.com/intune/fundamentals/what-is-intune).</span></span>

## <a name="configuration-manager"></a><span data-ttu-id="c2115-121">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="c2115-121">Configuration Manager</span></span>

<span data-ttu-id="c2115-122">Configuration Manager is een on-premises beheeroplossing voor het beheer van desktops, servers en laptops op uw netwerk of op internet.</span><span class="sxs-lookup"><span data-stu-id="c2115-122">Configuration Manager is an on-premises management solution to manage desktops, servers, and laptops that are on your network or internet-based.</span></span> <span data-ttu-id="c2115-123">Gebruik Configuration Manager om apps, software-updates en besturingssystemen te implementeren.</span><span class="sxs-lookup"><span data-stu-id="c2115-123">Use Configuration Manager to deploy apps, software updates, and operating systems.</span></span> <span data-ttu-id="c2115-124">U kunt ook toezicht houden op naleving, clients in real time doorzoeken en hiermee communiceren, en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="c2115-124">You can also monitor compliance, query and act on clients in real time, and much more.</span></span> <span data-ttu-id="c2115-125">U kunt cloudtoegang inschakelen voor integratie met Intune, Azure AD, Microsoft Defender ATP en andere cloudservices.</span><span class="sxs-lookup"><span data-stu-id="c2115-125">You can cloud-enable it to integrate with Intune, Azure AD, Microsoft Defender ATP, and other cloud services.</span></span> 

<span data-ttu-id="c2115-126">Zie voor meer informatie dit [overzicht van Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span><span class="sxs-lookup"><span data-stu-id="c2115-126">For more information, see this [overview of Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/understand/introduction).</span></span>

## <a name="co-management"></a><span data-ttu-id="c2115-127">Co-management</span><span class="sxs-lookup"><span data-stu-id="c2115-127">Co-management</span></span>

<span data-ttu-id="c2115-128">Met co-management wordt uw bestaande on-premises Configuration Manager gekoppeld aan de cloud via Intune en andere Microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="c2115-128">Co-management combines your existing on-premises Configuration Manager investment with the cloud using Intune and other Microsoft 365 cloud services.</span></span> <span data-ttu-id="c2115-129">Kies of u Configuration Manager of Intune wilt gebruiken als instantie voor het beheer van wisselende werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="c2115-129">You choose whether Configuration Manager or Intune is the management authority for different workload.</span></span> 

<span data-ttu-id="c2115-130">Bij het gebruik van co-management worden cloudfuncties op basis van Intune gebruikt, waaronder voorwaardelijke toegang en het afdwingen van apparaatcompliance.</span><span class="sxs-lookup"><span data-stu-id="c2115-130">Co-management uses Intune-based cloud features, including Conditional Access and enforcing device compliance.</span></span> <span data-ttu-id="c2115-131">U kunt bepaalde taken on-premises blijven doen terwijl u andere taken in de cloud uitvoert.</span><span class="sxs-lookup"><span data-stu-id="c2115-131">You keep some tasks on-premises, while running other tasks in the cloud.</span></span>

<span data-ttu-id="c2115-132">Zie voor meer informatie dit [overzicht van co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span><span class="sxs-lookup"><span data-stu-id="c2115-132">For more information, see this [overview of co-management](https://docs.microsoft.com/mem/configmgr/comanage/overview).</span></span>

## <a name="desktop-analytics"></a><span data-ttu-id="c2115-133">Desktop Analytics</span><span class="sxs-lookup"><span data-stu-id="c2115-133">Desktop Analytics</span></span>

<span data-ttu-id="c2115-134">Desktop Analytics is een cloudservice die kan worden geïntegreerd met Configuration Manager en die u inzicht en informatie biedt, zodat u weloverwogen beslissingen kunt nemen over uw Windows-clients.</span><span class="sxs-lookup"><span data-stu-id="c2115-134">Desktop Analytics is a cloud-based service that integrates with Configuration Manager and provides you with insight and intelligence so you can make informed decisions about your Windows clients.</span></span> <span data-ttu-id="c2115-135">De service combineert gegevens van uw organisatie met gegevens verzameld van miljoenen apparaten die zijn verbonden met Microsoft-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="c2115-135">It combines data from your organization with data aggregated from millions of devices connected to Microsoft cloud services.</span></span> 

<span data-ttu-id="c2115-136">Met Desktop Analytics kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="c2115-136">With Desktop Analytics, you can:</span></span>

- <span data-ttu-id="c2115-137">Een inventaris maken van apps die in uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c2115-137">Create an inventory of apps running in your organization.</span></span>
- <span data-ttu-id="c2115-138">Compatibiliteit van de app met de meest recente functie-updates voor Windows 10 verifiëren.</span><span class="sxs-lookup"><span data-stu-id="c2115-138">Assess app compatibility with the latest Windows 10 feature updates.</span></span>
- <span data-ttu-id="c2115-139">Compatibiliteitsproblemen opsporen en suggesties voor risicobeperking ontvangen die zijn gebaseerd op gegevensinzichten uit de cloud.</span><span class="sxs-lookup"><span data-stu-id="c2115-139">Identify compatibility issues, and receive mitigation suggestions based on cloud-enabled data insights.</span></span>
- <span data-ttu-id="c2115-140">Testfasegroepen aanmaken die de gehele toepassing en stuurprogramma‘s op een minimale verzameling apparaten vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="c2115-140">Create pilot groups that represent the entire application and driver estate across a minimal set of devices.</span></span>
- <span data-ttu-id="c2115-141">Implementeer Windows 10 op testfase- en productieapparaten.</span><span class="sxs-lookup"><span data-stu-id="c2115-141">Deploy Windows 10 to pilot and production-managed devices.</span></span>

<span data-ttu-id="c2115-142">Zie voor meer informatie dit [overzicht van Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span><span class="sxs-lookup"><span data-stu-id="c2115-142">For more information, see this [overview of Desktop Analytics](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview)</span></span>

## <a name="windows-autopilot"></a><span data-ttu-id="c2115-143">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="c2115-143">Windows Autopilot</span></span>

<span data-ttu-id="c2115-144">Windows Autopilot is een zero-touch, selfservice Windows-implementatieplatform.</span><span class="sxs-lookup"><span data-stu-id="c2115-144">Windows Autopilot is a zero-touch, self-service Windows deployment platform.</span></span> <span data-ttu-id="c2115-145">Het platform bevat een verzameling technologieën die worden gebruikt om nieuwe apparaten in te stellen en vooraf te configureren, zodat ze klaar zijn voor productief gebruik.</span><span class="sxs-lookup"><span data-stu-id="c2115-145">It includes a collection of technologies used to set up and pre-configure new devices, getting them ready for productive use.</span></span> <span data-ttu-id="c2115-146">U kunt Windows Autopilot ook gebruiken om apparaten opnieuw in te stellen, aan te passen en te herstellen.</span><span class="sxs-lookup"><span data-stu-id="c2115-146">You can also use Windows Autopilot to reset, repurpose and recover devices.</span></span> 

<span data-ttu-id="c2115-147">Met Windows Autopilot kan een IT-afdeling apparaten vooraf configureren via een eenvoudig proces, nagenoeg zonder het beheer van enige infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="c2115-147">Windows Autopilot enables an IT department to pre-configure devices with little to no infrastructure to manage, with a process that's easy and simple.</span></span> 

- <span data-ttu-id="c2115-148">De apparaten voor gebruikers kunnen met slechts enkele eenvoudige bewerkingen worden klaargemaakt voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="c2115-148">From the user's perspective, it only takes a few simple operations to make their device ready to use.</span></span> 
- <span data-ttu-id="c2115-149">En IT-professionals hoeven er alleen maar voor te zorgen dat eindgebruikers verbinding kunnen maken met een netwerk door hun referenties te verifiëren.</span><span class="sxs-lookup"><span data-stu-id="c2115-149">From the IT pro's perspective, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span>

<span data-ttu-id="c2115-150">Voor meer informatie raadpleegt u dit [overzicht van Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span><span class="sxs-lookup"><span data-stu-id="c2115-150">For more information, see this [overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot).</span></span>

## <a name="admin-technical-resources-for-endpoint-management"></a><span data-ttu-id="c2115-151">Technische bronnen voor eindpuntbeheerders</span><span class="sxs-lookup"><span data-stu-id="c2115-151">Admin technical resources for endpoint management</span></span>

- [<span data-ttu-id="c2115-152">De video Deel 3 over het beheren van Windows 10-apparaten voor externe werknemers</span><span class="sxs-lookup"><span data-stu-id="c2115-152">The Part 3 video on managing Windows 10 devices for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="c2115-153">De video Deel 5 over het beheren van gebruikersdesktops en browsers voor externe werknemers</span><span class="sxs-lookup"><span data-stu-id="c2115-153">The Part 5 video on managing user desktops and browsers for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)
- [<span data-ttu-id="c2115-154">Een mobiliteitsinfrastructuur voor Microsoft 365 implementeren</span><span class="sxs-lookup"><span data-stu-id="c2115-154">Deploy a mobility infrastructure for Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/mobility-infrastructure)
- [<span data-ttu-id="c2115-155">Verschillende typen apparaten inschrijven voor het beheer van mobiele apparaten</span><span class="sxs-lookup"><span data-stu-id="c2115-155">How to enroll different types of devices for mobile device management</span></span>](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)
- [<span data-ttu-id="c2115-156">Uw eindgebruikers informeren over Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c2115-156">How to educate your end users about Microsoft Intune</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/end-user-educate)
 
## <a name="results-of-step-3"></a><span data-ttu-id="c2115-157">Resultaten van stap 3</span><span class="sxs-lookup"><span data-stu-id="c2115-157">Results of Step 3</span></span>

<span data-ttu-id="c2115-158">U gebruikt de reeks functies en mogelijkheden van Endpoint Manager om mobiele apparaten, desktopcomputers, virtuele machines, embedded apparaten en servers te beheren.</span><span class="sxs-lookup"><span data-stu-id="c2115-158">You are using the suite of Endpoint Manager features and capabilities to manage mobile devices, desktop computers, virtual machines, embedded devices, and servers.</span></span>

## <a name="next-step"></a><span data-ttu-id="c2115-159">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c2115-159">Next step</span></span>

<span data-ttu-id="c2115-160">Ga verder met [stap 5](empower-people-to-work-remotely-teams-productivity-apps.md) om te zorgen dat externe werknemers productiviteits-apps voor Microsoft 365 gaan gebruiken, zoals Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c2115-160">Continue with [Step 5](empower-people-to-work-remotely-teams-productivity-apps.md) to get your remote workers using Microsoft 365 productivity apps such as Microsoft Teams.</span></span>
