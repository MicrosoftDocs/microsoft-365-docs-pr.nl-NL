---
title: Een gebruiker uit uw organisatie verwijderen
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
- SPO_Content
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: Meer informatie over gebruikersaccounts verwijderen. Bepaal wat u wilt doen met de e-mail van de gebruiker, de inhoud op OneDrive en of u de productlicentie wilt behouden of er niet meer voor wilt betalen.
ms.openlocfilehash: 1d529627841c648684c8a9fe217a761b29749150
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617246"
---
# <a name="delete-a-user-from-your-organization"></a><span data-ttu-id="15acc-104">Een gebruiker uit uw organisatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="15acc-104">Delete a user from your organization</span></span>
  
||
|:-----|
|<span data-ttu-id="15acc-105">**Op zoek naar hoe u uw *eigen* Microsoft 365-gebruikersaccount verwijderen dat u op het werk of op school gebruikt? Neem contact op met de technische ondersteuning op uw werk of universiteit om deze stappen voor u uit te voeren.**</span><span class="sxs-lookup"><span data-stu-id="15acc-105">**Looking for how to delete your *own* Microsoft 365 user account that you use at work or school? Contact the technical support at your work or university to do these steps for you.**</span></span>|
   
## <a name="what-you-need-to-know-about-deleting-users"></a><span data-ttu-id="15acc-106">Wat u moet weten over het verwijderen van gebruikers</span><span class="sxs-lookup"><span data-stu-id="15acc-106">What you need to know about deleting users</span></span>

- <span data-ttu-id="15acc-107">Alleen mensen met machtigingen voor algemene beheer- of gebruikersbeheer van [Microsoft 365](about-admin-roles.md) kunnen gebruikersaccounts verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15acc-107">Only people who have [Microsoft 365 global admin](about-admin-roles.md) or User management permissions for the business or school can delete user accounts.</span></span> 
    
- <span data-ttu-id="15acc-108">U hebt 30 dagen de tijd om het account te [herstellen](restore-user.md). Daarna worden de gegevens van de gebruiker permanent verwijderd.</span><span class="sxs-lookup"><span data-stu-id="15acc-108">You have 30 days to [restore](restore-user.md) the account before the user's data is permanently deleted.</span></span> 
    
- <span data-ttu-id="15acc-p102">Als u de OneDrive-gegevens van de gebruiker wilt behouden, verplaatst u ze naar een andere locatie. U kunt dit nog tot 30 dagen na het verwijderen van het account doen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md). U hoeft de SharePoint-bestanden van de gebruiker niet te verplaatsen; u hebt daar nog steeds toegang toe.</span><span class="sxs-lookup"><span data-stu-id="15acc-p102">If you want to keep the user's OneDrive data, move it to a different location. You can even do this up to 30 days after deleting the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md). You don't need to move their SharePoint files; you'll still have access to them.</span></span>
    
- <span data-ttu-id="15acc-p103">Als u de e-mail van de gebruiker wilt bewaren, moet u deze naar een andere locatie verplaatsen **VOORDAT** u het account verwijdert. Als u het account al hebt verwijderd, kunt u het binnen 30 dagen herstellen en vervolgens de e-mailgegevens verplaatsen. Hierna kunt u het account verwijderen. Zie [Toegang krijgen tot de gegevens van een voormalige gebruiker en er een back-up van maken](get-access-to-and-back-up-a-former-user-s-data.md).</span><span class="sxs-lookup"><span data-stu-id="15acc-p103">If you want to keep the user's email, **BEFORE** you delete the account, move the email to a different location. If you've already deleted the account: if it's been less than 30 days you can restore it, then move the email data, then delete the account. See [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).</span></span>
    
