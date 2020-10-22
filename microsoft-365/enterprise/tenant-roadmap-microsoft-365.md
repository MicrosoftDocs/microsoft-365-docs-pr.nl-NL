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
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: De routekaart voor het instellen van uw tenants voor Microsoft 365.
ms.openlocfilehash: db0f9552fce460ca6d25ee74ea2031bea388b8dc
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656005"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="766ea-103">Tenant plattegrond voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="766ea-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="766ea-104">Uw Microsoft 365-Tenant is de set services die is toegewezen aan uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="766ea-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="766ea-105">Deze Tenant is meestal gekoppeld aan een of meer van uw DNS-domeinnamen en fungeert als een centrale container voor verschillende abonnementen en de licenties binnen de licenties die u toewijst aan gebruikersaccounts.</span><span class="sxs-lookup"><span data-stu-id="766ea-105">Typically, this tenant is associated with one or more of your DNS domain names and acts as a central container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="766ea-106">Zie [abonnementen, licenties, accounts en tenants voor Cloud aanbiedingen van Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="766ea-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="766ea-107">Wanneer u een Microsoft 365-Tenant maakt, wordt deze toegewezen aan een bepaalde geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="766ea-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="766ea-108">U kunt ook een Tenant met meerdere geografische locaties hebben en uw Tenant verplaatsen van de ene locatie naar de andere.</span><span class="sxs-lookup"><span data-stu-id="766ea-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="766ea-109">Om de identiteit voor te bereiden, is het belangrijk dat u de Tenant configuratie zorgvuldig plant en uitvoert.</span><span class="sxs-lookup"><span data-stu-id="766ea-109">To get your tenant ready for identity, it's critical to carefully plan and execute your tenant configuration.</span></span>


## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="766ea-110">Uw Microsoft 365-Tenant instellen</span><span class="sxs-lookup"><span data-stu-id="766ea-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="766ea-111">Nadat u ervoor hebt gezorgd dat uw netwerk voor de toegang tot Microsoft 365 is geoptimaliseerd voor zowel on-premises gebruikers als zelfstandige medewerkers, wordt uw Microsoft 365-Tenant geconfigureerd en geconfigureerd met DNS-domeinnamen, common Services en voor de infrastructuur van de identiteit die een beveiligde gebruikersaanmelding ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="766ea-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

## <a name="plan"></a><span data-ttu-id="766ea-112">Plan</span><span class="sxs-lookup"><span data-stu-id="766ea-112">Plan</span></span>

<span data-ttu-id="766ea-113">Voor het plannen van uw Tenant-implementatie:</span><span class="sxs-lookup"><span data-stu-id="766ea-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="766ea-114">Meer informatie over abonnementen, licenties en Azure AD-tenants (Azure Active Directory)</span><span class="sxs-lookup"><span data-stu-id="766ea-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="766ea-115">Meer informatie over het gebruik van SSL-certificaten van derden</span><span class="sxs-lookup"><span data-stu-id="766ea-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="766ea-116">Inzicht in de manier waarop een Microsoft 365-Tenant is geïntegreerd met Azure AD Services</span><span class="sxs-lookup"><span data-stu-id="766ea-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="766ea-117">Ondersteuning voor client-apps plannen</span><span class="sxs-lookup"><span data-stu-id="766ea-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="766ea-118">Bepalen hoe u moderne verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="766ea-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="766ea-119">Abonnement voor Office 2007 en Office 2010 upgraden</span><span class="sxs-lookup"><span data-stu-id="766ea-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="766ea-120">Meer informatie over Tenant isolatie</span><span class="sxs-lookup"><span data-stu-id="766ea-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)
- [<span data-ttu-id="766ea-121">Meer informatie over Microsoft 365 service Assurance</span><span class="sxs-lookup"><span data-stu-id="766ea-121">Get the details on Microsoft 365 service assurance</span></span>](microsoft-365-administrative-access-controls-overview.md)

### <a name="deploy"></a><span data-ttu-id="766ea-122">Implementeren</span><span class="sxs-lookup"><span data-stu-id="766ea-122">Deploy</span></span>

