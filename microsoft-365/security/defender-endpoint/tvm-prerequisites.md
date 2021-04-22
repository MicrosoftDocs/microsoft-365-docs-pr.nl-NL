---
title: Vereisten & machtigingen - bedreigings- en kwetsbaarheidsbeheer
description: Voordat u bedreigings- en kwetsbaarheidsbeheer gaat gebruiken, moet u de relevante configuraties en machtigingen hebben.
keywords: vereisten & vereisten voor beveiligingsprobleembeheer, vereisten voor bedreigings- en kwetsbaarheidsbeheer, vereisten voor Microsoft Defender voor endpoint-tvm-machtigingen, beveiligingsprobleembeheer
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0df348e3a5564720468d95d7b23578f9dcad9294
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935183"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="60ffe-104">Vereisten & machtigingen - bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="60ffe-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="60ffe-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="60ffe-105">**Applies to:**</span></span>

- [<span data-ttu-id="60ffe-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="60ffe-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="60ffe-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="60ffe-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="60ffe-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60ffe-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="60ffe-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="60ffe-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="60ffe-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="60ffe-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="60ffe-111">Zorg ervoor dat uw apparaten:</span><span class="sxs-lookup"><span data-stu-id="60ffe-111">Ensure that your devices:</span></span>

- <span data-ttu-id="60ffe-112">Zijn onboarded to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="60ffe-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="60ffe-113">Ondersteunde [besturingssystemen en platforms uitvoeren](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="60ffe-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="60ffe-114">De volgende verplichte updates hebben geïnstalleerd en geïmplementeerd in uw netwerk om de detectiepercentages voor kwetsbaarheidsbeoordeling te verhogen:</span><span class="sxs-lookup"><span data-stu-id="60ffe-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="60ffe-115">Release</span><span class="sxs-lookup"><span data-stu-id="60ffe-115">Release</span></span> | <span data-ttu-id="60ffe-116">KB-nummer en koppeling voor beveiligingsupdate</span><span class="sxs-lookup"><span data-stu-id="60ffe-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="60ffe-117">Windows 10 versie 1709</span><span class="sxs-lookup"><span data-stu-id="60ffe-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="60ffe-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) en [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="60ffe-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="60ffe-119">Windows 10 versie 1803</span><span class="sxs-lookup"><span data-stu-id="60ffe-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="60ffe-120">[KB4493464](https://support.microsoft.com/help/4493464) en [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="60ffe-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="60ffe-121">Windows 10 versie 1809</span><span class="sxs-lookup"><span data-stu-id="60ffe-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="60ffe-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="60ffe-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="60ffe-123">Windows 10 versie 1903</span><span class="sxs-lookup"><span data-stu-id="60ffe-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="60ffe-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="60ffe-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="60ffe-125">Zijn onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and Microsoft Endpoint Configuration Manager to  [help remediate](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) threats found by threat and vulnerability management.</span><span class="sxs-lookup"><span data-stu-id="60ffe-125">Are onboarded to [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="60ffe-126">Als u Configuration Manager gebruikt, moet u de console bijwerken naar de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="60ffe-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="60ffe-127">**Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt.</span><span class="sxs-lookup"><span data-stu-id="60ffe-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="60ffe-128">Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="60ffe-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="60ffe-129">Minimaal één beveiligingsaanbeveling hebben die kan worden bekeken op de apparaatpagina</span><span class="sxs-lookup"><span data-stu-id="60ffe-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="60ffe-130">Zijn gelabeld of gemarkeerd als co-beheerd</span><span class="sxs-lookup"><span data-stu-id="60ffe-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="60ffe-131">Relevante machtigingsopties</span><span class="sxs-lookup"><span data-stu-id="60ffe-131">Relevant permission options</span></span>

1. <span data-ttu-id="60ffe-132">Meld u aan bij het Microsoft Defender-beveiligingscentrum met behulp van een account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.</span><span class="sxs-lookup"><span data-stu-id="60ffe-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="60ffe-133">Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**</span><span class="sxs-lookup"><span data-stu-id="60ffe-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="60ffe-134">Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer](user-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="60ffe-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="60ffe-135">Gegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="60ffe-135">View data</span></span>

- <span data-ttu-id="60ffe-136">**Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal</span><span class="sxs-lookup"><span data-stu-id="60ffe-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="60ffe-137">**Bedreigings- en kwetsbaarheidsbeheer** : gegevens over bedreigings- en kwetsbaarheidsbeheer weergeven in de portal</span><span class="sxs-lookup"><span data-stu-id="60ffe-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="60ffe-138">Actieve herstelacties</span><span class="sxs-lookup"><span data-stu-id="60ffe-138">Active remediation actions</span></span>

- <span data-ttu-id="60ffe-139">**Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="60ffe-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="60ffe-140">**Bedreigings- en kwetsbaarheidsbeheer - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren</span><span class="sxs-lookup"><span data-stu-id="60ffe-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="60ffe-141">**Bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling** - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren</span><span class="sxs-lookup"><span data-stu-id="60ffe-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="60ffe-142">Zie [RBAC-machtigingsopties voor meer informatie](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="60ffe-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="60ffe-143">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="60ffe-143">Related articles</span></span>

- [<span data-ttu-id="60ffe-144">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="60ffe-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="60ffe-145">Ondersteunde besturingssystemen en -platforms</span><span class="sxs-lookup"><span data-stu-id="60ffe-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="60ffe-146">Apparaatwaarde toewijzen</span><span class="sxs-lookup"><span data-stu-id="60ffe-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="60ffe-147">Dashboard Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="60ffe-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

