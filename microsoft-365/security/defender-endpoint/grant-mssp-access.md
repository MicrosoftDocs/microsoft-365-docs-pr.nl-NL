---
title: Toegang verlenen aan een beheerde beveiligingsserviceprovider (MSSP)
description: Neem de benodigde stappen voor het configureren van MSSP-integratie met de MICROSOFT Defender ATP
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1bb7bc3565bbb7c05f165c5649f3672ff33bb18b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165451"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a><span data-ttu-id="43ac5-104">Toegang verlenen voor beheerde beveiligingsserviceproviders (MSSP) (preview)</span><span class="sxs-lookup"><span data-stu-id="43ac5-104">Grant managed security service provider (MSSP) access (preview)</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="43ac5-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="43ac5-105">**Applies to:**</span></span>
- [<span data-ttu-id="43ac5-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="43ac5-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="43ac5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="43ac5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="43ac5-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="43ac5-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="43ac5-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="43ac5-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)

>[!IMPORTANT] 
><span data-ttu-id="43ac5-110">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="43ac5-110">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="43ac5-111">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="43ac5-111">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="43ac5-112">Als u een oplossing voor gedelegeerde toegang met meerdere tenants wilt implementeren, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="43ac5-112">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="43ac5-113">Schakel [toegangsbeheer op basis van rollen](rbac.md) in defender voor eindpunt in en maak verbinding met Ad-groepen (Active Directory).</span><span class="sxs-lookup"><span data-stu-id="43ac5-113">Enable [role-based access control](rbac.md) in Defender for Endpoint and connect with Active Directory (AD) groups.</span></span>

