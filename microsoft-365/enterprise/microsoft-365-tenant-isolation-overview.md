---
title: Tenant isolatie in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dit artikel bevat een overzicht van hoe Microsoft Tenant isolatie afdwingt in cloudservices zoals Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7aca35fc61d03e94225375fcf67970e13dd691c9
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332686"
---
# <a name="tenant-isolation-in-microsoft-365"></a><span data-ttu-id="46771-103">Tenant isolatie in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46771-103">Tenant Isolation in Microsoft 365</span></span>

<span data-ttu-id="46771-104">Een van de belangrijkste voordelen van Cloud Computing is concept van een gemeenschappelijke, gemeenschappelijke infrastructuur in meerdere klanten, zodat u deze kunt schalen.</span><span class="sxs-lookup"><span data-stu-id="46771-104">One of the primary benefits of cloud computing is concept of a shared, common infrastructure across numerous customers simultaneously, leading to economies of scale.</span></span> <span data-ttu-id="46771-105">Dit concept heet multitenancy *.*</span><span class="sxs-lookup"><span data-stu-id="46771-105">This concept is called *multi-tenancy*.</span></span> <span data-ttu-id="46771-106">Microsoft werkt continu, zodat de architecturen voor meerdere tenants van onze cloudservices ondersteuning bieden voor beveiliging van ondernemingen, vertrouwelijkheid, privacy, integriteit en beschikbaarheid.</span><span class="sxs-lookup"><span data-stu-id="46771-106">Microsoft works continuously to ensure that the multi-tenant architectures of our cloud services support enterprise-level security, confidentiality, privacy, integrity, and availability standards.</span></span>

