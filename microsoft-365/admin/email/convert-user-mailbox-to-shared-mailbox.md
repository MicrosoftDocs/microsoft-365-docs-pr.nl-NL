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
description: 'Informatie over het converteren van een privépostvak naar een gedeeld postvak dat door meerdere personen kan worden gebruikt in plaats van door slechts één persoon. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635472"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="1c5be-103">Het postvak van een gebruiker converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="1c5be-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="1c5be-104">Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden.</span><span class="sxs-lookup"><span data-stu-id="1c5be-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="1c5be-105">Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon.</span><span class="sxs-lookup"><span data-stu-id="1c5be-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="1c5be-106">Op een later tijdstip kunt u een gedeeld postvak weer converteren naar een (privé)postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c5be-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1c5be-107">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="1c5be-107">Before you begin</span></span>

<span data-ttu-id="1c5be-108">**Hier vindt u enkele belangrijke dingen die u moet weten:**</span><span class="sxs-lookup"><span data-stu-id="1c5be-108">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="1c5be-109">Het gebruikerspostvak dat u converteert, heeft een licentie nodig die aan het postvak is toegewezen voordat u het converteert naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-109">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="1c5be-110">Anders wordt de optie om het postvak te converteren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="1c5be-110">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="1c5be-111">Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren.</span><span class="sxs-lookup"><span data-stu-id="1c5be-111">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="1c5be-112">Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="1c5be-112">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="1c5be-113">Gedeelde postvakken kunnen maximaal 50 GB aan gegevens bevatten zonder dat er een licentie aan is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-113">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="1c5be-114">Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-114">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="1c5be-115">Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-115">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="1c5be-p104">Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="1c5be-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="1c5be-119">De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-119">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="1c5be-120">Het beheercentrum Exchange een postvak converteren</span><span class="sxs-lookup"><span data-stu-id="1c5be-120">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="1c5be-121">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="1c5be-121">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="1c5be-122">Selecteer **GeadresseerdenPostvakken.** \> </span><span class="sxs-lookup"><span data-stu-id="1c5be-122">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="1c5be-123">Selecteer het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c5be-123">Select the user mailbox.</span></span> <span data-ttu-id="1c5be-124">Selecteer **onder Converteren naar gedeeld postvak** de optie **Converteren.**</span><span class="sxs-lookup"><span data-stu-id="1c5be-124">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1c5be-125">Als het postvak kleiner is dan 50 GB, kunt u de licentie van de gebruiker verwijderen [en](../manage/remove-licenses-from-users.md)stoppen met betalen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-125">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="1c5be-126">Verwijder het account van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="1c5be-126">Don't delete the user's account.</span></span> <span data-ttu-id="1c5be-127">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="1c5be-127">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="1c5be-128">Als u het postvak van een werknemer converteert die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat ze zich niet meer kunnen aanmelden.</span><span class="sxs-lookup"><span data-stu-id="1c5be-128">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="1c5be-129">Zie [Een voormalige werknemer verwijderen uit Microsoft 365.](../add-users/remove-former-employee.md)</span><span class="sxs-lookup"><span data-stu-id="1c5be-129">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1c5be-130">Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-130">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="1c5be-131">Als het wachtwoord echter niet opnieuw wordt **ingesteld,** blijven de oorspronkelijke gebruikersnaam en het oorspronkelijke wachtwoord werken nadat de postvakconversie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="1c5be-131">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="1c5be-132">Zie Over gedeelde postvakken en Een [](about-shared-mailboxes.md) gedeeld postvak maken voor alles wat u moet weten over [gedeelde postvakken.](create-a-shared-mailbox.md)</span><span class="sxs-lookup"><span data-stu-id="1c5be-132">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1c5be-133">Voor gedeelde postvakken is geen aparte licentie vereist.</span><span class="sxs-lookup"><span data-stu-id="1c5be-133">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="1c5be-134">Als u echter In-Place Archive wilt inschakelen of een In-Place Hold of Een Geschil in de wacht wilt zetten op een gedeeld postvak, moet u een Exchange Online Plan 1 met Exchange Online Archiving- of Exchange Online Plan 2-licentie aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-134">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>

## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="1c5be-135">Het postvak van een verwijderde gebruiker converteren</span><span class="sxs-lookup"><span data-stu-id="1c5be-135">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="1c5be-p109">Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:</span><span class="sxs-lookup"><span data-stu-id="1c5be-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="1c5be-138">[Het account van de gebruiker herstellen.](../add-users/restore-user.md)</span><span class="sxs-lookup"><span data-stu-id="1c5be-138">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="1c5be-139">Zorg ervoor dat Microsoft 365 licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-139">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="1c5be-140">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="1c5be-140">Reset the user's password.</span></span>
    
4. <span data-ttu-id="1c5be-141">Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1c5be-141">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="1c5be-142">Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-142">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="1c5be-143">Nadat dat is gebeurd, kunt u de licentie verwijderen uit het postvak van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="1c5be-143">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="1c5be-144">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="1c5be-144">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="1c5be-145">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="1c5be-145">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="1c5be-146">Voeg leden toe aan het gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-146">Add members to the shared mailbox.</span></span>

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="1c5be-147">Een gedeeld postvak converteren naar het (privé)postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="1c5be-147">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="1c5be-148">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="1c5be-148">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="1c5be-149">Selecteer **Geadresseerden** \> **gedeeld.**</span><span class="sxs-lookup"><span data-stu-id="1c5be-149">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="1c5be-150">Selecteer het gedeelde postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-150">Select the shared mailbox.</span></span> <span data-ttu-id="1c5be-151">Selecteer **onder Converteren naar normaal postvak** de optie **Converteren.**</span><span class="sxs-lookup"><span data-stu-id="1c5be-151">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="1c5be-152">Ga terug naar het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1c5be-152">Go back to the admin center.</span></span> <span data-ttu-id="1c5be-153">Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="1c5be-153">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="1c5be-154">Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="1c5be-154">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="1c5be-p113">Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.</span><span class="sxs-lookup"><span data-stu-id="1c5be-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="1c5be-157">Het postvak van een gebruiker converteren in een hybride omgeving</span><span class="sxs-lookup"><span data-stu-id="1c5be-157">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="1c5be-158">Zie voor meer informatie over het converteren van een gebruikerspostvak naar een gedeeld postvak in Exchange hybride omgeving:</span><span class="sxs-lookup"><span data-stu-id="1c5be-158">For more info about converting a user mailbox to a shared mailbox in an Exchange Hybrid environment, see:</span></span>

 - [<span data-ttu-id="1c5be-159">Cmdlets voor het maken of wijzigen van een extern gedeeld postvak in een on-premises Exchange omgeving</span><span class="sxs-lookup"><span data-stu-id="1c5be-159">Cmdlets to create or modify a remote shared mailbox in an on-premises Exchange environment</span></span>](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [<span data-ttu-id="1c5be-160">Gedeelde postvakken worden onverwacht geconverteerd naar gebruikerspostvakken nadat adreslijstsynchronisatie is uitgevoerd in een Exchange hybride implementatie</span><span class="sxs-lookup"><span data-stu-id="1c5be-160">Shared mailboxes are unexpectedly converted to user mailboxes after directory synchronization runs in an Exchange hybrid deployment</span></span>](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> <span data-ttu-id="1c5be-161">Als u lid bent van de rollengroep Organisatiebeheer of Geadresseerdenbeheer, kunt u de Exchange Management Shell gebruiken om een gebruikerspostvak te wijzigen in een gedeeld postvak on-premises.</span><span class="sxs-lookup"><span data-stu-id="1c5be-161">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management Shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="1c5be-162">Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="1c5be-162">For example, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.</span></span>

## <a name="related-content"></a><span data-ttu-id="1c5be-163">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="1c5be-163">Related content</span></span>

<span data-ttu-id="1c5be-164">[Over gedeelde postvakken](about-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1c5be-164">[About shared mailboxes](about-shared-mailboxes.md) (article)</span></span>\
<span data-ttu-id="1c5be-165">[Een gedeeld postvak](create-a-shared-mailbox.md) maken (artikel)</span><span class="sxs-lookup"><span data-stu-id="1c5be-165">[Create a shared mailbox](create-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="1c5be-166">[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1c5be-166">[Configure a shared mailbox](configure-a-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="1c5be-167">[Een licentie verwijderen uit een gedeeld postvak](remove-license-from-shared-mailbox.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1c5be-167">[Remove a license from a shared mailbox](remove-license-from-shared-mailbox.md) (article)</span></span>\
<span data-ttu-id="1c5be-168">[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="1c5be-168">[Resolve issues with shared mailboxes](resolve-issues-with-shared-mailboxes.md) (article)</span></span>