---
title: App-beleid beheren
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Beheer uw app-beheerbeleid.
ms.openlocfilehash: 756402f86d6b65d48afb02c49b3e5bfc4e73fe3d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420206"
---
# <a name="manage-app-policies"></a><span data-ttu-id="58b85-103">App-beleid beheren</span><span class="sxs-lookup"><span data-stu-id="58b85-103">Manage app policies</span></span>

><span data-ttu-id="58b85-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="58b85-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="58b85-105">Om op de hoogte te blijven van de nieuwste apps die uw organisatie gebruikt, te reageren op nieuwe app-gebaseerde aanvallen en voor voortdurende wijzigingen in uw app-nalevingsbehoeften, moet u mogelijk uw app-beleid op de volgende manieren beheren:</span><span class="sxs-lookup"><span data-stu-id="58b85-105">To keep up with the latest apps your organization is using, respond to new app-based attacks, and for ongoing changes to your app compliance needs, you might need to manage your app policies in these ways:</span></span>

- <span data-ttu-id="58b85-106">Nieuw beleid maken dat is gericht op nieuwe apps</span><span class="sxs-lookup"><span data-stu-id="58b85-106">Create new policies targeted at new apps</span></span>
- <span data-ttu-id="58b85-107">De status van een bestaand beleid wijzigen (actief, inactief, auditmodus)</span><span class="sxs-lookup"><span data-stu-id="58b85-107">Change the status of an existing policy (active, inactive, audit mode)</span></span>
- <span data-ttu-id="58b85-108">De voorwaarden van een bestaand beleid wijzigen</span><span class="sxs-lookup"><span data-stu-id="58b85-108">Change the conditions of an existing policy</span></span>
- <span data-ttu-id="58b85-109">De acties van een bestaand beleid voor automatisch herstel van waarschuwingen wijzigen</span><span class="sxs-lookup"><span data-stu-id="58b85-109">Change the actions of an existing policy for auto-remediation of alerts</span></span>

<span data-ttu-id="58b85-110">Hier is een voorbeeld van een proces voor het beheren van een bestaand beleid:</span><span class="sxs-lookup"><span data-stu-id="58b85-110">Here's an example of a process for managing an existing policy:</span></span>

1. <span data-ttu-id="58b85-111">Bewerk het beleid:</span><span class="sxs-lookup"><span data-stu-id="58b85-111">Edit the policy:</span></span>

  - <span data-ttu-id="58b85-112">Wijzig de instellingen van het beleid.</span><span class="sxs-lookup"><span data-stu-id="58b85-112">Change the settings of the policy.</span></span>
  - <span data-ttu-id="58b85-113">Wijzig indien nodig voor testdoeleinden de status in **Auditmodus**.</span><span class="sxs-lookup"><span data-stu-id="58b85-113">If needed, change the status to **Audit mode** for testing.</span></span>

2. <span data-ttu-id="58b85-114">Controleer op verwacht gedrag, zoals gegenereerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="58b85-114">Check for expected behavior, such as alerts generated.</span></span>
1. <span data-ttu-id="58b85-115">Als het gedrag niet wordt verwacht, gaat u terug naar stap 1.</span><span class="sxs-lookup"><span data-stu-id="58b85-115">If the behavior is not expected, go back to step 1.</span></span>
1. <span data-ttu-id="58b85-116">Als het gedrag wordt verwacht, bewerkt u het beleid en wijzigt u de status in actief (indien nodig).</span><span class="sxs-lookup"><span data-stu-id="58b85-116">If the behavior is expected, edit the policy and change its status to active (if needed).</span></span>

![De werkstroom voor app-beleid beheren](../media/manage-app-protection-governance/mapg-manage-policy-process.png)

## <a name="editing-an-app-policy-configuration"></a><span data-ttu-id="58b85-118">De configuratie van een app-beleid bewerken</span><span class="sxs-lookup"><span data-stu-id="58b85-118">Editing an app policy configuration</span></span>

<span data-ttu-id="58b85-119">De configuratie van een bestaand app-beleid wijzigen:</span><span class="sxs-lookup"><span data-stu-id="58b85-119">To change the configuration of an existing app policy:</span></span>

