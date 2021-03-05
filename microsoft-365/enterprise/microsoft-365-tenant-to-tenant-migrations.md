---
title: Migratie van tenant naar tenant van Microsoft 365
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
description: Informatie over het migreren van Microsoft 365-tenants.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 09b2bc77333afaf1991064369846241328db85ff
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461641"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a><span data-ttu-id="5479a-103">Migratie van tenant naar tenant van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5479a-103">Microsoft 365 tenant-to-tenant migrations</span></span>

<span data-ttu-id="5479a-104">Er zijn verschillende architectuurbenaderingen voor fusies, overnames, verkoop en andere scenario's die ertoe kunnen leiden dat u een bestaande Microsoft 365-tenant migreert naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="5479a-104">There are several architecture approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> <span data-ttu-id="5479a-105">De meeste klanten werken met Microsoft Consulting Services of een Microsoft-partner om tenants te migreren, inclusief het gebruik van hulpprogramma's van derden om inhoud te migreren.</span><span class="sxs-lookup"><span data-stu-id="5479a-105">Most customers work with Microsoft Consulting Services or a Microsoft partner to migrate tenants, including using third-party tools to migrate content.</span></span> 

<span data-ttu-id="5479a-106">Gebruik het [architectuurmodel voor tenant-naar-tenant-migratie](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) voor meer informatie over het plannen van migraties tussen tenants en Microsoft 365 en de stappen van een migratie.</span><span class="sxs-lookup"><span data-stu-id="5479a-106">Use the [Tenant-to-tenant migration architecture model](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) to understand how to plan for Microsoft 365 tenant-to-tenant migrations and the steps of a migration.</span></span>

<span data-ttu-id="5479a-107">[![Migratiemodel per tenant](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span><span class="sxs-lookup"><span data-stu-id="5479a-107">[![Tenant-to-tenant migration model](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf)</span></span> 

<span data-ttu-id="5479a-108">U kunt dit model downloaden in [PDF-indeling](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) en afdrukken op papier van letter-, legal- of tabloid-formaat (11 x 17).</span><span class="sxs-lookup"><span data-stu-id="5479a-108">You download this model in [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-tenant-to-tenant-migration.pdf) format and print it on letter, legal, or tabloid (11 x 17) size paper.</span></span>

<span data-ttu-id="5479a-109">Dit model biedt richtlijnen en een uitgangspunt voor de planning met de volgende secties:</span><span class="sxs-lookup"><span data-stu-id="5479a-109">This model provides guidance and a starting-point for planning with sections on:</span></span>

- <span data-ttu-id="5479a-110">Toewijzing van zakelijke scenario's aan architectuurbenaderingen</span><span class="sxs-lookup"><span data-stu-id="5479a-110">Mapping of business scenarios to architecture approaches</span></span>
- <span data-ttu-id="5479a-111">Ontwerpoverwegingen</span><span class="sxs-lookup"><span data-stu-id="5479a-111">Design considerations</span></span>

<span data-ttu-id="5479a-112">Dit model bevat ook gedetailleerde voorbeelden van:</span><span class="sxs-lookup"><span data-stu-id="5479a-112">This model also contains detailed examples of:</span></span>

- <span data-ttu-id="5479a-113">Eén migratiestroom voor één gebeurtenis</span><span class="sxs-lookup"><span data-stu-id="5479a-113">A single event migration flow</span></span>
- <span data-ttu-id="5479a-114">Een gefaseeerde migratiestroom</span><span class="sxs-lookup"><span data-stu-id="5479a-114">A phased migration flow</span></span>
- <span data-ttu-id="5479a-115">Een tenant verplaatsen of splitsen</span><span class="sxs-lookup"><span data-stu-id="5479a-115">A tenant move or split flow</span></span>
