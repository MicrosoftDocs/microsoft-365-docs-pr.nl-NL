---
title: Tenant roadmap voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: De routekaart voor het instellen van uw tenants voor Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909452"
---
# <a name="tenant-roadmap-for-microsoft-365"></a><span data-ttu-id="11089-103">Tenant roadmap voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="11089-103">Tenant roadmap for Microsoft 365</span></span>

<span data-ttu-id="11089-104">Uw Microsoft 365-tenant is de set services die aan uw organisatie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="11089-104">Your Microsoft 365 tenant is the set of services assigned to your organization.</span></span> <span data-ttu-id="11089-105">Deze tenant is meestal gekoppeld aan een of meer van uw openbare DNS-domeinnamen en fungeert als een centrale en geïsoleerde container voor verschillende abonnementen en de licenties die u aan gebruikersaccounts toewijst.</span><span class="sxs-lookup"><span data-stu-id="11089-105">Typically, this tenant is associated with one or more of your public DNS domain names and acts as a central and isolated container for different subscriptions and the licenses within them that you assign to user accounts.</span></span> <span data-ttu-id="11089-106">Zie [Abonnementen, licenties, accounts](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)en tenants voor het cloudaanbod van Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="11089-106">For more information, see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>

<span data-ttu-id="11089-107">Wanneer u een Microsoft 365-tenant maakt, wijst u deze toe aan een specifieke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="11089-107">When you create a Microsoft 365 tenant, you assign it to a specific geographical location.</span></span> <span data-ttu-id="11089-108">U kunt ook een tenant met meerdere geografische locaties hebben en uw tenant van de ene locatie naar de andere verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="11089-108">You can also have a tenant with multiple geographical locations and move your tenant from one location to another.</span></span>

<span data-ttu-id="11089-109">Als u uw tenant wilt voorbereiden op gebruikers,groepen, licenties en cloud-apps, is het essentieel om de tenantconfiguratie zorgvuldig te plannen en uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="11089-109">To get your tenant ready for user, groups, licenses, and cloud apps, it's critical to carefully plan and execute your tenant configuration.</span></span>

## <a name="set-up-your-microsoft-365-tenant"></a><span data-ttu-id="11089-110">Uw Microsoft 365-tenant instellen</span><span class="sxs-lookup"><span data-stu-id="11089-110">Set up your Microsoft 365 tenant</span></span>

<span data-ttu-id="11089-111">Nadat u ervoor hebt gezorgd dat uw netwerk is geoptimaliseerd voor toegang tot Microsoft 365 voor zowel on-premises als externe werknemers, zijn uw volgende grote taken van plan om uw Microsoft 365-tenant te configureren voor DNS-domeinnamen, algemene services en voor die identiteitsinfrastructuur die veilige aanmelding van gebruikers ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="11089-111">After ensuring that your networking is optimized for access to Microsoft 365 for both on-premises and remote workers, your next big tasks are planning for and then configuring your Microsoft 365 tenant for DNS domain names, common services, and for that identity infrastructure that supports secure user sign-in.</span></span>

### <a name="plan"></a><span data-ttu-id="11089-112">Plannen</span><span class="sxs-lookup"><span data-stu-id="11089-112">Plan</span></span>

<span data-ttu-id="11089-113">Plannen voor de implementatie van uw tenant:</span><span class="sxs-lookup"><span data-stu-id="11089-113">To plan for your tenant implementation:</span></span>

