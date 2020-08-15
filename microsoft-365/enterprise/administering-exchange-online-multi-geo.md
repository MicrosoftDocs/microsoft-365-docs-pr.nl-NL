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
ms.openlocfilehash: 645d48066ca02dbf3480e20ae30dc187f84293cf
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688945"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a><span data-ttu-id="c7a59-103">Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren</span><span class="sxs-lookup"><span data-stu-id="c7a59-103">Administering Exchange Online mailboxes in a multi-geo environment</span></span>

<span data-ttu-id="c7a59-104">Externe PowerShell is vereist voor het weergeven en configureren van meervoudige geo-eigenschappen in uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="c7a59-104">Remote PowerShell is required to view and configure multi geo properties in your Microsoft 365 environment.</span></span> <span data-ttu-id="c7a59-105">Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a59-105">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="c7a59-106">U hebt [Microsoft Azure Active Directory PowerShell module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 of hoger nodig in v1. x om de eigenschap **PreferredDataLocation** voor gebruikersobjecten weer te geven.</span><span class="sxs-lookup"><span data-stu-id="c7a59-106">You need the [Microsoft Azure Active Directory PowerShell Module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 or later in v1.x to see the **PreferredDataLocation** property on user objects.</span></span> <span data-ttu-id="c7a59-107">Gebruikersobjecten die zijn gesynchroniseerd via AAD Connect in AAD, kunnen hun **PreferredDataLocation** -waarde niet rechtstreeks wijzigen via Aad PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a59-107">User objects synchronized via AAD Connect into AAD cannot have their **PreferredDataLocation** value directly modified via AAD PowerShell.</span></span> <span data-ttu-id="c7a59-108">Gebruikersobjecten in de Cloud kunnen met behulp van AAD PowerShell worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c7a59-108">Cloud-only user objects can be modified via AAD PowerShell.</span></span> <span data-ttu-id="c7a59-109">Als u verbinding wilt maken met Azure AD PowerShell, raadpleegt [u verbinding maken met PowerShell](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c7a59-109">To connect to Azure AD PowerShell, see [Connect to PowerShell](connect-to-microsoft-365-powershell.md).</span></span>

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a><span data-ttu-id="c7a59-110">Direct verbinding maken met een geo-locatie met Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7a59-110">Connect directly to a geo location using Exchange Online PowerShell</span></span>

<span data-ttu-id="c7a59-111">Meestal maakt Exchange Online PowerShell verbinding met de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="c7a59-111">Typically, Exchange Online PowerShell will connect to the central geo location.</span></span> <span data-ttu-id="c7a59-112">Maar u kunt ook rechtstreeks verbinding maken met satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="c7a59-112">But, you can also connect directly to satellite geo locations.</span></span> <span data-ttu-id="c7a59-113">Vanwege prestatieverbeteringen wordt u aangeraden direct verbinding te maken met de geografische locatie van de satelliet wanneer u alleen gebruikers op die locatie beheert.</span><span class="sxs-lookup"><span data-stu-id="c7a59-113">Because of performance improvements, we recommend connecting directly to the satellite geo location when you only manage users in that location.</span></span>

<span data-ttu-id="c7a59-114">Als u verbinding wilt maken met een specifieke geografische locatie, is de parameter *ConnectionUri* niet gelijk aan de reguliere verbindings instructies.</span><span class="sxs-lookup"><span data-stu-id="c7a59-114">To connect to a specific geo location, the *ConnectionUri* parameter is different than the regular connection instructions.</span></span> <span data-ttu-id="c7a59-115">De rest van de opdrachten en waarden zijn hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="c7a59-115">The rest of the commands and values are the same.</span></span> <span data-ttu-id="c7a59-116">De stappen zijn:</span><span class="sxs-lookup"><span data-stu-id="c7a59-116">The steps are:</span></span>

