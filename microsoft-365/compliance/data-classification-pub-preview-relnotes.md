---
title: Opmerkingen bij de release van gegevensclassificatie
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Releasenotities voor gegevensclassificatie.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2021
ms.locfileid: "52162852"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="396a7-103">Opmerkingen bij de release van gegevensclassificatie</span><span class="sxs-lookup"><span data-stu-id="396a7-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="396a7-104">Exchange aantal postvakken</span><span class="sxs-lookup"><span data-stu-id="396a7-104">Exchange mailbox count</span></span>

<span data-ttu-id="396a7-105">U ziet een kleine knoptip wanneer u inzoomt op Exchange postvakken.</span><span class="sxs-lookup"><span data-stu-id="396a7-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="396a7-106">Dit betekent dat het statistische aantal dat wordt weergegeven voor het type gevoelige informatie, het gevoeligheidslabel en het bewaarlabel mogelijk niet exact overeenkomen met het aantal items dat u in het postvak vindt.</span><span class="sxs-lookup"><span data-stu-id="396a7-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="396a7-107">Dit komt doordat de inzooming in de map de liveweergave van inhoud op haalt, die is geclassificeerd, terwijl het samengevoegde aantal wordt berekend.</span><span class="sxs-lookup"><span data-stu-id="396a7-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="396a7-108">Weergave van versleutelde documenten</span><span class="sxs-lookup"><span data-stu-id="396a7-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="396a7-109">SharePoint, Exchange en OneDrive bestanden die zijn versleuteld, worden niet weergegeven in de inhoudsverkenner.</span><span class="sxs-lookup"><span data-stu-id="396a7-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="396a7-110">Dit is een gevoelig probleem dat een evenwicht vereist tussen de noodzaak om bestandsinhoud te zien in inhoudsverkenner en de noodzaak om de inhoud versleuteld te houden.</span><span class="sxs-lookup"><span data-stu-id="396a7-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="396a7-111">Met de machtigingen die zijn verleend  door Inhoudsverkenner-lijstviewer en inhoudsverkenner-rollengroepen, ziet u een lijstweergave van de bestanden, de bestandsmetagegevens en een koppeling die u kunt gebruiken om de inhoud te openen via de webclient. </span><span class="sxs-lookup"><span data-stu-id="396a7-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="396a7-112">Ondersteunde tekens in namen van bewaarlabels in SharePoint zoeken</span><span class="sxs-lookup"><span data-stu-id="396a7-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="396a7-113">SharePoint zoeken ondersteunt geen namen van bewaarlabels `-` met of `_` in deze.</span><span class="sxs-lookup"><span data-stu-id="396a7-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="396a7-114">Bijvoorbeeld, `Label-MIP` en `Label_MIP` worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="396a7-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="396a7-115">SharePoint zoeken ondersteunt deze tekens in namen van gevoeligheidslabels en gevoelige gegevenstypenamen.</span><span class="sxs-lookup"><span data-stu-id="396a7-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="396a7-116">OneDrive blijft in voorbeeld</span><span class="sxs-lookup"><span data-stu-id="396a7-116">OneDrive remains in preview</span></span>

<span data-ttu-id="396a7-117">Bedankt voor uw waardevolle feedback over OneDrive integratie tijdens ons preview-programma.</span><span class="sxs-lookup"><span data-stu-id="396a7-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="396a7-118">Wanneer we de specifieke gegevens doors uitvoeren, kan het zijn dat u inconsistente gegevens/stromen tegen komt.</span><span class="sxs-lookup"><span data-stu-id="396a7-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="396a7-119">We blijven de OneDrive voorbeeld weergeven totdat alle oplossingen zijn opgelost.</span><span class="sxs-lookup"><span data-stu-id="396a7-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="396a7-120">We waarderen uw voortdurende ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="396a7-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="396a7-121">Zie ook</span><span class="sxs-lookup"><span data-stu-id="396a7-121">See also</span></span>

- [<span data-ttu-id="396a7-122">Aan de slag met gegevensclassificatie (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="396a7-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="396a7-123">Labelactiviteit weergeven (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="396a7-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="396a7-124">Gelabelde inhoud weergeven (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="396a7-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="396a7-125">Meer informatie over vertrouwelijkheidslabels</span><span class="sxs-lookup"><span data-stu-id="396a7-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="396a7-126">Meer informatie over bewaarbeleid en bewaarlabels</span><span class="sxs-lookup"><span data-stu-id="396a7-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="396a7-127">Definities van entiteiten van het type Gevoelige informatie</span><span class="sxs-lookup"><span data-stu-id="396a7-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)