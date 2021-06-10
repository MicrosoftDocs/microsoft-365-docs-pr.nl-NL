---
title: Vereisten & machtigingen - Threat and Vulnerability Management
description: Voordat u begint met Threat and Vulnerability Management, moet u de relevante configuraties en machtigingen hebben.
keywords: vereisten & vulnerability management voor bedreigingen Threat and Vulnerability Management machtigingen, vereisten voor Microsoft Defender voor endpoint-tvm-machtigingen, vulnerability management
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
ms.openlocfilehash: c0544665ea4e9b1ceafa645a2dcc96a224b0c242
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843948"
---
# <a name="prerequisites--permissions---threat-and-vulnerability-management"></a><span data-ttu-id="acfd6-104">Vereisten & machtigingen - Threat and Vulnerability Management</span><span class="sxs-lookup"><span data-stu-id="acfd6-104">Prerequisites & permissions - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="acfd6-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="acfd6-105">**Applies to:**</span></span>

- [<span data-ttu-id="acfd6-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="acfd6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="acfd6-107">Bedreiging en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="acfd6-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="acfd6-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="acfd6-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="acfd6-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="acfd6-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="acfd6-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="acfd6-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="acfd6-111">Zorg ervoor dat uw apparaten:</span><span class="sxs-lookup"><span data-stu-id="acfd6-111">Ensure that your devices:</span></span>

- <span data-ttu-id="acfd6-112">Zijn onboarded to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="acfd6-112">Are onboarded to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="acfd6-113">Ondersteunde [besturingssystemen en platforms uitvoeren](tvm-supported-os.md)</span><span class="sxs-lookup"><span data-stu-id="acfd6-113">Run [supported operating systems and platforms](tvm-supported-os.md)</span></span>
- <span data-ttu-id="acfd6-114">De volgende verplichte updates hebben geïnstalleerd en geïmplementeerd in uw netwerk om de detectiepercentages voor kwetsbaarheidsbeoordeling te verhogen:</span><span class="sxs-lookup"><span data-stu-id="acfd6-114">Have the following mandatory updates installed and deployed in your network to boost your vulnerability assessment detection rates:</span></span>

> <span data-ttu-id="acfd6-115">Release</span><span class="sxs-lookup"><span data-stu-id="acfd6-115">Release</span></span> | <span data-ttu-id="acfd6-116">KB-nummer en koppeling voor beveiligingsupdate</span><span class="sxs-lookup"><span data-stu-id="acfd6-116">Security update KB number and link</span></span>
> :---|:---
> <span data-ttu-id="acfd6-117">Windows 10 Versie 1709</span><span class="sxs-lookup"><span data-stu-id="acfd6-117">Windows 10 Version 1709</span></span> | <span data-ttu-id="acfd6-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) en [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span><span class="sxs-lookup"><span data-stu-id="acfd6-118">[KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) and [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)</span></span>
> <span data-ttu-id="acfd6-119">Windows 10 Versie 1803</span><span class="sxs-lookup"><span data-stu-id="acfd6-119">Windows 10 Version 1803</span></span> | <span data-ttu-id="acfd6-120">[KB4493464](https://support.microsoft.com/help/4493464) en [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span><span class="sxs-lookup"><span data-stu-id="acfd6-120">[KB4493464](https://support.microsoft.com/help/4493464) and [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)</span></span>
> <span data-ttu-id="acfd6-121">Windows 10 Versie 1809</span><span class="sxs-lookup"><span data-stu-id="acfd6-121">Windows 10 Version 1809</span></span> | [<span data-ttu-id="acfd6-122">KB 4516077</span><span class="sxs-lookup"><span data-stu-id="acfd6-122">KB 4516077</span></span>](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
> <span data-ttu-id="acfd6-123">Windows 10 Versie 1903</span><span class="sxs-lookup"><span data-stu-id="acfd6-123">Windows 10 Version 1903</span></span> | [<span data-ttu-id="acfd6-124">KB 4512941</span><span class="sxs-lookup"><span data-stu-id="acfd6-124">KB 4512941</span></span>](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)

- <span data-ttu-id="acfd6-125">Zijn onboarded [voor](/mem/intune/fundamentals/what-is-intune) Microsoft Intune en [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) om te helpen bij het herstellen van bedreigingen die door Threat and Vulnerability Management.</span><span class="sxs-lookup"><span data-stu-id="acfd6-125">Are onboarded to [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and  [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) to help remediate threats found by threat and vulnerability management.</span></span> <span data-ttu-id="acfd6-126">Als u Configuration Manager gebruikt, moet u de console bijwerken naar de nieuwste versie.</span><span class="sxs-lookup"><span data-stu-id="acfd6-126">If you're using Configuration Manager, update your console to the latest version.</span></span>
    - <span data-ttu-id="acfd6-127">**Opmerking:** Als de Intune-verbinding is ingeschakeld, krijgt u een optie om een Intune-beveiligingstaak te maken wanneer u een herstelaanvraag maakt.</span><span class="sxs-lookup"><span data-stu-id="acfd6-127">**Note**: If you have the Intune connection enabled, you get an option to create an Intune security task when creating a remediation request.</span></span> <span data-ttu-id="acfd6-128">Deze optie wordt niet weergegeven als de verbinding niet is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="acfd6-128">This option does not appear if the connection is not set.</span></span>
- <span data-ttu-id="acfd6-129">Minimaal één beveiligingsaanbeveling hebben die kan worden bekeken op de apparaatpagina</span><span class="sxs-lookup"><span data-stu-id="acfd6-129">Have at least one security recommendation that can be viewed in the device page</span></span>
- <span data-ttu-id="acfd6-130">Zijn gelabeld of gemarkeerd als co-beheerd</span><span class="sxs-lookup"><span data-stu-id="acfd6-130">Are tagged or marked as co-managed</span></span>

## <a name="relevant-permission-options"></a><span data-ttu-id="acfd6-131">Relevante machtigingsopties</span><span class="sxs-lookup"><span data-stu-id="acfd6-131">Relevant permission options</span></span>

1. <span data-ttu-id="acfd6-132">Meld u aan bij Microsoft Defender-beveiligingscentrum account met een beveiligingsbeheerder of globale beheerdersrol toegewezen.</span><span class="sxs-lookup"><span data-stu-id="acfd6-132">Log in to Microsoft Defender Security Center using account with a Security administrator or Global administrator role assigned.</span></span>
2. <span data-ttu-id="acfd6-133">Selecteer in het navigatiedeelvenster **Instellingen > Rollen.**</span><span class="sxs-lookup"><span data-stu-id="acfd6-133">In the navigation pane, select **Settings > Roles**.</span></span>

<span data-ttu-id="acfd6-134">Zie Rollen maken en beheren voor op rollen [gebaseerd toegangsbeheer](user-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="acfd6-134">For more information, see [Create and manage roles for role-based access control](user-roles.md)</span></span>

### <a name="view-data"></a><span data-ttu-id="acfd6-135">Gegevens weergeven</span><span class="sxs-lookup"><span data-stu-id="acfd6-135">View data</span></span>

- <span data-ttu-id="acfd6-136">**Beveiligingsbewerkingen:** alle gegevens over beveiligingsbewerkingen weergeven in de portal</span><span class="sxs-lookup"><span data-stu-id="acfd6-136">**Security operations** - View all security operations data in the portal</span></span>
- <span data-ttu-id="acfd6-137">**Bedreiging en vulnerability management** - Bekijk Threat and Vulnerability Management gegevens in de portal</span><span class="sxs-lookup"><span data-stu-id="acfd6-137">**Threat and vulnerability management** - View threat and vulnerability management data in the portal</span></span>

### <a name="active-remediation-actions"></a><span data-ttu-id="acfd6-138">Actieve herstelacties</span><span class="sxs-lookup"><span data-stu-id="acfd6-138">Active remediation actions</span></span>

- <span data-ttu-id="acfd6-139">**Beveiligingsbewerkingen:** actie ondernemen, in behandeling zijnde herstelacties goedkeuren of afwijzen, toegestane/geblokkeerde lijsten voor automatisering en indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="acfd6-139">**Security operations** - Take response actions, approve or dismiss pending remediation actions, manage allowed/blocked lists for automation and indicators</span></span>
- <span data-ttu-id="acfd6-140">**Bedreiging en vulnerability management - Afhandeling van uitzonderingen** - Nieuwe uitzonderingen maken en actieve uitzonderingen beheren</span><span class="sxs-lookup"><span data-stu-id="acfd6-140">**Threat and vulnerability management - Exception handling** - Create new exceptions and manage active exceptions</span></span>
- <span data-ttu-id="acfd6-141">**Bedreiging en vulnerability management -** Herstelafhandeling - Nieuwe herstelaanvragen indienen, tickets maken en bestaande herstelactiviteiten beheren</span><span class="sxs-lookup"><span data-stu-id="acfd6-141">**Threat and vulnerability management - Remediation handling** - Submit new remediation requests, create tickets, and manage existing remediation activities</span></span>

<span data-ttu-id="acfd6-142">Zie [RBAC-machtigingsopties voor meer informatie](user-roles.md#permission-options)</span><span class="sxs-lookup"><span data-stu-id="acfd6-142">For more information, see [RBAC permission options](user-roles.md#permission-options)</span></span>

## <a name="related-articles"></a><span data-ttu-id="acfd6-143">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="acfd6-143">Related articles</span></span>

- [<span data-ttu-id="acfd6-144">Overzicht van bedreigingen en vulnerability management</span><span class="sxs-lookup"><span data-stu-id="acfd6-144">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="acfd6-145">Ondersteunde besturingssystemen en -platforms</span><span class="sxs-lookup"><span data-stu-id="acfd6-145">Supported operating systems and platforms</span></span>](tvm-supported-os.md)
- [<span data-ttu-id="acfd6-146">Apparaatwaarde toewijzen</span><span class="sxs-lookup"><span data-stu-id="acfd6-146">Assign device value</span></span>](tvm-assign-device-value.md)
- [<span data-ttu-id="acfd6-147">Bedreiging en vulnerability management dashboard</span><span class="sxs-lookup"><span data-stu-id="acfd6-147">Threat and vulnerability management dashboard</span></span>](tvm-dashboard-insights.md)