1. <span data-ttu-id="c7a59-117">Open Windows PowerShell op uw lokale computer en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c7a59-117">On your local computer, open Windows PowerShell and run the following command:</span></span>

   ```powershell
   $UserCredential = Get-Credential
   ```

   <span data-ttu-id="c7a59-118">In het dialoogvenster **referentie aanvraag voor Windows PowerShell** typt u uw werk-of schoolaccount en wachtwoord en klikt u op **OK**.</span><span class="sxs-lookup"><span data-stu-id="c7a59-118">In the **Windows PowerShell Credential Request** dialog box, type your work or school account and password, and then click **OK**.</span></span>

2. <span data-ttu-id="c7a59-119">Vervang door `<emailaddress>` het e-mailadres van **een** postvak op de geografische locatie van de doellocatie en voer de volgende opdracht uit.</span><span class="sxs-lookup"><span data-stu-id="c7a59-119">Replace `<emailaddress>` with the email address of **any** mailbox in the target geo location and run the following command.</span></span> <span data-ttu-id="c7a59-120">Uw machtigingen voor het postvak en de relatie met uw referenties in stap 1 zijn geen factor; het e-mailadres vertelt Exchange Online waar verbinding moet worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c7a59-120">Your permissions on the mailbox and the relationship to your credentials in Step 1 are not a factor; the email address simply tells Exchange Online where to connect.</span></span>
  
   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=<emailaddress> -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

   <span data-ttu-id="c7a59-121">Als olga@contoso.onmicrosoft.com bijvoorbeeld het e-mailadres van een geldig postvak is op de geografische locatie waar u een verbinding wilt maken, voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c7a59-121">For example, if olga@contoso.onmicrosoft.com is the email address of a valid mailbox in the geo location where you want to connect, run the following command:</span></span>

   ```powershell
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com -Credential $UserCredential -Authentication  Basic -AllowRedirection
   ```

3. <span data-ttu-id="c7a59-122">Voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="c7a59-122">Run the following command:</span></span>

    ```powershell
    Import-PSSession $Session
    ```

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a><span data-ttu-id="c7a59-123">De beschikbare geo-locaties weergeven die zijn geconfigureerd in uw Exchange Online-organisatie</span><span class="sxs-lookup"><span data-stu-id="c7a59-123">View the available geo locations that are configured in your Exchange Online organization</span></span>

<span data-ttu-id="c7a59-124">Voer de volgende opdracht uit in PowerShell van Exchange Online voor een overzicht van de geconfigureerde geografische locaties in Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="c7a59-124">To see the list of configured geo locations in Microsoft 365 Multi-Geo, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a><span data-ttu-id="c7a59-125">De centrale geo-locatie voor uw Exchange Online-organisatie weergeven</span><span class="sxs-lookup"><span data-stu-id="c7a59-125">View the central geo location for your Exchange Online organization</span></span>

<span data-ttu-id="c7a59-126">Voer de volgende opdracht uit in Exchange Online PowerShell als u de centrale geografische locatie van de Tenant wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="c7a59-126">To view your tenant's central geo location, run the following command in Exchange Online PowerShell:</span></span>

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a><span data-ttu-id="c7a59-127">De geografische locatie van een postvak zoeken</span><span class="sxs-lookup"><span data-stu-id="c7a59-127">Find the geo location of a mailbox</span></span>

<span data-ttu-id="c7a59-128">Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende eigenschappen met betrekking tot multi-geografische eigenschappen weergegeven voor postvakken:</span><span class="sxs-lookup"><span data-stu-id="c7a59-128">The **Get-Mailbox** cmdlet in Exchange Online PowerShell displays the following multi-geo related properties on mailboxes:</span></span>

- <span data-ttu-id="c7a59-129">**Database**: de eerste drie letters van de database naam komen overeen met de geografische code, waarmee wordt aangegeven waar het postvak zich momenteel bevindt.</span><span class="sxs-lookup"><span data-stu-id="c7a59-129">**Database**: The first 3 letters of the database name correspond to the geo code, which tells you where the mailbox is currently located.</span></span> <span data-ttu-id="c7a59-130">Voor online archief postvakken moet de eigenschap **ArchiveDatabase** worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c7a59-130">For Online Archive Mailboxes the **ArchiveDatabase** property should be used.</span></span>

