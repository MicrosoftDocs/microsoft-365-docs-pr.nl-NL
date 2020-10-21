---
title: Contoso IT-infrastructuur en bedrijfsbehoeften
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en de manier waarop de zakelijke behoeften van het bedrijf voldoen aan Microsoft 365 for Enterprise.
ms.openlocfilehash: bc2b34254da01a3d49085082ab8ee8632df2d434
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637173"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="bf081-103">Contoso IT-infrastructuur en bedrijfsbehoeften</span><span class="sxs-lookup"><span data-stu-id="bf081-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="bf081-104">Contoso overstapt van een on-premises, gecentraliseerde IT-infrastructuur naar een in de Cloud uitgedeelde instelling voor het uitvoeren van persoonlijke productiviteit en toepassingen op basis van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="bf081-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="bf081-105">Bestaande infrastructuur contoso IT</span><span class="sxs-lookup"><span data-stu-id="bf081-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="bf081-106">Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="bf081-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="bf081-107">Afbeelding 1 toont het hoofdkantoor met Application datacenters, een DMZ en Internet.</span><span class="sxs-lookup"><span data-stu-id="bf081-107">Figure 1 shows the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Bestaande infrastructuur contoso IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="bf081-109">**Afbeelding 1: bestaande contoso IT-infrastructuur**</span><span class="sxs-lookup"><span data-stu-id="bf081-109">**Figure 1: Existing Contoso IT infrastructure**</span></span>
 
<span data-ttu-id="bf081-110">De on-premises toepassingsdatacenters hosten:</span><span class="sxs-lookup"><span data-stu-id="bf081-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="bf081-111">Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.</span><span class="sxs-lookup"><span data-stu-id="bf081-111">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="bf081-112">Een set verouderde SharePoint-servers.</span><span class="sxs-lookup"><span data-stu-id="bf081-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="bf081-113">Servers op organisatie- en teamniveau voor bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="bf081-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="bf081-114">Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties.</span><span class="sxs-lookup"><span data-stu-id="bf081-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="bf081-115">Deze servers worden onderhouden door regionale IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="bf081-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="bf081-116">Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.</span><span class="sxs-lookup"><span data-stu-id="bf081-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="bf081-117">In het contoso Headquarters DMZ kunt u verschillende sets servers maken:</span><span class="sxs-lookup"><span data-stu-id="bf081-117">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="bf081-118">Het hosten van de openbare website van contoso, van welke klanten producten, onderdelen, bevoorrading en dienst kunnen bestellen.</span><span class="sxs-lookup"><span data-stu-id="bf081-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="bf081-119">Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.</span><span class="sxs-lookup"><span data-stu-id="bf081-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="bf081-120">Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="bf081-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="bf081-121">Bedrijfsbehoeften met contoso</span><span class="sxs-lookup"><span data-stu-id="bf081-121">Contoso business needs</span></span>

<span data-ttu-id="bf081-122">De behoeften van Contoso Business zijn in vijf hoofdcategorieën onderverdeeld:</span><span class="sxs-lookup"><span data-stu-id="bf081-122">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="bf081-123">**Productiviteit**</span><span class="sxs-lookup"><span data-stu-id="bf081-123">**Productivity**</span></span>

- <span data-ttu-id="bf081-124">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="bf081-124">Make collaboration easier</span></span>

  <span data-ttu-id="bf081-125">E-mail en on-line samenwerking vervangen op basis van een online model dat wijzigingen in realtime toestaat in documenten, eenvoudiger onlinevergaderingen en vastgelegde gespreks threads.</span><span class="sxs-lookup"><span data-stu-id="bf081-125">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="bf081-126">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="bf081-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="bf081-127">Met een groot aantal werknemers die in huis of in het veld werken, vervangt u de bewaarde VPN-oplossing door uitvoering van toegang tot contoso-gegevens en-bronnen in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="bf081-127">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="bf081-128">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="bf081-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="bf081-129">Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.</span><span class="sxs-lookup"><span data-stu-id="bf081-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="bf081-130">**Beveiliging**</span><span class="sxs-lookup"><span data-stu-id="bf081-130">**Security**</span></span>