<span data-ttu-id="766ea-123">Uw Tenant implementeren:</span><span class="sxs-lookup"><span data-stu-id="766ea-123">To deploy your tenant:</span></span> 

- <span data-ttu-id="766ea-124">Voeg de [DNS-domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) voor uw organisatie toe.</span><span class="sxs-lookup"><span data-stu-id="766ea-124">Add the [DNS domains](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) for your organization.</span></span>
- <span data-ttu-id="766ea-125">Gebruik de [installatie handleidingen in het Microsoft 365-Beheercentrum](setup-guides-for-microsoft-365.md).</span><span class="sxs-lookup"><span data-stu-id="766ea-125">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="766ea-126">Maak uw [identiteits infrastructuur](identity-roadmap-microsoft-365.md) en [Beveilig uw gebruikers aanmeld](microsoft-365-secure-sign-in.md).</span><span class="sxs-lookup"><span data-stu-id="766ea-126">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="766ea-127">De geografische locaties van een Tenant verplaatsen</span><span class="sxs-lookup"><span data-stu-id="766ea-127">Move a tenant's geographic locations</span></span>

<span data-ttu-id="766ea-128">Microsoft gaat verder met het openen van nieuwe geografische locaties (GEOS) voor Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="766ea-128">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="766ea-129">Deze nieuwe datacenter GEOS voegt capaciteit toe en berekent bronnen voor de ondersteuning van de vraag en de gebruiks groei van de klant.</span><span class="sxs-lookup"><span data-stu-id="766ea-129">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="766ea-130">Daarnaast biedt de nieuwe datacenter GEOS een in-geo data woonplaats voor de primaire klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="766ea-130">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="766ea-131">Zie [Core Data verplaatsen naar nieuwe Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="766ea-131">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="766ea-132">Microsoft 365 multi-geo implementeren</span><span class="sxs-lookup"><span data-stu-id="766ea-132">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="766ea-133">Met Microsoft 365 multi-geo kan uw organisatie zijn Microsoft 365-aanwezigheid uitbreiden naar meerdere geografische regio's en/of landen binnen de bestaande Tenant.</span><span class="sxs-lookup"><span data-stu-id="766ea-133">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="766ea-134">Zie [Microsoft 365 multi-geo](microsoft-365-multi-geo.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="766ea-134">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenancies"></a><span data-ttu-id="766ea-135">Meerdere Microsoft 365-tenancies</span><span class="sxs-lookup"><span data-stu-id="766ea-135">Manage multiple Microsoft 365 tenancies</span></span> 

<span data-ttu-id="766ea-136">Hoewel een enkele Tenant voor uw oganization ideaal is, is het mogelijk dat u een van de vele organisaties hebt met meerdere tenancies.</span><span class="sxs-lookup"><span data-stu-id="766ea-136">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenancies.</span></span> <span data-ttu-id="766ea-137">Redenen voor meerdere tenancies kunnen samen voegers en verwervingen zijn, u wilt de beheerder van de beheerder of een gedecentraliseerde beheerder.</span><span class="sxs-lookup"><span data-stu-id="766ea-137">Reasons for multiple tenancies can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="766ea-138">Als u meerdere Microsoft 365-tenancies hebt, raadpleegt u de volgende artikelen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="766ea-138">If you have multiple Microsoft 365 tenancies, see these articles for more information about:</span></span>

- [<span data-ttu-id="766ea-139">Samenwerking tussen verschillende tenants</span><span class="sxs-lookup"><span data-stu-id="766ea-139">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="766ea-140">Migratie van postvakken tussen tenants</span><span class="sxs-lookup"><span data-stu-id="766ea-140">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="766ea-141">Tenant-naar-tenant-migraties</span><span class="sxs-lookup"><span data-stu-id="766ea-141">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)


## <a name="next-step"></a><span data-ttu-id="766ea-142">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="766ea-142">Next step</span></span>

<span data-ttu-id="766ea-143">Start uw Tenant planning met [abonnementen, licenties, accounts en tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span><span class="sxs-lookup"><span data-stu-id="766ea-143">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>
