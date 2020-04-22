---
title: Aangepaste rapportageoplossingen gebruiken met geautomatiseerd onderzoek en respons
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Meer informatie over het integreren van geautomatiseerd onderzoek en respons met een aangepaste of externe rapportageoplossing.
ms.openlocfilehash: 4bd53de9a880fc774814588ed84dce2284535922
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634716"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="a4640-104">Gebruik de API voor beheeractiviteit voor aangepaste of externe rapportageoplossingen</span><span class="sxs-lookup"><span data-stu-id="a4640-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="a4640-105">Met [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)krijgt u gedetailleerde informatie over [geautomatiseerde onderzoeken.](air-view-investigation-results.md)</span><span class="sxs-lookup"><span data-stu-id="a4640-105">With [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="a4640-106">Sommige organisaties gebruiken echter ook een aangepaste of externe rapportageoplossing.</span><span class="sxs-lookup"><span data-stu-id="a4640-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="a4640-107">Als uw organisatie informatie over geautomatiseerde onderzoeken met een dergelijke oplossing wil integreren, u de Office 365 Management Activity API gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a4640-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="a4640-108">Gebruik de volgende bronnen om dit in te stellen:</span><span class="sxs-lookup"><span data-stu-id="a4640-108">Use the following resources to set this up:</span></span>

|<span data-ttu-id="a4640-109">Resource</span><span class="sxs-lookup"><span data-stu-id="a4640-109">Resource</span></span>  |<span data-ttu-id="a4640-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a4640-110">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="a4640-111">Overzicht van Office 365 Management API's</span><span class="sxs-lookup"><span data-stu-id="a4640-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="a4640-112">De Office 365 Management Activity API bevat informatie over verschillende gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit Microsoft 365- en Azure Active Directory-activiteitslogboeken.</span><span class="sxs-lookup"><span data-stu-id="a4640-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="a4640-113">Aan de slag met Office 365 Management API's</span><span class="sxs-lookup"><span data-stu-id="a4640-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="a4640-114">De Office 365 Management API maakt gebruik van Azure AD om verificatieservices voor uw toepassing te bieden om toegang te krijgen tot Microsoft 365-gegevens.</span><span class="sxs-lookup"><span data-stu-id="a4640-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="a4640-115">Volg de stappen in dit artikel om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a4640-115">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="a4640-116">Verwijzing naar api-activiteit voor Office 365-beheer</span><span class="sxs-lookup"><span data-stu-id="a4640-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="a4640-117">U de Office 365 Management Activity API gebruiken om informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op te halen uit microsoft 365- en Azure AD-activiteitslogboeken.</span><span class="sxs-lookup"><span data-stu-id="a4640-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="a4640-118">Lees dit artikel voor meer informatie over hoe dit werkt.</span><span class="sxs-lookup"><span data-stu-id="a4640-118">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="a4640-119">Api-schema voor activiteitsbeheer office 365</span><span class="sxs-lookup"><span data-stu-id="a4640-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="a4640-120">Krijg een overzicht van het [common-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [Office 365 ATP- en bedreigingsonderzoeks- en reactieschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor meer informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="a4640-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="a4640-121">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="a4640-121">Related articles</span></span>

- [<span data-ttu-id="a4640-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a4640-122">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

- [<span data-ttu-id="a4640-123">Meer informatie over geautomatiseerd onderzoek en reactie in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="a4640-123">Learn about automated investigation and response in Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)