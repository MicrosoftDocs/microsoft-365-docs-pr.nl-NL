---
title: MsSP-toegang (Managed Security Service Provider) bieden
description: Meer informatie over wijzigingen van het Microsoft Defender-beveiligingscentrum in het Microsoft 365-beveiligingscentrum
keywords: Aan de slag met het Microsoft 365-beveiligingscentrum, Microsoft Defender voor Office 365, Microsoft Defender voor Eindpunt, MDO, MDE, enkel deelvenster glas, geconvergeerde portal, beveiligingsportal, defender security portal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 4b34d3ea20716fb2424d9317b8a51c088a5714a6
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935351"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="c29df-104">MsSP-toegang (Managed Security Service Provider) bieden</span><span class="sxs-lookup"><span data-stu-id="c29df-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="c29df-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="c29df-105">**Applies to:**</span></span>

- [<span data-ttu-id="c29df-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c29df-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="c29df-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="c29df-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="c29df-108">Als u een oplossing voor gedelegeerde toegang met meerdere tenants wilt implementeren, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="c29df-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="c29df-109">Schakel [op rollen gebaseerde toegangsbeheer](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender voor Eindpunt in microsoft 365-beveiligingscentrum in en maak verbinding met Azure Active Directory -groepen (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="c29df-109">Enable [role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="c29df-110">[Beheertoegangspakketten configureren voor toegangsaanvraag](/azure/active-directory/governance/identity-governance-overview) en inrichting.</span><span class="sxs-lookup"><span data-stu-id="c29df-110">Configure [Governance Access Packages](/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="c29df-111">Toegangsaanvragen en -audits beheren in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="c29df-111">Manage access requests and audits in [Microsoft Myaccess](/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="c29df-112">Op rollen gebaseerde toegangsbesturingselementen inschakelen in Microsoft Defender voor Eindpunt in microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="c29df-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="c29df-113">**Toegangsgroepen maken voor MSSP-resources in Klant-AAD: Groepen**</span><span class="sxs-lookup"><span data-stu-id="c29df-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="c29df-114">Deze groepen worden gekoppeld aan de rollen die u maakt in Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="c29df-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="c29df-115">Maak in de ad-tenant van de klant drie groepen om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="c29df-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="c29df-116">In onze voorbeeldbenadering maken we de volgende groepen:</span><span class="sxs-lookup"><span data-stu-id="c29df-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="c29df-117">Tier 1 Analyst</span><span class="sxs-lookup"><span data-stu-id="c29df-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="c29df-118">Tier 2 Analyst</span><span class="sxs-lookup"><span data-stu-id="c29df-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="c29df-119">MSSP-analist-goedkeurders</span><span class="sxs-lookup"><span data-stu-id="c29df-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="c29df-120">Maak Defender voor eindpuntrollen voor de juiste toegangsniveaus in Customer Defender voor Eindpunt in microsoft 365 beveiligingscentrumrollen en -groepen.</span><span class="sxs-lookup"><span data-stu-id="c29df-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="c29df-121">Als u RBAC wilt inschakelen in het microsoft 365-beveiligingscentrum van de klant, hebt u toegang tot machtigingen > eindpunten rollen & groepen > Rollen met een gebruikersaccount met globale **beheerders- of** beveiligingsbeheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="c29df-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Afbeelding van MSSP-toegang](../../media/mssp-access.png)

    <span data-ttu-id="c29df-123">Maak vervolgens RBAC-rollen om te voldoen aan de soc-laagbehoeften van MSSP.</span><span class="sxs-lookup"><span data-stu-id="c29df-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="c29df-124">Koppel deze rollen aan de gemaakte gebruikersgroepen via 'Toegewezen gebruikersgroepen'.</span><span class="sxs-lookup"><span data-stu-id="c29df-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="c29df-125">Twee mogelijke rollen:</span><span class="sxs-lookup"><span data-stu-id="c29df-125">Two possible roles:</span></span>

    - <span data-ttu-id="c29df-126">**Tier 1-analisten**</span><span class="sxs-lookup"><span data-stu-id="c29df-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="c29df-127">Voer alle acties uit, behalve livereacties en beheer beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="c29df-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="c29df-128">**Laag 2-analisten**</span><span class="sxs-lookup"><span data-stu-id="c29df-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="c29df-129">Tier 1-mogelijkheden met de toevoeging aan [livereactie](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="c29df-129">Tier 1 capabilities with the addition to [live response](/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="c29df-130">Zie Op rollen gebaseerde [toegangsbeheer gebruiken](/windows/security/threat-protection/microsoft-defender-atp/rbac)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c29df-130">For more information, see [Use role-based access control](/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="c29df-131">Governance Access-pakketten configureren</span><span class="sxs-lookup"><span data-stu-id="c29df-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="c29df-132">**MSSP toevoegen als verbonden organisatie in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c29df-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="c29df-133">Als u mssp toevoegt als een verbonden organisatie, kan de MSSP aanvragen en toegang hebben tot de inrichting.</span><span class="sxs-lookup"><span data-stu-id="c29df-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="c29df-134">Als u dit wilt doen, krijgt u in de ad-tenant van de klant toegang tot Identiteitsbeheer: Verbonden organisatie.</span><span class="sxs-lookup"><span data-stu-id="c29df-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="c29df-135">Voeg een nieuwe organisatie toe en zoek naar uw MSSP Analyst-tenant via tenant-id of domein.</span><span class="sxs-lookup"><span data-stu-id="c29df-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="c29df-136">We raden u aan een aparte AD-tenant te maken voor uw MSSP-analisten.</span><span class="sxs-lookup"><span data-stu-id="c29df-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="c29df-137">**Een resourcecatalogus maken in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c29df-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c29df-138">Resourcecatalogi zijn een logische verzameling toegangspakketten die zijn gemaakt in de AD-tenant van de klant.</span><span class="sxs-lookup"><span data-stu-id="c29df-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="c29df-139">U doet dit door in de AD-tenant van de klant identiteitsbeheer: catalogi te openen en Nieuwe catalogus **toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="c29df-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="c29df-140">In ons voorbeeld noemen we het **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="c29df-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Afbeelding van nieuwe catalogus](../../media/goverance-catalog.png)

    <span data-ttu-id="c29df-142">Zie Een catalogus met resources maken voor [meer informatie.](/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="c29df-142">Further more information, see [Create a catalog of resources](/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="c29df-143">**Access-pakketten maken voor MSSP-resources Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c29df-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c29df-144">Access-pakketten zijn de verzameling rechten en toegangen die een aangever na goedkeuring wordt verleend.</span><span class="sxs-lookup"><span data-stu-id="c29df-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="c29df-145">U doet dit door in de AD-tenant van de klant identiteitsbeheer: Access-pakketten te openen en Nieuw **Access-pakket toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="c29df-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="c29df-146">Maak een toegangspakket voor de MSSP-goedkeurders en elke analistlaag.</span><span class="sxs-lookup"><span data-stu-id="c29df-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="c29df-147">Met de volgende configuratie van Tier 1 Analyst wordt bijvoorbeeld een toegangspakket gemaakt dat:</span><span class="sxs-lookup"><span data-stu-id="c29df-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="c29df-148">Vereist dat een lid van de AD-groep **MSSP Analyst Approvers** nieuwe aanvragen autorizert</span><span class="sxs-lookup"><span data-stu-id="c29df-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="c29df-149">Heeft jaarlijkse toegangsbeoordelingen, waarbij de SOC-analisten een toegangsextensie kunnen aanvragen</span><span class="sxs-lookup"><span data-stu-id="c29df-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="c29df-150">Kan alleen worden aangevraagd door gebruikers in de SOC-tenant van MSSP</span><span class="sxs-lookup"><span data-stu-id="c29df-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="c29df-151">Access Auto verloopt na 365 dagen</span><span class="sxs-lookup"><span data-stu-id="c29df-151">Access auto expires after 365 days</span></span>

    ![Afbeelding van nieuw toegangspakket](../../media/new-access-package.png)

    <span data-ttu-id="c29df-153">Zie Een nieuw [toegangspakket maken](/azure/active-directory/governance/entitlement-management-access-package-create)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c29df-153">For more information, see [Create a new access package](/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="c29df-154">**Koppeling voor toegangsaanvraag naar MSSP-resources van Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="c29df-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="c29df-155">De koppeling Mijn Access-portal wordt door MSSP-SOC-analisten gebruikt om toegang te vragen via de gemaakte toegangspakketten.</span><span class="sxs-lookup"><span data-stu-id="c29df-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="c29df-156">De koppeling is duurzaam, wat betekent dat dezelfde koppeling in de tijd kan worden gebruikt voor nieuwe analisten.</span><span class="sxs-lookup"><span data-stu-id="c29df-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="c29df-157">De aanvraag van de analist wordt in een wachtrij geplaatst voor goedkeuring door de **MSSP-analist-goedkeurders.**</span><span class="sxs-lookup"><span data-stu-id="c29df-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Afbeelding van access-eigenschappen](../../media/access-properties.png)

    <span data-ttu-id="c29df-159">De koppeling bevindt zich op de overzichtspagina van elk toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="c29df-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="c29df-160">Toegang beheren</span><span class="sxs-lookup"><span data-stu-id="c29df-160">Manage access</span></span> 

1. <span data-ttu-id="c29df-161">Toegangsaanvragen controleren en machtigen in myaccess klant en/of MSSP.</span><span class="sxs-lookup"><span data-stu-id="c29df-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="c29df-162">Access-aanvragen worden beheerd in de klant My Access, door leden van de groep MsSP Analyst Approvers.</span><span class="sxs-lookup"><span data-stu-id="c29df-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="c29df-163">U kunt dit doen door de myaccess van de klant te openen met behulp van:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="c29df-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="c29df-164">Voorbeeld:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="c29df-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="c29df-165">Aanvragen goedkeuren of weigeren in **de sectie Goedkeuringen** van de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="c29df-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="c29df-166">Op dit moment is de toegang tot analisten ingericht en moet elke analist toegang hebben tot het Microsoft 365-beveiligingscentrum van de klant:</span><span class="sxs-lookup"><span data-stu-id="c29df-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="c29df-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` met de machtigingen en rollen die aan hen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c29df-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c29df-168">Gedelegeerde toegang tot Microsoft Defender voor Eindpunt in het Microsoft 365-beveiligingscentrum biedt momenteel toegang tot één tenant per browservenster.</span><span class="sxs-lookup"><span data-stu-id="c29df-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span>