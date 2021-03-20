---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informatie over het converteren van een privépostvak naar een gedeeld postvak dat toegankelijk is voor meerdere gebruikers. '
ms.openlocfilehash: d5b33731908d2d555a8dd12d5d7fbbd462bd83ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915864"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="38337-103">Het postvak van een gebruiker converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="38337-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="38337-104">Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden.</span><span class="sxs-lookup"><span data-stu-id="38337-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="38337-105">Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon.</span><span class="sxs-lookup"><span data-stu-id="38337-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="38337-106">Op een later tijdstip kunt u een gedeeld postvak weer converteren naar een (privé)postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="38337-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="38337-107">**Hier vindt u enkele belangrijke dingen die u moet weten:**</span><span class="sxs-lookup"><span data-stu-id="38337-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="38337-108">Het gebruikerspostvak dat u converteert, heeft een licentie nodig die aan het postvak is toegewezen voordat u het converteert naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="38337-109">Anders wordt de optie om het postvak te converteren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="38337-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="38337-110">Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren.</span><span class="sxs-lookup"><span data-stu-id="38337-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="38337-111">Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="38337-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="38337-112">Gedeelde postvakken kunnen maximaal 50 GB aan gegevens bevatten zonder dat er een licentie aan is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="38337-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="38337-113">Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="38337-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="38337-114">Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="38337-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="38337-p104">Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="38337-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="38337-118">De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="38337-119">Het Exchange-beheercentrum gebruiken om een postvak te converteren</span><span class="sxs-lookup"><span data-stu-id="38337-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="38337-120">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="38337-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="38337-121">Selecteer **GeadresseerdenPostvakken.** \> </span><span class="sxs-lookup"><span data-stu-id="38337-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="38337-122">Selecteer het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="38337-122">Select the user mailbox.</span></span> <span data-ttu-id="38337-123">Selecteer **onder Converteren naar gedeeld postvak** de optie **Converteren.**</span><span class="sxs-lookup"><span data-stu-id="38337-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="38337-124">Als het postvak kleiner is dan 50 GB, kunt u de licentie van de gebruiker verwijderen [en](../manage/remove-licenses-from-users.md)stoppen met betalen.</span><span class="sxs-lookup"><span data-stu-id="38337-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="38337-125">Verwijder het account van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="38337-125">Don't delete the user's account.</span></span> <span data-ttu-id="38337-126">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="38337-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="38337-127">Als u het postvak van een werknemer converteert die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat ze zich niet meer kunnen aanmelden.</span><span class="sxs-lookup"><span data-stu-id="38337-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="38337-128">Zie [Een voormalige werknemer verwijderen uit Microsoft 365.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="38337-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="38337-129">Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="38337-130">Als het wachtwoord echter niet opnieuw wordt **ingesteld,** blijven de oorspronkelijke gebruikersnaam en het oorspronkelijke wachtwoord werken nadat de postvakconversie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="38337-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="38337-131">Zie Over gedeelde postvakken en Een [](about-shared-mailboxes.md) gedeeld postvak maken voor alles wat u moet weten over [gedeelde postvakken.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="38337-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="38337-132">Voor gedeelde postvakken is geen aparte licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="38337-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="38337-133">Als u echter In-Place Archive wilt inschakelen of een licentie voor een In-Place-opslag of een geschil in een gedeeld postvak wilt inschakelen, moet u een Exchange Online Plan 1 met Exchange Online Archiving- of Exchange Online Plan 2-licentie aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="38337-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="38337-134">Het postvak van een verwijderde gebruiker converteren</span><span class="sxs-lookup"><span data-stu-id="38337-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="38337-p109">Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:</span><span class="sxs-lookup"><span data-stu-id="38337-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="38337-137">[Het account van de gebruiker herstellen.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="38337-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="38337-138">Zorg ervoor dat er een Microsoft 365-licentie aan is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="38337-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="38337-139">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="38337-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="38337-140">Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="38337-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="38337-141">Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="38337-142">Nadat dat is gebeurd, kunt u de licentie verwijderen uit het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="38337-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="38337-143">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="38337-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="38337-144">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="38337-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="38337-145">Voeg leden toe aan het gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="38337-146">Een gedeeld postvak converteren naar het (privé)postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="38337-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="38337-147">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="38337-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="38337-148">Selecteer **Geadresseerden** \> **gedeeld.**</span><span class="sxs-lookup"><span data-stu-id="38337-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="38337-149">Selecteer het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-149">Select the shared mailbox.</span></span> <span data-ttu-id="38337-150">Selecteer **onder Converteren naar normaal postvak** de optie **Converteren.**</span><span class="sxs-lookup"><span data-stu-id="38337-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="38337-151">Ga terug naar het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="38337-151">Go back to the admin center.</span></span> <span data-ttu-id="38337-152">Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="38337-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="38337-153">Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="38337-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="38337-p113">Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.</span><span class="sxs-lookup"><span data-stu-id="38337-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="38337-156">Het postvak van een gebruiker converteren in een hybride omgeving</span><span class="sxs-lookup"><span data-stu-id="38337-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="38337-157">Zie voor meer informatie over het converteren van een gebruikerspostvak naar een gedeeld postvak in een hybride Exchange-omgeving:</span><span class="sxs-lookup"><span data-stu-id="38337-157">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="38337-158">Cmdlets voor het maken of wijzigen van een extern gedeeld postvak in een on-premises Exchange-omgeving</span><span class="sxs-lookup"><span data-stu-id="38337-158">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="38337-159">Gedeelde postvakken worden onverwacht geconverteerd naar gebruikerspostvakken nadat adreslijstsynchronisatie is uitgevoerd in een hybride Exchange-implementatie</span><span class="sxs-lookup"><span data-stu-id="38337-159">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="38337-160">Als u lid bent van de rollengroep Organisatiebeheer of Geadresseerdenbeheer, kunt u de Exchange Management Shell gebruiken om een gebruikerspostvak te wijzigen in een gedeeld postvak on-premises.</span><span class="sxs-lookup"><span data-stu-id="38337-160">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="38337-161">Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="38337-161">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-articles"></a><span data-ttu-id="38337-162">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="38337-162">Related articles</span></span>

[<span data-ttu-id="38337-163">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="38337-163">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="38337-164">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="38337-164">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="38337-165">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="38337-165">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="38337-166">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="38337-166">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="38337-167">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="38337-167">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)