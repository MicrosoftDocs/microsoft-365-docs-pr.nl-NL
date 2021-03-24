---
title: Microsoft Defender voor endpoint-onderdrukkingsregels beheren
description: Mogelijk moet u voorkomen dat waarschuwingen in de portal worden weergegeven met behulp van onderdrukkingsregels. Meer informatie over het beheren van uw onderdrukkingsregels in Microsoft Defender ATP.
keywords: onderdrukken, regels, regelnaam, bereik, actie, waarschuwingen beheren, in- en uitschakelen
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
ms.openlocfilehash: 3b65b71cc90d8e79b5de02822a12d8a44cf6c0a6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058245"
---
# <a name="manage-suppression-rules"></a><span data-ttu-id="bd036-105">Onderdrukkende regels beheren</span><span class="sxs-lookup"><span data-stu-id="bd036-105">Manage suppression rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="bd036-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bd036-106">**Applies to:**</span></span>
- [<span data-ttu-id="bd036-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="bd036-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="bd036-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bd036-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="bd036-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="bd036-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="bd036-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="bd036-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="bd036-111">Er kunnen scenario's zijn waarin u waarschuwingen wilt onderdrukken die worden weergegeven in de portal.</span><span class="sxs-lookup"><span data-stu-id="bd036-111">There might be scenarios where you need to suppress alerts from appearing in the portal.</span></span> <span data-ttu-id="bd036-112">U kunt onderdrukkingsregels maken voor specifieke waarschuwingen die onschadelijk zijn, zoals bekende hulpmiddelen of processen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bd036-112">You can create suppression rules for specific alerts that are known to be innocuous such as known tools or processes in your organization.</span></span> <span data-ttu-id="bd036-113">Zie Waarschuwingen onderdrukken voor meer informatie over het onderdrukken [van waarschuwingen.](manage-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="bd036-113">For more information on how to suppress alerts, see [Suppress alerts](manage-alerts.md).</span></span>

<span data-ttu-id="bd036-114">U kunt een lijst met alle onderdrukkingsregels weergeven en deze op één plaats beheren.</span><span class="sxs-lookup"><span data-stu-id="bd036-114">You can view a list of all the suppression rules and manage them in one place.</span></span> <span data-ttu-id="bd036-115">U kunt ook een regel voor het onderdrukken van waarschuwingen in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="bd036-115">You can also turn an alert suppression rule on or off.</span></span>


1. <span data-ttu-id="bd036-116">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Waarschuwingsonderdrukking**.</span><span class="sxs-lookup"><span data-stu-id="bd036-116">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="bd036-117">De lijst met onderdrukkingsregels die gebruikers in uw organisatie hebben gemaakt, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bd036-117">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="bd036-118">Selecteer een regel door op het selectievakje naast de naam van de regel te klikken.</span><span class="sxs-lookup"><span data-stu-id="bd036-118">Select a rule by clicking on the check-box beside the rule name.</span></span>

3. <span data-ttu-id="bd036-119">Klik **op Regel in-,** **Regel bewerken of** Regel  **verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="bd036-119">Click **Turn rule on**, **Edit rule**, or  **Delete rule**.</span></span> <span data-ttu-id="bd036-120">Wanneer u wijzigingen aan een regel aan brengt, kunt u ervoor kiezen om waarschuwingen vrij te geven die al zijn onderdrukt, ongeacht of deze waarschuwingen voldoen aan de nieuwe criteria.</span><span class="sxs-lookup"><span data-stu-id="bd036-120">When making changes to a rule, you can choose to release alerts that it has already suppressed, regardless whether or not these alerts match the new criteria.</span></span> 


## <a name="view-details-of-a-suppression-rule"></a><span data-ttu-id="bd036-121">Details van een onderdrukkingsregel weergeven</span><span class="sxs-lookup"><span data-stu-id="bd036-121">View details of a suppression rule</span></span>

1. <span data-ttu-id="bd036-122">Selecteer in het navigatiedeelvenster **Instellingen**  >  **Waarschuwingsonderdrukking**.</span><span class="sxs-lookup"><span data-stu-id="bd036-122">In the navigation pane, select **Settings** > **Alert suppression**.</span></span> <span data-ttu-id="bd036-123">De lijst met onderdrukkingsregels die gebruikers in uw organisatie hebben gemaakt, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bd036-123">The list of suppression rules that users in your organization have created is displayed.</span></span>

2. <span data-ttu-id="bd036-124">Klik op een regelnaam.</span><span class="sxs-lookup"><span data-stu-id="bd036-124">Click on a rule name.</span></span> <span data-ttu-id="bd036-125">Details van de regel worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bd036-125">Details of the rule is displayed.</span></span> <span data-ttu-id="bd036-126">U ziet de regeldetails, zoals status, bereik, actie, aantal overeenkomende waarschuwingen, gemaakt op en datum waarop de regel is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="bd036-126">You'll see the rule details such as  status, scope, action, number of matching alerts, created by, and date when the rule was created.</span></span> <span data-ttu-id="bd036-127">U kunt ook gekoppelde waarschuwingen en de regelvoorwaarden bekijken.</span><span class="sxs-lookup"><span data-stu-id="bd036-127">You can also view associated alerts and the rule conditions.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bd036-128">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="bd036-128">Related topics</span></span>

- [<span data-ttu-id="bd036-129">Waarschuwingen beheren</span><span class="sxs-lookup"><span data-stu-id="bd036-129">Manage alerts</span></span>](manage-alerts.md)
