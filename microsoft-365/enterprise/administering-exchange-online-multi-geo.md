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
ms.openlocfilehash: ea7090cd65634138f9677960beab7770825a6e86
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950674"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="20e4f-103">Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="20e4f-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="20e4f-104">Exchange Online PowerShell is vereist voor het weergeven en configureren van meervoudige geo-eigenschappen in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="20e4f-104">Exchange Online PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="20e4f-105">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e4f-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="20e4f-106">U hebt [Microsoft Azure Active Directory PowerShell module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 of hoger nodig in v1. x om de eigenschap **PreferredDataLocation** voor gebruikersobjecten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="20e4f-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="20e4f-107">Gebruikersobjecten die zijn gesynchroniseerd via AAD Connect in AAD, kunnen hun **PreferredDataLocation** -waarde niet rechtstreeks wijzigen via Aad PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e4f-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="20e4f-108">Gebruikersobjecten in de Cloud kunnen met behulp van AAD PowerShell worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="20e4f-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="20e4f-109">Als u verbinding wilt maken met Azure AD PowerShell, raadpleegt [u verbinding maken met PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="20e4f-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="20e4f-110">Direct verbinding maken met een geo-locatie met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="20e4f-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="20e4f-111">Meestal maakt Exchange Online PowerShell verbinding met de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="20e4f-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="20e4f-112">Maar u kunt ook rechtstreeks verbinding maken met satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="20e4f-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="20e4f-113">Vanwege prestatieverbeteringen wordt u aangeraden direct verbinding te maken met de geografische locatie van de satelliet wanneer u alleen gebruikers op die locatie beheert.</span><span class="sxs-lookup"><span data-stu-id="20e4f-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="20e4f-114">De vereisten voor het installeren en gebruiken van de module EXO v2 worden beschreven in [de Exo V2-module installeren en onderhouden](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span><span class="sxs-lookup"><span data-stu-id="20e4f-114">The requirements for installing and using the EXO V2 module are described in [Install and maintain the EXO V2 module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).</span></span>

<span data-ttu-id="20e4f-115">Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de parameter *ConnectionUri* niet gelijk aan de reguliere verbindings instructies.</span><span class="sxs-lookup"><span data-stu-id="20e4f-115">To connect Exchange Online PowerShell to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="20e4f-116">De rest van de opdrachten en waarden zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="20e4f-116">The rest of the commands and values are the same.</span></span>

<span data-ttu-id="20e4f-117">U moet de waarde specifiek toevoegen `?email=<emailaddress>` aan het einde van de _ConnectionUri_ -waarde.</span><span class="sxs-lookup"><span data-stu-id="20e4f-117">Specifically, you need to add the `?email=<emailaddress>` value to end of the _ConnectionUri_ value.</span></span> <span data-ttu-id="20e4f-118">`<emailaddress>` het e-mailadres van **een** postvak in de geografische doellocatie.</span><span class="sxs-lookup"><span data-stu-id="20e4f-118">`<emailaddress>` is the email address of **any** mailbox in the target geo location.</span></span> <span data-ttu-id="20e4f-119">Uw machtigingen voor dit postvak of de relatie met uw referenties zijn geen factor. het e-mailadres vertelt Exchange Online PowerShell waar verbinding moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="20e4f-119">Your permissions to that mailbox or the relationship to your credentials are not a factor; the email address simply tells Exchange Online PowerShell where to connect.</span></span>

<span data-ttu-id="20e4f-120">Voor klanten met Microsoft 365 of Microsoft 365 GCC, hoeft u de _ConnectionUri_ -parameter meestal niet te gebruiken om verbinding te maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e4f-120">Microsoft 365 or Microsoft 365 GCC customers typically don't need to use the _ConnectionUri_ parameter to connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="20e4f-121">Als u verbinding wilt maken met een specifieke geografische locatie, moet u _ConnectionUri_ -parameter gebruiken, zodat u `?email=<emailaddress>` deze kunt gebruiken in de waarde.</span><span class="sxs-lookup"><span data-stu-id="20e4f-121">But, to connect to a specific geo location, you do need to use _ConnectionUri_ parameter so you can use `?email=<emailaddress>` in the value.</span></span>

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-using-multi-factor-authentication-mfa"></a><span data-ttu-id="20e4f-122">Verbinding maken met een geografische locatie in Exchange Online PowerShell met multi-factor Authentication (MFA)</span><span class="sxs-lookup"><span data-stu-id="20e4f-122">Connect to a geo location in Exchange Online PowerShell using multi-factor authentication (MFA)</span></span>

1. <span data-ttu-id="20e4f-123">Laad in een Windows PowerShell-venster de module EXO V2 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="20e4f-123">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="20e4f-124">In het volgende voorbeeld is admin@contoso.onmicrosoft.com het beheerdersaccount en is de geografische locatie van de doellocatie de plaats waar het postvak olga@contoso.onmicrosoft.com zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="20e4f-124">In the following example, admin@contoso.onmicrosoft.com is the admin account, and the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

  ```powershell
  Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
  ```

### <a name="connect-to-a-geo-location-in-exchange-online-powershell-without-using-mfa"></a><span data-ttu-id="20e4f-125">Verbinding maken met een geografische locatie in Exchange Online PowerShell zonder MFA te gebruiken</span><span class="sxs-lookup"><span data-stu-id="20e4f-125">Connect to a geo location in Exchange Online PowerShell without using MFA</span></span>

1. <span data-ttu-id="20e4f-126">Laad in een Windows PowerShell-venster de module EXO V2 door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="20e4f-126">In a Windows PowerShell window, load the EXO V2 module by running the following command:</span></span>

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. <span data-ttu-id="20e4f-127">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="20e4f-127">Run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="20e4f-128">In het dialoogvenster **referentie aanvraag voor Windows PowerShell** dat wordt weergegeven, typt u uw werk-of schoolaccount en wachtwoord en klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="20e4f-128">In the **Windows PowerShell Credential Request** dialog box that appears, type your work or school account and password, and then click **OK**.</span></span>

3. <span data-ttu-id="20e4f-129">In het volgende voorbeeld is de geografische locatie van de doellocatie waar de Postvak olga@contoso.onmicrosoft.com zich bevinden.</span><span class="sxs-lookup"><span data-stu-id="20e4f-129">In the following example, the target geo location is where the mailbox olga@contoso.onmicrosoft.com resides.</span></span>

   ```powershell
   Connect-ExchangeOnline -Credential $UserCredential -ShowProgress $true -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="20e4f-130">De beschikbare geo-locaties weergeven die zijn geconfigureerd in uw Exchange Online-organisatie</span><span class="sxs-lookup"><span data-stu-id="20e4f-130">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="20e4f-131">Voer de volgende opdracht uit in PowerShell van Exchange Online voor een overzicht van de geconfigureerde geografische locaties in Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="20e4f-131">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="20e4f-132">De centrale geo-locatie voor uw Exchange Online-organisatie weergeven</span><span class="sxs-lookup"><span data-stu-id="20e4f-132">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="20e4f-133">Voer de volgende opdracht uit in Exchange Online PowerShell als u de centrale geografische locatie van de Tenant wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="20e4f-133">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="20e4f-134">De geografische locatie van een postvak zoeken</span><span class="sxs-lookup"><span data-stu-id="20e4f-134">Find the geo location of a mailbox</span></span>

<span data-ttu-id="20e4f-135">Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende eigenschappen met betrekking tot multi-geografische eigenschappen weergegeven voor postvakken:</span><span class="sxs-lookup"><span data-stu-id="20e4f-135">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="20e4f-136">**Database**: de eerste drie letters van de database naam komen overeen met de geografische code, waarmee wordt aangegeven waar het postvak zich momenteel bevindt.</span><span class="sxs-lookup"><span data-stu-id="20e4f-136">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="20e4f-137">Voor online archief postvakken moet de eigenschap **ArchiveDatabase** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="20e4f-137">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="20e4f-138">**MailboxRegion**: geeft de geografische locatie code aan die door de beheerder is ingesteld (gesynchroniseerd van **PREFERREDDATALOCATION** in azure AD).</span><span class="sxs-lookup"><span data-stu-id="20e4f-138">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="20e4f-139">**MailboxRegionLastUpdateTime**: geeft aan wanneer de MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).</span><span class="sxs-lookup"><span data-stu-id="20e4f-139">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="20e4f-140">Gebruik de volgende syntaxis om de eigenschappen van een postvak te bekijken:</span><span class="sxs-lookup"><span data-stu-id="20e4f-140">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="20e4f-141">Voer de volgende opdracht uit als u de gegevens van de geografische locatie voor de Postvak chris@contoso.onmicrosoft.com wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="20e4f-141">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="20e4f-142">De uitvoer van de opdracht ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="20e4f-142">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="20e4f-143">Als de geo-vestigingcode in de databasenaam niet overeenkomt met de waarde van **MailboxRegion** , wordt het postvak automatisch toegevoegd aan een wachtrij voor hernoemen en wordt verplaatst naar de geo-locatie die is opgegeven via de **MailboxRegion** -waarde (Exchange Online zoekt de waarden van deze eigenschap niet.</span><span class="sxs-lookup"><span data-stu-id="20e4f-143">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="20e4f-144">Een bestaand postvak met alleen de Cloud naar een specifieke geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="20e4f-144">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="20e4f-145">Een gebruiker met Cloud is een gebruiker die niet is gesynchroniseerd met de Tenant via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="20e4f-145">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="20e4f-146">Deze gebruiker is rechtstreeks gemaakt in azure AD.</span><span class="sxs-lookup"><span data-stu-id="20e4f-146">This user was created directly in Azure AD.</span></span> <span data-ttu-id="20e4f-147">Met de cmdlet **Get-MsolUser** en **set-MsolUser** in de Azure ad-module voor Windows PowerShell kunt u de geografische locatie weergeven of opgeven waarop het postvak van de gebruikers van de Cloud wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="20e4f-147">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="20e4f-148">Als u de **PreferredDataLocation** waarde voor een gebruiker wilt bekijken, gebruikt u deze syntaxis in azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="20e4f-148">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="20e4f-149">Voer de volgende opdracht uit als u de **PreferredDataLocation** waarde voor het gebruikers Michelle@contoso.onmicrosoft.com wilt bekijken:</span><span class="sxs-lookup"><span data-stu-id="20e4f-149">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="20e4f-150">Gebruik de volgende syntaxis in azure AD PowerShell om de **PreferredDataLocation** -waarde voor een gebruikersobject in de cloud te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="20e4f-150">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="20e4f-151">Voer de volgende opdracht uit om de **PreferredDataLocation** waarde in te stellen op de Europese Unie (USD) Geo voor de gebruikers Michelle@contoso.onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="20e4f-151">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - <span data-ttu-id="20e4f-152">Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten uit on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="20e4f-152">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="20e4f-153">U moet de **PreferredDataLocation** waarde in Active Directory wijzigen en synchroniseren met behulp van Aad Connect.</span><span class="sxs-lookup"><span data-stu-id="20e4f-153">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="20e4f-154">Zie voor meer informatie [Azure Active Directory Connect Sync: voorkeur gegevenslocatie voor Microsoft 365-bronnen configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="20e4f-154">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
>
> - <span data-ttu-id="20e4f-155">Hoe lang het duurt om een postvak te verplaatsen naar een nieuwe geografische locatie, is afhankelijk van verschillende factoren:</span><span class="sxs-lookup"><span data-stu-id="20e4f-155">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
>
>   - <span data-ttu-id="20e4f-156">De grootte en het type van het postvak.</span><span class="sxs-lookup"><span data-stu-id="20e4f-156">The size and type of mailbox.</span></span>
>   - <span data-ttu-id="20e4f-157">Het aantal postvakken dat wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="20e4f-157">The number of mailboxes being moved.</span></span>
>   - <span data-ttu-id="20e4f-158">De beschikbaarheid van bronnen voor verhuizing.</span><span class="sxs-lookup"><span data-stu-id="20e4f-158">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="20e4f-159">Uitgeschakelde postvakken in de geschil stand verplaatsen</span><span class="sxs-lookup"><span data-stu-id="20e4f-159">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="20e4f-160">Uitgeschakelde postvakken voor het bewaren van een zaak die behouden blijven voor eDiscovery-doeleinden kunnen niet worden verplaatst door de **PreferredDataLocation** -waarde in hun uitgeschakelde staat te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="20e4f-160">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="20e4f-161">Een uitgeschakeld Postvak verplaatsen voor de geschil:</span><span class="sxs-lookup"><span data-stu-id="20e4f-161">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="20e4f-162">Wijs een licentie tijdelijk toe aan het postvak.</span><span class="sxs-lookup"><span data-stu-id="20e4f-162">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="20e4f-163">Wijzig de **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="20e4f-163">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="20e4f-164">Verwijder de licentie uit het postvak nadat deze naar de geselecteerde geo-locatie is verplaatst en zet deze weer in de status uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="20e4f-164">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="20e4f-165">Nieuwe Cloud postvakken maken op een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="20e4f-165">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="20e4f-166">Voer een van de volgende stappen uit als u een nieuw postvak op een specifieke geografische locatie wilt maken:</span><span class="sxs-lookup"><span data-stu-id="20e4f-166">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="20e4f-167">Configureer de **PreferredDataLocation** waarde zoals beschreven in de vorige sectie *voordat* het postvak in Exchange Online werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="20e4f-167">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="20e4f-168">Configureer bijvoorbeeld de **PreferredDataLocation** -waarde voor een gebruiker voordat u een licentie toewijst.</span><span class="sxs-lookup"><span data-stu-id="20e4f-168">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="20e4f-169">Wijs tegelijkertijd een licentie toe aan de **PreferredDataLocation** -waarde.</span><span class="sxs-lookup"><span data-stu-id="20e4f-169">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="20e4f-170">Gebruik de volgende syntaxis in azure AD PowerShell voor het maken van een nieuwe, in de Cloud gerichte gebruiker (niet AAD Connected) op een specifieke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="20e4f-170">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="20e4f-171">In dit voorbeeld wordt een nieuwe gebruikersaccount gemaakt voor Elizabeth Brunner met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="20e4f-171">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="20e4f-172">UPN (User Principal Name): ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="20e4f-172">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>
- <span data-ttu-id="20e4f-173">Voornaam: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="20e4f-173">First name: Elizabeth</span></span>
- <span data-ttu-id="20e4f-174">Achternaam: Brunner</span><span class="sxs-lookup"><span data-stu-id="20e4f-174">Last name: Brunner</span></span>
- <span data-ttu-id="20e4f-175">Weergavenaam: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="20e4f-175">Display name: Elizabeth Brunner</span></span>
- <span data-ttu-id="20e4f-176">Wachtwoord: willekeurig gegenereerd en wordt weergegeven in de resultaten van de opdracht (omdat we de *wachtwoord* parameters niet gebruiken)</span><span class="sxs-lookup"><span data-stu-id="20e4f-176">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>
- <span data-ttu-id="20e4f-177">Licentie: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="20e4f-177">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>
- <span data-ttu-id="20e4f-178">Locatie: Australië (AUS)</span><span class="sxs-lookup"><span data-stu-id="20e4f-178">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="20e4f-179">Als u meer wilt weten over het maken van nieuwe gebruikersaccounts en het vinden van LicenseAssignment-waarden in azure AD PowerShell, raadpleegt u [gebruikersaccounts maken met PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en [licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="20e4f-179">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20e4f-180">Als u Exchange Online PowerShell gebruikt om een postvak in te schakelen en het postvak rechtstreeks moet maken op de geografische locatie die in **PreferredDataLocation**is opgegeven, moet u een cmdlet van Exchange Online gebruiken, zoals **inschakelen-postvak** of **Nieuw-postvak** rechtstreeks op de Cloud-service.</span><span class="sxs-lookup"><span data-stu-id="20e4f-180">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="20e4f-181">Als u de **Enable-RemoteMailbox-** cmdlet in on-premises Exchange PowerShell gebruikt, wordt het postvak gemaakt in de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="20e4f-181">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="20e4f-182">Bestaande on-premises postvakken in een specifieke geografische locatie opvullen</span><span class="sxs-lookup"><span data-stu-id="20e4f-182">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="20e4f-183">U kunt de standaardhulpprogramma's en [-](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) processen voor onboarding gebruiken voor het migreren van een postvak vanuit een on-premises Exchange-organisatie naar Exchange Online, inclusief het [migratie dashboard in het](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e4f-183">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="20e4f-184">De eerste stap bestaat uit het controleren van een gebruikersobject, en de juiste **PreferredDataLocation** waarde is geconfigureerd in azure AD.</span><span class="sxs-lookup"><span data-stu-id="20e4f-184">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="20e4f-185">Met de hulpmiddelen voor onboarding wordt de **PreferredDataLocation** waarde bepaald en worden de postvakken direct naar de opgegeven geografische locatie gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="20e4f-185">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="20e4f-186">U kunt ook de volgende stappen uitvoeren om postvakken rechtstreeks op te zetten op een specifieke geo-locatie met behulp van de [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) -cmdlet in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20e4f-186">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="20e4f-187">Controleer of het gebruikersobject bestaat voor elk postvak en dat **PreferredDataLocation** is ingesteld op de gewenste waarde in azure AD.</span><span class="sxs-lookup"><span data-stu-id="20e4f-187">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="20e4f-188">De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het **MailboxRegion** -kenmerk van het bijbehorende e-mail gebruikersobject in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="20e4f-188">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="20e4f-189">Verbind rechtstreeks met de specifieke geografische locatie van de satelliet met de verbindings instructies van eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="20e4f-189">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="20e4f-190">In Exchange Online PowerShell slaat u de on-premises beheerdersreferenties op die wordt gebruikt om een migratie van een postvak in een variabele uit te voeren door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="20e4f-190">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="20e4f-191">Maak in Exchange Online PowerShell een nieuwe **nieuwe MoveRequest** die vergelijkbaar is met het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="20e4f-191">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="20e4f-192">Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische locatie van de satelliet waarmee u momenteel bent verbonden.</span><span class="sxs-lookup"><span data-stu-id="20e4f-192">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="20e4f-193">Als u extra postvakken moet migreren naar verschillende geografische locaties, herhaalt u stappen 2 tot en met 4 voor elke specifieke locatie.</span><span class="sxs-lookup"><span data-stu-id="20e4f-193">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="20e4f-194">Meerdere geografische rapporten</span><span class="sxs-lookup"><span data-stu-id="20e4f-194">Multi-geo reporting</span></span>

<span data-ttu-id="20e4f-195">Met de **rapporten voor meerdere geografische gebruik** in het microsoft 365-Beheercentrum wordt het aantal gebruikers per geo-locatie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="20e4f-195">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="20e4f-196">In het rapport wordt de distributie van gebruikers weergegeven voor de huidige maand en de historische gegevens voor de afgelopen zes maanden.</span><span class="sxs-lookup"><span data-stu-id="20e4f-196">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="20e4f-197">Zie ook</span><span class="sxs-lookup"><span data-stu-id="20e4f-197">See also</span></span>

[<span data-ttu-id="20e4f-198">Microsoft 365 beheren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="20e4f-198">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
