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
ms.openlocfilehash: b3b67429faccc5d22d49a2921fff4c8b3c3c062e
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920452"
---
# <a name="contoso-it-infrastructure-and-business-needs"></a><span data-ttu-id="6f29b-103">Contoso IT-infrastructuur en bedrijfsbehoeften</span><span class="sxs-lookup"><span data-stu-id="6f29b-103">Contoso IT infrastructure and business needs</span></span>

<span data-ttu-id="6f29b-104">Contoso overstapt van een on-premises, gecentraliseerde IT-infrastructuur naar een in de Cloud uitgedeelde instelling voor het uitvoeren van persoonlijke productiviteit en toepassingen op basis van de Cloud.</span><span class="sxs-lookup"><span data-stu-id="6f29b-104">Contoso is transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive setup that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="existing-contoso-it-infrastructure"></a><span data-ttu-id="6f29b-105">Bestaande infrastructuur contoso IT</span><span class="sxs-lookup"><span data-stu-id="6f29b-105">Existing Contoso IT infrastructure</span></span>

<span data-ttu-id="6f29b-106">Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="6f29b-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="6f29b-107">Hier is Office Headquarters Office met Application datacenters, een DMZ en Internet.</span><span class="sxs-lookup"><span data-stu-id="6f29b-107">Here is the headquarters office with application datacenters, a DMZ, and the internet.</span></span>

