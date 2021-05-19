---
title: Organisatie en levenscyclusbeheer plannen voor Microsoft 365 groepen en Microsoft Teams
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
recommendations: false
description: Lean about lifecycle governance options for collaboration tools in Microsoft 365
ms.openlocfilehash: 7d88618b75ef731bf38df029970efdc05f3eea5a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538817"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="b3482-103">Organisatie en levenscyclusbeheer plannen voor Microsoft 365 groepen en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3482-103">Plan organization and lifecycle governance for Microsoft 365 groups and Microsoft Teams</span></span>

<span data-ttu-id="b3482-104">Microsoft 365 groepen beschikt over een uitgebreide set hulpprogramma's voor het implementeren van de beheermogelijkheden die uw organisatie nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="b3482-104">Microsoft 365 groups has a rich set of tools to implement the governance capabilities your organization requires.</span></span> 

<span data-ttu-id="b3482-105">In de volgende sectie worden de mogelijkheden beschreven, aanbevolen procedures en worden richtlijnen gegeven voor het stellen van de juiste vragen om de vereisten voor beheer te bepalen en hoe u aan deze vereisten kunt voldoen.</span><span class="sxs-lookup"><span data-stu-id="b3482-105">The following section describes the capabilities, recommends best practices, and provides guidance to ask the right questions to determine the requirements for governance, and how to meet them.</span></span>

## <a name="control-who-can-create-microsoft-365-groups"></a><span data-ttu-id="b3482-106">Bepalen wie groepen Microsoft 365 maken</span><span class="sxs-lookup"><span data-stu-id="b3482-106">Control who can create Microsoft 365 groups</span></span>

<span data-ttu-id="b3482-107">Groepen kunnen door eindgebruikers worden gemaakt vanuit meerdere eindpunten, waaronder Outlook, SharePoint, Teams en andere omgevingen.</span><span class="sxs-lookup"><span data-stu-id="b3482-107">Groups can be created by end-users from multiple end-points including Outlook, SharePoint, Teams, and other environments.</span></span>

![afbeeldingssc](../media/04.png)

<span data-ttu-id="b3482-109">We raden selfservice ten zeerste aan om groepseigenaren in staat te stellen en gebruikers te helpen hun werk gemakkelijker te doen.</span><span class="sxs-lookup"><span data-stu-id="b3482-109">We highly recommend self-service to empower group owners and help users get their work done more easily.</span></span> <span data-ttu-id="b3482-110">Als u groeps- en teamcreatie beperkt, kan de productiviteit van gebruikers Microsoft 365 omdat voor veel services groepen moeten worden gemaakt om de service te laten functioneren.</span><span class="sxs-lookup"><span data-stu-id="b3482-110">Limiting group and team creation can slow users productivity because many Microsoft 365 services require that groups be created for the service to function.</span></span>

<span data-ttu-id="b3482-111">Overweeg de volgende beheeropties voor het maken van groepen:</span><span class="sxs-lookup"><span data-stu-id="b3482-111">Consider the following governance options for groups creation:</span></span>

- <span data-ttu-id="b3482-112">Als u groepsuitbreiding wilt beperken, gebruikt u [verloopbeleid](microsoft-365-groups-expiration-policy.md) voor groepen om groepen die niet worden gebruikt, automatisch te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b3482-112">To limit group sprawl, use [groups expiration policies](microsoft-365-groups-expiration-policy.md) to automatically delete groups that are not being used.</span></span>
- <span data-ttu-id="b3482-113">Beperk het maken van groepen tot leden van een [beveiligingsgroep met dynamisch](/azure/active-directory/users-groups-roles/groups-create-rule) lidmaatschap, bijvoorbeeld alle voltijdse werknemers.</span><span class="sxs-lookup"><span data-stu-id="b3482-113">Limit group creation to members of a [security groups with dynamic membership](/azure/active-directory/users-groups-roles/groups-create-rule) containing, for example, all full-time employees.</span></span>
- <span data-ttu-id="b3482-114">Beperk het maken van groepen tot een beveiligingsgroep en vereist dat gebruikers de training in het groepsbeleid van uw organisatie voltooien om lid te worden van de beveiligingsgroep.</span><span class="sxs-lookup"><span data-stu-id="b3482-114">Limit group creation to a security group and require users to complete training in your organization's group usage policies in order to become members of the security group.</span></span>

