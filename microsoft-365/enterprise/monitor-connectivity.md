---
title: Microsoft 365-connectiviteit bewaken
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
description: In dit artikel vindt u meer informatie over de hulpmiddelen en technieken die u kunt gebruiken om Microsoft 365-connectiviteit te controleren en te onderhouden.
ms.openlocfilehash: 7e62bcaae24f9e42fd0514c34c3d7dee764bc271
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688966"
---
# <a name="monitor-microsoft-365-connectivity"></a><span data-ttu-id="fb9d2-103">Microsoft 365-connectiviteit bewaken</span><span class="sxs-lookup"><span data-stu-id="fb9d2-103">Monitor Microsoft 365 connectivity</span></span>

<span data-ttu-id="fb9d2-104">Na de implementatie van Microsoft 365 kunt u Microsoft 365-verbindingen onderhouden met behulp van enkele van de hulpmiddelen en technieken.</span><span class="sxs-lookup"><span data-stu-id="fb9d2-104">Once you've deployed Microsoft 365, you can maintain Microsoft 365 connectivity using some of the tools and techniques below.</span></span> <span data-ttu-id="fb9d2-105">U wilt inzicht krijgen in de officiële richtlijnen [en de continuïteits](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) richtlijnen en onze [Best practices voor het gebruik van Microsoft 365 op een traag netwerk](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span><span class="sxs-lookup"><span data-stu-id="fb9d2-105">You'll want to understand the official [Service Health and Continuity](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) guidelines as well as our [Best practices for using Microsoft 365 on a slow network](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166).</span></span> <span data-ttu-id="fb9d2-106">U wilt ook de [app Microsoft 365 admin](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) oppakken en bladwijzer toevoegen aan onze [Microsoft 365 voor bedrijven-Help voor beheerders](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span><span class="sxs-lookup"><span data-stu-id="fb9d2-106">You'll also want to grab the [Microsoft 365 admin app](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/) and bookmark our [Microsoft 365 for business - Admin Help](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791).</span></span>
  
## <a name="monitoring-microsoft-365-connectivity"></a><span data-ttu-id="fb9d2-107">Microsoft 365-connectiviteit bewaken</span><span class="sxs-lookup"><span data-stu-id="fb9d2-107">Monitoring Microsoft 365 Connectivity</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="fb9d2-108">**Meldingen ontvangen over nieuwe Microsoft 365-eindpunten**</span><span class="sxs-lookup"><span data-stu-id="fb9d2-108">**Getting notified of new Microsoft 365 endpoints**</span></span> <br/> |<span data-ttu-id="fb9d2-109">Als u [Microsoft 365-eindpunten beheert](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), wilt u meldingen ontvangen wanneer nieuwe eindpunten worden gepubliceerd, u kunt zich abonneren op de RSS-feed met uw favoriete RSS-lezer.</span><span class="sxs-lookup"><span data-stu-id="fb9d2-109">If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader.</span></span> <span data-ttu-id="fb9d2-110">U kunt als volgt een [abonnement nemen via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) of u kunt [de RSS-feed e-mail laten bijwerken](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span><span class="sxs-lookup"><span data-stu-id="fb9d2-110">Here is how to [subscribe via Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) or you can [have the RSS feed updates emailed to you](https://go.microsoft.com/fwlink/p/?LinkId=532417).</span></span>  <br/> |
|<span data-ttu-id="fb9d2-111">**System Center gebruiken om Microsoft 365 te bewaken**</span><span class="sxs-lookup"><span data-stu-id="fb9d2-111">**Use System Center to Monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="fb9d2-112">Als u Microsoft System Center gebruikt, kunt u het [System Center Management Pack voor Office 365](https://www.microsoft.com/download/details.aspx?id=43708) downloaden om te beginnen met het bijhouden van microsoft 365 vandaag.</span><span class="sxs-lookup"><span data-stu-id="fb9d2-112">If you're using Microsoft System Center, you can download the [System Center Management Pack for Office 365](https://www.microsoft.com/download/details.aspx?id=43708) to begin monitoring Microsoft 365 today.</span></span> <span data-ttu-id="fb9d2-113">Voor uitgebreidere richtlijnen raadpleegt u de bewerkings handleiding van het Management Pack of dit blogbericht [Office365 monitoring met System Center Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span><span class="sxs-lookup"><span data-stu-id="fb9d2-113">For more detailed guidance, please see the management pack operations guide or this blog post [Office365 Monitoring using System Centre Operations Manager](https://blogs.msdn.com/b/mvpawardprogram/archive/2015/07/08/office365-monitoring-using-system-centre-operations-manager.aspx)</span></span> <br/> |
|<span data-ttu-id="fb9d2-114">**De status van Azure ExpressRoute bewaken**</span><span class="sxs-lookup"><span data-stu-id="fb9d2-114">**Monitoring the health of Azure ExpressRoute**</span></span> <br/> |<span data-ttu-id="fb9d2-115">Als u verbinding maakt met Microsoft 365 met behulp van Azure ExpressRoute voor Microsoft 365, moet u ervoor zorgen dat u zowel het dashboard van Microsoft 365 service status als het Azure voor de [periode van Azure reduceert met de status van Azure-bron](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span><span class="sxs-lookup"><span data-stu-id="fb9d2-115">If you are connecting to Microsoft 365 using Azure ExpressRoute for Microsoft 365, you'll want to ensure that you're using both the Microsoft 365 Service Health Dashboard as well as the Azure [Reducing troubleshooting time with Azure Resource health](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/)</span></span> <br/> |
|<span data-ttu-id="fb9d2-116">**Azure AD Connect Health gebruiken met AD FS**</span><span class="sxs-lookup"><span data-stu-id="fb9d2-116">**Using Azure AD Connect Health with AD FS**</span></span> <br/> |<span data-ttu-id="fb9d2-117">Als u AD FS gebruikt voor eenmalige aanmelding met Microsoft 365, moet u [Azure AD Connect Health gebruiken voor het bewaken van uw AD FS-infrastructuur](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span><span class="sxs-lookup"><span data-stu-id="fb9d2-117">If you're using AD FS for Single Sign-On with Microsoft 365, you'll want to begin [using Azure AD Connect Health to monitor your AD FS infrastructure](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect-health-adfs/).</span></span>  <br/> |
|<span data-ttu-id="fb9d2-118">**Microsoft 365 bewaken via programmacode**</span><span class="sxs-lookup"><span data-stu-id="fb9d2-118">**Programmatically monitor Microsoft 365**</span></span> <br/> |<span data-ttu-id="fb9d2-119">Raadpleeg onze richtlijnen op de [Microsoft 365-beheer-API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="fb9d2-119">Refer to our guidance on the [Microsoft 365 Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>  <br/> |

<span data-ttu-id="fb9d2-120">Met deze korte koppeling kunt u teruggaan: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span><span class="sxs-lookup"><span data-stu-id="fb9d2-120">Here's a short link you can use to come back: [https://aka.ms/monitorconnectivity365](https://aka.ms/monitorconnectivity365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fb9d2-121">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="fb9d2-121">Related topics</span></span>

[<span data-ttu-id="fb9d2-122">Microsoft 365 Enterprise-Services en-toepassingen configureren</span><span class="sxs-lookup"><span data-stu-id="fb9d2-122">Configure Microsoft 365 Enterprise services and applications</span></span>](configure-services-and-applications.md)
  
[<span data-ttu-id="fb9d2-123">Uw organisatie voorbereiden op Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="fb9d2-123">Get your organization ready for Microsoft 365 Enterprise</span></span>](get-your-organization-ready-for-office-365.md)
  
[<span data-ttu-id="fb9d2-124">Netwerk planning en prestaties optimaliseren voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fb9d2-124">Network planning and performance tuning for Microsoft 365</span></span>](network-planning-and-performance.md)
  
[<span data-ttu-id="fb9d2-125">Microsoft 365-integratie met on-premises omgevingen</span><span class="sxs-lookup"><span data-stu-id="fb9d2-125">Microsoft 365 integration with on-premises environments</span></span>](microsoft-365-integration.md)
  
[<span data-ttu-id="fb9d2-126">Microsoft 365-eindpunten beheren</span><span class="sxs-lookup"><span data-stu-id="fb9d2-126">Managing Microsoft 365 endpoints</span></span>](managing-office-365-endpoints.md)
