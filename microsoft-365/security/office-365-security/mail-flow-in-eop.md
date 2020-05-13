---
title: E-mailstroom in EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Beheerder kan meer informatie krijgen over de opties voor het configureren van e-mailstroom en routering in Exchange Online Protection (EOP).
ms.openlocfilehash: cb2ae7370d50fe32802ad5c279cc2170eb35f581
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208328"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="c505a-103">E-mailstroom in EOP</span><span class="sxs-lookup"><span data-stu-id="c505a-103">Mail flow in EOP</span></span>

<span data-ttu-id="c505a-104">In Microsoft 365-organisaties met Exchange Online-postvakken of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken, gaan alle berichten die naar uw organisatie worden verzonden via EOP voordat uw werknemers ze zien.</span><span class="sxs-lookup"><span data-stu-id="c505a-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="c505a-105">U hebt opties voor het routeren van berichten die via EOP worden verzonden voor verwerking voordat ze worden doorgestuurd naar de postvakken van uw werknemer.</span><span class="sxs-lookup"><span data-stu-id="c505a-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="c505a-106">Werken met berichten en opties voor berichttoegang</span><span class="sxs-lookup"><span data-stu-id="c505a-106">Working with messages and message access options</span></span>

<span data-ttu-id="c505a-107">EOP biedt flexibiliteit in de manier waarop uw berichten worden doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="c505a-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="c505a-108">In de volgende onderwerpen worden stappen in het e-mailstroomproces uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="c505a-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="c505a-109">[Directory based edge blocking gebruiken om berichten die naar ongeldige ontvangers worden verzonden, af te wijzen](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Directory Based Edge Blocking waarmee u berichten weigeren voor ongeldige ontvangers in de perimeter van het servicenetwerk.</span><span class="sxs-lookup"><span data-stu-id="c505a-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="c505a-110">[Beheerde domeinen weergeven of bewerken in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) beschrijft hoe u domeinen beheert die zijn gekoppeld aan uw EOP-service.</span><span class="sxs-lookup"><span data-stu-id="c505a-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="c505a-111">Als u subdomeinen aan uw organisatie toevoegt, kan uw EOP-service u ook helpen deze te beheren.</span><span class="sxs-lookup"><span data-stu-id="c505a-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="c505a-112">Meer informatie over subdomeinen bij [E-mailstroom inschakelen voor subdomeinen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="c505a-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="c505a-113">[Configureer e-mailstroom met behulp van connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceert connectors en laat zien hoe u ze gebruiken om e-mailroutering aan te passen.</span><span class="sxs-lookup"><span data-stu-id="c505a-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="c505a-114">Scenario's omvatten het waarborgen van veilige communicatie met een partnerorganisatie en het opzetten van een slimme host.</span><span class="sxs-lookup"><span data-stu-id="c505a-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="c505a-115">[Met verbeterde filtering voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) wordt beschreven hoe u connectors configureert als uw e-mail vóór EOP naar een service of apparaat wordt doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="c505a-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="c505a-116">In zelfstandige EOP-organisaties moet u een paar configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorgestuurd naar de map met ongewenste e-mail van elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c505a-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="c505a-117">Deze worden beschreven in [Standalone EOP configureren om spam te leveren aan de map Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="c505a-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="c505a-118">Als u geen berichten naar de map met ongewenste e-mail van elke gebruiker wilt verplaatsen, u een andere actie kiezen door uw antispambeleid te bewerken (ook wel inhoudsfilterbeleid genoemd).</span><span class="sxs-lookup"><span data-stu-id="c505a-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="c505a-119">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c505a-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="c505a-120">E-mailstroom verifiëren</span><span class="sxs-lookup"><span data-stu-id="c505a-120">Verify mail flow</span></span>

<span data-ttu-id="c505a-121">Zie de 'Hoe weet je dat deze taak heeft gewerkt', inclusief je connectorconfiguratie, om te controleren of je eop-setup, inclusief je connectorconfiguratie, goed werkt.</span><span class="sxs-lookup"><span data-stu-id="c505a-121">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="c505a-122">sectie in [Uw EOP-service instellen](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="c505a-122">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="c505a-123">[Test de e-mailstroom door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) en geeft instructies voor het testen dat uw e-mailstroom correct is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="c505a-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
