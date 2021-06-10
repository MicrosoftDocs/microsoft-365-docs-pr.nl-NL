---
title: Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden
description: Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166051"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a><span data-ttu-id="9d766-104">Waarschuwingsmeldingen configureren die naar MSSP's worden verzonden</span><span class="sxs-lookup"><span data-stu-id="9d766-104">Configure alert notifications that are sent to MSSPs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9d766-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="9d766-105">**Applies to:**</span></span>
- [<span data-ttu-id="9d766-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="9d766-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d766-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d766-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="9d766-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="9d766-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9d766-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="9d766-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
><span data-ttu-id="9d766-110">Deze stap kan worden uitgevoerd door de MSSP-klant of MSSP.</span><span class="sxs-lookup"><span data-stu-id="9d766-110">This step can be done by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="9d766-111">MsSP's moeten de juiste machtigingen krijgen om dit namens de MSSP-klant te configureren.</span><span class="sxs-lookup"><span data-stu-id="9d766-111">MSSPs must be granted the appropriate permissions to configure this on behalf of the MSSP customer.</span></span>

<span data-ttu-id="9d766-112">Nadat toegang tot de portal is verleend, kunnen waarschuwingsmeldingen worden gemaakt, zodat e-mailberichten worden verzonden naar MSSP's wanneer waarschuwingen aan de tenant worden gemaakt en voorwaarden worden ingesteld.</span><span class="sxs-lookup"><span data-stu-id="9d766-112">After access the portal is granted, alert notification rules can to be created so that emails are sent to MSSPs when alerts associated with the tenant are created and set conditions are met.</span></span>

 
<span data-ttu-id="9d766-113">Zie Regels maken [voor waarschuwingsmeldingen voor meer informatie.](configure-email-notifications.md#create-rules-for-alert-notifications)</span><span class="sxs-lookup"><span data-stu-id="9d766-113">For more information, see [Create rules for alert notifications](configure-email-notifications.md#create-rules-for-alert-notifications).</span></span>
 

<span data-ttu-id="9d766-114">Deze selectievakjes moeten zijn ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="9d766-114">These check boxes must be checked:</span></span>
- <span data-ttu-id="9d766-115">**Naam van organisatie opnemen:** de klantnaam wordt toegevoegd aan e-mailmeldingen</span><span class="sxs-lookup"><span data-stu-id="9d766-115">**Include organization name** - The customer name will be added to email notifications</span></span>
- <span data-ttu-id="9d766-116">**Tenantspecifieke portalkoppeling opnemen:** url van waarschuwingskoppeling heeft tenantspecifieke parameter (tid=target_tenant_id) waarmee directe toegang tot de doel tenantportal wordt mogelijk</span><span class="sxs-lookup"><span data-stu-id="9d766-116">**Include tenant-specific portal link** - Alert link URL will have tenant specific parameter (tid=target_tenant_id) that allows direct access to target tenant portal</span></span>


## <a name="related-topics"></a><span data-ttu-id="9d766-117">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9d766-117">Related topics</span></span>
- [<span data-ttu-id="9d766-118">MSSP-toegang verlenen tot de portal</span><span class="sxs-lookup"><span data-stu-id="9d766-118">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="9d766-119">Toegang tot de MSSP-klantportal</span><span class="sxs-lookup"><span data-stu-id="9d766-119">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="9d766-120">Waarschuwingen ophalen van de klant-tenant</span><span class="sxs-lookup"><span data-stu-id="9d766-120">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
