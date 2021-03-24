---
title: Domeinen en & van de ene EOP-organisatie naar de andere verplaatsen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 9d64867b-ebdb-4323-8e30-4560d76b4c97
ms.custom:
- seo-marvel-apr2020
description: In dit artikel leert u hoe u domeinen en instellingen van de ene EOP-organisatie (tenant) van Microsoft Exchange Online Protection (tenant) naar een andere kunt verplaatsen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4a9209f71905a858bb631a3c2901b7bfa62551d7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058870"
---
# <a name="move-domains-and-settings-from-one-eop-organization-to-another"></a><span data-ttu-id="67a2c-103">Domeinen en instellingen van één EOP-organisatie naar een andere verplaatsen</span><span class="sxs-lookup"><span data-stu-id="67a2c-103">Move domains and settings from one EOP organization to another</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67a2c-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="67a2c-104">**Applies to**</span></span>
-  [<span data-ttu-id="67a2c-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="67a2c-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="67a2c-106">Als u de bedrijfsvereisten wilt wijzigen, moet u soms één EOP-organisatie (Microsoft Exchange Online Protection) splitsen in twee afzonderlijke organisaties, twee organisaties samenvoegen in één organisatie of uw domeinen en EOP-instellingen van de ene organisatie naar een andere organisatie verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="67a2c-106">Changing business requirements can sometimes require splitting one Microsoft Exchange Online Protection (EOP) organization (tenant) into two separate organizations, merging two organizations into one, or moving your domains and EOP settings from one organization to another organization.</span></span> <span data-ttu-id="67a2c-107">De overstap van de ene EOP-organisatie naar een tweede EOP-organisatie kan lastig zijn, maar met een paar eenvoudige externe Windows PowerShell-scripts en een kleine hoeveelheid voorbereiding kan dit worden bereikt met een relatief klein onderhoudsvenster.</span><span class="sxs-lookup"><span data-stu-id="67a2c-107">Moving from one EOP organization to a second EOP organization can be challenging, but with a few basic remote Windows PowerShell scripts and a small amount of preparation, this can be achieved with a relatively small maintenance window.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="67a2c-108">Instellingen kunnen alleen betrouwbaar worden verplaatst van een zelfstandige EOP-organisatie (Standard) naar een andere EOP Standard of een Exchange Enterprise CAL with Services-organisatie (EOP Premium) of van een EOP Premium-organisatie naar een andere EOP Premium-organisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-108">Settings can be reliably moved only from an EOP standalone (Standard) organization to either another EOP Standard or an Exchange Enterprise CAL with Services (EOP Premium) organization, or from an EOP Premium organization to another EOP Premium organization.</span></span> <span data-ttu-id="67a2c-109">Omdat sommige premiumfuncties niet worden ondersteund in EOP Standard-organisaties, is de overstap van een EOP Premium-organisatie naar een EOP Standard-organisatie mogelijk niet gelukt.</span><span class="sxs-lookup"><span data-stu-id="67a2c-109">Because some premium features are not supported in EOP Standard organizations, moves from an EOP Premium organization to an EOP Standard organization might not be successful.</span></span>
>
> - <span data-ttu-id="67a2c-110">Deze instructies zijn voor organisaties met alleen EOP-filtering.</span><span class="sxs-lookup"><span data-stu-id="67a2c-110">These instructions are for EOP filtering-only organizations.</span></span> <span data-ttu-id="67a2c-111">Er zijn extra aandachtspunten bij het over te zetten van de ene Exchange Online-organisatie naar een andere Exchange Online-organisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-111">There are additional considerations in moving from one Exchange Online organization to another Exchange Online organization.</span></span> <span data-ttu-id="67a2c-112">Exchange Online-organisaties kunnen deze instructies niet volgen.</span><span class="sxs-lookup"><span data-stu-id="67a2c-112">Exchange Online organizations are out of scope for these instructions.</span></span>

<span data-ttu-id="67a2c-113">In het volgende voorbeeld is Contoso, Ltd. samengevoegd met Contoso Suites.</span><span class="sxs-lookup"><span data-stu-id="67a2c-113">In the following example, Contoso, Ltd. has merged with Contoso Suites.</span></span> <span data-ttu-id="67a2c-114">In de volgende afbeelding ziet u het proces van het verplaatsen van domeinen, e-mailgebruikers en groepen en instellingen van de bron-EOP-organisatie (contoso.onmicrosoft.com) naar de doel-EOP-organisatie (contososuites.onmicrosoft.com):</span><span class="sxs-lookup"><span data-stu-id="67a2c-114">The following image shows the process of moving domains, mail users and groups, and settings from the source EOP organization (contoso.onmicrosoft.com) to the target EOP organization (contososuites.onmicrosoft.com):</span></span>

![EOP-domeinen en -instellingen verplaatsen](../../media/EOP-Move-domains-and-settings.jpg)

<span data-ttu-id="67a2c-116">De uitdaging bij het verplaatsen van domeinen van de ene organisatie naar de andere is dat een geverifieerd domein niet in twee organisaties tegelijk kan bestaan.</span><span class="sxs-lookup"><span data-stu-id="67a2c-116">The challenge in moving domains from one organization to another is that a verified domain can't exist in two organizations at the same time.</span></span> <span data-ttu-id="67a2c-117">De volgende stappen helpen u om dit uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="67a2c-117">The following steps help you work through this.</span></span>

## <a name="step-1-collect-data-from-the-source-organization"></a><span data-ttu-id="67a2c-118">Stap 1: Gegevens verzamelen uit de bronorganisatie</span><span class="sxs-lookup"><span data-stu-id="67a2c-118">Step 1: Collect data from the source organization</span></span>

<span data-ttu-id="67a2c-119">Als u de bronorganisatie in de doelorganisatie opnieuw wilt maken, moet u de volgende informatie over de bronorganisatie verzamelen en opslaan:</span><span class="sxs-lookup"><span data-stu-id="67a2c-119">In order to re-create the source organization in the target organization, make sure that you collect and store the following information about the source organization:</span></span>

- <span data-ttu-id="67a2c-120">Domeinen</span><span class="sxs-lookup"><span data-stu-id="67a2c-120">Domains</span></span>
- <span data-ttu-id="67a2c-121">E-mailgebruikers</span><span class="sxs-lookup"><span data-stu-id="67a2c-121">Mail users</span></span>
- <span data-ttu-id="67a2c-122">Groepen</span><span class="sxs-lookup"><span data-stu-id="67a2c-122">Groups</span></span>
- <span data-ttu-id="67a2c-123">Antispam</span><span class="sxs-lookup"><span data-stu-id="67a2c-123">Anti-spam</span></span>
  - <span data-ttu-id="67a2c-124">Antispambeleid (ook wel inhoudsfilterbeleid genoemd)</span><span class="sxs-lookup"><span data-stu-id="67a2c-124">Anti-spam policies (also known as content filter policies)</span></span>
  - <span data-ttu-id="67a2c-125">Beleid voor uitgaand spamfilter</span><span class="sxs-lookup"><span data-stu-id="67a2c-125">Outbound spam filter policies</span></span>
  - <span data-ttu-id="67a2c-126">Verbindingsfilterbeleid</span><span class="sxs-lookup"><span data-stu-id="67a2c-126">Connection filter policies</span></span>
- <span data-ttu-id="67a2c-127">Anti-malwarebeleid</span><span class="sxs-lookup"><span data-stu-id="67a2c-127">Anti-malware policies</span></span>
- <span data-ttu-id="67a2c-128">Verbindingslijnen</span><span class="sxs-lookup"><span data-stu-id="67a2c-128">Connectors</span></span>
- <span data-ttu-id="67a2c-129">Regels voor e-mailstroom (ook wel transportregels genoemd)</span><span class="sxs-lookup"><span data-stu-id="67a2c-129">Mail flow rules (also known as transport rules)</span></span>

  > [!NOTE]
  > <span data-ttu-id="67a2c-130">Cmdlet-ondersteuning voor het exporteren en importeren van de verzameling e-mailstroomregel wordt momenteel alleen ondersteund voor EOP Premium-abonnementsabonnementen.</span><span class="sxs-lookup"><span data-stu-id="67a2c-130">Cmdlet support for the export and import of the mail flow rule collection is currently only supported for EOP Premium subscription plans.</span></span>

<span data-ttu-id="67a2c-131">De eenvoudigste manier om al uw instellingen te verzamelen, is door PowerShell te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="67a2c-131">The easiest way to collect all of your settings is to use PowerShell.</span></span> <span data-ttu-id="67a2c-132">Zie [Verbinding maken met Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell) als je verbinding wilt maken met zelfstandige EOP PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67a2c-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

<span data-ttu-id="67a2c-133">Vervolgens kunt u al uw instellingen verzamelen en exporteren naar een XML-bestand dat moet worden geïmporteerd in de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="67a2c-133">Next, you can collect all your settings and export them to an .xml file to be imported into the target tenant.</span></span> <span data-ttu-id="67a2c-134">In het algemeen kunt u de **uitvoer** van de cmdlet Downloaden voor elke instelling naar de cmdlet **Exporteren-Clixml** doorvervolgen om de instellingen op te slaan in XML-bestanden, zoals wordt weergegeven in het volgende codevoorbeeld.</span><span class="sxs-lookup"><span data-stu-id="67a2c-134">In general, you can pipe the output of the **Get** cmdlet for each setting to the **Export-Clixml** cmdlet to save the settings in .xml files, as shown in the following code sample.</span></span>

<span data-ttu-id="67a2c-135">Maak in zelfstandige EOP PowerShell een adreslijst met de naam Exporteren op een locatie die u gemakkelijk kunt vinden en wijzigen in die adreslijst.</span><span class="sxs-lookup"><span data-stu-id="67a2c-135">In standalone EOP PowerShell, create a directory called Export in a location that's easy to find and change to that directory.</span></span> <span data-ttu-id="67a2c-136">Bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="67a2c-136">For example:</span></span>

```PowerShell
mkdir C:\EOP\Export
```

```PowerShell
cd C:\EOP\Export
```

<span data-ttu-id="67a2c-137">Het volgende script kan worden gebruikt om alle e-mailgebruikers, groepen, antispaminstellingen, anti-malwareinstellingen, verbindingslijnen en regels voor e-mailstroom in de bronorganisatie te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="67a2c-137">The following script can be used to collect all the mail users, groups, anti-spam settings, anti-malware settings, connectors, and mail flow rules in the source organization.</span></span> <span data-ttu-id="67a2c-138">Kopieer en plak de volgende tekst in een teksteditor zoals Kladblok, sla het bestand op als Source_EOP_Settings.ps1 in de map Exporteren die u zojuist hebt gemaakt en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="67a2c-138">Copy and paste the following text into a text editor like Notepad, save the file as Source_EOP_Settings.ps1 in the Export directory you just created, and run the following command:</span></span>

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
# Anti-malware policies
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

<span data-ttu-id="67a2c-139">Voer de volgende opdrachten uit vanuit de map Exporteren om de XML-bestanden bij te werken met de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-139">Run the following commands from the Export directory to update the .xml files with the target organization.</span></span> <span data-ttu-id="67a2c-140">Vervang contoso.onmicrosoft.com en contososuites.onmicrosoft.com door de namen van de bron- en doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-140">Replace contoso.onmicrosoft.com and contososuites.onmicrosoft.com with your source and target organization names.</span></span>

```PowerShell
$files = ls
ForEach ($file in $files) { (Get-Content $file.Name) | Foreach-Object {$_ -replace 'contoso.onmicrosoft.com', 'contososuites.onmicrosoft.com'} | Set-Content $file.Name}
```

## <a name="step-2-add-domains-to-the-target-organization"></a><span data-ttu-id="67a2c-141">Stap 2: Domeinen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="67a2c-141">Step 2: Add domains to the target organization</span></span>

<span data-ttu-id="67a2c-142">Voeg domeinen toe aan de doelorganisatie met behulp van het volgende script.</span><span class="sxs-lookup"><span data-stu-id="67a2c-142">Add domains to the target organization by using the following script.</span></span> <span data-ttu-id="67a2c-143">Kopieer en plak de tekst in een teksteditor zoals Kladblok, sla het script op als C:\EOP\Export\Add_Domains.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="67a2c-143">Copy and paste the text into a text editor like Notepad, save the script as C:\EOP\Export\Add_Domains.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Add_Domains.ps1"
```

<span data-ttu-id="67a2c-144">Deze domeinen worden niet geverifieerd en kunnen niet worden gebruikt om e-mail door te sturen, maar nadat de domeinen zijn toegevoegd, kunt u de benodigde gegevens verzamelen om de domeinen te verifiëren en uw MX-records uiteindelijk bijwerken voor de nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="67a2c-144">These domains won't be verified and can't be used to route mail, but after the domains are added, you can collect the information needed to verify the domains and eventually update your MX records for the new tenant.</span></span>

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

<span data-ttu-id="67a2c-145">U kunt nu de gegevens bekijken en verzamelen vanuit het Microsoft 365-beheercentrum van uw doelorganisatie, zodat u uw domeinen snel kunt verifiëren wanneer het tijd is:</span><span class="sxs-lookup"><span data-stu-id="67a2c-145">Now you can review and collect the information from the Microsoft 365 admin center of your target organization so you can quickly verify your domains when the time comes:</span></span>

1. <span data-ttu-id="67a2c-146">Meld u aan bij het Microsoft 365-beheercentrum bij <https://portal.office.com> .</span><span class="sxs-lookup"><span data-stu-id="67a2c-146">Sign in to the Microsoft 365 admin center at <https://portal.office.com>.</span></span>

2. <span data-ttu-id="67a2c-147">Klik **op Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="67a2c-147">Click **Domains**.</span></span>

   <span data-ttu-id="67a2c-148">Als u geen domeinen ziet, klikt u op Navigatie **aanpassen,** **selecteert** u Setup en klikt u vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="67a2c-148">If you don't see domains, click **Customize navigation**, select **Setup**, and then click **Save**.</span></span>

3. <span data-ttu-id="67a2c-149">Klik op **elke koppeling Start-instelling** en ga vervolgens door de installatiewizard.</span><span class="sxs-lookup"><span data-stu-id="67a2c-149">Click each **Start setup** link, and then proceed through the setup wizard.</span></span>

4. <span data-ttu-id="67a2c-150">Selecteer op **de pagina** Eigendom bevestigen de optie Algemene instructies voor Stapsgewijs instructies voor het uitvoeren van deze **stap** met . </span><span class="sxs-lookup"><span data-stu-id="67a2c-150">On the **Confirm ownership** page, for **See step-by-step instructions for performing this step with**, select **General instructions**.</span></span>

5. <span data-ttu-id="67a2c-151">Neem de MX-record of TXT-record op die u gebruikt om uw domein te verifiëren en maak de installatiewizard af.</span><span class="sxs-lookup"><span data-stu-id="67a2c-151">Record the MX record or TXT record that you'll use to verify your domain, and finish the setup wizard.</span></span>

6. <span data-ttu-id="67a2c-152">Voeg de verificatie-TXT-records toe aan uw DNS-records.</span><span class="sxs-lookup"><span data-stu-id="67a2c-152">Add the verification TXT records to your DNS records.</span></span> <span data-ttu-id="67a2c-153">Hierdoor kunt u de domeinen in de bronorganisatie sneller verifiëren nadat ze zijn verwijderd uit de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-153">This will let you more quickly verify the domains in the source organization after they're removed from the target organization.</span></span> <span data-ttu-id="67a2c-154">Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="67a2c-154">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

## <a name="step-3-force-senders-to-queue-mail"></a><span data-ttu-id="67a2c-155">Stap 3: Afzenders dwingen om e-mail in de wachtrij te zetten</span><span class="sxs-lookup"><span data-stu-id="67a2c-155">Step 3: Force senders to queue mail</span></span>

<span data-ttu-id="67a2c-156">Wanneer u uw domeinen van de ene tenant naar de andere verplaatst, moet u de domeinen verwijderen uit de bronorganisatie en deze vervolgens verifiëren in uw doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="67a2c-156">While moving your domains from one tenant to another, you'll need to delete the domains from the source organization and then verify them in your target organization.</span></span> <span data-ttu-id="67a2c-157">Gedurende deze periode kunt u geen e-mail door e-mail sturen via EOP.</span><span class="sxs-lookup"><span data-stu-id="67a2c-157">During this time, you won't be able to route mail through EOP.</span></span>

<span data-ttu-id="67a2c-158">Een optie om afzenders te dwingen e-mail in de wachtrij te zetten, is door uw MX-records bij te werken om rechtstreeks naar uw on-premises e-mailserver te wijzen.</span><span class="sxs-lookup"><span data-stu-id="67a2c-158">One option to force senders to queue mail is to update your MX records to point directly to your on-premises mail server.</span></span>

<span data-ttu-id="67a2c-159">Een andere optie is om een ongeldige MX-record in elk domein te plaatsen waar de DNS-records voor uw domein worden bewaard (ook wel uw DNS-hostingservice genoemd).</span><span class="sxs-lookup"><span data-stu-id="67a2c-159">Another option is to put an invalid MX record in each domain where the DNS records for your domain are kept (also known as your DNS hosting service).</span></span> <span data-ttu-id="67a2c-160">Dit zorgt ervoor dat de afzender uw e-mail in de wachtrij moet staan en opnieuw moet proberen (normale pogingen tot opnieuw proberen duren 48 uur, maar dit kan per provider verschillen).</span><span class="sxs-lookup"><span data-stu-id="67a2c-160">This will cause the sender to queue your mail and retry (typical retry attempts are for 48 hours, but this might vary from provider to provider).</span></span> <span data-ttu-id="67a2c-161">U kunt de invalid.outlook.com als ongeldig MX-doel gebruiken.</span><span class="sxs-lookup"><span data-stu-id="67a2c-161">You can use invalid.outlook.com as an invalid MX target.</span></span> <span data-ttu-id="67a2c-162">Als u de TTL-waarde (Time to Live) verlaagt tot vijf minuten op de MX-record, kan de wijziging sneller worden doorgegeven aan DNS-providers.</span><span class="sxs-lookup"><span data-stu-id="67a2c-162">Lowering the Time to Live (TTL) value to five minutes on the MX record will help the change propagate to DNS providers more quickly.</span></span>

<span data-ttu-id="67a2c-163">Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="67a2c-163">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67a2c-164">Verschillende providers staan in de wachtrij voor verschillende perioden.</span><span class="sxs-lookup"><span data-stu-id="67a2c-164">Different providers queue mail for different periods of time.</span></span> <span data-ttu-id="67a2c-165">U moet uw nieuwe tenant snel instellen en uw DNS-instellingen herstellen om te voorkomen dat niet-bezorgingsrapporten (NR's) naar de afzender worden verzonden als de wachtrijtijd verloopt.</span><span class="sxs-lookup"><span data-stu-id="67a2c-165">You'll need to set up your new tenant quickly and revert your DNS settings to avoid non-delivery reports (NDRs) from being sent to the sender if the queuing time expires.</span></span>

## <a name="step-4-remove-users-groups-and-domains-from-the-source-organization"></a><span data-ttu-id="67a2c-166">Stap 4: Gebruikers, groepen en domeinen verwijderen uit de bronorganisatie</span><span class="sxs-lookup"><span data-stu-id="67a2c-166">Step 4: Remove users, groups, and domains from the source organization</span></span>

<span data-ttu-id="67a2c-167">Met het volgende script worden gebruikers, groepen en domeinen uit de bronten tenant verwijderd met Behulp van Azure Active Directory PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67a2c-167">The following script removes users, groups, and domains from the source tenant by using Azure Active Directory PowerShell.</span></span> <span data-ttu-id="67a2c-168">Kopieer en plak de volgende tekst in een teksteditor zoals Kladblok, sla het bestand op als C:\EOP\Export\Remove_Users_and_Groups.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="67a2c-168">Copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Remove_Users_and_Groups.ps1, and run the following command:</span></span>

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

## <a name="step-5-verify-domains-for-the-target-organization"></a><span data-ttu-id="67a2c-169">Stap 5: Domeinen voor de doelorganisatie verifiëren</span><span class="sxs-lookup"><span data-stu-id="67a2c-169">Step 5: Verify domains for the target organization</span></span>

1. <span data-ttu-id="67a2c-170">Meld u aan bij het beheercentrum op <https://portal.office.com> .</span><span class="sxs-lookup"><span data-stu-id="67a2c-170">Sign in to the admin center at <https://portal.office.com>.</span></span>

2. <span data-ttu-id="67a2c-171">Klik **op Domeinen.**</span><span class="sxs-lookup"><span data-stu-id="67a2c-171">Click **Domains**.</span></span>

3. <span data-ttu-id="67a2c-172">Klik op **elke koppeling Start-instelling** voor het doeldomein en ga door de installatiewizard.</span><span class="sxs-lookup"><span data-stu-id="67a2c-172">Click each **Start setup** link for the target domain and proceed through the setup wizard.</span></span>

## <a name="step-6-add-mail-users-and-groups-to-the-target-organization"></a><span data-ttu-id="67a2c-173">Stap 6: E-mailgebruikers en groepen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="67a2c-173">Step 6: Add mail users and groups to the target organization</span></span>

<span data-ttu-id="67a2c-174">Een goede gewoonte voor EOP is om Azure Active Directory te gebruiken om uw on-premises Active Directory te synchroniseren met uw doel tenant.</span><span class="sxs-lookup"><span data-stu-id="67a2c-174">A best practice for EOP is to use Azure Active Directory to sync your on-premises Active Directory to your target tenant.</span></span> <span data-ttu-id="67a2c-175">Zie 'Adreslijstsynchronisatie gebruiken om e-mailgebruikers te beheren' in EOP e-mailgebruikers beheren voor meer informatie over hoe u dit [doet.](manage-mail-users-in-eop.md)</span><span class="sxs-lookup"><span data-stu-id="67a2c-175">For more information about how to do this, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="67a2c-176">U kunt ook het volgende script gebruiken om uw gebruikers en groepen opnieuw te maken vanuit uw bron tenant.</span><span class="sxs-lookup"><span data-stu-id="67a2c-176">You can also use the following script to recreate your users and groups from your source tenant.</span></span> <span data-ttu-id="67a2c-177">Opmerking: Gebruikerswachtwoorden kunnen niet worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="67a2c-177">Note: User passwords cannot be moved.</span></span> <span data-ttu-id="67a2c-178">Nieuwe gebruikerswachtwoorden worden gemaakt en opgeslagen in het bestand met de UsersAndGroups.ps1.</span><span class="sxs-lookup"><span data-stu-id="67a2c-178">New user passwords are created and saved in the file named UsersAndGroups.ps1.</span></span>

<span data-ttu-id="67a2c-179">Als u het script wilt gebruiken, kopieert en plakt u de volgende tekst in een teksteditor, zoals Kladblok, sla het bestand op als C:\EOP\Export\Add_Users_and_Groups.ps1 en voer u de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="67a2c-179">To use the script, copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Add_Users_and_Groups.ps1, and run the following command:</span></span>

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

## <a name="step-7-add-protection-settings-to-the-target-organization"></a><span data-ttu-id="67a2c-180">Stap 7: Beveiligingsinstellingen toevoegen aan de doelorganisatie</span><span class="sxs-lookup"><span data-stu-id="67a2c-180">Step 7: Add protection settings to the target organization</span></span>

<span data-ttu-id="67a2c-181">U kunt het volgende script uitvoeren vanuit de map Exporteren terwijl u bent aangemeld bij uw doelorganisatie om de instellingen te maken die eerder vanuit de bronorganisatie naar XML-bestanden zijn geëxporteerd.</span><span class="sxs-lookup"><span data-stu-id="67a2c-181">You can run the following script from the Export directory while logged in to your target organization to recreate the settings exported to .xml files earlier from the source organization.</span></span>

<span data-ttu-id="67a2c-182">Kopieer en plak de scripttekst in een teksteditor zoals Kladblok, sla het bestand op als C:\EOP\Export\Import_Settings.ps1 en voer de volgende opdracht uit:</span><span class="sxs-lookup"><span data-stu-id="67a2c-182">Copy and paste the script text into a text editor like Notepad, save the file as C:\EOP\Export\Import_Settings.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Import_Settings.ps1"
```

<span data-ttu-id="67a2c-183">Met dit script worden de XML-bestanden geïmporteerd en wordt een Windows PowerShell-scriptbestand gemaakt met de naam Settings.ps1 dat u kunt controleren, bewerken en vervolgens kunt uitvoeren om uw beveiligings- en e-mailstroominstellingen opnieuw te maken.</span><span class="sxs-lookup"><span data-stu-id="67a2c-183">This script imports the .xml files and create a Windows PowerShell script file called Settings.ps1 that you can review, edit, and then run to recreate your protection and mail-flow settings.</span></span>

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
$HostedContentFilterPolicies = Import-Clixml ".\HostedContentFilterPolicy.xml"
$HostedContentFilterPolicyCount = $HostedContentFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterPolicyCount Inbound Connectors"
    ForEach ($HostedContentFilterPolicy in $HostedContentFilterPolicies) {
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
$HostedOutboundSpamFilterPolicies = Import-Clixml ".\HostedOutboundSpamFilterPolicy.xml"
$HostedOutboundSpamFilterPolicyCount = $HostedOutboundSpamFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedOutboundSpamFilterPolicyCount Hosted Outbound Spam Filter Policies"
    ForEach ($HostedOutboundSpamFilterPolicy in $HostedOutboundSpamFilterPolicies) {
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
$HostedConnectionFilterPolicies = Import-Clixml ".\HostedConnectionFilterPolicy.xml"
$HostedConnectionFilterPolicyCount = $HostedConnectionFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedConnectionFilterPolicyCount Hosted Connection Filter Policies"
    ForEach ($HostedConnectionFilterPolicy in $HostedConnectionFilterPolicies) {
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
$MalwareFilterPolicies = Import-Clixml ".\MalwareFilterPolicy.xml"
$MalwareFilterPolicyCount = $MalwareFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterPolicyCount Malware Filter Policies"
    ForEach ($MalwareFilterPolicy in $MalwareFilterPolicies) {
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

## <a name="step-8-revert-your-dns-settings-to-stop-mail-queuing"></a><span data-ttu-id="67a2c-184">Stap 8: Uw DNS-instellingen terugdraaien om e-mail te stoppen</span><span class="sxs-lookup"><span data-stu-id="67a2c-184">Step 8: Revert your DNS settings to stop mail queuing</span></span>

<span data-ttu-id="67a2c-185">Als u ervoor kiest om uw MX-records in te stellen op een ongeldig adres om ervoor te zorgen dat de afzenders e-mail in de wachtrij zetten tijdens de overgang, moet u deze opnieuw instellen op de juiste waarde, zoals is opgegeven in het [beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="67a2c-185">If you chose to set your MX records to an invalid address to cause the senders to queue mail during your transition, you'll need to set them back to the correct value as specified in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="67a2c-186">Zie DNS-records maken bij een [DNS-hostingprovider voor Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)voor meer informatie over het configureren van DNS.</span><span class="sxs-lookup"><span data-stu-id="67a2c-186">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>