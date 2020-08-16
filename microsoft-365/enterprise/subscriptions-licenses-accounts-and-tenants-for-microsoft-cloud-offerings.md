---
title: Abonnementen, licenties, accounts en tenants voor cloudaanbiedingen van Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/25/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.assetid: c720cffc-f9b5-4f43-9100-422f86a1027c
ms.custom:
- seo-marvel-apr2020
- Ent_Architecture
description: Begrijp de relaties tussen organisaties, abonnementen, licenties, gebruikersaccounts en tenants in cloudaanbiedingen van Microsoft.
ms.openlocfilehash: 7b19c2d6a870f53642d37ee98276f7b6a9e1febf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689067"
---
# <a name="subscriptions-licenses-accounts-and-tenants-for-microsofts-cloud-offerings"></a><span data-ttu-id="93f36-103">Abonnementen, licenties, accounts en tenants voor cloudaanbiedingen van Microsoft</span><span class="sxs-lookup"><span data-stu-id="93f36-103">Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings</span></span>

<span data-ttu-id="93f36-104">Microsoft biedt een hiërarchie van organisaties, abonnementen, licenties en gebruikersaccounts voor een consistent gebruik van identiteiten en facturering voor de Cloud-aanbiedingen:</span><span class="sxs-lookup"><span data-stu-id="93f36-104">Microsoft provides a hierarchy of organizations, subscriptions, licenses, and user accounts for consistent use of identities and billing across its cloud offerings:</span></span>
  
- <span data-ttu-id="93f36-105">Microsoft 365 en Microsoft Office 365</span><span class="sxs-lookup"><span data-stu-id="93f36-105">Microsoft 365 and Microsoft Office 365</span></span>
- <span data-ttu-id="93f36-106">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="93f36-106">Microsoft Azure</span></span>
- <span data-ttu-id="93f36-107">Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="93f36-107">Microsoft Dynamics 365</span></span>

## <a name="elements-of-the-hierarchy"></a><span data-ttu-id="93f36-108">Elementen van de hiërarchie</span><span class="sxs-lookup"><span data-stu-id="93f36-108">Elements of the hierarchy</span></span>

<span data-ttu-id="93f36-109">Dit zijn de elementen van de hiërarchie:</span><span class="sxs-lookup"><span data-stu-id="93f36-109">Here are the elements of the hierarchy:</span></span>
  
### <a name="organization"></a><span data-ttu-id="93f36-110">Organisatie</span><span class="sxs-lookup"><span data-stu-id="93f36-110">Organization</span></span>

<span data-ttu-id="93f36-111">Een organisatie vertegenwoordigt een zakelijke entiteit die gebruikmaakt van Microsoft-Cloud aanbiedingen, meestal aangeduid door een of meer DNS-domeinnamen (openbare DNS), zoals contoso.com.</span><span class="sxs-lookup"><span data-stu-id="93f36-111">An organization represents a business entity that is using Microsoft cloud offerings, typically identified by one or more public Domain Name System (DNS) domain names, such as contoso.com.</span></span> <span data-ttu-id="93f36-112">De organisatie is een container voor abonnementen.</span><span class="sxs-lookup"><span data-stu-id="93f36-112">The organization is a container for subscriptions.</span></span>
  
### <a name="subscriptions"></a><span data-ttu-id="93f36-113">Abonnementen</span><span class="sxs-lookup"><span data-stu-id="93f36-113">Subscriptions</span></span>

<span data-ttu-id="93f36-114">Een-abonnement is een overeenkomst met Microsoft voor het gebruik van een of meer Microsoft cloudplatformen of-services, waarvoor kosten worden berekend op basis van licentiekosten per gebruiker of op het resourceverbruik op de Cloud.</span><span class="sxs-lookup"><span data-stu-id="93f36-114">A subscription is an agreement with Microsoft to use one or more Microsoft cloud platforms or services, for which charges accrue based on either a per-user license fee or on cloud-based resource consumption.</span></span> 

