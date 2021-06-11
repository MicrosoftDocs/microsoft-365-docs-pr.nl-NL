---
title: Microsoft 365-connectiviteit controleren
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: In dit artikel vindt u informatie over de hulpprogramma's en technieken die u kunt gebruiken om de Microsoft 365 bewaken en onderhouden.
ms.openlocfilehash: dfba158085e6642856049d7894b4156f42353236
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538805"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="c9d0b-103">Microsoft 365-connectiviteit controleren</span><span class="sxs-lookup"><span data-stu-id="c9d0b-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="c9d0b-104">Nadat u een Microsoft 365 hebt geïmplementeerd, kunt u de Microsoft 365 met behulp van enkele van de onderstaande hulpprogramma's en technieken.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="c9d0b-105">U wilt de officiële richtlijnen voor [service-](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) en continuïteitsrichtlijnen en onze best practices voor het gebruik van Microsoft 365 [op een traag netwerk begrijpen.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="c9d0b-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="c9d0b-106">U wilt ook de app voor beheerders [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) en onze Microsoft 365 voor Bedrijven [- Help voor beheerders .](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="c9d0b-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="c9d0b-107">Monitoring Microsoft 365 Connectivity</span><span class="sxs-lookup"><span data-stu-id="c9d0b-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c9d0b-108">**Op de hoogte worden gesteld van Microsoft 365 eindpunten**</span><span class="sxs-lookup"><span data-stu-id="c9d0b-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="c9d0b-109">Als u Microsoft 365 eindpunten [beheert,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)wilt u meldingen ontvangen wanneer we nieuwe eindpunten publiceren, kunt u zich abonneren op onze RSS-feed met uw favoriete RSS-lezer.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="c9d0b-110">U kunt zich als eerste [abonneren via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) of u kunt de [RSS-feedupdates](https://go.microsoft.com/fwlink/p/?LinkId=532417)per e-mail naar u sturen.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="c9d0b-111">**Gebruik System Center om de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="c9d0b-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="c9d0b-112">Als u Microsoft-System Center gebruikt, kunt u het System Center [Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) voor Office 365 downloaden om de Microsoft 365 controleren.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="c9d0b-113">Zie de handleiding voor beheerpakketbewerkingen voor meer gedetailleerde richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-113">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="c9d0b-114">**De status van Azure ExpressRoute controleren**</span><span class="sxs-lookup"><span data-stu-id="c9d0b-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="c9d0b-115">Als u verbinding maakt met Microsoft 365 met Behulp van Azure ExpressRoute voor Microsoft 365, wilt u ervoor zorgen dat u zowel het Microsoft 365 Service Health Dashboard als azure [Reducing troubleshooting time](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) with Azure Resource health gebruikt</span><span class="sxs-lookup"><span data-stu-id="c9d0b-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="c9d0b-116">**Azure AD-Verbinding maken gebruiken met AD FS**</span><span class="sxs-lookup"><span data-stu-id="c9d0b-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="c9d0b-117">Als u AD FS voor Één Sign-On gebruikt met Microsoft 365, wilt u Azure AD Verbinding maken Health gebruiken om uw [AD FS-infrastructuur](/azure/active-directory/hybrid/how-to-connect-health-adfs)te controleren.</span><span class="sxs-lookup"><span data-stu-id="c9d0b-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="c9d0b-118">**Programmatisch controleren Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="c9d0b-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="c9d0b-119">Raadpleeg onze richtlijnen voor de [Microsoft 365 Management API.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="c9d0b-119">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="c9d0b-120">Met deze korte koppeling kunt u teruggaan: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="c9d0b-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c9d0b-121">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c9d0b-121">Related topics</span></span>

[<span data-ttu-id="c9d0b-122">Microsoft 365 Enterprise services en toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="c9d0b-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="c9d0b-123">Uw organisatie voorbereiden op Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9d0b-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="c9d0b-124">Netwerkplanning en prestaties optimaliseren voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c9d0b-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="c9d0b-125">Microsoft 365 integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="c9d0b-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="c9d0b-126">Eindpunten Microsoft 365 beheren</span><span class="sxs-lookup"><span data-stu-id="c9d0b-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
