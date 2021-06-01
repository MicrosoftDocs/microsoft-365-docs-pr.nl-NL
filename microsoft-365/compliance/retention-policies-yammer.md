---
title: Meer informatie over retentie voor Yammer
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Lees meer over retentiebeleid dat van toepassing is op Yammer.
ms.openlocfilehash: 1b99d0915cfb159f821818fb1425d7191a011351
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2021
ms.locfileid: "52710704"
---
# <a name="learn-about-retention-for-yammer"></a><span data-ttu-id="0a700-103">Meer informatie over retentie voor Yammer</span><span class="sxs-lookup"><span data-stu-id="0a700-103">Learn about retention for Yammer</span></span>

><span data-ttu-id="0a700-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="0a700-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

> [!NOTE]
> <span data-ttu-id="0a700-105">Deze functie is nog niet beschikbaar in de preview-versie voor alle klanten.</span><span class="sxs-lookup"><span data-stu-id="0a700-105">This feature is in preview and not yet available for all customers.</span></span>

<span data-ttu-id="0a700-106">De informatie in dit artikel is een aanvulling op [Meer informatie over retentie](retention.md), omdat deze informatie specifiek is voor Yammer.</span><span class="sxs-lookup"><span data-stu-id="0a700-106">The information in this article supplements [Learn about retention](retention.md) because it has information that's specific to Yammer.</span></span>

<span data-ttu-id="0a700-107">Zie voor andere workloads:</span><span class="sxs-lookup"><span data-stu-id="0a700-107">For other workloads, see:</span></span>

