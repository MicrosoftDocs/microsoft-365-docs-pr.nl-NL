---
title: Domeinen verplaatsen & instellingen van de ene EOP-organisatie naar de andere
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9d64867b-ebdb-4323-8e30-4560d76b4c97
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u domeinen en instellingen verplaatst van de ene Microsoft Exchange Online Protection (EOP)-organisatie (tenant) naar de andere.
ms.openlocfilehash: 86f268e6bfb5ed7229137df8b6bf017f15ab1f9c
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033960"
---
# <a name="move-domains-and-settings-from-one-eop-organization-to-another-eop-organization"></a><span data-ttu-id="deeb5-103">Domeinen en instellingen van één EOP-organisatie naar een andere EOP-organisatie verplaatsen</span><span class="sxs-lookup"><span data-stu-id="deeb5-103">Move domains and settings from one EOP organization to another EOP organization</span></span>

<span data-ttu-id="deeb5-104">Als u de vereisten voor bedrijven wijzigt, moet soms één EOP-organisatie (tenant) (Microsoft Exchange Online Protection) worden opgesplitst in twee afzonderlijke organisaties, twee organisaties samenvoegen tot één of moeten uw domeinen en EOP-instellingen van de ene organisatie naar de andere worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="deeb5-104">Changing business requirements can sometimes require splitting one Microsoft Exchange Online Protection (EOP) organization (tenant) into two separate organizations, merging two organizations into one, or moving your domains and EOP settings from one organization to another organization.</span></span> <span data-ttu-id="deeb5-105">De overstap van de ene EOP-organisatie naar een tweede EOP-organisatie kan een uitdaging zijn, maar met een paar eenvoudige externe Windows PowerShell-scripts en een kleine hoeveelheid voorbereiding kan dit worden bereikt met een relatief klein onderhoudsvenster.</span><span class="sxs-lookup"><span data-stu-id="deeb5-105">Moving from one EOP organization to a second EOP organization can be challenging, but with a few basic remote Windows PowerShell scripts and a small amount of preparation, this can be achieved with a relatively small maintenance window.</span></span>

> [!NOTE]
> <span data-ttu-id="deeb5-106">Instellingen kunnen alleen betrouwbaar worden verplaatst van een EOP standalone (Standard) organisatie naar een andere EOP Standard of een Exchange Enterprise CAL with Services (EOP Premium) organisatie, of van een EOP Premium organisatie naar een andere EOP Premium organisatie.</span><span class="sxs-lookup"><span data-stu-id="deeb5-106">Settings can be reliably moved only from an EOP standalone (Standard) organization to either another EOP Standard or an Exchange Enterprise CAL with Services (EOP Premium) organization, or from an EOP Premium organization to another EOP Premium organization.</span></span> <span data-ttu-id="deeb5-107">Omdat sommige premiumfuncties niet worden ondersteund in EOP Standard-organisaties, is de overstap van een EOP Premium-organisatie naar een EOP Standard-organisatie mogelijk niet succesvol.</span><span class="sxs-lookup"><span data-stu-id="deeb5-107">Because some premium features are not supported in EOP Standard organizations, moves from an EOP Premium organization to an EOP Standard organization might not be successful.</span></span> <br><br> <span data-ttu-id="deeb5-108">Deze instructies zijn voor EOP-filtering-only organisaties.</span><span class="sxs-lookup"><span data-stu-id="deeb5-108">These instructions are for EOP filtering-only organizations.</span></span> <span data-ttu-id="deeb5-109">Er zijn aanvullende overwegingen bij het overstappen van de ene Exchange Online-organisatie naar een andere Exchange Online-organisatie.</span><span class="sxs-lookup"><span data-stu-id="deeb5-109">There are additional considerations in moving from one Exchange Online organization to another Exchange Online organization.</span></span> <span data-ttu-id="deeb5-110">Exchange Online-organisaties zijn buiten het bereik van deze instructies.</span><span class="sxs-lookup"><span data-stu-id="deeb5-110">Exchange Online organizations are out of scope for these instructions.</span></span>

<span data-ttu-id="deeb5-111">In het volgende voorbeeld is Contoso, Ltd. gefuseerd met Contoso Suites.</span><span class="sxs-lookup"><span data-stu-id="deeb5-111">In the following example, Contoso, Ltd. has merged with Contoso Suites.</span></span> <span data-ttu-id="deeb5-112">De volgende afbeelding toont het proces van het verplaatsen van domeinen, e-mailgebruikers en -groepen en instellingen van de bron-EOP-organisatie (contoso.onmicrosoft.com) naar de doelorganisatie EOP (contososuites.onmicrosoft.com):</span><span class="sxs-lookup"><span data-stu-id="deeb5-112">The following image shows the process of moving domains, mail users and groups, and settings from the source EOP organization (contoso.onmicrosoft.com) to the target EOP organization (contososuites.onmicrosoft.com):</span></span>

![EOP-domeinen en -instellingen verplaatsen](../../media/EOP-Move-domains-and-settings.jpg)

<span data-ttu-id="deeb5-114">De uitdaging bij het verplaatsen van domeinen van de ene organisatie naar de andere is dat een geverifieerd domein niet kan bestaan in twee organisaties tegelijk.</span><span class="sxs-lookup"><span data-stu-id="deeb5-114">The challenge in moving domains from one organization to another is that a verified domain can't exist in two organizations at the same time.</span></span> <span data-ttu-id="deeb5-115">De volgende stappen helpen u hierbij te werken.</span><span class="sxs-lookup"><span data-stu-id="deeb5-115">The following steps help you work through this.</span></span>

## <a name="step-1-collect-data-from-the-source-organization"></a><span data-ttu-id="deeb5-116">Stap 1: Gegevens verzamelen van de bronorganisatie</span><span class="sxs-lookup"><span data-stu-id="deeb5-116">Step 1: Collect data from the source organization</span></span>

<span data-ttu-id="deeb5-117">Als u de bronorganisatie in de doelorganisatie opnieuw wilt maken, moet u ervoor zorgen dat u de volgende informatie over de bronorganisatie verzamelt en opslaat:</span><span class="sxs-lookup"><span data-stu-id="deeb5-117">In order to re-create the source organization in the target organization, make sure that you collect and store the following information about the source organization:</span></span>