<span data-ttu-id="46771-107">Op basis van de substantiële investeringen en ervaring van [Trustworthy Computing](https://www.microsoft.com/trust-center) en de [levenscyclus](https://www.microsoft.com/securityengineering/sdl/)van de veiligheid werden Microsoft-cloudservices ontworpen met de hypothese dat alle tenants potentieel vijandelijk zijn voor alle andere tenants en kunnen we beveiligingsmaatregelen implementeren om te voorkomen dat de acties van een bepaalde Tenant van invloed zijn op de beveiliging of service van een andere Tenant</span><span class="sxs-lookup"><span data-stu-id="46771-107">Based upon the significant investments and experience gathered from [Trustworthy Computing](https://www.microsoft.com/trust-center) and the [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/), Microsoft cloud services were designed with the assumption that all tenants are potentially hostile to all other tenants, and we have implemented security measures to prevent the actions of one tenant from affecting the security or service of another tenant, or accessing the content of another tenant.</span></span>

<span data-ttu-id="46771-108">De twee belangrijkste doelstellingen voor de handhaving van Tenant isolatie in een omgeving met meerdere tenants zijn:</span><span class="sxs-lookup"><span data-stu-id="46771-108">The two primary goals of maintaining tenant isolation in a multi-tenant environment are:</span></span>

1.    <span data-ttu-id="46771-109">Het verhinderen van lekkage van toegang tot inhoud van klanten via tenants voorkomen; en</span><span class="sxs-lookup"><span data-stu-id="46771-109">Preventing leakage of, or unauthorized access to, customer content across tenants; and</span></span>
2.    <span data-ttu-id="46771-110">Verhinderen dat de acties van een Tenant de service nadelig beïnvloeden voor een andere Tenant</span><span class="sxs-lookup"><span data-stu-id="46771-110">Preventing the actions of one tenant from adversely affecting the service for another tenant</span></span>

<span data-ttu-id="46771-111">Er zijn meerdere vormen van bescherming geïmplementeerd in Microsoft 365 om te voorkomen dat klanten Microsoft 365-Services of-toepassingen in gevaar brengen of om onbevoegde toegang tot de gegevens van andere tenants of het Microsoft 365-systeem zelf te verkrijgen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="46771-111">Multiple forms of protection have been implemented throughout Microsoft 365 to prevent customers from compromising Microsoft 365 services or applications or gaining unauthorized access to the information of other tenants or the Microsoft 365 system itself, including:</span></span>

- <span data-ttu-id="46771-112">De logische isolatie van de inhoud van klanten binnen elke Tenant voor Microsoft 365-Services wordt gerealiseerd via Azure Active Directory-autorisatie en op rollen gebaseerd toegangsbeheer.</span><span class="sxs-lookup"><span data-stu-id="46771-112">Logical isolation of customer content within each tenant for Microsoft 365 services is achieved through Azure Active Directory authorization and role-based access control.</span></span>
- <span data-ttu-id="46771-113">SharePoint Online biedt mechanismen voor gegevensisolatie op opslagniveau.</span><span class="sxs-lookup"><span data-stu-id="46771-113">SharePoint Online provides data isolation mechanisms at the storage level.</span></span>
- <span data-ttu-id="46771-114">Microsoft gebruikt strikte fysieke beveiliging, achtergrondcontrole en een meerlaagse versleutelings strategie om de vertrouwelijkheid en integriteit van klant inhoud te beschermen.</span><span class="sxs-lookup"><span data-stu-id="46771-114">Microsoft uses rigorous physical security, background screening, and a multi-layered encryption strategy to protect the confidentiality and integrity of customer content.</span></span> <span data-ttu-id="46771-115">Alle Microsoft 365-datacenters beschikken over besturingselementen voor biometrische toegang, met de meeste Palm afdrukken, zodat u fysieke toegang krijgt.</span><span class="sxs-lookup"><span data-stu-id="46771-115">All Microsoft 365 datacenters have biometric access controls, with most requiring palm prints to gain physical access.</span></span> <span data-ttu-id="46771-116">Daarnaast zijn alle op de VS gebaseerde Microsoft-werknemers nodig om een standaardachtergrond controle uit te voeren als onderdeel van het wervingsproces.</span><span class="sxs-lookup"><span data-stu-id="46771-116">In addition, all U.S.-based Microsoft employees are required to successfully complete a standard background check as part of the hiring process.</span></span> <span data-ttu-id="46771-117">Zie voor meer informatie over de besturingselementen die worden gebruikt voor beheerderstoegang in Microsoft 365, [Microsoft 365 Administrative Access controls](microsoft-365-administrative-access-controls-overview.md).</span><span class="sxs-lookup"><span data-stu-id="46771-117">For more information on the controls used for administrative access in Microsoft 365, see [Microsoft 365 Administrative Access Controls](microsoft-365-administrative-access-controls-overview.md).</span></span>
- <span data-ttu-id="46771-118">Microsoft 365 maakt gebruik van technologieën voor de service die de inhoud van een klant versleutelen en in transit, waaronder BitLocker, eenmalige versleuteling, TLS (Transport Layer Security) en IPsec (Internet Protocol Security).</span><span class="sxs-lookup"><span data-stu-id="46771-118">Microsoft 365 uses service-side technologies that encrypt customer content at rest and in transit, including BitLocker, per-file encryption, Transport Layer Security (TLS) and Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="46771-119">Zie [technologieën voor gegevensversleuteling in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)voor specifieke informatie over versleuteling in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="46771-119">For specific details about encryption in Microsoft 365, see [Data Encryption Technologies in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span>

<span data-ttu-id="46771-120">De hierboven genoemde bescherming biedt een robuuste logische isolatie regeling die de bescherming van de bescherming en de beperking van de schade biedt.</span><span class="sxs-lookup"><span data-stu-id="46771-120">Together, the above-listed protections provide robust logical isolation controls that provide threat protection and mitigation equivalent to that provided by physical isolation alone.</span></span>

## <a name="related-links"></a><span data-ttu-id="46771-121">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="46771-121">Related Links</span></span>

- [<span data-ttu-id="46771-122">Isolatie en toegankelijkheid beheren in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="46771-122">Isolation and Access Control in Azure Active Directory</span></span>](microsoft-365-isolation-in-azure-active-directory.md)
- [<span data-ttu-id="46771-123">Tenant isolatie in Office Graph en Delve</span><span class="sxs-lookup"><span data-stu-id="46771-123">Tenant Isolation in the Office Graph and Delve</span></span>](microsoft-365-isolation-in-graph-and-delve.md)
- [<span data-ttu-id="46771-124">Tenant isolatie in Microsoft 365 zoeken</span><span class="sxs-lookup"><span data-stu-id="46771-124">Tenant Isolation in Microsoft 365 Search</span></span>](microsoft-365-isolation-in-microsoft-365-search.md)
- [<span data-ttu-id="46771-125">Tenant isolatie in Office 365 video</span><span class="sxs-lookup"><span data-stu-id="46771-125">Tenant Isolation in Office 365 Video</span></span>](microsoft-365-isolation-in-microsoft-365-video.md)
- [<span data-ttu-id="46771-126">Resourcelimieten</span><span class="sxs-lookup"><span data-stu-id="46771-126">Resource Limits</span></span>](microsoft-365-resource-limits.md)
- [<span data-ttu-id="46771-127">Tenant grenzen controleren en testen</span><span class="sxs-lookup"><span data-stu-id="46771-127">Monitoring and Testing Tenant Boundaries</span></span>](microsoft-365-monitoring-and-testing.md)
- [<span data-ttu-id="46771-128">Isolatie en toegangsbeheer in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="46771-128">Isolation and Access Control in Microsoft 365</span></span>](microsoft-365-isolation-in-microsoft-365.md)