- <span data-ttu-id="58b85-120">Selecteer het beleid in de beleidslijst en selecteer vervolgens **Bewerken** in het deelvenster App-beleid.</span><span class="sxs-lookup"><span data-stu-id="58b85-120">Select the policy in the policy list, and then select **Edit** on the app policy pane.</span></span>
- <span data-ttu-id="58b85-121">Selecteer het verticale beletselteken voor het beleid in de lijst en selecteer vervolgens **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="58b85-121">Select the vertical ellipses for the policy in the list, and then select **Edit**.</span></span>

<span data-ttu-id="58b85-122">Voor de pagina **Beleid bewerken** doorloopt u de pagina's en brengt u de gewenste wijzigingen aan:</span><span class="sxs-lookup"><span data-stu-id="58b85-122">For the **Edit policy** page, step through the pages and make the appropriate changes:</span></span>

- <span data-ttu-id="58b85-123">**Beschrijving**: wijzig de beschrijving om het doel van het beleid beter te begrijpen.</span><span class="sxs-lookup"><span data-stu-id="58b85-123">**Description**: Change the description to make it easier to understand the policy's purpose.</span></span>
- <span data-ttu-id="58b85-124">**Ernst**</span><span class="sxs-lookup"><span data-stu-id="58b85-124">**Severity**</span></span>
- <span data-ttu-id="58b85-125">**Beleidsinstellingen**: wijzig de set apps waarop het beleid van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="58b85-125">**Policy settings**: Change the set of apps to which the policy applies.</span></span> <span data-ttu-id="58b85-126">U kunt er ook voor kiezen om de bestaande voorwaarden te gebruiken of de voorwaarden te wijzigen</span><span class="sxs-lookup"><span data-stu-id="58b85-126">You can also choose to use the existing conditions or modify the conditions</span></span>
- <span data-ttu-id="58b85-127">**Acties**: wijzig de actie voor automatisch herstel voor waarschuwingen die door het beleid worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="58b85-127">**Actions**: Change the auto-remediation action for alerts generated by the policy.</span></span>
- <span data-ttu-id="58b85-128">**Status**: wijzig de beleidsstatus.</span><span class="sxs-lookup"><span data-stu-id="58b85-128">**Status**: Change the policy status.</span></span>

## <a name="deleting-an-app-policy"></a><span data-ttu-id="58b85-129">Een app-beleid verwijderen</span><span class="sxs-lookup"><span data-stu-id="58b85-129">Deleting an app policy</span></span>

<span data-ttu-id="58b85-130">Als u een app-beleid wilt verwijderen, kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="58b85-130">To delete an app policy, you can:</span></span>

- <span data-ttu-id="58b85-131">Selecteer het beleid in de beleidslijst en selecteer vervolgens **Verwijderen** in het deelvenster App-beleid.</span><span class="sxs-lookup"><span data-stu-id="58b85-131">Select the policy in the policy list, and then select **Delete** on the app policy pane.</span></span>
- <span data-ttu-id="58b85-132">Selecteer het verticale beletselteken voor het beleid in de lijst en selecteer vervolgens **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="58b85-132">Select the vertical ellipses for the policy in the list, and then select **Delete**.</span></span>

<span data-ttu-id="58b85-133">Een alternatief voor het verwijderen van een app-beleid is het wijzigen van de status in inactief.</span><span class="sxs-lookup"><span data-stu-id="58b85-133">An alternative to deleting an app policy is to change its status to inactive.</span></span> <span data-ttu-id="58b85-134">Zodra deze inactief is, worden er geen waarschuwingen gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="58b85-134">Once inactive, it will not generate alerts.</span></span> <span data-ttu-id="58b85-135">In plaats van een app-beleid te verwijderen voor een app met een specifieke set voorwaarden die nuttig zijn voor een toekomstig beleid, kunt u bijvoorbeeld de naam van het app-beleid wijzigen om het nut ervan aan te geven en de status ervan instellen op inactief.</span><span class="sxs-lookup"><span data-stu-id="58b85-135">For example, rather than deleting an app policy for an app with a specific set of conditions that are useful for a future policy, rename the app policy to indicate its usefulness and set its status to inactive.</span></span> <span data-ttu-id="58b85-136">U kunt later terugkeren naar het beleid en het wijzigen voor een vergelijkbare app en de status ervan instellen op auditmodus of inactief.</span><span class="sxs-lookup"><span data-stu-id="58b85-136">You can later return to the policy and modify it for a similar app and set its status to audit mode or inactive.</span></span>
