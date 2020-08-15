---
title: Beheerfuncties voor toegankelijkheid in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Dit artikel bevat een overzicht van de beheerbare besturingselementen en gegevens categorisatie in Microsoft 365.
ms.openlocfilehash: b5063f89e89b6cffffda53a5df3088a80f89c242
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689001"
---
# <a name="administrative-access-controls-in-microsoft-365"></a><span data-ttu-id="2987f-103">Beheerfuncties voor toegankelijkheid in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2987f-103">Administrative access controls in Microsoft 365</span></span> 

<span data-ttu-id="2987f-104">Microsoft heeft sterk geïnvesteerd in systemen en besturingselementen waarmee de meeste Microsoft 365-bewerkingen worden geautomatiseerd en de toegang tot de inhoud van klanten door Microsoft wordt beperkt.</span><span class="sxs-lookup"><span data-stu-id="2987f-104">Microsoft has invested heavily in systems and controls that automate most Microsoft 365 operations while intentionally limiting access to customer content by Microsoft.</span></span> <span data-ttu-id="2987f-105">Mensen die de service beheersen, en software exploiteert de dienst.</span><span class="sxs-lookup"><span data-stu-id="2987f-105">Humans govern the service, and software operates the service.</span></span> <span data-ttu-id="2987f-106">Daardoor kan Microsoft Microsoft 365 beheren op schaal en de Risico's van interne bedreigingen voor klant inhoud beheren.</span><span class="sxs-lookup"><span data-stu-id="2987f-106">This enables Microsoft to manage Microsoft 365 at scale and manage the risks of internal threats to customer content.</span></span>

<span data-ttu-id="2987f-107">Standaard hebben Microsoft-technici een beheerdersbevoegdheid voor de permanente beheerder en is er geen toegang tot de inhoud van klanten in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2987f-107">By default, Microsoft engineers have zero standing administrative privileges and zero standing access to customer content in Microsoft 365.</span></span> <span data-ttu-id="2987f-108">Een Microsoft-engineer kan de inhoud van een klant beperkt, gecontroleerd en beveiligd zijn gedurende een beperkte periode.</span><span class="sxs-lookup"><span data-stu-id="2987f-108">A Microsoft engineer can have limited, audited, and secured access to a customer's content for a limited amount of time.</span></span> <span data-ttu-id="2987f-109">Access is alleen indien nodig voor serviceactiviteiten en alleen wanneer deze is goedgekeurd door een lid van Microsoft Senior Management.</span><span class="sxs-lookup"><span data-stu-id="2987f-109">Access is only when necessary for service operations and only when approved by a member of Microsoft senior management.</span></span> <span data-ttu-id="2987f-110">Voor klanten-lockbox-licenties biedt de klant toestemming voor toegang tot de inhoud van de klant in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2987f-110">For Customer Lockbox licensed customers, the customer provides access approval to their content hosted on Microsoft 365.</span></span>

<span data-ttu-id="2987f-111">Microsoft biedt online services via meerdere vormen van Cloud levering:</span><span class="sxs-lookup"><span data-stu-id="2987f-111">Microsoft provides online services using multiple forms of cloud delivery:</span></span>

