---
title: Overzicht van Microsoft 365 Defender API's
description: Meer informatie over de beschikbare API's in Microsoft 365 Defender
keywords: api, apis, overview, incident, incidents, threat hunting, microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8e06d4b4f7c895b532091c73e8269411fb38bf21
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49931000"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="2edf9-104">Overzicht van Microsoft 365 Defender API's</span><span class="sxs-lookup"><span data-stu-id="2edf9-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2edf9-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2edf9-105">**Applies to:**</span></span>

- <span data-ttu-id="2edf9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2edf9-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2edf9-107">Sommige informatie heeft betrekking op vooraf uitgebracht product dat aanzienlijk kan worden gewijzigd voordat het in de handel wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="2edf9-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2edf9-108">Microsoft biedt geen garanties, uitdrukkelijk of impliciet, met betrekking tot de informatie die hier wordt be gegeven.</span><span class="sxs-lookup"><span data-stu-id="2edf9-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2edf9-109">Microsoft 365 Defender is gebouwd op een platform dat klaar is voor integratie.</span><span class="sxs-lookup"><span data-stu-id="2edf9-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="2edf9-110">Gebruik de Microsoft 365 Defender API's om werkstromen te automatiseren op basis van het gedeelde incident en geavanceerde zoektabellen.</span><span class="sxs-lookup"><span data-stu-id="2edf9-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="2edf9-111">**[Wachtrij met gecombineerde](api-incident.md)** incidenten: richt u op wat kritiek is door het volledige bereik van de aanval en alle beïnvloede assets te groeperen onder de incident-API.</span><span class="sxs-lookup"><span data-stu-id="2edf9-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="2edf9-112">**[Op zoek](api-advanced-hunting.md)** naar bedreigingen in verschillende producten - Maak gebruik van de kennis van uw beveiligingsteam in de organisatie om te zoeken naar tekens van bedreigingen door uw eigen aangepaste query's te maken om onbewerkte gegevens te ft die worden verzameld over meerdere beveiligingsproducten.</span><span class="sxs-lookup"><span data-stu-id="2edf9-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="2edf9-113">Naast deze Microsoft 365 Defender-specifieke API's worden [](api-articles.md) in al onze andere beveiligingsproducten extra API's aan de man brengen om u te helpen profiteren van hun unieke mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="2edf9-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="2edf9-114">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="2edf9-114">Learn more</span></span>

| <span data-ttu-id="2edf9-115">**Meer informatie over het openen van de API's**</span><span class="sxs-lookup"><span data-stu-id="2edf9-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="2edf9-116">Meer informatie over API-quota's en licenties</span><span class="sxs-lookup"><span data-stu-id="2edf9-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="2edf9-117">Toegang tot de Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="2edf9-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="2edf9-118">**Apps bouwen**</span><span class="sxs-lookup"><span data-stu-id="2edf9-118">**Build apps**</span></span> |
| [<span data-ttu-id="2edf9-119">Een app 'Hallo wereld' maken</span><span class="sxs-lookup"><span data-stu-id="2edf9-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="2edf9-120">Een app maken voor toegang tot Microsoft 365 Defender API's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2edf9-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="2edf9-121">Een app maken voor toegang tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="2edf9-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="2edf9-122">Een app maken met partnertoegang met meerdere tenants tot Microsoft 365 Defender-API's</span><span class="sxs-lookup"><span data-stu-id="2edf9-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="2edf9-123">**Problemen met uw apps oplossen en onderhouden**</span><span class="sxs-lookup"><span data-stu-id="2edf9-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="2edf9-124">Meer informatie over API-foutcodes</span><span class="sxs-lookup"><span data-stu-id="2edf9-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="2edf9-125">Geheimen in uw apps beheren met Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="2edf9-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="2edf9-126">OAuth 2.0-autorisatie implementeren voor aanmelding door gebruiker</span><span class="sxs-lookup"><span data-stu-id="2edf9-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
