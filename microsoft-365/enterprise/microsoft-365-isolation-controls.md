---
title: Microsoft 365-isolatie besturingselementen
ms.author: josephd
author: JoeDavies-MSFT
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
description: Meer informatie over de manier waarop de isolatie besturingselementen werken binnen Microsoft 365, zodat services onder de juiste plaats kunnen blijven.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 15805c2fb57cbcaa33c5ba24dcbcaa378feea4bc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689283"
---
# <a name="microsoft-365-isolation-controls"></a><span data-ttu-id="ebc24-103">Microsoft 365-isolatie besturingselementen</span><span class="sxs-lookup"><span data-stu-id="ebc24-103">Microsoft 365 isolation controls</span></span> 

<span data-ttu-id="ebc24-104">Microsoft werkt continu, zodat de architectuur met meerdere tenants van Microsoft 365 ondersteuning biedt voor beveiliging, vertrouwelijkheid, privacy, integriteit, lokale, internationale en beschikbaarheids [normen](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span><span class="sxs-lookup"><span data-stu-id="ebc24-104">Microsoft continuously works to ensure that the multi-tenant architecture of Microsoft 365 supports enterprise-level security, confidentiality, privacy, integrity, local, international, and availability [standards](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons).</span></span> <span data-ttu-id="ebc24-105">De schaal en het servicebereik van Microsoft maken het moeilijk en niet-rendabel om Microsoft 365 te beheren met aanzienlijke menselijke interactie.</span><span class="sxs-lookup"><span data-stu-id="ebc24-105">The scale and the scope of services provided by Microsoft make it difficult and non-economical to manage Microsoft 365 with significant human interaction.</span></span> <span data-ttu-id="ebc24-106">Microsoft 365-services worden geleverd via meerdere algemeen gedistribueerde gegevenscentra, elk met een geautomatiseerd aantal bewerkingen waarbij een menselijk aanraak niveau of toegang tot de inhoud van de klant is vereist.</span><span class="sxs-lookup"><span data-stu-id="ebc24-106">Microsoft 365 services are provided through multiple globally distributed data centers, each highly automated with few operations requiring a human touch or any access to customer content.</span></span> <span data-ttu-id="ebc24-107">Onze medewerkers ondersteunen deze services en datacenters met behulp van geautomatiseerde hulpprogramma's en zeer veilige externe toegang.</span><span class="sxs-lookup"><span data-stu-id="ebc24-107">Our staff supports these services and data centers using automated tools and highly secure remote access.</span></span> 

<span data-ttu-id="ebc24-108">Microsoft 365 is samengesteld uit meerdere services die belangrijke bedrijfsfunctionaliteit bieden en bijdragen aan de volledige Microsoft 365-ervaring.</span><span class="sxs-lookup"><span data-stu-id="ebc24-108">Microsoft 365 is composed of multiple services that provide important business functionality and contribute to the entire Microsoft 365 experience.</span></span> <span data-ttu-id="ebc24-109">Deze services zijn zelf en ontworpen voor integratie met elkaar.</span><span class="sxs-lookup"><span data-stu-id="ebc24-109">Each of these services is self-contained and designed to integrate with one another.</span></span>

<span data-ttu-id="ebc24-110">Microsoft 365 is ontworpen met de volgende beginselen:</span><span class="sxs-lookup"><span data-stu-id="ebc24-110">Microsoft 365 is designed with the following principles:</span></span>

 - <span data-ttu-id="ebc24-111">\*\* [Service gerichte architectuur](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):\*\* het ontwerpen en ontwikkelen van software in de vorm van interoperabele diensten die goed gedefinieerde bedrijfsfunctionaliteit bieden.</span><span class="sxs-lookup"><span data-stu-id="ebc24-111">**[Service-Oriented Architecture](https://docs.microsoft.com/previous-versions/aa480021(v=msdn.10)):** designing and developing software in the form of interoperable services providing well-defined business functionality.</span></span>
 - <span data-ttu-id="ebc24-112">**[Operationele beveiligings zekerheid](https://www.microsoft.com/download/details.aspx?id=40872):** een kader dat de kennis vormt van diverse mogelijkheden die uniek zijn voor Microsoft, waaronder de Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), het [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx)en de grondige bewustmaking van de Cyber Security-Threat liggend.</span><span class="sxs-lookup"><span data-stu-id="ebc24-112">**[Operational Security Assurance](https://www.microsoft.com/download/details.aspx?id=40872):** a framework that incorporates the knowledge gained through various capabilities that are unique to Microsoft, including the Microsoft [Security Development Lifecycle](https://www.microsoft.com/sdl/default.aspx), the [Microsoft Security Response Center](https://technet.microsoft.com/library/dn440717.aspx), and deep awareness of the cybersecurity threat landscape.</span></span>

<span data-ttu-id="ebc24-113">Microsoft 365-services die onderling samenwerken, maar zijn ontworpen en geïmplementeerd, zodat ze kunnen worden geïmplementeerd en geëxploiteerd als autonome Services, ongeacht elkaar.</span><span class="sxs-lookup"><span data-stu-id="ebc24-113">Microsoft 365 services inter-operate with each other, but are designed and implemented so they can be deployed and operated as autonomous services, independent of each other.</span></span> <span data-ttu-id="ebc24-114">Microsoft scheidt bevoegdheden en verantwoordelijkheidsgebieden voor Microsoft 365 om de verkoopkansen te verminderen voor ongeoorloofde of onbedoelde wijzigingen of misbruik van de assets van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="ebc24-114">Microsoft segregates duties and areas of responsibility for Microsoft 365 to reduce opportunities for unauthorized or unintentional modification or misuse of the organization's assets.</span></span> <span data-ttu-id="ebc24-115">Microsoft 365 teams heeft rollen gedefinieerd als onderdeel van een uitgebreid toegangsbeheer mechanisme op basis van rollen.</span><span class="sxs-lookup"><span data-stu-id="ebc24-115">Microsoft 365 teams have defined roles as part of a comprehensive role-based access control mechanism.</span></span>

## <a name="customer-content-isolation"></a><span data-ttu-id="ebc24-116">Inhouds isolatie van klanten</span><span class="sxs-lookup"><span data-stu-id="ebc24-116">Customer content isolation</span></span>

<span data-ttu-id="ebc24-117">Alle inhoud van de klant in een Tenant is geïsoleerd van andere tenants en van operations-en systeemgegevens die worden gebruikt in het beheer van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc24-117">All customer content in a tenant is isolated from other tenants and from operations and systems data used in the management of Microsoft 365.</span></span> <span data-ttu-id="ebc24-118">Er worden meerdere vormen van bescherming geïmplementeerd in Microsoft 365, zodat u het risico voor compromissen met een Microsoft 365-service of-toepassing beperkt.</span><span class="sxs-lookup"><span data-stu-id="ebc24-118">Multiple forms of protection are implemented throughout Microsoft 365 to minimize the risk of compromise of any Microsoft 365 service or application.</span></span> <span data-ttu-id="ebc24-119">Meerdere vormen van bescherming verhinderen ook onbevoegde toegang tot de gegevens van tenants of het Microsoft 365-systeem zelf.</span><span class="sxs-lookup"><span data-stu-id="ebc24-119">Multiple forms of protection also prevent unauthorized access to the information of tenants or the Microsoft 365 system itself.</span></span>

<span data-ttu-id="ebc24-120">Zie [Tenant isolatie in Microsoft 365](microsoft-365-tenant-isolation-overview.md)voor informatie over hoe Microsoft logische isolatie van Tenant gegevens implementeert in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ebc24-120">For information about how Microsoft implements logical isolation of tenant data within Microsoft 365, see [Tenant Isolation in Microsoft 365](microsoft-365-tenant-isolation-overview.md).</span></span>
