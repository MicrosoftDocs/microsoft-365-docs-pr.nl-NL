---
title: Activiteiten na de migratie voor de migratie vanuit Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Overzicht: Activiteiten na de migratie na de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.'
ms.openlocfilehash: 3659ce8ffa3424c3521c8f8954be88c7d53d0a51
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930413"
---
# <a name="post-migration-activities-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="80bff-103">Activiteiten na de migratie voor de migratie vanuit Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="80bff-103">Post-migration activities for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="80bff-104">De volgende secties bieden activiteiten na de migratie voor meerdere services na de overstap van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio.</span><span class="sxs-lookup"><span data-stu-id="80bff-104">The following sections provide post-migration activities for multiple services after moving from Microsoft Cloud Germany (Microsoft Cloud Deutschland) to Office 365 services in the new German datacenter region.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="80bff-105">Azure AD</span><span class="sxs-lookup"><span data-stu-id="80bff-105">Azure AD</span></span>
<!-- This AAD Endpoints comparison table could be added to the documentation, not finally decided.
### Azure AD Endpoints
**Applies to:** All customers

After the cut over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland and the endpoints cannot be used anymore. At this point, the customer needs to ensure that all applications are using the endpoints for the new German datacenter region.
The following table provides an overview about which endpoints will replace the previously used endpoints in Microsoft Cloud Germany (Microsoft Cloud Deutschland). 

|Endpoint in Microsoft Cloud Germany  |Endpoint in the new German datacenter region  |
|:---------|:---------|
|becws.microsoftonline.de<br>provisioningapi.microsoftonline.de |becws.microsoftonline.com<br>provisioningapi.microsoftonline.com |
|adminwebservice.microsoftonline.de |adminwebservice.microsoftonline.com |
|login.microsoftonline.de<br>logincert.microsoftonline.de<br>sts.microsoftonline.de |login.microsoftonline.com<br>login.windows.net<br>logincert.microsoftonline.com<br>accounts.accesscontrol.windows.net |
|enterpriseregistration.microsoftonline.de |enterpriseregistration.windows.net |
|graph.cloudapi.de |graph.windows.net |
|graph.microsoft.de |graph.microsoft.com |
|||
-->

### <a name="azure-ad-federated-authentication-with-ad-fs"></a><span data-ttu-id="80bff-106">Azure AD federatief verificatie met AD FS</span><span class="sxs-lookup"><span data-stu-id="80bff-106">Azure AD federated authentication with AD FS</span></span>
<span data-ttu-id="80bff-107">**Van toepassing op:** Alle klanten die federatief verificatie gebruiken met AD FS</span><span class="sxs-lookup"><span data-stu-id="80bff-107">**Applies to:** All customers using federated authentication with AD FS</span></span>

| <span data-ttu-id="80bff-108">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="80bff-108">Step(s)</span></span> | <span data-ttu-id="80bff-109">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="80bff-109">Description</span></span> | <span data-ttu-id="80bff-110">Gevolg</span><span class="sxs-lookup"><span data-stu-id="80bff-110">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="80bff-111">Vertrouwen van afhankelijke partijen verwijderen uit Microsoft Cloud Deutschland AD FS.</span><span class="sxs-lookup"><span data-stu-id="80bff-111">Remove relying party trusts from Microsoft Cloud Deutschland AD FS.</span></span> | <span data-ttu-id="80bff-112">Nadat de cut-over naar Azure AD is voltooid, gebruikt de organisatie volledig Office 365 services en is ze niet meer verbonden met Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="80bff-112">After the cut-over to Azure AD is complete, the organization is fully using Office 365 services and is no longer connected to Microsoft Cloud Deutschland.</span></span> <span data-ttu-id="80bff-113">Op dit moment moet de klant het vertrouwen van de vertrouwensrelatie met de Microsoft Cloud Deutschland-eindpunten verwijderen.</span><span class="sxs-lookup"><span data-stu-id="80bff-113">At this point, the customer needs to remove the relying party trust to the Microsoft Cloud Deutschland endpoints.</span></span> <span data-ttu-id="80bff-114">Dit kan alleen als geen van de toepassingen van de klant naar Microsoft Cloud Deutschland-eindpunten wijst wanneer Azure AD wordt gebruikt als idp (Identity Provider).</span><span class="sxs-lookup"><span data-stu-id="80bff-114">This can only be done when none of the customer's applications points to Microsoft Cloud Deutschland endpoints when Azure AD is leveraged as an Identity Provider (IdP).</span></span> | <span data-ttu-id="80bff-115">Federatief verificatie-organisaties</span><span class="sxs-lookup"><span data-stu-id="80bff-115">Federated Authentication organizations</span></span> | 
||||

