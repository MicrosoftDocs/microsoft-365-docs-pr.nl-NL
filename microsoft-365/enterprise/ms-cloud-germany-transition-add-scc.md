---
title: Informatie over eDiscovery-ervaring tijdens de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: eDiscovery-migratiestappen voor de migratie van Microsoft Cloud Deutschland.'
ms.openlocfilehash: 0128c8563b2043e4ec41d2c5ab1b208bd3977511
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844248"
---
# <a name="information-about-the-ediscovery-experience-during-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="c29c4-103">Informatie over de eDiscovery-ervaring tijdens de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="c29c4-103">Information about the eDiscovery experience during the migration from Microsoft Cloud Deutschland</span></span>
<span data-ttu-id="c29c4-104">In de volgende secties vindt u aanvullende informatie over de eDiscovery-ervaring bij het over stappen van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.</span><span class="sxs-lookup"><span data-stu-id="c29c4-104">The following sections provide additional information about the eDiscovery experience when moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="ediscovery-administration-until-phase-4"></a><span data-ttu-id="c29c4-105">eDiscovery-beheer tot fase 4</span><span class="sxs-lookup"><span data-stu-id="c29c4-105">eDiscovery administration until phase 4</span></span>
<span data-ttu-id="c29c4-106">Tot fase 4 is het Beveiligings- en compliancecentrum volledig beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="c29c4-106">Until phase 4, the Security and Compliance Center will be fully available.</span></span> <span data-ttu-id="c29c4-107">Alle inhoud blijft nog steeds in de Microsoft Cloud Germany staan en kan worden beheert door het Microsoft Cloud Germany Security and Compliance Center ( https://protection.office.de/) .</span><span class="sxs-lookup"><span data-stu-id="c29c4-107">All content still remains in the Microsoft Cloud Germany and is manageable by the Microsoft Cloud Germany Security and Compliance Center (https://protection.office.de/).</span></span>

## <a name="ediscovery-experience-between-phase-4-until-the-the-end-of-phase-9"></a><span data-ttu-id="c29c4-108">eDiscovery-ervaring tussen fase 4 tot het einde van fase 9</span><span class="sxs-lookup"><span data-stu-id="c29c4-108">eDiscovery experience between phase 4 until the the end of phase 9</span></span>
<span data-ttu-id="c29c4-109">Vanaf het begin van fase 4 tot fase 9 is voltooid, mislukken eDiscovery-zoekopdrachten of retourneren 0 resultaten voor SharePoint Online OneDrive voor Bedrijven- en Exchange Online-locaties die zijn gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="c29c4-109">From the beginning of phase 4 until phase 9 is completed, eDiscovery searches will fail or return 0 results for SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated.</span></span>

> [!NOTE]
> <span data-ttu-id="c29c4-110">Tijdens de migratie kunnen klanten zaken blijven maken, in- en uitbaten en exporteren in het [beveiligings- & compliancecentrum,](/microsoft-365/compliance/manage-legal-investigations)inclusief [Inhoud zoeken.](/microsoft-365/compliance/search-for-content)</span><span class="sxs-lookup"><span data-stu-id="c29c4-110">During migration, customers can continue to create cases, holds, searches, and exports in the [Security & Compliance Center](/microsoft-365/compliance/manage-legal-investigations), including [Content Search](/microsoft-365/compliance/search-for-content).</span></span> <span data-ttu-id="c29c4-111">Zoekopdrachten met SharePoint online, OneDrive voor Bedrijven en Exchange Online die zijn gemigreerd, leveren echter 0 resultaten op of leveren een fout op.</span><span class="sxs-lookup"><span data-stu-id="c29c4-111">However, searches against SharePoint Online, OneDrive for Business, and Exchange Online locations that have been migrated will either return 0 results or produce an error.</span></span>

<span data-ttu-id="c29c4-112">Als een zoekopdracht nul resultaten of een fout oplevert tijdens de migratie, moet u de volgende actie ondernemen voor SharePoint Online:</span><span class="sxs-lookup"><span data-stu-id="c29c4-112">In the event that a search returns zero results or an error during migration, please take the following action for SharePoint Online:</span></span>

- <span data-ttu-id="c29c4-113">Download sites rechtstreeks van de SharePoint Online- of OneDrive voor Bedrijven-site door de instructies te volgen in Bestanden en mappen downloaden van OneDrive of [SharePoint.](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)</span><span class="sxs-lookup"><span data-stu-id="c29c4-113">Download sites directly from the SharePoint Online or OneDrive for Business site by following the instructions in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05).</span></span> <span data-ttu-id="c29c4-114">Voor deze methode zijn SharePoint beheerdersmachtigingen of alleen-lezen-machtigingen op de site vereist.</span><span class="sxs-lookup"><span data-stu-id="c29c4-114">This method will require SharePoint Online administrator permissions or read-only permissions on the site.</span></span>
- <span data-ttu-id="c29c4-115">Als limieten worden overschreden, zoals wordt uitgelegd in Bestanden en mappen downloaden van OneDrive of [SharePoint,](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05)kunnen klanten de synchronisatieclient OneDrive voor Bedrijven gebruiken door de richtlijnen in Bestanden synchroniseren SharePoint en [Teams met](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88)uw computer te volgen.</span><span class="sxs-lookup"><span data-stu-id="c29c4-115">If limits are exceeded, as explained in [Download files and folders from OneDrive or SharePoint](https://support.office.com/article/download-files-and-folders-from-onedrive-or-sharepoint-5c7397b7-19c7-4893-84fe-d02e8fa5df05), customers can use the OneDrive for Business sync client by following the guidance in [Sync SharePoint and Teams files with your computer](https://support.office.com/article/sync-sharepoint-files-with-the-new-onedrive-sync-app-6de9ede8-5b6e-4503-80b2-6190f3354a88).</span></span>

- <span data-ttu-id="c29c4-116">Zie voor meer informatie [In-place eDiscovery in Exchange Server.](/Exchange/policy-and-compliance/ediscovery/ediscovery)</span><span class="sxs-lookup"><span data-stu-id="c29c4-116">For more information, see  [In-Place eDiscovery in Exchange Server](/Exchange/policy-and-compliance/ediscovery/ediscovery).</span></span>


## <a name="ediscovery-administration-after-phase-9"></a><span data-ttu-id="c29c4-117">eDiscovery-beheer na fase 9</span><span class="sxs-lookup"><span data-stu-id="c29c4-117">eDiscovery administration after phase 9</span></span>

<span data-ttu-id="c29c4-118">**Van toepassing op:** Alle klanten die eDiscovery gebruiken</span><span class="sxs-lookup"><span data-stu-id="c29c4-118">**Applies to:** All customers using eDiscovery</span></span>

<span data-ttu-id="c29c4-119">In fase 9 worden de laatste stappen voor het verplaatsen naar het nieuwe Duitse datacenter voltooid.</span><span class="sxs-lookup"><span data-stu-id="c29c4-119">In phase 9, the final steps for moving to the new German datacenter region will be completed.</span></span> <span data-ttu-id="c29c4-120">In deze fase worden alle resterende serviceonderdelen gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="c29c4-120">In this phase, all remaining service components will be migrated.</span></span>
<span data-ttu-id="c29c4-121">Na fase 9 wordt het gebruik van het Beveiligings- en compliancecentrum in Microsoft Cloud Germany (protection.office.de) niet meer ondersteund.</span><span class="sxs-lookup"><span data-stu-id="c29c4-121">After phase 9, using the Security and Compliance Center in Microsoft Cloud Germany (protection.office.de) is no longer supported.</span></span> <span data-ttu-id="c29c4-122">Gebruik in plaats daarvan [het nieuwe beveiligingscentrum](https://security.microsoft.com/) [of compliancecentrum.](https://compliance.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="c29c4-122">Please use the new [Security Center](https://security.microsoft.com/) or [Compliance Center](https://compliance.microsoft.com/) instead.</span></span> <span data-ttu-id="c29c4-123">Alle gegevens zijn gemigreerd naar de nieuwe beheerportalen.</span><span class="sxs-lookup"><span data-stu-id="c29c4-123">All data have been migrated to the new admin portals.</span></span>

| <span data-ttu-id="c29c4-124">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="c29c4-124">Step(s)</span></span> | <span data-ttu-id="c29c4-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c29c4-125">Description</span></span> | <span data-ttu-id="c29c4-126">Gevolg</span><span class="sxs-lookup"><span data-stu-id="c29c4-126">Impact</span></span> |
|:-------|:-------|:-------|
|  <span data-ttu-id="c29c4-127">Alle SharePoint online, OneDrive voor Bedrijven en Exchange Online zijn samen met het SCC (Security and Compliance Center) gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="c29c4-127">All SharePoint Online, OneDrive for Business, and Exchange Online locations have been migrated along with the Security and Compliance Center (SCC).</span></span> | <span data-ttu-id="c29c4-128">Alle eDiscovery-activiteiten moeten worden uitgevoerd vanuit de wereldwijde tenant.</span><span class="sxs-lookup"><span data-stu-id="c29c4-128">All eDiscovery activity should be run from the worldwide tenant.</span></span> <span data-ttu-id="c29c4-129">Zoekopdrachten zijn nu 100% succesvol.</span><span class="sxs-lookup"><span data-stu-id="c29c4-129">Searches will now be 100% successful.</span></span> <span data-ttu-id="c29c4-130">Eventuele fouten of fouten moeten de normale ondersteuningskanalen volgen.</span><span class="sxs-lookup"><span data-stu-id="c29c4-130">Any failures or errors should follow normal support channels.</span></span> | <span data-ttu-id="c29c4-131">Geen</span><span class="sxs-lookup"><span data-stu-id="c29c4-131">None</span></span> |
||||

### <a name="ediscovery-retention-policy"></a><span data-ttu-id="c29c4-132">eDiscovery-bewaarbeleid</span><span class="sxs-lookup"><span data-stu-id="c29c4-132">eDiscovery Retention Policy</span></span>
<span data-ttu-id="c29c4-133">**Van toepassing op:**  Alle klanten die een bewaarbeleid hebben toegepast als onderdeel van de stappen vóór de migratie</span><span class="sxs-lookup"><span data-stu-id="c29c4-133">**Applies to:**  All customers who applied a retention policy as part of the pre-migration steps</span></span>

| <span data-ttu-id="c29c4-134">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="c29c4-134">Step(s)</span></span> | <span data-ttu-id="c29c4-135">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="c29c4-135">Description</span></span> | <span data-ttu-id="c29c4-136">Gevolg</span><span class="sxs-lookup"><span data-stu-id="c29c4-136">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="c29c4-137">Bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens de stappen vóór de migratie</span><span class="sxs-lookup"><span data-stu-id="c29c4-137">Remove organization-wide retention policies that were created during pre-migration steps</span></span> | <span data-ttu-id="c29c4-138">Klanten kunnen het bewaarbeleid voor de hele organisatie verwijderen dat is gemaakt tijdens het werk van de klanten vóór de migratie.</span><span class="sxs-lookup"><span data-stu-id="c29c4-138">Customers can remove the organization-wide retention policies that were created during the customers' pre-migration work.</span></span> | <span data-ttu-id="c29c4-139">Geen</span><span class="sxs-lookup"><span data-stu-id="c29c4-139">None</span></span> |
||||
