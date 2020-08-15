---
title: De IT-infrastructuur en zakelijke behoeften van Contoso
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
description: Inzicht in de basisstructuur van de on-premises IT-infrastructuur van Contoso en de manier waarop de bedrijfsbehoeften zijn behaald door Microsoft 365 for Enterprise.
ms.openlocfilehash: 3dd744a8d936307c61303bf8ba0f2f198af59d91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685828"
---
# <a name="contosos-it-infrastructure-and-business-needs"></a><span data-ttu-id="8c8a8-103">De IT-infrastructuur en zakelijke behoeften van Contoso</span><span class="sxs-lookup"><span data-stu-id="8c8a8-103">Contoso's IT infrastructure and business needs</span></span>

<span data-ttu-id="8c8a8-104">Contoso is overgestapt van een on-premises gecentraliseerde IT-infrastructuur naar een cloud-inclusieve infrastructuur die persoonlijke productiviteitsworkloads en toepassingen in de cloud omvat.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-104">Contoso has been transitioning from an on-premises, centralized IT infrastructure to a cloud-inclusive one that incorporates cloud-based personal productivity workloads and applications.</span></span>

## <a name="contosos-existing-it-infrastructure"></a><span data-ttu-id="8c8a8-105">De bestaande IT-infrastructuur van Contoso</span><span class="sxs-lookup"><span data-stu-id="8c8a8-105">Contoso's existing IT infrastructure</span></span>

<span data-ttu-id="8c8a8-106">Contoso maakt gebruik van een grotendeels gecentraliseerde on-premise IT-infrastructuur, met toepassingsdatacenters op het hoofdkantoor in Parijs.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-106">Contoso uses a mostly centralized on-premises IT infrastructure, with application datacenters in the Paris headquarters.</span></span>

<span data-ttu-id="8c8a8-107">Figuur 1 toont een hoofdkantoor met toepassingsdatacenters, een DMZ en internet.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-107">Figure 1 shows a headquarters office with application datacenters, a DMZ, and the Internet.</span></span>

![De bestaande IT-infrastructuur van Contoso](../media/contoso-infra-needs/contoso-infra-needs-fig1.png)

<span data-ttu-id="8c8a8-109">**Afbeelding 1: de bestaande IT-infrastructuur van Contoso**</span><span class="sxs-lookup"><span data-stu-id="8c8a8-109">**Figure 1: Contoso's existing IT infrastructure**</span></span>
 
<span data-ttu-id="8c8a8-110">De on-premises toepassingsdatacenters hosten:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-110">The on-premises application datacenters host:</span></span> 

- <span data-ttu-id="8c8a8-111">Aangepaste bedrijfstoepassingen die gebruikmaken van SQL Server en andere Linux-databases.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-111">Custom line of business applications that use SQL Server and other Linux databases.</span></span>
- <span data-ttu-id="8c8a8-112">Een set verouderde SharePoint-servers.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-112">A set of legacy SharePoint servers.</span></span>
- <span data-ttu-id="8c8a8-113">Servers op organisatie- en teamniveau voor bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-113">Organization and team-level servers for file storage.</span></span>

<span data-ttu-id="8c8a8-114">Bovendien ondersteunt elk regionaal hubkantoor een set servers met een vergelijkbare set applicaties.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-114">Additionally, each regional hub office supports a set of servers with a similar set of applications.</span></span> <span data-ttu-id="8c8a8-115">Deze servers worden onderhouden door regionale IT-afdelingen.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-115">These servers are under the control of regional IT departments.</span></span>

<span data-ttu-id="8c8a8-116">Doorzoekbaarheid in de applicaties en gegevens van deze afzonderlijke, geografisch verspreide datacenters blijft een uitdaging.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-116">Searchability across the applications and data of these separate multi-geographical datacenters continues to be a challenge.</span></span>

<span data-ttu-id="8c8a8-117">In Contoso's hoofdkantoor DMZ bieden verschillende verzamelingen servers het volgende:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-117">In Contoso's headquarters DMZ, different sets of servers provide:</span></span>