2. <span data-ttu-id="43ac5-114">[Beheertoegangspakketten configureren voor toegangsaanvraag](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) en inrichting.</span><span class="sxs-lookup"><span data-stu-id="43ac5-114">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="43ac5-115">Toegangsaanvragen en -audits beheren in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span><span class="sxs-lookup"><span data-stu-id="43ac5-115">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="43ac5-116">Toegangsbesturingselementen op basis van rollen inschakelen in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="43ac5-116">Enable role-based access controls in Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="43ac5-117">**Toegangsgroepen maken voor MSSP-resources in Klant-AAD: Groepen**</span><span class="sxs-lookup"><span data-stu-id="43ac5-117">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="43ac5-118">Deze groepen worden gekoppeld aan de rollen die u maakt in Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="43ac5-118">These groups will be linked to the Roles you create in Defender for Endpoint.</span></span> <span data-ttu-id="43ac5-119">Maak in de ad-tenant van de klant drie groepen om dit te doen.</span><span class="sxs-lookup"><span data-stu-id="43ac5-119">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="43ac5-120">In onze voorbeeldbenadering maken we de volgende groepen:</span><span class="sxs-lookup"><span data-stu-id="43ac5-120">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="43ac5-121">Tier 1 Analyst</span><span class="sxs-lookup"><span data-stu-id="43ac5-121">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="43ac5-122">Tier 2 Analyst</span><span class="sxs-lookup"><span data-stu-id="43ac5-122">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="43ac5-123">MSSP-analist-goedkeurders</span><span class="sxs-lookup"><span data-stu-id="43ac5-123">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="43ac5-124">Maak Defender voor eindpuntrollen voor de juiste toegangsniveaus in Customer Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="43ac5-124">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint.</span></span>

    <span data-ttu-id="43ac5-125">Als u RBAC wilt inschakelen in het Microsoft Defender-beveiligingscentrum van de klant, hebt u toegang tot Instellingen **> Machtigingen > Rollen** en 'Rollen inschakelen', vanuit een gebruikersaccount met globale beheerders- of beveiligingsbeheerdersrechten.</span><span class="sxs-lookup"><span data-stu-id="43ac5-125">To enable RBAC in the customer Microsoft Defender Security Center, access **Settings > Permissions > Roles** and "Turn on roles", from a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Afbeelding van MSSP-toegang](images/mssp-access.png)

    <span data-ttu-id="43ac5-127">Maak vervolgens RBAC-rollen om te voldoen aan de soc-laagbehoeften van MSSP.</span><span class="sxs-lookup"><span data-stu-id="43ac5-127">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="43ac5-128">Koppel deze rollen aan de gemaakte gebruikersgroepen via 'Toegewezen gebruikersgroepen'.</span><span class="sxs-lookup"><span data-stu-id="43ac5-128">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="43ac5-129">Twee mogelijke rollen:</span><span class="sxs-lookup"><span data-stu-id="43ac5-129">Two possible roles:</span></span>

    - <span data-ttu-id="43ac5-130">**Tier 1-analisten**</span><span class="sxs-lookup"><span data-stu-id="43ac5-130">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="43ac5-131">Voer alle acties uit, behalve livereacties en beheer beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="43ac5-131">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="43ac5-132">**Laag 2-analisten**</span><span class="sxs-lookup"><span data-stu-id="43ac5-132">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="43ac5-133">Tier 1-mogelijkheden met de toevoeging aan [livereactie](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="43ac5-133">Tier 1 capabilities with the addition to [live response](live-response.md)</span></span>

    <span data-ttu-id="43ac5-134">Zie Op rollen gebaseerde [toegangsbeheer gebruiken](rbac.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="43ac5-134">For more information, see [Use role-based access control](rbac.md).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="43ac5-135">Governance Access-pakketten configureren</span><span class="sxs-lookup"><span data-stu-id="43ac5-135">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="43ac5-136">**MSSP toevoegen als verbonden organisatie in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="43ac5-136">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="43ac5-137">Als u mssp toevoegt als een verbonden organisatie, kan de MSSP aanvragen en toegang hebben tot de inrichting.</span><span class="sxs-lookup"><span data-stu-id="43ac5-137">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="43ac5-138">Als u dit wilt doen, krijgt u in de ad-tenant van de klant toegang tot Identiteitsbeheer: Verbonden organisatie.</span><span class="sxs-lookup"><span data-stu-id="43ac5-138">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="43ac5-139">Voeg een nieuwe organisatie toe en zoek naar uw MSSP Analyst-tenant via tenant-id of domein.</span><span class="sxs-lookup"><span data-stu-id="43ac5-139">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="43ac5-140">We raden u aan een aparte AD-tenant te maken voor uw MSSP-analisten.</span><span class="sxs-lookup"><span data-stu-id="43ac5-140">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="43ac5-141">**Een resourcecatalogus maken in Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="43ac5-141">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43ac5-142">Resourcecatalogi zijn een logische verzameling toegangspakketten die zijn gemaakt in de AD-tenant van de klant.</span><span class="sxs-lookup"><span data-stu-id="43ac5-142">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="43ac5-143">U doet dit door in de AD-tenant van de klant identiteitsbeheer: catalogi te openen en Nieuwe catalogus **toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="43ac5-143">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="43ac5-144">In ons voorbeeld noemen we het **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="43ac5-144">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Afbeelding van nieuwe catalogus](images/goverance-catalog.png)

    <span data-ttu-id="43ac5-146">Zie Een catalogus met resources maken voor [meer informatie.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="43ac5-146">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="43ac5-147">**Access-pakketten maken voor MSSP-resources Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="43ac5-147">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43ac5-148">Access-pakketten zijn de verzameling rechten en toegangen die een aangever na goedkeuring wordt verleend.</span><span class="sxs-lookup"><span data-stu-id="43ac5-148">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="43ac5-149">U doet dit door in de AD-tenant van de klant identiteitsbeheer: Access-pakketten te openen en Nieuw **Access-pakket toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="43ac5-149">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="43ac5-150">Maak een toegangspakket voor de MSSP-goedkeurders en elke analistlaag.</span><span class="sxs-lookup"><span data-stu-id="43ac5-150">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="43ac5-151">Met de volgende configuratie van Tier 1 Analyst wordt bijvoorbeeld een toegangspakket gemaakt dat:</span><span class="sxs-lookup"><span data-stu-id="43ac5-151">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="43ac5-152">Vereist dat een lid van de AD-groep **MSSP Analyst Approvers** nieuwe aanvragen autorizert</span><span class="sxs-lookup"><span data-stu-id="43ac5-152">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="43ac5-153">Heeft jaarlijkse toegangsbeoordelingen, waarbij de SOC-analisten een toegangsextensie kunnen aanvragen</span><span class="sxs-lookup"><span data-stu-id="43ac5-153">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="43ac5-154">Kan alleen worden aangevraagd door gebruikers in de SOC-tenant van MSSP</span><span class="sxs-lookup"><span data-stu-id="43ac5-154">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="43ac5-155">Access Auto verloopt na 365 dagen</span><span class="sxs-lookup"><span data-stu-id="43ac5-155">Access auto expires after 365 days</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="43ac5-156">![Afbeelding van nieuw toegangspakket](images/new-access-package.png)</span><span class="sxs-lookup"><span data-stu-id="43ac5-156">![Image of new access package](images/new-access-package.png)</span></span>

    <span data-ttu-id="43ac5-157">Zie Een nieuw [toegangspakket maken](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="43ac5-157">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="43ac5-158">**Koppeling voor toegangsaanvraag naar MSSP-resources van Customer AAD: Identity Governance**</span><span class="sxs-lookup"><span data-stu-id="43ac5-158">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="43ac5-159">De koppeling Mijn Access-portal wordt door MSSP-SOC-analisten gebruikt om toegang te vragen via de gemaakte toegangspakketten.</span><span class="sxs-lookup"><span data-stu-id="43ac5-159">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="43ac5-160">De koppeling is duurzaam, wat betekent dat dezelfde koppeling in de tijd kan worden gebruikt voor nieuwe analisten.</span><span class="sxs-lookup"><span data-stu-id="43ac5-160">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="43ac5-161">De aanvraag van de analist wordt in een wachtrij geplaatst voor goedkeuring door de **MSSP-analist-goedkeurders.**</span><span class="sxs-lookup"><span data-stu-id="43ac5-161">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="43ac5-162">![Afbeelding van access-eigenschappen](images/access-properties.png)</span><span class="sxs-lookup"><span data-stu-id="43ac5-162">![Image of access properties](images/access-properties.png)</span></span>

    <span data-ttu-id="43ac5-163">De koppeling bevindt zich op de overzichtspagina van elk toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="43ac5-163">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="43ac5-164">Toegang beheren</span><span class="sxs-lookup"><span data-stu-id="43ac5-164">Manage access</span></span> 

1. <span data-ttu-id="43ac5-165">Toegangsaanvragen controleren en machtigen in myaccess klant en/of MSSP.</span><span class="sxs-lookup"><span data-stu-id="43ac5-165">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="43ac5-166">Access-aanvragen worden beheerd in de klant My Access, door leden van de groep MsSP Analyst Approvers.</span><span class="sxs-lookup"><span data-stu-id="43ac5-166">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="43ac5-167">U kunt dit doen door de myaccess van de klant te openen met behulp van:  `https://myaccess.microsoft.com/@<Customer Domain >` .</span><span class="sxs-lookup"><span data-stu-id="43ac5-167">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="43ac5-168">Voorbeeld:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="43ac5-168">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="43ac5-169">Aanvragen goedkeuren of weigeren in **de sectie Goedkeuringen** van de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="43ac5-169">Approve or deny requests in the **Approvals** section of the UI.</span></span>

    <span data-ttu-id="43ac5-170">Op dit moment is de toegang tot analisten ingericht en moet elke analist toegang hebben tot het Microsoft Defender-beveiligingscentrum van de klant: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span><span class="sxs-lookup"><span data-stu-id="43ac5-170">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft Defender Security Center: `https://securitycenter.Microsoft.com/?tid=<CustomerTenantId>`</span></span>

## <a name="related-topics"></a><span data-ttu-id="43ac5-171">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="43ac5-171">Related topics</span></span>
- [<span data-ttu-id="43ac5-172">Toegang tot de MSSP-klantportal</span><span class="sxs-lookup"><span data-stu-id="43ac5-172">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="43ac5-173">Waarschuwingsmeldingen configureren</span><span class="sxs-lookup"><span data-stu-id="43ac5-173">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="43ac5-174">Waarschuwingen ophalen van klant tenant</span><span class="sxs-lookup"><span data-stu-id="43ac5-174">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)



 

