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
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926557"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="4a379-103">Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DOD</span><span class="sxs-lookup"><span data-stu-id="4a379-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="4a379-104">*Dit artikel is van toepassing op Office 365 GCC Hoge, Office 365 DOD, Microsoft 365 GCC Hoog en Microsoft 365 DOD.*</span><span class="sxs-lookup"><span data-stu-id="4a379-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="4a379-105">Office 365 GCC High en DOD zijn veilige cloudomgevingen om te voldoen aan de behoeften van de Amerikaanse overheid en haar leveranciers en contractanten.</span><span class="sxs-lookup"><span data-stu-id="4a379-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="4a379-106">Deze cloudomgevingen hebben extra netwerkbeperkingen waarvoor de services toegang hebben tot externe eindpunten.</span><span class="sxs-lookup"><span data-stu-id="4a379-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="4a379-107">GCC Hoge en dod-klanten die federatief identiteiten of hybride coëxistentie willen gebruiken, moeten mogelijk inkomende en/of uitgaande toegang toestaan tot uw bestaande on-premises implementaties.</span><span class="sxs-lookup"><span data-stu-id="4a379-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="4a379-108">Voorbeelden van deze activiteiten zijn:</span><span class="sxs-lookup"><span data-stu-id="4a379-108">Examples of these activities include:</span></span>

* <span data-ttu-id="4a379-109">Gebruik van federatief identiteiten (met Active Directory Federation Services of soortgelijke ondersteunde STS)</span><span class="sxs-lookup"><span data-stu-id="4a379-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="4a379-110">Hybride coëxistentie met een on-premises Exchange Server of Skype voor Bedrijven implementatie</span><span class="sxs-lookup"><span data-stu-id="4a379-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="4a379-111">Migratie van bestaande gebruikersinhoud vanuit een on-premises systeem</span><span class="sxs-lookup"><span data-stu-id="4a379-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="4a379-112">Als u wilt toestaan dat de service met  uw on-premises eindpunten communiceert, moet u een e-mail verzenden naar Office 365 engineering voor netwerkwijzigingen.</span><span class="sxs-lookup"><span data-stu-id="4a379-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="4a379-113">Alle aanvragen hebben een SLA van drie **weken** en kunnen niet worden versneld vanwege de vereiste beveiligings- en compliancecontroles en implementatiepijplijnen.</span><span class="sxs-lookup"><span data-stu-id="4a379-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="4a379-114">Dit omvat initiële onboarding-netwerkaanvragen en eventuele wijzigingen nadat u naar de service bent gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="4a379-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="4a379-115">Zorg ervoor dat uw netwerkteams op de hoogte zijn van deze tijdlijn en neem deze op in hun planningscyclus.</span><span class="sxs-lookup"><span data-stu-id="4a379-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="4a379-116">Stuur een [e-mail naar Office 365 Government Allow-List aanvragen](mailto:o365gwlt@microsoft.com) met de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="4a379-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="4a379-117">**Om**: [Office 365 Government Allow-List aanvragen](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4a379-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="4a379-118">**Van**: Een tenantbeheerder: de e-mail verzenden **moet overeenkomen** met een globale beheerder in uw tenant</span><span class="sxs-lookup"><span data-stu-id="4a379-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="4a379-119">**Onderwerp** e-mail: Office 365 GCC High Network Request - contoso.onmicrosoft.us (vervangen door uw tenantnaam)</span><span class="sxs-lookup"><span data-stu-id="4a379-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="4a379-120">De hoofd van het bericht moet de volgende gegevens bevatten:</span><span class="sxs-lookup"><span data-stu-id="4a379-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="4a379-121">Uw Microsoft Online Services-tenantnaam (bijvoorbeeld contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span><span class="sxs-lookup"><span data-stu-id="4a379-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="4a379-122">Een e-maildistributielijst met microsoft voor on-going communicatie met betrekking tot netwerkwijzigingen en/of opvolging van ongeldige subnetten</span><span class="sxs-lookup"><span data-stu-id="4a379-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="4a379-123">Aangeven of u van plan bent om Microsoft Teams hybride coëxistentie te gebruiken met uw on-premises implementaties</span><span class="sxs-lookup"><span data-stu-id="4a379-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="4a379-124">Federatief identiteitssysteem extern toegankelijke URL (bijvoorbeeld sts.contoso.com) en IP-adresbereik in CIDR-notatie (bijvoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="4a379-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="4a379-125">10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="4a379-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="4a379-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span><span class="sxs-lookup"><span data-stu-id="4a379-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="4a379-127">Extern toegankelijke URL en IP-adresbereik voor Exchange Server on-premises implementatie in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="4a379-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="4a379-128">Extern toegankelijke URL en IP-adresbereik voor Skype voor Bedrijven on-premises implementatie in CIDR-notatie</span><span class="sxs-lookup"><span data-stu-id="4a379-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="4a379-129">Houd om veiligheids- en nalevingsredenen rekening met de volgende beperkingen voor uw aanvraag:</span><span class="sxs-lookup"><span data-stu-id="4a379-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="4a379-130">Er is een beperking van vier subnets per tenant</span><span class="sxs-lookup"><span data-stu-id="4a379-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="4a379-131">Subnetten moeten in CIDR-notatie zijn (bijvoorbeeld 10.1.1.0/28)</span><span class="sxs-lookup"><span data-stu-id="4a379-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="4a379-132">Subnetbereiken mogen niet groter zijn dan /24</span><span class="sxs-lookup"><span data-stu-id="4a379-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="4a379-133">We **kunnen geen** aanvragen voor toegang tot commerciële cloudservices toestaan (commerciële Office 365, Google G-Suite, Amazon Web Services, enzovoort)</span><span class="sxs-lookup"><span data-stu-id="4a379-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="4a379-134">Wanneer uw aanvraag is ontvangen en goedgekeurd door Microsoft, is er een SLA van drie weken voor implementatie en kan deze niet worden versneld.</span><span class="sxs-lookup"><span data-stu-id="4a379-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="4a379-135">U ontvangt een eerste bevestiging wanneer we uw aanvraag hebben ontvangen en een definitieve bevestiging zodra deze is voltooid.</span><span class="sxs-lookup"><span data-stu-id="4a379-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
