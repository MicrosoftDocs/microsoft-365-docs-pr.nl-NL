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
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
ms.custom:
- seo-marvel-apr2020
description: Beheerder biedt informatie over de opties voor het configureren van e-mail stroom en routering in Exchange Online Protection (EOP).
ms.openlocfilehash: e1c821e3de8dd7dd18c192522bd18fd32a395dca
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200701"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="ea152-103">E-mailstroom in EOP</span><span class="sxs-lookup"><span data-stu-id="ea152-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="ea152-104">In Microsoft 365-organisaties met postvakken van Exchange Online of zelfstandige Exchange Online Protection-organisaties (EOP) zonder Exchange Online-postvakken worden alle berichten die naar uw organisatie worden verzonden, doorgestuurd naar EOP voordat ze de werknemers zien.</span><span class="sxs-lookup"><span data-stu-id="ea152-104">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="ea152-105">U hebt opties voor het doorsturen van berichten die door EOP worden verwerkt voordat ze worden doorgestuurd naar de postvakken van uw werknemers.</span><span class="sxs-lookup"><span data-stu-id="ea152-105">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="ea152-106">Werken met berichten en opties voor het openen van berichten</span><span class="sxs-lookup"><span data-stu-id="ea152-106">Working with messages and message access options</span></span>

<span data-ttu-id="ea152-107">EOP biedt flexibiliteit bij het routeren van uw berichten.</span><span class="sxs-lookup"><span data-stu-id="ea152-107">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="ea152-108">In de volgende onderwerpen wordt stapsgewijs uitgelegd hoe u de e-mail stroom procedure uitvoert.</span><span class="sxs-lookup"><span data-stu-id="ea152-108">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="ea152-109">[Op mappen gebaseerde rand blokkeren om berichten die naar ongeldige geadresseerden zijn verzonden, af te](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) wijzen Een beschrijving van de functie voor het blokkeren van basis op basis van een rand die u kunt gebruiken om berichten voor ongeldige geadresseerden op de netwerk blokkering te weigeren</span><span class="sxs-lookup"><span data-stu-id="ea152-109">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="ea152-110">[Beheerde domeinen weergeven of bewerken in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) wordt beschreven hoe u domeinen kunt beheren die aan uw EOP-service zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ea152-110">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="ea152-111">Als u subdomeinen toevoegt aan uw organisatie, kunt u deze ook door de EOP-service beheren.</span><span class="sxs-lookup"><span data-stu-id="ea152-111">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="ea152-112">Meer informatie over subdomeinen vindt u [in e-mail stroom inschakelen voor subdomeinen in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="ea152-112">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="ea152-113">[E-mail stroom configureren met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduceert verbindingslijnen en laat zien hoe u deze kunt gebruiken om e-mail routering aan te passen.</span><span class="sxs-lookup"><span data-stu-id="ea152-113">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="ea152-114">Scenario's zijn voor veilig communiceren met een partnerorganisatie en het instellen van een Smart host.</span><span class="sxs-lookup"><span data-stu-id="ea152-114">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="ea152-115">[Uitgebreid filteren op connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) hierin wordt beschreven hoe u connectors kunt configureren als uw e-mail wordt gerouteerd naar een service of apparaat vóór EOP.</span><span class="sxs-lookup"><span data-stu-id="ea152-115">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="ea152-116">In zelfstandige EOP-organisaties moet u een paar configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt gerouteerd naar de map Ongewenste e-mail in elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ea152-116">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="ea152-117">Deze informatie wordt uitvoerig beschreven in [zelfstandige EOP configureren voor spam op de map Ongewenste e-mail in hybride omgevingen](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span><span class="sxs-lookup"><span data-stu-id="ea152-117">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="ea152-118">Als u berichten niet naar de map Ongewenste e-mail wilt verplaatsen naar de map Ongewenste e-mail, kunt u een andere actie kiezen door uw Antispambeleid te bewerken (ook wel inhouds filter beleid genoemd).</span><span class="sxs-lookup"><span data-stu-id="ea152-118">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="ea152-119">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ea152-119">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="ea152-120">De e-mail stroom controleren</span><span class="sxs-lookup"><span data-stu-id="ea152-120">Verify mail flow</span></span>

<span data-ttu-id="ea152-121">Als u wilt controleren of de EOP-instellingen, waaronder de connectorconfiguratie, goed werken, raadpleegt u de sectie Hoe weet u dat deze taak heeft gewerkt?</span><span class="sxs-lookup"><span data-stu-id="ea152-121">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="ea152-122">sectie voor [het instellen van uw EOP-service](set-up-your-eop-service.md).</span><span class="sxs-lookup"><span data-stu-id="ea152-122">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="ea152-123">[De e-mail stroom testen door uw Microsoft 365-connectors te valideren](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) bevat instructies voor het testen van de juiste configuratie van uw e-mail stroom.</span><span class="sxs-lookup"><span data-stu-id="ea152-123">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
