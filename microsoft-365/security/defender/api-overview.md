---
title: Overzicht van Microsoft 365 Defender-API's
description: Meer informatie over de beschikbare API's in Microsoft 365 Defender
keywords: api's, overzicht, incident, incidenten, bedreigingsjacht, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: b19a6072be5f97b90c117f053ccae4593587c43d
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730892"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="cc141-104">Overzicht van Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="cc141-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cc141-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cc141-105">**Applies to:**</span></span>

- <span data-ttu-id="cc141-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cc141-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc141-107">Sommige informatie is gerelateerd aan voorlopige productversies die mogelijk aanzienlijk gewijzigd worden voordat ze commercieel gepubliceerd worden.</span><span class="sxs-lookup"><span data-stu-id="cc141-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="cc141-108">Microsoft geeft geen garantie, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt beschreven.</span><span class="sxs-lookup"><span data-stu-id="cc141-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="cc141-109">Microsoft 365 Defender is gebouwd op een platform dat klaar is voor integratie.</span><span class="sxs-lookup"><span data-stu-id="cc141-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="cc141-110">Gebruik de Microsoft 365 Defender-API's om werkstromen te automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen.</span><span class="sxs-lookup"><span data-stu-id="cc141-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="cc141-111">**[Wachtrij gecombineerde](api-incident.md)** incidenten: focus op wat kritiek is door het volledige aanvalsbereik en alle beïnvloede activa te groeperen onder de incident-API.</span><span class="sxs-lookup"><span data-stu-id="cc141-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="cc141-112">**[Op zoek](api-advanced-hunting.md)** naar bedreigingen tussen producten: gebruik de organisatiekennis van uw beveiligingsteam om te zoeken naar tekenen van compromissen door uw eigen aangepaste query's te maken om onbewerkte gegevens te oversprokken die zijn verzameld in meerdere beveiligingsproducten.</span><span class="sxs-lookup"><span data-stu-id="cc141-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="cc141-113">Gebruik de [Streaming API om](../defender-endpoint/raw-data-export.md) realtimegebeurtenissen en waarschuwingen van exemplaren te verzenden terwijl deze binnen één gegevensstroom plaatsvinden.</span><span class="sxs-lookup"><span data-stu-id="cc141-113">Use the [Streaming API](../defender-endpoint/raw-data-export.md) to ship real-time events and alerts from instances as they occur within a single data stream.</span></span>


<span data-ttu-id="cc141-114">Naast deze Microsoft 365 defender-specifieke API's, worden in elk [](api-articles.md) van onze andere beveiligingsproducten extra API's aan de man Microsoft 365 om te profiteren van hun unieke mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="cc141-114">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>


> [!NOTE]
> <span data-ttu-id="cc141-115">De overgang naar de geïntegreerde portal mag geen invloed hebben op de PowerBi-dashboards op basis van MICROSOFT Defender voor eindpunt-API's.</span><span class="sxs-lookup"><span data-stu-id="cc141-115">The transition to the unified portal should not affect the PowerBi dashboards based on Microsoft Defender for Endpoint APIs.</span></span> <span data-ttu-id="cc141-116">U kunt blijven werken met de bestaande API's, ongeacht de interactieve portalovergang.</span><span class="sxs-lookup"><span data-stu-id="cc141-116">You can continue to work with the existing APIs regardless of the interactive portal transition.</span></span>


## <a name="learn-more"></a><span data-ttu-id="cc141-117">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="cc141-117">Learn more</span></span>

| <span data-ttu-id="cc141-118">**Meer informatie over het openen van de API's**</span><span class="sxs-lookup"><span data-stu-id="cc141-118">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="cc141-119">Meer informatie over API-quota en -licenties</span><span class="sxs-lookup"><span data-stu-id="cc141-119">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="cc141-120">Toegang tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="cc141-120">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="cc141-121">**Apps maken**</span><span class="sxs-lookup"><span data-stu-id="cc141-121">**Build apps**</span></span> |
| [<span data-ttu-id="cc141-122">Een 'Hello world' app maken</span><span class="sxs-lookup"><span data-stu-id="cc141-122">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="cc141-123">Een app maken voor toegang Microsoft 365 Defender-API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="cc141-123">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="cc141-124">Een app maken voor toegang Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="cc141-124">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="cc141-125">Een app maken met partnertoegang voor meerdere tenants Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="cc141-125">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="cc141-126">**Problemen met uw apps oplossen en onderhouden**</span><span class="sxs-lookup"><span data-stu-id="cc141-126">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="cc141-127">Api-foutcodes begrijpen</span><span class="sxs-lookup"><span data-stu-id="cc141-127">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="cc141-128">Geheimen beheren in uw apps met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="cc141-128">Manage secrets in your apps with Azure Key Vault</span></span>](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="cc141-129">OAuth 2.0-autorisatie implementeren voor het aanmelden van gebruikers</span><span class="sxs-lookup"><span data-stu-id="cc141-129">Implement OAuth 2.0 authorization for user sign in</span></span>](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |