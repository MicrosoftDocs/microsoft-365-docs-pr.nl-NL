---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: 'Leer hoe u een privé postvak converteert naar een gedeeld postvak dat door meerdere gebruikers kan worden geopend. '
ms.openlocfilehash: 027236afb5a77e950083f254a154c491d6abc6ac
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341190"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a><span data-ttu-id="3e425-103">Het postvak van een gebruiker converteren naar een gedeeld postvak</span><span class="sxs-lookup"><span data-stu-id="3e425-103">Convert a user mailbox to a shared mailbox</span></span>

<span data-ttu-id="3e425-104">Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden.</span><span class="sxs-lookup"><span data-stu-id="3e425-104">When you convert a user's mailbox to a shared mailbox, all of the existing email and calendar is retained.</span></span> <span data-ttu-id="3e425-105">Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon.</span><span class="sxs-lookup"><span data-stu-id="3e425-105">Only now it's in a shared mailbox where several people will be able to access it instead of one person.</span></span> <span data-ttu-id="3e425-106">Op een latere datum kunt u een gedeeld postvak weer converteren naar een gebruikerspostvak (privé).</span><span class="sxs-lookup"><span data-stu-id="3e425-106">At a later date, you can convert a shared mailbox back to a user (private) mailbox.</span></span>

<span data-ttu-id="3e425-107">**Hier volgen enkele belangrijke zaken die u moet weten:**</span><span class="sxs-lookup"><span data-stu-id="3e425-107">**Here are some really important things that you need to know:**</span></span>

- <span data-ttu-id="3e425-108">Het gebruikerspostvak waarnaar u een licentie converteert, moet een licentie zijn toegewezen voordat u deze converteert naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-108">The user mailbox you're converting needs a license assigned to it before you convert it to a shared mailbox.</span></span> <span data-ttu-id="3e425-109">Anders wordt de optie om het postvak te converteren niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3e425-109">Otherwise, you won't see the option to convert the mailbox.</span></span> <span data-ttu-id="3e425-110">Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren.</span><span class="sxs-lookup"><span data-stu-id="3e425-110">If you've removed the license, add it back so you can convert the mailbox.</span></span> <span data-ttu-id="3e425-111">Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.</span><span class="sxs-lookup"><span data-stu-id="3e425-111">After converting the mailbox to a shared one, you can remove the license from the user's account.</span></span>

- <span data-ttu-id="3e425-112">Gedeelde postvakken kunnen tot maximaal 50 GB aan gegevens bevatten zonder dat hieraan een licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3e425-112">Shared mailboxes can have up to 50 GB of data without a license assigned to them.</span></span> <span data-ttu-id="3e425-113">Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen.</span><span class="sxs-lookup"><span data-stu-id="3e425-113">To hold more data than that, you need a license assigned to it.</span></span> <span data-ttu-id="3e425-114">Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3e425-114">You may need to delete a bunch of large emails (say, ones with attachments) from the shared mailbox to shrink it down so you can remove the license.</span></span>

