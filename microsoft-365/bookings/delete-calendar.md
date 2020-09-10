---
title: Een boekings agenda verwijderen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Gebruik het Microsoft 365-Beheercentrum of Windows PowerShell om boekings agenda's te verwijderen.
ms.openlocfilehash: 3a1cb1c54f60247ab72056b3e39b56b0981228b7
ms.sourcegitcommit: eb3c30d53a5434d8bad7c8f48a5612f3e2675945
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422440"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="dafdb-103">Een boekings agenda verwijderen in Bookings</span><span class="sxs-lookup"><span data-stu-id="dafdb-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="dafdb-104">In dit artikel wordt uitgelegd hoe u een ongewenste boekings agenda kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="dafdb-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="dafdb-105">U kunt de boekings agenda verwijderen in het Microsoft 365-Beheercentrum of u kunt PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dafdb-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="dafdb-106">De Bookings-agenda is een postvak in Exchange Online, zodat u het bijbehorende gebruikersaccount verwijdert om de boekings agenda te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="dafdb-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dafdb-107">Alle boekings agenda's die u hebt gemaakt in 2017 of eerder, moeten worden verwijderd met behulp van de PowerShell-instructies in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="dafdb-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="dafdb-108">Alle boekings agenda's die zijn gemaakt in 2018 of na kunnen worden verwijderd in het Microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="dafdb-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="dafdb-109">De boekings agenda is de plaats waar alle relevante informatie over deze boekings agenda en gegevens zijn opgeslagen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="dafdb-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="dafdb-110">Bedrijfsinformatie, logo en werkuren die zijn toegevoegd tijdens het maken van de boekings agenda</span><span class="sxs-lookup"><span data-stu-id="dafdb-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="dafdb-111">Relevante medewerkers en services die zijn toegevoegd tijdens het maken van de boekings agenda</span><span class="sxs-lookup"><span data-stu-id="dafdb-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="dafdb-112">Alle Bookings-en time-out-afspraken worden toegevoegd aan de boekings agenda nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="dafdb-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="dafdb-113">Wanneer een boekings agenda wordt verwijderd, wordt deze aanvullende informatie ook permanent verwijderd en kan deze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="dafdb-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="dafdb-114">Een boekings agenda verwijderen in het Microsoft 365-Beheercentrum</span><span class="sxs-lookup"><span data-stu-id="dafdb-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="dafdb-115">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="dafdb-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="dafdb-116">Selecteer **Gebruikers** in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="dafdb-116">In the Admin center, select **Users**.</span></span>

   ![Afbeelding van gebruikersinterface in Microsoft 365-Beheercentrum](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="dafdb-118">Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="dafdb-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Afbeelding van de gebruikersinterface voor verwijderen van de gebruiker in Microsoft 365-Beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="dafdb-120">Een boekings agenda verwijderen met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="dafdb-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="dafdb-121">Zie [verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) voor vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dafdb-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="dafdb-122">U kunt deze stappen alleen uitvoeren als u een actief Microsoft PowerShell-opdrachtvenster gebruikt dat u hebt uitgevoerd door de optie als beheerder uitvoeren te kiezen.</span><span class="sxs-lookup"><span data-stu-id="dafdb-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="dafdb-123">Voer de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="dafdb-123">Enter the following command:</span></span>

   ```PowerShell
    $user = get-credential
   ```

1. <span data-ttu-id="dafdb-124">Wanneer u hierom wordt gevraagd, meldt u zich aan met de referenties van de tenantbeheerder voor de Microsoft 365-Tenant die de boekings agenda host die u definitief wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="dafdb-124">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

1. <span data-ttu-id="dafdb-125">Voer de volgende opdracht uit op de PowerShell-opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="dafdb-125">At the PowerShell command prompt, enter this command:</span></span>

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. <span data-ttu-id="dafdb-126">Voer de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="dafdb-126">Enter the following command:</span></span>

   ```PowerShell
    Import-PSSession $s
   ```

1. <span data-ttu-id="dafdb-127">Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:</span><span class="sxs-lookup"><span data-stu-id="dafdb-127">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. <span data-ttu-id="dafdb-128">Typ de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="dafdb-128">Type the following command:</span></span>

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="dafdb-129">Let erop dat u de exacte naam opgeeft van de alias van het reserve-postvak dat u definitief wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="dafdb-129">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

1. <span data-ttu-id="dafdb-130">Voer de volgende opdracht uit om te controleren of de agenda is verwijderd:</span><span class="sxs-lookup"><span data-stu-id="dafdb-130">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   <span data-ttu-id="dafdb-131">De verwijderde agenda wordt niet weergegeven in de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="dafdb-131">The deleted calendar will not appear in the output.</span></span>
