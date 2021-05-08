---
title: Aangepaste rapportageoplossingen met geautomatiseerd onderzoek en antwoord
keywords: SIEM, API, AIR, autoIR, Microsoft Defender voor Eindpunt, geautomatiseerd onderzoek, integratie, aangepast rapport
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Lees hoe u geautomatiseerd onderzoek en antwoord kunt integreren met een aangepaste of externe rapportageoplossing.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ed752f9514f1d2c8cadeb7cbbd1d7b9311b1b5f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275010"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="3196e-104">Aangepaste of externe rapportageoplossingen voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3196e-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="3196e-105">Met [Microsoft Defender voor Office 365](defender-for-office-365.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="3196e-105">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="3196e-106">Sommige organisaties gebruiken echter ook een aangepaste of externe rapportageoplossing.</span><span class="sxs-lookup"><span data-stu-id="3196e-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="3196e-107">Als uw organisatie informatie [](office-365-air.md) over geautomatiseerde onderzoeken met een dergelijke oplossing wil integreren, kunt u de Office 365 Management Activity API gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3196e-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="3196e-108">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3196e-108">**Applies to**</span></span>
- [<span data-ttu-id="3196e-109">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3196e-109">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3196e-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3196e-110">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3196e-111">Met [Microsoft Defender voor Office 365](defender-for-office-365.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="3196e-111">With [Microsoft Defender for Office 365](defender-for-office-365.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="3196e-112">Sommige organisaties gebruiken echter ook een aangepaste of externe rapportageoplossing.</span><span class="sxs-lookup"><span data-stu-id="3196e-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="3196e-113">Als uw organisatie informatie over geautomatiseerde onderzoeken met een dergelijke oplossing wil integreren, kunt u de Office 365 Management Activity API gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3196e-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="3196e-114">Resource</span><span class="sxs-lookup"><span data-stu-id="3196e-114">Resource</span></span>|<span data-ttu-id="3196e-115">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="3196e-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="3196e-116">Office 365 Overzicht van beheer-API's</span><span class="sxs-lookup"><span data-stu-id="3196e-116">Office 365 Management APIs overview</span></span>](/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="3196e-117">De Office 365 Management Activity API bevat informatie over verschillende gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit Microsoft 365 en Azure Active Directory activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="3196e-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="3196e-118">Aan de slag met Office 365 management-API's</span><span class="sxs-lookup"><span data-stu-id="3196e-118">Get started with Office 365 Management APIs</span></span>](/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="3196e-119">De Office 365 Management API gebruikt Azure AD om verificatieservices aan te bieden voor uw toepassing om toegang te krijgen tot Microsoft 365 gegevens.</span><span class="sxs-lookup"><span data-stu-id="3196e-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="3196e-120">Volg de stappen in dit artikel om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3196e-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="3196e-121">Office 365 Management Activity-API-referentie</span><span class="sxs-lookup"><span data-stu-id="3196e-121">Office 365 Management Activity API reference</span></span>](/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="3196e-122">U kunt de Office 365 Management Activity API gebruiken om informatie op te halen over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit Microsoft 365 en Azure AD-activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="3196e-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="3196e-123">Lees dit artikel voor meer informatie over hoe dit werkt.</span><span class="sxs-lookup"><span data-stu-id="3196e-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="3196e-124">Office 365 Management Activity-API-schema</span><span class="sxs-lookup"><span data-stu-id="3196e-124">Office 365 Management Activity API schema</span></span>](/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="3196e-125">Krijg een overzicht van het algemene [schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [Defender voor Office 365-](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) en bedreigingsonderzoeks- en antwoordschema voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="3196e-125">Get an overview of the [Common schema](/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="3196e-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3196e-126">See also</span></span>

- [<span data-ttu-id="3196e-127">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3196e-127">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3196e-128">Geautomatiseerd onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3196e-128">Automated investigation and response in Microsoft 365 Defender</span></span>](/microsoft-365/security/defender/m365d-autoir)
