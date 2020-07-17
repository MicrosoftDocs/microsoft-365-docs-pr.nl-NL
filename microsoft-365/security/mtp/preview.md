---
title: Voorbeeldfuncties in Microsoft Threat Protection
description: Meer informatie over nieuwe functies in Microsoft 365-beveiliging
keywords: preview, nieuwe, m365 beveiliging, beveiliging, 365, mogelijkheden
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 45bc42e825c55ca228b13e8d308f9a1384301d07
ms.sourcegitcommit: 11218af1d792af297b4280ca5975d139d2bbe350
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2020
ms.locfileid: "45048265"
---
# <a name="microsoft-threat-protection-preview-features"></a><span data-ttu-id="e1201-104">Microsoft Threat Protection preview-functies</span><span class="sxs-lookup"><span data-stu-id="e1201-104">Microsoft Threat Protection preview features</span></span>

<span data-ttu-id="e1201-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e1201-105">**Applies to:**</span></span>
- <span data-ttu-id="e1201-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e1201-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="e1201-107">De Microsoft Threat Protection-service wordt voortdurend bijgewerkt met nieuwe functieverbeteringen en -mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="e1201-107">The Microsoft Threat Protection service is constantly being updated to include new feature enhancements and capabilities.</span></span>

<span data-ttu-id="e1201-108">Lees meer over nieuwe functies in de Microsoft Threat Protection preview-release en probeer als een van de eersten aankomende functies door de preview-ervaring in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="e1201-108">Learn about new features in the Microsoft Threat Protection preview release and be among the first to try upcoming features by turning on the preview experience.</span></span>

<span data-ttu-id="e1201-109">Zie Nieuwe mogelijkheden [in Microsoft Threat Protection](whats-new.md)voor meer informatie over nieuwe mogelijkheden die algemeen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="e1201-109">For more information on new capabilities that are generally available, see [What's new in Microsoft Threat Protection](whats-new.md).</span></span>

## <a name="turn-on-preview-features"></a><span data-ttu-id="e1201-110">Voorbeeldfuncties inschakelen</span><span class="sxs-lookup"><span data-stu-id="e1201-110">Turn on preview features</span></span>
<span data-ttu-id="e1201-111">Je hebt toegang tot aankomende functies waarop je feedback geven om de algehele ervaring te verbeteren voordat functies algemeen beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="e1201-111">You'll have access to upcoming features which you can provide feedback on to help improve the overall experience before features are generally available.</span></span>

<span data-ttu-id="e1201-112">Schakel de instelling voor voorbeeldervaring in om als een van de eersten aankomende functies uit te proberen.</span><span class="sxs-lookup"><span data-stu-id="e1201-112">Turn on the preview experience setting to be among the first to try upcoming features.</span></span>

1. <span data-ttu-id="e1201-113">Selecteer **Instellingen**in het navigatiedeelvenster .</span><span class="sxs-lookup"><span data-stu-id="e1201-113">In the navigation pane, select **Settings**.</span></span>

2. <span data-ttu-id="e1201-114">Selecteer **Microsoft-bedreigingsbeveiliging**.</span><span class="sxs-lookup"><span data-stu-id="e1201-114">Select **Microsoft Threat Protection**.</span></span>


3. <span data-ttu-id="e1201-115">Voorbeeldfuncties **Preview features**  >  **selecteren Voorbeeldfuncties inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="e1201-115">Select **Preview features** > **Turn on preview features**.</span></span> 

3. <span data-ttu-id="e1201-116">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="e1201-116">Select **Save**.</span></span>

<span data-ttu-id="e1201-117">U weet dat u voorbeeldfuncties hebt ingeschakeld wanneer u ziet dat het selectievakje **Voorbeeldfuncties inschakelen** is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1201-117">You'll know you have preview features turned on when you see that the **Turn on preview features** check box is selected.</span></span> 

## <a name="preview-features"></a><span data-ttu-id="e1201-118">Voorbeeldfuncties</span><span class="sxs-lookup"><span data-stu-id="e1201-118">Preview features</span></span>
<span data-ttu-id="e1201-119">De volgende functies en verbeteringen zijn momenteel beschikbaar in preview:</span><span class="sxs-lookup"><span data-stu-id="e1201-119">The following features and enhancements are currently available on preview:</span></span>

- <span data-ttu-id="e1201-120">**[In-portal schema referentie](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — informatie over schematabellen direct beschikbaar in het beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="e1201-120">**[In-portal schema reference](advanced-hunting-schema-tables.md#get-schema-information-in-the-security-center)** — information about schema tables available directly in the security center.</span></span> <span data-ttu-id="e1201-121">Naast tabel- en kolombeschrijvingen bevat deze verwijzing informatie over ondersteunde gebeurtenistypen `ActionType` (waarden) en voorbeeldquery's.</span><span class="sxs-lookup"><span data-stu-id="e1201-121">In addition to table and column descriptions, this reference provides information about supported event types (`ActionType` values) and sample queries.</span></span>  

- <span data-ttu-id="e1201-122">**[Identiteits- en apptabellen](advanced-hunting-schema-tables.md)** — krijg inzicht in verificatiegebeurtenissen, Active Directory-query's en app-gerelateerde activiteiten met de [tabellen IdentityLogonEvents,](advanced-hunting-identitylogonevents-table.md) [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)en [AppFileEvents](advanced-hunting-appfileevents-table.md) in het geavanceerde jachtschema.</span><span class="sxs-lookup"><span data-stu-id="e1201-122">**[Identity and app tables](advanced-hunting-schema-tables.md)** — get visibility into authentication events, Active Directory queries, and app-related activity with the [IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md), [IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md), and [AppFileEvents](advanced-hunting-appfileevents-table.md) tables in the advanced hunting schema.</span></span>

- <span data-ttu-id="e1201-123">**[Ga op jacht](advanced-hunting-go-hunt.md)** — draai snel van het onderzoeken van een incident tot het inspecteren van een specifieke gebeurtenis, een gebruiker, een apparaat of andere entiteitstypen met behulp van geavanceerde [jachtmogelijkheden](advanced-hunting-overview.md) op basis van query's.</span><span class="sxs-lookup"><span data-stu-id="e1201-123">**[Go hunt](advanced-hunting-go-hunt.md)** — quickly pivot from investigating an incident to inspecting a specific event, a user, a device, or other entity types using query-based [advanced hunting](advanced-hunting-overview.md) capabilities.</span></span>

- <span data-ttu-id="e1201-124">**[FileProfile() functie](advanced-hunting-fileprofile-function.md)** — gebruik in uw geavanceerde jachtquery's om uitgebreide bestandsinformatie op te nemen. [advanced hunting](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1201-124">**[FileProfile() function](advanced-hunting-fileprofile-function.md)** — use in your [advanced hunting](advanced-hunting-overview.md) queries to incorporate comprehensive file information.</span></span>
