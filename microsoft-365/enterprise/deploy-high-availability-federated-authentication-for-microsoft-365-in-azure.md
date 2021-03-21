---
title: Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150s
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_Solutions
ms.assetid: 34b1ab9c-814c-434d-8fd0-e5a82cd9bff6
description: 'Overzicht: Configureer federatief hoge beschikbaarheidsverificatie voor uw Microsoft 365-abonnement in Microsoft Azure.'
ms.openlocfilehash: 3989ebb06b4ac5dfa1cded5e07c086c4778f94e7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919150"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="c34d4-103">Federatieverificatie met hoge beschikbaarheid implementeren voor Microsoft 365 in Azure</span><span class="sxs-lookup"><span data-stu-id="c34d4-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="c34d4-104">Dit artikel bevat koppelingen naar de stapsgewijs instructies voor het implementeren van federatieverificatie met hoge beschikbaarheid voor Microsoft Microsoft 365 in Azure-infrastructuurservices met deze virtuele machines:</span><span class="sxs-lookup"><span data-stu-id="c34d4-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="c34d4-105">Twee proxyservers voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="c34d4-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="c34d4-106">Twee Ad FS-servers (Active Directory Federation Services)</span><span class="sxs-lookup"><span data-stu-id="c34d4-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="c34d4-107">Twee replicadomeincontrollers</span><span class="sxs-lookup"><span data-stu-id="c34d4-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="c34d4-108">Eén adreslijstsynchronisatieserver met Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c34d4-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="c34d4-109">Hier is de configuratie, met namen van tijdelijke aanduidingen voor elke server.</span><span class="sxs-lookup"><span data-stu-id="c34d4-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="c34d4-110">**Een federatief hoge beschikbaarheid voor Microsoft 365-infrastructuur in Azure**</span><span class="sxs-lookup"><span data-stu-id="c34d4-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![De uiteindelijke configuratie van de microsoft 365 federatie-infrastructuur voor federatieverificatie met hoge beschikbaarheid in Azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="c34d4-112">Alle virtuele machines maken deel uit van één lokaal virtueel Azure-netwerk (VNet).</span><span class="sxs-lookup"><span data-stu-id="c34d4-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c34d4-113">Federatief verificatie van afzonderlijke gebruikers is niet afhankelijk van on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="c34d4-113">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="c34d4-114">Als de cross-premises verbinding echter niet beschikbaar wordt, ontvangen de domeincontrollers in het VNet geen updates voor gebruikersaccounts en groepen die zijn gemaakt in de on-premises Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="c34d4-114">However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="c34d4-115">Om ervoor te zorgen dat dit niet gebeurt, kunt u een hoge beschikbaarheid configureren voor uw cross-premises verbinding.</span><span class="sxs-lookup"><span data-stu-id="c34d4-115">To ensure this does not happen, you can configure high availability for your cross-premises connection.</span></span> <span data-ttu-id="c34d4-116">Zie Zeer beschikbare [cross-premises en VNet-to-VNet-connectiviteit](/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c34d4-116">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="c34d4-117">Elk paar virtuele machines voor een specifieke rol heeft een eigen subnet en beschikbaarheidsset.</span><span class="sxs-lookup"><span data-stu-id="c34d4-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c34d4-118">Omdat dit VNet is verbonden met het on-premises netwerk, bevat deze configuratie geen jumpbox of het bewaken van virtuele machines op een beheerssubnet.</span><span class="sxs-lookup"><span data-stu-id="c34d4-118">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet.</span></span> <span data-ttu-id="c34d4-119">Zie Windows [VM's uitvoeren voor een N-tier-architectuur](/azure/guidance/guidance-compute-n-tier-vm)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c34d4-119">For more information, see [Running Windows VMs for an N-tier architecture](/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="c34d4-120">Het resultaat van deze configuratie is dat u federatief verificatie hebt voor al uw Microsoft 365-gebruikers, waarin ze hun AD DS-referenties kunnen gebruiken om zich aan te melden in plaats van hun Microsoft 365-account.</span><span class="sxs-lookup"><span data-stu-id="c34d4-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="c34d4-121">De federatief verificatie-infrastructuur maakt gebruik van een redundante set servers die gemakkelijker kunnen worden geïmplementeerd in Azure-infrastructuurservices, in plaats van in uw on-premises edge-netwerk.</span><span class="sxs-lookup"><span data-stu-id="c34d4-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="c34d4-122">Factuur van materialen</span><span class="sxs-lookup"><span data-stu-id="c34d4-122">Bill of materials</span></span>

<span data-ttu-id="c34d4-123">Voor deze basislijnconfiguratie is de volgende set Azure-services en -onderdelen vereist:</span><span class="sxs-lookup"><span data-stu-id="c34d4-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="c34d4-124">Zeven virtuele machines</span><span class="sxs-lookup"><span data-stu-id="c34d4-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="c34d4-125">Eén cross-premises virtueel netwerk met vier subnetten</span><span class="sxs-lookup"><span data-stu-id="c34d4-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="c34d4-126">Vier resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="c34d4-126">Four resource groups</span></span>
    
- <span data-ttu-id="c34d4-127">Drie beschikbaarheidssets</span><span class="sxs-lookup"><span data-stu-id="c34d4-127">Three availability sets</span></span>
    
- <span data-ttu-id="c34d4-128">Eén Azure-abonnement</span><span class="sxs-lookup"><span data-stu-id="c34d4-128">One Azure subscription</span></span>
    
<span data-ttu-id="c34d4-129">Hier zijn de virtuele machines en de standaardgrootten voor deze configuratie.</span><span class="sxs-lookup"><span data-stu-id="c34d4-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="c34d4-130">**Item**</span><span class="sxs-lookup"><span data-stu-id="c34d4-130">**Item**</span></span>|<span data-ttu-id="c34d4-131">**Beschrijving van virtuele machine**</span><span class="sxs-lookup"><span data-stu-id="c34d4-131">**Virtual machine description**</span></span>|<span data-ttu-id="c34d4-132">**Afbeelding van azuregalerie**</span><span class="sxs-lookup"><span data-stu-id="c34d4-132">**Azure gallery image**</span></span>|<span data-ttu-id="c34d4-133">**Standaardgrootte**</span><span class="sxs-lookup"><span data-stu-id="c34d4-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c34d4-134">1.</span><span class="sxs-lookup"><span data-stu-id="c34d4-134">1.</span></span>  <br/> |<span data-ttu-id="c34d4-135">Eerste domeincontroller</span><span class="sxs-lookup"><span data-stu-id="c34d4-135">First domain controller</span></span>  <br/> |<span data-ttu-id="c34d4-136">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-137">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-137">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-138">2.</span><span class="sxs-lookup"><span data-stu-id="c34d4-138">2.</span></span>  <br/> |<span data-ttu-id="c34d4-139">Tweede domeincontroller</span><span class="sxs-lookup"><span data-stu-id="c34d4-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="c34d4-140">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-141">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-141">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-142">3.</span><span class="sxs-lookup"><span data-stu-id="c34d4-142">3.</span></span>  <br/> |<span data-ttu-id="c34d4-143">Azure AD Connect-server</span><span class="sxs-lookup"><span data-stu-id="c34d4-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="c34d4-144">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-145">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-145">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-146">4.</span><span class="sxs-lookup"><span data-stu-id="c34d4-146">4.</span></span>  <br/> |<span data-ttu-id="c34d4-147">Eerste AD FS-server</span><span class="sxs-lookup"><span data-stu-id="c34d4-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="c34d4-148">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-149">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-149">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-150">5.</span><span class="sxs-lookup"><span data-stu-id="c34d4-150">5.</span></span>  <br/> |<span data-ttu-id="c34d4-151">Tweede AD FS-server</span><span class="sxs-lookup"><span data-stu-id="c34d4-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="c34d4-152">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-153">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-153">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-154">6.</span><span class="sxs-lookup"><span data-stu-id="c34d4-154">6.</span></span>  <br/> |<span data-ttu-id="c34d4-155">Eerste proxyserver voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="c34d4-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="c34d4-156">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-157">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-157">D2</span></span>  <br/> |
|<span data-ttu-id="c34d4-158">7.</span><span class="sxs-lookup"><span data-stu-id="c34d4-158">7.</span></span>  <br/> |<span data-ttu-id="c34d4-159">Tweede proxyserver voor webtoepassing</span><span class="sxs-lookup"><span data-stu-id="c34d4-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="c34d4-160">Windows Server 2016 Datacenter</span><span class="sxs-lookup"><span data-stu-id="c34d4-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="c34d4-161">D2</span><span class="sxs-lookup"><span data-stu-id="c34d4-161">D2</span></span>  <br/> |
   
<span data-ttu-id="c34d4-162">Als u de geschatte kosten voor deze configuratie wilt berekenen, bekijkt u de [Azure-prijsberekening](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="c34d4-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="c34d4-163">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="c34d4-163">Phases of deployment</span></span>

<span data-ttu-id="c34d4-164">U implementeert deze werkbelasting in de volgende fasen:</span><span class="sxs-lookup"><span data-stu-id="c34d4-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="c34d4-165">[Fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="c34d4-165">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> <span data-ttu-id="c34d4-166">Maak resourcegroepen, opslagaccounts, beschikbaarheidssets en een cross-premises virtueel netwerk.</span><span class="sxs-lookup"><span data-stu-id="c34d4-166">Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="c34d4-167">[Fase 2: Domeincontrollers configureren.](high-availability-federated-authentication-phase-2-configure-domain-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="c34d4-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="c34d4-168">Maak en configureer replica AD DS-domeincontrollers en de adreslijstsynchronisatieserver.</span><span class="sxs-lookup"><span data-stu-id="c34d4-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="c34d4-169">[Fase 3: AD FS-servers configureren.](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md)</span><span class="sxs-lookup"><span data-stu-id="c34d4-169">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="c34d4-170">Maak en configureer de twee AD FS-servers.</span><span class="sxs-lookup"><span data-stu-id="c34d4-170">Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="c34d4-171">[Fase 4: Webtoepassingsproxies configureren.](high-availability-federated-authentication-phase-4-configure-web-application-pro.md)</span><span class="sxs-lookup"><span data-stu-id="c34d4-171">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="c34d4-172">De twee proxyservers voor webtoepassing maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="c34d4-172">Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="c34d4-173">[Fase 5: Federatief verificatie configureren voor Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="c34d4-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="c34d4-174">Federatief verificatie configureren voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="c34d4-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="c34d4-175">Deze artikelen bevatten een prescriptieve, fase-voor-fase-handleiding voor een vooraf gedefinieerde architectuur om een functionele federatieve verificatie met hoge beschikbaarheid te maken voor Microsoft 365 in Azure-infrastructuurservices.</span><span class="sxs-lookup"><span data-stu-id="c34d4-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="c34d4-176">Houd het volgende in gedachten:</span><span class="sxs-lookup"><span data-stu-id="c34d4-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="c34d4-177">Als u een ervaren AD FS-implementer bent, kunt u de instructies in fasen 3 en 4 aanpassen en de set servers maken die het beste bij uw behoeften passen.</span><span class="sxs-lookup"><span data-stu-id="c34d4-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="c34d4-178">Als u al een bestaande hybride Azure-cloudimplementatie met een bestaand cross-premises virtueel netwerk hebt, kunt u de instructies in fasen 1 en 2 aanpassen of overslaan en de proxyservers voor AD FS en webtoepassing op de juiste subnetten plaatsen.</span><span class="sxs-lookup"><span data-stu-id="c34d4-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="c34d4-179">Zie Federatief identiteit voor uw [Microsoft 365-dev-/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)voor het bouwen van een dev/testomgeving of een proof-of-concept van deze configuratie.</span><span class="sxs-lookup"><span data-stu-id="c34d4-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="c34d4-180">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="c34d4-180">Next step</span></span>

<span data-ttu-id="c34d4-181">Start de configuratie van deze werkbelasting met [Fase 1: Azure configureren.](high-availability-federated-authentication-phase-1-configure-azure.md)</span><span class="sxs-lookup"><span data-stu-id="c34d4-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
