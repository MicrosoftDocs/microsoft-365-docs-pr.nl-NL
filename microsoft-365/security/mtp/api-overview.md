---
title: Overzicht van Microsoft 365 Defender-Api's
description: Meer informatie over de beschikbare Api's in Microsoft 365 Defender
keywords: API, api's, overzicht, incident, incidenten, Threat jacht, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 1a75a561e60c05208e8ea302505f9644ac0bc044
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719188"
---
# <a name="overview-of--microsoft-365-defender-apis"></a><span data-ttu-id="a3b4e-104">Overzicht van Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="a3b4e-104">Overview of  Microsoft 365 Defender APIs</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="a3b4e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="a3b4e-105">**Applies to:**</span></span>

- <span data-ttu-id="a3b4e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3b4e-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a3b4e-107">Sommige informatie verhoudt zich tot een voorvrijgegeven product dat bij de commerciële versie van de commerciële versie mogelijk ingrijpend werd gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="a3b4e-108">Microsoft biedt geen garanties, expliciete of impliciete informatie met betrekking tot de informatie die u hier opgeeft.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="a3b4e-109">Microsoft 365 Defender is gebouwd op basis van een platform voor de integratie-Ready.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-109">Microsoft 365 Defender is built on top of an integration-ready platform.</span></span>

<span data-ttu-id="a3b4e-110">Met de Microsoft 365 Defender-Api's kunt u werkstromen automatiseren op basis van de tabellen gedeeld incident en Geavanceerd jacht.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-110">Use the Microsoft 365 Defender APIs to automate workflows based on the shared incident and advanced hunting tables.</span></span>

- <span data-ttu-id="a3b4e-111">**[Wachtrij voor samengetelde aanvragen](api-incident.md)** -focus op wat is er essentieel voor het groeperen van het volledige aanvals bereik en alle beïnvloede assets onder de incident API.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-111">**[Combined incidents queue](api-incident.md)** - Focus on what's critical by grouping the full attack scope and all impacted assets together under the incident API.</span></span>

- <span data-ttu-id="a3b4e-112">**[Jacht](api-advanced-hunting.md)** met behulp van de bedreiging van de bedreiging van uw beveiligingsteam: Profiteer van de organisatorische informatie van uw Beveiligingsteam om te beginnen met het aanbrengen van tekenen van compromissen door uw eigen aangepaste query's te maken met SIFT-gegevens die worden verzameld in meerdere beveiligingsproducten.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-112">**[Cross-product threat hunting](api-advanced-hunting.md)** - Leverage your security team's organizational knowledge to hunt for signs of compromise, by creating your own custom queries to sift over raw data collected across multiple protection products.</span></span>

<span data-ttu-id="a3b4e-113">Met deze Microsoft 365-Api's voor het toepassen van ondersteuning biedt elk van onze andere beveiligingsproducten [extra api's](api-articles.md) , zodat u optimaal gebruik kunt maken van hun unieke mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="a3b4e-113">Along with these Microsoft 365 Defender-specific APIs, each of our other security products expose [additional APIs](api-articles.md) to help you take advantage of their unique capabilities.</span></span>

## <a name="learn-more"></a><span data-ttu-id="a3b4e-114">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="a3b4e-114">Learn more</span></span>

| <span data-ttu-id="a3b4e-115">**Meer informatie over het openen van de Api's**</span><span class="sxs-lookup"><span data-stu-id="a3b4e-115">**Understand how to access the APIs**</span></span> |
|-|
| [<span data-ttu-id="a3b4e-116">Meer informatie over API-quota's en licenties</span><span class="sxs-lookup"><span data-stu-id="a3b4e-116">Learn about API quotas and licensing</span></span>](api-terms.md) |
| [<span data-ttu-id="a3b4e-117">Toegang tot de Microsoft 365 Defender-Api's</span><span class="sxs-lookup"><span data-stu-id="a3b4e-117">Access the Microsoft 365 Defender APIs</span></span>](api-access.md) |
| <span data-ttu-id="a3b4e-118">**Apps maken**</span><span class="sxs-lookup"><span data-stu-id="a3b4e-118">**Build apps**</span></span> |
| [<span data-ttu-id="a3b4e-119">Een ' Hallo wereld '-app maken</span><span class="sxs-lookup"><span data-stu-id="a3b4e-119">Create a 'Hello world' app</span></span>](api-hello-world.md) |
| [<span data-ttu-id="a3b4e-120">Een app maken om toegang te krijgen tot Microsoft 365 Defender-Api's namens een gebruiker</span><span class="sxs-lookup"><span data-stu-id="a3b4e-120">Create an app to access Microsoft 365 Defender APIs on behalf of a user</span></span>](api-create-app-user-context.md) |
| [<span data-ttu-id="a3b4e-121">Een app maken om toegang te krijgen tot Microsoft 365 Defender zonder een gebruiker</span><span class="sxs-lookup"><span data-stu-id="a3b4e-121">Create an app to access Microsoft 365 Defender without a user</span></span>](api-create-app-web.md) |
| [<span data-ttu-id="a3b4e-122">Een app maken met toegang met meerdere tenants voor partners van Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a3b4e-122">Create an app with multi-tenant partner access to Microsoft 365 Defender APIs</span></span>](api-partner-access.md) |
| <span data-ttu-id="a3b4e-123">**Problemen oplossen en uw apps onderhouden**</span><span class="sxs-lookup"><span data-stu-id="a3b4e-123">**Troubleshoot and maintain your apps**</span></span> |
| [<span data-ttu-id="a3b4e-124">Meer informatie over API-foutcodes</span><span class="sxs-lookup"><span data-stu-id="a3b4e-124">Understand API error codes</span></span>](api-error-codes.md) |
| [<span data-ttu-id="a3b4e-125">Geheimen in uw apps beheren met Azure-sleutel kluis</span><span class="sxs-lookup"><span data-stu-id="a3b4e-125">Manage secrets in your apps with Azure Key Vault</span></span>](https://docs.microsoft.com/learn/modules/manage-secrets-with-azure-key-vault/) |
| [<span data-ttu-id="a3b4e-126">OAuth 2,0-autorisatie voor aanmelding van gebruikers implementeren</span><span class="sxs-lookup"><span data-stu-id="a3b4e-126">Implement OAuth 2.0 authorization for user sign in</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
