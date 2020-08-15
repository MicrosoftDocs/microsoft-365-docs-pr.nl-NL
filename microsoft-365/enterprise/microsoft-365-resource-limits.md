---
title: Microsoft 365-resource limieten
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
description: In dit artikel vindt u informatie over resource limieten voor de verschillende toepassingen in Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6053740d41b02461432243c8527391a4f8ae22ea
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689373"
---
# <a name="resource-limits"></a><span data-ttu-id="3f45b-103">Resource limieten</span><span class="sxs-lookup"><span data-stu-id="3f45b-103">Resource Limits</span></span>

<span data-ttu-id="3f45b-104">Resource limieten worden afgedwongen met quota's (limieten) en gashendel.</span><span class="sxs-lookup"><span data-stu-id="3f45b-104">Resource limits are enforced using quotas (limits) and throttling.</span></span> <span data-ttu-id="3f45b-105">Azure Active Directory (Azure AD) en de afzonderlijke Microsoft 365-Services gebruiken beide.</span><span class="sxs-lookup"><span data-stu-id="3f45b-105">Azure Active Directory (Azure AD) and the individual Microsoft 365 services use both.</span></span> <span data-ttu-id="3f45b-106">Limieten zijn specifiek voor de service, en veranderen over de tijd wanneer nieuwe functies worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="3f45b-106">Limits are service-specific and change over time as new capabilities are added.</span></span> <span data-ttu-id="3f45b-107">Zie de volgende onderwerpen voor meer informatie over de huidige limieten voor de verschillende services:</span><span class="sxs-lookup"><span data-stu-id="3f45b-107">For details on the current limits for the various services, see the following topics:</span></span>

- [<span data-ttu-id="3f45b-108">Azure AD-Servicebeperkingen en-beperkingen</span><span class="sxs-lookup"><span data-stu-id="3f45b-108">Azure AD service limits and restrictions</span></span>](https://docs.microsoft.com/azure/azure-resource-manager/management/azure-subscription-service-limits)
- [<span data-ttu-id="3f45b-109">Beperkingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f45b-109">Exchange Online Limits</span></span>](https://technet.microsoft.com/library/exchange-online-limits.aspx)
- [<span data-ttu-id="3f45b-110">Beveiligingsbeperkingen voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3f45b-110">Exchange Online Protection Limits</span></span>](https://technet.microsoft.com/library/exchange-online-protection-limits.aspx)
- [<span data-ttu-id="3f45b-111">Software grenzen en-limieten voor SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3f45b-111">SharePoint Online software boundaries and limits</span></span>](https://support.office.com/article/SharePoint-Online-software-boundaries-and-limits-8F34FF47-B749-408B-ABC0-B605E1F6D498)
- [<span data-ttu-id="3f45b-112">Limieten voor Skype voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="3f45b-112">Skype for Business Limits</span></span>](https://technet.microsoft.com/library/skype-for-business-online-limits.aspx)
- [<span data-ttu-id="3f45b-113">Yammer REST API en tarief limieten</span><span class="sxs-lookup"><span data-stu-id="3f45b-113">Yammer REST API and Rate Limits</span></span>](https://developer.yammer.com/docs/rest-api-rate-limits)
- [<span data-ttu-id="3f45b-114">Limieten voor de bestandsgrootte in Sway</span><span class="sxs-lookup"><span data-stu-id="3f45b-114">File Size Limits in Sway</span></span>](https://support.office.com/article/File-size-limits-in-Sway-4db21bc6-b42b-499f-9272-66e089db109f)

<span data-ttu-id="3f45b-115">Naast deze limieten worden ook enkele mechanismen voor het beperken van de gashendel gebruikt in azure AD en Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3f45b-115">In addition to these limits, several throttling mechanisms are used throughout Azure AD and Microsoft 365.</span></span> <span data-ttu-id="3f45b-116">De beperking binnen de service is vooral belangrijk, op voorwaarde dat netwerkbronnen in de datacenters van Microsoft zijn geoptimaliseerd voor de grote set klanten die de Services gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3f45b-116">Throttling within the service is especially important, given that network resources in Microsoft's datacenters are optimized for the broad set of customers that use the services.</span></span> <span data-ttu-id="3f45b-117">Beperkings mechanismen omvatten:</span><span class="sxs-lookup"><span data-stu-id="3f45b-117">Throttling mechanisms include:</span></span>

- <span data-ttu-id="3f45b-118">Gebruikers van Azure AD en Microsoft 365 stellen gebruikersniveau in voor het beperken van het aantal transacties of gelijktijdig bellen (via script of code) dat door één gebruiker kan worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3f45b-118">Azure AD and Microsoft 365 feature user-level throttling, which limit the number of transactions or concurrent calls (by script or code) that can be performed by a single user.</span></span>
- <span data-ttu-id="3f45b-119">Bij het maken van tenants wordt een standaard PowerShell-beleid voor PowerShell toegewezen aan elke Tenant.</span><span class="sxs-lookup"><span data-stu-id="3f45b-119">A default PowerShell throttling policy is assigned to each tenant at tenant creation.</span></span> <span data-ttu-id="3f45b-120">Deze instellingen zijn van invloed op andere items, zoals het maximum aantal gelijktijdige PowerShell-sessies dat door één beheerder kan worden geopend.</span><span class="sxs-lookup"><span data-stu-id="3f45b-120">These settings affect other items, such as the maximum number of simultaneous PowerShell sessions that can be opened by a single administrator.</span></span>
- <span data-ttu-id="3f45b-121">Elke Exchange Online-klant heeft een standaardbeleid voor Exchange Web Services (EWS) dat is afgestemd op EWS-client bewerkingen en beperkingen die van toepassing zijn op alle Outlook-clients.</span><span class="sxs-lookup"><span data-stu-id="3f45b-121">Each Exchange Online customer has a default Exchange Web Services (EWS) policy that is tuned for EWS client operations, and throttling that applies to all Outlook clients.</span></span>
