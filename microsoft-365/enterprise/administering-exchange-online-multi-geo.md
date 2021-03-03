---
title: Exchange Online-postvakken beheren in een multige geo-omgeving
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Informatie over het beheren van multige geo-instellingen van Exchange Online in uw Microsoft 365-omgeving met PowerShell.
ms.openlocfilehash: 83889b4582d2e305b2cb9f07a64307e85d30be77
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406040"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="a4028-103">Exchange Online-postvakken beheren in een multige geo-omgeving</span><span class="sxs-lookup"><span data-stu-id="a4028-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="a4028-104">Exchange Online PowerShell is vereist voor het weergeven en configureren van meerdere geografische eigenschappen in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="a4028-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="a4028-105">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4028-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="a4028-106">U hebt de [Microsoft Azure Active Directory PowerShell-module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 of hoger in v1.x nodig om de eigenschap **PreferredDataLocation** op gebruikersobjecten te zien.</span><span class="sxs-lookup"><span data-stu-id="a4028-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="a4028-107">Gebruikersobjecten die via AAD Connect in AAD zijn gesynchroniseerd, kunnen hun **PreferredDataLocation-waarde** niet rechtstreeks wijzigen via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4028-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="a4028-108">Gebruikersobjecten in de cloud kunnen worden gewijzigd via AAD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4028-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="a4028-109">Zie Connect to PowerShell (Verbinding maken met PowerShell) als u verbinding wilt maken met Azure AD [PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a4028-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="a4028-110">In Exchange Online-omgevingen met meerdere geografische omgevingen hoeft u geen handmatige stappen uit te voeren om geo's toe te voegen aan uw tenant.</span><span class="sxs-lookup"><span data-stu-id="a4028-110">In Exchange Online multi-geo environments, you don't need to do any manual steps to add geos to your tenant.</span></span> <span data-ttu-id="a4028-111">Nadat u het bericht in het berichtencentrum hebt ontvangen dat multige geo gereed is voor Exchange Online, zijn alle beschikbare geo's gereed en geconfigureerd voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="a4028-111">After you receive the Message Center post that says multi-geo is ready for Exchange Online, all available geos will be ready and configured for you to use.</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="a4028-112">Rechtstreeks verbinding maken met een geografische locatie met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4028-112">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="a4028-113">Normaal gesproken maakt Exchange Online PowerShell verbinding met de centrale geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-113">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="a4028-114">Maar u kunt ook rechtstreeks verbinding maken met geografische satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="a4028-114">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="a4028-115">Vanwege prestatieverbeteringen is het raadzaam om rechtstreeks verbinding te maken met de geografische satellietlocatie als u alleen gebruikers op die locatie beheert.</span><span class="sxs-lookup"><span data-stu-id="a4028-115">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="a4028-116">De vereisten voor het installeren en gebruiken van de EXO V2-module worden beschreven in [de EXO V2-module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)installeren en onderhouden.</span><span class="sxs-lookup"><span data-stu-id="a4028-116">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="a4028-117">Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de *ConnectionUri-parameter* anders dan de normale verbindingsinstructies.</span><span class="sxs-lookup"><span data-stu-id="a4028-117">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="a4028-118">De rest van de opdrachten en waarden zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="a4028-118">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="a4028-119">U moet de waarde toevoegen aan het einde `?email=<emailaddress>` van de _ConnectionUri-waarde._</span><span class="sxs-lookup"><span data-stu-id="a4028-119">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="a4028-120">`<emailaddress>` is het e-mailadres van **een postvak** op de doellocatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-120">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="a4028-121">Uw machtigingen voor dat postvak of de relatie met uw referenties zijn geen factor. Met het e-mailadres wordt aan Exchange Online PowerShell alleen verteld waar verbinding moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a4028-121">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="a4028-122">Klanten van Microsoft 365 of Microsoft 365 GCC hoeven meestal de _ConnectionUri-parameter_ niet te gebruiken om verbinding te maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4028-122">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="a4028-123">Maar als u verbinding wilt maken met een specifieke geografische locatie, moet u de _ConnectionUri-parameter_ gebruiken zodat u deze in de waarde `?email=<emailaddress>` kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a4028-123">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="a4028-124">Verbinding maken met een geografische locatie in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4028-124">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="a4028-125">De volgende verbindingsinstructies werken voor accounts die al dan niet zijn geconfigureerd voor meervoudige verificatie (MFA).</span><span class="sxs-lookup"><span data-stu-id="a4028-125">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="a4028-126">Laad in een Windows PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a4028-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="a4028-127">In het volgende voorbeeld admin@contoso.onmicrosoft.com het beheerdersaccount en is de doellocatie de locatie olga@contoso.onmicrosoft.com postvak.</span><span class="sxs-lookup"><span data-stu-id="a4028-127">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="a4028-128">Voer het wachtwoord voor de admin@contoso.onmicrosoft.com in de prompt die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a4028-128">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="a4028-129">Als het account is geconfigureerd voor MFA, moet u ook de beveiligingscode invoeren.</span><span class="sxs-lookup"><span data-stu-id="a4028-129">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="a4028-130">De beschikbare geografische locaties bekijken die zijn geconfigureerd in uw Exchange Online-organisatie</span><span class="sxs-lookup"><span data-stu-id="a4028-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="a4028-131">Voer de volgende opdracht uit in Exchange Online PowerShell om de lijst met geconfigureerde geografische locaties in Microsoft 365 Multi-Geo weer te geven:</span><span class="sxs-lookup"><span data-stu-id="a4028-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="a4028-132">De centrale geografische locatie voor uw Exchange Online-organisatie weergeven</span><span class="sxs-lookup"><span data-stu-id="a4028-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="a4028-133">Voer de volgende opdracht uit in Exchange Online PowerShell om de centrale geografische locatie van uw tenant weer te geven:</span><span class="sxs-lookup"><span data-stu-id="a4028-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="a4028-134">De geografische locatie van een postvak zoeken</span><span class="sxs-lookup"><span data-stu-id="a4028-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="a4028-135">Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende multi geo-gerelateerde eigenschappen voor postvakken weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a4028-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="a4028-136">**Database:** de eerste drie letters van de databasenaam komen overeen met de geografische code, die u vertelt waar het postvak zich momenteel bevindt.</span><span class="sxs-lookup"><span data-stu-id="a4028-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="a4028-137">Voor onlinearchiefpostvakken moet de **eigenschap ArchiveDatabase** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a4028-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="a4028-138">**MailboxRegion:** geeft de geografische locatiecode aan die is ingesteld door de beheerder (gesynchroniseerd vanuit **PreferredDataLocation** in Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a4028-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="a4028-139">**MailboxRegionLastUpdateTime:** geeft aan wanneer MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).</span><span class="sxs-lookup"><span data-stu-id="a4028-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="a4028-140">Gebruik de volgende syntaxis om deze eigenschappen voor een postvak weer te geven:</span><span class="sxs-lookup"><span data-stu-id="a4028-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="a4028-141">Als u bijvoorbeeld de geografische locatiegegevens voor de postvakgegevens chris@contoso.onmicrosoft.com, moet u de volgende opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a4028-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="a4028-142">De uitvoer van de opdracht ziet er zo uit:</span><span class="sxs-lookup"><span data-stu-id="a4028-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="a4028-143">Als de geografische locatiecode in de databasenaam niet overeenkomen met de waarde voor **MailboxRegion,** wordt het postvak automatisch in een wachtrij geplaatst en verplaatst naar de geografische locatie die wordt opgegeven door de waarde voor **PostvakRegio** (Exchange Online zoekt naar een niet-overeenkomende waarde tussen deze eigenschapswaarden).</span><span class="sxs-lookup"><span data-stu-id="a4028-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="a4028-144">Een bestaand postvak in de cloud verplaatsen naar een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="a4028-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="a4028-145">Een gebruiker die alleen in de cloud werkt, is een gebruiker die niet wordt gesynchroniseerd met de tenant via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a4028-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="a4028-146">Deze gebruiker is rechtstreeks in Azure AD gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a4028-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="a4028-147">Gebruik de cmdlets **Get-MsolUser** en **Set-MsolUser** in de Azure AD-module voor Windows PowerShell om de geografische locatie weer te geven waar het postvak van een gebruiker die alleen in de cloud wordt opgeslagen, wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="a4028-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="a4028-148">Als u de **PreferredDataLocation-waarde voor** een gebruiker wilt bekijken, gebruikt u deze syntaxis in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a4028-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="a4028-149">Als u bijvoorbeeld de **waarde PreferredDataLocation** voor de michelle@contoso.onmicrosoft.com gebruiker wilt zien, moet u de volgende opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a4028-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="a4028-150">Gebruik de volgende syntaxis in Azure AD PowerShell om de **waarde PreferredDataLocation** te wijzigen voor een gebruikersobject in de cloud:</span><span class="sxs-lookup"><span data-stu-id="a4028-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a4028-151">Als u bijvoorbeeld de **waarde PreferredDataLocation** wilt instellen op de geografische waarde van de Europese Unie (EUR) voor de michelle@contoso.onmicrosoft.com gebruiker, moet u de volgende opdracht uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="a4028-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="a4028-152">Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten vanuit on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4028-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="a4028-153">U moet de waarde **van PreferredDataLocation** in Active Directory wijzigen en synchroniseren met AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="a4028-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="a4028-154">Zie Azure [Active Directory Connect-synchronisatie: Voorkeursgegevenslocatie configureren voor Microsoft 365-bronnen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="a4028-155">Hoe lang het duurt om een postvak een nieuwe geografische locatie te geven, hangt af van verschillende factoren:</span><span class="sxs-lookup"><span data-stu-id="a4028-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="a4028-156">De grootte en het type van het postvak.</span><span class="sxs-lookup"><span data-stu-id="a4028-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="a4028-157">Het aantal postvakken dat wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="a4028-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="a4028-158">De beschikbaarheid van resources verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="a4028-158">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="a4028-159">Een inactief postvak verplaatsen naar een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="a4028-159">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="a4028-160">U kunt inactieve postvakken die blijven behouden voor nalevingsdoeleinden (bijvoorbeeld postvakken bij het bewaren van postvakken met een juridische procedure) niet verplaatsen door de **PreferredDataLocation-waarde te** wijzigen.</span><span class="sxs-lookup"><span data-stu-id="a4028-160">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="a4028-161">Als u een inactief postvak wilt verplaatsen naar een ander geografisch gebied, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="a4028-161">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="a4028-162">Herstel het inactieve postvak.</span><span class="sxs-lookup"><span data-stu-id="a4028-162">Recover the inactive mailbox.</span></span> <span data-ttu-id="a4028-163">Zie Een [inactief postvak herstellen voor instructies.](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)</span><span class="sxs-lookup"><span data-stu-id="a4028-163">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="a4028-164">Voorkom dat beheerde mapassistent het herstelde postvak verwerkt door het te vervangen door de naam, alias, het account of het e-mailadres van het postvak en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a4028-164">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="a4028-165">Wijs een **licentie voor Exchange Online Abonnement 2** toe aan het herstelde postvak.</span><span class="sxs-lookup"><span data-stu-id="a4028-165">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="a4028-166">Deze stap is vereist om het postvak weer in de wacht te zetten bij juridische procedure.</span><span class="sxs-lookup"><span data-stu-id="a4028-166">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="a4028-167">Zie Licenties toewijzen [aan gebruikers voor instructies.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="a4028-167">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="a4028-168">Configureer de **PreferredDataLocation-waarde** voor het postvak, zoals beschreven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="a4028-168">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="a4028-169">Nadat u hebt bevestigd dat het postvak is verplaatst naar de nieuwe geografische locatie, zet u het herstelde postvak weer in de postvak in de juridische procedure.</span><span class="sxs-lookup"><span data-stu-id="a4028-169">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="a4028-170">Zie Postvak in de wacht zetten [voor juridische procedures voor instructies.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)</span><span class="sxs-lookup"><span data-stu-id="a4028-170">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="a4028-171">Nadat u hebt gecontroleerd of de Postvak IN van postvakgegevens is geplaatst, laat u de Beheerde mapassistent het postvak opnieuw verwerken door het postvak te vervangen door de naam, alias, het account of het e-mailadres van het postvak en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="a4028-171">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="a4028-172">Maak het postvak opnieuw inactief door het gebruikersaccount te verwijderen dat aan het postvak is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="a4028-172">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="a4028-173">Zie Een gebruiker [uit uw organisatie verwijderen voor instructies.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="a4028-173">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="a4028-174">Met deze stap wordt ook de licentie voor Exchange Online (Abonnement 2) voor ander gebruik uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="a4028-174">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="a4028-175">**Opmerking:** wanneer u een inactief postvak naar een andere geografische locatie verplaatst, kan dit van invloed zijn op zoekresultaten voor inhoud of de mogelijkheid om in het postvak te zoeken vanaf de voormalige geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-175">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="a4028-176">Zie Zoeken en exporteren [van inhoud in Multi-Geo-omgevingen](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-176">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a4028-177">Nieuwe postvakken in de cloud maken op een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="a4028-177">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="a4028-178">Als u een nieuw postvak wilt maken op een specifieke geografische locatie, moet u een van de volgende stappen volgen:</span><span class="sxs-lookup"><span data-stu-id="a4028-178">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="a4028-179">Configureer de **waarde PreferredDataLocation** zoals is beschreven in de vorige  sectie Een bestaand [postvak](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) in de cloud verplaatsen naar een specifieke geografische locatie voordat u het postvak in Exchange Online maakt.</span><span class="sxs-lookup"><span data-stu-id="a4028-179">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="a4028-180">Configureer bijvoorbeeld de **waarde PreferredDataLocation** voor een gebruiker voordat u een licentie toewijst.</span><span class="sxs-lookup"><span data-stu-id="a4028-180">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="a4028-181">Wijs een licentie toe op het moment dat u de **waarde van PreferredDataLocation in** stelt.</span><span class="sxs-lookup"><span data-stu-id="a4028-181">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="a4028-182">Als u een nieuwe gebruiker met een cloudlicentie wilt maken (niet gesynchroniseerd met AAD Connect) op een specifieke geografische locatie, gebruikt u de volgende syntaxis in Azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a4028-182">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="a4028-183">In dit voorbeeld wordt een nieuw gebruikersaccount voor Elizabeth Bwaarden aangemaakt met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="a4028-183">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="a4028-184">User principal name: ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a4028-184">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="a4028-185">Voornaam: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="a4028-185">First name: Elizabeth</span></span>
- <span data-ttu-id="a4028-186">Achternaam: B goed</span><span class="sxs-lookup"><span data-stu-id="a4028-186">Last name: Brunner</span></span>
- <span data-ttu-id="a4028-187">Weergavenaam: Elizabeth Bweergave</span><span class="sxs-lookup"><span data-stu-id="a4028-187">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="a4028-188">Wachtwoord: willekeurig gegenereerd en weergegeven in de resultaten van de opdracht (omdat we de parameter *Password niet* gebruiken)</span><span class="sxs-lookup"><span data-stu-id="a4028-188">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="a4028-189">Licentie: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="a4028-189">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="a4028-190">Locatie: Australië (Australië)</span><span class="sxs-lookup"><span data-stu-id="a4028-190">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="a4028-191">Zie Gebruikersaccounts maken met [PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en licenties en services weergeven met PowerShell voor meer informatie over het maken van nieuwe gebruikersaccounts en het zoeken naar de waarden voor LicenseAssignment in Azure AD [PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="a4028-191">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a4028-192">Als u Exchange Online PowerShell gebruikt om een postvak in teschakelen en u het postvak rechtstreeks wilt maken op de geografische locatie die is opgegeven in **PreferredDataLocation,** moet u een Exchange Online-cmdlet zoals **Enable-Mailbox** of **New-Mailbox** rechtstreeks gebruiken voor de cloudservice.</span><span class="sxs-lookup"><span data-stu-id="a4028-192">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="a4028-193">Als u de cmdlet **Enable-RemoteMailbox** gebruikt in on-premises Exchange PowerShell, wordt het postvak gemaakt op de centrale geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-193">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="a4028-194">Bestaande on-premises postvakken in een specifieke geografische locatie onboarden</span><span class="sxs-lookup"><span data-stu-id="a4028-194">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="a4028-195">U kunt de standaard-onboarding-hulpprogramma's en -processen gebruiken om een postvak te migreren van een on-premises Exchange-organisatie naar Exchange Online, inclusief het migratiedashboard in het Exchange-exchange-programma en de cmdlet [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) in Exchange Online PowerShell. [](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)</span><span class="sxs-lookup"><span data-stu-id="a4028-195">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="a4028-196">De eerste stap bestaat uit het controleren van een gebruikersobject voor elk postvak dat moet worden onboarded en controleren of de juiste **PreferredDataLocation-waarde** is geconfigureerd in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4028-196">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="a4028-197">De onboarding-hulpprogramma's houden zich aan de **waarde preferredDataLocation** en migreren de postvakken rechtstreeks naar de opgegeven geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-197">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="a4028-198">U kunt ook de volgende stappen gebruiken om postvakken rechtstreeks in een specifieke geografische locatie in te voeren met de cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4028-198">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="a4028-199">Controleer of het gebruikersobject bestaat voor elk postvak dat moet worden onboarded en of **PreferredDataLocation** is ingesteld op de gewenste waarde in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4028-199">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="a4028-200">De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het kenmerk **MailboxRegion** van het bijbehorende e-mailgebruikersobject in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="a4028-200">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="a4028-201">Maak rechtstreeks verbinding met de specifieke geografische satellietlocatie aan de hand van de verbindingsinstructies eerder in dit onderwerp.</span><span class="sxs-lookup"><span data-stu-id="a4028-201">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="a4028-202">Sla in Exchange Online PowerShell de lokale beheerdersreferenties op die worden gebruikt voor het uitvoeren van een postvakmigratie in een variabele door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="a4028-202">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="a4028-203">Maak in Exchange Online PowerShell een nieuwe **New-MoveRequest** zoals in het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="a4028-203">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="a4028-204">Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische satellietlocatie die u momenteel hebt verbonden.</span><span class="sxs-lookup"><span data-stu-id="a4028-204">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="a4028-205">Als u extra postvakken wilt migreren naar verschillende geografische satellietlocaties, herhaalt u stap 2 tot en met 4 voor elke specifieke locatie.</span><span class="sxs-lookup"><span data-stu-id="a4028-205">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="a4028-206">Multi-geo reporting</span><span class="sxs-lookup"><span data-stu-id="a4028-206">Multi-geo reporting</span></span>

<span data-ttu-id="a4028-207">**Rapporten over multige geoverbruik** in het Microsoft 365-beheercentrum geven het aantal gebruikers per geografische locatie weer.</span><span class="sxs-lookup"><span data-stu-id="a4028-207">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="a4028-208">In het rapport wordt de gebruikersdistributie voor de huidige maand weergegeven en worden historische gegevens voor de afgelopen zes maanden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a4028-208">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4028-209">Zie ook</span><span class="sxs-lookup"><span data-stu-id="a4028-209">See also</span></span>

[<span data-ttu-id="a4028-210">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="a4028-210">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
