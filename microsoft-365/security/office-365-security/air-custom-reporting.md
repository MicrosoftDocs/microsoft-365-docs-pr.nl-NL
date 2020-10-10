---
title: Aangepaste rapportage oplossingen gebruiken met automatisch onderzoek en antwoord
keywords: SIEM, API, AIR, autoIR, ATP, automatisch onderzoek, integratie, aangepast rapport
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
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
description: Leer hoe u een geautomatiseerd onderzoek en antwoord kunt integreren met een aangepaste oplossing of een rapportage oplossing van derden.
ms.date: 09/29/2020
ms.custom:
- air
ms.openlocfilehash: 429ceae87e3beeb9ec0a254b120289be4ab51d16
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411971"
---
# <a name="use-the-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="59242-104">De API voor beheeractiviteiten gebruiken voor aangepaste oplossingen of oplossingen voor rapportage van derden</span><span class="sxs-lookup"><span data-stu-id="59242-104">Use the Management Activity API for custom or third-party reporting solutions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="59242-105">Met [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)kunt u [gedetailleerde informatie raadplegen over geautomatiseerde onderzoek](air-view-investigation-results.md).</span><span class="sxs-lookup"><span data-stu-id="59242-105">With [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp), you get [detailed information about automated investigations](air-view-investigation-results.md).</span></span> <span data-ttu-id="59242-106">Sommige organisaties gebruiken echter ook een aangepaste oplossing of een rapportage oplossing van derden.</span><span class="sxs-lookup"><span data-stu-id="59242-106">However, some organizations also use a custom or third-party reporting solution.</span></span> <span data-ttu-id="59242-107">Als uw organisatie informatie wil integreren over een geautomatiseerd onderzoek met een dergelijke oplossing, kunt u gebruikmaken van de API Office 365 Management Activity.</span><span class="sxs-lookup"><span data-stu-id="59242-107">If your organization wants to integrate information about automated investigations with such a solution, you can use the Office 365 Management Activity API.</span></span>

<span data-ttu-id="59242-108">Gebruik de volgende bronnen om dit in te stellen:</span><span class="sxs-lookup"><span data-stu-id="59242-108">Use the following resources to set this up:</span></span>

****

|<span data-ttu-id="59242-109">Materialen</span><span class="sxs-lookup"><span data-stu-id="59242-109">Resource</span></span>|<span data-ttu-id="59242-110">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="59242-110">Description</span></span>|
|---|---|
|[<span data-ttu-id="59242-111">Overzicht van Office 365 Management Api's</span><span class="sxs-lookup"><span data-stu-id="59242-111">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)|<span data-ttu-id="59242-112">De Office 365 Management Activity API biedt informatie over diverse acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure Active Directory-activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="59242-112">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Microsoft 365 and Azure Active Directory activity logs.</span></span>|
|[<span data-ttu-id="59242-113">Aan de slag met Api's van Office 365 Management</span><span class="sxs-lookup"><span data-stu-id="59242-113">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)|<span data-ttu-id="59242-114">De Office 365-beheer-API maakt gebruik van Azure AD om authenticatie services te bieden voor de toepassing om toegang te krijgen tot gegevens van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="59242-114">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Microsoft 365 data.</span></span> <span data-ttu-id="59242-115">Voer de stappen in dit artikel uit om dit in te stellen.</span><span class="sxs-lookup"><span data-stu-id="59242-115">Follow the steps in this article to set this up.</span></span>|
|[<span data-ttu-id="59242-116">Naslag voor Office 365 Management Activity API</span><span class="sxs-lookup"><span data-stu-id="59242-116">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)|<span data-ttu-id="59242-117">U kunt de Office 365 Management Activity API gebruiken om informatie op te halen over acties en gebeurtenissen van gebruikers, beheerders, systemen en beleid uit Microsoft 365 en Azure AD-activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="59242-117">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Microsoft 365 and Azure AD activity logs.</span></span> <span data-ttu-id="59242-118">Lees dit artikel voor meer informatie over hoe dit werkt.</span><span class="sxs-lookup"><span data-stu-id="59242-118">Read this article to learn more about how this works.</span></span>|
|[<span data-ttu-id="59242-119">Office 365 Management Activity API-schema</span><span class="sxs-lookup"><span data-stu-id="59242-119">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)|<span data-ttu-id="59242-120">Bekijk een overzicht van het [gemeenschappelijke schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) en het [schema Office 365 ATP-en risico onderzoek en antwoordschema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) voor informatie over specifieke soorten gegevens die beschikbaar zijn via de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="59242-120">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>|
|

## <a name="see-also"></a><span data-ttu-id="59242-121">Zie ook</span><span class="sxs-lookup"><span data-stu-id="59242-121">See also</span></span>

- [<span data-ttu-id="59242-122">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="59242-122">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

- [<span data-ttu-id="59242-123">Automatisch onderzoek en antwoord in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59242-123">Automated investigation and response in Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