- <span data-ttu-id="93f36-115">Software van Microsoft als een service (SaaS)-cloudaanbieding (Microsoft 365 en Dynamics 365) brengt licentiekosten per gebruiker in rekening.</span><span class="sxs-lookup"><span data-stu-id="93f36-115">Microsoft's Software as a Service (SaaS)-based cloud offerings (Microsoft 365 and Dynamics 365) charge per-user license fees.</span></span> 
- <span data-ttu-id="93f36-116">Het platform van Microsoft als een service (PaaS) en infrastructuur als service (IaaS)-Cloud-aanbiedingen (Azure) op basis van het verbruik van de cloudresource.</span><span class="sxs-lookup"><span data-stu-id="93f36-116">Microsoft's Platform as a Service (PaaS) and Infrastructure as a Service (IaaS) cloud offerings (Azure) charge based on cloud resource consumption.</span></span>
 
<span data-ttu-id="93f36-117">U kunt ook een proefabonnement gebruiken, maar het abonnement verloopt na een bepaalde tijd of verbruikte kosten.</span><span class="sxs-lookup"><span data-stu-id="93f36-117">You can also use a trial subscription, but the subscription expires after a specific amount of time or consumption charges.</span></span> <span data-ttu-id="93f36-118">U kunt een proefabonnement omzetten naar een betaald abonnement.</span><span class="sxs-lookup"><span data-stu-id="93f36-118">You can convert a trial subscription to a paid subscription.</span></span>
  
<span data-ttu-id="93f36-119">Organisaties kunnen meerdere abonnementen hebben voor de cloud van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="93f36-119">Organizations can have multiple subscriptions for Microsoft's cloud offerings.</span></span> <span data-ttu-id="93f36-120">Afbeelding 1 toont één organisatie met meerdere Microsoft 365-abonnementen, een Dynamics 365-abonnement en meerdere Azure-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="93f36-120">Figure 1 shows a single organization that has multiple Microsoft 365 subscriptions, a Dynamics 365 subscription, and multiple Azure subscriptions.</span></span>

<span data-ttu-id="93f36-121">**Afbeelding 1: voorbeeld van meerdere abonnementen voor een organisatie**</span><span class="sxs-lookup"><span data-stu-id="93f36-121">**Figure 1: Example of multiple subscriptions for an organization**</span></span>

![Een voorbeeld organisatie met meerdere abonnementen voor de cloud van Microsoft.](../media/Subscriptions/Subscriptions-Fig1.png)
  
### <a name="licenses"></a><span data-ttu-id="93f36-123">Licenties</span><span class="sxs-lookup"><span data-stu-id="93f36-123">Licenses</span></span>

<span data-ttu-id="93f36-124">Voor Microsoft SaaS-cloudaanbiedingen kan een licentie een specifiek gebruikersaccount gebruiken om de services van de cloud te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93f36-124">For Microsoft's SaaS cloud offerings, a license allows a specific user account to use the services of the cloud offering.</span></span> <span data-ttu-id="93f36-125">Er worden kosten in rekening gebracht als onderdeel van uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="93f36-125">You are charged a fixed monthly fee as part of your subscription.</span></span> <span data-ttu-id="93f36-126">Beheerders kunnen licenties toewijzen aan afzonderlijke gebruikersaccounts in het abonnement.</span><span class="sxs-lookup"><span data-stu-id="93f36-126">Administrators assign licenses to individual user accounts in the subscription.</span></span> <span data-ttu-id="93f36-127">Voor het voorbeeld in afbeelding 2 heeft Contoso Corporation een Microsoft 365 E5-abonnement met 100 licenties, waarmee maximaal 100 afzonderlijke gebruikersaccounts kunnen worden gebruikt voor de functies en services van Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="93f36-127">For the example in Figure 2, the Contoso Corporation has a Microsoft 365 E5 subscription with 100 licenses, which allows to up to 100 individual user accounts to use Microsoft 365 E5 features and services.</span></span>
  
<span data-ttu-id="93f36-128">**Afbeelding 2: licenties in de op SaaS gebaseerde abonnementen voor een organisatie**</span><span class="sxs-lookup"><span data-stu-id="93f36-128">**Figure 2: Licenses within the SaaS-based subscriptions for an organization**</span></span>

![Een voorbeeld van meerdere licenties binnen abonnementen voor de op SaaS gebaseerde cloudaanbiedingen van Microsoft.](../media/Subscriptions/Subscriptions-Fig2.png)
  