- <span data-ttu-id="3e425-p104">Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).</span><span class="sxs-lookup"><span data-stu-id="3e425-p104">Don't delete the old user's account. That's required to anchor the shared mailbox. If you've already deleted the user account, see [Convert the mailbox of a deleted user](#convert-the-mailbox-of-a-deleted-user).</span></span>

- <span data-ttu-id="3e425-118">De regels blijven ongewijzigd nadat het postvak is geconverteerd naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-118">The rules are intact after the mailbox is converted to a shared mailbox.</span></span>

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a><span data-ttu-id="3e425-119">Het Exchange-Beheercentrum gebruiken om een postvak te converteren</span><span class="sxs-lookup"><span data-stu-id="3e425-119">Use the Exchange admin center to convert a mailbox</span></span>
 
1. <span data-ttu-id="3e425-120">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3e425-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="3e425-121">Selecteer **ontvangers** \> **postvakken**.</span><span class="sxs-lookup"><span data-stu-id="3e425-121">Select **Recipients** \> **Mailboxes**.</span></span>

3. <span data-ttu-id="3e425-122">Selecteer het gebruikerspostvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-122">Select the user mailbox.</span></span> <span data-ttu-id="3e425-123">Selecteer **converteren**onder **converteren naar gedeeld postvak**.</span><span class="sxs-lookup"><span data-stu-id="3e425-123">Under **Convert to Shared Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="3e425-124">Als het postvak kleiner is dan 50 GB, kunt u de [licentie van de gebruiker](../manage/remove-licenses-from-users.md)intrekken en geen betaling meer betalen.</span><span class="sxs-lookup"><span data-stu-id="3e425-124">If the mailbox is smaller than 50 GB, you can remove the [license from the user](../manage/remove-licenses-from-users.md), and stop paying for it.</span></span> <span data-ttu-id="3e425-125">Verwijder niet het account van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3e425-125">Don't delete the user's account.</span></span> <span data-ttu-id="3e425-126">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="3e425-126">The shared mailbox needs it there as an anchor.</span></span> <span data-ttu-id="3e425-127">Als u het postvak wilt converteren van een werknemer die uw organisatie verlaat, moet u extra stappen uitvoeren om ervoor te zorgen dat ze niet meer kunnen worden aangemeld.</span><span class="sxs-lookup"><span data-stu-id="3e425-127">If you are converting the mailbox of an employee that is leaving your organization, you should take additional steps to make sure that they cannot log in anymore.</span></span> <span data-ttu-id="3e425-128">Zie [een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).</span><span class="sxs-lookup"><span data-stu-id="3e425-128">Please see [Remove a former employee from Microsoft 365](../add-users/remove-former-employee.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="3e425-129">Het is niet nodig om het wachtwoord van de gebruiker opnieuw in te stellen tijdens het converteren van het postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-129">It's not required to reset the user's password during mailbox conversion.</span></span> <span data-ttu-id="3e425-130">Als het wachtwoord echter niet opnieuw wordt ingesteld, **blijven de oorspronkelijke gebruikersnaam en het wachtwoord werken** na voltooiing van de Postvak conversie.</span><span class="sxs-lookup"><span data-stu-id="3e425-130">However, if the password is not reset, **the original username and password continue to work** after the mailbox conversion is finished.</span></span>

<span data-ttu-id="3e425-131">Voor alles wat u verder moet weten over gedeelde postvakken raadpleegt u [gedeelde postvakken](about-shared-mailboxes.md) en [Maak een gedeeld postvak](create-a-shared-mailbox.md).</span><span class="sxs-lookup"><span data-stu-id="3e425-131">For everything else you need to know about shared mailboxes, see [About shared mailboxes](about-shared-mailboxes.md) and [Create a shared mailbox](create-a-shared-mailbox.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3e425-132">Voor gedeelde postvakken is geen afzonderlijke licentie nodig.</span><span class="sxs-lookup"><span data-stu-id="3e425-132">Shared mailboxes don’t require a separate license.</span></span> <span data-ttu-id="3e425-133">Als u echter in-place archief of een in-place bewaring of een in-place bewaring wilt inschakelen voor een gedeeld postvak, moet u een Exchange Online-abonnement 1 toewijzen met een licentie voor Exchange Online Archiving of Exchange Online plan 2 voor het postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-133">However, if you want to enable In-Place Archive or put an In-Place Hold or a Litigation Hold on a shared mailbox, you must assign an Exchange Online Plan 1 with Exchange Online Archiving or Exchange Online Plan 2 license to the mailbox.</span></span>


## <a name="convert-the-mailbox-of-a-deleted-user"></a><span data-ttu-id="3e425-134">Het postvak van een verwijderde gebruiker converteren</span><span class="sxs-lookup"><span data-stu-id="3e425-134">Convert the mailbox of a deleted user</span></span>

<span data-ttu-id="3e425-p109">Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:</span><span class="sxs-lookup"><span data-stu-id="3e425-p109">Let's say you've deleted a user account and now you want to convert their old mailbox to a share mailbox. Here's what you need to do:</span></span>

1. <span data-ttu-id="3e425-137">[Herstel het account van de gebruiker](../add-users/restore-user.md).</span><span class="sxs-lookup"><span data-stu-id="3e425-137">[Restore the user's account](../add-users/restore-user.md).</span></span>

2. <span data-ttu-id="3e425-138">Zorg ervoor dat er een Microsoft 365-licentie aan het account is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3e425-138">Make sure a Microsoft 365 license is assigned to it.</span></span>

3. <span data-ttu-id="3e425-139">Het wachtwoord van de gebruiker opnieuw instellen.</span><span class="sxs-lookup"><span data-stu-id="3e425-139">Reset the user's password.</span></span>
    
4. <span data-ttu-id="3e425-140">Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3e425-140">Wait 20-30 minutes for their mailbox to be recreated.</span></span>
    
5. <span data-ttu-id="3e425-141">Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-141">Now follow the instructions on this page to convert their mailbox to a shared mailbox.</span></span>
    
6. <span data-ttu-id="3e425-142">Wanneer u klaar bent, kunt u de licentie van het postvak van de gebruiker verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3e425-142">After that's done, you can remove the license from the user's mailbox.</span></span> <span data-ttu-id="3e425-143">Verwijder het oude postvak van de gebruiker niet.</span><span class="sxs-lookup"><span data-stu-id="3e425-143">Don't delete the user's old mailbox.</span></span> <span data-ttu-id="3e425-144">Het gedeelde postvak moet blijven bestaan als anker.</span><span class="sxs-lookup"><span data-stu-id="3e425-144">The shared mailbox needs it there as an anchor.</span></span>
    
7. <span data-ttu-id="3e425-145">Voeg leden toe aan het gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-145">Add members to the shared mailbox.</span></span>


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a><span data-ttu-id="3e425-146">Een gedeeld postvak weer converteren naar het persoonlijke postvak van een gebruiker</span><span class="sxs-lookup"><span data-stu-id="3e425-146">Convert a shared mailbox back to a user's (private) mailbox</span></span>

1. <span data-ttu-id="3e425-147">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3e425-147">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
   
2. <span data-ttu-id="3e425-148">Selecteer **Recipients** \> **gedeelde**geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="3e425-148">Select **Recipients** \> **Shared**.</span></span>

3. <span data-ttu-id="3e425-149">Selecteer het gedeelde Postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-149">Select the shared mailbox.</span></span> <span data-ttu-id="3e425-150">Selecteer converteren **naar normaal postvak voor** **converteren**.</span><span class="sxs-lookup"><span data-stu-id="3e425-150">Under **Convert to Regular Mailbox**, select **Convert**.</span></span>

4. <span data-ttu-id="3e425-151">Ga terug naar het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="3e425-151">Go back to the admin center.</span></span> <span data-ttu-id="3e425-152">Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="3e425-152">Under **Users**, choose the user account associated with the old shared mailbox.</span></span> <span data-ttu-id="3e425-153">Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.</span><span class="sxs-lookup"><span data-stu-id="3e425-153">Assign a license to the account, and reset the password.</span></span>

   <span data-ttu-id="3e425-p113">Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.</span><span class="sxs-lookup"><span data-stu-id="3e425-p113">It will take a few minutes for the mailbox to get set up, but after that, the person who is going to use that account is ready to go. When they sign in, they'll see the email and calendar items that used to be in the shared mailbox.</span></span>

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a><span data-ttu-id="3e425-156">Het postvak van een gebruiker converteren in een hybride omgeving</span><span class="sxs-lookup"><span data-stu-id="3e425-156">Convert a user's mailbox in a hybrid environment</span></span>

<span data-ttu-id="3e425-157">Als dit gedeelde Postvak zich in een hybride omgeving bevindt, wordt u **ten zeerste aangeraden** (bijna verplicht!) u het gebruikerspostvak weer naar on-premises verplaatsen, het postvak van de gebruiker converteren naar een gedeeld postvak en het gedeelde Postvak vervolgens weer naar de Cloud verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3e425-157">If this shared mailbox is in a hybrid environment, we **strongly recommend** (almost require!) that you move the user mailbox back to on-premises, convert the user mailbox to a shared mailbox, and then move the shared mailbox back to the cloud.</span></span> 

<span data-ttu-id="3e425-158">Ga als volgt te werk: als u het postvak in de Cloud converteert, kan het worden geconverteerd, maar on-premises is het postvak van de gebruiker, omdat de nieuwe realiteit geen keer wordt gesynchroniseerd op on-premises.</span><span class="sxs-lookup"><span data-stu-id="3e425-158">Here's why: if you convert the mailbox in the cloud, it can get converted, but on-premises still thinks the mailbox is the user mailbox, because the new reality does not sync back to on-premises.</span></span>

<span data-ttu-id="3e425-159">Dit is meestal niet het geval, maar er zijn een aantal scenario's waarin de on-premises kenmerken (waarmee het postvak van de gebruikerspostvak kan worden overschreven), de nieuwe Cloud versies van die kenmerken kunnen overzetten, en het postvak kan hierdoor worden geconverteerd.</span><span class="sxs-lookup"><span data-stu-id="3e425-159">Usually this is not a problem, but there are some scenarios where the on-premises attributes (which think that the mailbox is the user mailbox) can overwrite the new cloud versions of those attributes, and as a result, the mailbox might convert back.</span></span> <span data-ttu-id="3e425-160">Dit is een probleem omdat gebruikerspostvakken licenties nodig hebben **of ze gedurende 30 dagen worden verwijderd**.</span><span class="sxs-lookup"><span data-stu-id="3e425-160">This is a problem because user mailboxes require licenses **or they are soft deleted after 30 days**!</span></span>

<span data-ttu-id="3e425-161">We hebben de meeste redenen besproken waarom dit gebeurt, maar het is wel zo vaak.</span><span class="sxs-lookup"><span data-stu-id="3e425-161">We've addressed most of the reasons why this happens but it still CAN happen, although infrequently.</span></span> <span data-ttu-id="3e425-162">U kunt het beste veilig zijn en het postvak weer naar on-premises verplaatsen, dit converteren en het gedeelde Postvak vervolgens weer naar de Cloud verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3e425-162">It's best to be safe and move the mailbox back to on-premises, convert it, and then move the shared mailbox back to the cloud.</span></span> <span data-ttu-id="3e425-163">Deze aanbevolen oplossing is niet in strijd met de licentieovereenkomst voor hybride omgevingen omdat het gebruik van de on-premises postvak van de gebruiker slechts tijdelijk is.</span><span class="sxs-lookup"><span data-stu-id="3e425-163">This recommended solution is not in violation of the licensing agreement for hybrid environments because the existence of the user mailbox on-premises is only temporary.</span></span> <span data-ttu-id="3e425-164">Als u het postvak van de gebruiker of het gedeelde Postvak in uw on-premises organisatie onderneemt, krijgt u overtreding van uw licentie.</span><span class="sxs-lookup"><span data-stu-id="3e425-164">You would be in violation of your license if you maintained the user mailbox or shared mailbox in your on-premises organization and did not move it back to the cloud.</span></span>

> [!NOTE]
> <span data-ttu-id="3e425-165">Als u lid bent van de rollen groep beheer van organisatie of geadresseerden, kunt u de Exchange-beheer shell gebruiken om een gebruikerspostvak te wijzigen in een gedeelde Postvak on-premises.</span><span class="sxs-lookup"><span data-stu-id="3e425-165">If you are a member of the Organization Management or Recipient Management role group, you can use the Exchange Management shell to change a user mailbox to a shared mailbox on-premises.</span></span> <span data-ttu-id="3e425-166">Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span><span class="sxs-lookup"><span data-stu-id="3e425-166">For example, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.</span></span>

> [!TIP]
> <span data-ttu-id="3e425-167">Zie de tijdelijke oplossing in deze ondersteunings oplossing voor gevallen waarin [gedeelde postvakken onverwacht worden geconverteerd naar postvakken van gebruikers](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span><span class="sxs-lookup"><span data-stu-id="3e425-167">See the workaround in this support solution for instances when [shared mailboxes are unexpectedly converted to user mailboxes](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="3e425-168">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3e425-168">Related articles</span></span>

[<span data-ttu-id="3e425-169">Meer over gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="3e425-169">About shared mailboxes</span></span>](about-shared-mailboxes.md)

[<span data-ttu-id="3e425-170">Een gedeeld postvak maken</span><span class="sxs-lookup"><span data-stu-id="3e425-170">Create a shared mailbox</span></span>](create-a-shared-mailbox.md)

[<span data-ttu-id="3e425-171">Een gedeeld postvak configureren</span><span class="sxs-lookup"><span data-stu-id="3e425-171">Configure a shared mailbox</span></span>](configure-a-shared-mailbox.md)

[<span data-ttu-id="3e425-172">Een licentie uit een gedeeld postvak verwijderen</span><span class="sxs-lookup"><span data-stu-id="3e425-172">Remove a license from a shared mailbox</span></span>](remove-license-from-shared-mailbox.md)

[<span data-ttu-id="3e425-173">Problemen oplossen met gedeelde postvakken</span><span class="sxs-lookup"><span data-stu-id="3e425-173">Resolve issues with shared mailboxes</span></span>](resolve-issues-with-shared-mailboxes.md)
