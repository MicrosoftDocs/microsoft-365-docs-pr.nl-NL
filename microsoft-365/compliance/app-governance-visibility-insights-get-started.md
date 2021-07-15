---
title: Aan de slag met zichtbaarheid en inzichten
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Aan de slag met zichtbaarheid en inzichten.
ms.openlocfilehash: 93be3557c32345e81c7126b669ead8edf8ebac21
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430478"
---
# <a name="get-started-with-visibility-and-insights"></a><span data-ttu-id="e5327-103">Aan de slag met zichtbaarheid en inzichten</span><span class="sxs-lookup"><span data-stu-id="e5327-103">Get started with visibility and insights</span></span>

><span data-ttu-id="e5327-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="e5327-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="e5327-105">De eerste plaats om te beginnen is het app-governance-dashboard op [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span><span class="sxs-lookup"><span data-stu-id="e5327-105">The first place to get started is the app governance dashboard at [https://aka.ms/appgovernance](https://aka.ms/appgovernance).</span></span> <span data-ttu-id="e5327-106">Merk op dat het aanmeldingsaccount één van [deze app-governancebeheerdersrollen](app-governance-get-started.md#administrator-roles) moet hebben om app-governancegegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e5327-106">Note that your sign-in account must have one of [these app governance administrator roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>

![De overzichtpagina van de app-governance in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-overview.png)

<span data-ttu-id="e5327-108">Je kan ook toegang krijgen tot het app-governance-dashboard vanuit **Microsoft 365-beheercentrum > Microsoft 365-compliance > App-governance > Overzichtspagina**.</span><span class="sxs-lookup"><span data-stu-id="e5327-108">You can also access the app governance dashboard from **Microsoft 365 admin center > Microsoft 365 Compliance Center > App governance > Overview page**.</span></span>

## <a name="whats-available-on-the-dashboard"></a><span data-ttu-id="e5327-109">Wat is er beschikbaar op het dashboard</span><span class="sxs-lookup"><span data-stu-id="e5327-109">What’s available on the dashboard</span></span>

<span data-ttu-id="e5327-110">Het dashboard bevat een samenvatting van de componenten van het Microsoft 365-app-ecosysteem in de tenant:</span><span class="sxs-lookup"><span data-stu-id="e5327-110">The dashboard contains a summary of the components of the Microsoft 365 app ecosystem in the tenant:</span></span>

- <span data-ttu-id="e5327-111">**Tenant-samenvatting**: Het aantal categorieën voor belangrijke apps en waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="e5327-111">**Tenant summary**: The count of key app and alert categories.</span></span>
- <span data-ttu-id="e5327-112">**Waarschuwingen voor detectie en beleid**: De meest recente actieve waarschuwingen in de tenant</span><span class="sxs-lookup"><span data-stu-id="e5327-112">**Detection and policy alerts**: The most recent active alerts in the tenant</span></span>
- <span data-ttu-id="e5327-113">**Toegang tot gegevens en resources**: Samengestelde toegang van toepassings-API en algemeen gebruik van belangrijkste resources in de tenant.</span><span class="sxs-lookup"><span data-stu-id="e5327-113">**Data and resources access**: Aggregate application API access and overall usage of top resources in the tenant.</span></span> <span data-ttu-id="e5327-114">Muis over elke maandkolom in de grafiek om de overeenkomende datum weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e5327-114">Mouse over each month column in the graph to see the corresponding value.</span></span>
- <span data-ttu-id="e5327-115">**Verbeter de bescherming en het beheer van je app**: Aanbevolen acties zoals het maken van een beleid voor gebruik en machtigingen voor de app.</span><span class="sxs-lookup"><span data-stu-id="e5327-115">**Improve your app protection and governance**: Recommended actions such as creating an app usage or permissions policy.</span></span>
- <span data-ttu-id="e5327-116">**Belangrijkste apps per categorie**: De belangrijkste apps gesorteerd op de volgende categorieën:</span><span class="sxs-lookup"><span data-stu-id="e5327-116">**Top apps by categories**: The top apps sorted by these categories:</span></span>
  
  - <span data-ttu-id="e5327-117">**Alle categorieën**: Sorteren op alle beschikbare categorieën.</span><span class="sxs-lookup"><span data-stu-id="e5327-117">**All categories**: Sorts across all available categories.</span></span>
  - <span data-ttu-id="e5327-118">**Hoge bevoegdheid**: Hoge bevoegdheid is een intern bepaalde categorie gebaseerd op machine learning van het platform en signalen.</span><span class="sxs-lookup"><span data-stu-id="e5327-118">**High privilege**: High privilege is an internally determined category based on platform machine learning and signals.</span></span>
  - <span data-ttu-id="e5327-119">**Te veel machtigingen**: Wanneer app-governance telemetrie ontvangt die aangeeft dat een machtiging is toegekend aan een toepassing en die niet is gebruikt in de afgelopen 90 dagen, heeft de toepassing te veel machtigingen.</span><span class="sxs-lookup"><span data-stu-id="e5327-119">**Overprivileged**: When app governance receives telemetry that indicates that a permission granted to an application has not been used in the last 90 days, that application is overprivileged.</span></span> <span data-ttu-id="e5327-120">App-governance moet ten minste 90 dagen actief zijn om te bepalen of een app te veel machtigingen heeft.</span><span class="sxs-lookup"><span data-stu-id="e5327-120">App governance must be operating for at least 90 days to determine if any app is overprivileged.</span></span>  
  - <span data-ttu-id="e5327-121">**Niet-geverifieerd**: Toepassingen die geen [uitgeverscertificering](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) hebben gekregen worden beschouwd als niet-geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="e5327-121">**Unverified**: Applications that have not received [publisher certification](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) are considered unverified.</span></span>
  - <span data-ttu-id="e5327-122">**Alleen app**: [Toegangsmachtigingen](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) die door apps gebruikt worden die zonder een aanwezige aangemelde gebruiker kunnen uitgevoerd worden.</span><span class="sxs-lookup"><span data-stu-id="e5327-122">**App only**: [Application permissions](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) are used by apps that can run without a signed-in user present.</span></span> <span data-ttu-id="e5327-123">Apps met machtigingen voor toegang tot gegevens in de hele tenant zijn een potentieel hoog risico.</span><span class="sxs-lookup"><span data-stu-id="e5327-123">Apps with permissions to access data across the tenant are potentially a higher risk.</span></span>
  - <span data-ttu-id="e5327-124">**Nieuwe apps**: Nieuwe Microsoft 365-apps die in de afgelopen zeven dagen geregistreerd werden.</span><span class="sxs-lookup"><span data-stu-id="e5327-124">**New apps**: New Microsoft 365 apps that have been registered in the last seven days.</span></span>  

## <a name="next-step"></a><span data-ttu-id="e5327-125">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="e5327-125">Next step</span></span>

<span data-ttu-id="e5327-126">[Gedetailleerde inzichten op voor een specifieke app ophalen](app-governance-visibility-insights-view-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e5327-126">[Get detailed insights on a specific app](app-governance-visibility-insights-view-apps.md).</span></span>