<span data-ttu-id="93f36-130">Voor Azure PaaS-cloudservices zijn softwarelicenties ingebouwd in de serviceprijzen.</span><span class="sxs-lookup"><span data-stu-id="93f36-130">For Azure PaaS-based cloud services, software licenses are built into the service pricing.</span></span>
  
<span data-ttu-id="93f36-131">Voor Azure IaaS-virtuele machines zijn er mogelijk extra licenties vereist voor het gebruik van de software of toepassing die op een virtuele machine-afbeelding zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="93f36-131">For Azure IaaS-based virtual machines, additional licenses to use the software or application installed on a virtual machine image might be required.</span></span> <span data-ttu-id="93f36-132">Voor sommige virtuele-machine beelden zijn gelicentieerde versies van software geïnstalleerd en de kosten worden opgenomen in de prijs per minuut voor de server.</span><span class="sxs-lookup"><span data-stu-id="93f36-132">Some virtual machine images have licensed versions of software installed and the cost is included in the per-minute rate for the server.</span></span> <span data-ttu-id="93f36-133">Voorbeelden zijn de virtuele machines voor SQL Server 2014 en SQL Server 2016.</span><span class="sxs-lookup"><span data-stu-id="93f36-133">Examples are the virtual machine images for SQL Server 2014 and SQL Server 2016.</span></span> 
  
<span data-ttu-id="93f36-134">Voor sommige virtuele-machine beelden zijn proefversies van-toepassingen geïnstalleerd en u hebt aanvullende software licenties nodig voor gebruik na de proefperiode.</span><span class="sxs-lookup"><span data-stu-id="93f36-134">Some virtual machine images have trial versions of applications installed and need additional software application licenses for use beyond the trial period.</span></span> <span data-ttu-id="93f36-135">Bijvoorbeeld, de installatiekopie van de evaluatieversie van SharePoint Server 2016 bevat bijvoorbeeld een evaluatieversie van SharePoint Server 2016 vooraf geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="93f36-135">For example, the SharePoint Server 2016 Trial virtual machine image includes a trial version of SharePoint Server 2016 pre-installed.</span></span> <span data-ttu-id="93f36-136">Als u SharePoint Server 2016 wilt blijven gebruiken na de vervaldatum van het proefabonnement, moet u een licentie voor SharePoint Server 2016 en clientlicenties bij Microsoft aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="93f36-136">To continue using SharePoint Server 2016 after the trial expiration date, you must purchase a SharePoint Server 2016 license and client licenses from Microsoft.</span></span> <span data-ttu-id="93f36-137">Deze kosten staan los van het Azure-abonnement en de prijs per minuut voor de virtuele machine is nog steeds van toepassing.</span><span class="sxs-lookup"><span data-stu-id="93f36-137">These charges are separate from the Azure subscription and the per-minute rate to run the virtual machine still applies.</span></span>
  
### <a name="user-accounts"></a><span data-ttu-id="93f36-138">Gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="93f36-138">User accounts</span></span>

<span data-ttu-id="93f36-139">Gebruikersaccounts voor alle cloudaanbiedingen van Microsoft worden opgeslagen in een Azure Active Directory-Tenant (Azure AD) die gebruikersaccounts en groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="93f36-139">User accounts for all of Microsoft's cloud offerings are stored in an Azure Active Directory (Azure AD) tenant, which contains user accounts and groups.</span></span> <span data-ttu-id="93f36-140">Een Azure AD-Tenant kan worden gesynchroniseerd met uw bestaande AD DS-accounts (Active Directory Domain Services) via Azure AD Connect, een Windows Server-service.</span><span class="sxs-lookup"><span data-stu-id="93f36-140">An Azure AD tenant can be synchronized with your existing Active Directory Domain Services (AD DS) accounts using Azure AD Connect, a Windows server-based service.</span></span> <span data-ttu-id="93f36-141">Dit wordt ook wel adreslijstsynchronisatie genoemd.</span><span class="sxs-lookup"><span data-stu-id="93f36-141">This is known as directory synchronization.</span></span>
  
