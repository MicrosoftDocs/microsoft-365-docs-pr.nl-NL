---
title: Ondersteuning voor beheerde beveiligingsservice configureren
description: De benodigde stappen ondernemen om de MSSP-integratie met microsoft Defender voor eindpunt te configureren
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
ms.openlocfilehash: 6786d423d20ec90c12d2ea712003acc787ed599d
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165247"
---
# <a name="configure-managed-security-service-provider-integration"></a><span data-ttu-id="8fa25-104">Integratie van beheerde beveiligingsproviders configureren</span><span class="sxs-lookup"><span data-stu-id="8fa25-104">Configure managed security service provider integration</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8fa25-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8fa25-105">**Applies to:**</span></span>
- [<span data-ttu-id="8fa25-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="8fa25-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8fa25-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8fa25-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="8fa25-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8fa25-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="8fa25-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8fa25-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8fa25-110">U moet de volgende configuratiestappen nemen om de MSSP-integratie (Managed Security Service Provider) in te stellen.</span><span class="sxs-lookup"><span data-stu-id="8fa25-110">You'll need to take the following configuration steps to enable the managed security service provider (MSSP) integration.</span></span>

>[!NOTE]
><span data-ttu-id="8fa25-111">In dit artikel worden de volgende termen gebruikt om onderscheid te maken tussen de serviceprovider en de service-consument:</span><span class="sxs-lookup"><span data-stu-id="8fa25-111">The following terms are used in this article to distinguish between the service provider and service consumer:</span></span>
> - <span data-ttu-id="8fa25-112">MSSP's: beveiligingsorganisaties die bieden om beveiligingsapparaten voor een organisatie te bewaken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="8fa25-112">MSSPs: Security organizations that offer to monitor and manage security devices for an organization.</span></span>
> - <span data-ttu-id="8fa25-113">MSSP-klanten: organisaties die zich bezighouden met de services van MSSP's.</span><span class="sxs-lookup"><span data-stu-id="8fa25-113">MSSP customers: Organizations that engage the services of MSSPs.</span></span>

<span data-ttu-id="8fa25-114">Met de integratie kunnen MSSP's de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="8fa25-114">The integration will allow MSSPs to take the following actions:</span></span>

- <span data-ttu-id="8fa25-115">Toegang krijgen tot de Microsoft Defender-beveiligingscentrumportal van MSSP-klanten</span><span class="sxs-lookup"><span data-stu-id="8fa25-115">Get access to MSSP customer's Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="8fa25-116">E-mailmeldingen ontvangen en</span><span class="sxs-lookup"><span data-stu-id="8fa25-116">Get email notifications, and</span></span> 
- <span data-ttu-id="8fa25-117">Waarschuwingen ophalen via hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM)</span><span class="sxs-lookup"><span data-stu-id="8fa25-117">Fetch alerts through security information and event management (SIEM) tools</span></span>

<span data-ttu-id="8fa25-118">Voordat MSSP's deze acties kunnen uitvoeren, moet de MSSP-klant toegang verlenen tot de Defender for Endpoint-tenant, zodat de MSSP toegang heeft tot de portal.</span><span class="sxs-lookup"><span data-stu-id="8fa25-118">Before MSSPs can take these actions, the MSSP customer will need to grant access to their Defender for Endpoint tenant so that the MSSP can access the portal.</span></span> 
 

<span data-ttu-id="8fa25-119">MsSP-klanten nemen meestal de eerste configuratiestappen om MSSP's toegang te verlenen tot hun Windows Defender Security Central-tenant.</span><span class="sxs-lookup"><span data-stu-id="8fa25-119">Typically, MSSP customers take the initial configuration steps to grant MSSPs access to their Windows Defender Security Central tenant.</span></span> <span data-ttu-id="8fa25-120">Nadat toegang is verleend, kunnen andere configuratiestappen worden uitgevoerd door de MSSP-klant of de MSSP.</span><span class="sxs-lookup"><span data-stu-id="8fa25-120">After access is granted, other configuration steps can be done by either the MSSP customer or the MSSP.</span></span>


<span data-ttu-id="8fa25-121">In het algemeen moeten de volgende configuratiestappen worden ondernomen:</span><span class="sxs-lookup"><span data-stu-id="8fa25-121">In general, the following configuration steps need to be taken:</span></span>