- <span data-ttu-id="deeb5-118">Domeinen</span><span class="sxs-lookup"><span data-stu-id="deeb5-118">Domains</span></span>

- <span data-ttu-id="deeb5-119">E-mailgebruikers</span><span class="sxs-lookup"><span data-stu-id="deeb5-119">Mail users</span></span>

- <span data-ttu-id="deeb5-120">Groepen</span><span class="sxs-lookup"><span data-stu-id="deeb5-120">Groups</span></span>

- <span data-ttu-id="deeb5-121">Filters voor antispaminhoud</span><span class="sxs-lookup"><span data-stu-id="deeb5-121">Anti-spam content filters</span></span>

- <span data-ttu-id="deeb5-122">Filters voor anti-malware-inhoud</span><span class="sxs-lookup"><span data-stu-id="deeb5-122">Anti-malware content filters</span></span>

- <span data-ttu-id="deeb5-123">Verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="deeb5-123">Connectors</span></span>

- <span data-ttu-id="deeb5-124">Regels voor e-mailstroom (ook wel transportregels genoemd)</span><span class="sxs-lookup"><span data-stu-id="deeb5-124">Mail flow rules (also known as transport rules)</span></span>

  > [!NOTE]
  > <span data-ttu-id="deeb5-125">Cmdlet-ondersteuning voor het exporteren en importeren van de verzameling e-mailstromenregels wordt momenteel alleen ondersteund voor EOP Premium-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="deeb5-125">Cmdlet support for the export and import of the mail flow rule collection is currently only supported for EOP Premium subscription plans.</span></span>

<span data-ttu-id="deeb5-126">De eenvoudigste manier om al uw instellingen te verzamelen, is door PowerShell te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="deeb5-126">The easiest way to collect all of your settings is to use PowerShell.</span></span> <span data-ttu-id="deeb5-127">Zie Verbinding maken met Exchange [Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)als u verbinding wilt maken met Exchange Online Protection PowerShell.</span><span class="sxs-lookup"><span data-stu-id="deeb5-127">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

<span data-ttu-id="deeb5-128">Vervolgens u al uw instellingen verzamelen en exporteren naar een .xml-bestand dat moet worden geïmporteerd in de doeltenant.</span><span class="sxs-lookup"><span data-stu-id="deeb5-128">Next, you can collect all your settings and export them to an .xml file to be imported into the target tenant.</span></span> <span data-ttu-id="deeb5-129">In het algemeen u de uitvoer van de **cmdlet Get** voor elke instelling naar de cmdlet **Exporteren-Clixml** geleid om de instellingen in XML-bestanden op te slaan, zoals in het volgende codevoorbeeld wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="deeb5-129">In general, you can pipe the output of the **Get** cmdlet for each setting to the **Export-Clixml** cmdlet to save the settings in .xml files, as shown in the following code sample.</span></span>

<span data-ttu-id="deeb5-130">Maak in Exchange Online Protection PowerShell een map met de naam Exporteren op een locatie die gemakkelijk te vinden en te wijzigen is in die map.</span><span class="sxs-lookup"><span data-stu-id="deeb5-130">In Exchange Online Protection PowerShell, create a directory called Export in a location that's easy to find and change to that directory.</span></span> <span data-ttu-id="deeb5-131">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="deeb5-131">For example:</span></span>

```PowerShell
mkdir C:\EOP\Export
```

```PowerShell
cd C:\EOP\Export
```

<span data-ttu-id="deeb5-132">Het volgende script kan worden gebruikt om alle e-mailgebruikers, groepen, antispam-instellingen, anti-malware-instellingen, connectors en regels voor e-mailstromen in de bronorganisatie te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="deeb5-132">The following script can be used to collect all the mail users, groups, anti-spam settings, anti-malware settings, connectors, and mail flow rules in the source organization.</span></span> <span data-ttu-id="deeb5-133">Kopieer en plak de volgende tekst in een teksteditor zoals Kladblok, sla het bestand op als Source_EOP_Settings.ps1 in de map Exporteren die u zojuist hebt gemaakt en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="deeb5-133">Copy and paste the following text into a text editor like Notepad, save the file as Source_EOP_Settings.ps1 in the Export directory you just created, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Source_EOP_Settings.ps1"
```

```PowerShell
#****************************************************************************
# Export Domains
#*****************************************************************************
Get-AcceptedDomain | Export-Clixml Domains.xml
#****************************************************************************
# Export mail users
#
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUser | Export-Clixml MailUsers.xml
#****************************************************************************
# Groups
#
# If you're using directory synchronization, you can skip this step and
# simply sync to the target
# tenant.
# First, you need to capture information about the distribution groups.
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalDistributionGroup | Export-Clixml DistributionGroups.xml
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalSecurityGroup | Export-Clixml SecurityGroups.xml
#****************************************************************************
# And then we'll use that output to loop through each group and get the
# members.
#****************************************************************************
$DGs = Import-Clixml .\DistributionGroups.xml
ForEach ($dg in $DGs) {Get-DistributionGroupMember -Identity $dg.name | Export-Clixml $dg.ExternalDirectoryObjectId}
$SGs = Import-Clixml .\SecurityGroups.xml
ForEach ($sg in $SGs) {Get-DistributionGroupMember -Identity $sg.name | Export-Clixml $sg.ExternalDirectoryObjectId}
#*****************************************************************************
# Export dynamic distribution groups - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply
# sync to the target tenant.
#*****************************************************************************
Get-DynamicDistributionGroup -ResultSize unlimited | Export-Clixml DynamicDistributionGroups.xml
#*****************************************************************************
# Export mail contacts - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply
# sync to the target tenant.
#*****************************************************************************
Get-MailContact -ResultSize unlimited -RecipientTypeDetails MailContact | Export-Clixml MailContacts.xml
#****************************************************************************
# Anti-spam
#****************************************************************************
Get-HostedConnectionFilterPolicy | Export-Clixml HostedConnectionFilterPolicy.xml
Get-HostedContentFilterPolicy | Export-Clixml HostedContentFilterPolicy.xml
Get-HostedContentFilterRule | Export-Clixml HostedContentFilterRule.xml
Get-HostedOutboundSpamFilterPolicy | Export-Clixml HostedOutboundSpamFilterPolicy.xml
#****************************************************************************
# Anti-malware content filters
#****************************************************************************
Get-MalwareFilterPolicy | Export-Clixml MalwareFilterPolicy.xml
Get-MalwareFilterRule | Export-Clixml MalwareFilterRule.xml
#****************************************************************************
# Connectors
#****************************************************************************
Get-InboundConnector | Export-Clixml InboundConnector.xml
Get-OutboundConnector | Export-Clixml OutboundConnector.xml
#****************************************************************************
# Exchange mail flow rules
#****************************************************************************
$file = Export-TransportRuleCollection
Set-Content -Path ".TransportRules.xml" -Value $file.FileData -Encoding Byte
```

<span data-ttu-id="deeb5-134">Voer de volgende opdrachten uit de map Exporteren uit om de XML-bestanden bij te werken met de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="deeb5-134">Run the following commands from the Export directory to update the .xml files with the target organization.</span></span> <span data-ttu-id="deeb5-135">Vervang contoso.onmicrosoft.com en contososuites.onmicrosoft.com door de namen van uw bron en doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="deeb5-135">Replace contoso.onmicrosoft.com and contososuites.onmicrosoft.com with your source and target organization names.</span></span>

```PowerShell
$files = ls
ForEach ($file in $files) { (Get-Content $file.Name) | Foreach-Object {$_ -replace 'contoso.onmicrosoft.com', 'contososuites.onmicrosoft.com'} | Set-Content $file.Name}
```

## <a name="step-2-add-domains-to-the-target-organization"></a><span data-ttu-id="deeb5-136">Stap 2: Domeinen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="deeb5-136">Step 2: Add domains to the target organization</span></span>

<span data-ttu-id="deeb5-137">Voeg domeinen toe aan de doelorganisatie met behulp van het volgende script.</span><span class="sxs-lookup"><span data-stu-id="deeb5-137">Add domains to the target organization by using the following script.</span></span> <span data-ttu-id="deeb5-138">Kopieer en plak de tekst in een teksteditor zoals Kladblok, sla het script op als C:\EOP\Export\Add_Domains.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="deeb5-138">Copy and paste the text into a text editor like Notepad, save the script as C:\EOP\Export\Add_Domains.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Add_Domains.ps1"
```