<span data-ttu-id="b3482-115">Als u wilt beperken wie groepen kan maken, zie Beheren wie groepen Microsoft 365 [maken](manage-creation-of-groups.md) voor informatie over het configureren van deze groepen.</span><span class="sxs-lookup"><span data-stu-id="b3482-115">If you want to limit who can create groups, see [Manage who can create Microsoft 365 groups](manage-creation-of-groups.md) for information on how to configure this.</span></span>

## <a name="group-delete-restore-and-archiving"></a><span data-ttu-id="b3482-116">Verwijderen, herstellen en archiveren groeperen</span><span class="sxs-lookup"><span data-stu-id="b3482-116">Group delete, restore, and archiving</span></span>

<span data-ttu-id="b3482-117">Wanneer een Microsoft 365 groep wordt verwijderd, wordt deze standaard 30 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="b3482-117">When a Microsoft 365 group is deleted, by default it's retained for 30 days.</span></span> <span data-ttu-id="b3482-118">Tijdens deze periode van 30 dagen kunt u de groep nog steeds herstellen.</span><span class="sxs-lookup"><span data-stu-id="b3482-118">This 30-day period is called "soft-delete" because you can still restore the group.</span></span> <span data-ttu-id="b3482-119">Na 30 dagen worden de groep en de bijbehorende inhoud definitief verwijderd en kunnen deze niet worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="b3482-119">After 30 days, the group and associated content is permanently deleted and cannot be restored.</span></span>

<span data-ttu-id="b3482-120">Als u bewaarbeleid hebt om chat, bestanden of e-mail te behouden, blijven deze items behouden nadat de groep is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b3482-120">If you have retention policies in place to retain chat, files, or mail, those items will be preserved after the group is deleted.</span></span> <span data-ttu-id="b3482-121">Zie [Meer informatie over bewaarbeleid](../compliance/retention.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3482-121">See [Learn about retention policies](../compliance/retention.md) for details.</span></span>

