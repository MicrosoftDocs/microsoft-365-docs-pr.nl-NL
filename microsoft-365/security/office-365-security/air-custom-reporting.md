---
title: Aangepaste rapportageoplossingen gebruiken met geautomatiseerd onderzoek en respons in Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, reactie, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Meer informatie over het integreren van geautomatiseerd onderzoek en respons in Office 365 met een aangepaste of externe rapportageoplossing.
ms.openlocfilehash: 3df69c9118b3170924a99a1787761b1bb07aadfa
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/20/2020
ms.locfileid: "42811008"
---
# <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="3bfb1-104">De OFFICE 365-beheeractiviteits-API gebruiken voor aangepaste of externe rapportageoplossingen</span><span class="sxs-lookup"><span data-stu-id="3bfb1-104">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="3bfb1-105">Met [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="3bfb1-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="3bfb1-106">Sommige organisaties gebruiken echter ook een aangepaste of externe rapportageoplossing.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="3bfb1-107">Als uw organisatie informatie over geautomatiseerde onderzoeken met een dergelijke oplossing wil integreren, u de API voor beheeractiviteit van Office 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="3bfb1-108">Gebruik de volgende resources om dit in te stellen:</span><span class="sxs-lookup"><span data-stu-id="3bfb1-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="3bfb1-109">Resource</span><span class="sxs-lookup"><span data-stu-id="3bfb1-109">Resource</span></span>  |<span data-ttu-id="3bfb1-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3bfb1-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="3bfb1-111">Overzicht van API's voor Office 365-beheer</span><span class="sxs-lookup"><span data-stu-id="3bfb1-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="3bfb1-112">De OFFICE 365-beheeractiviteits-api biedt informatie over verschillende gebruikers-, beheer-, systeem- en beleidsacties en -gebeurtenissen uit activiteitenlogboeken en gebeurtenissen van Office 365 en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="3bfb1-113">Aan de slag met Api's voor Beheer van Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfb1-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="3bfb1-114">De Office 365 Management API maakt gebruik van Azure AD om verificatieservices voor uw toepassing te bieden om toegang te krijgen tot Office 365-gegevens.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="3bfb1-115">Volg de stappen in dit artikel om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="3bfb1-116">API-naslaginformatie over beheeractiviteit van Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfb1-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="3bfb1-117">U de API voor beheeractiviteiten van Office 365 gebruiken om informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op te halen uit activiteitenlogboeken en gebeurtenissen van Office 365 en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="3bfb1-118">Lees dit artikel voor meer informatie over hoe dit werkt.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="3bfb1-119">API-schema voor beheeractiviteit van Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfb1-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="3bfb1-120">Krijg een overzicht van het [Algemene schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [Office 365 ATP- en bedreigingsonderzoeks- en reactieschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de OFFICE 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="3bfb1-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="3bfb1-121">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3bfb1-121">Related articles</span></span>

- [<span data-ttu-id="3bfb1-122">Geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="3bfb1-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="3bfb1-123">Meer informatie over geautomatiseerd onderzoek en respons in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3bfb1-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)