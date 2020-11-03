---
title: Contoso IT-infrastructuur en bedrijfsbehoeften
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
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en de manier waarop de zakelijke behoeften van het bedrijf voldoen aan Microsoft 365 for Enterprise.
ms.openlocfilehash: 0a837a457869fc579d94ee5e5f9bb114cb93f641
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847128"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="22065-103">Contoso IT-infrastructuur en bedrijfsbehoeften</span><span class="sxs-lookup"><span data-stu-id="22065-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="22065-104">Contoso overstapt van een on-premises, gecentraliseerde IT-infrastructuur naar een in de Cloud uitgedeelde instelling voor het uitvoeren van persoonlijke productiviteit en toepassingen op basis van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="22065-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="22065-105">Bestaande infrastructuur contoso IT</span><span class="sxs-lookup"><span data-stu-id="22065-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="22065-106">Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="22065-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="22065-107">Hier is Office Headquarters Office met Application datacenters, een DMZ en Internet.</span><span class="sxs-lookup"><span data-stu-id="22065-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Bestaande infrastructuur contoso IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="22065-109">De on-premises toepassingsdatacenters hosten:</span><span class="sxs-lookup"><span data-stu-id="22065-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="22065-110">Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.</span><span class="sxs-lookup"><span data-stu-id="22065-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="22065-111">Een set verouderde SharePoint-servers.</span><span class="sxs-lookup"><span data-stu-id="22065-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="22065-112">Servers op organisatie- en teamniveau voor bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="22065-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="22065-113">Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties.</span><span class="sxs-lookup"><span data-stu-id="22065-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="22065-114">Deze servers worden onderhouden door regionale IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="22065-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="22065-115">Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.</span><span class="sxs-lookup"><span data-stu-id="22065-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="22065-116">In het contoso Headquarters DMZ kunt u verschillende sets servers maken:</span><span class="sxs-lookup"><span data-stu-id="22065-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="22065-117">Het hosten van de openbare website van contoso, van welke klanten producten, onderdelen, bevoorrading en dienst kunnen bestellen.</span><span class="sxs-lookup"><span data-stu-id="22065-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="22065-118">Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.</span><span class="sxs-lookup"><span data-stu-id="22065-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="22065-119">Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="22065-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="22065-120">Bedrijfsbehoeften met contoso</span><span class="sxs-lookup"><span data-stu-id="22065-120">Contoso business needs</span></span>

<span data-ttu-id="22065-121">De behoeften van Contoso Business zijn in vijf hoofdcategorieën onderverdeeld:</span><span class="sxs-lookup"><span data-stu-id="22065-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="22065-122">**Productiviteit**</span><span class="sxs-lookup"><span data-stu-id="22065-122">**Productivity**</span></span>

- <span data-ttu-id="22065-123">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="22065-123">Make collaboration easier</span></span>

  <span data-ttu-id="22065-124">E-mail en on-line samenwerking vervangen op basis van een online model dat wijzigingen in realtime toestaat in documenten, eenvoudiger onlinevergaderingen en vastgelegde gespreks threads.</span><span class="sxs-lookup"><span data-stu-id="22065-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="22065-125">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="22065-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="22065-126">Met een groot aantal werknemers die in huis of in het veld werken, vervangt u de bewaarde VPN-oplossing door uitvoering van toegang tot contoso-gegevens en-bronnen in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="22065-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="22065-127">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="22065-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="22065-128">Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.</span><span class="sxs-lookup"><span data-stu-id="22065-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="22065-129">**Beveiliging**</span><span class="sxs-lookup"><span data-stu-id="22065-129">**Security**</span></span>

- <span data-ttu-id="22065-130">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="22065-130">Identity and access management</span></span>

  <span data-ttu-id="22065-131">Afdwingen van meervoudige en andere vormen van verificatie en beveiliging van gebruikers-en beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="22065-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="22065-132">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-132">Threat protection</span></span>

  <span data-ttu-id="22065-133">Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.</span><span class="sxs-lookup"><span data-stu-id="22065-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="22065-134">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-134">Information protection</span></span>

  <span data-ttu-id="22065-135">Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.</span><span class="sxs-lookup"><span data-stu-id="22065-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="22065-136">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="22065-136">Security management</span></span>

  <span data-ttu-id="22065-137">Bewaak beveiligings-Posture en spoor en reageer op bedreigingen in realtime.</span><span class="sxs-lookup"><span data-stu-id="22065-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="22065-138">**Externe en mobiele toegang en zakelijke partners**</span><span class="sxs-lookup"><span data-stu-id="22065-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="22065-139">Beveiliging voor externe en mobiele werknemers verbeteren</span><span class="sxs-lookup"><span data-stu-id="22065-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="22065-140">Implementeer uw eigen apparaat (BYOD) en bedrijfseigendoms beheer ter waarborging om te zorgen voor beveiligde toegang, het corrigeren van toepassings gedrag en de bescherming van bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="22065-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="22065-141">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="22065-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="22065-142">Ondersteunings-en ondersteuningskosten verlagen en de prestaties van de Remote Access-oplossing verbeteren door regelmatig toegankelijke bronnen naar de cloud te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="22065-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="22065-143">Zorgt voor betere connectiviteit en lagere overhead voor Business-to-susiness (B2B)-transacties</span><span class="sxs-lookup"><span data-stu-id="22065-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="22065-144">Vervang een verouderd en kostbaar partner extranet met een in de cloud gebaseerde oplossing die federatieve verificatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="22065-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="22065-145">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="22065-145">**Compliance**</span></span>

