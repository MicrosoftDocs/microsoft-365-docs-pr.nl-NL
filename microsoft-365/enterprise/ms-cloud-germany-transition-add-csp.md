---
title: Aanvullende informatie voor cloudoplossingsproviders
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
description: 'Overzicht: Aanvullende informatie voor cloudoplossingsproviders die relevant zijn voor de migratie van Microsoft Cloud Deutschland.'
ms.openlocfilehash: 843552c55acba57c5c2da4a1a885d65cb4e59d84
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984914"
---
# <a name="additional-information-for-cloud-solution-providers"></a><span data-ttu-id="d60a3-103">Aanvullende informatie voor cloudoplossingsproviders</span><span class="sxs-lookup"><span data-stu-id="d60a3-103">Additional information for Cloud Solution Providers</span></span>

<span data-ttu-id="d60a3-104">Cloud Solution Providers (CSP's) die klanten ondersteunen, moeten extra stappen ondernemen tijdens de migratie van Microsoft Cloud Deutschland naar de nieuwe Duitse datacenterregio.</span><span class="sxs-lookup"><span data-stu-id="d60a3-104">Cloud Solution Providers (CSPs) supporting customers  need to take additional steps during the migration from Microsoft Cloud Deutschland to the new German datacenter region.</span></span>

## <a name="partner-tenant-migration"></a><span data-ttu-id="d60a3-105">Migratie van partner tenant</span><span class="sxs-lookup"><span data-stu-id="d60a3-105">Partner tenant migration</span></span>

<span data-ttu-id="d60a3-106">Partner Microsoft Cloud Deutschland-tenants worden niet gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="d60a3-106">Partner Microsoft Cloud Deutschland tenants won't be migrated.</span></span> <span data-ttu-id="d60a3-107">In plaats daarvan wordt een nieuwe Office 365 services tenant gemaakt voor elke Microsoft-partner in de nieuwe Duitse datacenterregio.</span><span class="sxs-lookup"><span data-stu-id="d60a3-107">Instead, a new Office 365 services tenant will be created for each Microsoft Partner in the new German datacenter region.</span></span>

<span data-ttu-id="d60a3-108">CSP-klantten tenants worden gemigreerd naar de nieuwe Duitse datacenterregio en worden gekoppeld aan de nieuwe Office 365 servicesten tenant van dezelfde partner.</span><span class="sxs-lookup"><span data-stu-id="d60a3-108">CSP customer tenants will be migrated to the new German datacenter region and be linked to the new Office 365 services tenant of the same partner.</span></span> <span data-ttu-id="d60a3-109">Na de klantovergang kan de partner de klant beheren met de nieuwe Office 365 services tenant in de Duitse datacenterregio.</span><span class="sxs-lookup"><span data-stu-id="d60a3-109">After customer transition, the partner can manage the customer using the new Office 365 services tenant in the German datacenter region.</span></span>

## <a name="missing-subscriptions-in-azure"></a><span data-ttu-id="d60a3-110">Ontbrekende abonnementen in Azure</span><span class="sxs-lookup"><span data-stu-id="d60a3-110">Missing subscriptions in Azure</span></span>

<span data-ttu-id="d60a3-111">Nadat [de abonnements- en licentieovergang (fase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) is voltooid, hebben Cloud Solution Providers geen toegang meer tot het Azure-abonnement.</span><span class="sxs-lookup"><span data-stu-id="d60a3-111">After [the subscription and license transition (phase 3)](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer) has been completed, Cloud Solution Providers will not have access to the Azure subscription anymore.</span></span>

<span data-ttu-id="d60a3-112">Als u toegang wilt herstellen, volgt u deze stappen om de toegang tot alle Azure-abonnementen en [beheergroepen te verbeteren.](/azure/role-based-access-control/elevate-access-global-admin)</span><span class="sxs-lookup"><span data-stu-id="d60a3-112">To recover access, follow these steps to [elevate access to manage all Azure subscriptions and management groups](/azure/role-based-access-control/elevate-access-global-admin).</span></span>
