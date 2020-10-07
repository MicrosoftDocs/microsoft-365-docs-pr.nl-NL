---
title: Beheer organisatie en levenscyclusbeheer voor Microsoft 365-groepen en Microsoft teams
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Opties voor het beheer van de levenscyclus van functies voor samenwerking in Microsoft 365
ms.openlocfilehash: 706f1aaecf22c4088d4539c208fef68320c5e710
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377185"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="28b0a-103">Beheer organisatie en levenscyclusbeheer voor Microsoft 365-groepen en Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="28b0a-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="28b0a-104">Microsoft 365-groepen heeft een uitgebreide set hulpmiddelen voor de implementatie van de beheermogelijkheden die uw organisatie nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="28b0a-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="28b0a-105">In de volgende sectie worden de mogelijkheden beschreven, aanbevolen procedures aanbevolen en richtlijnen om de juiste vragen te stellen voor het bepalen van de vereisten voor beheer en hoe u deze kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="28b0a-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="28b0a-106">Bepalen wie Microsoft 365-groepen kan maken</span><span class="sxs-lookup"><span data-stu-id="28b0a-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="28b0a-107">Groepen kunnen worden gemaakt door eindgebruikers van meerdere eindpunten, waaronder Outlook, SharePoint, teams en andere omgevingen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![Beschrijving van de afbeelding](../media/04.png)

<span data-ttu-id="28b0a-109">We raden u ten zeerste aan om groepseigenaren te bieden en gebruikers te helpen gemakkelijker hun werk gedaan te krijgen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="28b0a-110">Wanneer u beperkingen voor groepen en teams beperkt, kunnen gebruikers de productiviteit van de gebruikers verminderen omdat voor veel services van Microsoft 365 de groepen die voor de service zijn gemaakt, moeten worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="28b0a-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="28b0a-111">Houd rekening met de volgende beheeropties voor het maken van groepen:</span><span class="sxs-lookup"><span data-stu-id="28b0a-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="28b0a-112">Als u de groeps sprawl wilt beperken, gebruikt u [beleidsregels voor groepen](microsoft-365-groups-expiration-policy.md) waarmee u groepen die niet worden gebruikt, automatisch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="28b0a-113">Maak het maken van groepen beperkt tot leden van een [beveiligingsgroep met dynamisch lidmaatschap met een dynamisch lidmaatschap](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) , bijvoorbeeld alle fulltime werknemers.</span><span class="sxs-lookup"><span data-stu-id="28b0a-113">Limit group creation to members of a [security groups with dynamic membership](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="28b0a-114">Maak het maken van groepen beperkt tot een beveiligingsgroep en vraag gebruikers training te voltooien in het beleid voor groepsgebruik van uw organisatie om lid te worden van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="28b0a-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="28b0a-115">Als u wilt beperken wie groepen kan maken, raadpleegt u [Manage wie Microsoft 365-groepen kunnen maken](manage-creation-of-groups.md) voor informatie over het configureren van dit.</span><span class="sxs-lookup"><span data-stu-id="28b0a-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="28b0a-116">Groep verwijderen, herstellen en archiveren</span><span class="sxs-lookup"><span data-stu-id="28b0a-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="28b0a-117">Wanneer een Microsoft 365-groep wordt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="28b0a-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="28b0a-118">Tijdens deze periode van 30 dagen kunt u de groep nog steeds herstellen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="28b0a-119">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="28b0a-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="28b0a-120">Als u wilt dat het bewaarbeleid voor chatberichten, bestanden of e-mail bewaard blijft, blijven deze items behouden nadat de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="28b0a-121">Zie [meer informatie over bewaarbeleid](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="28b0a-121">See [Learn about retention policies](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) for details.</span></span>

<span data-ttu-id="28b0a-122">Als u een groep wilt verwijderen, maar de inhoud van een of meer met de groep verbonden services wilt behouden, raadpleegt u [Archief groepen, teams en Yammer](end-life-cycle-groups-teams-sites-yammer.md) voor informatie.</span><span class="sxs-lookup"><span data-stu-id="28b0a-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="28b0a-123">Naam beleid voor groepen</span><span class="sxs-lookup"><span data-stu-id="28b0a-123">Group naming policy</span></span>

<span data-ttu-id="28b0a-124">Met behulp van een Groepsbeleid kunt u op twee manieren groepen beheren:</span><span class="sxs-lookup"><span data-stu-id="28b0a-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="28b0a-125">Met een naamgevingsbeleid voorvoegsels/achtervoegsels kunnen vaste tekenreeksen of Azure AD-kenmerken aan het begin of einde van de groepsnaam en het bijbehorende e-mailadres worden afgedwongen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="28b0a-126">Op deze manier kunt u ervoor zorgen dat de namen van de afdelings namen of regio's worden opgenomen in de namen van groepen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="28b0a-127">Met het beleid voor geblokkeerde woorden kunt u ervoor zorgen dat bepaalde woorden, zoals de namen van leidinggevenden, niet worden gebruikt in groepsnamen.</span><span class="sxs-lookup"><span data-stu-id="28b0a-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="28b0a-128">Het naamgevingsbeleid wordt toegepast wanneer groepen worden gemaakt op basis van een van de groepen verbonden services.</span><span class="sxs-lookup"><span data-stu-id="28b0a-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="28b0a-129">Als u het naamgevingsbeleid voor groepen wilt gebruiken, raadpleegt u [Microsoft 365 groepen naam beleid](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="28b0a-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="28b0a-130">Verloopbeleid voor groepen</span><span class="sxs-lookup"><span data-stu-id="28b0a-130">Group expiration policy</span></span>

<span data-ttu-id="28b0a-131">U kunt een vervalperiode en groepen opgeven waarmee het einde van de periode wordt bereikt, en de groep wordt niet vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="28b0a-132">De verloopperiode begint wanneer de groep is gemaakt, of op de datum waarop deze het laatst is vernieuwd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="28b0a-133">Wanneer u groepen hebt ingesteld op verloopt, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="28b0a-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="28b0a-134">Eigenaren van de groep ontvangen een melding voor het verlengen van de groep als het verlopen van de groep.</span><span class="sxs-lookup"><span data-stu-id="28b0a-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="28b0a-135">Actieve groepen worden automatisch verlengd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="28b0a-136">Alle groepen die niet worden vernieuwd, worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="28b0a-137">Een groep die wordt verwijderd, kan binnen 30 dagen worden teruggezet door de groepseigenaren of de beheerder.</span><span class="sxs-lookup"><span data-stu-id="28b0a-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="28b0a-138">Verloopbeleid is een goede manier om de groeps sprawl te beperken door te zorgen dat groepen die niet meer worden gebruikt, worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="28b0a-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="28b0a-139">Zie [verloopbeleid voor groepen Microsoft 365](microsoft-365-groups-expiration-policy.md)als u een verloopbeleid voor groepen wilt maken.</span><span class="sxs-lookup"><span data-stu-id="28b0a-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>