- <span data-ttu-id="2987f-112">**Openbare wolken:** Waaronder meerdere Tenant versies van Microsoft 365, Azure en andere services die worden gehost in Noord-Amerika, Zuid-Amerika, Europa, Zuid-Oost, Australië enzovoort.</span><span class="sxs-lookup"><span data-stu-id="2987f-112">**Public clouds:** Includes multi-tenant versions of Microsoft 365, Azure, and other services hosted in North America, South America, Europe, Asia, Australia, etc.</span></span>
- <span data-ttu-id="2987f-113">**Nationale wolken:** Omvat alle soevereine en derden Bedien bare wolken buiten de Verenigde Staten (met uitzondering van de Verenigde Staten), zoals Microsoft 365 in China (beheerd door 21Vianet), en Microsoft 365 in Duitsland (beheerd door Microsoft, maar onder een model waarin een Duitse gegevensbeheerder, Duitse Telekom, besturingselementen en monitoren de toegang van klantgegevens en systemen van klantgegevens bevat</span><span class="sxs-lookup"><span data-stu-id="2987f-113">**National clouds:** Includes all sovereign and third party-operated clouds outside of the United States (except ones noted previously), such as Microsoft 365 in China (operated by 21Vianet), and Microsoft 365 in Germany (operated by Microsoft, but under a model in which a German data trustee, Deutsche Telekom, controls and monitors Microsoft's access to customer data and systems that contain customer data).</span></span>
- <span data-ttu-id="2987f-114">**Overheids wolken:** Dit omvat Microsoft 365 en Azure Services die beschikbaar zijn voor klanten van de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="2987f-114">**Government clouds:** Includes Microsoft 365 and Azure services that are available to United States government customers.</span></span>

<span data-ttu-id="2987f-115">Voor de toepassing van dit artikel omvat Microsoft 365-Services:</span><span class="sxs-lookup"><span data-stu-id="2987f-115">For purposes of this article, Microsoft 365 services include:</span></span>

- [<span data-ttu-id="2987f-116">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2987f-116">Exchange Online</span></span>](https://docs.microsoft.com/Exchange/exchange-online)
- [<span data-ttu-id="2987f-117">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2987f-117">Exchange Online Protection</span></span>](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [<span data-ttu-id="2987f-118">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="2987f-118">SharePoint Online</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [<span data-ttu-id="2987f-119">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="2987f-119">OneDrive for Business</span></span>](https://docs.microsoft.com/OneDrive/onedrive)
- [<span data-ttu-id="2987f-120">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="2987f-120">Skype for Business</span></span>](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [<span data-ttu-id="2987f-121">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2987f-121">Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [<span data-ttu-id="2987f-122">Yammer</span><span class="sxs-lookup"><span data-stu-id="2987f-122">Yammer</span></span>](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a><span data-ttu-id="2987f-123">Microsoft 365 Access-besturingselementen</span><span class="sxs-lookup"><span data-stu-id="2987f-123">Microsoft 365 access controls</span></span>

<span data-ttu-id="2987f-124">Microsoft categoriseert Microsoft 365-gegevens als klantgegevens of een ander type gegevens voor toegangsbeheer doeleinden.</span><span class="sxs-lookup"><span data-stu-id="2987f-124">For access control purposes, Microsoft categorizes Microsoft 365 data as customer data or other types of data.</span></span>

### <a name="customer-data"></a><span data-ttu-id="2987f-125">Klantgegevens</span><span class="sxs-lookup"><span data-stu-id="2987f-125">Customer data</span></span>

<span data-ttu-id="2987f-126">Klantgegevens zijn alle gegevens verstrekt door of namens een klant met behulp van Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="2987f-126">Customer data is all data provided by or on behalf of a customer when using Microsoft 365 services.</span></span> <span data-ttu-id="2987f-127">Deze klant inhoud wordt direct gemaakt of geüpload door Microsoft 365-gebruikers, waaronder:</span><span class="sxs-lookup"><span data-stu-id="2987f-127">This is customer content directly created or uploaded by Microsoft 365 users, including:</span></span>

- <span data-ttu-id="2987f-128">Sturen</span><span class="sxs-lookup"><span data-stu-id="2987f-128">Emails</span></span>
- <span data-ttu-id="2987f-129">SharePoint Online-inhoud</span><span class="sxs-lookup"><span data-stu-id="2987f-129">SharePoint Online content</span></span>
- <span data-ttu-id="2987f-130">Chatberichten</span><span class="sxs-lookup"><span data-stu-id="2987f-130">Instant messages</span></span>
- <span data-ttu-id="2987f-131">Agenda-items</span><span class="sxs-lookup"><span data-stu-id="2987f-131">Calendar items</span></span>
- <span data-ttu-id="2987f-132">Faxdocumenten</span><span class="sxs-lookup"><span data-stu-id="2987f-132">Documents</span></span>
- <span data-ttu-id="2987f-133">Contactpersonen</span><span class="sxs-lookup"><span data-stu-id="2987f-133">Contacts</span></span>
- <span data-ttu-id="2987f-134">Identificeerbare informatie van door de gebruiker gerichte informatie (EUII) (gegevens die uniek is voor een gebruiker of die kan worden gekoppeld aan een individuele gebruiker, maar bevat geen klant inhoud)</span><span class="sxs-lookup"><span data-stu-id="2987f-134">End-user identifiable information (EUII) (data that is unique to a user or that is linkable to an individual user but does not include customer content)</span></span>

### <a name="other-types-of-data"></a><span data-ttu-id="2987f-135">Andere gegevenstypen</span><span class="sxs-lookup"><span data-stu-id="2987f-135">Other types of data</span></span>

<span data-ttu-id="2987f-136">Andere gegevenstypen zijn:</span><span class="sxs-lookup"><span data-stu-id="2987f-136">Other types of data include:</span></span>

- <span data-ttu-id="2987f-137">**Account gegevens:** Inclusief beheergegevens (informatie van beheerders die worden verstrekt door beheerders wanneer ze zich aanmelding of de aankoop van Services), en betalingsgegevens (informatie over betaalinstrumenten, zoals creditcardgegevens).</span><span class="sxs-lookup"><span data-stu-id="2987f-137">**Account data:** Includes administrative data (information provided by administrators when they sign-up or purchase services), and payment data (information about payment instruments, such as credit card details).</span></span>
- <span data-ttu-id="2987f-138">**Organisatie-identificeerbare informatie:** Bevat gegevens die worden gebruikt voor het identificeren van een Tenant, gebruiksgegevens en die niet kunnen worden gekoppeld aan een individuele gebruiker of die is opgenomen in de inhoud van de klant.</span><span class="sxs-lookup"><span data-stu-id="2987f-138">**Organizationally identifiable information:** Includes data used to identify a tenant, usage data, and not linkable to an individual user or included in customer content.</span></span>
- <span data-ttu-id="2987f-139">**Systeem metagegevens:** Bevat servicelogboeken die configuratie-instellingen, systeemstatus, Microsoft IP-adressen en technische informatie over abonnementen en tenants bevatten.</span><span class="sxs-lookup"><span data-stu-id="2987f-139">**System metadata:** Includes service logs that contain configuration settings, system status, Microsoft IP addresses, and technical information about subscriptions and tenants.</span></span>

<span data-ttu-id="2987f-140">Microsoft heeft de mechanismen voor toegangsbeheer opgezet om te voorkomen dat niemand toegang heeft tot klantgegevens of toegangsbeheer gegevens.</span><span class="sxs-lookup"><span data-stu-id="2987f-140">Microsoft has established access control mechanisms to ensure that no one has unapproved access to Customer Data or access control data.</span></span> <span data-ttu-id="2987f-141">Met toegangsbeheer gegevens wordt de toegang tot andere gegevenstypen of functies binnen de omgeving beheerd, waaronder toegang tot inhoud van de klant of EUII, Microsoft-wachtwoorden, beveiligingscertificaten en andere verificatie-gerelateerde gegevens.</span><span class="sxs-lookup"><span data-stu-id="2987f-141">Access control data manages access to other types of data or functions within the environment, including access to customer content or EUII, Microsoft passwords, security certificates, and other authentication-related data.</span></span> <span data-ttu-id="2987f-142">Methoden voor toegangsbeheer bieden ook bescherming tegen niet-goedgekeurde fysieke, logische of externe toegang tot de Microsoft 365-productieomgeving.</span><span class="sxs-lookup"><span data-stu-id="2987f-142">Access control mechanisms also guard against unapproved physical, logical, or remote access to the Microsoft 365 production environment.</span></span>

<span data-ttu-id="2987f-143">Er worden drie categorieën met toegangsbeheer voor Microsoft gebruikt voor de werking van Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="2987f-143">There are three categories of access controls used by Microsoft for operating Microsoft 365:</span></span>

- <span data-ttu-id="2987f-144">Isolatie besturingselementen</span><span class="sxs-lookup"><span data-stu-id="2987f-144">Isolation controls</span></span>
- <span data-ttu-id="2987f-145">Personeels besturingselementen</span><span class="sxs-lookup"><span data-stu-id="2987f-145">Personnel controls</span></span>
- <span data-ttu-id="2987f-146">Technologie regeling</span><span class="sxs-lookup"><span data-stu-id="2987f-146">Technology controls</span></span>

<span data-ttu-id="2987f-147">Met deze besturingselementen kunt u schadelijke acties in Microsoft 365 helpen voorkomen en detecteren.</span><span class="sxs-lookup"><span data-stu-id="2987f-147">When combined, these controls help prevent and detect malicious actions in Microsoft 365.</span></span> <span data-ttu-id="2987f-148">Naast de besturingselementen voor isolatie, medewerkers en technologie die door Microsoft worden gebruikt, is er een vierde categorie met besturingselementen: de functies die door klanten zijn geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="2987f-148">In addition to the isolation, personnel, and technology controls used by Microsoft, there is a fourth category of controls: those implemented by customers.</span></span>

<span data-ttu-id="2987f-149">Met Microsoft 365 kunt u gegevens beheren op dezelfde manier als gegevens worden beheerd in on-premises omgevingen.</span><span class="sxs-lookup"><span data-stu-id="2987f-149">Microsoft 365 allows you to manage data the same way data is managed in on-premises environments.</span></span> <span data-ttu-id="2987f-150">De persoon die een organisatie registreert voor Microsoft 365, wordt automatisch een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="2987f-150">The person who signs up an organization for Microsoft 365 automatically becomes a global administrator.</span></span> <span data-ttu-id="2987f-151">De globale beheerder heeft toegang tot alle functies in beheerportals en kan:</span><span class="sxs-lookup"><span data-stu-id="2987f-151">The global admin has access to all features in management portals and can:</span></span>

- <span data-ttu-id="2987f-152">Gebruikers maken of bewerken</span><span class="sxs-lookup"><span data-stu-id="2987f-152">Create or edit users</span></span>
- <span data-ttu-id="2987f-153">Beheerdersrollen toewijzen aan anderen</span><span class="sxs-lookup"><span data-stu-id="2987f-153">Assign admin roles to others</span></span>
- <span data-ttu-id="2987f-154">Gebruikerswachtwoorden opnieuw instellen</span><span class="sxs-lookup"><span data-stu-id="2987f-154">Reset user passwords</span></span>
- <span data-ttu-id="2987f-155">Gebruikerslicenties beheren</span><span class="sxs-lookup"><span data-stu-id="2987f-155">Manage user licenses</span></span>
- <span data-ttu-id="2987f-156">Domeinen beheren</span><span class="sxs-lookup"><span data-stu-id="2987f-156">Manage domains</span></span>
- <span data-ttu-id="2987f-157">Klanten-lockbox-aanvragen goedkeuren</span><span class="sxs-lookup"><span data-stu-id="2987f-157">Approve Customer Lockbox requests</span></span>

<span data-ttu-id="2987f-158">We raden u aan elke organisatie minstens twee beheerdersaccounts te configureren.</span><span class="sxs-lookup"><span data-stu-id="2987f-158">We recommend that each organization configure at least two admin accounts.</span></span> <span data-ttu-id="2987f-159">Voor grote Enterprise-organisaties wordt u aangeraden gespecialiseerde beheerdersaccounts voor verschillende functies aan te bieden.</span><span class="sxs-lookup"><span data-stu-id="2987f-159">For large enterprise organizations, we recommend specialized admin accounts that serve different functions.</span></span>

<span data-ttu-id="2987f-160">Zie [beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) en [beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)toewijzen voor meer informatie over het toewijzen van beheerdersrollen en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="2987f-160">For information about assigning admin roles and permissions, see [Assign admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) and [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).</span></span>

## <a name="related-links"></a><span data-ttu-id="2987f-161">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="2987f-161">Related Links</span></span>

- [<span data-ttu-id="2987f-162">Isolatie besturingselementen</span><span class="sxs-lookup"><span data-stu-id="2987f-162">Isolation Controls</span></span>](microsoft-365-isolation-controls.md)
- [<span data-ttu-id="2987f-163">Personeels besturingselementen</span><span class="sxs-lookup"><span data-stu-id="2987f-163">Personnel Controls</span></span>](microsoft-365-personnel-controls.md)
- [<span data-ttu-id="2987f-164">Technologie regeling</span><span class="sxs-lookup"><span data-stu-id="2987f-164">Technology Controls</span></span>](microsoft-365-technology-controls.md)
- [<span data-ttu-id="2987f-165">Toegangsbeheer controleren en controleren</span><span class="sxs-lookup"><span data-stu-id="2987f-165">Monitoring and Auditing Access Controls</span></span>](microsoft-365-monitoring-and-auditing-access-controls.md)
- [<span data-ttu-id="2987f-166">Enterprise Access-besturingselementen voor Yammer</span><span class="sxs-lookup"><span data-stu-id="2987f-166">Yammer Enterprise Access Controls</span></span>](microsoft-365-yammer-enterprise-access-controls.md)
