---
title: Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Overzicht: Office 365 GCC High en DoD hebben extra vereisten voor netwerkbeveiliging'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689239"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="6c5d5-103">Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DOD</span><span class="sxs-lookup"><span data-stu-id="6c5d5-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="6c5d5-104">*Dit artikel is van toepassing op Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High en Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="6c5d5-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="6c5d5-105">Office 365 GCC High en DOD is een veilig cloudomgeving om te voldoen aan de behoeften van de Amerikaanse overheid en de leveranciers van de Verenigde Staten.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="6c5d5-106">Voor deze Cloud omgevingen gelden extra netwerkbeperkingen voor de externe eindpunten van de services die toegang mogen hebben.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="6c5d5-107">Voor klanten met een GCC voor hoog en DOD mag Microsoft de mogelijkheid van inkomende en/of uitgaande toegang tot uw bestaande on-premises implementaties worden vereist.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="6c5d5-108">Voorbeelden van deze activiteiten zijn:</span><span class="sxs-lookup"><span data-stu-id="6c5d5-108">Examples of these activities include:</span></span>

* <span data-ttu-id="6c5d5-109">Gebruik van federatieve identiteiten (met Active Directory Federation Services of vergelijkbaar ondersteunde STS)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="6c5d5-110">Hybride samenwerking met een on-premises Exchange-Server of Skype voor bedrijven-implementatie</span><span class="sxs-lookup"><span data-stu-id="6c5d5-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="6c5d5-111">Migratie van bestaande gebruikers inhoud vanuit een on-premises systeem</span><span class="sxs-lookup"><span data-stu-id="6c5d5-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="6c5d5-112">Als u de service wilt toestaan om te communiceren met uw on-premises eindpunten, **moet** u een e-mailbericht verzenden naar Office 365 engineering voor netwerk wijzigingen.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="6c5d5-113">Alle aanvragen hebben een sla met **drie weken** en kunnen niet worden getransporteerd vanwege de vereiste besturingselementen voor beveiliging en compliance en implementatie pijplijnen.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="6c5d5-114">Dit geldt ook voor de aanvankelijke netwerkaanvragen voor onboarding en eventuele wijzigingen nadat u de service hebt gemigreerd naar de service.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="6c5d5-115">Zorg ervoor dat uw netwerk teams op de hoogte zijn van deze tijdlijn en neem deze op in de plannings cyclussen.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="6c5d5-116">Stuur een e-mailbericht naar [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com) en voer de volgende informatie in:</span><span class="sxs-lookup"><span data-stu-id="6c5d5-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="6c5d5-117">**Naar**: [Office 365 Government netwerk whitelist](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="6c5d5-118">**Van**: een tenantbeheerder-de e-mail verzenden **moet** overeenkomen met een contactpersoon van een globale beheerder in uw Tenant</span><span class="sxs-lookup"><span data-stu-id="6c5d5-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="6c5d5-119">**Onderwerp e-mail**: Office 365 gcc High netwerk Request-contoso.onmicrosoft.us (vervangt dit door de naam van de Tenant)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="6c5d5-120">De hoofdtekst van het bericht moet de volgende gegevens bevatten:</span><span class="sxs-lookup"><span data-stu-id="6c5d5-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="6c5d5-121">De naam van de Microsoft Online service-Tenant (bijv. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="6c5d5-122">Een distributielijst met e-mailberichten waarop Microsoft communiceert voor voortdurende berichten die betrekking hebben op netwerk wijzigingen en/of opvolgen voor ongeldige subnetten</span><span class="sxs-lookup"><span data-stu-id="6c5d5-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="6c5d5-123">Aangeven of u van plan bent om hybride medewerking van Microsoft teams te gebruiken met uw on-premises implementaties</span><span class="sxs-lookup"><span data-stu-id="6c5d5-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="6c5d5-124">Extern, federatieve identiteits systeem extern toegankelijke URL (bijvoorbeeld sts.contoso.com) en IP-adresbereik in CIDR-notatie (bijv. 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="6c5d5-125">URL en IP-adresbereik voor de intrekkingslijst van een certificeringsinstantie met een on-premises adreslijst</span><span class="sxs-lookup"><span data-stu-id="6c5d5-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="6c5d5-126">Extern toegankelijke URL en IP-adresbereik voor Exchange Server on-premises implementatie in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="6c5d5-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="6c5d5-127">Extern toegankelijke URL en IP-adresbereik voor de on-premises implementatie van Skype voor bedrijven in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="6c5d5-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="6c5d5-128">Ter bescherming van beveiligings-en nalevings redenen dient u rekening te houden met de volgende beperkingen voor uw aanvraag:</span><span class="sxs-lookup"><span data-stu-id="6c5d5-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="6c5d5-129">Er geldt een limiet van vier subnetten per Tenant</span><span class="sxs-lookup"><span data-stu-id="6c5d5-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="6c5d5-130">De subnetten moeten in CIDR-notatie staan (bijvoorbeeld 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="6c5d5-131">Subnetobject mag niet groter zijn dan/24</span><span class="sxs-lookup"><span data-stu-id="6c5d5-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="6c5d5-132">We **kunnen geen** aanvragen indienen voor het verlenen van toegang tot commerciële cloudservices (commercial Office 365, Google G-suite, Amazon Web Services, etc.)</span><span class="sxs-lookup"><span data-stu-id="6c5d5-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="6c5d5-133">Wanneer uw aanvraag is ontvangen en goedgekeurd door Microsoft, is er een SLA met drie weken voor de implementatie en kan deze niet worden getransporteerd.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="6c5d5-134">U ontvangt een eerste bevestiging wanneer uw aanvraag en de laatste bevestiging eenmaal zijn ontvangen.</span><span class="sxs-lookup"><span data-stu-id="6c5d5-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