<span data-ttu-id="deeb5-139">Deze domeinen worden niet geverifieerd en kunnen niet worden gebruikt om e-mail te routeren, maar nadat de domeinen zijn toegevoegd, u de informatie verzamelen die nodig is om de domeinen te verifiëren en uiteindelijk uw MX-records voor de nieuwe tenant bij te werken.</span><span class="sxs-lookup"><span data-stu-id="deeb5-139">These domains won't be verified and can't be used to route mail, but after the domains are added, you can collect the information needed to verify the domains and eventually update your MX records for the new tenant.</span></span>

```PowerShell
#***********************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred = Get-Credential
connect-msolservice -credential $msolcred
#****************************************************************************
# Add domains
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
Foreach ($domain in $Domains) {
    New-MsolDomain -Name $domain.Name
}
```

<span data-ttu-id="deeb5-140">Nu u de informatie bekijken en verzamelen uit het Microsoft 365-beheercentrum van uw doelorganisatie, zodat u uw domeinen snel verifiëren wanneer het zover is:</span><span class="sxs-lookup"><span data-stu-id="deeb5-140">Now you can review and collect the information from the Microsoft 365 admin center of your target organization so you can quickly verify your domains when the time comes:</span></span>

1. <span data-ttu-id="deeb5-141">Meld u aan bij het Microsoft [https://portal.office.com](https://portal.office.com)365-beheercentrum op .</span><span class="sxs-lookup"><span data-stu-id="deeb5-141">Sign in to the Microsoft 365 admin center at [https://portal.office.com](https://portal.office.com).</span></span>

2. <span data-ttu-id="deeb5-142">Klik **op Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="deeb5-142">Click **Domains**.</span></span>

3. <span data-ttu-id="deeb5-143">Klik op elke koppeling **Start-installatie** en ga vervolgens door de wizard Setup.</span><span class="sxs-lookup"><span data-stu-id="deeb5-143">Click each **Start setup** link, and then proceed through the setup wizard.</span></span>

4. <span data-ttu-id="deeb5-144">Selecteer op de pagina **Eigendom bevestigen** voor **Stapsgewijze instructies voor het uitvoeren van deze stap met**De optie Algemene **instructies**.</span><span class="sxs-lookup"><span data-stu-id="deeb5-144">On the **Confirm ownership** page, for **See step-by-step instructions for performing this step with**, select **General instructions**.</span></span>

5. <span data-ttu-id="deeb5-145">Neem de MX-record of TXT-record op die u gebruikt om uw domein te verifiëren en de wizard Setup af te ronden.</span><span class="sxs-lookup"><span data-stu-id="deeb5-145">Record the MX record or TXT record that you'll use to verify your domain, and finish the setup wizard.</span></span>

6. <span data-ttu-id="deeb5-146">Voeg de verificatie-TXT-records toe aan uw DNS-records.</span><span class="sxs-lookup"><span data-stu-id="deeb5-146">Add the verification TXT records to your DNS records.</span></span> <span data-ttu-id="deeb5-147">Hiermee u sneller de domeinen in de bronorganisatie verifiëren nadat ze uit de doelorganisatie zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="deeb5-147">This will let you more quickly verify the domains in the source organization after they're removed from the target organization.</span></span> <span data-ttu-id="deeb5-148">Zie [DNS-records maken bij elke DNS-hostingprovider voor Office 365 voor](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="deeb5-148">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

## <a name="step-3-force-senders-to-queue-mail"></a><span data-ttu-id="deeb5-149">Stap 3: Afzenders dwingen om e-mail in de wachtrij te plaatsen</span><span class="sxs-lookup"><span data-stu-id="deeb5-149">Step 3: Force senders to queue mail</span></span>

<span data-ttu-id="deeb5-150">Terwijl u uw domeinen van de ene tenant naar de andere verplaatst, moet u de domeinen uit de bronorganisatie verwijderen en deze vervolgens verifiëren in uw doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="deeb5-150">While moving your domains from one tenant to another, you'll need to delete the domains from the source organization and then verify them in your target organization.</span></span> <span data-ttu-id="deeb5-151">Gedurende deze periode u geen e-mail routeren via EOP.</span><span class="sxs-lookup"><span data-stu-id="deeb5-151">During this time, you won't be able to route mail through EOP.</span></span>

<span data-ttu-id="deeb5-152">Een optie om afzenders te dwingen in de wachtrij te staan, is door uw MX-records bij te werken om rechtstreeks naar uw on-premises e-mailserver te wijzen.</span><span class="sxs-lookup"><span data-stu-id="deeb5-152">One option to force senders to queue mail is to update your MX records to point directly to your on-premises mail server.</span></span>

<span data-ttu-id="deeb5-153">Een andere optie is om een ongeldige MX-record in elk domein te plaatsen waar de DNS-records voor uw domein worden bewaard (ook wel uw DNS-hostingservice genoemd).</span><span class="sxs-lookup"><span data-stu-id="deeb5-153">Another option is to put an invalid MX record in each domain where the DNS records for your domain are kept (also known as your DNS hosting service).</span></span> <span data-ttu-id="deeb5-154">Dit zal ertoe leiden dat de afzender in de wachtrij van uw e-mail en opnieuw proberen (typische pogingen opnieuw proberen zijn voor 48 uur, maar dit kan variëren van provider tot provider).</span><span class="sxs-lookup"><span data-stu-id="deeb5-154">This will cause the sender to queue your mail and retry (typical retry attempts are for 48 hours, but this might vary from provider to provider).</span></span> <span data-ttu-id="deeb5-155">U invalid.outlook.com gebruiken als ongeldig MX-doel.</span><span class="sxs-lookup"><span data-stu-id="deeb5-155">You can use invalid.outlook.com as an invalid MX target.</span></span> <span data-ttu-id="deeb5-156">Door de Waarde Time to Live (TTL) te verlagen tot vijf minuten op de MX-record, wordt de wijziging sneller doorgevoerd in DNS-providers.</span><span class="sxs-lookup"><span data-stu-id="deeb5-156">Lowering the Time to Live (TTL) value to five minutes on the MX record will help the change propagate to DNS providers more quickly.</span></span>

<span data-ttu-id="deeb5-157">Zie [DNS-records maken bij elke DNS-hostingprovider voor Office 365 voor](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="deeb5-157">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="deeb5-158">Verschillende providers wachtrij e-mail voor verschillende perioden.</span><span class="sxs-lookup"><span data-stu-id="deeb5-158">Different providers queue mail for different periods of time.</span></span> <span data-ttu-id="deeb5-159">U moet uw nieuwe tenant snel instellen en uw DNS-instellingen terugdraaien om te voorkomen dat niet-leveringsrapporten (NDR's) naar de afzender worden verzonden als de wachtrijtijd verstrijkt.</span><span class="sxs-lookup"><span data-stu-id="deeb5-159">You'll need to set up your new tenant quickly and revert your DNS settings to avoid non-delivery reports (NDRs) from being sent to the sender if the queuing time expires.</span></span>

## <a name="step-4-remove-users-groups-and-domains-from-the-source-organization"></a><span data-ttu-id="deeb5-160">Stap 4: Gebruikers, groepen en domeinen verwijderen uit de bronorganisatie</span><span class="sxs-lookup"><span data-stu-id="deeb5-160">Step 4: Remove users, groups, and domains from the source organization</span></span>

<span data-ttu-id="deeb5-161">In het volgende script worden gebruikers, groepen en domeinen uit de brontenant verwijderd met Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="deeb5-161">The following script removes users, groups, and domains from the source tenant by using Azure Active Directory PowerShell.</span></span> <span data-ttu-id="deeb5-162">Kopieer en plak de volgende tekst in een teksteditor zoals Kladblok, sla het bestand op als C:\EOP\Export\Remove_Users_and_Groups.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="deeb5-162">Copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Remove_Users_and_Groups.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Remove_Users_and_Groups.ps1"
```

```PowerShell
#*****************************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred= Get-Credential
connect-msolservice -credential $msolcred
#*****************************************************************************
# Remove users
#*****************************************************************************
$Users = Get-MSOLUser -All | sort UserPrincipalName
$user_count = $Users.count
write-host "Removing $user_count users."
Foreach ($User in $Users) {
write-host $User.UserPrincipalName
$User | Remove-MSOLUser -Force
}
#*****************************************************************************
# Remove groups
#*****************************************************************************
Get-MSOLGroup | Remove-MSOLGroup -Force
#*****************************************************************************
# Remove domains
# Note: Your onmicrosoft.com domain should be the default domain
#*****************************************************************************
$Domains = Get-MsolDomain
$Domain_count = $Domains.count
write-host "Removing $Domain_count domains."
Foreach ($Domain in $Domains) {
write-host $Domain.Name
Remove-MsolDomain -DomainName $Domain.Name -Force
}
```

## <a name="step-5-verify-domains-for-the-target-organization"></a><span data-ttu-id="deeb5-163">Stap 5: Domeinen voor de doelorganisatie verifiëren</span><span class="sxs-lookup"><span data-stu-id="deeb5-163">Step 5: Verify domains for the target organization</span></span>

1. <span data-ttu-id="deeb5-164">Meld u aan bij [https://portal.office.com](https://portal.office.com)het beheercentrum op .</span><span class="sxs-lookup"><span data-stu-id="deeb5-164">Sign in to the admin center at [https://portal.office.com](https://portal.office.com).</span></span>

2. <span data-ttu-id="deeb5-165">Klik **op Domeinen**.</span><span class="sxs-lookup"><span data-stu-id="deeb5-165">Click **Domains**.</span></span>

3. <span data-ttu-id="deeb5-166">Klik op elke koppeling **Start-installatie** voor het doeldomein en ga verder met de wizard Setup.</span><span class="sxs-lookup"><span data-stu-id="deeb5-166">Click each **Start setup** link for the target domain and proceed through the setup wizard.</span></span>

## <a name="step-6-add-mail-users-and-groups-to-the-target-organization"></a><span data-ttu-id="deeb5-167">Stap 6: E-mailgebruikers en -groepen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="deeb5-167">Step 6: Add mail users and groups to the target organization</span></span>

<span data-ttu-id="deeb5-168">Een aanbevolen toepassing voor EOP is het gebruik van Azure Active Directory om uw on-premises Active Directory te synchroniseren met uw doeltenant.</span><span class="sxs-lookup"><span data-stu-id="deeb5-168">A best practice for EOP is to use Azure Active Directory to sync your on-premises Active Directory to your target tenant.</span></span> <span data-ttu-id="deeb5-169">Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' [voor](manage-mail-users-in-eop.md)meer informatie over hoe u dit doen.</span><span class="sxs-lookup"><span data-stu-id="deeb5-169">For more information about how to do this, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="deeb5-170">U ook het volgende script gebruiken om uw gebruikers en groepen opnieuw te maken vanuit uw brontenant.</span><span class="sxs-lookup"><span data-stu-id="deeb5-170">You can also use the following script to recreate your users and groups from your source tenant.</span></span> <span data-ttu-id="deeb5-171">Opmerking: Gebruikerswachtwoorden kunnen niet worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="deeb5-171">Note: User passwords cannot be moved.</span></span> <span data-ttu-id="deeb5-172">Er worden nieuwe gebruikerswachtwoorden gemaakt en opgeslagen in het bestand met de naam UsersAndGroups.ps1.</span><span class="sxs-lookup"><span data-stu-id="deeb5-172">New user passwords are created and saved in the file named UsersAndGroups.ps1.</span></span>

<span data-ttu-id="deeb5-173">Als u het script wilt gebruiken, kopieert en plakt u de volgende tekst in een teksteditor zoals Kladblok, slaat u het bestand op als C:\EOP\Export\Add_Users_and_Groups.ps1 en voert u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="deeb5-173">To use the script, copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Add_Users_and_Groups.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Add_Users_and_Groups.ps1"
```

```PowerShell
#***********************************************************************
# makeparam helper function
#****************************************************************************
function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-MailUser"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPMailUser"
        }
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress

        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }

        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-DistributionGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        }
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy

        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-SecurityGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPSecurityGroup"
        }
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy

        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Synamic Distribution Groups for EOP Standard organizations."
}else{
    $DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
    $DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
    if($DynamicDistributionGroupsCount -gt 0){
        Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
        foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
            $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup"
            $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
            $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName
            $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy
            $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled
            $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name
            $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress
            $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
            $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
            $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
            $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
            $RecipientFilterParam += "}"
            $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
            $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications
            Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
        }

    }else{
        Write-Host "No Dynamic Distribution Groups to add."
    }
}
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Mail Contact for EOP Standard organizations."
}else{
    $MailContacts = Import-Clixml ".\MailContacts.xml"
    $MailContactsCount = $MailContacts.Name.Count
    if($MailContactsCount -gt 0){
        Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
        foreach ($MailContact in $MailContacts) {
            $MailContactsCmdlet = "New-MailContact"
            $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
            $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
            $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
            $MailContactsCmdlet += makeparam "Name" $MailContact.Name
            $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
            $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
            $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
            $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
            $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
            $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
            $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
            $MailContactsCmdlet += " -Confirm:`$False"
            $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
            $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
            $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
            Add-Content $outfile "`n$MailContactsCmdlet"
        }

    }else{
        Write-Host "No Mail Contacts to add."
    }
}
#***********************************************************************
# makeparam helper function
#************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-EOPMailUser"
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress

        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }

        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy

        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-EOPSecurityGroup"
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy

        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
$DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
$DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
if($DynamicDistributionGroupsCount -gt 0){
    Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
    foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
        $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup"
        $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
        $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName
        $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy
        $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled
        $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name
        $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress
        $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
        $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
        $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
        $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
        $RecipientFilterParam += "}"
        $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
        $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications
        Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
    }

}else{
    Write-Host "No Dynamic Distribution Groups to add."
}
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
$MailContacts = Import-Clixml ".\MailContacts.xml"
$MailContactsCount = $MailContacts.Name.Count
if($MailContactsCount -gt 0){
    Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
    foreach ($MailContact in $MailContacts) {
        $MailContactsCmdlet = "New-MailContact"
        $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
        $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
        $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
        $MailContactsCmdlet += makeparam "Name" $MailContact.Name
        $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
        $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
        $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
        $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
        $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
        $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
        $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
        $MailContactsCmdlet += " -Confirm:`$False"
        $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
        $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
        $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
        Add-Content $outfile "`n$MailContactsCmdlet"
    }

}else{
    Write-Host "No Mail Contacts to add."
}
```

## <a name="step-7-add-protection-settings-to-the-target-organization"></a><span data-ttu-id="deeb5-174">Stap 7: Beveiligingsinstellingen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="deeb5-174">Step 7: Add protection settings to the target organization</span></span>

<span data-ttu-id="deeb5-175">U het volgende script uitvoeren vanuit de map Exporteren terwijl u bent aangemeld bij uw doelorganisatie om de instellingen opnieuw te maken die eerder vanuit de bronorganisatie naar .xml-bestanden zijn geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="deeb5-175">You can run the following script from the Export directory while logged in to your target organization to recreate the settings exported to .xml files earlier from the source organization.</span></span>

<span data-ttu-id="deeb5-176">Kopieer en plak de scripttekst in een teksteditor zoals Kladblok, sla het bestand op als C:\EOP\Export\Import_Settings.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="deeb5-176">Copy and paste the script text into a text editor like Notepad, save the file as C:\EOP\Export\Import_Settings.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Import_Settings.ps1"
```