- <span data-ttu-id="bf081-131">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="bf081-131">Identity and access management</span></span>

  <span data-ttu-id="bf081-132">Afdwingen van meervoudige en andere vormen van verificatie en beveiliging van gebruikers-en beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="bf081-132">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="bf081-133">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-133">Threat protection</span></span>

  <span data-ttu-id="bf081-134">Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.</span><span class="sxs-lookup"><span data-stu-id="bf081-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="bf081-135">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-135">Information protection</span></span>

  <span data-ttu-id="bf081-136">Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.</span><span class="sxs-lookup"><span data-stu-id="bf081-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="bf081-137">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="bf081-137">Security management</span></span>

  <span data-ttu-id="bf081-138">Bewaak beveiligings-Posture en spoor en reageer op bedreigingen in realtime.</span><span class="sxs-lookup"><span data-stu-id="bf081-138">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="bf081-139">**Externe en mobiele toegang en zakelijke partners**</span><span class="sxs-lookup"><span data-stu-id="bf081-139">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="bf081-140">Beveiliging voor externe en mobiele werknemers verbeteren</span><span class="sxs-lookup"><span data-stu-id="bf081-140">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="bf081-141">Implementeer uw eigen apparaat (BYOD) en bedrijfseigendoms beheer ter waarborging om te zorgen voor beveiligde toegang, het corrigeren van toepassings gedrag en de bescherming van bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="bf081-141">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="bf081-142">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="bf081-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="bf081-143">Ondersteunings-en ondersteuningskosten verlagen en de prestaties van de Remote Access-oplossing verbeteren door regelmatig toegankelijke bronnen naar de cloud te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="bf081-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="bf081-144">Zorgt voor betere connectiviteit en lagere overhead voor Business-to-susiness (B2B)-transacties</span><span class="sxs-lookup"><span data-stu-id="bf081-144">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="bf081-145">Vervang een verouderd en kostbaar partner extranet met een in de cloud gebaseerde oplossing die federatieve verificatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="bf081-145">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="bf081-146">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="bf081-146">**Compliance**</span></span>

- <span data-ttu-id="bf081-147">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="bf081-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="bf081-148">Zorg ervoor dat de naleving van industriële en regionale voorschriften voor het opslaan, versleutelen, data privacy en persoonlijke gegevens voorschriften, zoals de algemene verordening gegevensbescherming (AVG) voor de Europe Union, voldoen.</span><span class="sxs-lookup"><span data-stu-id="bf081-148">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="bf081-149">**Beheer**</span><span class="sxs-lookup"><span data-stu-id="bf081-149">**Management**</span></span>