<!--
    Question from ckinder
    The following paragraph is not clear
-->
### <a name="group-approvals"></a><span data-ttu-id="80bff-116">Groepsgoedkeuringen</span><span class="sxs-lookup"><span data-stu-id="80bff-116">Group approvals</span></span>
<span data-ttu-id="80bff-117">**Van toepassing op:** Eindgebruikers van wie de goedkeuringsaanvragen voor Azure AD-groep niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie</span><span class="sxs-lookup"><span data-stu-id="80bff-117">**Applies to:** End-users whose Azure AD group approval requests weren't approved in the last 30 days before migration</span></span> 

| <span data-ttu-id="80bff-118">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="80bff-118">Step(s)</span></span> | <span data-ttu-id="80bff-119">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="80bff-119">Description</span></span> | <span data-ttu-id="80bff-120">Gevolg</span><span class="sxs-lookup"><span data-stu-id="80bff-120">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="80bff-121">Aanvragen om deel te nemen aan een Azure AD-groep in de afgelopen 30 dagen vóór de migratie, moeten opnieuw worden aangevraagd als de oorspronkelijke aanvraag niet is goedgekeurd.</span><span class="sxs-lookup"><span data-stu-id="80bff-121">Requests to join an Azure AD group in the last 30 days before migration will need to be requested again if the original request wasn't approved.</span></span> | <span data-ttu-id="80bff-122">Eindgebruikers moeten het Access-deelvenster gebruiken om opnieuw een aanvraag in te dienen om deel te nemen aan een Azure AD-groep als deze aanvragen niet zijn goedgekeurd in de laatste 30 dagen vóór de migratie.</span><span class="sxs-lookup"><span data-stu-id="80bff-122">End-user customers will need to use the Access panel to submit a request to join an Azure AD group again if those requests weren't approved in the last 30 days before the migration.</span></span> |  <span data-ttu-id="80bff-123">Als eindgebruiker:</span><span class="sxs-lookup"><span data-stu-id="80bff-123">As an end-user:</span></span> <ol><li><span data-ttu-id="80bff-124">Ga naar [het Access-deelvenster](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span><span class="sxs-lookup"><span data-stu-id="80bff-124">Navigate to [Access panel](https://account.activedirectory.windowsazure.com/r#/joinGroups).</span></span></li><li><span data-ttu-id="80bff-125">Zoek een Azure AD-groep waarvoor lidmaatschapsgoedkeuring in behandeling was gedurende de 30 dagen vóór de migratie.</span><span class="sxs-lookup"><span data-stu-id="80bff-125">Find an Azure AD group for which membership approval was pending during the 30 days before migration.</span></span></li><li><span data-ttu-id="80bff-126">Vraag om opnieuw deel te nemen aan de Azure AD-groep.</span><span class="sxs-lookup"><span data-stu-id="80bff-126">Request to join the Azure AD group again.</span></span></li></ol> <span data-ttu-id="80bff-127">Aanvragen om deel te nemen aan een groep die minder dan 30 dagen vóór de migratie actief zijn, kunnen niet worden goedgekeurd, tenzij ze na de migratie opnieuw worden aangevraagd.</span><span class="sxs-lookup"><span data-stu-id="80bff-127">Requests to join a group that are active less than 30 days before migration cannot be approved, unless they're requested again after migration.</span></span> |
||||

## <a name="custom-dns-updates"></a><span data-ttu-id="80bff-128">Aangepaste DNS-updates</span><span class="sxs-lookup"><span data-stu-id="80bff-128">Custom DNS updates</span></span>
<span data-ttu-id="80bff-129">**Van toepassing op:**  Alle klanten die hun eigen DNS-zones beheren</span><span class="sxs-lookup"><span data-stu-id="80bff-129">**Applies to:**  All customer managing their own DNS zones</span></span>

| <span data-ttu-id="80bff-130">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="80bff-130">Step(s)</span></span> | <span data-ttu-id="80bff-131">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="80bff-131">Description</span></span> | <span data-ttu-id="80bff-132">Gevolg</span><span class="sxs-lookup"><span data-stu-id="80bff-132">Impact</span></span> |
|:------|:-------|:-------|
| <span data-ttu-id="80bff-133">On-premises DNS-services bijwerken voor Office 365 services-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="80bff-133">Update on-premises DNS services for Office 365 services endpoints.</span></span> | <span data-ttu-id="80bff-134">Door klanten beheerde DNS-vermeldingen die naar Microsoft Cloud Deutschland wijzen, moeten worden bijgewerkt om te wijzen naar de Office 365 global services-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="80bff-134">Customer-managed DNS entries that point to Microsoft Cloud Deutschland need to be updated to point to the Office 365 Global services endpoints.</span></span> <span data-ttu-id="80bff-135">Raadpleeg Domeinen [in het Microsoft 365 beheercentrum](https://admin.microsoft.com/Adminportal/Home#/Domains) en pas de wijzigingen in uw DNS-configuratie toe.</span><span class="sxs-lookup"><span data-stu-id="80bff-135">Please refer to [Domains in the Microsoft 365 admin center](https://admin.microsoft.com/Adminportal/Home#/Domains) and apply the changes in your DNS configuration.</span></span> | <span data-ttu-id="80bff-136">Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients.</span><span class="sxs-lookup"><span data-stu-id="80bff-136">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||

## <a name="third-party-services"></a><span data-ttu-id="80bff-137">Services van derden</span><span class="sxs-lookup"><span data-stu-id="80bff-137">Third-party services</span></span>
<span data-ttu-id="80bff-138">**Van toepassing op:** Klanten die services van derden gebruiken voor Office 365 services-eindpunten</span><span class="sxs-lookup"><span data-stu-id="80bff-138">**Applies to:** Customers using third-party services for Office 365 services endpoints</span></span>

| <span data-ttu-id="80bff-139">Stap(en)</span><span class="sxs-lookup"><span data-stu-id="80bff-139">Step(s)</span></span> | <span data-ttu-id="80bff-140">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="80bff-140">Description</span></span> | <span data-ttu-id="80bff-141">Gevolg</span><span class="sxs-lookup"><span data-stu-id="80bff-141">Impact</span></span> |
|:-------|:-------|:-------|
| <span data-ttu-id="80bff-142">Werk partners en services van derden bij voor Office 365 services-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="80bff-142">Update partners and third-party services for Office 365 services endpoints.</span></span> | <ul><li><span data-ttu-id="80bff-143">Services en partners van derden die naar Duitsland Office 365, moeten worden bijgewerkt om te wijzen Office 365 services-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="80bff-143">Third-party services and partners that point to Office 365 Germany need to be updated to point to the Office 365 services endpoints.</span></span> <span data-ttu-id="80bff-144">Voorbeeld: Registreer opnieuw, in overeenstemming met uw leveranciers en partners, de galerie-app-versie van toepassingen, indien beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="80bff-144">Example: Re-register, in alignment with your vendors and partners, the gallery app version of applications, if available.</span></span> </li><li><span data-ttu-id="80bff-145">Wijs alle aangepaste toepassingen aan die gebruikmaken Graph API van `graph.microsoft.de` naar `graph.microsoft.com` .</span><span class="sxs-lookup"><span data-stu-id="80bff-145">Point all custom applications that leverage Graph API from `graph.microsoft.de` to `graph.microsoft.com`.</span></span> <span data-ttu-id="80bff-146">Andere API's met gewijzigde eindpunten moeten ook worden bijgewerkt, als ze worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="80bff-146">Other APIs with changed endpoints also need to be updated, if leveraged.</span></span> </li><li><span data-ttu-id="80bff-147">Wijzig alle niet-first-party enterprise-toepassingen om om te leiden naar de wereldwijde eindpunten.</span><span class="sxs-lookup"><span data-stu-id="80bff-147">Change all non-first-party enterprise applications to redirect to the worldwide endpoints.</span></span> </li></ul>| <span data-ttu-id="80bff-148">Vereiste actie.</span><span class="sxs-lookup"><span data-stu-id="80bff-148">Required action.</span></span> <span data-ttu-id="80bff-149">Als u dit niet doet, kan dit leiden tot een fout van de service of van software-clients.</span><span class="sxs-lookup"><span data-stu-id="80bff-149">Failure to do so may result in failure of the service or of software clients.</span></span> |
||||