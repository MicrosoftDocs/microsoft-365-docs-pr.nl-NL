---
title: Gebruikers individueel of in bulk toevoegen aan Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 1970f7d6-03b5-442f-b385-5880b9c256ec
description: 'Lees hoe u gebruikers kunt toevoegen aan Office 365, een voor een of meerdere gebruikers tegelijk vanuit een CSV-bestand. '
ms.openlocfilehash: 708bce2cb5a2c1b6a621bffc3ce56a2744bb518d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806686"
---
# <a name="add-users-individually-or-in-bulk-to-office-365"></a><span data-ttu-id="c7694-103">Gebruikers individueel of in bulk toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="c7694-103">Add users individually or in bulk to Office 365</span></span>

<span data-ttu-id="c7694-104">De personen in uw team hebben elk een gebruikersaccount nodig voordat ze zich kunnen aanmelden en toegang hebben tot [Office 365 voor Bedrijven](https://go.microsoft.com/fwlink/?LinkID=519395).</span><span class="sxs-lookup"><span data-stu-id="c7694-104">The people on your team each need a user account before they can sign in and access [Office 365 for business](https://go.microsoft.com/fwlink/?LinkID=519395).</span></span> <span data-ttu-id="c7694-105">De eenvoudigste manier om gebruikersaccounts toe te voegen, is om ze één voor één toe te voegen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c7694-105">The easiest way to add user accounts is to add them one at a time in the Microsoft 365 admin center.</span></span> <span data-ttu-id="c7694-106">Nadat u deze stap hebt uitgevoerd, hebben uw gebruikers Office 365-licenties, aanmeldingsreferenties en Office 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="c7694-106">After you do this step, your users will have Office 365 licenses, sign in credentials, and Office 365 mailboxes.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="c7694-107">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c7694-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="c7694-108">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="c7694-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="c7694-109">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c7694-109">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
3. <span data-ttu-id="c7694-110">Vul de volgende gegevens in het deelvenster **Basisinformatie instellen** in en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c7694-110">In the **Set up the basics** pane, fill in the following information, and then select **Next**.</span></span> 
  
- <span data-ttu-id="c7694-111">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="c7694-111">**Name** Fill in first, last, display name, and username.</span></span> 
    
- <span data-ttu-id="c7694-112">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Wander is en zijn domein contoso.com, dan zal hij zich aanmelden bij Office 365 met wander@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c7694-112">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="c7694-113">**Wachtwoordinstellingen** Kies ervoor om het automatisch gegenereerde wachtwoord te gebruiken of maak zelf een sterk wachtwoord voor de gebruiker aan.</span><span class="sxs-lookup"><span data-stu-id="c7694-113">**Password settings** Choose to the use auto-generated password or create your own strong password for the user.</span></span> 
    
    - <span data-ttu-id="c7694-114">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c7694-114">They'll need to change their password after 90 days.</span></span> <span data-ttu-id="c7694-115">U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="c7694-115">Or you can choose to **Require this user to change their password when they first sign in**.</span></span>
    
    - <span data-ttu-id="c7694-116">Kies of u het wachtwoord in een e-mail wilt verzenden wanneer de gebruiker is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c7694-116">Choose whether you want to  send the password in email when the user has been added.</span></span> 
    
4. <span data-ttu-id="c7694-117">Selecteer in het deelvenster **Productlicenties toewijzen** de locatie en de geschikte licentie voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c7694-117">In the **Assign product licenses** pane, select the location and the appropriate license for the user.</span></span> <span data-ttu-id="c7694-118">Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="c7694-118">If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> <span data-ttu-id="c7694-119">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="c7694-119">Select **Next**.</span></span>

5. <span data-ttu-id="c7694-120">Vouw op de pagina **Optionele instellingen** **Rollen** uit als u deze gebruiker een beheerder wilt maken en vouw **Profielgegevens** uit als u extra informatie over de gebruiker wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c7694-120">In the **Optional settings** page, expand **Roles** if you want to make this user an admin, and expand **Profile info** if you want to add additional information about the user.</span></span> 

6. <span data-ttu-id="c7694-121">Selecteer **Volgende**, controleer de instellingen van de nieuwe gebruiker, breng de gewenste wijzigingen aan en selecteer vervolgens **Toevoegen voltooid**.</span><span class="sxs-lookup"><span data-stu-id="c7694-121">Select **Next**, review your new user's settings, make any changes you like, and then select **Finish adding**.</span></span> 

::: moniker-end


::: moniker range="o365-germany"

1. <span data-ttu-id="c7694-122">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="c7694-122">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

2. <span data-ttu-id="c7694-123">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c7694-123">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="c7694-124">Vul de volgende gegevens in het deelvenster **Nieuwe gebruikers** in.</span><span class="sxs-lookup"><span data-stu-id="c7694-124">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c7694-125">Selecteer **Toevoegen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c7694-125">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="c7694-126">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="c7694-126">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="c7694-127">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Wander is en zijn domein contoso.com, dan zal hij zich aanmelden bij Office 365 met wander@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c7694-127">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="c7694-128">**Contactgegevens** Vouw deze sectie uit om een mobiel telefoonnummer, adres, enzovoort in te vullen.</span><span class="sxs-lookup"><span data-stu-id="c7694-128">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="c7694-129">**Wachtwoord** Gebruik het automatisch gegenereerde wachtwoord of vouw deze sectie uit om een sterk wachtwoord voor de gebruiker op te geven.</span><span class="sxs-lookup"><span data-stu-id="c7694-129">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="c7694-p105">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen. U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="c7694-p105">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="c7694-132">**Rollen** Vouw deze sectie uit als u van deze gebruiker een beheerder wilt maken.</span><span class="sxs-lookup"><span data-stu-id="c7694-132">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="c7694-p106">**Productlicenties** Vouw deze sectie uit en selecteer de juiste licentie. Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="c7694-p106">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c7694-135">Ga naar het beheercentrum via <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="c7694-135">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

2. <span data-ttu-id="c7694-136">Ga naar **Gebruikers** > **Actieve gebruikers** en selecteer **Gebruiker toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="c7694-136">Go to **Users** > **Active users**, and select **Add a user**.</span></span>
   
  
   <span data-ttu-id="c7694-137">Vul de volgende gegevens in het deelvenster **Nieuwe gebruikers** in.</span><span class="sxs-lookup"><span data-stu-id="c7694-137">In the **New user** pane, fill in the following information.</span></span> <span data-ttu-id="c7694-138">Selecteer **Toevoegen** wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c7694-138">Select **Add** when you are done.</span></span> 
  
- <span data-ttu-id="c7694-139">**Naam** Vul de voor- en achternaam, weergavenaam en gebruikersnaam in.</span><span class="sxs-lookup"><span data-stu-id="c7694-139">**Name** Fill in first, last, display name, and user name.</span></span> 
    
- <span data-ttu-id="c7694-140">**Domein** Als de gebruikersnaam van de gebruiker bijvoorbeeld Wander is en zijn domein contoso.com, dan zal hij zich aanmelden bij Office 365 met wander@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="c7694-140">**Domain** For example, if the user's username is Jakob, and his domain is contoso.com, he'll sign in to Office 365 by typing jakob@contoso.com.</span></span> 
    
- <span data-ttu-id="c7694-141">**Contactgegevens** Vouw deze sectie uit om een mobiel telefoonnummer, adres, enzovoort in te vullen.</span><span class="sxs-lookup"><span data-stu-id="c7694-141">**Contact information** Expand to fill in a mobile phone number, address, and so on.</span></span> 
    
- <span data-ttu-id="c7694-142">**Wachtwoord** Gebruik het automatisch gegenereerde wachtwoord of vouw deze sectie uit om een sterk wachtwoord voor de gebruiker op te geven.</span><span class="sxs-lookup"><span data-stu-id="c7694-142">**Password** Use the auto-generated password or expand to specify a strong password for the user.</span></span> 
    
    <span data-ttu-id="c7694-p108">Gebruikers moeten hun wachtwoord na 90 dagen wijzigen. U kunt ook de optie **Laat deze persoon zijn wachtwoord wijzigen bij de volgende aanmelding** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="c7694-p108">They'll need to change their password after 90 days. Or you can choose to **Make this user change their password when they first sign in**.</span></span>
    
- <span data-ttu-id="c7694-145">**Rollen** Vouw deze sectie uit als u van deze gebruiker een beheerder wilt maken.</span><span class="sxs-lookup"><span data-stu-id="c7694-145">**Roles** Expand if you need to make this user an admin.</span></span> 
    
- <span data-ttu-id="c7694-p109">**Productlicenties** Vouw deze sectie uit en selecteer de juiste licentie. Als u geen beschikbare licenties hebt, kunt u nog steeds een gebruiker toevoegen en extra licenties kopen.</span><span class="sxs-lookup"><span data-stu-id="c7694-p109">**Product licenses** Expand this section and select the appropriate license. If you don't have any licenses available, you can still add a user and buy additional licenses.</span></span> 

::: moniker-end 
  
<span data-ttu-id="c7694-148">Nadat u een gebruiker toevoegt, krijgt u een e-mailmelding van het team van Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="c7694-148">After you add a user, you'll get an email notification from the Microsoft Online Services Team.</span></span> <span data-ttu-id="c7694-149">Het e-mailbericht bevat de gebruikers-id en het wachtwoord van de persoon voor Office 365, zodat deze zich kan aanmelden bij Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7694-149">The email will contain the person's Office 365 user ID and password so they can sign in to Office 365.</span></span> <span data-ttu-id="c7694-150">U moet nieuwe gebruikers nog wel informeren over hun Office 365-aanmeldgegevens.</span><span class="sxs-lookup"><span data-stu-id="c7694-150">You need to tell your new user about their Office 365 sign in information.</span></span> <span data-ttu-id="c7694-151">Gebruik het gangbare proces voor het doorgeven van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="c7694-151">Use your normal process for communicating new passwords.</span></span>

> [!NOTE]
><span data-ttu-id="c7694-152">Als u gebruikers aanmaakt door postvakken te migreren, moet u Office 365-gebruikersaccounts activeren door licenties toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="c7694-152">If you create users by migrating mail boxes, you will need to activate Office 365 user accounts by assigning licenses.</span></span> <span data-ttu-id="c7694-153">Als u geen licentie toewijst aan een gebruiker, wordt het postvak uitgeschakeld na een respijtperiode van 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="c7694-153">If you don't assign a license to a user, their mailbox will be disabled after a grace period of 30 days.</span></span> <span data-ttu-id="c7694-154">Ontdek hoe u [licenties aan gebruikers kunt toewijzen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c7694-154">See how to [assign licenses to users](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) using the Microsoft 365 admin center.</span></span>

### <a name="video-add-and-manage-users-in-the-admin-center"></a><span data-ttu-id="c7694-155">Video: Gebruikers toevoegen en beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="c7694-155">Video: Add and manage users in the admin center</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]
  
## <a name="next-steps"></a><span data-ttu-id="c7694-156">Volgende stappen</span><span class="sxs-lookup"><span data-stu-id="c7694-156">Next steps</span></span>

<span data-ttu-id="c7694-157">Deel de handleiding [Aan de slag voor werknemers](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) met uw nieuwe gebruikers voor het instellen van dingen als [Office op een pc of Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) en [mobiele Office-apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span><span class="sxs-lookup"><span data-stu-id="c7694-157">Share the [Employee quick start guide](https://support.office.com/article/b9700090-ce64-4046-ab92-ce8488a7bc0f.aspx) with your new users to set things up, like [Office on a PC or Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx) and [Office mobile apps](https://support.office.com/article/7dabb6cb-0046-40b6-81fe-767e0b1f014f.aspx).</span></span>
  
## <a name="need-help"></a><span data-ttu-id="c7694-158">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="c7694-158">Need help?</span></span>

<span data-ttu-id="c7694-159">[Neem contact op met de ondersteuning van Office 365 voor Bedrijven](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="c7694-159">[Contact Office 365 for business support](../contact-support-for-business-products.md).</span></span>  

## <a name="have-hundreds-or-thousands-of-users-to-add"></a><span data-ttu-id="c7694-160">Wilt u honderden of duizenden gebruikers toevoegen?</span><span class="sxs-lookup"><span data-stu-id="c7694-160">Have hundreds or thousands of users to add?</span></span>


<span data-ttu-id="c7694-161">Volg deze stappen om meerdere gebruikers tegelijkertijd toe te voegen: </span><span class="sxs-lookup"><span data-stu-id="c7694-161">To add multiple users at the same time, follow these steps:</span></span>
  
- <span data-ttu-id="c7694-162">**Gebruik een spreadsheet om personen bulksgewijs toe te voegen.**</span><span class="sxs-lookup"><span data-stu-id="c7694-162">**Use a spreadsheet to add people in bulk.**</span></span> <span data-ttu-id="c7694-163">Zie [Meerdere gebruikers tegelijk toevoegen](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span><span class="sxs-lookup"><span data-stu-id="c7694-163">See [Add several users at the same time](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time).</span></span>
    
- <span data-ttu-id="c7694-164">**Automatiseer het toevoegen van accounts en het toewijzen van licenties.**</span><span class="sxs-lookup"><span data-stu-id="c7694-164">**Automate adding accounts and assigning licenses.**</span></span> <span data-ttu-id="c7694-165">Zie [Gebruikersaccounts maken met Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c7694-165">See [Create user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/create-user-accounts-with-office-365-powershell).</span></span> <span data-ttu-id="c7694-166">Kies deze methode als u al vertrouwd bent met het gebruik van Windows PowerShell-cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c7694-166">Choose this method if you're already familiar with using Windows PowerShell cmdlets.</span></span>
    
- <span data-ttu-id="c7694-167">**Gebruikt u ActiveDirectory?**</span><span class="sxs-lookup"><span data-stu-id="c7694-167">**Using ActiveDirectory?**</span></span> <span data-ttu-id="c7694-168">[Adreslijstsynchronisatie voor Office 365 instellen](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="c7694-168">[Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span> <span data-ttu-id="c7694-169">Gebruik het hulpprogramma Azure Active Directory Connect om Active Directory-gebruikersaccounts (en andere Active Directory-objecten) te repliceren in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c7694-169">Use the Azure AD Connect tool to replicate Active Directory user accounts (and other Active Directory objects) in Office 365.</span></span> <span data-ttu-id="c7694-170">Tijdens de synchronisatie worden alleen de gebruikersaccounts toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c7694-170">The sync only adds the user accounts.</span></span> <span data-ttu-id="c7694-171">U zult licenties moeten toewijzen aan de gesynchroniseerde gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7694-171">You will need to assign licenses to the synced users before they can use email and other Office apps.</span></span>
    
- <span data-ttu-id="c7694-172">**Migreert u vanuit Exchange?**</span><span class="sxs-lookup"><span data-stu-id="c7694-172">**Migrating from Exchange?**</span></span> <span data-ttu-id="c7694-173">[Manieren om meerdere e-mailaccounts naar Office 365 te migreren](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span><span class="sxs-lookup"><span data-stu-id="c7694-173">[Ways to migrate multiple email accounts to Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration).</span></span> <span data-ttu-id="c7694-174">Wanneer u meerdere postvakken naar Office 365 wilt migreren met behulp van een cutover-, gefaseerde of een hybride Exchange-methode, voegt u gebruikers automatisch als onderdeel van de migratie toe.</span><span class="sxs-lookup"><span data-stu-id="c7694-174">When you migrate multiple mailboxes to Office 365 by using either cutover, staged, or a hybrid Exchange method, you will add users automatically as part of the migration.</span></span> <span data-ttu-id="c7694-175">Tijdens de migratie worden alleen de gebruikersaccounts toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="c7694-175">The migration only adds the user accounts.</span></span> <span data-ttu-id="c7694-176">U moet licenties toewijzen aan de gebruikers voordat ze e-mail en andere Office-apps kunnen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c7694-176">You will need assign licenses to the users before they can use email and other Office apps.</span></span>

## <a name="related-articles"></a><span data-ttu-id="c7694-177">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="c7694-177">Related articles</span></span>

[<span data-ttu-id="c7694-178">Een nieuwe werknemer toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="c7694-178">Add a new employee to Office 365</span></span>](add-new-employee.md)

[<span data-ttu-id="c7694-179">Een gebruiker uit uw organisatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="c7694-179">Delete a user from your organization</span></span>](delete-a-user.md)

[<span data-ttu-id="c7694-180">Een gebruiker herstellen in Office 365</span><span class="sxs-lookup"><span data-stu-id="c7694-180">Restore a user in Office 365</span></span>](restore-user.md)

[<span data-ttu-id="c7694-181">Meerdere gebruikers tegelijk toevoegen aan Office 365</span><span class="sxs-lookup"><span data-stu-id="c7694-181">Add several users at the same time to Office 365</span></span>](https://docs.microsoft.com/office365/enterprise/add-several-users-at-the-same-time)