- <span data-ttu-id="bf081-150">Minder IT-kosten voor het beheren van software die draait op client Pc's en-apparaten</span><span class="sxs-lookup"><span data-stu-id="bf081-150">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="bf081-151">De installatie van updates voor het Windows-besturingssysteem en Microsoft 365-apps voor Enterprise binnen de organisatie automatiseren.</span><span class="sxs-lookup"><span data-stu-id="bf081-151">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="bf081-152">Contoso Business behoeften toewijzen aan Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="bf081-152">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="bf081-153">De IT-afdeling van Contoso heeft bepaald dat de volgende toewijzingen van zakelijke behoeften aan Microsoft 365 E5-functies voorafgaand aan de implementatie:</span><span class="sxs-lookup"><span data-stu-id="bf081-153">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="bf081-154">Categorie</span><span class="sxs-lookup"><span data-stu-id="bf081-154">Category</span></span> | <span data-ttu-id="bf081-155">Zakelijke behoefte</span><span class="sxs-lookup"><span data-stu-id="bf081-155">Business need</span></span> | <span data-ttu-id="bf081-156">Microsoft 365 voor Enterprise-producten of-functies</span><span class="sxs-lookup"><span data-stu-id="bf081-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="bf081-157">Productiviteit</span><span class="sxs-lookup"><span data-stu-id="bf081-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="bf081-158">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="bf081-158">Make collaboration easier</span></span> | <span data-ttu-id="bf081-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="bf081-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="bf081-160">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="bf081-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="bf081-161">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf081-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="bf081-162">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="bf081-162">Increase creativity and innovation</span></span> | <span data-ttu-id="bf081-163">Windows Ink, Cortana op het werk, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="bf081-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="bf081-164">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-164">Security</span></span> |  |  |
|  | <span data-ttu-id="bf081-165">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="bf081-165">Identity & access management</span></span> | <span data-ttu-id="bf081-166">Toegewezen globale beheerdersaccounts met Azure multi-factor Authentication (MFA) en Azure Active Directory-geprivilegieerde identiteitsbeheer (PIM)</span><span class="sxs-lookup"><span data-stu-id="bf081-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure Active Directory Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="bf081-167">MFA voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="bf081-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="bf081-168">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="bf081-168">Conditional Access</span></span> <BR> <span data-ttu-id="bf081-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="bf081-169">Windows Hello</span></span> <BR> <span data-ttu-id="bf081-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="bf081-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="bf081-171">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-171">Threat protection</span></span> | <span data-ttu-id="bf081-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="bf081-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="bf081-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="bf081-173">Windows Defender</span></span> <BR> <span data-ttu-id="bf081-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf081-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="bf081-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="bf081-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="bf081-176">Microsoft 365 Threat onderzoek en-antwoord</span><span class="sxs-lookup"><span data-stu-id="bf081-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="bf081-177">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-177">Information protection</span></span> | <span data-ttu-id="bf081-178">Azure-gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="bf081-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="bf081-179">Preventie van gegevensverlies (DLP, Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="bf081-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="bf081-180">Windows-gegevensbescherming (WIP)</span><span class="sxs-lookup"><span data-stu-id="bf081-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="bf081-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bf081-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="bf081-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bf081-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="bf081-183">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="bf081-183">Security management</span></span> | <span data-ttu-id="bf081-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="bf081-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="bf081-185">Windows Defender-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="bf081-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="bf081-186">Externe en mobiele toegang en zakelijke partners</span><span class="sxs-lookup"><span data-stu-id="bf081-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="bf081-187">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="bf081-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="bf081-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bf081-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="bf081-189">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="bf081-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="bf081-190">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf081-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="bf081-191">De connectiviteit en lagere overhead voor B2B-transacties verbeteren</span><span class="sxs-lookup"><span data-stu-id="bf081-191">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="bf081-192">Federatieve verificatie en cloudgebaseerde bronnen</span><span class="sxs-lookup"><span data-stu-id="bf081-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="bf081-193">Naleving</span><span class="sxs-lookup"><span data-stu-id="bf081-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="bf081-194">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="bf081-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="bf081-195">AVG-functies in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bf081-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="bf081-196">Beheer</span><span class="sxs-lookup"><span data-stu-id="bf081-196">Management</span></span> |  |  |
|  | <span data-ttu-id="bf081-197">Minder IT-kosten voor de installatie van clientupdates</span><span class="sxs-lookup"><span data-stu-id="bf081-197">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="bf081-198">Implementatieringen.</span><span class="sxs-lookup"><span data-stu-id="bf081-198">Deployment rings</span></span> <BR> <span data-ttu-id="bf081-199">Updates voor Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bf081-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="bf081-200">Updates voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="bf081-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="bf081-201">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="bf081-201">Next step</span></span>

<span data-ttu-id="bf081-202">[Meer informatie](contoso-networking.md) over het on-premises netwerk van Contoso Corporation en hoe dit is geoptimaliseerd voor toegang en latentie tot microsoft 365 cloudresources.</span><span class="sxs-lookup"><span data-stu-id="bf081-202">[Learn](contoso-networking.md) about the Contoso Corporation on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf081-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bf081-203">See also</span></span>

[<span data-ttu-id="bf081-204">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="bf081-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="bf081-205">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="bf081-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