- <span data-ttu-id="c7a59-131">**MailboxRegion**: geeft de geografische locatie code aan die door de beheerder is ingesteld (gesynchroniseerd van **PREFERREDDATALOCATION** in azure AD).</span><span class="sxs-lookup"><span data-stu-id="c7a59-131">**MailboxRegion**: Specifies the geo location code that was set by the admin (synchronized from **PreferredDataLocation** in Azure AD).</span></span>

- <span data-ttu-id="c7a59-132">**MailboxRegionLastUpdateTime**: geeft aan wanneer de MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).</span><span class="sxs-lookup"><span data-stu-id="c7a59-132">**MailboxRegionLastUpdateTime**: Indicates when MailboxRegion was last updated (either automatically or manually).</span></span>

<span data-ttu-id="c7a59-133">Gebruik de volgende syntaxis om de eigenschappen van een postvak te bekijken:</span><span class="sxs-lookup"><span data-stu-id="c7a59-133">To see these properties for a mailbox, use the following syntax:</span></span>

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

<span data-ttu-id="c7a59-134">Voer de volgende opdracht uit als u de gegevens van de geografische locatie voor de Postvak chris@contoso.onmicrosoft.com wilt weergeven:</span><span class="sxs-lookup"><span data-stu-id="c7a59-134">For example, to see the geo location information for the mailbox chris@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

