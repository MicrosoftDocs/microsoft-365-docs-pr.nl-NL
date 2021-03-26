---
title: Detecties naar uw SIEM-hulpprogramma's halen vanuit Microsoft Defender voor Eindpunt
description: Meer informatie over het gebruik van REST API en het configureren van ondersteunde hulpprogramma's voor beveiligingsgegevens en gebeurtenissenbeheer voor het ontvangen en trekken van detecties.
keywords: siem- en beveiligingsinformatie- en evenementenbeheerhulpmiddelen configureren, splunk, boogsight, aangepaste indicatoren, rest-api, waarschuwingsdefinities, indicatoren van compromissen
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
ms.openlocfilehash: 97a64c8537ff2a6f9948ed6ed056b8aa7379ce69
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222333"
---
# <a name="pull-detections-to-your-siem-tools"></a><span data-ttu-id="d216b-104">Detecties naar uw SIEM-hulpprogramma's trekken</span><span class="sxs-lookup"><span data-stu-id="d216b-104">Pull detections to your SIEM tools</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d216b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d216b-105">**Applies to:**</span></span>
- [<span data-ttu-id="d216b-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="d216b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d216b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d216b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="d216b-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="d216b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d216b-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="d216b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configuresiem-abovefoldlink) 

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a><span data-ttu-id="d216b-110">Detecties trekken met behulp van siem-hulpprogramma's (Security Information and Events Management)</span><span class="sxs-lookup"><span data-stu-id="d216b-110">Pull detections using security information and events management (SIEM) tools</span></span>

>[!NOTE]
>- <span data-ttu-id="d216b-111">[Microsoft Defender for Endpoint Alert](alerts.md) is samengesteld uit een of meer detecties.</span><span class="sxs-lookup"><span data-stu-id="d216b-111">[Microsoft Defender for Endpoint Alert](alerts.md) is composed from one or more detections.</span></span>
>- <span data-ttu-id="d216b-112">[Microsoft Defender voor eindpuntdetectie](api-portal-mapping.md) is samengesteld uit de verdachte gebeurtenis op het apparaat en de bijbehorende waarschuwingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="d216b-112">[Microsoft Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>
><span data-ttu-id="d216b-113">-De Microsoft Defender for Endpoint Alert API is de nieuwste API voor waarschuwingsverbruik en bevat een gedetailleerde lijst met verwante gegevens voor elke waarschuwing.</span><span class="sxs-lookup"><span data-stu-id="d216b-113">-The Microsoft Defender for Endpoint Alert API is the latest API for alert consumption and contain a detailed list of related evidence for each alert.</span></span> <span data-ttu-id="d216b-114">Zie Waarschuwingsmethoden en [-eigenschappen](alerts.md) en [Lijstwaarschuwingen](get-alerts.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d216b-114">For more information, see [Alert methods and properties](alerts.md) and [List alerts](get-alerts.md).</span></span>

<span data-ttu-id="d216b-115">Defender for Endpoint ondersteunt hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om detecties op te halen.</span><span class="sxs-lookup"><span data-stu-id="d216b-115">Defender for Endpoint supports security information and event management (SIEM) tools to pull detections.</span></span> <span data-ttu-id="d216b-116">In Defender for Endpoint worden waarschuwingen via een HTTPS-eindpunt dat wordt gehost in Azure, beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="d216b-116">Defender for Endpoint exposes alerts through an HTTPS endpoint hosted in Azure.</span></span> <span data-ttu-id="d216b-117">Het eindpunt kan worden geconfigureerd om detecties op te halen van uw enterprise tenant in Azure Active Directory (AAD) met behulp van het OAuth 2.0-verificatieprotocol voor een AAD-toepassing die de specifieke SIEM-connector vertegenwoordigt die in uw omgeving is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="d216b-117">The endpoint can be configured to pull detections from your enterprise tenant in Azure Active Directory (AAD) using the OAuth 2.0 authentication protocol for an AAD application that represents the specific SIEM connector installed in your environment.</span></span>

<span data-ttu-id="d216b-118">Defender voor Eindpunt ondersteunt momenteel de volgende specifieke SIEM-oplossingshulpmiddelen via een speciaal SIEM-integratiemodel:</span><span class="sxs-lookup"><span data-stu-id="d216b-118">Defender for Endpoint currently supports the following specific SIEM solution tools through a dedicated SIEM integration model:</span></span>

- <span data-ttu-id="d216b-119">IBM QRadar</span><span class="sxs-lookup"><span data-stu-id="d216b-119">IBM QRadar</span></span>
- <span data-ttu-id="d216b-120">MicroFocus ArcSight</span><span class="sxs-lookup"><span data-stu-id="d216b-120">Micro Focus ArcSight</span></span>

<span data-ttu-id="d216b-121">Andere SIEM-oplossingen (zoals Splunk, RSA NetWitness) worden ondersteund via een ander integratiemodel op basis van de nieuwe Alert API.</span><span class="sxs-lookup"><span data-stu-id="d216b-121">Other SIEM solutions (such as Splunk, RSA NetWitness) are supported through a different integration model based on the new Alert API.</span></span> <span data-ttu-id="d216b-122">Zie de pagina [Partnertoepassing](https://securitycenter.microsoft.com/interoperability/partners) voor meer informatie en selecteer de sectie Beveiligingsgegevens en analyse voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d216b-122">For more information, view the [Partner application](https://securitycenter.microsoft.com/interoperability/partners) page and select the Security Information and Analytics section for full details.</span></span>

<span data-ttu-id="d216b-123">Als u een van deze ondersteunde SIEM-hulpprogramma's wilt gebruiken, moet u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="d216b-123">To use either of these supported SIEM tools, you'll need to:</span></span>

- [<span data-ttu-id="d216b-124">SIEM-integratie inschakelen in Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="d216b-124">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- <span data-ttu-id="d216b-125">Het ondersteunde SIEM-hulpprogramma configureren:</span><span class="sxs-lookup"><span data-stu-id="d216b-125">Configure the supported SIEM tool:</span></span>
     - [<span data-ttu-id="d216b-126">MicroFocus ArcSight configureren om Defender voor eindpuntdetecties op te halen</span><span class="sxs-lookup"><span data-stu-id="d216b-126">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>](configure-arcsight.md)
     - <span data-ttu-id="d216b-127">CONFIGURE IBM QRadar to pull Defender for Endpoint detections (IBM [Knowledge Center)](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d216b-127">Configure IBM QRadar to pull Defender for Endpoint detections For more information, see [IBM Knowledge Center](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1).</span></span>

<span data-ttu-id="d216b-128">Zie [Defender voor eindpuntdetectievelden](api-portal-mapping.md)voor meer informatie over de lijst met velden die worden weergegeven in de Detectie-API.</span><span class="sxs-lookup"><span data-stu-id="d216b-128">For more information on the list of fields exposed in the Detection API, see [Defender for Endpoint Detection fields](api-portal-mapping.md).</span></span>
