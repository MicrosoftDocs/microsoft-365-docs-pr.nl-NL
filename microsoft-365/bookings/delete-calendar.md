---
title: Een reserveringsagenda verwijderen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Gebruik het Microsoft 365-beheercentrum of Windows PowerShell om Bookings-agenda's te verwijderen.
ms.openlocfilehash: 21fc7b9994ffd7f76ed04000a50bd0ee8f7f167e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034089"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="b8e8a-103">Een boekingsagenda verwijderen in Bookings</span><span class="sxs-lookup"><span data-stu-id="b8e8a-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="b8e8a-104">In dit artikel wordt uitgelegd hoe u een ongewenste boekingsagenda kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="b8e8a-105">U kunt de boekingsagenda verwijderen in het Microsoft 365-beheercentrum of u kunt PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="b8e8a-106">De Bookings-agenda is een postvak in Exchange Online, dus u verwijdert het bijbehorende gebruikersaccount om de boekingsagenda te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b8e8a-107">Alle boekingsagenda's die u in 2017 of eerder hebt gemaakt, moeten worden verwijderd met de PowerShell-instructies over dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="b8e8a-108">Alle boekingsagenda's die in 2018 of daarna zijn gemaakt, kunnen worden verwijderd in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b8e8a-109">In de boekingskalender worden alle relevante informatie over die boekingsagenda en -gegevens opgeslagen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="b8e8a-110">Zakelijke gegevens, logo's en werkuren toegevoegd wanneer de boekingsagenda is gemaakt</span><span class="sxs-lookup"><span data-stu-id="b8e8a-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="b8e8a-111">Relevante medewerkers en services toegevoegd bij het maken van de boekingsagenda</span><span class="sxs-lookup"><span data-stu-id="b8e8a-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="b8e8a-112">Alle boekingen en vrijafafspraken die zijn toegevoegd aan de boekingsagenda nadat deze zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="b8e8a-113">Wanneer een boekingsagenda is verwijderd, worden deze aanvullende gegevens ook permanent verwijderd en kunnen ze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="b8e8a-114">Een boekingsagenda verwijderen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="b8e8a-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="b8e8a-115">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="b8e8a-116">Selecteer **Gebruikers** in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-116">In the Admin center, select **Users**.</span></span>

   ![Afbeelding van de gebruikersinterface van gebruikers in het Microsoft 365-beheercentrum](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="b8e8a-118">Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Afbeelding van gebruikersgebruikersinterface verwijderen in microsoft 365-beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="b8e8a-120">Een boekingsagenda verwijderen met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8e8a-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="b8e8a-121">Zie [Verbinding maken met Exchange Online PowerShell voor](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-121">See [Connect to Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="b8e8a-122">Als u deze stappen wilt uitvoeren, moet u een actief Microsoft PowerShell-opdrachtvenster gebruiken dat u hebt uitgevoerd door de optie Als beheerder uitvoeren te kiezen.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="b8e8a-123">Laad in een PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="b8e8a-124">Als u de [EXO V2-module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)al hebt geïnstalleerd, werkt de vorige opdracht zoals geschreven.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-124">If you've already [installed the EXO V2 module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="b8e8a-125">De opdracht die u moet uitvoeren, gebruikt de volgende syntaxis:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="b8e8a-126">_\<UPN\>_ is uw account in de notatie van de gebruikersnaam `john@contoso.com` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="b8e8a-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="b8e8a-127">Wanneer u wordt gevraagd, meld u zich aan met de tenantbeheerderreferenties bij de Microsoft 365-tenant die de reserveringsagenda host die u permanent wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="b8e8a-128">Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. <span data-ttu-id="b8e8a-129">Typ de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="b8e8a-130">Typ de exacte naam van de reserveringspostvakalias die u definitief wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="b8e8a-131">Als u wilt controleren of de agenda is verwijderd, voert u de volgende opdracht in:</span><span class="sxs-lookup"><span data-stu-id="b8e8a-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="b8e8a-132">De verwijderde agenda wordt niet weergegeven in de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="b8e8a-132">The deleted calendar will not appear in the output.</span></span>
