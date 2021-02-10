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
description: Beheerder vindt meer informatie over de opties voor het configureren van de e-mailstroom en routering in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cd07c4448d9b30c90c97c7bc89c787b2fdc08cdd
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167237"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="932d5-103">E-mailstroom in EOP</span><span class="sxs-lookup"><span data-stu-id="932d5-103">Mail flow in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="932d5-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="932d5-104">**Applies to**</span></span>
- [<span data-ttu-id="932d5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="932d5-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="932d5-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="932d5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="932d5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="932d5-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="932d5-108">In Microsoft 365-organisaties met Exchange Online-postvakken of zelfstandige organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken, worden alle berichten die naar uw organisatie worden verzonden, doorgestuurd via EOP voordat uw werknemers deze zien.</span><span class="sxs-lookup"><span data-stu-id="932d5-108">In Microsoft 365 organizations with Exchange Online mailboxes, or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, all messages sent to your organization pass through EOP before your workers see them.</span></span> <span data-ttu-id="932d5-109">U hebt opties voor het routeeren van berichten die via EOP worden verwerkt voordat deze worden doorvergeleid naar het Postvak IN van uw werknemer.</span><span class="sxs-lookup"><span data-stu-id="932d5-109">You have options about how to route messages that pass through EOP for processing before they are routed to your worker inboxes.</span></span>

## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="932d5-110">Werken met opties voor berichten en berichttoegang</span><span class="sxs-lookup"><span data-stu-id="932d5-110">Working with messages and message access options</span></span>

<span data-ttu-id="932d5-111">EOP biedt flexibiliteit in de manier waarop uw berichten worden omgeleid.</span><span class="sxs-lookup"><span data-stu-id="932d5-111">EOP offers flexibility in how your messages are routed.</span></span> <span data-ttu-id="932d5-112">In de volgende onderwerpen worden de stappen in het e-mailstroomproces uitgelegd.</span><span class="sxs-lookup"><span data-stu-id="932d5-112">The following topics explain steps in the mail flow process.</span></span>

<span data-ttu-id="932d5-113">[Randblokkering op basis van adreslijst gebruiken om berichten te weigeren die naar ongeldige geadresseerden zijn verzonden](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Beschrijft de functie Randblokkering op basis van adreslijst, waarmee u berichten kunt weigeren voor ongeldige geadresseerden aan de perimeter van het servicenetwerk.</span><span class="sxs-lookup"><span data-stu-id="932d5-113">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span>

<span data-ttu-id="932d5-114">[In Het weergeven of bewerken van beheerde](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) domeinen in EOP wordt beschreven hoe u domeinen kunt beheren die zijn gekoppeld aan uw EOP-service.</span><span class="sxs-lookup"><span data-stu-id="932d5-114">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>

<span data-ttu-id="932d5-115">Als u subdomeinen aan uw organisatie toevoegt, kan uw EOP-service u helpen deze ook te beheren.</span><span class="sxs-lookup"><span data-stu-id="932d5-115">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="932d5-116">Meer informatie over subdomeinen op [E-mailstroom inschakelen voor subdomeinen in Exchange Online.](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)</span><span class="sxs-lookup"><span data-stu-id="932d5-116">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

<span data-ttu-id="932d5-117">[Configureer de e-mailstroom met connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) en laat zien hoe u deze kunt gebruiken om e-mailroutering aan te passen.</span><span class="sxs-lookup"><span data-stu-id="932d5-117">[Configure mail flow using connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing.</span></span> <span data-ttu-id="932d5-118">Scenario's zijn onder andere het zorgen voor veilige communicatie met een partnerorganisatie en het instellen van een smart host.</span><span class="sxs-lookup"><span data-stu-id="932d5-118">Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>

<span data-ttu-id="932d5-119">[Met verbeterd filteren voor connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) wordt beschreven hoe u connectors configureert als uw e-mail wordt doorgestuurd naar een service of apparaat vóór EOP.</span><span class="sxs-lookup"><span data-stu-id="932d5-119">[Enhanced Filtering for Connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors) describes how to configure connectors if your mail is routed to a service or device before EOP.</span></span>

<span data-ttu-id="932d5-120">In zelfstandige EOP-organisaties moet u een aantal configuratiestappen uitvoeren om ervoor te zorgen dat ongewenste e-mail correct wordt doorverrouteerd naar de map ongewenste e-mail van elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="932d5-120">In standalone EOP organizations, you need to perform a couple configuration steps to ensure that junk email is routed correctly to each user's junk-email folder.</span></span> <span data-ttu-id="932d5-121">Deze worden beschreven in zelfstandige EOP configureren om spam te leveren aan de map [Ongewenste e-mail in hybride omgevingen.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)</span><span class="sxs-lookup"><span data-stu-id="932d5-121">These are detailed in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="932d5-122">Als u geen berichten wilt verplaatsen naar de map ongewenste e-mail van elke gebruiker, kunt u een andere actie kiezen door het antispambeleid (ook wel inhoudsfilterbeleid genoemd) te bewerken.</span><span class="sxs-lookup"><span data-stu-id="932d5-122">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="932d5-123">Zie [Antispambeleid configureren](configure-your-spam-filter-policies.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="932d5-123">For more information, see [Configure anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

## <a name="verify-mail-flow"></a><span data-ttu-id="932d5-124">E-mailstroom controleren</span><span class="sxs-lookup"><span data-stu-id="932d5-124">Verify mail flow</span></span>

<span data-ttu-id="932d5-125">Als u wilt controleren of uw EOP-installatie, inclusief de configuratie van de connector, goed werkt, gaat u naar de pagina 'Hoe weet u of deze taak heeft gewerkt?'</span><span class="sxs-lookup"><span data-stu-id="932d5-125">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?"</span></span> <span data-ttu-id="932d5-126">in de [sectie Uw EOP-service instellen.](set-up-your-eop-service.md)</span><span class="sxs-lookup"><span data-stu-id="932d5-126">section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>

<span data-ttu-id="932d5-127">[Test de e-mailstroom door uw Microsoft 365-connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) te valideren instructies voor het testen van uw e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="932d5-127">[Test mail flow by validating your Microsoft 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