- [<span data-ttu-id="11089-114">Meer inzicht in abonnementen, licenties en Azure Active Directory -tenants (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="11089-114">Understand subscriptions, licenses, and Azure Active Directory (Azure AD) tenants</span></span>](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [<span data-ttu-id="11089-115">Meer informatie over het gebruik van SSL-certificaten van derden</span><span class="sxs-lookup"><span data-stu-id="11089-115">Understand how to use third-party SSL certificates</span></span>](plan-for-third-party-ssl-certificates.md)
- [<span data-ttu-id="11089-116">Inzicht in de manieren waarop een Microsoft 365-tenant is geïntegreerd met Azure AD-services</span><span class="sxs-lookup"><span data-stu-id="11089-116">Understand the ways a Microsoft 365 tenant is integrated with Azure AD services</span></span>](integrated-apps-and-azure-ads.md)
- [<span data-ttu-id="11089-117">Ondersteuning voor client-apps plannen</span><span class="sxs-lookup"><span data-stu-id="11089-117">Plan for client app support</span></span>](microsoft-365-client-support-certificate-based-authentication.md)
- [<span data-ttu-id="11089-118">Bepalen hoe u hybride moderne verificatie gebruikt</span><span class="sxs-lookup"><span data-stu-id="11089-118">Determine how to use hybrid modern authentication</span></span>](hybrid-modern-auth-overview.md)
- [<span data-ttu-id="11089-119">Office 2007- en Office 2010-upgrades plannen</span><span class="sxs-lookup"><span data-stu-id="11089-119">Plan for Office 2007 and Office 2010 upgrades</span></span>](plan-upgrade-previous-versions-office.md)
- [<span data-ttu-id="11089-120">Tenantisolatie begrijpen</span><span class="sxs-lookup"><span data-stu-id="11089-120">Understand tenant isolation</span></span>](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a><span data-ttu-id="11089-121">Implementeren</span><span class="sxs-lookup"><span data-stu-id="11089-121">Deploy</span></span>

<span data-ttu-id="11089-122">Uw tenant implementeren:</span><span class="sxs-lookup"><span data-stu-id="11089-122">To deploy your tenant:</span></span> 

- <span data-ttu-id="11089-123">Voeg de [DNS-domeinen voor](../admin/setup/add-domain.md) uw organisatie toe.</span><span class="sxs-lookup"><span data-stu-id="11089-123">Add the [DNS domains](../admin/setup/add-domain.md) for your organization.</span></span>
- <span data-ttu-id="11089-124">Gebruik de [installatiehulplijnen in het Microsoft 365-beheercentrum.](setup-guides-for-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="11089-124">Use the [setup guides in the Microsoft 365 admin center](setup-guides-for-microsoft-365.md).</span></span>
- <span data-ttu-id="11089-125">Bouw uw [identiteitsinfrastructuur uit en](identity-roadmap-microsoft-365.md) [beveilig uw aanmeldingen voor gebruikers.](microsoft-365-secure-sign-in.md)</span><span class="sxs-lookup"><span data-stu-id="11089-125">Build out your [identity infrastructure](identity-roadmap-microsoft-365.md) and [secure your user sign-ins](microsoft-365-secure-sign-in.md).</span></span>

### <a name="move-a-tenants-geographic-locations"></a><span data-ttu-id="11089-126">Geografische locaties van een tenant verplaatsen</span><span class="sxs-lookup"><span data-stu-id="11089-126">Move a tenant's geographic locations</span></span>

<span data-ttu-id="11089-127">Microsoft blijft nieuwe geografische datacenterlocaties (geos) openen voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="11089-127">Microsoft continues to open new datacenter geographic locations (geos) for Microsoft 365 services.</span></span> <span data-ttu-id="11089-128">Deze nieuwe datacenter-geo's voegen capaciteits- en rekenbronnen toe om de vraag van klanten en de groei van het gebruik te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="11089-128">These new datacenter geos add capacity and compute resources to support customer demand and usage growth.</span></span> <span data-ttu-id="11089-129">Bovendien bieden de nieuwe datacentergeo's in-geogegevenslocatie voor basisgegevens van klanten.</span><span class="sxs-lookup"><span data-stu-id="11089-129">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="11089-130">Zie Kerngegevens verplaatsen naar nieuwe [Microsoft 365-datacenter-geo's voor meer informatie.](moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="11089-130">For more information, see [Moving core data to new Microsoft 365 datacenter geos](moving-data-to-new-datacenter-geos.md).</span></span>


## <a name="deploy-microsoft-365-multi-geo"></a><span data-ttu-id="11089-131">Microsoft 365 Multi-Geo implementeren</span><span class="sxs-lookup"><span data-stu-id="11089-131">Deploy Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="11089-132">Met Microsoft 365 Multi-Geo kan uw organisatie de aanwezigheid van Microsoft 365 uitbreiden naar meerdere geografische regio's en/of landen binnen uw bestaande tenant.</span><span class="sxs-lookup"><span data-stu-id="11089-132">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span>

<span data-ttu-id="11089-133">Zie Microsoft [365 Multi-Geo](microsoft-365-multi-geo.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="11089-133">For more information, see [Microsoft 365 Multi-Geo](microsoft-365-multi-geo.md).</span></span>

## <a name="manage-multiple-microsoft-365-tenants"></a><span data-ttu-id="11089-134">Meerdere Microsoft 365-tenants beheren</span><span class="sxs-lookup"><span data-stu-id="11089-134">Manage multiple Microsoft 365 tenants</span></span> 

<span data-ttu-id="11089-135">Hoewel één tenant voor uw oganisatie ideaal is, kunt u een van de vele organisaties zijn die meerdere tenants hebben.</span><span class="sxs-lookup"><span data-stu-id="11089-135">Although having a single tenant for your oganization is ideal, you may be one of many organizations that have multiple tenants.</span></span> <span data-ttu-id="11089-136">Redenen kunnen fusies en overnames zijn, u wilt administratieve isolatie of u hebt een gedecentraliseerde IT.</span><span class="sxs-lookup"><span data-stu-id="11089-136">Reasons can include mergers and aquisitions, you want administrative isolation, or you have a decentralized IT.</span></span>

<span data-ttu-id="11089-137">Als u meerdere Microsoft 365-tenants hebt, bekijkt u deze artikelen voor meer informatie over:</span><span class="sxs-lookup"><span data-stu-id="11089-137">If you have multiple Microsoft 365 tenants, see these articles for more information about:</span></span>

- [<span data-ttu-id="11089-138">Samenwerking tussen verschillende tenants</span><span class="sxs-lookup"><span data-stu-id="11089-138">Inter-tenant collaboration</span></span>](microsoft-365-inter-tenant-collaboration.md)
- [<span data-ttu-id="11089-139">Migratie van postvakken tussen tenants</span><span class="sxs-lookup"><span data-stu-id="11089-139">Cross-tenant mailbox migration</span></span>](cross-tenant-mailbox-migration.md)
- [<span data-ttu-id="11089-140">Tenant-naar-tenant-migraties</span><span class="sxs-lookup"><span data-stu-id="11089-140">Tenant-to-tenant migrations</span></span>](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a><span data-ttu-id="11089-141">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="11089-141">Next step</span></span>

<span data-ttu-id="11089-142">Start uw tenantplanning [met Abonnementen, licenties, accounts en tenants.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)</span><span class="sxs-lookup"><span data-stu-id="11089-142">Start your tenant planning with [Subscriptions, licenses, accounts, and tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).</span></span>