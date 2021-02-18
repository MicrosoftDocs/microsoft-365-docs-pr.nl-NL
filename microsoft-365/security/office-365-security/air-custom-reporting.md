---
title: Aangepaste rapportageoplossingen met automatisch onderzoek en reactie
keywords: SIEM, API, AIR, AutoIR, ATP, geautomatiseerd onderzoek, integratie, aangepast rapport
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Lees hoe u automatisch onderzoek en antwoorden kunt integreren met een aangepaste rapportageoplossing of een oplossing van derden.
ms.date: 01/29/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13782a8e0a8c691a66f214d3f9f03ef9cad4da1f
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287135"
---
# <a name="custom-or-third-party-reporting-solutions-for-microsoft-defender-for-office-365"></a><span data-ttu-id="25e05-104">Aangepaste of externe rapportageoplossingen voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="25e05-104">Custom or third-party reporting solutions for Microsoft Defender for Office 365</span></span>

<span data-ttu-id="25e05-105">Met [Microsoft Defender voor Office 365](office-365-atp.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="25e05-105">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="25e05-106">Sommige organisaties gebruiken echter ook een aangepaste rapportageoplossing of rapportageoplossing van derden.</span><span class="sxs-lookup"><span data-stu-id="25e05-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="25e05-107">Als uw organisatie informatie [](office-365-air.md) over geautomatiseerde onderzoeken wil integreren met een dergelijke oplossing, kunt u de Office 365 Management Activity-API gebruiken.</span><span class="sxs-lookup"><span data-stu-id="25e05-107">If your organization wants to integrate information about [automated investigations](office-365-air.md) with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="25e05-108">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="25e05-108">**Applies to**</span></span>
- [<span data-ttu-id="25e05-109">Abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="25e05-109">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="25e05-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25e05-110">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="25e05-111">Met [Microsoft Defender voor Office 365](office-365-atp.md)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="25e05-111">With [Microsoft Defender for Office 365](office-365-atp.md), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="25e05-112">Sommige organisaties gebruiken echter ook een aangepaste rapportageoplossing of rapportageoplossing van derden.</span><span class="sxs-lookup"><span data-stu-id="25e05-112">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="25e05-113">Als uw organisatie informatie over geautomatiseerde onderzoeken wil integreren met een dergelijke oplossing, kunt u de Office 365 Management Activity-API gebruiken.</span><span class="sxs-lookup"><span data-stu-id="25e05-113">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

|<span data-ttu-id="25e05-114">Resource</span><span class="sxs-lookup"><span data-stu-id="25e05-114">Resource</span></span>|<span data-ttu-id="25e05-115">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="25e05-115">Description</span></span>|
|:---|:---|
|[<span data-ttu-id="25e05-116">Overzicht van Office 365-beheer-API's</span><span class="sxs-lookup"><span data-stu-id="25e05-116">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="25e05-117">De Office 365 Management Activity-API biedt informatie over diverse gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit microsoft 365- en Azure Active Directory-activiteitslogboeken.</span><span class="sxs-lookup"><span data-stu-id="25e05-117">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="25e05-118">Aan de slag met Beheer-API's van Office 365</span><span class="sxs-lookup"><span data-stu-id="25e05-118">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="25e05-119">De Office 365 Management-API gebruikt Azure AD om verificatieservices aan te bieden voor uw toepassing voor toegang tot Microsoft 365-gegevens.</span><span class="sxs-lookup"><span data-stu-id="25e05-119">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="25e05-120">Volg de stappen in dit artikel om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="25e05-120">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="25e05-121">Office 365 Management Activity-API-referentie</span><span class="sxs-lookup"><span data-stu-id="25e05-121">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="25e05-122">U kunt de Office 365 Management Activity-API gebruiken om informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op te halen uit activiteitenlogboeken van Microsoft 365 en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="25e05-122">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="25e05-123">Lees dit artikel voor meer informatie over hoe dit werkt.</span><span class="sxs-lookup"><span data-stu-id="25e05-123">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="25e05-124">Office 365 Management Activity-API-schema</span><span class="sxs-lookup"><span data-stu-id="25e05-124">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="25e05-125">Krijg een overzicht van het [algemene schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het Defender voor [Office 365-](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) en bedreigingsonderzoek en antwoordschema voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de Management Activity API van Office 365.</span><span class="sxs-lookup"><span data-stu-id="25e05-125">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Defender for Office 365 and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="25e05-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="25e05-126">See also</span></span>

- [<span data-ttu-id="25e05-127">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="25e05-127">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="25e05-128">Automatisch onderzoek en antwoorden in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="25e05-128">Automated investigation and response in Microsoft 365 Defender</span></span>](../mtp/mtp-autoir.md)
