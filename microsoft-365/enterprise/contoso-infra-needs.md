---
title: Contoso IT-infrastructuur en zakelijke behoeften
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en hoe aan de zakelijke behoeften van het bedrijf wordt voldaan door Microsoft 365 voor ondernemingen.
ms.openlocfilehash: 72d502b5078a1e572eeba27832550af52907e209
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558404"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="45762-103">Contoso IT-infrastructuur en zakelijke behoeften</span><span class="sxs-lookup"><span data-stu-id="45762-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="45762-104">Contoso maakt de overstap van een on-premises, gecentraliseerde IT-infrastructuur naar een cloudinclusieve installatie met persoonlijke productiviteitsbelastingen en -toepassingen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="45762-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="45762-105">Bestaande IT-infrastructuur van Contoso</span><span class="sxs-lookup"><span data-stu-id="45762-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="45762-106">Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="45762-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="45762-107">Hier bevindt zich het hoofdkantoor met toepassingscentra, een DMZ en internet.</span><span class="sxs-lookup"><span data-stu-id="45762-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Bestaande IT-infrastructuur van Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="45762-109">De on-premises toepassingsdatacenters hosten:</span><span class="sxs-lookup"><span data-stu-id="45762-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="45762-110">Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.</span><span class="sxs-lookup"><span data-stu-id="45762-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="45762-111">Een set verouderde SharePoint-servers.</span><span class="sxs-lookup"><span data-stu-id="45762-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="45762-112">Servers op organisatie- en teamniveau voor bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="45762-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="45762-113">Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties.</span><span class="sxs-lookup"><span data-stu-id="45762-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="45762-114">Deze servers worden onderhouden door regionale IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="45762-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="45762-115">Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.</span><span class="sxs-lookup"><span data-stu-id="45762-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="45762-116">In het Contoso-hoofdkantoor DMZ bieden verschillende sets servers het volgende:</span><span class="sxs-lookup"><span data-stu-id="45762-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="45762-117">Hosting voor de openbare Website van Contoso, waaruit klanten producten, onderdelen, leveringen en service kunnen bestellen.</span><span class="sxs-lookup"><span data-stu-id="45762-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="45762-118">Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.</span><span class="sxs-lookup"><span data-stu-id="45762-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="45762-119">Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="45762-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="45762-120">Zakelijke behoeften van Contoso</span><span class="sxs-lookup"><span data-stu-id="45762-120">Contoso business needs</span></span>

<span data-ttu-id="45762-121">De zakelijke behoeften van Contoso zijn onderverdeeld in vijf hoofdcategorieën:</span><span class="sxs-lookup"><span data-stu-id="45762-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="45762-122">**Productiviteit**</span><span class="sxs-lookup"><span data-stu-id="45762-122">**Productivity**</span></span>

- <span data-ttu-id="45762-123">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="45762-123">Make collaboration easier</span></span>

  <span data-ttu-id="45762-124">Vervang samenwerking op basis van e-mail en bestanden door een onlinemodel waarmee realtime wijzigingen in documenten, eenvoudigere onlinevergaderingen en vastgelegde gespreksthreads mogelijk zijn.</span><span class="sxs-lookup"><span data-stu-id="45762-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="45762-125">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="45762-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="45762-126">Als veel werknemers thuis of in het veld werken, vervangt u de vpn-oplossing met knelpunten door performant toegang tot Contoso-gegevens en -resources in de cloud.</span><span class="sxs-lookup"><span data-stu-id="45762-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="45762-127">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="45762-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="45762-128">Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.</span><span class="sxs-lookup"><span data-stu-id="45762-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="45762-129">**Beveiliging**</span><span class="sxs-lookup"><span data-stu-id="45762-129">**Security**</span></span>

- <span data-ttu-id="45762-130">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="45762-130">Identity and access management</span></span>

  <span data-ttu-id="45762-131">Dwing multifactor- en andere vormen van verificatie af en bescherm gebruikers- en beheerdersaccountreferenties.</span><span class="sxs-lookup"><span data-stu-id="45762-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="45762-132">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-132">Threat protection</span></span>

  <span data-ttu-id="45762-133">Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.</span><span class="sxs-lookup"><span data-stu-id="45762-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="45762-134">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-134">Information protection</span></span>

  <span data-ttu-id="45762-135">Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.</span><span class="sxs-lookup"><span data-stu-id="45762-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="45762-136">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="45762-136">Security management</span></span>

  <span data-ttu-id="45762-137">Controleer de beveiligingshouding en detecteer en reageer in realtime op bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="45762-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="45762-138">**Externe en mobiele toegang en zakelijke partners**</span><span class="sxs-lookup"><span data-stu-id="45762-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="45762-139">De beveiliging voor externe en mobiele werknemers verbeteren</span><span class="sxs-lookup"><span data-stu-id="45762-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="45762-140">Implementeert bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span><span class="sxs-lookup"><span data-stu-id="45762-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="45762-141">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="45762-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="45762-142">Verminder de kosten voor onderhoud en ondersteuning en verbeter de prestaties voor oplossing voor externe toegang door veelgebruikte resources naar de cloud te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="45762-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="45762-143">Betere connectiviteit en lagere overhead voor B2B-transacties (Business-to-Susiness)</span><span class="sxs-lookup"><span data-stu-id="45762-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="45762-144">Vervang een ouder en duur partner extranet door een cloudoplossing die federatief verificatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="45762-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="45762-145">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="45762-145">**Compliance**</span></span>