- <span data-ttu-id="8c8a8-118">Hosting van de openbare website van Contoso, waar klanten producten, onderdelen, benodigdheden of service kunnen bestellen.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-118">Hosting for the Contoso public web site, from which customers can order products, parts, supplies, or service.</span></span>
- <span data-ttu-id="8c8a8-119">Hosting van het partner-extranet voor communicatie en samenwerking met Contoso-partners.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-119">Hosting for the Contoso partner extranet for partner communication and collaboration.</span></span>
- <span data-ttu-id="8c8a8-120">Op VPN'S gebaseerde externe toegang tot het intranet van Contoso en webproxy voor werknemers in het hoofdkantoor van Parijs.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-120">Virtual private network (VPN)-based remote access to the Contoso intranet and web proxying for workers in the Paris headquarters.</span></span>

## <a name="contosos-business-needs"></a><span data-ttu-id="8c8a8-121">De zakelijke behoeften van Contoso</span><span class="sxs-lookup"><span data-stu-id="8c8a8-121">Contoso's business needs</span></span>

<span data-ttu-id="8c8a8-122">De zakelijke behoeften van Contoso bestaan uit vijf hoofdcategorieën.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-122">Contoso's business needs fall into five main categories.</span></span>

<span data-ttu-id="8c8a8-123">Productiviteit:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-123">Productivity:</span></span>

- <span data-ttu-id="8c8a8-124">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="8c8a8-124">Make collaboration easier</span></span>

  <span data-ttu-id="8c8a8-125">Vervang de samenwerking op basis van e-mail en het delen van bestanden door een online model dat realtime wijzigingen in documenten, eenvoudigere online vergaderingen en vastgelegde gespreks-threads mogelijk maakt.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-125">Replace the email and file share-based collaboration with an online model that allows real-time changes on documents, easier online meetings, and captured conversation threads.</span></span>
- <span data-ttu-id="8c8a8-126">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="8c8a8-126">Improve productivity for remote and mobile workers</span></span>

  <span data-ttu-id="8c8a8-127">Omdat veel werknemers vanuit huis of in het veld werken, vervangt u de snel blokkerende VPN-oplossing door performante toegang tot Contoso-gegevens en -bronnen in de cloud.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-127">With many employees working from homes or in the field, replace the bottlenecked VPN solution with performant access to Contoso data and resources in the cloud.</span></span>
- <span data-ttu-id="8c8a8-128">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="8c8a8-128">Increase creativity and innovation</span></span>

  <span data-ttu-id="8c8a8-129">Profiteer van de nieuwste visuele leer- en ideeontwikkelingsmethoden, inclusief inkt en 3D-visualisatie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-129">Take advantage of the latest visual learning and idea development methods, including inking and 3D visualization.</span></span>

<span data-ttu-id="8c8a8-130">Beveiliging:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-130">Security:</span></span>

- <span data-ttu-id="8c8a8-131">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c8a8-131">Identity and access management</span></span>

  <span data-ttu-id="8c8a8-132">Dwing meervoudige verificatie en andere vormen van verificatie af en bescherm de accountgegevens van gebruikers en beheerders.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-132">Enforce multi-factor and other forms of authentication and protect user and administrator account credentials.</span></span>

- <span data-ttu-id="8c8a8-133">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-133">Threat protection</span></span>

  <span data-ttu-id="8c8a8-134">Bescherm tegen externe beveiligingsdreigingen, waaronder e-mail en op het besturingssysteem gebaseerde malware.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-134">Protect against external security threats, including email and operating system-based malware.</span></span>

- <span data-ttu-id="8c8a8-135">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-135">Information protection</span></span>

  <span data-ttu-id="8c8a8-136">Vergrendel de toegang tot en codeer hoogwaardige digitale middelen, zoals klantgegevens, ontwerp- en fabricagespecificaties en werknemersinformatie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-136">Lock down access to and encrypt high-value digital assets, such as customer data, design and manufacturing specifications, and employee information.</span></span>

- <span data-ttu-id="8c8a8-137">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c8a8-137">Security management</span></span>

  <span data-ttu-id="8c8a8-138">Bewaak de veiligheid, detecteer bedreigingen en onderneem in realtime actie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-138">Monitor security posture and be able to detect and respond to threats in real time.</span></span>

<span data-ttu-id="8c8a8-139">Externe en mobiele toegang en zakelijke partners:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-139">Remote and mobile access and business partners:</span></span>

