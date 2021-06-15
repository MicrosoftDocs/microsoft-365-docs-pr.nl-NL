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
ms.openlocfilehash: 8fa0820cf9b7778001be5184041e5c96930a29dd
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924197"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="5599a-103">Microsoft 365-connectiviteit controleren</span><span class="sxs-lookup"><span data-stu-id="5599a-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="5599a-104">Nadat u een Microsoft 365 hebt geïmplementeerd, kunt u de Microsoft 365 met behulp van enkele van de onderstaande hulpprogramma's en technieken.</span><span class="sxs-lookup"><span data-stu-id="5599a-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="5599a-105">U wilt de officiële richtlijnen voor [service-](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) en continuïteitsrichtlijnen en onze best practices voor het gebruik van Microsoft 365 [op een traag netwerk begrijpen.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166)</span><span class="sxs-lookup"><span data-stu-id="5599a-105">You'll want to understand the official [Service Health and Continuity](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="5599a-106">U wilt ook de app voor beheerders [Microsoft 365](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) en onze Microsoft 365 voor Bedrijven [- Help voor beheerders .](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791)</span><span class="sxs-lookup"><span data-stu-id="5599a-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="5599a-107">Monitoring Microsoft 365 Connectivity</span><span class="sxs-lookup"><span data-stu-id="5599a-107">Monitoring Microsoft 365 Connectivity</span></span>

|<span data-ttu-id="5599a-108">Type controle</span><span class="sxs-lookup"><span data-stu-id="5599a-108">Type of monitoring</span></span> |<span data-ttu-id="5599a-109">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="5599a-109">Description</span></span> |
|:-----|:-----|
|<span data-ttu-id="5599a-110">**Op de hoogte worden gesteld van Microsoft 365 eindpunten**</span><span class="sxs-lookup"><span data-stu-id="5599a-110">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="5599a-111">Als u Microsoft 365 eindpunten [beheert,](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)wilt u meldingen ontvangen wanneer we nieuwe eindpunten publiceren, kunt u zich abonneren op onze RSS-feed met uw favoriete RSS-lezer.</span><span class="sxs-lookup"><span data-stu-id="5599a-111">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="5599a-112">U kunt zich als eerste [abonneren via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) of u kunt de [RSS-feedupdates](https://go.microsoft.com/fwlink/p/?LinkId=532417)per e-mail naar u sturen.</span><span class="sxs-lookup"><span data-stu-id="5599a-112">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="5599a-113">**Gebruik System Center om de Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5599a-113">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5599a-114">Als u Microsoft-System Center gebruikt, kunt u het System Center [Management Pack](https://www.microsoft.com/download/details.aspx?id=43708) voor Office 365 downloaden om de Microsoft 365 controleren.</span><span class="sxs-lookup"><span data-stu-id="5599a-114">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="5599a-115">Zie de handleiding voor beheerpakketbewerkingen voor meer gedetailleerde richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="5599a-115">For more detailed guidance, please see the management pack operations guide.</span></span> <br/> |
|<span data-ttu-id="5599a-116">**De status van Azure ExpressRoute controleren**</span><span class="sxs-lookup"><span data-stu-id="5599a-116">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="5599a-117">Als u verbinding maakt met Microsoft 365 met Behulp van Azure ExpressRoute voor Microsoft 365, wilt u ervoor zorgen dat u zowel het Microsoft 365 Service Health Dashboard als azure [Reducing troubleshooting time](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) with Azure Resource health gebruikt</span><span class="sxs-lookup"><span data-stu-id="5599a-117">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="5599a-118">**Azure AD-Verbinding maken gebruiken met AD FS**</span><span class="sxs-lookup"><span data-stu-id="5599a-118">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="5599a-119">Als u AD FS voor Één Sign-On gebruikt met Microsoft 365, wilt u Azure AD Verbinding maken Health gebruiken om uw [AD FS-infrastructuur](/azure/active-directory/hybrid/how-to-connect-health-adfs)te controleren.</span><span class="sxs-lookup"><span data-stu-id="5599a-119">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](/azure/active-directory/hybrid/how-to-connect-health-adfs).</span></span>  <br/> |
|<span data-ttu-id="5599a-120">**Programmatisch controleren Microsoft 365**</span><span class="sxs-lookup"><span data-stu-id="5599a-120">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="5599a-121">Raadpleeg onze richtlijnen voor de [Microsoft 365 Management API.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="5599a-121">Refer to our guidance on the [Microsoft 365 Management API](/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="5599a-122">Met deze korte koppeling kunt u teruggaan: [https://aka.ms/monitorconnectivity365]()</span><span class="sxs-lookup"><span data-stu-id="5599a-122">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365]()</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5599a-123">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5599a-123">Related topics</span></span>

[<span data-ttu-id="5599a-124">Microsoft 365 Enterprise services en toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="5599a-124">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="5599a-125">Uw organisatie voorbereiden op Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="5599a-125">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="5599a-126">Netwerkplanning en prestaties optimaliseren voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5599a-126">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="5599a-127">Microsoft 365 integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="5599a-127">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="5599a-128">Eindpunten Microsoft 365 beheren</span><span class="sxs-lookup"><span data-stu-id="5599a-128">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