- <span data-ttu-id="8fa25-122">**MsSP-toegang verlenen tot Microsoft Defender-beveiligingscentrum**</span><span class="sxs-lookup"><span data-stu-id="8fa25-122">**Grant the MSSP access to Microsoft Defender Security Center**</span></span> <br>
<span data-ttu-id="8fa25-123">Deze actie moet worden uitgevoerd door de MSSP-klant.</span><span class="sxs-lookup"><span data-stu-id="8fa25-123">This action needs to be done by the MSSP customer.</span></span> <span data-ttu-id="8fa25-124">Het verleent de MSSP-toegang tot de Defender for Endpoint-tenant van de MSSP-klant.</span><span class="sxs-lookup"><span data-stu-id="8fa25-124">It grants the MSSP access to the MSSP customer's Defender for Endpoint tenant.</span></span>
 

- <span data-ttu-id="8fa25-125">**Waarschuwingsmeldingen configureren die zijn verzonden naar MSSP's**</span><span class="sxs-lookup"><span data-stu-id="8fa25-125">**Configure alert notifications sent to MSSPs**</span></span> <br>
<span data-ttu-id="8fa25-126">Deze actie kan worden ondernomen door de MSSP-klant of MSSP.</span><span class="sxs-lookup"><span data-stu-id="8fa25-126">This action can be taken by either the MSSP customer or MSSP.</span></span> <span data-ttu-id="8fa25-127">Op deze manier weten de MSSP's welke waarschuwingen ze moeten adresseringen voor de MSSP-klant.</span><span class="sxs-lookup"><span data-stu-id="8fa25-127">This lets the MSSPs know what alerts they need to address for the MSSP customer.</span></span>

- <span data-ttu-id="8fa25-128">**Waarschuwingen ophalen van de tenant van MSSP-klant in het SIEM-systeem**</span><span class="sxs-lookup"><span data-stu-id="8fa25-128">**Fetch alerts from MSSP customer's tenant into SIEM system**</span></span> <br> <span data-ttu-id="8fa25-129">Deze actie wordt ondernomen door de MSSP.</span><span class="sxs-lookup"><span data-stu-id="8fa25-129">This action is taken by the MSSP.</span></span> <span data-ttu-id="8fa25-130">Hiermee kunnen MSSP's waarschuwingen ophalen in SIEM-hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="8fa25-130">It allows MSSPs to fetch alerts in SIEM tools.</span></span>

- <span data-ttu-id="8fa25-131">**Waarschuwingen ophalen bij de tenant van MSSP-klanten met API's**</span><span class="sxs-lookup"><span data-stu-id="8fa25-131">**Fetch alerts from MSSP customer's tenant using APIs**</span></span> <br>
<span data-ttu-id="8fa25-132">Deze actie wordt ondernomen door de MSSP.</span><span class="sxs-lookup"><span data-stu-id="8fa25-132">This action is taken by the MSSP.</span></span> <span data-ttu-id="8fa25-133">Hiermee kunnen MSSP's waarschuwingen ophalen met API's.</span><span class="sxs-lookup"><span data-stu-id="8fa25-133">It allows MSSPs to fetch alerts using APIs.</span></span>

## <a name="multi-tenant-access-for-mssps"></a><span data-ttu-id="8fa25-134">Multiten tenanttoegang voor MSSP's</span><span class="sxs-lookup"><span data-stu-id="8fa25-134">Multi-tenant access for MSSPs</span></span>
<span data-ttu-id="8fa25-135">Zie [Multi-tenant access for Managed Security Service Providers (Multi-tenant access for Managed Security Service Providers)](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)voor informatie over het implementeren van een gedelegeerde toegang met meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="8fa25-135">For information on how to implement a multi-tenant delegated access, see [Multi-tenant access for Managed Security Service Providers](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440).</span></span>



## <a name="related-topics"></a><span data-ttu-id="8fa25-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8fa25-136">Related topics</span></span>
- [<span data-ttu-id="8fa25-137">MSSP-toegang verlenen tot de portal</span><span class="sxs-lookup"><span data-stu-id="8fa25-137">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="8fa25-138">Toegang tot de MSSP-klantportal</span><span class="sxs-lookup"><span data-stu-id="8fa25-138">Access the MSSP customer portal</span></span>](access-mssp-portal.md)
- [<span data-ttu-id="8fa25-139">Waarschuwingsmeldingen configureren</span><span class="sxs-lookup"><span data-stu-id="8fa25-139">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="8fa25-140">Waarschuwingen ophalen van klant tenant</span><span class="sxs-lookup"><span data-stu-id="8fa25-140">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)