<span data-ttu-id="c7a59-135">De uitvoer van de opdracht ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c7a59-135">The output of the command looks like this:</span></span>

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> <span data-ttu-id="c7a59-136">Als de geo-vestigingcode in de databasenaam niet overeenkomt met de waarde van **MailboxRegion** , wordt het postvak automatisch toegevoegd aan een wachtrij voor hernoemen en wordt verplaatst naar de geo-locatie die is opgegeven via de **MailboxRegion** -waarde (Exchange Online zoekt de waarden van deze eigenschap niet.</span><span class="sxs-lookup"><span data-stu-id="c7a59-136">If the geo location code in the database name doesn't match **MailboxRegion** value, the mailbox will be automatically be put into a relocation queue and moved to the geo location specified by the **MailboxRegion** value (Exchange Online looks for a mismatch between these property values).</span></span>

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a><span data-ttu-id="c7a59-137">Een bestaand postvak met alleen de Cloud naar een specifieke geografische locatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="c7a59-137">Move an existing cloud-only mailbox to a specific geo location</span></span>

<span data-ttu-id="c7a59-138">Een gebruiker met Cloud is een gebruiker die niet is gesynchroniseerd met de Tenant via AAD Connect.</span><span class="sxs-lookup"><span data-stu-id="c7a59-138">A cloud-only user is a user not synchronized to the tenant via AAD Connect.</span></span> <span data-ttu-id="c7a59-139">Deze gebruiker is rechtstreeks gemaakt in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c7a59-139">This user was created directly in Azure AD.</span></span> <span data-ttu-id="c7a59-140">Met de cmdlet **Get-MsolUser** en **set-MsolUser** in de Azure ad-module voor Windows PowerShell kunt u de geografische locatie weergeven of opgeven waarop het postvak van de gebruikers van de Cloud wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="c7a59-140">Use the **Get-MsolUser** and **Set-MsolUser** cmdlets in the Azure AD Module for Windows PowerShell to view or specify the geo location where a cloud-only user's mailbox will be stored.</span></span>

<span data-ttu-id="c7a59-141">Als u de **PreferredDataLocation** waarde voor een gebruiker wilt bekijken, gebruikt u deze syntaxis in azure AD PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c7a59-141">To view the **PreferredDataLocation** value for a user, use this syntax in Azure AD PowerShell:</span></span>

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

<span data-ttu-id="c7a59-142">Voer de volgende opdracht uit als u de **PreferredDataLocation** waarde voor het gebruikers Michelle@contoso.onmicrosoft.com wilt bekijken:</span><span class="sxs-lookup"><span data-stu-id="c7a59-142">For example, to see the **PreferredDataLocation** value for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

<span data-ttu-id="c7a59-143">Gebruik de volgende syntaxis in azure AD PowerShell om de **PreferredDataLocation** -waarde voor een gebruikersobject in de cloud te wijzigen:</span><span class="sxs-lookup"><span data-stu-id="c7a59-143">To modify the **PreferredDataLocation** value for a cloud-only user object, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="c7a59-144">Voer de volgende opdracht uit om de **PreferredDataLocation** waarde in te stellen op de Europese Unie (USD) Geo voor de gebruikers Michelle@contoso.onmicrosoft.com:</span><span class="sxs-lookup"><span data-stu-id="c7a59-144">For example, to set the **PreferredDataLocation** value to the European Union (EUR) geo for the user michelle@contoso.onmicrosoft.com, run the following command:</span></span>

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
> - <span data-ttu-id="c7a59-145">Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten uit on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7a59-145">As mentioned previously, you cannot use this procedure for synchronized user objects from on-premises Active Directory.</span></span> <span data-ttu-id="c7a59-146">U moet de **PreferredDataLocation** waarde in Active Directory wijzigen en synchroniseren met behulp van Aad Connect.</span><span class="sxs-lookup"><span data-stu-id="c7a59-146">You need to change the **PreferredDataLocation** value in Active Directory and synchronize it using AAD Connect.</span></span> <span data-ttu-id="c7a59-147">Zie voor meer informatie [Azure Active Directory Connect Sync: voorkeur gegevenslocatie voor Microsoft 365-bronnen configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span><span class="sxs-lookup"><span data-stu-id="c7a59-147">For more information, see [Azure Active Directory Connect sync: Configure preferred data location for Microsoft 365 resources](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).</span></span>
> 
> - <span data-ttu-id="c7a59-148">Hoe lang het duurt om een postvak te verplaatsen naar een nieuwe geografische locatie, is afhankelijk van verschillende factoren:</span><span class="sxs-lookup"><span data-stu-id="c7a59-148">How long it takes to relocate a mailbox to a new geo location depends on several factors:</span></span>
> 
>   - <span data-ttu-id="c7a59-149">De grootte en het type van het postvak.</span><span class="sxs-lookup"><span data-stu-id="c7a59-149">The size and type of mailbox.</span></span>
> 
>   - <span data-ttu-id="c7a59-150">Het aantal postvakken dat wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="c7a59-150">The number of mailboxes being moved.</span></span>
> 
>   - <span data-ttu-id="c7a59-151">De beschikbaarheid van bronnen voor verhuizing.</span><span class="sxs-lookup"><span data-stu-id="c7a59-151">The availability of move resources.</span></span>

### <a name="move-disabled-mailboxes-that-are-on-litigation-hold"></a><span data-ttu-id="c7a59-152">Uitgeschakelde postvakken in de geschil stand verplaatsen</span><span class="sxs-lookup"><span data-stu-id="c7a59-152">Move disabled mailboxes that are on Litigation Hold</span></span>

<span data-ttu-id="c7a59-153">Uitgeschakelde postvakken voor het bewaren van een zaak die behouden blijven voor eDiscovery-doeleinden kunnen niet worden verplaatst door de **PreferredDataLocation** -waarde in hun uitgeschakelde staat te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c7a59-153">Disabled mailboxes on Litigation Hold that are preserved for eDiscovery purposes cannot be moved by changing their **PreferredDataLocation** value in their disabled state.</span></span> <span data-ttu-id="c7a59-154">Een uitgeschakeld Postvak verplaatsen voor de geschil:</span><span class="sxs-lookup"><span data-stu-id="c7a59-154">To move a disabled mailbox on litigation hold:</span></span>

1. <span data-ttu-id="c7a59-155">Wijs een licentie tijdelijk toe aan het postvak.</span><span class="sxs-lookup"><span data-stu-id="c7a59-155">Temporarily assign a license to the mailbox.</span></span>

2. <span data-ttu-id="c7a59-156">Wijzig de **PreferredDataLocation**.</span><span class="sxs-lookup"><span data-stu-id="c7a59-156">Change the **PreferredDataLocation**.</span></span>

3. <span data-ttu-id="c7a59-157">Verwijder de licentie uit het postvak nadat deze naar de geselecteerde geo-locatie is verplaatst en zet deze weer in de status uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c7a59-157">Remove the license from the mailbox after it has been moved to the selected geo location to put it back into the disabled state.</span></span>

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="c7a59-158">Nieuwe Cloud postvakken maken op een specifieke geografische locatie</span><span class="sxs-lookup"><span data-stu-id="c7a59-158">Create new cloud mailboxes in a specific geo location</span></span>

<span data-ttu-id="c7a59-159">Voer een van de volgende stappen uit als u een nieuw postvak op een specifieke geografische locatie wilt maken:</span><span class="sxs-lookup"><span data-stu-id="c7a59-159">To create a new mailbox in a specific geo location, you need to do either of these steps:</span></span>

- <span data-ttu-id="c7a59-160">Configureer de **PreferredDataLocation** waarde zoals beschreven in de vorige sectie *voordat* het postvak in Exchange Online werd gemaakt.</span><span class="sxs-lookup"><span data-stu-id="c7a59-160">Configure the **PreferredDataLocation** value as described in the previous section *before* the mailbox is created in Exchange Online.</span></span> <span data-ttu-id="c7a59-161">Configureer bijvoorbeeld de **PreferredDataLocation** -waarde voor een gebruiker voordat u een licentie toewijst.</span><span class="sxs-lookup"><span data-stu-id="c7a59-161">For example, configure the **PreferredDataLocation** value on a user before assigning a license.</span></span>

- <span data-ttu-id="c7a59-162">Wijs tegelijkertijd een licentie toe aan de **PreferredDataLocation** -waarde.</span><span class="sxs-lookup"><span data-stu-id="c7a59-162">Assign a license at the same time you set the **PreferredDataLocation** value.</span></span>

<span data-ttu-id="c7a59-163">Gebruik de volgende syntaxis in azure AD PowerShell voor het maken van een nieuwe, in de Cloud gerichte gebruiker (niet AAD Connected) op een specifieke geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="c7a59-163">To create a new cloud-only licensed user (not AAD Connect synchronized) in a specific geo location, use the following syntax in Azure AD PowerShell:</span></span>

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

<span data-ttu-id="c7a59-164">In dit voorbeeld wordt een nieuwe gebruikersaccount gemaakt voor Elizabeth Brunner met de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="c7a59-164">This example create a new user account for Elizabeth Brunner with the following values:</span></span>

- <span data-ttu-id="c7a59-165">UPN (User Principal Name): ebrunner@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c7a59-165">User principal name: ebrunner@contoso.onmicrosoft.com</span></span>

- <span data-ttu-id="c7a59-166">Voornaam: Elizabeth</span><span class="sxs-lookup"><span data-stu-id="c7a59-166">First name: Elizabeth</span></span>

- <span data-ttu-id="c7a59-167">Achternaam: Brunner</span><span class="sxs-lookup"><span data-stu-id="c7a59-167">Last name: Brunner</span></span>

- <span data-ttu-id="c7a59-168">Weergavenaam: Elizabeth Brunner</span><span class="sxs-lookup"><span data-stu-id="c7a59-168">Display name: Elizabeth Brunner</span></span>

- <span data-ttu-id="c7a59-169">Wachtwoord: willekeurig gegenereerd en wordt weergegeven in de resultaten van de opdracht (omdat we de *wachtwoord* parameters niet gebruiken)</span><span class="sxs-lookup"><span data-stu-id="c7a59-169">Password: randomly-generated and shown in the results of the command (because we're not using the *Password* parameter)</span></span>

- <span data-ttu-id="c7a59-170">Licentie: `contoso:ENTERPRISEPREMIUM` (E5)</span><span class="sxs-lookup"><span data-stu-id="c7a59-170">License: `contoso:ENTERPRISEPREMIUM` (E5)</span></span>

- <span data-ttu-id="c7a59-171">Locatie: Australië (AUS)</span><span class="sxs-lookup"><span data-stu-id="c7a59-171">Location: Australia (AUS)</span></span>

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

<span data-ttu-id="c7a59-172">Als u meer wilt weten over het maken van nieuwe gebruikersaccounts en het vinden van LicenseAssignment-waarden in azure AD PowerShell, raadpleegt u [gebruikersaccounts maken met PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en [licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="c7a59-172">For more information about creating new user accounts and finding LicenseAssignment values in Azure AD PowerShell, see [Create user accounts with PowerShell](create-user-accounts-with-microsoft-365-powershell.md) and [View licenses and services with PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7a59-173">Als u Exchange Online PowerShell gebruikt om een postvak in te schakelen en het postvak rechtstreeks moet maken op de geografische locatie die in **PreferredDataLocation**is opgegeven, moet u een cmdlet van Exchange Online gebruiken, zoals **inschakelen-postvak** of **Nieuw-postvak** rechtstreeks op de Cloud-service.</span><span class="sxs-lookup"><span data-stu-id="c7a59-173">If you are using Exchange Online PowerShell to enable a mailbox and need the mailbox to be created directly in the geo location that's specified in **PreferredDataLocation**, you need to use an Exchange Online cmdlet such as **Enable-Mailbox** or **New-Mailbox** directly against the cloud service.</span></span> <span data-ttu-id="c7a59-174">Als u de **Enable-RemoteMailbox-** cmdlet in on-premises Exchange PowerShell gebruikt, wordt het postvak gemaakt in de centrale geo-locatie.</span><span class="sxs-lookup"><span data-stu-id="c7a59-174">If you use the **Enable-RemoteMailbox** cmdlet in on-premises Exchange PowerShell, the mailbox will be created in the central geo location.</span></span>

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a><span data-ttu-id="c7a59-175">Bestaande on-premises postvakken in een specifieke geografische locatie opvullen</span><span class="sxs-lookup"><span data-stu-id="c7a59-175">Onboard existing on-premises mailboxes in a specific geo location</span></span>

<span data-ttu-id="c7a59-176">U kunt de standaardhulpprogramma's en [-](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) processen voor onboarding gebruiken voor het migreren van een postvak vanuit een on-premises Exchange-organisatie naar Exchange Online, inclusief het [migratie dashboard in het](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a59-176">You can use the standard onboarding tools and processes to migrate a mailbox from an on-premises Exchange organization to Exchange Online, including the [Migration dashboard in the EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331), and the [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) cmdlet in Exchange Online PowerShell.</span></span>

<span data-ttu-id="c7a59-177">De eerste stap bestaat uit het controleren van een gebruikersobject, en de juiste **PreferredDataLocation** waarde is geconfigureerd in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c7a59-177">The first step is to verify a user object exists for each mailbox to be onboarded, and verify the correct **PreferredDataLocation** value is configured in Azure AD.</span></span> <span data-ttu-id="c7a59-178">Met de hulpmiddelen voor onboarding wordt de **PreferredDataLocation** waarde bepaald en worden de postvakken direct naar de opgegeven geografische locatie gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="c7a59-178">The onboarding tools will respect the **PreferredDataLocation** value and will migrate the mailboxes directly to the specified geo location.</span></span>

<span data-ttu-id="c7a59-179">U kunt ook de volgende stappen uitvoeren om postvakken rechtstreeks op te zetten op een specifieke geo-locatie met behulp van de [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) -cmdlet in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7a59-179">Or, you can use the following steps to onboard mailboxes directly in a specific geo location using the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) cmdlet in Exchange Online PowerShell.</span></span>

1. <span data-ttu-id="c7a59-180">Controleer of het gebruikersobject bestaat voor elk postvak en dat **PreferredDataLocation** is ingesteld op de gewenste waarde in azure AD.</span><span class="sxs-lookup"><span data-stu-id="c7a59-180">Verify the user object exists for each mailbox to be onboarded and that **PreferredDataLocation** is set to the desired value in Azure AD.</span></span> <span data-ttu-id="c7a59-181">De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het **MailboxRegion** -kenmerk van het bijbehorende e-mail gebruikersobject in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c7a59-181">The value of **PreferredDataLocation** will be synchronized to the **MailboxRegion** attribute of the corresponding mail user object in Exchange Online.</span></span>

2. <span data-ttu-id="c7a59-182">Verbind rechtstreeks met de specifieke geografische locatie van de satelliet met de verbindings instructies van eerder in dit artikel.</span><span class="sxs-lookup"><span data-stu-id="c7a59-182">Connect directly to the specific satellite geo location using the connection instructions from earlier in this topic.</span></span>

3. <span data-ttu-id="c7a59-183">In Exchange Online PowerShell slaat u de on-premises beheerdersreferenties op die wordt gebruikt om een migratie van een postvak in een variabele uit te voeren door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="c7a59-183">In Exchange Online PowerShell, store the on-premises administrator credentials that's used to perform a mailbox migration in a variable by running the following command:</span></span>

   ```powershell
   $RC = Get-Credential
   ```

4. <span data-ttu-id="c7a59-184">Maak in Exchange Online PowerShell een nieuwe **nieuwe MoveRequest** die vergelijkbaar is met het volgende voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="c7a59-184">In Exchange Online PowerShell, create a new **New-MoveRequest** similar to the following example:</span></span>

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. <span data-ttu-id="c7a59-185">Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische locatie van de satelliet waarmee u momenteel bent verbonden.</span><span class="sxs-lookup"><span data-stu-id="c7a59-185">Repeat step #4 for every mailbox you need to migrate from on-premises Exchange to the satellite geo location you are currently connected to.</span></span>

6. <span data-ttu-id="c7a59-186">Als u extra postvakken moet migreren naar verschillende geografische locaties, herhaalt u stappen 2 tot en met 4 voor elke specifieke locatie.</span><span class="sxs-lookup"><span data-stu-id="c7a59-186">If you need to migrate additional mailboxes to different satellite geo locations, repeat steps 2 through 4 for each specific location.</span></span>

## <a name="multi-geo-reporting"></a><span data-ttu-id="c7a59-187">Meerdere geografische rapporten</span><span class="sxs-lookup"><span data-stu-id="c7a59-187">Multi-geo reporting</span></span>

<span data-ttu-id="c7a59-188">Met de **rapporten voor meerdere geografische gebruik** in het microsoft 365-Beheercentrum wordt het aantal gebruikers per geo-locatie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c7a59-188">**Multi-Geo Usage Reports** in the Microsoft 365 admin center displays the user count by geo location.</span></span> <span data-ttu-id="c7a59-189">In het rapport wordt de distributie van gebruikers weergegeven voor de huidige maand en de historische gegevens voor de afgelopen zes maanden.</span><span class="sxs-lookup"><span data-stu-id="c7a59-189">The report displays user distribution for the current month and provides historical data for the past 6 months.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7a59-190">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c7a59-190">See also</span></span>

[<span data-ttu-id="c7a59-191">Microsoft 365 en Exchange Online beheren met Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c7a59-191">Managing Microsoft 365 and Exchange Online with Windows PowerShell</span></span>](https://support.office.com//article/06a743bb-ceb6-49a9-a61d-db4ffdf54fa6)