- <span data-ttu-id="45762-146">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="45762-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="45762-147">Zorg ervoor dat de industrie- en regionale voorschriften voor gegevensopslag, versleuteling, privacy van gegevens en persoonsgegevens worden nageleefd, zoals de Algemene verordening gegevensbescherming (AVG) voor de Europese Unie.</span><span class="sxs-lookup"><span data-stu-id="45762-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="45762-148">**Beheer**</span><span class="sxs-lookup"><span data-stu-id="45762-148">**Management**</span></span>

- <span data-ttu-id="45762-149">Lagere IT-overhead voor het beheren van software die wordt uitgevoerd op client-pc's en -apparaten</span><span class="sxs-lookup"><span data-stu-id="45762-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="45762-150">Automatiseer de installatie van updates voor het Windows besturingssysteem en Microsoft 365-apps voor ondernemingen in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="45762-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="45762-151">Contoso-bedrijven toewijzen moet Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="45762-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="45762-152">De IT-afdeling Contoso heeft de volgende toewijzing van bedrijfsbehoeften vastgesteld Microsoft 365 E5 functies vóór de implementatie:</span><span class="sxs-lookup"><span data-stu-id="45762-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="45762-153">Categorie</span><span class="sxs-lookup"><span data-stu-id="45762-153">Category</span></span> | <span data-ttu-id="45762-154">Zakelijke behoefte</span><span class="sxs-lookup"><span data-stu-id="45762-154">Business need</span></span> | <span data-ttu-id="45762-155">Microsoft 365 voor ondernemingsproducten of -functies</span><span class="sxs-lookup"><span data-stu-id="45762-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="45762-156">Productiviteit</span><span class="sxs-lookup"><span data-stu-id="45762-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="45762-157">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="45762-157">Make collaboration easier</span></span> | <span data-ttu-id="45762-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="45762-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="45762-159">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="45762-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="45762-160">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45762-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="45762-161">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="45762-161">Increase creativity and innovation</span></span> | <span data-ttu-id="45762-162">Windows Ink, Cortana op het werk, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="45762-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="45762-163">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-163">Security</span></span> |  |  |
|  | <span data-ttu-id="45762-164">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="45762-164">Identity & access management</span></span> | <span data-ttu-id="45762-165">Toegewezen globale beheerdersaccounts met Azure AD Multi-Factor Authentication (MFA) en Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="45762-165">Dedicated global administrator accounts with Azure AD Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="45762-166">MFA voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="45762-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="45762-167">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="45762-167">Conditional Access</span></span> <BR> <span data-ttu-id="45762-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="45762-168">Windows Hello</span></span> <BR> <span data-ttu-id="45762-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="45762-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="45762-170">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-170">Threat protection</span></span> | <span data-ttu-id="45762-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="45762-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="45762-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="45762-172">Windows Defender</span></span> <BR> <span data-ttu-id="45762-173">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="45762-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="45762-174">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="45762-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="45762-175">Microsoft 365 bedreigingsonderzoek en -antwoord</span><span class="sxs-lookup"><span data-stu-id="45762-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="45762-176">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-176">Information protection</span></span> | <span data-ttu-id="45762-177">Azure-gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="45762-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="45762-178">Preventie van gegevensverlies (DLP, Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="45762-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="45762-179">Windows-gegevensbescherming (WIP)</span><span class="sxs-lookup"><span data-stu-id="45762-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="45762-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="45762-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="45762-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="45762-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="45762-182">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="45762-182">Security management</span></span> | <span data-ttu-id="45762-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="45762-183">Azure Defender</span></span>  <BR> <span data-ttu-id="45762-184">Windows Defender-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="45762-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="45762-185">Externe en mobiele toegang en zakelijke partners</span><span class="sxs-lookup"><span data-stu-id="45762-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="45762-186">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="45762-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="45762-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="45762-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="45762-188">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="45762-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="45762-189">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45762-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="45762-190">Connectiviteit en lagere overhead voor B2B-transacties verbeteren</span><span class="sxs-lookup"><span data-stu-id="45762-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="45762-191">Federatieve verificatie en cloudgebaseerde bronnen</span><span class="sxs-lookup"><span data-stu-id="45762-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="45762-192">Naleving</span><span class="sxs-lookup"><span data-stu-id="45762-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="45762-193">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="45762-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="45762-194">GDPR-functies in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="45762-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="45762-195">Beheer</span><span class="sxs-lookup"><span data-stu-id="45762-195">Management</span></span> |  |  |
|  | <span data-ttu-id="45762-196">Lagere IT-overhead voor het installeren van clientupdates</span><span class="sxs-lookup"><span data-stu-id="45762-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="45762-197">Updates voor Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="45762-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="45762-198">Updates voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="45762-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="45762-199">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="45762-199">Next step</span></span>

<span data-ttu-id="45762-200">Meer informatie over het [on-premises](contoso-networking.md) netwerk van Contoso Corporation en hoe het is geoptimaliseerd voor toegang en latentie om Microsoft 365 cloudbronnen te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="45762-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="45762-201">Zie ook</span><span class="sxs-lookup"><span data-stu-id="45762-201">See also</span></span>

[<span data-ttu-id="45762-202">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="45762-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="45762-203">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="45762-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