<span data-ttu-id="deeb5-177">Dit script importeert de .xml-bestanden en maakt een Windows PowerShell-scriptbestand met de naam Settings.ps1, dat u bekijken, bewerken en vervolgens uitvoeren om uw beveiligings- en e-mailstroominstellingen opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="deeb5-177">This script imports the .xml files and create a Windows PowerShell script file called Settings.ps1 that you can review, edit, and then run to recreate your protection and mail-flow settings.</span></span>

```PowerShell
#***********************************************************************
# makeparam helper function
#****************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\Settings.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# HostedContentFilterPolicy
#****************************************************************************
$HostedContentFilterPolicys = Import-Clixml ".\HostedContentFilterPolicy.xml"
$HostedContentFilterPolicyCount = $HostedContentFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterPolicyCount Inbound Connectors"
    ForEach ($HostedContentFilterPolicy in $HostedContentFilterPolicys) {
        $HostedContentFilterPolicyCmdlet = "New-HostedContentFilterPolicy"
        if($HostedContentFilterPolicy.Name -eq "Default") {$HostedContentFilterPolicyCmdlet = "Set-HostedContentFilterPolicy -Identity Default"}
        else {
        $HostedContentFilterPolicyCmdlet += makeparam "Name" $HostedContentFilterPolicy.Name
        }
        $HostedContentFilterPolicyCmdlet += makeparam "AddXHeaderValue" $HostedContentFilterPolicy.AddXHeaderValue
        $HostedContentFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedContentFilterPolicy.AdminDisplayName
        $HostedContentFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedContentFilterPolicyCmdlet += makeparam "DownloadLink" $HostedContentFilterPolicy.DownloadLink
        $HostedContentFilterPolicyCmdlet += makeparam "EnableEndUserSpamNotifications" $HostedContentFilterPolicy.EnableEndUserSpamNotifications
        $HostedContentFilterPolicyCmdlet += makeparam "EnableLanguageBlockList" $HostedContentFilterPolicy.EnableLanguageBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "EnableRegionBlockList" $HostedContentFilterPolicy.EnableRegionBlockList
        if($HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress.Length -gt 0)
        {
            $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromAddress" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress
        }
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromName" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromName
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomSubject" $HostedContentFilterPolicy.EndUserSpamNotificationCustomSubject
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationFrequency" $HostedContentFilterPolicy.EndUserSpamNotificationFrequency
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationLanguage" $HostedContentFilterPolicy.EndUserSpamNotificationLanguage
        $HostedContentFilterPolicyCmdlet += makeparam "LanguageBlockList" $HostedContentFilterPolicy.LanguageBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamBulkMail" $HostedContentFilterPolicy.MarkAsSpamBulkMail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmbedTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamEmbedTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmptyMessages" $HostedContentFilterPolicy.MarkAsSpamEmptyMessages
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFormTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamFormTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFramesInHtml" $HostedContentFilterPolicy.MarkAsSpamFramesInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFromAddressAuthFail" $HostedContentFilterPolicy.MarkAsSpamFromAddressAuthFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamJavaScriptInHtml" $HostedContentFilterPolicy.MarkAsSpamJavaScriptInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamNdrBackscatter" $HostedContentFilterPolicy.MarkAsSpamNdrBackscatter
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamObjectTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamObjectTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSensitiveWordList" $HostedContentFilterPolicy.MarkAsSpamSensitiveWordList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSpfRecordHardFail" $HostedContentFilterPolicy.MarkAsSpamSpfRecordHardFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamWebBugsInHtml" $HostedContentFilterPolicy.MarkAsSpamWebBugsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "ModifySubjectValue" $HostedContentFilterPolicy.ModifySubjectValue
        $HostedContentFilterPolicyCmdlet += makeparam "Organization" $HostedContentFilterPolicy.Organization
        $HostedContentFilterPolicyCmdlet += makeparam "QuarantineRetentionPeriod" $HostedContentFilterPolicy.QuarantineRetentionPeriod
        $HostedContentFilterPolicyCmdlet += makeparam "RedirectToRecipients" $HostedContentFilterPolicy.RedirectToRecipients
        $HostedContentFilterPolicyCmdlet += makeparam "RegionBlockList" $HostedContentFilterPolicy.RegionBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "SpamAction" $HostedContentFilterPolicy.SpamAction
        $HostedContentFilterPolicyCmdlet += makeparam "TestModeBccToRecipients" $HostedContentFilterPolicy.TestModeBccToRecipients
        Add-Content $outfile "`n$HostedContentFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Policy Filters to add."
 }
