---
title: Gebruikers afzonderlijk of in bulk toevoegen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: Meer informatie over het toevoegen van gebruikers aan Microsoft 365, één voor één of meerdere gebruikers tegelijk vanuit een CSV-bestand.
ms.openlocfilehash: 1b63f09bf34f5ca54be83eedfac9188251578a05
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387259"
---
# <a name="add-users-individually-or-in-bulk"></a><span data-ttu-id="e212b-103">Gebruikers afzonderlijk of in bulk toevoegen</span><span class="sxs-lookup"><span data-stu-id="e212b-103">Add users individually or in bulk</span></span>

<span data-ttu-id="e212b-104">De mensen in uw team hebben elk een gebruikersaccount nodig voordat ze zich kunnen aanmelden en toegang hebben tot [Microsoft 365 voor bedrijven.](https://go.microsoft.com/fwlink/?LinkID=519395)</span><span class="sxs-lookup"><span data-stu-id="e212b-104">The people on your team each need a user account before they can sign in and access [Microsoft 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="e212b-105">De eenvoudigste manier om gebruikersaccounts toe te voegen, is om ze één voor één toe te voegen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="e212b-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e212b-106">Nadat u deze stap hebt gedaan, hebben uw gebruikers Microsoft 365-licenties, inloggegevens en Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="e212b-106">After you do this step, your users will have Microsoft 365 licenses, sign in credentials, and Microsoft 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e212b-107">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="e212b-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="e212b-108">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="e212b-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="e212b-109">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e212b-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="e212b-110">Vul de volgende gegevens in het deelvenster **Basisinformatie instellen** in en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e212b-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="e212b-111">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="e212b-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="e212b-112">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Jakob is en zijn domein contoso.com is, meldt hij zich aan door jakob@contoso.com te typen.</span><span class="sxs-lookup"><span data-stu-id="e212b-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="e212b-113">**Wachtwoordinstellingen** Kies ervoor om het automatisch gegenereerde wachtwoord te gebruiken of maak zelf een sterk wachtwoord voor de gebruiker aan.</span><span class="sxs-lookup"><span data-stu-id="e212b-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="e212b-114">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="e212b-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="e212b-115">U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e212b-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="e212b-116">Kies of u het wachtwoord in een e-mail wilt verzenden wanneer de gebruiker is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="e212b-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="e212b-117">Selecteer in het deelvenster **Productlicenties toewijzen** de locatie en de geschikte licentie voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="e212b-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="e212b-118">Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="e212b-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="e212b-119">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="e212b-119">Select **Next**.</span></span>

5. <span data-ttu-id="e212b-120">Vouw op de pagina **Optionele instellingen** **Rollen** uit als u deze gebruiker een beheerder wilt maken en vouw **Profielgegevens** uit als u extra informatie over de gebruiker wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="e212b-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="e212b-121">Selecteer **Volgende**, controleer de instellingen van de nieuwe gebruiker, breng de gewenste wijzigingen aan en selecteer vervolgens **Toevoegen voltooid**.</span><span class="sxs-lookup"><span data-stu-id="e212b-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="e212b-122">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="e212b-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="e212b-123">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e212b-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="e212b-124">Vul de volgende gegevens in het deelvenster **Nieuwe gebruikers** in.</span><span class="sxs-lookup"><span data-stu-id="e212b-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="e212b-125">Selecteer **Toevoegen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="e212b-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="e212b-126">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="e212b-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="e212b-127">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Jakob is en zijn domein contoso.com is, meldt hij zich aan door jakob@contoso.com te typen.</span><span class="sxs-lookup"><span data-stu-id="e212b-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="e212b-128">**Contactgegevens** Vouw deze sectie uit om een mobiel telefoonnummer, adres, enzovoort in te vullen.</span><span class="sxs-lookup"><span data-stu-id="e212b-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="e212b-129">**Wachtwoord** Gebruik het automatisch gegenereerde wachtwoord of vouw deze sectie uit om een sterk wachtwoord voor de gebruiker op te geven.</span><span class="sxs-lookup"><span data-stu-id="e212b-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="e212b-p105">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen. U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e212b-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="e212b-132">**Rollen** Vouw deze sectie uit als u van deze gebruiker een beheerder wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e212b-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="e212b-p106">**Productlicenties** Vouw deze sectie uit en selecteer de juiste licentie. Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="e212b-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e212b-135">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="e212b-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="e212b-136">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="e212b-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="e212b-137">Vul de volgende gegevens in het deelvenster **Nieuwe gebruikers** in.</span><span class="sxs-lookup"><span data-stu-id="e212b-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="e212b-138">Selecteer **Toevoegen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="e212b-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="e212b-139">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="e212b-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="e212b-140">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Jakob is en zijn domein contoso.com is, meldt hij zich aan door jakob@contoso.com te typen.</span><span class="sxs-lookup"><span data-stu-id="e212b-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="e212b-141">**Contactgegevens** Vouw deze sectie uit om een mobiel telefoonnummer, adres, enzovoort in te vullen.</span><span class="sxs-lookup"><span data-stu-id="e212b-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="e212b-142">**Wachtwoord** Gebruik het automatisch gegenereerde wachtwoord of vouw deze sectie uit om een sterk wachtwoord voor de gebruiker op te geven.</span><span class="sxs-lookup"><span data-stu-id="e212b-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="e212b-p108">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen. U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="e212b-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="e212b-145">**Rollen** Vouw deze sectie uit als u van deze gebruiker een beheerder wilt maken.</span><span class="sxs-lookup"><span data-stu-id="e212b-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="e212b-p109">**Productlicenties** Vouw deze sectie uit en selecteer de juiste licentie. Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="e212b-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="e212b-148">Nadat u een gebruiker toevoegt, krijgt u een e-mailmelding van het team van Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="e212b-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="e212b-149">De e-mail bevat de gebruikersnaam en het wachtwoord van de persoon, zodat deze zich kan aanmelden bij Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e212b-149">The email will contain the person's user ID and password so they can sign in to Microsoft 365.</span></span> <span data-ttu-id="e212b-150">U moet uw nieuwe gebruiker vertellen over hun Microsoft 365-aanmeldingsgegevens.</span><span class="sxs-lookup"><span data-stu-id="e212b-150">You need to tell your new user about their Microsoft 365 sign in information.</span></span> <span data-ttu-id="e212b-151">Gebruik het gangbare proces voor het doorgeven van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="e212b-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="e212b-152">Als u gebruikers maakt door e-mailboxen te migreren, moet u gebruikersaccounts activeren door licenties toe te eigenen.</span><span class="sxs-lookup"><span data-stu-id="e212b-152">If you create users by migrating mail boxes, you will need to activate user accounts by assigning licenses.</span></span> <span data-ttu-id="e212b-153">Als u geen licentie toewijst aan een gebruiker, wordt het postvak uitgeschakeld na een respijtperiode van 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="e212b-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="e212b-154">Ontdek hoe u [licenties aan gebruikers kunt toewijzen](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="e212b-154">See how to [assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="e212b-155">Video: Gebruikers toevoegen en beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="e212b-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="e212b-156">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="e212b-156">Next steps</span></span>

<span data-ttu-id="e212b-157">Deel de handleiding [Aan de slag voor werknemers](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) met uw nieuwe gebruikers voor het instellen van dingen als [Office op een pc of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) en [mobiele Office-apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="e212b-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="e212b-158">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="e212b-158">Need help?</span></span>

<span data-ttu-id="e212b-159">[Neem contact op met Microsoft 365 voor zakelijke ondersteuning](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="e212b-159">[Contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="e212b-160">Wilt u honderden of duizenden gebruikers toevoegen?</span><span class="sxs-lookup"><span data-stu-id="e212b-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="e212b-161">Volg deze stappen om meerdere gebruikers tegelijkertijd toe te voegen: </span><span class="sxs-lookup"><span data-stu-id="e212b-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="e212b-162">**Gebruik een spreadsheet om personen bulksgewijs toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="e212b-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="e212b-163">Zie [Meerdere gebruikers tegelijk toevoegen](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="e212b-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="e212b-164">**Automatiseer het toevoegen van accounts en het toewijzen van licenties.**</span><span class="sxs-lookup"><span data-stu-id="e212b-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="e212b-165">Zie [Gebruikersaccounts maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="e212b-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="e212b-166">Kies deze methode als u al vertrouwd bent met het gebruik van Windows PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="e212b-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="e212b-167">**Gebruikt u ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="e212b-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="e212b-168">[Adreslijstsynchronisatie voor Office 365 instellen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="e212b-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="e212b-169">Gebruik het hulpprogramma Azure Active Directory Connect om Active Directory-gebruikersaccounts (en andere Active Directory-objecten) te repliceren in Office 365.</span><span class="sxs-lookup"><span data-stu-id="e212b-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="e212b-170">Tijdens de synchronisatie worden alleen de gebruikersaccounts toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="e212b-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="e212b-171">U zult licenties moeten toewijzen aan de gesynchroniseerde gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e212b-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="e212b-172">**Migreert u vanuit Exchange?**</span><span class="sxs-lookup"><span data-stu-id="e212b-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="e212b-173">[Manieren om meerdere e-mailaccounts naar Office 365 te migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="e212b-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="e212b-174">Wanneer u meerdere postvakken migreert naar Microsoft 365 met behulp van cutover, gefaseerd of een hybride Exchange-methode, voegt u gebruikers automatisch toe als onderdeel van de migratie.</span><span class="sxs-lookup"><span data-stu-id="e212b-174">When you migrate multiple mailboxes to Microsoft 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="e212b-175">Tijdens de migratie worden alleen de gebruikersaccounts toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="e212b-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="e212b-176">U moet licenties toewijzen aan de gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e212b-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e212b-177">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e212b-177">Related articles</span></span>

[<span data-ttu-id="e212b-178">Een nieuwe werknemer toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e212b-178">Add a new employee to Microsoft 365</span></span>](add-new-employee.md)

[<span data-ttu-id="e212b-179">Een gebruiker uit uw organisatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="e212b-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="e212b-180">Een gebruiker herstellen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e212b-180">Restore a user in Microsoft 365</span></span>](restore-user.md)

[<span data-ttu-id="e212b-181">Meerdere gebruikers tegelijk toevoegen aan Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e212b-181">Add several users at the same time to Microsoft 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)