<span data-ttu-id="93f36-142">In afbeelding 3 ziet u een voorbeeld van meerdere abonnementen van een organisatie met een gemeenschappelijke Azure AD-Tenant met de accounts van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-142">Figure 3 shows an example of multiple subscriptions of an organization using a common Azure AD tenant that contains the organization's accounts.</span></span>
  
<span data-ttu-id="93f36-143">**Afbeelding 3: meerdere abonnementen van een organisatie die dezelfde Azure AD-Tenant gebruiken**</span><span class="sxs-lookup"><span data-stu-id="93f36-143">**Figure 3: Multiple subscriptions of an organization that use the same Azure AD tenant**</span></span>

![Een voorbeeld van een organisatie met meerdere abonnementen met dezelfde Azure AD-Tenant.](../media/Subscriptions/Subscriptions-Fig3.png)
  
### <a name="tenants"></a><span data-ttu-id="93f36-145">Tenants</span><span class="sxs-lookup"><span data-stu-id="93f36-145">Tenants</span></span>

<span data-ttu-id="93f36-146">Voor SaaS-cloudaanbiedingen is de tenant de regionale locatie die de servers bevat die cloudservices bieden.</span><span class="sxs-lookup"><span data-stu-id="93f36-146">For SaaS cloud offerings, the tenant is the regional location that houses the servers providing cloud services.</span></span> <span data-ttu-id="93f36-147">Contoso B.V. koos bijvoorbeeld voor de Europese regio om de Microsoft 365, EMS en Dynamics 365 tenants te hosten voor de 15.000-werknemers in hun hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="93f36-147">For example, the Contoso Corporation chose the European region to host its Microsoft 365, EMS, and Dynamics 365 tenants for the 15,000 workers in their Paris headquarters.</span></span>
  
<span data-ttu-id="93f36-148">Azure PaaS-Services en werkbelastingen voor virtuele machines die worden gehost in Azure IaaS kunnen in een Azure-datacenter overal ter wereld zijn.</span><span class="sxs-lookup"><span data-stu-id="93f36-148">Azure PaaS services and virtual machine-based workloads hosted in Azure IaaS can have tenancy in any Azure datacenter across the world.</span></span> <span data-ttu-id="93f36-149">U geeft het Azure-datacenter op dat wordt aangeduid als de locatie, wanneer u de Azure PaaS-app of-service of het element van een IaaS-werkbelasting maakt.</span><span class="sxs-lookup"><span data-stu-id="93f36-149">You specify the Azure datacenter, known as the location, when you create the Azure PaaS app or service or element of an IaaS workload.</span></span>
  
<span data-ttu-id="93f36-150">Een Azure AD-tenant is een specifiek exemplaar van Azure AD dat accounts en groepen bevat.</span><span class="sxs-lookup"><span data-stu-id="93f36-150">An Azure AD tenant is a specific instance of Azure AD containing accounts and groups.</span></span> <span data-ttu-id="93f36-151">Betaalde of proefabonnementen van Microsoft 365 of Dynamics 365 bevatten een gratis Azure AD-Tenant.</span><span class="sxs-lookup"><span data-stu-id="93f36-151">Paid or trial subscriptions of Microsoft 365 or Dynamics 365 include a free Azure AD tenant.</span></span> <span data-ttu-id="93f36-152">De Azure AD-tenant omvat geen andere Azure-Services en is niet hetzelfde als een (proef)abonnement van Azure.</span><span class="sxs-lookup"><span data-stu-id="93f36-152">This Azure AD tenant does not include other Azure services and is not the same as an Azure trial or paid subscription.</span></span>
  
### <a name="summary-of-the-hierarchy"></a><span data-ttu-id="93f36-153">Samenvatting van de hiërarchie</span><span class="sxs-lookup"><span data-stu-id="93f36-153">Summary of the hierarchy</span></span>

<span data-ttu-id="93f36-154">Dit is een snelle samenvatting:</span><span class="sxs-lookup"><span data-stu-id="93f36-154">Here is a quick recap:</span></span>
  
