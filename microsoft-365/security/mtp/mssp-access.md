---
title: Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum
description: Meer informatie over wijzigingen van het Microsoft Defender-beveiligingscentrum in het Microsoft 365-beveiligingscentrum
keywords: Aan de slag met het Microsoft 365-beveiligingscentrum, OATP, MDATP, MDO, MDE, één deelvenster met glas, geconvergeerde portal, beveiligingsportal, defender-beveiligingsportal
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: 96d5a3bdbd0acbf428f01cc3bb5afefaa95950b4
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242939"
---
# <a name="provide-managed-security-service-provider-mssp-access"></a><span data-ttu-id="156ab-104">MsSP-toegang (Managed Security Service Provider) bieden</span><span class="sxs-lookup"><span data-stu-id="156ab-104">Provide managed security service provider (MSSP) access</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="156ab-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="156ab-105">**Applies to:**</span></span>

- [<span data-ttu-id="156ab-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="156ab-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
- [<span data-ttu-id="156ab-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="156ab-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

<span data-ttu-id="156ab-108">Als u een oplossing voor gedelegeerde toegang met meerdere tenants wilt implementeren, voert u de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="156ab-108">To implement a multi-tenant delegated access solution, take the following steps:</span></span>

1. <span data-ttu-id="156ab-109">Schakel [toegangsbeheer op basis van rollen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in in het Microsoft 365-beveiligingscentrum en maak verbinding met Azure Active Directory-groepen (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="156ab-109">Enable [role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac) in Defender for Endpoint in Microsoft 365 security center and connect with Azure Active Directory (Azure AD) groups.</span></span>

2. <span data-ttu-id="156ab-110">Configureer [Beheerbeheertoegangspakketten voor toegangsaanvraag](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) en inrichting.</span><span class="sxs-lookup"><span data-stu-id="156ab-110">Configure [Governance Access Packages](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) for access request and provisioning.</span></span>

3. <span data-ttu-id="156ab-111">Beheer toegangsaanvragen en audits in [Microsoft Myaccess.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve)</span><span class="sxs-lookup"><span data-stu-id="156ab-111">Manage access requests and audits in [Microsoft Myaccess](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-request-approve).</span></span>

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint-in-microsoft-365-security-center"></a><span data-ttu-id="156ab-112">Toegangsbesturingselementen op basis van rollen inschakelen in Microsoft Defender for Endpoint in het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="156ab-112">Enable role-based access controls in Microsoft Defender for Endpoint in Microsoft 365 security center</span></span>

1. <span data-ttu-id="156ab-113">**Toegangsgroepen maken voor MSSP-resources in AAD klant: groepen**</span><span class="sxs-lookup"><span data-stu-id="156ab-113">**Create access groups for MSSP resources in Customer AAD: Groups**</span></span>

    <span data-ttu-id="156ab-114">Deze groepen worden gekoppeld aan de rollen die u maakt in Defender voor eindpunt in het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="156ab-114">These groups will be linked to the Roles you create in Defender for Endpoint in Microsoft 365 security center.</span></span> <span data-ttu-id="156ab-115">Maak in de AD-tenant van de klant drie groepen.</span><span class="sxs-lookup"><span data-stu-id="156ab-115">To do so, in the customer AD tenant, create three groups.</span></span> <span data-ttu-id="156ab-116">In onze voorbeeldbenadering maken we de volgende groepen:</span><span class="sxs-lookup"><span data-stu-id="156ab-116">In our example approach, we create the following groups:</span></span>

    - <span data-ttu-id="156ab-117">Laag 1-analist</span><span class="sxs-lookup"><span data-stu-id="156ab-117">Tier 1 Analyst</span></span> 
    - <span data-ttu-id="156ab-118">Laag 2-analist</span><span class="sxs-lookup"><span data-stu-id="156ab-118">Tier 2 Analyst</span></span> 
    - <span data-ttu-id="156ab-119">MSSP-analist goedkeurders</span><span class="sxs-lookup"><span data-stu-id="156ab-119">MSSP Analyst Approvers</span></span>  


2. <span data-ttu-id="156ab-120">Maak Defender voor eindpuntrollen voor de juiste toegangsniveaus in Customer Defender voor het eindpunt in de rollen en groepen van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="156ab-120">Create Defender for Endpoint roles for appropriate access levels in Customer Defender for Endpoint in Microsoft 365 security center roles and groups.</span></span>

    <span data-ttu-id="156ab-121">Om RBAC in teschakelen in het Microsoft 365-beveiligingscentrum van de klant, hebben de rollen machtigingen > eindpunten & groepen **> Rollen** met een gebruikersaccount met de rechten van globale beheerders > beveiligingsbeheerders.</span><span class="sxs-lookup"><span data-stu-id="156ab-121">To enable RBAC in the customer Microsoft 365 security center, access **Permissions >  Endpoints roles & groups > Roles** with a user account with Global Administrator or Security Administrator rights.</span></span>

    ![Afbeelding van MSSP-toegang](../../media/mssp-access.png)

    <span data-ttu-id="156ab-123">Maak vervolgens RBAC-rollen om te voldoen aan de behoeften van MSSP SOC Tier.</span><span class="sxs-lookup"><span data-stu-id="156ab-123">Then, create RBAC roles to meet MSSP SOC Tier needs.</span></span> <span data-ttu-id="156ab-124">Koppel deze rollen aan de gemaakte gebruikersgroepen via Toegewezen gebruikersgroepen.</span><span class="sxs-lookup"><span data-stu-id="156ab-124">Link these roles to the created user groups via "Assigned user groups".</span></span>

    <span data-ttu-id="156ab-125">Twee mogelijke rollen:</span><span class="sxs-lookup"><span data-stu-id="156ab-125">Two possible roles:</span></span>

    - <span data-ttu-id="156ab-126">**Laag 1-analisten**</span><span class="sxs-lookup"><span data-stu-id="156ab-126">**Tier 1 Analysts**</span></span> <br>
      <span data-ttu-id="156ab-127">Alle acties uitvoeren, met uitzondering van live antwoorden en beveiligingsinstellingen beheren.</span><span class="sxs-lookup"><span data-stu-id="156ab-127">Perform all actions except for live response and manage security settings.</span></span>

    - <span data-ttu-id="156ab-128">**Laag 2-analisten**</span><span class="sxs-lookup"><span data-stu-id="156ab-128">**Tier 2 Analysts**</span></span> <br>
      <span data-ttu-id="156ab-129">Laag 1-mogelijkheden met de toevoeging aan [live-antwoorden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="156ab-129">Tier 1 capabilities with the addition to [live response](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span></span>

    <span data-ttu-id="156ab-130">Zie Toegangsbeheer op basis van rollen [gebruiken voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)</span><span class="sxs-lookup"><span data-stu-id="156ab-130">For more information, see [Use role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac).</span></span>



## <a name="configure-governance-access-packages"></a><span data-ttu-id="156ab-131">Toegangspakketten voor beheerbeheer configureren</span><span class="sxs-lookup"><span data-stu-id="156ab-131">Configure Governance Access Packages</span></span>

1.  <span data-ttu-id="156ab-132">**MSSP toevoegen als verbonden organisatie in AAD klant: identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="156ab-132">**Add MSSP as Connected Organization in Customer AAD: Identity Governance**</span></span>
    
    <span data-ttu-id="156ab-133">Als u de MSSP toevoegt als verbonden organisatie, kan de MSSP aanvragen en toegang krijgen.</span><span class="sxs-lookup"><span data-stu-id="156ab-133">Adding the MSSP as a connected organization will allow the MSSP to request and have accesses provisioned.</span></span> 

    <span data-ttu-id="156ab-134">Dit doet u door in de AD-tenant van de klant identiteitsbeheer te openen: verbonden organisatie.</span><span class="sxs-lookup"><span data-stu-id="156ab-134">To do so, in the customer AD tenant, access Identity Governance: Connected organization.</span></span> <span data-ttu-id="156ab-135">Voeg een nieuwe organisatie toe en zoek naar uw MSSP Analyst-tenant via tenant-id of domein.</span><span class="sxs-lookup"><span data-stu-id="156ab-135">Add a new organization and search for your MSSP Analyst tenant via Tenant ID or Domain.</span></span> <span data-ttu-id="156ab-136">We raden u aan een afzonderlijke AD-tenant te maken voor uw MSSP-analisten.</span><span class="sxs-lookup"><span data-stu-id="156ab-136">We suggest creating a separate AD tenant for your MSSP Analysts.</span></span>

2. <span data-ttu-id="156ab-137">**Een resourcecatalogus maken in Klant-AAD: Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="156ab-137">**Create a resource catalog in Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="156ab-138">Resourcecatalogi zijn een logische verzameling toegangspakketten die zijn gemaakt in de AD-tenant van de klant.</span><span class="sxs-lookup"><span data-stu-id="156ab-138">Resource catalogs are a logical collection of access packages, created in the customer AD tenant.</span></span>

    <span data-ttu-id="156ab-139">Dit doet u door in de AD-tenant van de klant identiteitsbeheer te openen: Catalogi en Nieuwe catalogus **toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="156ab-139">To do so, in the customer AD tenant,  access Identity Governance: Catalogs, and add **New Catalog**.</span></span> <span data-ttu-id="156ab-140">In ons voorbeeld noemen we dit **MSSP Accesses.**</span><span class="sxs-lookup"><span data-stu-id="156ab-140">In our example, we will call it **MSSP Accesses**.</span></span> 

    ![Afbeelding van nieuwe catalogus](../../media/goverance-catalog.png)

    <span data-ttu-id="156ab-142">Zie Een catalogus [met resources maken voor meer informatie.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create)</span><span class="sxs-lookup"><span data-stu-id="156ab-142">Further more information, see [Create a catalog of resources](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-catalog-create).</span></span>


3. <span data-ttu-id="156ab-143">**Maak toegangspakketten voor MSSP-resources Klant AAD: Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="156ab-143">**Create access packages for MSSP resources Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="156ab-144">Access-pakketten zijn de verzameling rechten en toegangen die een aanvragende krijgt na goedkeuring.</span><span class="sxs-lookup"><span data-stu-id="156ab-144">Access packages are the collection of rights and accesses that a requestor will be granted upon approval.</span></span> 

    <span data-ttu-id="156ab-145">Dit doet u door in de AD-tenant van de klant identiteitsbeheer te openen: Access-pakketten en **nieuw toegangspakket toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="156ab-145">To do so, in the customer AD tenant, access Identity Governance: Access Packages, and add **New Access Package**.</span></span> <span data-ttu-id="156ab-146">Maak een toegangspakket voor de MSSP-goedkeurders en elke analistlaag.</span><span class="sxs-lookup"><span data-stu-id="156ab-146">Create an access package for the MSSP approvers and each analyst tier.</span></span> <span data-ttu-id="156ab-147">Met de volgende Laag 1-analistenconfiguratie wordt bijvoorbeeld een toegangspakket gemaakt dat:</span><span class="sxs-lookup"><span data-stu-id="156ab-147">For example, the following Tier 1 Analyst configuration creates an access package that:</span></span>

    - <span data-ttu-id="156ab-148">Vereist een lid van de **MSSP-analist van de AD-groep om** nieuwe aanvragen te kunnen goedkeuren</span><span class="sxs-lookup"><span data-stu-id="156ab-148">Requires a member of the AD group **MSSP Analyst Approvers** to authorize new requests</span></span>
    - <span data-ttu-id="156ab-149">Heeft jaarlijkse toegangsbeoordelingen, waarbij de SOC-analisten een toegangsuitbreiding kunnen aanvragen</span><span class="sxs-lookup"><span data-stu-id="156ab-149">Has annual access reviews, where the SOC analysts can request an access extension</span></span>
    - <span data-ttu-id="156ab-150">Kan alleen worden aangevraagd door gebruikers in de MSSP SOC-tenant</span><span class="sxs-lookup"><span data-stu-id="156ab-150">Can only be requested by users in the MSSP SOC Tenant</span></span>
    - <span data-ttu-id="156ab-151">Access verloopt automatisch na 365 dagen</span><span class="sxs-lookup"><span data-stu-id="156ab-151">Access auto expires after 365 days</span></span>

    ![Afbeelding van nieuw toegangspakket](../../media/new-access-package.png)

    <span data-ttu-id="156ab-153">Zie Een nieuw [toegangspakket maken voor meer informatie.](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create)</span><span class="sxs-lookup"><span data-stu-id="156ab-153">For more information, see [Create a new access package](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-access-package-create).</span></span>


4. <span data-ttu-id="156ab-154">**Koppeling voor toegangsaanvraag naar MSSP-resources bieden vanuit Klant AAD: Identiteitsbeheer**</span><span class="sxs-lookup"><span data-stu-id="156ab-154">**Provide access request link to MSSP resources from Customer AAD: Identity Governance**</span></span>

    <span data-ttu-id="156ab-155">De koppeling mijn toegangsportal wordt gebruikt door MSSP SOC-analisten om toegang aan te vragen via de gemaakte toegangspakketten.</span><span class="sxs-lookup"><span data-stu-id="156ab-155">The My Access portal link is used by MSSP SOC analysts to request access via the access packages created.</span></span> <span data-ttu-id="156ab-156">De koppeling is langer durend, wat betekent dat dezelfde koppeling in de tijd kan worden gebruikt voor nieuwe analisten.</span><span class="sxs-lookup"><span data-stu-id="156ab-156">The link is durable, meaning the same link may be used over time for new analysts.</span></span> <span data-ttu-id="156ab-157">Het verzoek van de analist wordt ter goedkeuring in een wachtrij geplaatst door de **MSSP-analist Goedkeurders.**</span><span class="sxs-lookup"><span data-stu-id="156ab-157">The analyst request goes into a queue for approval by the **MSSP Analyst Approvers**.</span></span>


    ![Afbeelding van eigenschappen van access](../../media/access-properties.png)

    <span data-ttu-id="156ab-159">De koppeling bevindt zich op de overzichtspagina van elk toegangspakket.</span><span class="sxs-lookup"><span data-stu-id="156ab-159">The link is located on the overview page of each access package.</span></span>

## <a name="manage-access"></a><span data-ttu-id="156ab-160">Toegang beheren</span><span class="sxs-lookup"><span data-stu-id="156ab-160">Manage access</span></span> 

1. <span data-ttu-id="156ab-161">Bekijk en autor geef toestemming voor toegangsaanvragen in Klant en/of MSSP myaccess.</span><span class="sxs-lookup"><span data-stu-id="156ab-161">Review and authorize access requests in Customer and/or MSSP myaccess.</span></span>

    <span data-ttu-id="156ab-162">Toegangsaanvragen worden beheerd in De klant Mijn toegang, door leden van de groep Goedkeurders voor MSSP-analisten.</span><span class="sxs-lookup"><span data-stu-id="156ab-162">Access requests are managed in the customer My Access, by members of the MSSP Analyst Approvers group.</span></span>

    <span data-ttu-id="156ab-163">U doet dit door de myaccess van de klant te openen met behulp van: `https://myaccess.microsoft.com/@<Customer Domain >`</span><span class="sxs-lookup"><span data-stu-id="156ab-163">To do so, access the customer's myaccess using:  `https://myaccess.microsoft.com/@<Customer Domain >`.</span></span> 

    <span data-ttu-id="156ab-164">Voorbeeld:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span><span class="sxs-lookup"><span data-stu-id="156ab-164">Example:  `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`</span></span>   
2. <span data-ttu-id="156ab-165">Verzoeken goedkeuren of weigeren in **de sectie Goedkeuringen** van de gebruikersinterface.</span><span class="sxs-lookup"><span data-stu-id="156ab-165">Approve or deny requests in the **Approvals** section of the UI.</span></span>

     <span data-ttu-id="156ab-166">Op dit moment is toegang tot de analisten ingericht en moet elke analist toegang hebben tot het Microsoft 365-beveiligingscentrum van de klant:</span><span class="sxs-lookup"><span data-stu-id="156ab-166">At this point, analyst access has been provisioned, and each analyst should be able to access the customer's Microsoft 365 Security Center:</span></span> 

    <span data-ttu-id="156ab-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` met de machtigingen en rollen die aan hen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="156ab-167">`https://security.microsoft.com/?tid=<CustomerTenantId>` with the permissions and roles they were assigned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="156ab-168">Gedelegeerde toegang tot Microsoft Defender voor eindpunt in het Microsoft 365-beveiligingscentrum biedt op dit moment toegang tot één tenant per browservenster.</span><span class="sxs-lookup"><span data-stu-id="156ab-168">Delegated access to Microsoft Defender for Endpoint in the Microsoft 365 security center currently allows access to a single tenant per browser window.</span></span> 