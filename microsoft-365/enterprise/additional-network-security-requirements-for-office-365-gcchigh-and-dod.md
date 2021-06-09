---
title: Aanvullende netwerkbeveiligingsvereisten voor Office 365 GCC High en DoD
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
description: 'Overzicht: Office 365 GCC High en DoD hebben extra netwerkbeveiligingsvereisten'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689239"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="0919f-103">Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DOD</span><span class="sxs-lookup"><span data-stu-id="0919f-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="0919f-104">*Dit artikel is van toepassing op Office 365 GCC Hoge, Office 365 DOD, Microsoft 365 GCC Hoog en Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="0919f-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="0919f-105">Office 365 GCC High en DOD zijn veilige cloudomgevingen om te voldoen aan de behoeften van de Amerikaanse overheid en haar leveranciers en contractanten.</span><span class="sxs-lookup"><span data-stu-id="0919f-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="0919f-106">Deze cloudomgevingen hebben extra netwerkbeperkingen waarvoor de services toegang hebben tot externe eindpunten.</span><span class="sxs-lookup"><span data-stu-id="0919f-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="0919f-107">GCC Hoge en dod-klanten die federatief identiteiten of hybride co-bestaan willen gebruiken, kunnen microsoft verplichten om inkomende en/of uitgaande toegang toe te staan tot uw bestaande on-premises implementaties.</span><span class="sxs-lookup"><span data-stu-id="0919f-107">GCC High and DOD customers planning to use federated identities or hybrid co-existence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="0919f-108">Voorbeelden van deze activiteiten zijn:</span><span class="sxs-lookup"><span data-stu-id="0919f-108">Examples of these activities include:</span></span>

* <span data-ttu-id="0919f-109">Gebruik van federatief identiteiten (met Active Directory Federation Services of soortgelijke ondersteunde STS)</span><span class="sxs-lookup"><span data-stu-id="0919f-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="0919f-110">Hybride coëxistentie met een on-premises Exchange Server of Skype voor Bedrijven implementatie</span><span class="sxs-lookup"><span data-stu-id="0919f-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="0919f-111">Migratie van bestaande gebruikersinhoud vanuit een on-premises systeem</span><span class="sxs-lookup"><span data-stu-id="0919f-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="0919f-112">Als u wilt toestaan dat de service met  uw on-premises eindpunten communiceert, moet u een e-mail verzenden naar Office 365 engineering voor netwerkwijzigingen.</span><span class="sxs-lookup"><span data-stu-id="0919f-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="0919f-113">Alle aanvragen hebben een SLA van drie **weken** en kunnen niet worden versneld vanwege de vereiste beveiligings- en compliancecontroles en implementatiepijplijnen.</span><span class="sxs-lookup"><span data-stu-id="0919f-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="0919f-114">Dit omvat initiële onboarding-netwerkaanvragen en eventuele wijzigingen nadat u naar de service bent gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="0919f-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="0919f-115">Zorg ervoor dat uw netwerkteams op de hoogte zijn van deze tijdlijn en neem deze op in hun planningscyclus.</span><span class="sxs-lookup"><span data-stu-id="0919f-115">Please ensure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="0919f-116">Stuur een e-mail [naar Office 365 Government whitelist met](mailto:o365gwlt@microsoft.com) de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="0919f-116">Please send an email to [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="0919f-117">**Naar**: [Office 365 Government Whitelist voor netwerken](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="0919f-117">**To**: [Office 365 Government Network Whitelist](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="0919f-118">**Van**: Een tenantbeheerder: de e-mail verzenden **moet overeenkomen** met een globale beheerder in uw tenant</span><span class="sxs-lookup"><span data-stu-id="0919f-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="0919f-119">**E-mailonderwerp:** Office 365 GCC High Network Request - contoso.onmicrosoft.us (vervang dit door uw tenantnaam)</span><span class="sxs-lookup"><span data-stu-id="0919f-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace this with your tenant name)</span></span>

<span data-ttu-id="0919f-120">De hoofd van het bericht moet de volgende gegevens bevatten:</span><span class="sxs-lookup"><span data-stu-id="0919f-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="0919f-121">Uw Microsoft Online Services-tenantnaam (dat wil zeggen contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="0919f-121">Your Microsoft Online Services tenant name (i.e. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="0919f-122">Een e-maildistributielijst met microsoft voor on-going communicatie met betrekking tot netwerkwijzigingen en/of opvolging van ongeldige subnetten</span><span class="sxs-lookup"><span data-stu-id="0919f-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="0919f-123">Geef aan of u van plan bent Microsoft Teams hybride co-existence te gebruiken met uw on-premises implementaties</span><span class="sxs-lookup"><span data-stu-id="0919f-123">Indicate whether you plan to use Microsoft Teams hybrid co-existence with your on-premises deployments</span></span>
* <span data-ttu-id="0919f-124">Federatief identiteitssysteem voor extern toegankelijke URL (bijvoorbeeld sts.contoso.com) en IP-adresbereik in CIDR-notatie (bijvoorbeeld 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="0919f-124">Federated identity system externally accessible URL (e.g. sts.contoso.com) and IP address range in CIDR notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="0919f-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span><span class="sxs-lookup"><span data-stu-id="0919f-125">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="0919f-126">Extern toegankelijke URL en IP-adresbereik voor Exchange Server on-premises implementatie in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="0919f-126">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="0919f-127">Extern toegankelijke URL en IP-adresbereik voor Skype voor Bedrijven on-premises implementatie in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="0919f-127">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="0919f-128">Houd om veiligheids- en nalevingsredenen rekening met de volgende beperkingen voor uw aanvraag:</span><span class="sxs-lookup"><span data-stu-id="0919f-128">For security and compliance reasons, please keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="0919f-129">Er is een beperking van vier subnets per tenant</span><span class="sxs-lookup"><span data-stu-id="0919f-129">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="0919f-130">Subnetten moeten in CIDR-notatie zijn (bijvoorbeeld 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="0919f-130">Subnets must be in CIDR Notation (e.g. 10.1.1.0/28)</span></span>
* <span data-ttu-id="0919f-131">Subnetbereiken mogen niet groter zijn dan /24</span><span class="sxs-lookup"><span data-stu-id="0919f-131">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="0919f-132">We **kunnen geen** aanvragen voor toegang tot commerciële cloudservices toestaan (commerciële Office 365, Google G-Suite, Amazon Web Services, enzovoort)</span><span class="sxs-lookup"><span data-stu-id="0919f-132">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="0919f-133">Wanneer uw aanvraag is ontvangen en goedgekeurd door Microsoft, is er een SLA van drie weken voor implementatie en kan deze niet worden versneld.</span><span class="sxs-lookup"><span data-stu-id="0919f-133">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="0919f-134">U ontvangt een eerste bevestiging wanneer we uw aanvraag hebben ontvangen en een definitieve bevestiging zodra deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="0919f-134">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgement once it has been completed.</span></span>