#****************************************************************************
# HostedContentFilterRule
#****************************************************************************
$HostedContentFilterRules = Import-Clixml ".\HostedContentFilterRule.xml"
$HostedContentFilterRuleCount = $HostedContentFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterRuleCount Hosted Content Filter Rules"
    ForEach ($HostedContentFilterRule in $HostedContentFilterRules) {
        $HostedContentFilterRuleCmdlet = "New-HostedContentFilterRule"
        if($HostedContentFilterRule.Name -eq "Default") {$HostedContentFilterRuleCmdlet = "Set-HostedContentFilterRule Default"}
        $HostedContentFilterRuleCmdlet += makeparam "Name" $HostedContentFilterRule.Name
        $HostedContentFilterRuleCmdlet  += makeparam "HostedContentFilterPolicy" $HostedContentFilterRule.HostedContentFilterPolicy
        $HostedContentFilterRuleCmdlet += makeparam "Comments" $HostedContentFilterRule.Comments
        $HostedContentFilterRuleCmdlet += " -Confirm:`$False"
        $HostedContentFilterRuleCmdlet += makeparam "Enabled" $HostedContentFilterRule.Enabled
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $HostedContentFilterRule.ExceptIfRecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentTo" $HostedContentFilterRule.ExceptIfSentTo
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $HostedContentFilterRule.ExceptIfSentToMemberOf
        $HostedContentFilterRuleCmdlet += makeparam "Priority" $HostedContentFilterRule.Priority
        $HostedContentFilterRuleCmdlet += makeparam "RecipientDomainIs" $HostedContentFilterRule.RecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "SentTo" $HostedContentFilterRule.SentTo
        $HostedContentFilterRuleCmdlet += makeparam "SentToMemberOf" $HostedContentFilterRule.SentToMemberOf
        Add-Content $outfile "`n$HostedContentFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Filter Rules to add."
 }
#****************************************************************************
# HostedOutboundSpamFilterPolicy
#****************************************************************************
$HostedOutboundSpamFilterPolicys = Import-Clixml ".\HostedOutboundSpamFilterPolicy.xml"
$HostedOutboundSpamFilterPolicyCount = $HostedOutboundSpamFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedOutboundSpamFilterPolicyCount Hosted Outbound Spam Filter Policies"
    ForEach ($HostedOutboundSpamFilterPolicy in $HostedOutboundSpamFilterPolicys) {
        $HostedOutboundSpamFilterPolicyCmdlet = "Set-HostedOutboundSpamFilterPolicy Default"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedOutboundSpamFilterPolicy.AdminDisplayName
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundAdditionalRecipients"
        $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundAdditionalRecipients
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundMail" $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundMail
        $HostedOutboundSpamFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "NotifyOutboundSpam" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpam
        $NotifyOutboundSpamRecipients  += makeparam "NotifyOutboundSpamRecipients" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpamRecipients
        Add-Content $outfile "`n$HostedOutboundSpamFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Outbound Spam Filter Policies to add."
 }