- <span data-ttu-id="8c8a8-140">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="8c8a8-140">Better security for remote and mobile workers</span></span>

  <span data-ttu-id="8c8a8-141">Stel apparaatbeheer in voor zowel privé (BYOD) als bedrijfseigen apparaten, om beveiligde toegang, correct applicatiegedrag en bedrijfsgegevensbescherming te garanderen.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-141">Institute Bring Your Own Device (BYOD) and company-owned device management to ensure secured access, correct application behavior, and company data protection.</span></span>

- <span data-ttu-id="8c8a8-142">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="8c8a8-142">Reduce remote access infrastructure for employees</span></span>

  <span data-ttu-id="8c8a8-143">Verlaag de onderhouds- en ondersteuningskosten en verbeter de prestaties voor oplossingen voor externe toegang door veelgebruikte bronnen naar de cloud te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-143">Reduce maintenance and support costs and improve performance for remote access solution by moving commonly-accessed resources to the cloud.</span></span>

- <span data-ttu-id="8c8a8-144">Zorg voor betere connectiviteit en lagere overhead voor B2B-transacties</span><span class="sxs-lookup"><span data-stu-id="8c8a8-144">Provide better connectivity and lower overhead for Business-to-Business (B2B) transactions</span></span>

  <span data-ttu-id="8c8a8-145">Vervang verouderd en kostbaar partner-extranet door een cloud-gebaseerde oplossing die gebruikmaakt van federatieve verificatie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-145">Replace aging and expensive partner extranet with a cloud-based solution that uses federated authentication.</span></span>

<span data-ttu-id="8c8a8-146">Naleving:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-146">Compliance:</span></span>

- <span data-ttu-id="8c8a8-147">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="8c8a8-147">Adhere to regional regulatory requirements</span></span>

  <span data-ttu-id="8c8a8-148">Werk blijvend in overeenstemming met de industriële en regionale voorschriften voor gegevensopslag, versleuteling, gegevensprivacy en persoonsgegevens, zoals de Algemene Verordening Gegevensbescherming (AVG) voor de Europese Unie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-148">Become and remain compliant with industry and regional regulations for data storage, encryption, data privacy, and personal data regulations, such as the General Data Protection Regulation (GDPR) for the Europe Union.</span></span>

<span data-ttu-id="8c8a8-149">Management:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-149">Management:</span></span>

- <span data-ttu-id="8c8a8-150">Verlaag de IT-overhead voor het beheer van software die wordt uitgevoerd op client-pc's en apparaten</span><span class="sxs-lookup"><span data-stu-id="8c8a8-150">Lower the IT overhead for managing software running on client PCs and devices</span></span>

  <span data-ttu-id="8c8a8-151">Automatiseer de installatie van updates voor het Windows-besturingssysteem en Microsoft 365-apps voor ondernemingen in de hele organisatie.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-151">Automate the installation of updates to the Windows operating system and Microsoft 365 Apps for enterprise across the organization.</span></span>

## <a name="mapping-contosos-business-needs-to-microsoft-365-for-enterprise"></a><span data-ttu-id="8c8a8-152">De zakelijke behoeften van Contoso toewijzen aan Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8c8a8-152">Mapping Contoso's business needs to Microsoft 365 for enterprise</span></span>

<span data-ttu-id="8c8a8-153">De IT-afdeling van Contoso heeft voorafgaand aan de implementatie de volgende informatie over de zakelijke behoeften aan Microsoft 365 E5-functies bepaald:</span><span class="sxs-lookup"><span data-stu-id="8c8a8-153">Contoso's IT department determined the following mapping of business needs to Microsoft 365 E5 features prior to deployment:</span></span>


