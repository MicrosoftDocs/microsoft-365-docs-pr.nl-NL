---
title: Aangepaste detectieregels weergeven en beheren in Microsoft Defender ATP
ms.reviewer: ''
description: Informatie over het weergeven en beheren van aangepaste detectieregels
keywords: aangepaste detecties, weergeven, beheren, waarschuwingen, bewerken, uitvoeren op aanvraag, detectieregels, geavanceerd zoeken, jagen, query, antwoordacties, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f6a7fc4d4141b19f9c5129eea9b89943d07695b2
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165775"
---
# <a name="view-and-manage-custom-detection-rules"></a><span data-ttu-id="f0b6e-104">Aangepaste detectieregels weergeven en beheren</span><span class="sxs-lookup"><span data-stu-id="f0b6e-104">View and manage custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f0b6e-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f0b6e-105">**Applies to:**</span></span>
- [<span data-ttu-id="f0b6e-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="f0b6e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f0b6e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0b6e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f0b6e-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f0b6e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="f0b6e-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="f0b6e-110">Beheer uw bestaande [aangepaste detectieregels om](custom-detection-rules.md) ervoor te zorgen dat ze effectief bedreigingen vinden en acties ondernemen.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-110">Manage your existing [custom detection rules](custom-detection-rules.md) to ensure they are effectively finding threats and taking actions.</span></span> <span data-ttu-id="f0b6e-111">Ontdek hoe u de lijst met regels kunt bekijken, de vorige runs kunt controleren en de waarschuwingen kunt bekijken die ze hebben geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-111">Explore how to view the list of rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="f0b6e-112">U kunt ook een regel op aanvraag uitvoeren en deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-112">You can also run a rule on demand and modify it.</span></span>

## <a name="required-permissions"></a><span data-ttu-id="f0b6e-113">Vereiste machtigingen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-113">Required permissions</span></span>

<span data-ttu-id="f0b6e-114">Als u aangepaste detecties wilt maken of beheren, [moet uw](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) rol de machtiging **beveiligingsinstellingen** beheren hebben.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="view-existing-rules"></a><span data-ttu-id="f0b6e-115">Bestaande regels weergeven</span><span class="sxs-lookup"><span data-stu-id="f0b6e-115">View existing rules</span></span>

<span data-ttu-id="f0b6e-116">Als u alle bestaande aangepaste detectieregels wilt weergeven, gaat u naar **Instellingen**  >  **Aangepaste detecties.**</span><span class="sxs-lookup"><span data-stu-id="f0b6e-116">To view all existing custom detection rules, navigate to **Settings** > **Custom detections**.</span></span> <span data-ttu-id="f0b6e-117">Op de pagina vindt u alle regels met de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="f0b6e-117">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="f0b6e-118">**Laatst uitgevoerd:** wanneer een regel voor het laatst is uitgevoerd om te controleren op query's en waarschuwingen te genereren</span><span class="sxs-lookup"><span data-stu-id="f0b6e-118">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="f0b6e-119">**Status laatst uitgevoerd**: of een regel is uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="f0b6e-119">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="f0b6e-120">**Volgende run**: de volgende geplande run</span><span class="sxs-lookup"><span data-stu-id="f0b6e-120">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="f0b6e-121">**Status**, ongeacht of een regel is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="f0b6e-121">**Status**—whether a rule has been turned on or off</span></span>

## <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="f0b6e-122">Regeldetails weergeven, regel wijzigen en regel uitvoeren</span><span class="sxs-lookup"><span data-stu-id="f0b6e-122">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="f0b6e-123">Als u uitgebreide informatie over een aangepaste detectieregel wilt weergeven, selecteert u de naam van de regel in de lijst met regels in **Instellingen**  >  **Aangepaste detecties.**</span><span class="sxs-lookup"><span data-stu-id="f0b6e-123">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Settings** > **Custom detections**.</span></span> <span data-ttu-id="f0b6e-124">Op een pagina over de geselecteerde regel worden de volgende gegevens weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f0b6e-124">A page about the selected rule displays the following information:</span></span>

- <span data-ttu-id="f0b6e-125">Algemene informatie over de regel, inclusief de details van de waarschuwing, de status uitvoeren en het bereik</span><span class="sxs-lookup"><span data-stu-id="f0b6e-125">General information about the rule, including the details of the alert, run status, and scope</span></span>
- <span data-ttu-id="f0b6e-126">Lijst met geactiveerde waarschuwingen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-126">List of triggered alerts</span></span>
- <span data-ttu-id="f0b6e-127">Lijst met geactiveerde acties</span><span class="sxs-lookup"><span data-stu-id="f0b6e-127">List of triggered actions</span></span>

<span data-ttu-id="f0b6e-128">![Pagina Aangepaste detectieregel](images/atp-custom-detection-rule-details.png)</span><span class="sxs-lookup"><span data-stu-id="f0b6e-128">![Custom detection rule page](images/atp-custom-detection-rule-details.png)</span></span><br>
<span data-ttu-id="f0b6e-129">*Pagina Aangepaste detectieregel*</span><span class="sxs-lookup"><span data-stu-id="f0b6e-129">*Custom detection rule page*</span></span>

<span data-ttu-id="f0b6e-130">U kunt ook de volgende acties uitvoeren op de regel op deze pagina:</span><span class="sxs-lookup"><span data-stu-id="f0b6e-130">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="f0b6e-131">**Uitvoeren:** voer de regel onmiddellijk uit.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-131">**Run**—run the rule immediately.</span></span> <span data-ttu-id="f0b6e-132">Met deze actie wordt ook het interval voor de volgende run opnieuw ingesteld.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-132">This action also resets the interval for the next run.</span></span>
- <span data-ttu-id="f0b6e-133">**Bewerken**: wijzig de regel zonder de query te wijzigen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-133">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="f0b6e-134">**Query wijzigen:** bewerk de query in geavanceerde zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="f0b6e-134">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="f0b6e-135">**In- en uit-**  /  **Uitschakelen :de** regel inschakelen of stoppen met uitvoeren</span><span class="sxs-lookup"><span data-stu-id="f0b6e-135">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="f0b6e-136">**Verwijderen**: schakel de regel uit en verwijder deze</span><span class="sxs-lookup"><span data-stu-id="f0b6e-136">**Delete**—turn off the rule and remove it</span></span>

>[!TIP]
><span data-ttu-id="f0b6e-137">Als u snel informatie wilt weergeven en actie wilt ondernemen voor een item in een tabel, gebruikt u de selectiekolom [&#10003;] links van de tabel.</span><span class="sxs-lookup"><span data-stu-id="f0b6e-137">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0b6e-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-138">Related topics</span></span>
- [<span data-ttu-id="f0b6e-139">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="f0b6e-139">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="f0b6e-140">Detectieregels maken</span><span class="sxs-lookup"><span data-stu-id="f0b6e-140">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="f0b6e-141">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f0b6e-142">Waarschuwingen weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="f0b6e-142">View and organize alerts</span></span>](alerts-queue.md)
