---
title: Tenant plattegrond voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/10/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom: it-pro
description: De routekaart voor het instellen van uw tenants voor Microsoft 365.
ms.openlocfilehash: 7834e8b7f9ff8a1b33f2f2a7ccc4a499e4da7c69
ms.sourcegitcommit: 13ae76220b4ad688438a5d1031a6e1b5300ffa23
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/15/2020
ms.locfileid: "47775145"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="fe451-103">Tenant plattegrond voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe451-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="fe451-104">Uw Microsoft 365-Tenant is de set services die is toegewezen aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="fe451-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="fe451-105">Deze Tenant is meestal gekoppeld aan een of meer van uw DNS-domeinnamen en fungeert als een centrale container voor verschillende abonnementen en de licenties binnen de licenties die u toewijst aan gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="fe451-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span>

<span data-ttu-id="fe451-106">Wanneer u een Microsoft 365-Tenant maakt, wordt deze toegewezen aan een bepaalde geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="fe451-106">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="fe451-107">U kunt ook een Tenant met meerdere geografische locaties hebben en uw Tenant verplaatsen van de ene locatie naar de andere.</span><span class="sxs-lookup"><span data-stu-id="fe451-107">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="fe451-108">Om uw Tenant voor te bereiden op de basisservice van netwerken en identiteiten, is het belangrijk om uw Tenant configuratie zorgvuldig te plannen en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="fe451-108">To get your tenant ready for the foundational services of networking and identity, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="plan"></a><span data-ttu-id="fe451-109">Abonnement</span><span class="sxs-lookup"><span data-stu-id="fe451-109">Plan</span></span>

<span data-ttu-id="fe451-110">Voor het plannen van uw Tenant-implementatie:</span><span class="sxs-lookup"><span data-stu-id="fe451-110">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="fe451-111">Meer informatie over abonnementen, licenties en Azure AD-tenants (Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="fe451-111">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="fe451-112">Meer informatie over het gebruik van SSL-certificaten van derden</span><span class="sxs-lookup"><span data-stu-id="fe451-112">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="fe451-113">Installatie handleidingen voor Access in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="fe451-113">Access setup guides in the Microsoft 365 admin center</span></span>](setup-guides-for-microsoft-365.md)
- [<span data-ttu-id="fe451-114">Inzicht in de manier waarop een Microsoft 365-Tenant is geïntegreerd met Azure AD Services</span><span class="sxs-lookup"><span data-stu-id="fe451-114">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="fe451-115">Ondersteuning voor client-apps plannen</span><span class="sxs-lookup"><span data-stu-id="fe451-115">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="fe451-116">Bepalen hoe u moderne verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="fe451-116">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="fe451-117">Abonnement voor Office 2007 en Office 2010 upgraden</span><span class="sxs-lookup"><span data-stu-id="fe451-117">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="fe451-118">Meer informatie over Tenant isolatie</span><span class="sxs-lookup"><span data-stu-id="fe451-118">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="fe451-119">Meer informatie over Microsoft 365 service Assurance</span><span class="sxs-lookup"><span data-stu-id="fe451-119">Get the details on Microsoft 365 service assurance</span></span>](https://docs.microsoft.com/microsoft-365/compliance/service-assurance)

## <a name="deploy"></a><span data-ttu-id="fe451-120">Implementeren</span><span class="sxs-lookup"><span data-stu-id="fe451-120">Deploy</span></span>

<span data-ttu-id="fe451-121">Voor de implementatie van de Tenant [voegt u de DNS-domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) voor uw organisatie toe.</span><span class="sxs-lookup"><span data-stu-id="fe451-121">To deploy your tenant, [add the DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>

## <a name="tenants-with-multiple-geographic-locations"></a><span data-ttu-id="fe451-122">Tenants met meerdere geografische locaties</span><span class="sxs-lookup"><span data-stu-id="fe451-122">Tenants with multiple geographic locations</span></span>

<span data-ttu-id="fe451-123">Met Microsoft 365 multi-geo kan uw organisatie zijn Microsoft 365-aanwezigheid uitbreiden naar meerdere geografische regio's en/of landen binnen de bestaande Tenant.</span><span class="sxs-lookup"><span data-stu-id="fe451-123">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="fe451-124">[Begin hier](microsoft-365-multi-geo.md)voor informatie over multi-geografische microsoft 365, waaronder het plannen, configureren en beheren van de app.</span><span class="sxs-lookup"><span data-stu-id="fe451-124">For information about Microsoft 365 Multi-Geo, including how to plan, configure, and administer it, [start here](microsoft-365-multi-geo.md).</span></span>

## <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="fe451-125">De geografische locaties van een Tenant verplaatsen</span><span class="sxs-lookup"><span data-stu-id="fe451-125">Move a tenant's geographic locations</span></span>

<span data-ttu-id="fe451-126">Microsoft gaat verder met het openen van nieuwe geografische locaties (GEOS) voor Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="fe451-126">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="fe451-127">Deze nieuwe datacenter GEOS voegt capaciteit toe en berekent bronnen voor de ondersteuning van de vraag en de gebruiks groei van de klant.</span><span class="sxs-lookup"><span data-stu-id="fe451-127">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="fe451-128">Daarnaast biedt de nieuwe datacenter GEOS een in-geo data woonplaats voor de primaire klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="fe451-128">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="fe451-129">[Begin hier](moving-data-to-new-datacenter-geos.md)voor informatie over microsoft 365 datacenter geo, waaronder het aanwijzen van een geo-data verplaatsing.</span><span class="sxs-lookup"><span data-stu-id="fe451-129">For information about Microsoft 365 datacenter geo, including how to request a geo data move, [start here](moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="fe451-130">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="fe451-130">Next step</span></span>

<span data-ttu-id="fe451-131">Start uw Tenant planning met [abonnementen, licenties, accounts en tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="fe451-131">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

