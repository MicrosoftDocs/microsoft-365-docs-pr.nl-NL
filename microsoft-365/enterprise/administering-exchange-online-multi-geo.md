---
title: Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren
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
description: Meer informatie over het beheren van multi-geografische instellingen van Exchange Online in uw Microsoft 365-omgeving met PowerShell.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552005"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="3f65e-103">Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="3f65e-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="3f65e-104">Exchange Online PowerShell is vereist voor het weergeven en configureren van meervoudige geo-eigenschappen in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="3f65e-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="3f65e-105">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f65e-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="3f65e-106">U hebt [Microsoft Azure Active Directory PowerShell module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 of hoger nodig in v1. x om de eigenschap **PreferredDataLocation** voor gebruikersobjecten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3f65e-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="3f65e-107">Gebruikersobjecten die zijn gesynchroniseerd via AAD Connect in AAD, kunnen hun **PreferredDataLocation** -waarde niet rechtstreeks wijzigen via Aad PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f65e-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="3f65e-108">Gebruikersobjecten in de Cloud kunnen met behulp van AAD PowerShell worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="3f65e-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="3f65e-109">Als u verbinding wilt maken met Azure AD PowerShell, raadpleegt [u verbinding maken met PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3f65e-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="3f65e-110">Direct verbinding maken met een geo-locatie met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f65e-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="3f65e-111">Meestal maakt Exchange Online PowerShell verbinding met de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="3f65e-112">Maar u kunt ook rechtstreeks verbinding maken met satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="3f65e-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="3f65e-113">Vanwege prestatieverbeteringen wordt u aangeraden direct verbinding te maken met de geografische locatie van de satelliet wanneer u alleen gebruikers op die locatie beheert.</span><span class="sxs-lookup"><span data-stu-id="3f65e-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="3f65e-114">De vereisten voor het installeren en gebruiken van de module EXO v2 worden beschreven in [de Exo V2-module installeren en onderhouden](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="3f65e-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="3f65e-115">Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de parameter *ConnectionUri* niet gelijk aan de reguliere verbindings instructies.</span><span class="sxs-lookup"><span data-stu-id="3f65e-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="3f65e-116">De rest van de opdrachten en waarden zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="3f65e-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="3f65e-117">U moet de waarde specifiek toevoegen `?email=<emailaddress>` aan het einde van de _ConnectionUri_ -waarde.</span><span class="sxs-lookup"><span data-stu-id="3f65e-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="3f65e-118">`<emailaddress>` het e-mailadres van **een** postvak in de geografische doellocatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="3f65e-119">Uw machtigingen voor dit postvak of de relatie met uw referenties zijn geen factor. het e-mailadres vertelt Exchange Online PowerShell waar verbinding moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="3f65e-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="3f65e-120">Voor klanten met Microsoft 365 of Microsoft 365 GCC, hoeft u de _ConnectionUri_ -parameter meestal niet te gebruiken om verbinding te maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f65e-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="3f65e-121">Als u verbinding wilt maken met een specifieke geografische locatie, moet u _ConnectionUri_ -parameter gebruiken, zodat u `?email=<emailaddress>` deze kunt gebruiken in de waarde.</span><span class="sxs-lookup"><span data-stu-id="3f65e-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a><span data-ttu-id="3f65e-122">Verbinding maken met een geografische locatie in Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f65e-122">Connect to a geo location in Exchange Online PowerShell</span></span>

<span data-ttu-id="3f65e-123">De volgende verbindings instructies werken voor accounts die niet zijn geconfigureerd voor multi-factor Authentication (MFA).</span><span class="sxs-lookup"><span data-stu-id="3f65e-123">The following connection instructions work for accounts that are or aren't configured for multi-factor authentication (MFA).</span></span>

1. <span data-ttu-id="3f65e-124">Laad in een Windows PowerShell-venster de module EXO V2 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="3f65e-124">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="3f65e-125">In het volgende voorbeeld is admin@contoso.onmicrosoft.com het beheerdersaccount en is de geografische locatie van de doellocatie de plaats waar het postvak olga@contoso.onmicrosoft.com zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="3f65e-125">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. <span data-ttu-id="3f65e-126">Voer het wachtwoord in voor de admin@contoso.onmicrosoft.com in de prompt die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3f65e-126">Enter the password for the admin@contoso.onmicrosoft.com in the prompt that appears.</span></span> <span data-ttu-id="3f65e-127">Als het account is geconfigureerd voor MFA, moet u ook de beveiligingscode invoeren.</span><span class="sxs-lookup"><span data-stu-id="3f65e-127">If the account is configured for MFA, you also need to enter the security code.</span></span>

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="3f65e-128">De beschikbare geo-locaties weergeven die zijn geconfigureerd in uw Exchange Online-organisatie</span><span class="sxs-lookup"><span data-stu-id="3f65e-128">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="3f65e-129">Voer de volgende opdracht uit in PowerShell van Exchange Online voor een overzicht van de geconfigureerde geografische locaties in Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="3f65e-129">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="3f65e-130">De centrale geo-locatie voor uw Exchange Online-organisatie weergeven</span><span class="sxs-lookup"><span data-stu-id="3f65e-130">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="3f65e-131">Voer de volgende opdracht uit in Exchange Online PowerShell als u de centrale geografische locatie van de Tenant wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="3f65e-131">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="3f65e-132">De geografische locatie van een postvak zoeken</span><span class="sxs-lookup"><span data-stu-id="3f65e-132">Find the geo location of a mailbox</span></span>

<span data-ttu-id="3f65e-133">Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende eigenschappen met betrekking tot multi-geografische eigenschappen weergegeven voor postvakken:</span><span class="sxs-lookup"><span data-stu-id="3f65e-133">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="3f65e-134">**Database**: de eerste drie letters van de database naam komen overeen met de geografische code, waarmee wordt aangegeven waar het postvak zich momenteel bevindt.</span><span class="sxs-lookup"><span data-stu-id="3f65e-134">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="3f65e-135">Voor online archief postvakken moet de eigenschap **ArchiveDatabase** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3f65e-135">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="3f65e-136">**MailboxRegion**: geeft de geografische locatie code aan die door de beheerder is ingesteld (gesynchroniseerd van **PREFERREDDATALOCATION** in azure AD).</span><span class="sxs-lookup"><span data-stu-id="3f65e-136">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="3f65e-137">**MailboxRegionLastUpdateTime**: geeft aan wanneer de MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).</span><span class="sxs-lookup"><span data-stu-id="3f65e-137">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="3f65e-138">Gebruik de volgende syntaxis om de eigenschappen van een postvak te bekijken:</span><span class="sxs-lookup"><span data-stu-id="3f65e-138">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="3f65e-139">Voer de volgende opdracht uit als u de gegevens van de geografische locatie voor de Postvak chris@contoso.onmicrosoft.com wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="3f65e-139">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="3f65e-140">De uitvoer van de opdracht ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="3f65e-140">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="3f65e-141">Als de geo-vestigingcode in de databasenaam niet overeenkomt met de waarde van **MailboxRegion** , wordt het postvak automatisch toegevoegd aan een wachtrij voor hernoemen en wordt verplaatst naar de geo-locatie die is opgegeven via de **MailboxRegion** -waarde (Exchange Online zoekt de waarden van deze eigenschap niet.</span><span class="sxs-lookup"><span data-stu-id="3f65e-141">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="3f65e-142">Een bestaand postvak met alleen de Cloud naar een specifieke geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3f65e-142">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="3f65e-143">Een gebruiker met Cloud is een gebruiker die niet is gesynchroniseerd met de Tenant via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="3f65e-143">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="3f65e-144">Deze gebruiker is rechtstreeks gemaakt in azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f65e-144">This user was created directly in Azure AD.</span></span> <span data-ttu-id="3f65e-145">Met de cmdlet **Get-MsolUser** en **set-MsolUser** in de Azure ad-module voor Windows PowerShell kunt u de geografische locatie weergeven of opgeven waarop het postvak van de gebruikers van de Cloud wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="3f65e-145">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="3f65e-146">Als u de **PreferredDataLocation** waarde voor een gebruiker wilt bekijken, gebruikt u deze syntaxis in azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="3f65e-146">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="3f65e-147">Voer de volgende opdracht uit als u de **PreferredDataLocation** waarde voor het gebruikers Michelle@contoso.onmicrosoft.com wilt bekijken:</span><span class="sxs-lookup"><span data-stu-id="3f65e-147">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="3f65e-148">Gebruik de volgende syntaxis in azure AD PowerShell om de **PreferredDataLocation** -waarde voor een gebruikersobject in de cloud te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="3f65e-148">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="3f65e-149">Voer de volgende opdracht uit om de **PreferredDataLocation** waarde in te stellen op de Europese Unie (USD) Geo voor de gebruikers Michelle@contoso.onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="3f65e-149">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="3f65e-150">Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten uit on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f65e-150">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="3f65e-151">U moet de **PreferredDataLocation** waarde in Active Directory wijzigen en synchroniseren met behulp van Aad Connect.</span><span class="sxs-lookup"><span data-stu-id="3f65e-151">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="3f65e-152">Zie voor meer informatie [Azure Active Directory Connect Sync: voorkeur gegevenslocatie voor Microsoft 365-bronnen configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="3f65e-152">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="3f65e-153">Hoe lang het duurt om een postvak te verplaatsen naar een nieuwe geografische locatie, is afhankelijk van verschillende factoren:</span><span class="sxs-lookup"><span data-stu-id="3f65e-153">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="3f65e-154">De grootte en het type van het postvak.</span><span class="sxs-lookup"><span data-stu-id="3f65e-154">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="3f65e-155">Het aantal postvakken dat wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="3f65e-155">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="3f65e-156">De beschikbaarheid van bronnen voor verhuizing.</span><span class="sxs-lookup"><span data-stu-id="3f65e-156">The availability of move resources.</span></span>

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a><span data-ttu-id="3f65e-157">Een inactief postvak naar een specifieke geo verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3f65e-157">Move an inactive mailbox to a specific geo</span></span>

<span data-ttu-id="3f65e-158">Het is niet mogelijk om niet-actieve postvakken te verplaatsen die worden bewaard voor nalevings functies (bijvoorbeeld postvakken op de aangifte voor de geschil) door hun **PreferredDataLocation** waarde te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="3f65e-158">You can't move inactive mailboxes that are preserved for compliance purposes (for example, mailboxes on Litigation Hold) by changing their **PreferredDataLocation** value.</span></span> <span data-ttu-id="3f65e-159">Voer de volgende stappen uit om een inactief postvak naar een andere geografische plaats te verplaatsen:</span><span class="sxs-lookup"><span data-stu-id="3f65e-159">To move an inactive mailbox to a different geo, do the following steps:</span></span>

1. <span data-ttu-id="3f65e-160">Herstel het inactief postvak.</span><span class="sxs-lookup"><span data-stu-id="3f65e-160">Recover the inactive mailbox.</span></span> <span data-ttu-id="3f65e-161">Zie [een inactief postvak herstellen](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3f65e-161">For instructions, see [Recover an inactive mailbox](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox).</span></span>

2. <span data-ttu-id="3f65e-162">Voorkomen dat de assistent voor beheerde mappen het herstelde postvak verwerkt door te vervangen door \<MailboxIdentity\> de naam, alias, account of het e-mailadres van het postvak en de volgende opdracht uit te voeren in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="3f65e-162">Prevent the Managed Folder Assistant from processing the recovered mailbox by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. <span data-ttu-id="3f65e-163">Wijs een licentie voor **Exchange Online plan 2** toe aan het hersteld postvak.</span><span class="sxs-lookup"><span data-stu-id="3f65e-163">Assign an **Exchange Online Plan 2** license to the recovered mailbox.</span></span> <span data-ttu-id="3f65e-164">Deze stap is vereist voor het terugplaatsen van het postvak op het in de wachtstand van een zaak.</span><span class="sxs-lookup"><span data-stu-id="3f65e-164">This step is required to place the mailbox back on Litigation Hold.</span></span> <span data-ttu-id="3f65e-165">Zie [licenties toewijzen aan gebruikers](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3f65e-165">For instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

4. <span data-ttu-id="3f65e-166">Configureer de **PreferredDataLocation** -waarde in het postvak, zoals beschreven in de vorige sectie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-166">Configure the **PreferredDataLocation** value on the mailbox as described in the previous section.</span></span>

5. <span data-ttu-id="3f65e-167">Nadat u hebt bevestigd dat het postvak naar de nieuwe geografische locatie is verplaatst, plaatst u het herstelde postvak weer op de plaats van het betreffende geschil.</span><span class="sxs-lookup"><span data-stu-id="3f65e-167">After you've confirmed that the mailbox has moved to the new geo location, place the recovered mailbox back on Litigation Hold.</span></span> <span data-ttu-id="3f65e-168">Zie voor instructies [een postvak in plaats van de rechtszaken](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span><span class="sxs-lookup"><span data-stu-id="3f65e-168">For instructions, see [Place a mailbox on Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).</span></span>

6. <span data-ttu-id="3f65e-169">Nadat u hebt gecontroleerd of het bericht over de bewaring is ingevoerd, kunt u de Managed folder-assistent opnieuw uitvoeren door de \<MailboxIdentity\> naam, alias, account of het e-mailadres van het postvak te vervangen door de volgende opdracht uit te voeren in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span><span class="sxs-lookup"><span data-stu-id="3f65e-169">After verifying that the Litigation Hold is in place, allow the Managed Folder Assistant to process the mailbox again by replacing \<MailboxIdentity\> with the name, alias, account, or email address of the mailbox and running the following command in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. <span data-ttu-id="3f65e-170">Maak het postvak opnieuw inactief door het gebruikersaccount dat is gekoppeld aan het postvak te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3f65e-170">Make the mailbox inactive again by removing the user account that's associated with the mailbox.</span></span> <span data-ttu-id="3f65e-171">Zie [een gebruiker van uw organisatie verwijderen](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="3f65e-171">For instructions, see [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span></span> <span data-ttu-id="3f65e-172">In deze stap wordt ook de licentie voor Exchange Online plan 2 vrijgegeven voor andere gebruiksdoeleinden.</span><span class="sxs-lookup"><span data-stu-id="3f65e-172">This step also releases the Exchange Online Plan 2 license for other uses.</span></span>

<span data-ttu-id="3f65e-173">**Opmerking**: wanneer u een inactief postvak naar een andere geografische locatie verplaatst, kan dit gevolgen hebben voor de zoekresultaten van inhoud of de mogelijkheid om te zoeken in het postvak van de voormalige geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-173">**Note**: When you move an inactive mailbox to a different geo location, you might affect content search results or the ability to search the mailbox from the former geo location.</span></span> <span data-ttu-id="3f65e-174">Zie [inhoud zoeken en exporteren in meerdere geo-omgevingen](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-174">For more information, see [Searching and exporting content in Multi-Geo environments](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments).</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="3f65e-175">Nieuwe Cloud postvakken maken op een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="3f65e-175">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="3f65e-176">Voer een van de volgende stappen uit als u een nieuw postvak op een specifieke geografische locatie wilt maken:</span><span class="sxs-lookup"><span data-stu-id="3f65e-176">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="3f65e-177">Configureer de **PreferredDataLocation** waarde zoals beschreven in het vorige [postvak van een bestaande Cloud naar een specifieke geo-locatie](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) sectie verplaatsen *voordat* u het postvak maakt in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3f65e-177">Configure the **PreferredDataLocation** value as described in the previous [Move an existing cloud-only mailbox to a specific geo location](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) section *before* you create the mailbox in Exchange Online.</span></span> <span data-ttu-id="3f65e-178">U kunt bijvoorbeeld de **PreferredDataLocation** -waarde configureren voor een gebruiker voordat u een licentie toewijst.</span><span class="sxs-lookup"><span data-stu-id="3f65e-178">For example, configure the **PreferredDataLocation** value on a user before you assign a license.</span></span>

- <span data-ttu-id="3f65e-179">Wijs tegelijkertijd een licentie toe aan de **PreferredDataLocation** -waarde.</span><span class="sxs-lookup"><span data-stu-id="3f65e-179">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="3f65e-180">Gebruik de volgende syntaxis in azure AD PowerShell voor het maken van een nieuwe, in de Cloud gerichte gebruiker (niet AAD Connected) op een specifieke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-180">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="3f65e-181">In dit voorbeeld wordt een nieuwe gebruikersaccount gemaakt voor Elizabeth Brunner met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="3f65e-181">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="3f65e-182">UPN (User Principal Name): ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3f65e-182">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="3f65e-183">Voornaam: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="3f65e-183">First name: Elizabeth</span></span>
- <span data-ttu-id="3f65e-184">Achternaam: Brunner</span><span class="sxs-lookup"><span data-stu-id="3f65e-184">Last name: Brunner</span></span>
- <span data-ttu-id="3f65e-185">Weergavenaam: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="3f65e-185">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="3f65e-186">Wachtwoord: willekeurig gegenereerd en wordt weergegeven in de resultaten van de opdracht (omdat we de *wachtwoord* parameters niet gebruiken)</span><span class="sxs-lookup"><span data-stu-id="3f65e-186">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="3f65e-187">Licentie: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="3f65e-187">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="3f65e-188">Locatie: Australië (AUS)</span><span class="sxs-lookup"><span data-stu-id="3f65e-188">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="3f65e-189">Als u meer wilt weten over het maken van nieuwe gebruikersaccounts en het vinden van LicenseAssignment-waarden in azure AD PowerShell, raadpleegt u [gebruikersaccounts maken met PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en [licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3f65e-189">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3f65e-190">Als u Exchange Online PowerShell gebruikt om een postvak in te schakelen en het postvak rechtstreeks moet maken op de geografische locatie die in **PreferredDataLocation** is opgegeven, moet u een cmdlet van Exchange Online gebruiken, zoals **inschakelen-postvak** of **Nieuw-postvak** rechtstreeks op de Cloud-service.</span><span class="sxs-lookup"><span data-stu-id="3f65e-190">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="3f65e-191">Als u de **Enable-RemoteMailbox-** cmdlet in on-premises Exchange PowerShell gebruikt, wordt het postvak gemaakt in de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-191">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="3f65e-192">Bestaande on-premises postvakken in een specifieke geografische locatie opvullen</span><span class="sxs-lookup"><span data-stu-id="3f65e-192">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="3f65e-193">U kunt de standaardhulpprogramma's en [-](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) processen voor onboarding gebruiken voor het migreren van een postvak vanuit een on-premises Exchange-organisatie naar Exchange Online, inclusief het [migratie dashboard in het](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f65e-193">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="3f65e-194">De eerste stap bestaat uit het controleren van een gebruikersobject, en de juiste **PreferredDataLocation** waarde is geconfigureerd in azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f65e-194">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="3f65e-195">Met de hulpmiddelen voor onboarding wordt de **PreferredDataLocation** waarde bepaald en worden de postvakken direct naar de opgegeven geografische locatie gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="3f65e-195">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="3f65e-196">U kunt ook de volgende stappen uitvoeren om postvakken rechtstreeks op te zetten op een specifieke geo-locatie met behulp van de [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) -cmdlet in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3f65e-196">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="3f65e-197">Controleer of het gebruikersobject bestaat voor elk postvak en dat **PreferredDataLocation** is ingesteld op de gewenste waarde in azure AD.</span><span class="sxs-lookup"><span data-stu-id="3f65e-197">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="3f65e-198">De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het **MailboxRegion** -kenmerk van het bijbehorende e-mail gebruikersobject in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3f65e-198">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="3f65e-199">Verbind rechtstreeks met de specifieke geografische locatie van de satelliet met de verbindings instructies van eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="3f65e-199">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="3f65e-200">In Exchange Online PowerShell slaat u de on-premises beheerdersreferenties op die wordt gebruikt om een migratie van een postvak in een variabele uit te voeren door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="3f65e-200">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="3f65e-201">Maak in Exchange Online PowerShell een nieuwe **nieuwe MoveRequest** die vergelijkbaar is met het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3f65e-201">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="3f65e-202">Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische locatie van de satelliet waarmee u momenteel bent verbonden.</span><span class="sxs-lookup"><span data-stu-id="3f65e-202">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="3f65e-203">Als u extra postvakken moet migreren naar verschillende geografische locaties, herhaalt u stappen 2 tot en met 4 voor elke specifieke locatie.</span><span class="sxs-lookup"><span data-stu-id="3f65e-203">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="3f65e-204">Meerdere geografische rapporten</span><span class="sxs-lookup"><span data-stu-id="3f65e-204">Multi-geo reporting</span></span>

<span data-ttu-id="3f65e-205">Met de **rapporten voor meerdere geografische gebruik** in het microsoft 365-Beheercentrum wordt het aantal gebruikers per geo-locatie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="3f65e-205">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="3f65e-206">In het rapport wordt de distributie van gebruikers weergegeven voor de huidige maand en de historische gegevens voor de afgelopen zes maanden.</span><span class="sxs-lookup"><span data-stu-id="3f65e-206">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="3f65e-207">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3f65e-207">See also</span></span>

[<span data-ttu-id="3f65e-208">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f65e-208">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
