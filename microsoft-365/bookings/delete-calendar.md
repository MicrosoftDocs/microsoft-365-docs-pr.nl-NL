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
description: Gebruik het Microsoft 365-beheercentrum of Windows PowerShell om Boekingsagenda's te verwijderen.
ms.openlocfilehash: 7407298adb402de79a1010b51544deee4b94cf5a
ms.sourcegitcommit: 9adb89206daa075af34a73bcb7e8fb86d7c2919a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/10/2021
ms.locfileid: "50604018"
---
# <a name="delete-a-booking-calendar-in-bookings"></a><span data-ttu-id="710b7-103">Een boekingsagenda verwijderen in Bookings</span><span class="sxs-lookup"><span data-stu-id="710b7-103">Delete a booking calendar in Bookings</span></span>

<span data-ttu-id="710b7-104">In dit artikel wordt uitgelegd hoe u een ongewenste boekingsagenda kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="710b7-104">This article explains how you can delete an unwanted booking calendar.</span></span> <span data-ttu-id="710b7-105">U kunt de boekingsagenda verwijderen in het Microsoft 365-beheercentrum of u kunt PowerShell gebruiken.</span><span class="sxs-lookup"><span data-stu-id="710b7-105">You can delete the booking calendar in the Microsoft 365 admin center or you can use PowerShell.</span></span> <span data-ttu-id="710b7-106">De Bookings-agenda is een postvak in Exchange Online, dus u verwijdert het bijbehorende gebruikersaccount om de boekingsagenda te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="710b7-106">The Bookings calendar is a mailbox in Exchange Online so you delete the corresponding user account to delete the booking calendar.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="710b7-107">Alle boekingsagenda's die u in 2017 of eerder hebt gemaakt, moeten worden verwijderd volgens de PowerShell-instructies voor dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="710b7-107">All booking calendars that you created in 2017 or before must be deleted using the PowerShell instructions on this topic.</span></span> <span data-ttu-id="710b7-108">Alle boekingsagenda's die in 2018 of later zijn gemaakt, kunnen worden verwijderd in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="710b7-108">All booking calendars created in 2018 or after can be deleted in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="710b7-109">In de boekingsagenda worden alle relevante informatie over de boekingsagenda en de gegevens opgeslagen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="710b7-109">The booking calendar is where all relevant information about that booking calendar and data are stored, including:</span></span>

- <span data-ttu-id="710b7-110">Bedrijfsgegevens, logo en werkuren die zijn toegevoegd toen de boekingsagenda werd gemaakt</span><span class="sxs-lookup"><span data-stu-id="710b7-110">Business information, logo, and working hours added when the booking calendar was created</span></span>
- <span data-ttu-id="710b7-111">Relevante medewerkers en services die zijn toegevoegd toen de boekingsagenda werd gemaakt</span><span class="sxs-lookup"><span data-stu-id="710b7-111">Relevant staff and services added when the booking calendar was created</span></span>
- <span data-ttu-id="710b7-112">Alle boekingen en afspraken met een time-off die zijn toegevoegd aan de boekingsagenda nadat deze is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="710b7-112">All bookings and time off appointments added to the booking calendar once it was created.</span></span>

> [!WARNING]
> <span data-ttu-id="710b7-113">Wanneer een boekingsagenda is verwijderd, wordt deze aanvullende informatie ook definitief verwijderd en kan deze niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="710b7-113">Once a booking calendar is deleted, this additional information is also permanently deleted and can't be recovered.</span></span>

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a><span data-ttu-id="710b7-114">Een boekingsagenda verwijderen in het Microsoft 365-beheercentrum</span><span class="sxs-lookup"><span data-stu-id="710b7-114">Delete a booking calendar in the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="710b7-115">Ga naar het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="710b7-115">Go to the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="710b7-116">Selecteer **Gebruikers** in het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="710b7-116">In the Admin center, select **Users**.</span></span>

   ![Afbeelding van de gebruikersinterface van gebruikers in het Microsoft 365-beheercentrum](../media/bookings-admin-center-users.png)

1. <span data-ttu-id="710b7-118">Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="710b7-118">On the **Active Users** page, choose the names of the users that you want to delete, and then select **Delete user**.</span></span>

   ![Afbeelding van de gebruikersinterface voor gebruikers verwijderen in het Microsoft 365-beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a><span data-ttu-id="710b7-120">Een boekingsagenda verwijderen met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="710b7-120">Delete a booking calendar using Exchange Online PowerShell</span></span>

<span data-ttu-id="710b7-121">Zie Connect to Exchange Online PowerShell for prerequisites and guidance for connecting to Exchange Online PowerShell (Verbinding maken met [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) voor vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="710b7-121">See [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) for prerequisites and guidance for connecting to Exchange Online PowerShell.</span></span>

<span data-ttu-id="710b7-122">Als u deze stappen wilt uitvoeren, moet u een actief Microsoft PowerShell-opdrachtvenster gebruiken dat u hebt uitgevoerd door de optie Als administrator uitvoeren te kiezen.</span><span class="sxs-lookup"><span data-stu-id="710b7-122">To perform these steps, you must be using an active Microsoft PowerShell command window that you ran by choosing the “Run as administrator” option.</span></span>

1. <span data-ttu-id="710b7-123">Laad in een PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="710b7-123">In a PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > <span data-ttu-id="710b7-124">Als u de [EXO V2-module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)al hebt geïnstalleerd, werkt de vorige opdracht zoals geschreven.</span><span class="sxs-lookup"><span data-stu-id="710b7-124">If you've already [installed the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module), the previous command will work as written.</span></span>
   
2. <span data-ttu-id="710b7-125">Voor de opdracht die u moet uitvoeren, wordt de volgende syntaxis gebruikt:</span><span class="sxs-lookup"><span data-stu-id="710b7-125">The command that you need to run uses the following syntax:</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - <span data-ttu-id="710b7-126">_\<UPN\>_ is uw account in de notatie User Principal Name `john@contoso.com` (bijvoorbeeld).</span><span class="sxs-lookup"><span data-stu-id="710b7-126">_\<UPN\>_ is your account in user principal name format (for example, `john@contoso.com`).</span></span>

3. <span data-ttu-id="710b7-127">Meld u aan met de referenties van de tenantbeheerder bij de Microsoft 365-tenant die als host de boekingsagenda bevat die u definitief wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="710b7-127">When you are prompted, log on with tenant administrator credentials to the Microsoft 365 tenant that hosts the booking calendar you want to permanently delete.</span></span>

4. <span data-ttu-id="710b7-128">Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:</span><span class="sxs-lookup"><span data-stu-id="710b7-128">Once this command is done processing, enter the following command to get a list of the booking mailboxes in your tenant:</span></span>

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. <span data-ttu-id="710b7-129">Typ de volgende opdracht:</span><span class="sxs-lookup"><span data-stu-id="710b7-129">Type the following command:</span></span>

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > <span data-ttu-id="710b7-130">Let op dat u de exacte naam typt van de postvakalias van de reservering die u definitief wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="710b7-130">Be careful to type the exact name of the booking mailbox alias that you want to permanently delete.</span></span>

6. <span data-ttu-id="710b7-131">Voer de volgende opdracht uit om te controleren of de agenda is verwijderd:</span><span class="sxs-lookup"><span data-stu-id="710b7-131">To verify that the calendar has been deleted, enter the following command:</span></span>

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   <span data-ttu-id="710b7-132">De verwijderde agenda wordt niet weergegeven in de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="710b7-132">The deleted calendar will not appear in the output.</span></span>