- <span data-ttu-id="15acc-116">Als u een Enterprise-abonnement hebt zoals Office 365 Enterprise E3, u de postvakgegevens van een verwijderd gebruikersaccount behouden door er een *inactief postvak van te*maken.</span><span class="sxs-lookup"><span data-stu-id="15acc-116">If you have an Enterprise subscription like Office 365 Enterprise E3, you can preserve the mailbox data of a deleted user account by turning it into an *inactive mailbox*.</span></span> <span data-ttu-id="15acc-117">Zie het Engelstalige artikel [Manage inactive mailboxes in Exchange Online (Inactieve postvakken beheren in Exchange Online)](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="15acc-117">To learn more, see [Manage inactive mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365).</span></span>


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a><span data-ttu-id="15acc-118">Globale beheerder: Verwijder een gebruiker, stop de betaling voor zijn licentie en kies u wilt doen met zijn e-mailadres en de OneDrive-inhoud</span><span class="sxs-lookup"><span data-stu-id="15acc-118">Global admin: Delete a user, stop paying for their license, and choose what to do with their email and OneDrive content</span></span>

<span data-ttu-id="15acc-119">Wanneer u een gebruiker verwijdert kunt u, als u een globale beheerder bent, ook een andere gebruiker toegang geven tot zijn e-mail, en kiezen wat u wilt doen met zijn OneDrive-inhoud.</span><span class="sxs-lookup"><span data-stu-id="15acc-119">If you are a global administrator, when you delete a user you can also give another user access to their email, and choose what to do with their OneDrive content.</span></span> 

  
### <a name="things-to-consider"></a><span data-ttu-id="15acc-120">Aandachtspunten</span><span class="sxs-lookup"><span data-stu-id="15acc-120">Things to consider...</span></span>

<span data-ttu-id="15acc-121">Denk, voordat u begint, na over wat u wilt doen met de e-mail- en OneDrive-inhoud van de gebruiker en of u de licentie wilt behouden of hier niet meer voor wilt betalen.</span><span class="sxs-lookup"><span data-stu-id="15acc-121">Before you begin, think about what you want to do with the user's email and OneDrive content, and whether you want to keep the license or stop paying for it.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="15acc-122">Productlicenties</span><span class="sxs-lookup"><span data-stu-id="15acc-122">Product licenses</span></span>  <br/> |<span data-ttu-id="15acc-p105">U kunt de licentie van de gebruiker verwijderen uit uw abonnementen zodat u niet langer betaalt voor deze licentie. Door deze optie te selecteren wordt de licentie automatisch verwijderd uit uw abonnementen.  </span><span class="sxs-lookup"><span data-stu-id="15acc-p105">You can remove the license from the user and remove it from your subscriptions to stop paying for that license. If you select this option, the license will be removed automatically from your subscriptions.  </span></span><br/><br/> <span data-ttu-id="15acc-p106">**U kunt de licentie niet verwijderen** als u deze hebt gekocht via een Partner of volumelicenties. Als u voor een jaarabonnement betaalt of als u in het midden van een factureringscyclus zit, kunt u de licentie niet verwijderen uit uw abonnement totdat uw verbintenis is voltooid.  </span><span class="sxs-lookup"><span data-stu-id="15acc-p106">**You can't remove the license** if you bought it through a Partner or volume licensing. If you are paying for an annual plan or if you are in the middle of a billing cycle, you won't be able to remove the license from your subscription until your commitment is completed.  </span></span><br/> |
|<span data-ttu-id="15acc-127">OneDrive-inhoud</span><span class="sxs-lookup"><span data-stu-id="15acc-127">OneDrive content</span></span>  <br/> |<span data-ttu-id="15acc-128">Als de gebruiker de bestanden in OneDrive heeft opgeslagen, kunt u een andere gebruiker toegang geven tot deze bestanden.</span><span class="sxs-lookup"><span data-stu-id="15acc-128">If the user saved their files to OneDrive, you can give another user access to these files.</span></span>  <br/><br/> <span data-ttu-id="15acc-p107">U moet de bestanden die u wilt behouden verplaatsen binnen de bewaarperiode die is ingesteld voor de OneDrive-bestanden. **Deze bewaarperiode is standaard 30 dagen.** Als u de bestanden niet binnen de bewaarperiode verplaatst na het verwijderen van de gebruiker, zal de OneDrive-inhoud permanent worden verwijderd. Als u het aantal dagen voor het bewaren van OneDrive-bestanden voor verwijderde accounts wilt verhogen, raadpleeg dan [Bewaren OneDrive instellen voor verwijderde gebruikers](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  </span><span class="sxs-lookup"><span data-stu-id="15acc-p107">You'll need to move the files you want to keep within the retention period that is set for OneDrive files. **By default, the retention period is 30 days.** If you don't move the files within the retention period after deleting the user, the OneDrive content will be permanently deleted. To increase the number of days that you retain OneDrive files for deleted accounts, see [Set the OneDrive retention for deleted users](https://support.office.com/article/fa1641ea-9f03-4f34-a826-dbd8697e76fe.aspx).  </span></span><br/><br/> <span data-ttu-id="15acc-133">**Belangrijk!**</span><span class="sxs-lookup"><span data-stu-id="15acc-133">**Important!**</span></span> <span data-ttu-id="15acc-134">Als de verwijderde gebruiker een pc gebruikte voor het downloaden van bestanden van SharePoint en OneDrive, dan is het niet mogelijk om de bestanden te wissen die deze persoon opgeslagen heeft op zijn computer.</span><span class="sxs-lookup"><span data-stu-id="15acc-134">If the deleted user used a personal computer to download files from SharePoint and OneDrive, there's no way for you to wipe those files they stored on their computer.</span></span> <span data-ttu-id="15acc-135">Zij zullen toegang blijven houden tot bestanden die werden gesynchroniseerd vanaf OneDrive.</span><span class="sxs-lookup"><span data-stu-id="15acc-135">They will continue to have access to any files that were synced from OneDrive.</span></span>           |
|<span data-ttu-id="15acc-136">E-mail</span><span class="sxs-lookup"><span data-stu-id="15acc-136">Email</span></span>  <br/> | <span data-ttu-id="15acc-p109">Als aan een andere gebruiker toegang wordt gegeven tot de e-mail van de verwijderde gebruiker, dan zal het postvak van de verwijderde gebruiker worden geconverteerd naar een gedeeld postvak. De nieuwe eigenaar van het postvak heeft vervolgens toegang tot het postvak en kan controleren op nieuwe e-mail. U beschikt tevens over de volgende opties:  </span><span class="sxs-lookup"><span data-stu-id="15acc-p109">Giving another user access to the deleted user's email will convert the deleted user's mailbox to a shared mailbox. The new mailbox owner can then access the mailbox and monitor for new email. You'll also have the following options:  </span></span><br/>  <br/><span data-ttu-id="15acc-140">De weergavenaam wijzigen - Het is raadzaam de weergavenaam te wijzigen zodat het gedeelde postvak in de lijst met Actieve gebruikers gemakkelijk te herkennen is.</span><span class="sxs-lookup"><span data-stu-id="15acc-140">Change the display name - We recommend changing the display name so that it will be easy to identify the shared mailbox in the Active users list.</span></span>  <br/>  <span data-ttu-id="15acc-p110">Automatische antwoorden inschakelen - Wij hebben alvast een beleefd automatisch antwoord voor u geschreven. U kunt verschillende automatische antwoorden verzenden naar personen van binnen uw organisatie en personen van buiten uw organisatie.  </span><span class="sxs-lookup"><span data-stu-id="15acc-p110">Turn on automatic replies - We've already written a polite automatic reply for you. You can send a different automatic replies to people within your organization and people from outside your organization.  </span></span><br/> <br/> <span data-ttu-id="15acc-143">Aliassen opschonen - Aliassen zijn extra e-mailadressen voor gebruikers.</span><span class="sxs-lookup"><span data-stu-id="15acc-143">Clean up aliases - Aliases are additional email addresses for users.</span></span> <span data-ttu-id="15acc-144">Sommige organisaties gebruiken ze niet, dus als u ze niet hebt, hoeft u hier verder niets te doen.</span><span class="sxs-lookup"><span data-stu-id="15acc-144">Some organizations don't use them, so if you don't have any you don't need to do anything else here.</span></span> <span data-ttu-id="15acc-145">Als de gebruiker aliassen heeft is het raadzaam deze te verwijderen zodat u deze e-mailadressen opnieuw kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="15acc-145">If the user does have aliases, we recommend removing them so that you can re-use those email addresses.</span></span> <span data-ttu-id="15acc-146">Anders u deze e-mailadressen pas opnieuw gebruiken als de bewaartermijn voor verwijderde postvakken is verstreken.</span><span class="sxs-lookup"><span data-stu-id="15acc-146">Otherwise, you can't re-use those email addresses until the retention period for deleted mailboxes has passed.</span></span> <span data-ttu-id="15acc-147">Een verwijderd postvak blijft standaard gedurende 30 dagen herstelbaar.</span><span class="sxs-lookup"><span data-stu-id="15acc-147">By default, a deleted mailbox is recoverable for 30 days.</span></span> <span data-ttu-id="15acc-148">Zie het Engelstalig artikel [Delete or restore user mailboxes in Exchange Online ](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="15acc-148">For more information, see  [Delete or restore user mailboxes in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox).</span></span> <br/> |
|<span data-ttu-id="15acc-149">Active Directory</span><span class="sxs-lookup"><span data-stu-id="15acc-149">Active Directory</span></span>  <br/> |<span data-ttu-id="15acc-150">Als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD, moet u het gebruikersaccount verwijderen uit Active Directory.</span><span class="sxs-lookup"><span data-stu-id="15acc-150">If your business uses **Active Directory** that is synchronizing with Azure AD, you need to delete the user account from Active Directory.</span></span> <span data-ttu-id="15acc-151">Dit is niet mogelijk via Office 365.</span><span class="sxs-lookup"><span data-stu-id="15acc-151">You can't do it through Office 365.</span></span> <span data-ttu-id="15acc-152">Lees voor instructies: [Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/p/?linkid=841808).</span><span class="sxs-lookup"><span data-stu-id="15acc-152">For instructions, see [Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808).</span></span>  <br/> |
   
### <a name="get-started"></a><span data-ttu-id="15acc-153">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="15acc-153">Get started</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="15acc-154">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="15acc-154">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end

<span data-ttu-id="15acc-155">Omdat de begeleide ervaring stap voor stap uitlegt hoe u de gebruiker verwijdert, gaat u als volgt aan de slag.</span><span class="sxs-lookup"><span data-stu-id="15acc-155">Since the guided experience walks through the steps to delete a user, here's how to get started.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="15acc-156">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15acc-157">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-157">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15acc-158">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-158">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="15acc-159">Selecteer de gebruiker die u wilt verwijderen en selecteer vervolgens **Gebruiker verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="15acc-159">Select the user you want to delete, and then select **Delete user**.</span></span>

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a><span data-ttu-id="15acc-160">Beheerder van gebruikersbeheer: Een of meer gebruikers verwijderen uit Office 365</span><span class="sxs-lookup"><span data-stu-id="15acc-160">User management admin: Delete one or more users from Office 365</span></span>


> [!IMPORTANT]
> <span data-ttu-id="15acc-p113">Verwijder het account van een gebruiker niet als je het hebt [geconverteerd naar een gedeeld postvak](../email/convert-user-mailbox-to-shared-mailbox.md) of als je e-mail doorsturen in het account hebt ingesteld. Die functies hebben nog steeds het account nodig. Voor een gedeeld postvak is geen licentie vereist. Als u het account hebt geconverteerd naar een gedeeld postvak, u [stoppen met betalen voor de licentie.](#stop-paying-for-the-license) Als u e-mail doorsturen voor het account hebt ingesteld, u de licentie niet verwijderen. Als u dit doet, wordt het doorsturen van e-mail gestopt en wordt het postvak gedeactiveerd.</span><span class="sxs-lookup"><span data-stu-id="15acc-p113">Don't delete a user's account if you've [converted it to a shared mailbox](../email/convert-user-mailbox-to-shared-mailbox.md) or if you've set up email forwarding on the account. Those functions still need the account. A shared mailbox doesn't require a license. If you've converted the account to a shared mailbox you can [Stop paying for the license](#stop-paying-for-the-license). If you've set up email forwarding on the account, you can't remove the license. Doing so will stop email forwarding and deactivate the mailbox.</span></span>
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="15acc-167">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-167">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="15acc-168">Selecteer de namen van de gebruikers die u wilt verwijderen, selecteer **Meer opties** (**...**) en kies vervolgens **Gebruiker verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="15acc-168">Select the names of the users that you want to delete, select **More options** (**...**), and then choose  **Delete user**.</span></span>

   <span data-ttu-id="15acc-169">Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**. </span><span class="sxs-lookup"><span data-stu-id="15acc-169">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="15acc-170">Zie de volgende procedure om de betaling voor de licentie stop te zetten.</span><span class="sxs-lookup"><span data-stu-id="15acc-170">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="15acc-171">U kunt de licentie ook toewijzen aan een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="15acc-171">Or, you can assign the license to another user.</span></span> <span data-ttu-id="15acc-172">Deze wordt niet automatisch aan iemand toegewezen.</span><span class="sxs-lookup"><span data-stu-id="15acc-172">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15acc-173">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-173">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="15acc-174">Selecteer de namen van de gebruikers die u wilt verwijderen en kies **Gebruikers verwijderen** in het deelvenster **Bulkacties**.</span><span class="sxs-lookup"><span data-stu-id="15acc-174">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="15acc-175">Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**. </span><span class="sxs-lookup"><span data-stu-id="15acc-175">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="15acc-176">Zie de volgende procedure om de betaling voor de licentie stop te zetten.</span><span class="sxs-lookup"><span data-stu-id="15acc-176">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="15acc-177">U kunt de licentie ook toewijzen aan een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="15acc-177">Or, you can assign the license to another user.</span></span> <span data-ttu-id="15acc-178">Deze wordt niet automatisch aan iemand toegewezen.</span><span class="sxs-lookup"><span data-stu-id="15acc-178">It won't be assigned to someone automatically.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15acc-179">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-179">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="15acc-180">Selecteer de namen van de gebruikers die u wilt verwijderen en kies **Gebruikers verwijderen** in het deelvenster **Bulkacties**.</span><span class="sxs-lookup"><span data-stu-id="15acc-180">Select the names of the users that you want to delete, and in the **Bulk actions** pane, choose **Delete users**.</span></span>

   <span data-ttu-id="15acc-181">Hoewel u het account van de gebruiker hebt verwijderd, **betaalt u nog steeds voor de licentie**. </span><span class="sxs-lookup"><span data-stu-id="15acc-181">Although you deleted the user's account, **you're still paying for the license**.</span></span> <span data-ttu-id="15acc-182">Zie de volgende procedure om de betaling voor de licentie stop te zetten.</span><span class="sxs-lookup"><span data-stu-id="15acc-182">See the next procedure to stop paying for the license.</span></span>  <span data-ttu-id="15acc-183">U kunt de licentie ook toewijzen aan een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="15acc-183">Or, you can assign the license to another user.</span></span> <span data-ttu-id="15acc-184">Deze wordt niet automatisch aan iemand toegewezen.</span><span class="sxs-lookup"><span data-stu-id="15acc-184">It won't be assigned to someone automatically.</span></span>

::: moniker-end

### <a name="stop-paying-for-the-license"></a><span data-ttu-id="15acc-185">Stoppen met betalen voor de licentie</span><span class="sxs-lookup"><span data-stu-id="15acc-185">Stop paying for the license</span></span>

<span data-ttu-id="15acc-186">Het aantal licenties beperken is een afzonderlijke stap die alleen kan worden uitgevoerd door de globale beheerder of de factureringsbeheerder.</span><span class="sxs-lookup"><span data-stu-id="15acc-186">Reducing the number of licenses is a separate step that can only be performed by the global admin or billing admin.</span></span> 
  
::: moniker range="o365-worldwide"

1. <span data-ttu-id="15acc-187">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Producten en services</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-187">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span> <span data-ttu-id="15acc-188">Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="15acc-188">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="15acc-189">Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.</span><span class="sxs-lookup"><span data-stu-id="15acc-189">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="15acc-190">Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.</span><span class="sxs-lookup"><span data-stu-id="15acc-190">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="15acc-191">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-191">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="15acc-192">Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="15acc-192">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="15acc-193">Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.</span><span class="sxs-lookup"><span data-stu-id="15acc-193">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="15acc-194">Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.</span><span class="sxs-lookup"><span data-stu-id="15acc-194">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="15acc-195">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="15acc-195">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span> <span data-ttu-id="15acc-196">Als u deze optie niet ziet, dan bent u geen globale beheerder of factureringsbeheerder en kunt u deze stap niet uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="15acc-196">If you don't see this option, you aren't a global admin or billing admin, and can't do this step.</span></span>

2. <span data-ttu-id="15acc-197">Selecteer het abonnement (als u er meer dan een hebt) en kies vervolgens **Licenties toevoegen/verwijderen** om de licentie te verwijderen, zodat u pas betaalt wanneer u een andere medewerker aanneemt.</span><span class="sxs-lookup"><span data-stu-id="15acc-197">Select the subscription (if you have more than one) and then select **Add/Remove licenses** to delete the license so you don't pay for it until you hire another person.</span></span>  

   <span data-ttu-id="15acc-198">Wanneer u later de stappen doorloopt om een andere persoon aan uw bedrijf toe te voegen, wordt u gevraagd tegelijkertijd een licentie te kopen. Dat kan met één stap.</span><span class="sxs-lookup"><span data-stu-id="15acc-198">Later when you go through the steps to add another person to your business, you'll be prompted to buy a license at the same time, with just one step!</span></span>

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a><span data-ttu-id="15acc-199">Meerdere gebruikers tegelijk verwijderen</span><span class="sxs-lookup"><span data-stu-id="15acc-199">Delete many users at the same time</span></span>

<span data-ttu-id="15acc-200">Zie de [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="15acc-200">See the [Remove-MsolUser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet.</span></span>

## <a name="fix-issues-with-deleting-a-user"></a><span data-ttu-id="15acc-201">Problemen met het verwijderen van een gebruiker oplossen</span><span class="sxs-lookup"><span data-stu-id="15acc-201">Fix issues with deleting a user</span></span>

<span data-ttu-id="15acc-202">Hier volgt een overzicht van de meestvoorkomende problemen tijdens het verwijderen van een gebruiker:  </span><span class="sxs-lookup"><span data-stu-id="15acc-202">Here are the most common issues people encounter when deleting a user:</span></span>
  
- <span data-ttu-id="15acc-p120">**U krijgt een foutbericht met de volgende strekking: 'Gebruiker kan niet worden verwijderd. Probeer het later opnieuw.'** Controleer of E-mail doorsturen is ingesteld voor het account of dat het account is omgezet naar een gedeeld postvak. In beide gevallen treedt deze fout op. Verwijder het account niet als e-mail doorsturen is ingesteld of als het account is omgezet naar een gedeeld postvak.</span><span class="sxs-lookup"><span data-stu-id="15acc-p120">**You get an error message along the lines of "User cannot be deleted. Please try again later."** Doublecheck whether the account has email forwarding set up on it, or it's been converted to a shared mailbox. Both of these will cause that error. Don't delete the account if it has email forwarding or it's been converted to a shared mailbox.</span></span>

- <span data-ttu-id="15acc-207">**U beschikt niet over de juiste machtigingen om een gebruiker te verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="15acc-207">**You don't have the appropriate permissions to delete a user**.</span></span> <span data-ttu-id="15acc-208">Alleen mensen die [algemene beheerders van Microsoft 365 of beheerders van gebruikersbeheer](about-admin-roles.md) zijn, kunnen gebruikers verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15acc-208">Only people who are [Microsoft 365 global admins or user management admins](about-admin-roles.md) can delete users.</span></span> <span data-ttu-id="15acc-209">Meestal is dit de technische ondersteuning van uw onderwijsinstelling of bedrijf.</span><span class="sxs-lookup"><span data-stu-id="15acc-209">Usually this is the technical support in your school or business.</span></span>

- <span data-ttu-id="15acc-p122">**U verwijdert de gebruiker, maar zijn of haar naam staat nog steeds in het globale adresboek**. Dit gebeurt als een bedrijf gebruikmaakt van Active Directory. U moet het gebruikersaccount uit Active Directory verwijderen. Zie het volgende TechNet-artikel voor instructies: [Gebruikersaccounts verwijderen.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span><span class="sxs-lookup"><span data-stu-id="15acc-p122">**You delete the user but their name continues appear in your global address book**. This happens when a business is using Active Directory. You have to delete the users account from Active Directory. For instructions, see this TechNet article: [Delete a User Account.](https://go.microsoft.com/fwlink/p/?linkid=841808)</span></span>

||
|:-----|
|<span data-ttu-id="15acc-214">**Wilt u Microsoft 365 van uw computer verwijderen? Ga naar [Uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).**</span><span class="sxs-lookup"><span data-stu-id="15acc-214">**Do you want to delete Microsoft 365 from your computer? Go to [Cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).**</span></span>|
   
## <a name="related-articles"></a><span data-ttu-id="15acc-215">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="15acc-215">Related articles</span></span>

[<span data-ttu-id="15acc-216">Een gebruiker herstellen</span><span class="sxs-lookup"><span data-stu-id="15acc-216">Restore a user</span></span>](restore-user.md)
  
[<span data-ttu-id="15acc-217">Een postvak definitief verwijderen</span><span class="sxs-lookup"><span data-stu-id="15acc-217">Permanently delete a mailbox</span></span>](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[<span data-ttu-id="15acc-218">Een voormalige werknemer verwijderen uit Office 365</span><span class="sxs-lookup"><span data-stu-id="15acc-218">Remove a former employee from Office 365</span></span>](remove-former-employee.md)

[<span data-ttu-id="15acc-219">Een nieuwe werknemer toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="15acc-219">Add a new employee to Office 365</span></span>](add-new-employee.md)

<span data-ttu-id="15acc-220">[Een gebruikersaccount verwijderen](https://go.microsoft.com/fwlink/p/?linkid=841808): volg deze instructies als uw bedrijf gebruikmaakt van **Active Directory** die wordt gesynchroniseerd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="15acc-220">[Delete a User Account](https://go.microsoft.com/fwlink/p/?linkid=841808): Use these instructions if your business uses **Active Directory** that is synchronizing with Azure AD.</span></span> <span data-ttu-id="15acc-221">Dat kan niet via Office 365.</span><span class="sxs-lookup"><span data-stu-id="15acc-221">You can't do it through Office 365.</span></span>