- <span data-ttu-id="93f36-155">Een organisatie kan meerdere abonnementen hebben.</span><span class="sxs-lookup"><span data-stu-id="93f36-155">An organization can have multiple subscriptions</span></span>
    
  - <span data-ttu-id="93f36-156">Een abonnement kan meerdere licenties hebben</span><span class="sxs-lookup"><span data-stu-id="93f36-156">A subscription can have multiple licenses</span></span>
    
  - <span data-ttu-id="93f36-157">U kunt licenties toewijzen aan afzonderlijke gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="93f36-157">Licenses can be assigned to individual user accounts</span></span>
    
  - <span data-ttu-id="93f36-158">Gebruikersaccounts worden opgeslagen in een Azure AD-tenant</span><span class="sxs-lookup"><span data-stu-id="93f36-158">User accounts are stored in an Azure AD tenant</span></span>
    
<span data-ttu-id="93f36-159">Hieronder ziet u een voorbeeld van de relatie tussen organisaties, abonnementen, licenties en gebruikersaccounts:</span><span class="sxs-lookup"><span data-stu-id="93f36-159">Here is an example of the relationship of organizations, subscriptions, licenses, and user accounts:</span></span>
  
- <span data-ttu-id="93f36-160">Een organisatie die is geïdentificeerd met de openbare domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="93f36-160">An organization identified by its public domain name.</span></span>
    
  - <span data-ttu-id="93f36-161">Een Microsoft 365 E3-abonnement met gebruikerslicenties.</span><span class="sxs-lookup"><span data-stu-id="93f36-161">A Microsoft 365 E3 subscription with user licenses.</span></span>
    
    <span data-ttu-id="93f36-162">Een Microsoft 365 E5-abonnement met gebruikerslicenties.</span><span class="sxs-lookup"><span data-stu-id="93f36-162">A Microsoft 365 E5 subscription with user licenses.</span></span>
    
    <span data-ttu-id="93f36-163">Een Microsoft 365 abonnement met gebruikerslicenties.</span><span class="sxs-lookup"><span data-stu-id="93f36-163">A Dynamics 365 subscription with user licenses.</span></span>
    
    <span data-ttu-id="93f36-164">Meerdere Azure abonnementen.</span><span class="sxs-lookup"><span data-stu-id="93f36-164">Multiple Azure subscriptions.</span></span>
    
  - <span data-ttu-id="93f36-165">De gebruikersaccounts van de organisatie in een gemeenschappelijke Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="93f36-165">The organization's user accounts in a common Azure AD tenant.</span></span>
    
<span data-ttu-id="93f36-166">Voor meerdere Microsoft cloudabonnementen kan dezelfde Azure AD-tenant worden gebruikt als voor een algemene identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="93f36-166">Multiple Microsoft cloud offering subscriptions can use the same Azure AD tenant that acts as a common identity provider.</span></span> <span data-ttu-id="93f36-167">Een centraal Azure AD-tenant met de gesynchroniseerde accounts van uw on-premises AD DS biedt cloudidentiteit als een service (IDaaS) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-167">A central Azure AD tenant that contains the synchronized accounts of your on-premises AD DS provides cloud-based Identity as a Service (IDaaS) for your organization.</span></span> 
  
<span data-ttu-id="93f36-168">**Afbeelding 4: gesynchroniseerde on-premises accounts en IDaaS voor een organisatie**</span><span class="sxs-lookup"><span data-stu-id="93f36-168">**Figure 4: Synchronized on-premises accounts and IDaaS for an organization**</span></span>

![Identiteit als service (IaaS) IDaaS voor uw organisatie.](../media/Subscriptions/Subscriptions-Fig4.png)
  
<span data-ttu-id="93f36-170">In afbeelding 4 ziet u hoe een gemeenschappelijke Azure AD-Tenant wordt gebruikt door SaaS-cloudaanbiedingen van Microsoft, Azure PaaS-apps en virtuele machines in Azure IaaS die Azure AD Domain Services gebruiken.</span><span class="sxs-lookup"><span data-stu-id="93f36-170">Figure 4 shows how a common Azure AD tenant is used by Microsoft's SaaS cloud offerings, Azure PaaS apps, and virtual machines in Azure IaaS that use Azure AD Domain Services.</span></span> <span data-ttu-id="93f36-171">Met Azure AD Connect wordt het on-premises AD DS-forest gesynchroniseerd met de Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="93f36-171">Azure AD Connect synchronizes the on-premises AD DS forest with the Azure AD tenant.</span></span>
  
