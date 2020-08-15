---
title: Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure
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
description: 'Overzicht: Configureer federatieve authenticatie van hoge beschikbaarheid voor uw Microsoft 365-abonnement in Microsoft Azure.'
ms.openlocfilehash: abe01445b8963dcdc5693b45a680e273f5084446
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689315"
---
# <a name="deploy-high-availability-federated-authentication-for-microsoft-365-in-azure"></a><span data-ttu-id="3cb3a-103">Federatieve authenticatie van hoge beschikbaarheid implementeren voor Microsoft 365 in azure</span><span class="sxs-lookup"><span data-stu-id="3cb3a-103">Deploy high availability federated authentication for Microsoft 365 in Azure</span></span>

<span data-ttu-id="3cb3a-104">Dit artikel bevat koppelingen naar de stapsgewijze instructies voor de implementatie van federatieve authenticatie van hoge beschikbaarheid voor Microsoft Microsoft 365 in azure-infrastructuurservices met deze virtuele machines:</span><span class="sxs-lookup"><span data-stu-id="3cb3a-104">This article has links to the step-by-step instructions for deploying high availability federated authentication for Microsoft Microsoft 365 in Azure infrastructure services with these virtual machines:</span></span>
  
- <span data-ttu-id="3cb3a-105">Twee toepassingen voor webtoepassingsproxy</span><span class="sxs-lookup"><span data-stu-id="3cb3a-105">Two web application proxy servers</span></span>
    
- <span data-ttu-id="3cb3a-106">Twee servers met Active Directory Federation Services (AD FS)</span><span class="sxs-lookup"><span data-stu-id="3cb3a-106">Two Active Directory Federation Services (AD FS) servers</span></span>
    
- <span data-ttu-id="3cb3a-107">Twee replica domeincontrollers</span><span class="sxs-lookup"><span data-stu-id="3cb3a-107">Two replica domain controllers</span></span>
    
- <span data-ttu-id="3cb3a-108">Eén adreslijstsynchronisatie server met Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="3cb3a-108">One directory synchronization server running Azure AD Connect</span></span>
    
<span data-ttu-id="3cb3a-109">De configuratie bevat de naam van een tijdelijke aanduiding voor elke server.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-109">Here is the configuration, with placeholder names for each server.</span></span>
  
<span data-ttu-id="3cb3a-110">**Een federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365-infrastructuur in azure**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-110">**A high availability federated authentication for Microsoft 365 infrastructure in Azure**</span></span>

![De laatste configuratie van de High Availability Microsoft 365 federatieve verificatie-infrastructuur in azure](../media/c5da470a-f2aa-489a-a050-df09b4d641df.png)
  