#****************************************************************************
# HostedConnectionFilterPolicy
#****************************************************************************
$HostedConnectionFilterPolicys = Import-Clixml ".\HostedConnectionFilterPolicy.xml"
$HostedConnectionFilterPolicyCount = $HostedConnectionFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedConnectionFilterPolicyCount Hosted Connection Filter Policies"
    ForEach ($HostedConnectionFilterPolicy in $HostedConnectionFilterPolicys) {
        $HostedConnectionFilterPolicyCmdlet = "Set-HostedConnectionFilterPolicy"
        $HostedConnectionFilterPolicyCmdlet += makeparam "Identity" $HostedConnectionFilterPolicy.Name
        $HostedConnectionFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedConnectionFilterPolicy.AdminDisplayName
        $HostedConnectionFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedConnectionFilterPolicyCmdlet += makeparam "EnableSafeList" $HostedConnectionFilterPolicy.EnableSafeList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPAllowList" $HostedConnectionFilterPolicy.IPAllowList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPBlockList" $HostedConnectionFilterPolicy.IPBlockList

        Add-Content $outfile "`n$HostedConnectionFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Connection Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterPolicy
#****************************************************************************
$MalwareFilterPolicys = Import-Clixml ".\MalwareFilterPolicy.xml"
$MalwareFilterPolicyCount = $MalwareFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterPolicyCount Malware Filter Policies"
    ForEach ($MalwareFilterPolicy in $MalwareFilterPolicys) {
        $MalwareFilterPolicyCmdlet = "New-MalwareFilterPolicy"
        if($MalwareFilterPolicy.Name -eq "Default") {$MalwareFilterPolicyCmdlet = "Set-MalwareFilterPolicy Default"}
        else {
        $MalwareFilterPolicyCmdlet += makeparam "Name" $MalwareFilterPolicy.Name
        }
        $MalwareFilterPolicyCmdlet += makeparam "Action" $MalwareFilterPolicy.Action
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseDefaultAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseDefaultAlertText
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseCustomAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseCustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "AdminDisplayName" $MalwareFilterPolicy.AdminDisplayName
        $MalwareFilterPolicyCmdlet += " -Confirm:`$False"
        $MalwareFilterPolicyCmdlet += makeparam "CustomAlertText" $MalwareFilterPolicy.CustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalBody" $MalwareFilterPolicy.CustomExternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalSubject" $MalwareFilterPolicy.CustomExternalSubject
        if($MalwareFilterPolicy.CustomFromAddress.Length -gt 0) {
            $MalwareFilterPolicyCmdlet += makeparam "CustomFromAddress" $MalwareFilterPolicy.CustomFromAddress
        }
        $MalwareFilterPolicyCmdlet += makeparam "CustomFromName" $MalwareFilterPolicy.CustomFromName
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalBody" $MalwareFilterPolicy.CustomInternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalSubject" $MalwareFilterPolicy.CustomInternalSubject
        $MalwareFilterPolicyCmdlet += makeparam "CustomNotifications" $MalwareFilterPolicy.CustomNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderAdminNotifications" $MalwareFilterPolicy.EnableExternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderNotifications" $MalwareFilterPolicy.EnableExternalSenderNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderAdminNotifications" $MalwareFilterPolicy.EnableInternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderNotifications" $MalwareFilterPolicy.EnableInternalSenderNotifications
        if($MalwareFilterPolicy.ExternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "ExternalSenderAdminAddress" $MalwareFilterPolicy.ExternalSenderAdminAddress
        }
        if($MalwareFilterPolicy.InternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "InternalSenderAdminAddress" $MalwareFilterPolicy.InternalSenderAdminAddress
        }
        Add-Content $outfile "`n$MalwareFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterRule
#****************************************************************************
$MalwareFilterRules = Import-Clixml ".\MalwareFilterRule.xml"
$MalwareFilterRuleCount = $MalwareFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterRuleCount Malware Filter Rules"
    ForEach ($MalwareFilterRule in $MalwareFilterRules) {
        $MalwareFilterRuleCmdlet = "New-MalwareFilterRule"
        if($MalwareFilterRule.Name -eq "Default") {$MalwareFilterRuleCmdlet = "Set-MalwareFilterPolicy Default"}
        $MalwareFilterRuleCmdlet += makeparam "Name" $MalwareFilterRule.Name
        $MalwareFilterRuleCmdlet += makeparam "MalwareFilterPolicy" $MalwareFilterRule.MalwareFilterPolicy
        $MalwareFilterRuleCmdlet += makeparam "Comments" $MalwareFilterRule.Comments
        $MalwareFilterRuleCmdlet += " -Confirm:`$False"
        $MalwareFilterRuleCmdlet += makeparam "Enabled" $MalwareFilterRule.Enabled
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $MalwareFilterRule.ExceptIfRecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentTo" $MalwareFilterRule.ExceptIfSentTo
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $MalwareFilterRule.ExceptIfSentToMemberOf
        $MalwareFilterRuleCmdlet += makeparam "RecipientDomainIs" $MalwareFilterRule.RecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "SentTo" $MalwareFilterRule.SentTo
        $MalwareFilterRuleCmdlet += makeparam "SentToMemberOf" $MalwareFilterRule.SentToMemberOf
        Add-Content $outfile "`n$MalwareFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Rules to add."
 }
#****************************************************************************
# InboundConnectors
#****************************************************************************
$InboundConnectors = Import-Clixml ".\InboundConnector.xml"
$InboundConnectorCount = $InboundConnectors.Name.Count
if($InboundConnectorCount -gt 0){
    Write-Host "Importing $InboundConnectorCount Inbound Connectors"
    ForEach ($InboundConnector in $InboundConnectors) {
        $InboundConnectorCmdlet = "New-InboundConnector"
        $InboundConnectorCmdlet += makeparam "Name" $InboundConnector.Name
        $InboundConnectorCmdlet += makeparam "SenderDomains" $InboundConnector.SenderDomains

        If($InboundConnector.AssociatedAcceptedDomains.Count -gt 0) {
            If($InboundConnector.AssociatedAcceptedDomains[0].Contains("/")) {
                # This connector was created in an EOP Standard tenant
                # Strip out just the domain name
                $InboundConnectorCmdlet += " -AssociatedAcceptedDomains "
                ForEach  ($accepteddomain in $InboundConnectors.AssociatedAcceptedDomains) {
                    $accepteddomain = $accepteddomain.SubString($accepteddomain.LastIndexOf("/")+1)
                    $InboundConnectorCmdlet += "`"$accepteddomain`","
                }
                $InboundConnectorCmdlet = $InboundConnectorCmdlet.TrimEnd(",")
            }else{
                $InboundConnectorCmdlet += makeparam "AssociatedAcceptedDomains" $InboundConnector.AssociatedAcceptedDomains
            }
        }

        $InboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $InboundConnector.CloudServicesMailEnabled
        $InboundConnectorCmdlet += makeparam "Comment" $InboundConnector.Comment
        $InboundConnectorCmdlet += " -Confirm:`$False"
        $InboundConnectorCmdlet += makeparam "ConnectorSource" $InboundConnector.ConnectorSource
        $InboundConnectorCmdlet += makeparam "ConnectorType" $InboundConnector.ConnectorType
        $InboundConnectorCmdlet += makeparam "Enabled" $InboundConnector.Enabled
        $InboundConnectorCmdlet += makeparam "RequireTls" $InboundConnector.RequireTls
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToCertificate" $InboundConnector.RestrictDomainsToCertificate
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToIPAddresses" $InboundConnector.RestrictDomainsToIPAddresses
        $InboundConnectorCmdlet += makeparam "SenderIPAddresses" $InboundConnector.SenderIPAddresses
        $InboundConnectorCmdlet += makeparam "TlsSenderCertificateName" $InboundConnector.TlsSenderCertificateName
        Add-Content $outfile "`n$InboundConnectorCmdlet"
     }
}else{
    Write-Host "No Inbound Connectors to add."
 }
#****************************************************************************
# OutboundConnector
#****************************************************************************
$OutboundConnectors = Import-Clixml ".\OutboundConnector.xml"
$OutboundConnectorCount = $OutboundConnectors.Name.Count
if($OutboundConnectorCount -gt 0){
    Write-Host "Importing $OutboundConnectorCount Outbound Connectors"
    ForEach ($OutboundConnector in $OutboundConnectors) {
        $OutboundConnectorCmdlet = "New-OutboundConnector"
        $OutboundConnectorCmdlet += makeparam "Name" $OutboundConnector.Name
        $OutboundConnectorCmdlet += makeparam "AllAcceptedDomains" $OutboundConnector.AllAcceptedDomains
        $OutboundConnectorCmdlet += makeparam "BypassValidation" $OutboundConnector.BypassValidation
        $OutboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $OutboundConnector.CloudServicesMailEnabled
        $OutboundConnectorCmdlet += makeparam "Comment" $OutboundConnector.Comment
        $OutboundConnectorCmdlet += " -Confirm:`$False"
        $OutboundConnectorCmdlet += makeparam "ConnectorSource" $OutboundConnector.ConnectorSource
        $OutboundConnectorCmdlet += makeparam "ConnectorType" $OutboundConnector.ConnectorType
        $OutboundConnectorCmdlet += makeparam "IsTransportRuleScoped" $OutboundConnector.IsTransportRuleScoped
        $OutboundConnectorCmdlet += makeparam "RecipientDomains" $OutboundConnector.RecipientDomains
        $OutboundConnectorCmdlet += makeparam "RouteAllMessagesViaOnPremises" $OutboundConnector.RouteAllMessagesViaOnPremises
        $OutboundConnectorCmdlet += makeparam "SmartHosts" $OutboundConnector.SmartHosts
        $OutboundConnectorCmdlet += makeparam "TlsDomain" $OutboundConnector.TlsDomain
        $OutboundConnectorCmdlet += makeparam "TlsSettings" $OutboundConnector.TlsSettings
        $OutboundConnectorCmdlet += makeparam "UseMXRecord" $OutboundConnector.UseMXRecord
        Add-Content $outfile "`n$OutboundConnectorCmdlet"
    }
 }else{
    Write-Host "No Outbound Connectors to add."
 }
#*****************************************************************************
# TransportRule
#*****************************************************************************
Add-Content $outfile "`n[Byte[]]$Data = Get-Content -Path `".TransportRules.xml`" -Encoding Byte -ReadCount 0"
Add-Content $outfile "`nImport-TransportRuleCollection -FileData $Data"
#****************************************************************************
# Domain Type
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
$DomainCount = $Domains.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $DomainCount Domains"
    ForEach ($Domain in $Domains) {
        $DomainCmdlet = "Set-AcceptedDomain"
        $DomainCmdlet += makeparam "Identity" $Domain.Name
        $DomainCmdlet += makeparam "DomainType" $Domain.DomainType
        Add-Content $outfile "`n$DomainCmdlet"
    }
 }else{
    Write-Host "No Domains to add."
 }
```

## <a name="step-8-revert-your-dns-settings-to-stop-mail-queuing"></a><span data-ttu-id="deeb5-178">Stap 8: Uw DNS-instellingen terugdraaien om e-mailwachtrijen te stoppen</span><span class="sxs-lookup"><span data-stu-id="deeb5-178">Step 8: Revert your DNS settings to stop mail queuing</span></span>

<span data-ttu-id="deeb5-179">Als u ervoor kiest om uw MX-records in te stellen op een ongeldig adres waardoor de afzenders tijdens uw overgang in de wachtrij staan, moet u deze weer instellen op de juiste waarde zoals opgegeven in het [beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="deeb5-179">If you chose to set your MX records to an invalid address to cause the senders to queue mail during your transition, you'll need to set them back to the correct value as specified in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="deeb5-180">Zie [DNS-records maken bij elke DNS-hostingprovider voor Office 365 voor](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="deeb5-180">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>