<span data-ttu-id="b3482-122">Zie [Groepen, teams](end-life-cycle-groups-teams-sites-yammer.md) en Yammer archiveren als u een groep wilt verwijderen, maar de inhoud wilt behouden van een of meer services die met de groep zijn verbonden.</span><span class="sxs-lookup"><span data-stu-id="b3482-122">If you want to delete a group but preserve the content from one or more of the group-connected services, see [Archive groups, teams, and Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information.</span></span>

## <a name="group-naming-policy"></a><span data-ttu-id="b3482-123">Groepsbeleid voor naamgeving</span><span class="sxs-lookup"><span data-stu-id="b3482-123">Group naming policy</span></span>

<span data-ttu-id="b3482-124">Met een naamgevingsbeleid voor groepen kunt u groepen op twee manieren besturen:</span><span class="sxs-lookup"><span data-stu-id="b3482-124">A groups naming policy can help you govern groups in two ways:</span></span>

- <span data-ttu-id="b3482-125">Een naamgevingsbeleid voor voorvoegsels/achtervoegsels kan worden gebruikt om vaste tekenreeksen of Azure AD-kenmerken af te dwingen aan het begin of einde van een groepsnaam en het bijbehorende e-mailadres.</span><span class="sxs-lookup"><span data-stu-id="b3482-125">A prefix/suffix naming policy can be used to enforce fixed strings or Azure AD attributes at the beginning or end of a group name and its associated email address.</span></span> <span data-ttu-id="b3482-126">Hierdoor kunt u ervoor zorgen dat bijvoorbeeld afdelingsnamen of regio's in groepsnamen worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="b3482-126">By doing this, you can ensure the inclusion of, for example, department names or regions in group names.</span></span>
- <span data-ttu-id="b3482-127">Een beleid voor geblokkeerde woorden kan ervoor zorgen dat bepaalde woorden, zoals de namen van leidinggevenden, niet worden gebruikt in groepsnamen.</span><span class="sxs-lookup"><span data-stu-id="b3482-127">A blocked words policy can ensure that certain words, such as the names of executives, are not used in group names.</span></span>

<span data-ttu-id="b3482-128">Naamgevingsbeleid wordt toegepast wanneer groepen worden gemaakt op een van de met de groep verbonden services.</span><span class="sxs-lookup"><span data-stu-id="b3482-128">Naming policies are applied when groups are created from any of the group-connected services.</span></span>

<span data-ttu-id="b3482-129">Als u besluit naamgevingsbeleid voor groepen te gebruiken, zie [Microsoft 365 Naamgevingsbeleid voor groepen](groups-naming-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b3482-129">If you decide to use naming policies for groups, see [Microsoft 365 Groups naming policy](groups-naming-policy.md).</span></span>

## <a name="group-expiration-policy"></a><span data-ttu-id="b3482-130">Verloopbeleid groep</span><span class="sxs-lookup"><span data-stu-id="b3482-130">Group expiration policy</span></span>

<span data-ttu-id="b3482-131">U kunt een verloopperiode opgeven en elke groep die het einde van die periode bereikt en niet wordt verlengd, wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b3482-131">You can specify an expiration period and any group that reaches the end of that period, and is not renewed, will be deleted.</span></span> <span data-ttu-id="b3482-132">De verloopperiode begint wanneer de groep wordt gemaakt of op de datum waarop de groep voor het laatst is verlengd.</span><span class="sxs-lookup"><span data-stu-id="b3482-132">The expiration period begins when the group is created, or on the date it was last renewed.</span></span>

<span data-ttu-id="b3482-133">Nadat u groepen hebt ingesteld op verlopen:</span><span class="sxs-lookup"><span data-stu-id="b3482-133">Once you set groups to expire:</span></span>
- <span data-ttu-id="b3482-134">Eigenaren van de groep krijgen een melding om de groep te verlengen zodra de vervaldatum nadert.</span><span class="sxs-lookup"><span data-stu-id="b3482-134">Owners of the group are notified to renew the group as the expiration nears.</span></span>
- <span data-ttu-id="b3482-135">Actieve groepen worden automatisch verlengd.</span><span class="sxs-lookup"><span data-stu-id="b3482-135">Active groups are renewed automatically.</span></span>
- <span data-ttu-id="b3482-136">Een groep die niet wordt verlengd, wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b3482-136">Any group that is not renewed is deleted.</span></span>
- <span data-ttu-id="b3482-137">Elke groep die wordt verwijderd, kan binnen 30 dagen worden hersteld door de groepseigenaars of de beheerder.</span><span class="sxs-lookup"><span data-stu-id="b3482-137">Any group that is deleted can be restored within 30 days by the group owners or the admin.</span></span>

<span data-ttu-id="b3482-138">Verloopbeleid is een goede manier om groepsuitbreiding te beperken door ervoor te zorgen dat groepen die niet meer worden gebruikt, worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b3482-138">Expiration policies are a good way to limit group sprawl by ensuring that groups that are no longer in use are deleted.</span></span> <span data-ttu-id="b3482-139">Als u een verloopbeleid voor groepen wilt maken, [bekijkt u Microsoft 365 Groep verloopbeleid](microsoft-365-groups-expiration-policy.md).</span><span class="sxs-lookup"><span data-stu-id="b3482-139">If you want to create a group expiration policy, see [Microsoft 365 Group Expiration Policy](microsoft-365-groups-expiration-policy.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b3482-140">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b3482-140">Related topics</span></span>

[<span data-ttu-id="b3482-141">Planning van samenwerkingsbeheer stap voor stap</span><span class="sxs-lookup"><span data-stu-id="b3482-141">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="b3482-142">Uw samenwerkingsbeheerplan maken</span><span class="sxs-lookup"><span data-stu-id="b3482-142">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="b3482-143">Een voormalige werknemer verwijderen en gegevens beveiligen</span><span class="sxs-lookup"><span data-stu-id="b3482-143">Remove a former employee and secure data</span></span>](/microsoft-365/admin/add-users/remove-former-employee)
