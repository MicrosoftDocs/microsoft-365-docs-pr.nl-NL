---
title: Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal
description: Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal
keywords: managed security service provider, mssp, configure, integration
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 97122decede91e8b4f059b3b66999ac12b300172
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164855"
---
# <a name="access-the-microsoft-defender-security-center-mssp-customer-portal"></a><span data-ttu-id="f6b07-104">Toegang tot Microsoft Defender-beveiligingscentrum MSSP-klantportal</span><span class="sxs-lookup"><span data-stu-id="f6b07-104">Access the Microsoft Defender Security Center MSSP customer portal</span></span>

<span data-ttu-id="f6b07-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f6b07-105">**Applies to:**</span></span>
- [<span data-ttu-id="f6b07-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f6b07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f6b07-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6b07-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="f6b07-108">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f6b07-108">**Applies to:**</span></span>

- [<span data-ttu-id="f6b07-109">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f6b07-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="f6b07-110">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f6b07-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6b07-111">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f6b07-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="f6b07-112">Deze reeks stappen zijn gericht op de MSSP.</span><span class="sxs-lookup"><span data-stu-id="f6b07-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="f6b07-113">MsSP-klanten hebben standaard toegang tot hun Microsoft Defender-beveiligingscentrum tenant via de volgende URL: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="f6b07-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="f6b07-114">MSSP's moeten echter een tenantspecifieke URL gebruiken in de volgende indeling: om toegang te krijgen  `https://securitycenter.windows.com?tid=customer_tenant_id` tot de MSSP-klantportal.</span><span class="sxs-lookup"><span data-stu-id="f6b07-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="f6b07-115">In het algemeen moeten MSSP's worden toegevoegd aan de Azure AD van de MSSP-klant die ze willen beheren.</span><span class="sxs-lookup"><span data-stu-id="f6b07-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="f6b07-116">Gebruik de volgende stappen om de MSSP-klant tenant-id te verkrijgen en vervolgens de id te gebruiken om toegang te krijgen tot de tenantspecifieke URL:</span><span class="sxs-lookup"><span data-stu-id="f6b07-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="f6b07-117">Meld u als MSSP aan bij Azure AD met uw referenties.</span><span class="sxs-lookup"><span data-stu-id="f6b07-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="f6b07-118">Schakel adreslijst over naar de tenant van de MSSP-klant.</span><span class="sxs-lookup"><span data-stu-id="f6b07-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="f6b07-119">Selecteer **Azure Active Directory > Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="f6b07-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="f6b07-120">U vindt de tenant-id in het veld Adreslijst-id.</span><span class="sxs-lookup"><span data-stu-id="f6b07-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="f6b07-121">Open de MSSP-klantportal door de waarde in de `customer_tenant_id` volgende URL te vervangen: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="f6b07-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="f6b07-122">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f6b07-122">Related topics</span></span>
- [<span data-ttu-id="f6b07-123">MSSP-toegang verlenen tot de portal</span><span class="sxs-lookup"><span data-stu-id="f6b07-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="f6b07-124">Waarschuwingsmeldingen configureren</span><span class="sxs-lookup"><span data-stu-id="f6b07-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="f6b07-125">Waarschuwingen ophalen van de klant-tenant</span><span class="sxs-lookup"><span data-stu-id="f6b07-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
