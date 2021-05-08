---
title: Scheduler instellen voor Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Scheduler instellen voor Microsoft 365.
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286154"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="56c81-103">Scheduler instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="56c81-103">Setting up Scheduler for Microsoft 365</span></span>

<span data-ttu-id="56c81-104">Als u de Scheduler voor Microsoft 365 wilt instellen, volgt u de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="56c81-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="56c81-105">**Wat heb ik nodig?**</span><span class="sxs-lookup"><span data-stu-id="56c81-105">**What do I need?**</span></span> |<span data-ttu-id="56c81-106">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="56c81-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="56c81-107">Postvak van Cortana</span><span class="sxs-lookup"><span data-stu-id="56c81-107">Cortana mailbox</span></span> |<span data-ttu-id="56c81-108">Tenantbeheerders moeten een postvak instellen als het postvak 'Cortana' (dat wil zeggen, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="56c81-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="56c81-109">Exchange Online postvak</span><span class="sxs-lookup"><span data-stu-id="56c81-109">Exchange Online mailbox</span></span> |<span data-ttu-id="56c81-110">Gebruikers moeten een e-Exchange Online en agenda hebben</span><span class="sxs-lookup"><span data-stu-id="56c81-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="56c81-111">Scheduler-licentie</span><span class="sxs-lookup"><span data-stu-id="56c81-111">Scheduler license</span></span> |<span data-ttu-id="56c81-112">Zie [Scheduler](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c81-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="56c81-113">Een postvak voor Cortana maken</span><span class="sxs-lookup"><span data-stu-id="56c81-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="56c81-114">Een Exchange postvak in uw tenant fungeert als het Cortana-postvak voor uw tenant om e-mailberichten te verzenden en te ontvangen van en naar Cortana.</span><span class="sxs-lookup"><span data-stu-id="56c81-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="56c81-115">Alle e-mailberichten die naar Cortana worden verzonden, worden bewaard in het Cortana-postvak van uw tenant op basis van uw bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="56c81-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="56c81-116">Gebruik het Microsoft 365 beheercentrum om een nieuw postvak te maken.</span><span class="sxs-lookup"><span data-stu-id="56c81-116">Use the Microsoft 365 admin center to create a new mailbox.</span></span> <span data-ttu-id="56c81-117">Een bewaarbeleid van 30 dagen wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="56c81-117">A 30-day retention policy is recommended.</span></span> <span data-ttu-id="56c81-118">Gebruik de naam Cortana in het primaire SMTP-adres van uw postvak.</span><span class="sxs-lookup"><span data-stu-id="56c81-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="56c81-119">Namen zoals 'Cortana@yourdomain.com', 'CortanaScheduler@contoso.com' of 'Cortana.Scheduler@yourdomain.com' worden aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="56c81-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>
- <span data-ttu-id="56c81-120">Neem contact op met Microsoft (scheduler_m365@microsoft.com) om uw Cortana-postvak in te stellen.</span><span class="sxs-lookup"><span data-stu-id="56c81-120">Contact Microsoft (scheduler_m365@microsoft.com) to enable your Cortana mailbox.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="56c81-121">Neem contact op met Microsoft om uw Cortana-postvak zo te configureren dat u de Scheduler-service kunt gebruiken door een e-mail scheduler_m365@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="56c81-121">You must contact Microsoft to configure your Cortana mailbox to use the Scheduler service by emailing scheduler_m365@microsoft.com.</span></span> <span data-ttu-id="56c81-122">Het inschakelen van uw Cortana-postvak kan maximaal twee weken duren.</span><span class="sxs-lookup"><span data-stu-id="56c81-122">Enabling your Cortana mailbox may take up to two weeks.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="56c81-123">Exchange Online postvak</span><span class="sxs-lookup"><span data-stu-id="56c81-123">Exchange Online mailbox</span></span>
<span data-ttu-id="56c81-124">Scheduler is een invoegvoegvoeging voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="56c81-124">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="56c81-125">Organisatoren van vergadering moeten een postvak Exchange Online agenda hebben om Scheduler te laten werken.</span><span class="sxs-lookup"><span data-stu-id="56c81-125">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="56c81-126">Exchange-vereisten</span><span class="sxs-lookup"><span data-stu-id="56c81-126">Exchange requirements</span></span>

<span data-ttu-id="56c81-127">Naast licentieplanning moet u een van de volgende licenties hebben:</span><span class="sxs-lookup"><span data-stu-id="56c81-127">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="56c81-128">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="56c81-128">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="56c81-129">Business Basic, Business, Business Standard, Premium</span><span class="sxs-lookup"><span data-stu-id="56c81-129">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="56c81-130">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="56c81-130">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="56c81-131">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="56c81-131">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="56c81-132">Exchange Online Abonnement 1- of Abonnement 2-licentie.</span><span class="sxs-lookup"><span data-stu-id="56c81-132">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="56c81-133">**Scheduler voor Microsoft 365** is niet beschikbaar voor gebruikers van Office 365 beheerd door 21Vianet in China.</span><span class="sxs-lookup"><span data-stu-id="56c81-133">**Scheduler for Microsoft 365** isn't available for users of Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="56c81-134">Het is ook niet beschikbaar voor gebruikers van Microsoft 365 met de Duitse cloud die gebruikmaakt van de Data Trustee German Telekom.</span><span class="sxs-lookup"><span data-stu-id="56c81-134">It's also not available for users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="56c81-135">Deze wordt ondersteund voor gebruikers in Duitsland waarvan de gegevenslocatie zich niet in het Duitse datacenter bevindt.</span><span class="sxs-lookup"><span data-stu-id="56c81-135">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="56c81-136">Deze functie wordt ook niet ondersteund voor gebruikers van de Government Cloud, zoals GCC, Consumer, GCC High of DoD.</span><span class="sxs-lookup"><span data-stu-id="56c81-136">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