![Bestaande infrastructuur contoso IT](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="6f29b-109">De on-premises toepassingsdatacenters hosten:</span><span class="sxs-lookup"><span data-stu-id="6f29b-109">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="6f29b-110">Aangepaste line-of-business-toepassingen die gebruikmaken van SQL Server en andere Linux-databases.</span><span class="sxs-lookup"><span data-stu-id="6f29b-110">Custom line-of-business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="6f29b-111">Een set verouderde SharePoint-servers.</span><span class="sxs-lookup"><span data-stu-id="6f29b-111">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="6f29b-112">Servers op organisatie- en teamniveau voor bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="6f29b-112">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="6f29b-113">Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties.</span><span class="sxs-lookup"><span data-stu-id="6f29b-113">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="6f29b-114">Deze servers worden onderhouden door regionale IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="6f29b-114">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="6f29b-115">Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.</span><span class="sxs-lookup"><span data-stu-id="6f29b-115">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="6f29b-116">In het contoso Headquarters DMZ kunt u verschillende sets servers maken:</span><span class="sxs-lookup"><span data-stu-id="6f29b-116">In the Contoso headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="6f29b-117">Het hosten van de openbare website van contoso, van welke klanten producten, onderdelen, bevoorrading en dienst kunnen bestellen.</span><span class="sxs-lookup"><span data-stu-id="6f29b-117">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, and service.</span></span>
- <span data-ttu-id="6f29b-118">Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.</span><span class="sxs-lookup"><span data-stu-id="6f29b-118">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="6f29b-119">Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="6f29b-119">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contoso-business-needs"></a><span data-ttu-id="6f29b-120">Bedrijfsbehoeften met contoso</span><span class="sxs-lookup"><span data-stu-id="6f29b-120">Contoso business needs</span></span>

<span data-ttu-id="6f29b-121">De behoeften van Contoso Business zijn in vijf hoofdcategorieën onderverdeeld:</span><span class="sxs-lookup"><span data-stu-id="6f29b-121">Contoso business needs fall into five main categories:</span></span>

<span data-ttu-id="6f29b-122">**Productiviteit**</span><span class="sxs-lookup"><span data-stu-id="6f29b-122">**Productivity**</span></span>

- <span data-ttu-id="6f29b-123">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="6f29b-123">Make collaboration easier</span></span>

  <span data-ttu-id="6f29b-124">E-mail en on-line samenwerking vervangen op basis van een online model dat wijzigingen in realtime toestaat in documenten, eenvoudiger onlinevergaderingen en vastgelegde gespreks threads.</span><span class="sxs-lookup"><span data-stu-id="6f29b-124">Replace email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="6f29b-125">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="6f29b-125">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="6f29b-126">Met een groot aantal werknemers die in huis of in het veld werken, vervangt u de bewaarde VPN-oplossing door uitvoering van toegang tot contoso-gegevens en-bronnen in de Cloud.</span><span class="sxs-lookup"><span data-stu-id="6f29b-126">With many employees working from home or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="6f29b-127">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="6f29b-127">Increase creativity and innovation</span></span>

  <span data-ttu-id="6f29b-128">Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.</span><span class="sxs-lookup"><span data-stu-id="6f29b-128">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="6f29b-129">**Beveiliging**</span><span class="sxs-lookup"><span data-stu-id="6f29b-129">**Security**</span></span>

- <span data-ttu-id="6f29b-130">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="6f29b-130">Identity and access management</span></span>

  <span data-ttu-id="6f29b-131">Afdwingen van meervoudige en andere vormen van verificatie en beveiliging van gebruikers-en beheerdersaccounts.</span><span class="sxs-lookup"><span data-stu-id="6f29b-131">Enforce multifactor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="6f29b-132">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-132">Threat protection</span></span>

  <span data-ttu-id="6f29b-133">Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.</span><span class="sxs-lookup"><span data-stu-id="6f29b-133">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="6f29b-134">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-134">Information protection</span></span>

  <span data-ttu-id="6f29b-135">Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.</span><span class="sxs-lookup"><span data-stu-id="6f29b-135">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="6f29b-136">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="6f29b-136">Security management</span></span>

  <span data-ttu-id="6f29b-137">Bewaak beveiligings-Posture en spoor en reageer op bedreigingen in realtime.</span><span class="sxs-lookup"><span data-stu-id="6f29b-137">Monitor security posture and detect and respond to threats in real time.</span></span>

<span data-ttu-id="6f29b-138">**Externe en mobiele toegang en zakelijke partners**</span><span class="sxs-lookup"><span data-stu-id="6f29b-138">**Remote and mobile access and business partners**</span></span>

- <span data-ttu-id="6f29b-139">Beveiliging voor externe en mobiele werknemers verbeteren</span><span class="sxs-lookup"><span data-stu-id="6f29b-139">Improve security for remote and mobile workers</span></span>

  <span data-ttu-id="6f29b-140">Implementeer uw eigen apparaat (BYOD) en bedrijfseigendoms beheer ter waarborging om te zorgen voor beveiligde toegang, het corrigeren van toepassings gedrag en de bescherming van bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="6f29b-140">Implement bring your own device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="6f29b-141">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="6f29b-141">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="6f29b-142">Ondersteunings-en ondersteuningskosten verlagen en de prestaties van de Remote Access-oplossing verbeteren door regelmatig toegankelijke bronnen naar de cloud te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="6f29b-142">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly accessed resources to the cloud.</span></span>

- <span data-ttu-id="6f29b-143">Zorgt voor betere connectiviteit en lagere overhead voor Business-to-susiness (B2B)-transacties</span><span class="sxs-lookup"><span data-stu-id="6f29b-143">Provide better connectivity and lower overhead for business-to-susiness (B2B) transactions</span></span>

  <span data-ttu-id="6f29b-144">Vervang een verouderd en kostbaar partner extranet met een in de cloud gebaseerde oplossing die federatieve verificatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6f29b-144">Replace an aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="6f29b-145">**Compliance**</span><span class="sxs-lookup"><span data-stu-id="6f29b-145">**Compliance**</span></span>

- <span data-ttu-id="6f29b-146">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="6f29b-146">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="6f29b-147">Zorg ervoor dat de naleving van industriële en regionale voorschriften voor het opslaan, versleutelen, data privacy en persoonlijke gegevens voorschriften, zoals de algemene verordening gegevensbescherming (AVG) voor de Europe Union, voldoen.</span><span class="sxs-lookup"><span data-stu-id="6f29b-147">Ensure compliance with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="6f29b-148">**Beheer**</span><span class="sxs-lookup"><span data-stu-id="6f29b-148">**Management**</span></span>

- <span data-ttu-id="6f29b-149">Minder IT-kosten voor het beheren van software die draait op client Pc's en-apparaten</span><span class="sxs-lookup"><span data-stu-id="6f29b-149">Lower IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="6f29b-150">De installatie van updates voor het Windows-besturingssysteem en Microsoft 365-apps voor Enterprise binnen de organisatie automatiseren.</span><span class="sxs-lookup"><span data-stu-id="6f29b-150">Automate installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contoso-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="6f29b-151">Contoso Business behoeften toewijzen aan Microsoft 365 for Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f29b-151">Mapping Contoso business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="6f29b-152">De IT-afdeling van Contoso heeft bepaald dat de volgende toewijzingen van zakelijke behoeften aan Microsoft 365 E5-functies voorafgaand aan de implementatie:</span><span class="sxs-lookup"><span data-stu-id="6f29b-152">The Contoso IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="6f29b-153">Categorie</span><span class="sxs-lookup"><span data-stu-id="6f29b-153">Category</span></span> | <span data-ttu-id="6f29b-154">Zakelijke behoefte</span><span class="sxs-lookup"><span data-stu-id="6f29b-154">Business need</span></span> | <span data-ttu-id="6f29b-155">Microsoft 365 voor Enterprise-producten of-functies</span><span class="sxs-lookup"><span data-stu-id="6f29b-155">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="6f29b-156">Productiviteit</span><span class="sxs-lookup"><span data-stu-id="6f29b-156">Productivity</span></span> |  |  |
|  | <span data-ttu-id="6f29b-157">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="6f29b-157">Make collaboration easier</span></span> | <span data-ttu-id="6f29b-158">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="6f29b-158">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="6f29b-159">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="6f29b-159">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="6f29b-160">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f29b-160">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6f29b-161">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="6f29b-161">Increase creativity and innovation</span></span> | <span data-ttu-id="6f29b-162">Windows Ink, Cortana op het werk, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6f29b-162">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="6f29b-163">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-163">Security</span></span> |  |  |
|  | <span data-ttu-id="6f29b-164">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="6f29b-164">Identity & access management</span></span> | <span data-ttu-id="6f29b-165">Toegewijde wereldwijde beheerdersaccounts met Azure meervoudige verificatie (MFA) en Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="6f29b-165">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="6f29b-166">MFA voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="6f29b-166">MFA for all user accounts</span></span> <BR> <span data-ttu-id="6f29b-167">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="6f29b-167">Conditional Access</span></span> <BR> <span data-ttu-id="6f29b-168">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="6f29b-168">Windows Hello</span></span> <BR> <span data-ttu-id="6f29b-169">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="6f29b-169">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="6f29b-170">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-170">Threat protection</span></span> | <span data-ttu-id="6f29b-171">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="6f29b-171">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="6f29b-172">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="6f29b-172">Windows Defender</span></span> <BR> <span data-ttu-id="6f29b-173">Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6f29b-173">Defender for Office 365</span></span> <BR> <span data-ttu-id="6f29b-174">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6f29b-174">Microsoft Defender for Office 365</span></span> <BR> <span data-ttu-id="6f29b-175">Microsoft 365 Threat onderzoek en-antwoord</span><span class="sxs-lookup"><span data-stu-id="6f29b-175">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="6f29b-176">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-176">Information protection</span></span> | <span data-ttu-id="6f29b-177">Azure-gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="6f29b-177">Azure Information Protection</span></span> <BR> <span data-ttu-id="6f29b-178">Preventie van gegevensverlies (DLP, Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="6f29b-178">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="6f29b-179">Windows-gegevensbescherming (WIP)</span><span class="sxs-lookup"><span data-stu-id="6f29b-179">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="6f29b-180">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6f29b-180">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="6f29b-181">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6f29b-181">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6f29b-182">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="6f29b-182">Security management</span></span> | <span data-ttu-id="6f29b-183">Azure Defender</span><span class="sxs-lookup"><span data-stu-id="6f29b-183">Azure Defender</span></span>  <BR> <span data-ttu-id="6f29b-184">Windows Defender-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="6f29b-184">Windows Defender Security Center</span></span> |
| <span data-ttu-id="6f29b-185">Externe en mobiele toegang en zakelijke partners</span><span class="sxs-lookup"><span data-stu-id="6f29b-185">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="6f29b-186">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="6f29b-186">Better security for remote and mobile workers</span></span> | <span data-ttu-id="6f29b-187">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6f29b-187">Microsoft Intune</span></span> |
|  | <span data-ttu-id="6f29b-188">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="6f29b-188">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="6f29b-189">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f29b-189">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="6f29b-190">De connectiviteit en lagere overhead voor B2B-transacties verbeteren</span><span class="sxs-lookup"><span data-stu-id="6f29b-190">Improve connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="6f29b-191">Federatieve verificatie en cloudgebaseerde bronnen</span><span class="sxs-lookup"><span data-stu-id="6f29b-191">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="6f29b-192">Naleving</span><span class="sxs-lookup"><span data-stu-id="6f29b-192">Compliance</span></span> |  |  |
|  | <span data-ttu-id="6f29b-193">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="6f29b-193">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="6f29b-194">AVG-functies in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6f29b-194">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="6f29b-195">Beheer</span><span class="sxs-lookup"><span data-stu-id="6f29b-195">Management</span></span> |  |  |
|  | <span data-ttu-id="6f29b-196">Minder IT-kosten voor de installatie van clientupdates</span><span class="sxs-lookup"><span data-stu-id="6f29b-196">Lower IT overhead for installing client updates</span></span> | <span data-ttu-id="6f29b-197">Updates voor Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f29b-197">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="6f29b-198">Updates voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="6f29b-198">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="6f29b-199">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="6f29b-199">Next step</span></span>

<span data-ttu-id="6f29b-200">Meer informatie over het [on-premises netwerk van](contoso-networking.md) Contoso Corporation en hoe dit is geoptimaliseerd voor toegang en latentie tot microsoft 365 cloudresources.</span><span class="sxs-lookup"><span data-stu-id="6f29b-200">Learn about the Contoso Corporation [on-premises network](contoso-networking.md) and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="6f29b-201">Zie ook</span><span class="sxs-lookup"><span data-stu-id="6f29b-201">See also</span></span>

[<span data-ttu-id="6f29b-202">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="6f29b-202">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="6f29b-203">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="6f29b-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