- [<span data-ttu-id="0a700-108">Meer informatie over retentie voor SharePoint en OneDrive</span><span class="sxs-lookup"><span data-stu-id="0a700-108">Learn about retention for SharePoint and OneDrive</span></span>](retention-policies-sharepoint.md)
- [<span data-ttu-id="0a700-109">Meer informatie over retentie voor Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0a700-109">Learn about retention for Microsoft Teams</span></span>](retention-policies-teams.md)
- [<span data-ttu-id="0a700-110">Meer informatie over retentie voor Exchange</span><span class="sxs-lookup"><span data-stu-id="0a700-110">Learn about retention for Exchange</span></span>](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a><span data-ttu-id="0a700-111">Wat is inbegrepen voor retentie en verwijdering?</span><span class="sxs-lookup"><span data-stu-id="0a700-111">What's included for retention and deletion</span></span>

<span data-ttu-id="0a700-112">De volgende Yammer-items kunnen worden bewaard en verwijderd via bewaarbeleid voor Yammer: communityberichten en privéberichten.</span><span class="sxs-lookup"><span data-stu-id="0a700-112">The following Yammer items can be retained and deleted by using retention policies for Yammer: Community messages and private messages.</span></span>

<span data-ttu-id="0a700-113">Reacties van anderen in de vorm van emoticons worden niet opgenomen in deze berichten.</span><span class="sxs-lookup"><span data-stu-id="0a700-113">Reactions from others in the form of emoticons are not included in these messages.</span></span>

## <a name="how-retention-works-with-yammer"></a><span data-ttu-id="0a700-114">Hoe retentie werkt voor Yammer</span><span class="sxs-lookup"><span data-stu-id="0a700-114">How retention works with Yammer</span></span>

<span data-ttu-id="0a700-115">U kunt een bewaarbeleid gebruiken om communityberichten en privéberichten in Yammer te behouden en te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0a700-115">You can use a retention policy to retain and delete community messages and private messages in Yammer.</span></span> <span data-ttu-id="0a700-116">Privéberichten worden opgeslagen in een verborgen map in het postvak van elke gebruiker in het bericht en communityberichten worden opgeslagen in een soortgelijke verborgen map in het groepspostvak voor de community.</span><span class="sxs-lookup"><span data-stu-id="0a700-116">Private messages are stored in a hidden folder in the mailbox of each user included in the message, and community messages are stored in a similar hidden folder in the group mailbox for the community.</span></span>

<span data-ttu-id="0a700-117">Yammer-berichten worden niet beïnvloed door bewaarbeleid dat is geconfigureerd voor postvakken van gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="0a700-117">Yammer messages are not affected by retention policies that are configured for user or group mailboxes.</span></span> <span data-ttu-id="0a700-118">Hoewel Yammer-berichten zijn opgeslagen in Exchange, worden deze Yammer-gegevens alleen opgenomen door een bewaarbeleid dat is geconfigureerd voor de **Yammer-communityberichten** en **Yammer-gebruikersberichten** en locaties.</span><span class="sxs-lookup"><span data-stu-id="0a700-118">Even though Yammer messages are stored in Exchange, this Yammer data is included only by a retention policy that's configured for the **Yammer community messages** and **Yammer user messages** locations.</span></span>

> [!NOTE]
> <span data-ttu-id="0a700-119">Als een gebruiker is opgenomen in een actief bewaarbeleid waarin Yammer-gegevens worden bewaard en u een postvak verwijdert van een gebruiker die in dit beleid is opgenomen, wordt het postvak omgezet naar een [inactief postvak](inactive-mailboxes-in-office-365.md) om de gegevens in Teams te behouden.</span><span class="sxs-lookup"><span data-stu-id="0a700-119">If a user is included in an active retention policy that retains Yammer data and you a delete a mailbox of a user who is included in this policy, to retain the Yammer data, the mailbox is converted into an [inactive mailbox](inactive-mailboxes-in-office-365.md).</span></span> <span data-ttu-id="0a700-120">Als u deze Yammer-gegevens voor de gebruiker niet wilt bewaren, moet u het gebruikersaccount uitsluiten van het bewaarbeleid voordat u het postvak van de gebruiker verwijdert.</span><span class="sxs-lookup"><span data-stu-id="0a700-120">If you don't need to retain this Yammer data for the user, exclude the user account from the retention policy before you delete their mailbox.</span></span>

<span data-ttu-id="0a700-121">Nadat een bewaarbeleid voor chatberichten en kanaalberichten is geconfigureerd, controleert een timer voor de Exchange-service regelmatig items in de verborgen map waarin deze Yammer-berichten zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0a700-121">After a retention policy is configured for Yammer messages, a timer job from the Exchange service periodically evaluates items in the hidden folder where these Yammer messages are stored.</span></span> <span data-ttu-id="0a700-122">Het kan zeven dagen duren voordat de taak is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="0a700-122">The timer job takes up to seven days to run.</span></span> <span data-ttu-id="0a700-123">Wanneer de retentieperiode voor deze items is verstreken, worden ze verplaatst naar de map SubstrateHolds. Dit is een verborgen map in het postvak van elke gebruiker of groep waarin 'soft-verwijderde' items worden opgeslagen voordat ze definitief worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a700-123">When these items have expired their retention period, they are moved to the SubstrateHolds folder—a hidden folder that's in every user or group mailbox to store "soft-deleted" items before they are permanently deleted.</span></span>

<span data-ttu-id="0a700-124">Nadat een bewaarbeleid voor Yammer-berichten is geconfigureerd, zijn de paden die de inhoud aflegt afhankelijk van of het bewaarbeleid bestaat uit het behouden en vervolgens verwijderen of alleen uit het behouden of verwijderen ervan.</span><span class="sxs-lookup"><span data-stu-id="0a700-124">After a retention policy is configured for Yammer messages, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.</span></span>

<span data-ttu-id="0a700-125">Wanneer het bewaarbeleid bepaalt dat inhoud moet worden behouden en vervolgens moet worden verwijderd:</span><span class="sxs-lookup"><span data-stu-id="0a700-125">When the retention policy is to retain and then delete:</span></span>

![Diagram van bewaarstroom voor Yammer-berichten](../media/yammerretentionlifecycle.png)

<span data-ttu-id="0a700-127">Voor de twee paden in het diagram:</span><span class="sxs-lookup"><span data-stu-id="0a700-127">For the two paths in the diagram:</span></span>

1. <span data-ttu-id="0a700-128">**Als een Yammer-bericht wordt bewerkt of verwijderd** door de gebruiker tijdens de retentieperiode, wordt het oorspronkelijke bericht onmiddellijk gekopieerd (indien bewerkt) of verplaatst (indien verwijderd) naar de map SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0a700-128">**If a Yammer message is edited or deleted** by the user during the retention period, the original message is immediately copied (if edited) or moved (if deleted) to the SubstrateHolds folder.</span></span> <span data-ttu-id="0a700-129">Het bericht wordt daar opgeslagen totdat de bewaarperiode is verstreken, waarna het bericht onmiddellijk definitief wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a700-129">The message is stored there until the retention period expires and then the message is immediately permanently deleted.</span></span>

2. <span data-ttu-id="0a700-130">**Als een Yammer-bericht niet wordt verwijderd**, wordt het bericht (evenals huidige berichten na bewerking) naar de map SubstrateHolds verplaatst wanneer de retentieperiode is verstreken.</span><span class="sxs-lookup"><span data-stu-id="0a700-130">**If a Yammer message is not deleted** and for current messages after editing, the message is moved to the SubstrateHolds folder after the retention period expires.</span></span> <span data-ttu-id="0a700-131">Deze actie duurt maximaal zeven dagen vanaf de vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="0a700-131">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0a700-132">Wanneer het bericht zich in de map MessageFolds staat, wordt het onmiddellijk definitief verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a700-132">When the message is in the SubstrateHolds folder, it is then immediately permanently deleted.</span></span> 

> [!NOTE]
> <span data-ttu-id="0a700-133">Berichten in de map Verantwoordelijken zijn doorzoekbaar in eDiscovery-hulpprogramma's.</span><span class="sxs-lookup"><span data-stu-id="0a700-133">Messages in the SubstrateHolds folder are searchable by eDiscovery tools.</span></span> <span data-ttu-id="0a700-134">Berichten blijven doorzoekbaar met eDiscovery-hulpprogramma's totdat ze permanent worden verwijderd (in de map SubstrateHolds).</span><span class="sxs-lookup"><span data-stu-id="0a700-134">Until messages are permanently deleted (in the SubstrateHolds folder), they remain searchable by eDiscovery tools.</span></span>

<span data-ttu-id="0a700-135">Als het bewaarbeleid is ingesteld op alleen bewaren of alleen verwijderen, is de route die de inhoud aflegt een variatie van bewaren en verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0a700-135">When the retention policy is retain-only, or delete-only, the content's paths are variations of retain and delete.</span></span>

### <a name="content-paths-for-retain-only-retention-policy"></a><span data-ttu-id="0a700-136">Inhoudsroutes voor retentiebeleid voor alleen bewaren</span><span class="sxs-lookup"><span data-stu-id="0a700-136">Content paths for retain-only retention policy</span></span>

1. <span data-ttu-id="0a700-137">**Als een Yammer-bericht wordt bewerkt of verwijderd**: het oorspronkelijke bericht wordt onmiddellijk verplaatst naar de map SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0a700-137">**If a Yammer message is edited or deleted**: A copy of the original message is immediately created in the SubstrateHolds folder and retained there until the retention period expires.</span></span> <span data-ttu-id="0a700-138">Het bericht wordt onmiddellijk permanent verwijderd uit de map SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0a700-138">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0a700-139">**Als het Yammer-bericht niet wordt gewijzigd of verwijderd** tijdens de retentieperiode, en in geval van huidige berichten na bewerking tijdens de retentieperiode: er gebeurt niets voor en na de retentieperiode; het bericht blijft op de oorspronkelijke locatie staan.</span><span class="sxs-lookup"><span data-stu-id="0a700-139">**If the Yammer message is not modified or deleted** and for current messages after editing during the retention period: Nothing happens before and after the retention period; the message remains in its original location.</span></span>

### <a name="content-paths-for-delete-only-retention-policy"></a><span data-ttu-id="0a700-140">Inhoudsroutes voor retentiebeleid voor alleen verwijderen</span><span class="sxs-lookup"><span data-stu-id="0a700-140">Content paths for delete-only retention policy</span></span>

1. <span data-ttu-id="0a700-141">**Als een Yammer-bericht niet wordt verwijderd** tijdens de retentieperiode: het bericht wordt aan het einde van de retentieperiode naar de map SubstrateHolds verplaatst.</span><span class="sxs-lookup"><span data-stu-id="0a700-141">**If the Yammer message is not deleted** during the retention period: At the end of the retention period, the message is moved to the SubstrateHolds folder.</span></span> <span data-ttu-id="0a700-142">Deze actie duurt maximaal zeven dagen vanaf de vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="0a700-142">This action takes up to seven days from the expiry date.</span></span> <span data-ttu-id="0a700-143">Het bericht wordt onmiddellijk permanent verwijderd uit de map SubstrateHolds.</span><span class="sxs-lookup"><span data-stu-id="0a700-143">Then the message is immediately permanently deleted from the SubstrateHolds folder.</span></span>

2. <span data-ttu-id="0a700-144">**Als het Yammer-bericht tijdens de periode door de gebruiker** verwijderd, wordt het item onmiddellijk verplaatst naar de map SubstrateHolds, waar het onmiddellijk definitief wordt verwijderd.</span><span class="sxs-lookup"><span data-stu-id="0a700-144">**If the Yammer message is deleted by the user** during the period, the item is immediately moved to the SubstrateHolds folder where it is immediately permanently deleted.</span></span>


## <a name="messages-and-external-users"></a><span data-ttu-id="0a700-145">Berichtenn en externe gebruikers</span><span class="sxs-lookup"><span data-stu-id="0a700-145">Messages and external users</span></span>

<span data-ttu-id="0a700-146">Standaard is een bewaarbeleid voor gebruikersberichten van Yammer van toepassing op alle gebruikers in uw organisatie, maar niet op externe gebruikers.</span><span class="sxs-lookup"><span data-stu-id="0a700-146">By default, a retention policy for Yammer user messages applies to all users in your organization, but not external users.</span></span> <span data-ttu-id="0a700-147">U kunteen bewaarbeleid toepassen op externe gebruikers als u de functie **Gebruiker kiezen** gebruikt en hun account opgeeft.</span><span class="sxs-lookup"><span data-stu-id="0a700-147">You can apply a retention policy to external users if you use the **Choose user** and specify their account.</span></span> 

<span data-ttu-id="0a700-148">Op dit moment worden gastgebruikers van Azure B2B niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="0a700-148">At this time, Azure B2B guest users are not supported.</span></span>

## <a name="when-a-user-leaves-the-organization"></a><span data-ttu-id="0a700-149">Wanneer een gebruiker de organisatie verlaat</span><span class="sxs-lookup"><span data-stu-id="0a700-149">When a user leaves the organization</span></span> 

<span data-ttu-id="0a700-150">Als een gebruiker uw organisatie verlaat en zijn of haar Microsoft 365-account wordt verwijderd, worden hun Yammer-gebruikersberichten die moeten worden bewaard, opgeslagen in een inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="0a700-150">If a user leaves your organization and their Microsoft 365 account is deleted, their Yammer user messages that are subject to retention are stored in an inactive mailbox.</span></span> <span data-ttu-id="0a700-151">Deze berichten blijven onderworpen aan het bewaarbeleid dat op de gebruiker van toepassing was voordat het postvak inactief werd en de inhoud blijft beschikbaar voor een eDiscovery-zoekopdracht.</span><span class="sxs-lookup"><span data-stu-id="0a700-151">These messages remain subject to any retention policy that was placed on the user before their mailbox was made inactive, and the contents are available to an eDiscovery search.</span></span> <span data-ttu-id="0a700-152">Zie voor meer informatie [Inactive postvakken in Exchange Online](inactive-mailboxes-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0a700-152">For more information, see [Inactive mailboxes in Exchange Online](inactive-mailboxes-in-office-365.md).</span></span> 

<span data-ttu-id="0a700-153">Raadpleeg de [equivalente sectie](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) voor SharePoint en OneDrive als de gebruiker bestanden in Yammer heeft opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="0a700-153">If the user stored any files in Yammer, see the [equivalent section](retention-policies-sharepoint.md#when-a-user-leaves-the-organization) for SharePoint and OneDrive.</span></span>

## <a name="limitations"></a><span data-ttu-id="0a700-154">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="0a700-154">Limitations</span></span>

<span data-ttu-id="0a700-155">Bewaarbeleid van Yammer is momenteel preview en we werken voortdurend aan het optimaliseren van functionaliteit voor bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="0a700-155">Yammer retention policies are currently in preview and we're continuously working on optimizing retention functionality.</span></span> <span data-ttu-id="0a700-156">Houd u in de tussentijd rekening met de volgende beperking wanneer u bewaarbeleid gebruikt voor berichten en privéberichten in de Yammer-community:</span><span class="sxs-lookup"><span data-stu-id="0a700-156">In the meantime, be aware of the following limitation when you use retention for Yammer community messages and private messages:</span></span>

- <span data-ttu-id="0a700-157">Wanneer u **Gebruikers kiezen** selecteert voor de locatie **Yammer-gebruikersberichten** krijgt u mogelijk gasten en niet-postvakgebruikers te zien.</span><span class="sxs-lookup"><span data-stu-id="0a700-157">When you select **Choose users** for the **Yammer user messages** location, you might see guests and non-mailbox users.</span></span> <span data-ttu-id="0a700-158">Bewaarbeleid is niet ontworpen voor deze gebruikers, selecteer ze daarom ook niet.</span><span class="sxs-lookup"><span data-stu-id="0a700-158">Retention policies aren't designed for these users, so don't select them.</span></span>

## <a name="configuration-guidance"></a><span data-ttu-id="0a700-159">Configuratierichtlijnen</span><span class="sxs-lookup"><span data-stu-id="0a700-159">Configuration guidance</span></span>

<span data-ttu-id="0a700-160">Zie [Aan de slag met bewaarbeleid en retentielabels](get-started-with-retention.md) als het configureren van retentie in Microsoft 365 nieuw voor u is.</span><span class="sxs-lookup"><span data-stu-id="0a700-160">If you're new to configuring retention in Microsoft 365, see [Get started with retention policies and retention labels](get-started-with-retention.md).</span></span>

<span data-ttu-id="0a700-161">Zie [Bewaarbeleid maken en configureren](create-retention-policies.md) als u een bewaarbeleid voor Yammer wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="0a700-161">If you're ready to configure a retention policy for Yammer, see [Create and configure retention policies](create-retention-policies.md).</span></span>