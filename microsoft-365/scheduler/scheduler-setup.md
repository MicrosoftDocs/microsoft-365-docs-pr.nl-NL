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
ms.openlocfilehash: f09d1f51ed8a868712c22fbd7a641b35f5d29073
ms.sourcegitcommit: b6e63febe24ef1f1793dfb3ecc5ed41a4e730578
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2021
ms.locfileid: "53309344"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a><span data-ttu-id="3b078-103">Planner instellen voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3b078-103">Setting up Scheduler for Microsoft 365</span></span>


<span data-ttu-id="3b078-104">Als u de Scheduler voor Microsoft 365 wilt instellen, volgt u de volgende vereisten:</span><span class="sxs-lookup"><span data-stu-id="3b078-104">To set up the Scheduler for Microsoft 365, following are the prerequisites:</span></span>

|<span data-ttu-id="3b078-105">**Wat heb ik nodig?**</span><span class="sxs-lookup"><span data-stu-id="3b078-105">**What do I need?**</span></span> |<span data-ttu-id="3b078-106">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="3b078-106">**Description**</span></span> |
|-------------------|-------------|
|<span data-ttu-id="3b078-107">Cortana postvak</span><span class="sxs-lookup"><span data-stu-id="3b078-107">Cortana mailbox</span></span> |<span data-ttu-id="3b078-108">Tenantbeheerders moeten een postvak instellen als het postvak 'Cortana' (dat wil zeggen, cortana@yourdomain.com).</span><span class="sxs-lookup"><span data-stu-id="3b078-108">Tenant admins will need to set a mailbox to serve as the “Cortana” mailbox (that is, cortana@yourdomain.com).</span></span>         |
|<span data-ttu-id="3b078-109">Exchange Online postvak</span><span class="sxs-lookup"><span data-stu-id="3b078-109">Exchange Online mailbox</span></span> |<span data-ttu-id="3b078-110">Gebruikers moeten een e-Exchange Online en agenda hebben</span><span class="sxs-lookup"><span data-stu-id="3b078-110">Users must have an Exchange Online mail and calendar</span></span>         |
|<span data-ttu-id="3b078-111">Scheduler-licentie</span><span class="sxs-lookup"><span data-stu-id="3b078-111">Scheduler license</span></span> |<span data-ttu-id="3b078-112">Zie [Scheduler](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b078-112">For licensing and pricing information, see [Scheduler for Microsoft 365](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing).</span></span>        |

## <a name="create-a-mailbox-for-cortana"></a><span data-ttu-id="3b078-113">Een postvak maken voor Cortana</span><span class="sxs-lookup"><span data-stu-id="3b078-113">Create a mailbox for Cortana</span></span>
<span data-ttu-id="3b078-114">Een Exchange postvak in uw tenant fungeert als het Cortana voor uw tenant om e-mailberichten te verzenden en te ontvangen van en naar Cortana.</span><span class="sxs-lookup"><span data-stu-id="3b078-114">An Exchange mailbox in your tenant acts as the Cortana mailbox for your tenant to send and receive emails to and from Cortana.</span></span> <span data-ttu-id="3b078-115">Alle e-mailberichten die naar Cortana worden bewaard in het postvak van uw tenant Cortana op basis van uw bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="3b078-115">All emails sent to Cortana are retained in your tenant’s Cortana mailbox based on your retention policy.</span></span>

- <span data-ttu-id="3b078-116">Gebruik de Microsoft 365-beheercentrum om een gebruikerspostvak te maken.</span><span class="sxs-lookup"><span data-stu-id="3b078-116">Use the Microsoft 365 admin center to create a user mailbox.</span></span> <span data-ttu-id="3b078-117">Een bewaarbeleid van 30 dagen wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="3b078-117">A 30-day retention policy is recommended.</span></span> 
- <span data-ttu-id="3b078-118">Gebruik de naam Cortana in het primaire SMTP-adres van uw postvak.</span><span class="sxs-lookup"><span data-stu-id="3b078-118">Use the name Cortana in your mailbox’s primary SMTP address.</span></span> <span data-ttu-id="3b078-119">Namen zoals 'Cortana@yourdomain.com', 'CortanaScheduler@contoso.com', of 'Cortana. Scheduler@yourdomain.com' wordt aanbevolen.</span><span class="sxs-lookup"><span data-stu-id="3b078-119">Names such as “Cortana@yourdomain.com,’ ‘CortanaScheduler@contoso.com,’ or ‘Cortana.Scheduler@yourdomain.com’ are recommended.</span></span>

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a><span data-ttu-id="3b078-120">Het postvak aanwijzen als planningsassistent</span><span class="sxs-lookup"><span data-stu-id="3b078-120">Designate the mailbox as the Scheduler Assistant</span></span>

<span data-ttu-id="3b078-121">Nadat er een uniek postvak Cortana Scheduler is gemaakt, moet u het postvak aanwijzen om formeel Microsoft 365 maken.</span><span class="sxs-lookup"><span data-stu-id="3b078-121">After a unique mailbox for Cortana Scheduler has been created, you must designate the mailbox to Microsoft 365 formally.</span></span> <span data-ttu-id="3b078-122">Nadat u het postvak Cortana scheduler hebt aangewezen, is het beschikbaar om vergaderingen namens uw gebruikers te plannen.</span><span class="sxs-lookup"><span data-stu-id="3b078-122">After you designate the Cortana Scheduler mailbox, it will be available to schedule meetings on behalf of your users.</span></span>

<span data-ttu-id="3b078-123">Als u het postvak Cortana scheduler wilt aanwijzen, moet een geautoriseerde beheerder een powershell-opdracht met één regel uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3b078-123">To designate the Cortana Scheduler mailbox, an authorized admin must run a one-line PowerShell command.</span></span> 

1. <span data-ttu-id="3b078-124">Verbinding maken om Microsoft 365 externe PowerShell-ruimte voor uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="3b078-124">Connect to Microsoft 365 remote PowerShell run space for your organization.</span></span>
2. <span data-ttu-id="3b078-125">Voer het volgende PowerShell-script uit om het postvak voor Scheduler aan te wijzen:</span><span class="sxs-lookup"><span data-stu-id="3b078-125">Run the following PowerShell script to designate the mailbox for Scheduler:</span></span>

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

<span data-ttu-id="3b078-126">Nadat u deze opdracht 'set' hebt uitgevoerd in het Cortana Scheduler-postvak, wordt er een nieuwe 'PersistedCapability' ingesteld op het postvak om te zien dat dit postvak het 'SchedulerAssistant' is.</span><span class="sxs-lookup"><span data-stu-id="3b078-126">After running this "set" command on the Cortana Scheduler mailbox, a new "PersistedCapability" is set on the mailbox to note that this mailbox is the "SchedulerAssistant".</span></span>

> [!NOTE]
> <span data-ttu-id="3b078-127">Volg deze stappen om uw organisatie te verbinden met PowerShell als u dit nog niet eerder hebt gedaan: Verbinding maken Microsoft 365 [PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="3b078-127">Follow these steps to connect your organization to PowerShell if you’ve not done so previously: [Connect to Microsoft 365 with PowerShell - Microsoft 365 Enterprise | Microsoft Docs](../enterprise/connect-to-microsoft-365-powershell.md)</span></span>

<span data-ttu-id="3b078-128">Als u wilt weten welk postvak in uw organisatie momenteel is ingesteld als de Cortana planningsassistent, kunt u de functie Get uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="3b078-128">To discover which mailbox in your organization is currently set as the Cortana Scheduler assistant, run the get function:</span></span>
 
```powershell

Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}

```

> [!IMPORTANT]
> <span data-ttu-id="3b078-129">Het kan maximaal twee uur duren voordat het Postvak Scheduler volledig is ingericht om de schedulerAssistant-functie in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3b078-129">It might take up to two hours for the Scheduler mailbox to complete full provisioning to set the SchedulerAssistant capability.</span></span>

## <a name="exchange-online-mailbox"></a><span data-ttu-id="3b078-130">Exchange Online postvak</span><span class="sxs-lookup"><span data-stu-id="3b078-130">Exchange Online mailbox</span></span>
<span data-ttu-id="3b078-131">Scheduler is een invoegvoegvoeging voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3b078-131">Scheduler is an add-on to Microsoft 365.</span></span> <span data-ttu-id="3b078-132">Organisatoren van vergadering moeten een postvak Exchange Online agenda hebben om Scheduler te laten werken.</span><span class="sxs-lookup"><span data-stu-id="3b078-132">Meeting organizers must have an Exchange Online mailbox and calendar for Scheduler to work.</span></span>

## <a name="exchange-requirements"></a><span data-ttu-id="3b078-133">Exchange-vereisten</span><span class="sxs-lookup"><span data-stu-id="3b078-133">Exchange requirements</span></span>

<span data-ttu-id="3b078-134">Naast licentieplanning moet u een van de volgende licenties hebben:</span><span class="sxs-lookup"><span data-stu-id="3b078-134">In addition to licensing Scheduler, you must have one of the following licenses:</span></span>

- <span data-ttu-id="3b078-135">Microsoft 365 E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="3b078-135">Microsoft 365 E3, A3, E5, A5</span></span>
- <span data-ttu-id="3b078-136">Business Basic, Business, Business Standard, Premium</span><span class="sxs-lookup"><span data-stu-id="3b078-136">Business Basic, Business, Business Standard, Business Premium</span></span>
- <span data-ttu-id="3b078-137">Office 365 E1, A1, E3, A3, E5, A5</span><span class="sxs-lookup"><span data-stu-id="3b078-137">Office 365 E1, A1, E3, A3, E5, A5</span></span>
- <span data-ttu-id="3b078-138">Business Essentials, Business Premium</span><span class="sxs-lookup"><span data-stu-id="3b078-138">Business Essentials, Business Premium</span></span>
- <span data-ttu-id="3b078-139">Exchange Online Abonnement 1- of Abonnement 2-licentie.</span><span class="sxs-lookup"><span data-stu-id="3b078-139">Exchange Online Plan 1 or Plan 2 license.</span></span> 

> [!Note]
> <span data-ttu-id="3b078-140">**Scheduler voor Microsoft 365** is momenteel beschikbaar voor wereldwijde multitenten, alleen in het Engels.</span><span class="sxs-lookup"><span data-stu-id="3b078-140">**Scheduler for Microsoft 365** is currently available for worldwide multi-tenants, in English only.</span></span></br>
>
><span data-ttu-id="3b078-141">Het is niet beschikbaar voor gebruikers van Office 365 beheerd door 21Vianet in China of gebruikers van Microsoft 365 met de Duitse cloud die gebruikmaakt van de Data Trustee German Telekom.</span><span class="sxs-lookup"><span data-stu-id="3b078-141">It is not available for users of Office 365 operated by 21Vianet in China or users of Microsoft 365 with the German cloud that uses the data trustee German Telekom.</span></span> <span data-ttu-id="3b078-142">Deze wordt ondersteund voor gebruikers in Duitsland waarvan de gegevenslocatie zich niet in het Duitse datacenter bevindt.</span><span class="sxs-lookup"><span data-stu-id="3b078-142">It is supported for users in Germany whose data location isn't in the German datacenter.</span></span>
>
><span data-ttu-id="3b078-143">Deze functie wordt ook niet ondersteund voor gebruikers van de Government Cloud, zoals GCC, Consumer, GCC High of DoD.</span><span class="sxs-lookup"><span data-stu-id="3b078-143">This feature is also not supported for users of the Government Cloud, including GCC, Consumer, GCC High, or DoD.</span></span>