## <a name="combining-subscriptions-for-multiple-microsoft-cloud-offerings"></a><span data-ttu-id="93f36-172">Abonnementen combineren voor meerdere Microsoft cloudaanbiedingen</span><span class="sxs-lookup"><span data-stu-id="93f36-172">Combining subscriptions for multiple Microsoft cloud offerings</span></span>

<span data-ttu-id="93f36-173">In de volgende tabel wordt beschreven hoe u meerdere Microsoft cloudaanbiedingen kunt combineren op basis van het al hebben van een abonnement voor één type cloudaanbieding (de labels lopen af in de eerste kolom) en een abonnement voor een andere Cloud aanbieding toe te voegen aan de hand van de kolommen.</span><span class="sxs-lookup"><span data-stu-id="93f36-173">The following table describes how you can combine multiple Microsoft cloud offerings based on already having a subscription for one type of cloud offering (the labels going down the first column) and adding a subscription for a different cloud offering (going across the columns).</span></span>
  
||<span data-ttu-id="93f36-174">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="93f36-174">**Microsoft 365**</span></span>|<span data-ttu-id="93f36-175">**Azure**</span><span class="sxs-lookup"><span data-stu-id="93f36-175">**Azure**</span></span>|<span data-ttu-id="93f36-176">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="93f36-176">**Dynamics 365**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93f36-177">**Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="93f36-177">**Microsoft 365**</span></span> <br/> |<span data-ttu-id="93f36-178">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="93f36-178">NA</span></span>  <br/> |<span data-ttu-id="93f36-179">U voegt een Azure-abonnement toe aan uw organisatie vanuit het Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="93f36-179">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="93f36-180">In het Microsoft 365-Beheercentrum voegt u een Dynamics 365-abonnement toe aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-180">You add a Dynamics 365 subscription to your organization from the Microsoft 365 admin center.</span></span>  <br/> |
|<span data-ttu-id="93f36-181">**Azure**</span><span class="sxs-lookup"><span data-stu-id="93f36-181">**Azure**</span></span> <br/> |<span data-ttu-id="93f36-182">U voegt een Microsoft 365-abonnement toe aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-182">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="93f36-183">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="93f36-183">NA</span></span>  <br/> |<span data-ttu-id="93f36-184">U voegt een Dynamics 365-abonnement toe aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-184">You add a Dynamics 365 subscription to your organization.</span></span>  <br/> |
|<span data-ttu-id="93f36-185">**Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="93f36-185">**Dynamics 365**</span></span> <br/> |<span data-ttu-id="93f36-186">U voegt een Microsoft 365-abonnement toe aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="93f36-186">You add a Microsoft 365 subscription to your organization.</span></span>  <br/> |<span data-ttu-id="93f36-187">U voegt een Azure-abonnement toe aan uw organisatie vanuit het Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="93f36-187">You add an Azure subscription to your organization from the Azure portal.</span></span>  <br/> |<span data-ttu-id="93f36-188">N.v.t.</span><span class="sxs-lookup"><span data-stu-id="93f36-188">NA</span></span>  <br/> |
   
<span data-ttu-id="93f36-189">Een eenvoudige manier om abonnementen toe te voegen aan uw organisatie voor op Microsoft SaaS gebaseerde services, is via het Beheercentrum:</span><span class="sxs-lookup"><span data-stu-id="93f36-189">An easy way to add subscriptions to your organization for Microsoft SaaS-based services is through the admin center:</span></span>
  
