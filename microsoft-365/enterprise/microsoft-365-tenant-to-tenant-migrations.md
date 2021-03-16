---
title: Microsoft 365 tenant-to-tenant-migraties
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Meer informatie over het migreren van Microsoft 365-tenants.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819712"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="aab6f-103">Microsoft 365 tenant-to-tenant-migraties</span><span class="sxs-lookup"><span data-stu-id="aab6f-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="aab6f-104">Er zijn verschillende architectuurbenaderingen voor fusies, overnames, afstotingen en andere scenario's die ertoe kunnen leiden dat u een bestaande Microsoft 365-tenant migreert naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="aab6f-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="aab6f-105">De meeste klanten werken samen met Microsoft Consulting Services of een Microsoft-partner om tenants te migreren, inclusief het gebruik van hulpprogramma's van derden om inhoud te migreren.</span><span class="sxs-lookup"><span data-stu-id="aab6f-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="aab6f-106">Gebruik het [tenant-to-tenant-migratiearchitectuurmodel](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) om te begrijpen hoe u microsoft 365 tenant-to-tenantmigraties en de stappen van een migratie kunt plannen.</span><span class="sxs-lookup"><span data-stu-id="aab6f-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="aab6f-107">[![Migratiemodel tenant-naar-tenant](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="aab6f-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="aab6f-108">U downloadt dit model in [PDF-indeling](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) en afdrukt het op papier van letter-, juridische of tabloidformaat (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="aab6f-108">You download this model in [PDF](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="aab6f-109">Dit model biedt richtlijnen en een beginpunt voor planning met secties op:</span><span class="sxs-lookup"><span data-stu-id="aab6f-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="aab6f-110">Toewijzing van bedrijfsscenario's aan architectuurbenaderingen</span><span class="sxs-lookup"><span data-stu-id="aab6f-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="aab6f-111">Ontwerpoverwegingen</span><span class="sxs-lookup"><span data-stu-id="aab6f-111">Design considerations</span></span>

<span data-ttu-id="aab6f-112">Dit model bevat ook gedetailleerde voorbeelden van:</span><span class="sxs-lookup"><span data-stu-id="aab6f-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="aab6f-113">Eén migratiestroom voor gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="aab6f-113">A single event migration flow</span></span>
- <span data-ttu-id="aab6f-114">Een gefaseerd migratiestroom</span><span class="sxs-lookup"><span data-stu-id="aab6f-114">A phased migration flow</span></span>
- <span data-ttu-id="aab6f-115">Een tenant verplaatsen of splitsen</span><span class="sxs-lookup"><span data-stu-id="aab6f-115">A tenant move or split flow</span></span>