| <span data-ttu-id="8c8a8-154">Categorie</span><span class="sxs-lookup"><span data-stu-id="8c8a8-154">Category</span></span> | <span data-ttu-id="8c8a8-155">Zakelijke behoefte</span><span class="sxs-lookup"><span data-stu-id="8c8a8-155">Business need</span></span> | <span data-ttu-id="8c8a8-156">Microsoft 365 voor Enterprise-producten of-functies</span><span class="sxs-lookup"><span data-stu-id="8c8a8-156">Microsoft 365 for enterprise products or features</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="8c8a8-157">Productiviteit</span><span class="sxs-lookup"><span data-stu-id="8c8a8-157">Productivity</span></span> |  |  |
|  | <span data-ttu-id="8c8a8-158">Eenvoudiger samenwerken</span><span class="sxs-lookup"><span data-stu-id="8c8a8-158">Make collaboration easier</span></span> | <span data-ttu-id="8c8a8-159">Microsoft Teams, SharePoint, OneDrive</span><span class="sxs-lookup"><span data-stu-id="8c8a8-159">Microsoft Teams, SharePoint, OneDrive</span></span> |
|  | <span data-ttu-id="8c8a8-160">Verbeter de productiviteit voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="8c8a8-160">Improve productivity for remote and mobile workers</span></span> | <span data-ttu-id="8c8a8-161">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c8a8-161">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="8c8a8-162">Verbeter de creativiteit en innovatie</span><span class="sxs-lookup"><span data-stu-id="8c8a8-162">Increase creativity and innovation</span></span> | <span data-ttu-id="8c8a8-163">Windows Ink, Cortana op het werk, PowerPoint</span><span class="sxs-lookup"><span data-stu-id="8c8a8-163">Windows Ink, Cortana at Work, PowerPoint</span></span> |
| <span data-ttu-id="8c8a8-164">Beveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-164">Security</span></span> |  |  |
|  | <span data-ttu-id="8c8a8-165">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c8a8-165">Identity & access management</span></span> | <span data-ttu-id="8c8a8-166">Toegewijde wereldwijde beheerdersaccounts met Azure meervoudige verificatie (MFA) en Azure AD Privileged Identity Management (PIM)</span><span class="sxs-lookup"><span data-stu-id="8c8a8-166">Dedicated global administrator accounts with Azure Multi-Factor Authentication (MFA) and Azure AD Privileged Identity Management (PIM)</span></span> <BR> <span data-ttu-id="8c8a8-167">MFA voor alle gebruikersaccounts</span><span class="sxs-lookup"><span data-stu-id="8c8a8-167">MFA for all user accounts</span></span> <BR> <span data-ttu-id="8c8a8-168">Voorwaardelijke toegang</span><span class="sxs-lookup"><span data-stu-id="8c8a8-168">Conditional Access</span></span> <BR> <span data-ttu-id="8c8a8-169">Windows Hello</span><span class="sxs-lookup"><span data-stu-id="8c8a8-169">Windows Hello</span></span> <BR> <span data-ttu-id="8c8a8-170">Windows Credential Guard</span><span class="sxs-lookup"><span data-stu-id="8c8a8-170">Windows Credential Guard</span></span> |
|  | <span data-ttu-id="8c8a8-171">Bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-171">Threat protection</span></span> | <span data-ttu-id="8c8a8-172">Advanced Threat Analytics</span><span class="sxs-lookup"><span data-stu-id="8c8a8-172">Advanced Threat Analytics</span></span> <BR> <span data-ttu-id="8c8a8-173">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="8c8a8-173">Windows Defender</span></span> <BR> <span data-ttu-id="8c8a8-174">Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c8a8-174">Advanced Threat Protection</span></span> <BR> <span data-ttu-id="8c8a8-175">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c8a8-175">Office 365 Advanced Threat Protection</span></span> <BR> <span data-ttu-id="8c8a8-176">Microsoft 365 Threat onderzoek en-antwoord</span><span class="sxs-lookup"><span data-stu-id="8c8a8-176">Microsoft 365 threat investigation and response</span></span> <BR> |
|  | <span data-ttu-id="8c8a8-177">Gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-177">Information protection</span></span> | <span data-ttu-id="8c8a8-178">Azure-gegevensbeveiliging</span><span class="sxs-lookup"><span data-stu-id="8c8a8-178">Azure Information Protection</span></span> <BR> <span data-ttu-id="8c8a8-179">Preventie van gegevensverlies (DLP, Data Loss Prevention)</span><span class="sxs-lookup"><span data-stu-id="8c8a8-179">Data Loss Prevention (DLP)</span></span> <BR> <span data-ttu-id="8c8a8-180">Windows-gegevensbescherming (WIP)</span><span class="sxs-lookup"><span data-stu-id="8c8a8-180">Windows Information Protection (WIP)</span></span> <BR> <span data-ttu-id="8c8a8-181">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8c8a8-181">Microsoft Cloud App Security</span></span> <BR> <span data-ttu-id="8c8a8-182">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8c8a8-182">Microsoft Intune</span></span> |
|  | <span data-ttu-id="8c8a8-183">Beveiligingsbeheer</span><span class="sxs-lookup"><span data-stu-id="8c8a8-183">Security management</span></span> | <span data-ttu-id="8c8a8-184">Azure Security Center</span><span class="sxs-lookup"><span data-stu-id="8c8a8-184">Azure Security Center</span></span>  <BR> <span data-ttu-id="8c8a8-185">Windows Defender-Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="8c8a8-185">Windows Defender Security Center</span></span> |
| <span data-ttu-id="8c8a8-186">Externe en mobiele toegang en zakelijke partners</span><span class="sxs-lookup"><span data-stu-id="8c8a8-186">Remote and mobile access and business partners</span></span> |  |  |
|  | <span data-ttu-id="8c8a8-187">Verbeterde beveiliging voor externe en mobiele werknemers</span><span class="sxs-lookup"><span data-stu-id="8c8a8-187">Better security for remote and mobile workers</span></span> | <span data-ttu-id="8c8a8-188">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8c8a8-188">Microsoft Intune</span></span> |
|  | <span data-ttu-id="8c8a8-189">De infrastructuur voor externe toegang voor werknemers reduceren</span><span class="sxs-lookup"><span data-stu-id="8c8a8-189">Reduce remote access infrastructure for employees</span></span> | <span data-ttu-id="8c8a8-190">Werkbelasting en cloud-gebaseerde gegevens voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c8a8-190">Microsoft 365 workloads and cloud-based data</span></span> |
|  | <span data-ttu-id="8c8a8-191">Zorgen voor betere connectiviteit en lagere overhead voor B2B-transacties</span><span class="sxs-lookup"><span data-stu-id="8c8a8-191">Provide better connectivity and lower overhead for B2B transactions</span></span> | <span data-ttu-id="8c8a8-192">Federatieve verificatie en cloudgebaseerde bronnen</span><span class="sxs-lookup"><span data-stu-id="8c8a8-192">Federated authentication and cloud-based resources</span></span> |
| <span data-ttu-id="8c8a8-193">Naleving</span><span class="sxs-lookup"><span data-stu-id="8c8a8-193">Compliance</span></span> |  |  |
|  | <span data-ttu-id="8c8a8-194">Voldoen aan regionale wettelijke voorschriften</span><span class="sxs-lookup"><span data-stu-id="8c8a8-194">Adhere to regional regulatory requirements</span></span> | <span data-ttu-id="8c8a8-195">AVG-functies in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c8a8-195">GDPR features in Microsoft 365</span></span> |
| <span data-ttu-id="8c8a8-196">Beheer</span><span class="sxs-lookup"><span data-stu-id="8c8a8-196">Management</span></span> |  |  |
|  | <span data-ttu-id="8c8a8-197">Verlaag de IT-overhead voor het installeren van client-updates</span><span class="sxs-lookup"><span data-stu-id="8c8a8-197">Lower the IT overhead for installing client updates</span></span> | <span data-ttu-id="8c8a8-198">Implementatieringen.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-198">Deployment rings</span></span> <BR> <span data-ttu-id="8c8a8-199">Updates voor Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="8c8a8-199">Windows 10 Enterprise updates</span></span> <BR> <span data-ttu-id="8c8a8-200">Updates voor Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8c8a8-200">Microsoft 365 Apps for enterprise updates</span></span> |
||||

## <a name="next-step"></a><span data-ttu-id="8c8a8-201">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="8c8a8-201">Next step</span></span>

<span data-ttu-id="8c8a8-202">[Meer informatie](contoso-networking.md) over het gebruik van het on-premises netwerk van Contoso Corporation en hoe het is geoptimaliseerd voor toegang en latentie tot resources van Microsoft 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="8c8a8-202">[Learn](contoso-networking.md) about the Contoso Corporation’s on-premises network and how it was optimized for access and latency to Microsoft 365 cloud-based resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c8a8-203">Zie ook</span><span class="sxs-lookup"><span data-stu-id="8c8a8-203">See also</span></span>

[<span data-ttu-id="8c8a8-204">Overzicht van Microsoft 365 voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="8c8a8-204">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8c8a8-205">Testlabrichtlijnen</span><span class="sxs-lookup"><span data-stu-id="8c8a8-205">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)