1. <span data-ttu-id="93f36-190">Meld u aan in het Microsoft 365-beheercentrum ([https://admin.microsoft.com](https://admin.microsoft.com)) met uw globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="93f36-190">Sign in to the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)) with your global administrator account.</span></span>
    
2. <span data-ttu-id="93f36-191">Klik vanaf de linkernavigatiebalk van de startpagina van het **Beheercentrum** op \*\*Facturering \*\*, en vervolgens op **Diensten aanschaffen**.</span><span class="sxs-lookup"><span data-stu-id="93f36-191">From the left navigation of the **Admin center** home page, click **Billing**, and then **Purchase services**.</span></span>
    
3. <span data-ttu-id="93f36-192">Koop de nieuwe abonnementen op de pagina **aanschaffen Services**.</span><span class="sxs-lookup"><span data-stu-id="93f36-192">On the **Purchase services** page, purchase your new subscriptions.</span></span>
    
<span data-ttu-id="93f36-193">Het Beheercentrum wijst de organisatie en de Azure AD-tenant van uw Microsoft 365-abonnement toe aan de nieuwe abonnementen voor op SaaS gebaseerde Cloud-aanbiedingen.</span><span class="sxs-lookup"><span data-stu-id="93f36-193">The admin center assigns the organization and Azure AD tenant of your Microsoft 365 subscription to the new subscriptions for SaaS-based cloud offerings.</span></span>
  
<span data-ttu-id="93f36-194">Om een Azure-abonnement met dezelfde organisatie en Azure AD tenant toe te voegen als uw Microsoft 365-abonnement:</span><span class="sxs-lookup"><span data-stu-id="93f36-194">To add an Azure subscription with the same organization and Azure AD tenant as your Microsoft 365 subscription:</span></span>
  
1. <span data-ttu-id="93f36-195">Meld u aan in het Azure Portal ([https://portal.azure.com](https://portal.azure.com)) met uw Microsoft 365 globale beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="93f36-195">Sign in to the Azure portal ([https://portal.azure.com](https://portal.azure.com)) with your Microsoft 365 global administrator account.</span></span>
    
2. <span data-ttu-id="93f36-196">In het linkernavigatievenster kiest u **Abonnementen** en klik dan op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="93f36-196">In the left navigation, click **Subscriptions**, and then click **Add**.</span></span>
    
3. <span data-ttu-id="93f36-197">Selecteer op de pagina **Abonnement toevoegen** een aanbieding en voltooi de betalingsgegevens en de overeenkomst.</span><span class="sxs-lookup"><span data-stu-id="93f36-197">On the **Add subscription** page, select an offer and complete the payment information and agreement.</span></span>
    
<span data-ttu-id="93f36-198">Als u de abonnementen Azure en Microsoft 365 afzonderlijk hebt aangeschaft en u de Microsoft 365 Azure AD-tenant wilt openen vanuit uw Azure-abonnement, raadpleeg dan de instructies in[Een bestaand Azure-abonnement aan uw Azure Active Directory-tenant toevoegen](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span><span class="sxs-lookup"><span data-stu-id="93f36-198">If you purchased Azure and Microsoft 365 subscriptions separately and want to access the Microsoft 365 Azure AD tenant from your Azure subscription, see the instructions in [Add an existing Azure subscription to your Azure Active Directory tenant](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory).</span></span>
 
## <a name="see-also"></a><span data-ttu-id="93f36-199">Zie ook</span><span class="sxs-lookup"><span data-stu-id="93f36-199">See also</span></span>

[<span data-ttu-id="93f36-200">Microsoft Cloud voor Enterprise Architects</span><span class="sxs-lookup"><span data-stu-id="93f36-200">Microsoft cloud for enterprise architects illustrations</span></span>](../solutions/cloud-architecture-models.md)
  
[<span data-ttu-id="93f36-201">Architectuurmodellen voor SharePoint, Exchange, Skype voor Bedrijven en Lync</span><span class="sxs-lookup"><span data-stu-id="93f36-201">Architectural models for SharePoint, Exchange, Skype for Business, and Lync</span></span>](architectural-models-for-sharepoint-exchange-skype-for-business-and-lync.md)
  
[<span data-ttu-id="93f36-202">Hybride oplossingen</span><span class="sxs-lookup"><span data-stu-id="93f36-202">Hybrid solutions</span></span>](hybrid-solutions.md)

## <a name="next-step"></a><span data-ttu-id="93f36-203">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="93f36-203">Next step</span></span>

[<span data-ttu-id="93f36-204">Microsoft 365-netwerkverbindingen evalueren</span><span class="sxs-lookup"><span data-stu-id="93f36-204">Assessing Microsoft 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
