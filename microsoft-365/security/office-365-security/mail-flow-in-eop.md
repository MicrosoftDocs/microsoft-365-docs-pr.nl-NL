---
title: E-mailstroom in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Beheerder kan meer informatie krijgen over de opties voor het configureren van e-mailstroom en routering in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9636025796aee1ba2027edff38a16f131974134f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842492"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="3a69b-103">E-mailstroom in EOP</span><span class="sxs-lookup"><span data-stu-id="3a69b-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3a69b-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3a69b-104">**Applies to**</span></span>
- [<span data-ttu-id="3a69b-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3a69b-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3a69b-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3a69b-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3a69b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3a69b-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3a69b-108">In Microsoft 365 organisaties met Exchange Online-postvakken of zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken, worden alle berichten die naar uw organisatie worden verzonden, via EOP verzonden voordat uw werknemers deze zien.</span><span class="sxs-lookup"><span data-stu-id="3a69b-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="3a69b-109">U hebt opties voor het doorverzenden van berichten die via EOP worden verzonden voor verwerking voordat ze worden doorgeleid naar uw postvak IN van uw werknemer.</span><span class="sxs-lookup"><span data-stu-id="3a69b-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="3a69b-110">Werken met opties voor berichten en berichttoegang</span><span class="sxs-lookup"><span data-stu-id="3a69b-110">Working with messages and message access options</span></span>

<span data-ttu-id="3a69b-111">EOP biedt flexibiliteit in de manier waarop uw berichten worden gerouteerd.</span><span class="sxs-lookup"><span data-stu-id="3a69b-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="3a69b-112">In de volgende onderwerpen worden de stappen in het e-mailstroomproces uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="3a69b-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="3a69b-113">[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Randblokkering op basis van adreslijst waarmee u berichten voor ongeldige geadresseerden kunt weigeren in de perimeter van het servicenetwerk.</span><span class="sxs-lookup"><span data-stu-id="3a69b-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="3a69b-114">[Geaccepteerde domeinen weergeven of bewerken in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschrijft hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.</span><span class="sxs-lookup"><span data-stu-id="3a69b-114">[View or edit accepted domains in EOP](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="3a69b-115">Als u subdomeinen toevoegt aan uw organisatie, kan uw EOP-service u helpen deze ook te beheren.</span><span class="sxs-lookup"><span data-stu-id="3a69b-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="3a69b-116">Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3a69b-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="3a69b-117">[Als u de e-mailstroom configureert met](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) behulp van verbindingslijnen, worden verbindingslijnen gebruikt en ziet u hoe u deze kunt gebruiken om e-mailroutering aan te passen.</span><span class="sxs-lookup"><span data-stu-id="3a69b-117">[Configure mail flow using connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="3a69b-118">Scenario's zijn onder andere zorgen voor veilige communicatie met een partnerorganisatie en het instellen van een slimme host.</span><span class="sxs-lookup"><span data-stu-id="3a69b-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="3a69b-119">[Verbeterde filtering voor verbindingslijnen](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) beschrijft hoe u verbindingslijnen configureert als uw e-mail wordt doorgestuurd naar een service of apparaat vóór EOP.</span><span class="sxs-lookup"><span data-stu-id="3a69b-119">[Enhanced Filtering for Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="3a69b-120">In hybride omgevingen waar EOP on-premises Exchange-postvakken beschermt, moet u regels voor e-mailstroom (ook wel transportregels genoemd) configureren in on-premises Exchange om de EOP-spamfilterbeoordeling te vertalen, zodat de regel voor ongewenste e-mail het bericht kan verplaatsen naar de map Ongewenste e-mail.</span><span class="sxs-lookup"><span data-stu-id="3a69b-120">In hybrid environments where EOP protects on-premises Exchange mailboxes, you need to configure mail flow rules (also known as transport rules) in on-premises Exchange to translate the EOP spam filtering verdict so the junk email rule can move the message to the Junk Email folder.</span></span> <span data-ttu-id="3a69b-121">Zie [EOP configureren om in hybride omgevingen spam te bezorgen in de map Ongewenste e-mail](/exchange/standalone-eop/configure-eop-spam-protection-hybrid) voor meer informatie. </span><span class="sxs-lookup"><span data-stu-id="3a69b-121">For details, see [Configure EOP to deliver spam to the Junk Email folder in hybrid environments](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).</span></span> <span data-ttu-id="3a69b-122">Als u berichten niet naar de map Ongewenste e-mail van elke gebruiker wilt verplaatsen, kunt u een andere actie kiezen door uw antispambeleid te bewerken (ook wel bekend als beleid voor inhoudsfilters).</span><span class="sxs-lookup"><span data-stu-id="3a69b-122">If you don't  want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="3a69b-123">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3a69b-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="3a69b-124">E-mailstroom controleren</span><span class="sxs-lookup"><span data-stu-id="3a69b-124">Verify mail flow</span></span>

<span data-ttu-id="3a69b-125">Zie 'Hoe weet u dat deze taak heeft gewerkt?' als u wilt controleren of uw EOP-instelling, inclusief de configuratie van de connector, correct werkt.</span><span class="sxs-lookup"><span data-stu-id="3a69b-125">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="3a69b-126">sectie in [Uw EOP-service instellen.](/exchange/standalone-eop/set-up-your-eop-service)</span><span class="sxs-lookup"><span data-stu-id="3a69b-126">section in [Set up your EOP service](/exchange/standalone-eop/set-up-your-eop-service).</span></span>

<span data-ttu-id="3a69b-127">[Test de e-mailstroom door uw Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) te valideren, zodat u kunt testen of de e-mailstroom correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="3a69b-127">[Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