<span data-ttu-id="3cb3a-112">Alle virtuele machines bevinden zich in één cross-premises Azure Virtual Network (VNet).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-112">All of the virtual machines are in a single cross-premises Azure virtual network (VNet).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3cb3a-113">Federatieve verificatie van afzonderlijke gebruikers is niet afhankelijk van lokale on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-113">Federated authentication of individual users does not rely on any on-premises resources.</span></span> <span data-ttu-id="3cb3a-114">Als de cross-premises verbinding echter niet meer beschikbaar is, ontvangen de domeincontrollers in de VNet geen updates voor gebruikersaccounts en groepen die zijn opgenomen in de on-premises Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-114">However, if the cross-premises connection becomes unavailable, the domain controllers in the VNet will not receive updates to user accounts and groups made in the on-premises Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3cb3a-115">U kunt ervoor zorgen dat dit niet gebeurt door de hoge beschikbaarheid van uw cross-premises verbinding te configureren.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-115">To ensure this does not happen, you can configure high availability for your cross-premises connection.</span></span> <span data-ttu-id="3cb3a-116">Zie [uiterst beschikbare cross-premises en vnet-to-VNet-verbinding](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-116">For more information, see [Highly Available Cross-Premises and VNet-to-VNet Connectivity](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-highlyavailable)</span></span>
  
<span data-ttu-id="3cb3a-117">Elke reeks virtuele machines voor een bepaalde rol bevindt zich in zijn eigen subnet en de beschikbaarheid.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-117">Each pair of virtual machines for a specific role is in its own subnet and availability set.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3cb3a-118">Aangezien dit VNet is verbonden met het on-premises netwerk, bevat deze configuratie geen JumpBox of virtuele machines op een management subnet.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-118">Because this VNet is connected to the on-premises network, this configuration does not include jumpbox or monitoring virtual machines on a management subnet.</span></span> <span data-ttu-id="3cb3a-119">Zie [Windows Vm's uitvoeren voor een architectuur met een N-tier](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-119">For more information, see [Running Windows VMs for an N-tier architecture](https://docs.microsoft.com/azure/guidance/guidance-compute-n-tier-vm).</span></span> 
  
<span data-ttu-id="3cb3a-120">Het resultaat van deze configuratie is dat u Federatie authenticatie onderneemt voor alle Microsoft 365-gebruikers, waarbij ze hun AD DS-referenties kunnen gebruiken om zich aan te melden in plaats van hun Microsoft 365-account.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-120">The result of this configuration is that you will have federated authentication for all of your Microsoft 365 users, in which they can use their AD DS credentials to sign in rather than their Microsoft 365 account.</span></span> <span data-ttu-id="3cb3a-121">De federatieve verificatie-infrastructuur gebruikt een redundante set servers die eenvoudiger in azure-infrastructuurservices kunnen worden geïmplementeerd, in plaats van in het on-premises Edge-netwerk.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-121">The federated authentication infrastructure uses a redundant set of servers that are more easily deployed in Azure infrastructure services, rather than in your on-premises edge network.</span></span>
  
## <a name="bill-of-materials"></a><span data-ttu-id="3cb3a-122">Stuklijsten</span><span class="sxs-lookup"><span data-stu-id="3cb3a-122">Bill of materials</span></span>

<span data-ttu-id="3cb3a-123">Voor deze basislijn configuratie is de volgende set Azure-Services en-onderdelen vereist:</span><span class="sxs-lookup"><span data-stu-id="3cb3a-123">This baseline configuration requires the following set of Azure services and components:</span></span>
  
- <span data-ttu-id="3cb3a-124">Zeven virtuele machines</span><span class="sxs-lookup"><span data-stu-id="3cb3a-124">Seven virtual machines</span></span>
    
- <span data-ttu-id="3cb3a-125">Eén cross-premises virtueel netwerk met vier subnetten</span><span class="sxs-lookup"><span data-stu-id="3cb3a-125">One cross-premises virtual network with four subnets</span></span>
    
- <span data-ttu-id="3cb3a-126">Vier resourcegroepen</span><span class="sxs-lookup"><span data-stu-id="3cb3a-126">Four resource groups</span></span>
    
- <span data-ttu-id="3cb3a-127">Drie beschikbare sets</span><span class="sxs-lookup"><span data-stu-id="3cb3a-127">Three availability sets</span></span>
    
- <span data-ttu-id="3cb3a-128">Eén Azure-abonnement</span><span class="sxs-lookup"><span data-stu-id="3cb3a-128">One Azure subscription</span></span>
    
<span data-ttu-id="3cb3a-129">Dit zijn de virtuele machines en de standaardformaten voor deze configuratie.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-129">Here are the virtual machines and their default sizes for this configuration.</span></span>
  
|<span data-ttu-id="3cb3a-130">**Item**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-130">**Item**</span></span>|<span data-ttu-id="3cb3a-131">**Beschrijving van virtuele machine**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-131">**Virtual machine description**</span></span>|<span data-ttu-id="3cb3a-132">**Afbeelding van Azure-galerie**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-132">**Azure gallery image**</span></span>|<span data-ttu-id="3cb3a-133">**Standaardgrootte**</span><span class="sxs-lookup"><span data-stu-id="3cb3a-133">**Default size**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3cb3a-134">1.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-134">1.</span></span>  <br/> |<span data-ttu-id="3cb3a-135">Eerste domeincontroller</span><span class="sxs-lookup"><span data-stu-id="3cb3a-135">First domain controller</span></span>  <br/> |<span data-ttu-id="3cb3a-136">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-136">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-137">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-137">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-138">2.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-138">2.</span></span>  <br/> |<span data-ttu-id="3cb3a-139">Tweede domeincontroller</span><span class="sxs-lookup"><span data-stu-id="3cb3a-139">Second domain controller</span></span>  <br/> |<span data-ttu-id="3cb3a-140">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-140">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-141">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-141">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-142">3.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-142">3.</span></span>  <br/> |<span data-ttu-id="3cb3a-143">Azure AD Connect-server</span><span class="sxs-lookup"><span data-stu-id="3cb3a-143">Azure AD Connect server</span></span>  <br/> |<span data-ttu-id="3cb3a-144">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-144">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-145">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-145">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-146">4.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-146">4.</span></span>  <br/> |<span data-ttu-id="3cb3a-147">Eerste AD FS-server</span><span class="sxs-lookup"><span data-stu-id="3cb3a-147">First AD FS server</span></span>  <br/> |<span data-ttu-id="3cb3a-148">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-148">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-149">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-149">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-150">5.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-150">5.</span></span>  <br/> |<span data-ttu-id="3cb3a-151">Tweede AD FS-server</span><span class="sxs-lookup"><span data-stu-id="3cb3a-151">Second AD FS server</span></span>  <br/> |<span data-ttu-id="3cb3a-152">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-152">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-153">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-153">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-154">zes.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-154">6.</span></span>  <br/> |<span data-ttu-id="3cb3a-155">Eerste proxyserver voor webtoepassingen</span><span class="sxs-lookup"><span data-stu-id="3cb3a-155">First web application proxy server</span></span>  <br/> |<span data-ttu-id="3cb3a-156">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-156">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-157">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-157">D2</span></span>  <br/> |
|<span data-ttu-id="3cb3a-158">7,5.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-158">7.</span></span>  <br/> |<span data-ttu-id="3cb3a-159">Tweede toepassing voor webtoepassingsproxy</span><span class="sxs-lookup"><span data-stu-id="3cb3a-159">Second web application proxy server</span></span>  <br/> |<span data-ttu-id="3cb3a-160">Windows Server 2016 datacenter</span><span class="sxs-lookup"><span data-stu-id="3cb3a-160">Windows Server 2016 Datacenter</span></span>  <br/> |<span data-ttu-id="3cb3a-161">Hetzelfde</span><span class="sxs-lookup"><span data-stu-id="3cb3a-161">D2</span></span>  <br/> |
   
<span data-ttu-id="3cb3a-162">Als u de geraamde kosten voor deze configuratie wilt berekenen, raadpleegt u de [Azure tarief berekening](https://azure.microsoft.com/pricing/calculator/)</span><span class="sxs-lookup"><span data-stu-id="3cb3a-162">To compute the estimated costs for this configuration, see the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/)</span></span>
  
## <a name="phases-of-deployment"></a><span data-ttu-id="3cb3a-163">Implementatiefasen</span><span class="sxs-lookup"><span data-stu-id="3cb3a-163">Phases of deployment</span></span>

<span data-ttu-id="3cb3a-164">U voert de volgende stappen uit om deze werkbelasting te implementeren:</span><span class="sxs-lookup"><span data-stu-id="3cb3a-164">You deploy this workload in the following phases:</span></span>
  
- <span data-ttu-id="3cb3a-165">[Fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-165">[Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> <span data-ttu-id="3cb3a-166">Maak bronnengroepen, opslagaccounts, beschikbaarheidssets en een virtueel netwerk voor cross-premises.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-166">Create resource groups, storage accounts, availability sets, and a cross-premises virtual network.</span></span>
    
- <span data-ttu-id="3cb3a-167">[Fase 2: configureer domeincontrollers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-167">[Phase 2: Configure domain controllers](high-availability-federated-authentication-phase-2-configure-domain-controllers.md).</span></span> <span data-ttu-id="3cb3a-168">Maak en configureer domeincontrollers voor de AD DS van de replica en de adreslijstsynchronisatie server.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-168">Create and configure replica AD DS domain controllers and the directory synchronization server.</span></span>
    
- <span data-ttu-id="3cb3a-169">[Fase 3: AD FS-servers configureren](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-169">[Phase 3: Configure AD FS servers](high-availability-federated-authentication-phase-3-configure-ad-fs-servers.md).</span></span> <span data-ttu-id="3cb3a-170">De twee AD FS-servers maken en configureren.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-170">Create and configure the two AD FS servers.</span></span>
    
- <span data-ttu-id="3cb3a-171">[Fase 4: proxy's voor webtoepassingen configureren](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-171">[Phase 4: Configure web application proxies](high-availability-federated-authentication-phase-4-configure-web-application-pro.md).</span></span> <span data-ttu-id="3cb3a-172">Maak en configureer de twee webtoepassings proxyservers.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-172">Create and configure the two web application proxy servers.</span></span>
    
- <span data-ttu-id="3cb3a-173">[Fase 5: federatieve verificatie voor Microsoft 365 configureren](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-173">[Phase 5: Configure federated authentication for Microsoft 365](high-availability-federated-authentication-phase-5-configure-federated-authentic.md).</span></span> <span data-ttu-id="3cb3a-174">Configureer federatieve verificatie voor uw Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-174">Configure federated authentication for your Microsoft 365 subscription.</span></span>
    
<span data-ttu-id="3cb3a-175">In deze artikelen vindt u een uitgebreide, fase-phase handleiding voor een vooraf gedefinieerde architectuur voor het maken van een functionele, federatieve authenticatie van hoge beschikbaarheid voor Microsoft 365 in azure-infrastructuurservices.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-175">These articles provide a prescriptive, phase-by-phase guide for a predefined architecture to create a functional, high availability federated authentication for Microsoft 365 in Azure infrastructure services.</span></span> <span data-ttu-id="3cb3a-176">Houd het volgende in gedachten:</span><span class="sxs-lookup"><span data-stu-id="3cb3a-176">Keep the following in mind:</span></span>
  
- <span data-ttu-id="3cb3a-177">Als u een ervaring hebt met de implementatie van AD FS, kunt u de instructies in de fasen 3 en 4 aanpassen en de sets servers maken die het beste aansluit bij uw behoeften.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-177">If you are an experienced AD FS implementer, feel free to adapt the instructions in phases 3 and 4 and build the set of servers that best suits your needs.</span></span>
    
- <span data-ttu-id="3cb3a-178">Als u al een Azure Hybrid Cloud-implementatie met een bestaand cross-premises virtueel netwerk hebt, kunt u de instructies in de fase 1 en 2 overslaan en overslaan en de proxyservers voor de AD FS-en webtoepassingsproxy-toepassing op de juiste subnetten plaatsen.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-178">If you already have an existing Azure hybrid cloud deployment with an existing cross-premises virtual network, feel free to adapt or skip the instructions in phases 1 and 2 and place the AD FS and web application proxy servers on the appropriate subnets.</span></span>
    
<span data-ttu-id="3cb3a-179">Zie [federatieve identiteit voor uw Microsoft 365 dev/testomgeving](federated-identity-for-your-microsoft-365-dev-test-environment.md)als u een ontwikkelaar/testomgeving of een controle van het concept van deze configuratie wilt maken.</span><span class="sxs-lookup"><span data-stu-id="3cb3a-179">To build a dev/test environment or a proof-of-concept of this configuration, see [Federated identity for your Microsoft 365 dev/test environment](federated-identity-for-your-microsoft-365-dev-test-environment.md).</span></span>
  
## <a name="next-step"></a><span data-ttu-id="3cb3a-180">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="3cb3a-180">Next step</span></span>

<span data-ttu-id="3cb3a-181">Start de configuratie van deze werkbelasting met [fase 1: Azure configureren](high-availability-federated-authentication-phase-1-configure-azure.md).</span><span class="sxs-lookup"><span data-stu-id="3cb3a-181">Start the configuration of this workload with [Phase 1: Configure Azure](high-availability-federated-authentication-phase-1-configure-azure.md).</span></span> 
  