- <span data-ttu-id="22065-146">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="22065-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="22065-147">Zorg ervoor dat de naleving van industriële en regionale voorschriften voor het opslaan, versleutelen, data privacy en persoonlijke gegevens voorschriften, zoals de algemene verordening gegevensbescherming (AVG) voor de Europe Union, voldoen.</span><span class="sxs-lookup"><span data-stu-id="22065-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="22065-148">**Beheer**</span><span class="sxs-lookup"><span data-stu-id="22065-148">**Management**</span></span>

- <span data-ttu-id="22065-149">Minder IT-kosten voor het beheren van software die draait op client Pc's en-apparaten</span><span class="sxs-lookup"><span data-stu-id="22065-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="22065-150">De installatie van updates voor het Windows-besturingssysteem en Microsoft 365-apps voor Enterprise binnen de organisatie automatiseren.</span><span class="sxs-lookup"><span data-stu-id="22065-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="22065-151">Contoso Business behoeften toewijzen aan Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="22065-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="22065-152">De IT-afdeling van Contoso heeft bepaald dat de volgende toewijzingen van zakelijke behoeften aan Microsoft 365 E5-functies voorafgaand aan de implementatie:</span><span class="sxs-lookup"><span data-stu-id="22065-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="22065-153">Categorie</span><span class="sxs-lookup"><span data-stu-id="22065-153">Category</span></span> | <span data-ttu-id="22065-154">Zakelijke behoefte</span><span class="sxs-lookup"><span data-stu-id="22065-154">Business need</span></span> | <span data-ttu-id="22065-155">Microsoft 365 voor Enterprise-producten of-functies</span><span class="sxs-lookup"><span data-stu-id="22065-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="22065-156">Productiviteit</span><span class="sxs-lookup"><span data-stu-id="22065-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="22065-157">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="22065-157">Make collaboration easier</span></span> | <span data-ttu-id="22065-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="22065-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="22065-159">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="22065-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="22065-160">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22065-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="22065-161">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="22065-161">Increase creativity and innovation</span></span> | <span data-ttu-id="22065-162">Windows Ink, Cortana op het werk, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="22065-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="22065-163">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-163">Security</span></span> |  |  |
|  | <span data-ttu-id="22065-164">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="22065-164">Identity & access management</span></span> | <span data-ttu-id="22065-165">Toegewijde wereldwijde beheerdersaccounts met Azure meervoudige verificatie (MFA) en Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="22065-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="22065-166">MFA voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="22065-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="22065-167">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="22065-167">Conditional Access</span></span> <BR> <span data-ttu-id="22065-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="22065-168">Windows Hello</span></span> <BR> <span data-ttu-id="22065-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="22065-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="22065-170">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-170">Threat protection</span></span> | <span data-ttu-id="22065-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="22065-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="22065-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="22065-172">Windows Defender</span></span> <BR> <span data-ttu-id="22065-173">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="22065-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="22065-174">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="22065-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="22065-175">Microsoft 365 Threat onderzoek en-antwoord</span><span class="sxs-lookup"><span data-stu-id="22065-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="22065-176">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-176">Information protection</span></span> | <span data-ttu-id="22065-177">Azure-gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="22065-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="22065-178">Preventie van gegevensverlies (DLP, Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="22065-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="22065-179">Windows-gegevensbescherming (WIP)</span><span class="sxs-lookup"><span data-stu-id="22065-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="22065-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="22065-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="22065-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="22065-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="22065-182">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="22065-182">Security management</span></span> | <span data-ttu-id="22065-183">Azure Defender \*</span><span class="sxs-lookup"><span data-stu-id="22065-183">Azure Defender\*</span></span>  <BR> <span data-ttu-id="22065-184">Windows Defender-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="22065-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="22065-185">Externe en mobiele toegang en zakelijke partners</span><span class="sxs-lookup"><span data-stu-id="22065-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="22065-186">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="22065-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="22065-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="22065-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="22065-188">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="22065-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="22065-189">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22065-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="22065-190">De connectiviteit en lagere overhead voor B2B-transacties verbeteren</span><span class="sxs-lookup"><span data-stu-id="22065-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="22065-191">Federatieve verificatie en cloudgebaseerde bronnen</span><span class="sxs-lookup"><span data-stu-id="22065-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="22065-192">Naleving</span><span class="sxs-lookup"><span data-stu-id="22065-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="22065-193">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="22065-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="22065-194">AVG-functies in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="22065-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="22065-195">Beheer</span><span class="sxs-lookup"><span data-stu-id="22065-195">Management</span></span> |  |  |
|  | <span data-ttu-id="22065-196">Minder IT-kosten voor de installatie van clientupdates</span><span class="sxs-lookup"><span data-stu-id="22065-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="22065-197">Updates voor Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="22065-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="22065-198">Updates voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="22065-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="22065-199">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="22065-199">Next step</span></span>

<span data-ttu-id="22065-200">Meer informatie over het [on-premises netwerk van](contoso-networking.md) Contoso Corporation en hoe dit is geoptimaliseerd voor toegang en latentie tot microsoft 365 cloudresources.</span><span class="sxs-lookup"><span data-stu-id="22065-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="22065-201">Zie ook</span><span class="sxs-lookup"><span data-stu-id="22065-201">See also</span></span>

[<span data-ttu-id="22065-202">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="22065-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="22065-203">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="22065-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
