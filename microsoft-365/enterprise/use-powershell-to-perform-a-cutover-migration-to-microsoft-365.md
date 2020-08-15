---
title: PowerShell gebruiken om een cutover-migratie uit te voeren naar Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: Lees hoe u PowerShell gebruikt om de inhoud van een bron-e-mailsysteem in één keer te verplaatsen door een cutover-migratie uit te voeren naar Microsoft 365.
ms.openlocfilehash: bf97fef7e0e927dc901b0223978a3eef377def2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688963"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="bad7c-103">PowerShell gebruiken om een cutover-migratie uit te voeren naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bad7c-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="bad7c-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="bad7c-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="bad7c-105">Met een cutover-migratie kunt u de inhoud van postvakken van gebruikers in één keer van het bron-e-mailsysteem migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad7c-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="bad7c-106">In dit artikel wordt u begeleid bij het uitvoeren van de taken voor een e-cutover-migratie via Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bad7c-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span> 
  
<span data-ttu-id="bad7c-107">Als u het onderwerp controleert, [wat u moet weten over een cutover-e-mail migratie naar Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), krijgt u een overzicht van het migratieproces.</span><span class="sxs-lookup"><span data-stu-id="bad7c-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), you can get an overview of the migration process.</span></span> <span data-ttu-id="bad7c-108">Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.</span><span class="sxs-lookup"><span data-stu-id="bad7c-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bad7c-109">U kunt ook het Exchange-Beheercentrum gebruiken om een cutover-migratie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="bad7c-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="bad7c-110">Zie [een cutover-migratie uitvoeren van e-mail naar Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span><span class="sxs-lookup"><span data-stu-id="bad7c-110">See [Perform a cutover migration of email to Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="bad7c-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="bad7c-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="bad7c-112">Geschatte tijd voor het voltooien van deze taak: 2-5 minuten om een migratie batch te maken.</span><span class="sxs-lookup"><span data-stu-id="bad7c-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="bad7c-113">Nadat de migratie batch is gestart, wordt de duur van de migratie verschillend gemaakt op basis van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit.</span><span class="sxs-lookup"><span data-stu-id="bad7c-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="bad7c-114">Zie [migratie prestaties](https://go.microsoft.com/fwlink/p/?LinkId=275079)voor informatie over andere factoren die van invloed zijn op de manier waarop u postvakken gaat migreren naar microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad7c-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="bad7c-115">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="bad7c-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="bad7c-116">Als u wilt zien welke machtigingen u nodig hebt, raadpleegt u de vermelding ' Migration ' in een tabel in het onderwerp [machtigingen voor geadresseerden](https://go.microsoft.com/fwlink/p/?LinkId=534105) .</span><span class="sxs-lookup"><span data-stu-id="bad7c-116">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="bad7c-117">Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-117">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="bad7c-118">Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="bad7c-118">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="bad7c-119">Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.</span><span class="sxs-lookup"><span data-stu-id="bad7c-119">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
## <a name="migration-steps"></a><span data-ttu-id="bad7c-120">Migratiestappen</span><span class="sxs-lookup"><span data-stu-id="bad7c-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="bad7c-121">Stap 1: een cutover-migratie voorbereiden</span><span class="sxs-lookup"><span data-stu-id="bad7c-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="bad7c-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="bad7c-123">**Voeg uw on-premises Exchange-organisatie toe als een geaccepteerd domein van uw Microsoft 365-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="bad7c-124">De Migratieservice gebruikt het SMTP-adres van uw on-premises postvakken om de gebruikers-ID en het e-mailadres van Microsoft Online Services te maken voor de nieuwe postvakken van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad7c-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="bad7c-125">De migratie mislukt als uw Exchange-domein geen geaccepteerd domein of het primaire domein van uw Microsoft 365-organisatie is.</span><span class="sxs-lookup"><span data-stu-id="bad7c-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="bad7c-126">Zie [uw domein verifiëren](https://go.microsoft.com/fwlink/p/?LinkId=534110)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-126">For more information, see [Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="bad7c-127">**Configureer Outlook op een plaats op uw on-premises Exchange-Server.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-127">**Configure Outlook Anywhere on your on-premises Exchange server.**</span></span> <span data-ttu-id="bad7c-128">De e-mail Migratieservice maakt gebruik van RPC via HTTP, of Outlook Anywhere, om verbinding te maken met uw on-premises Exchange-Server.</span><span class="sxs-lookup"><span data-stu-id="bad7c-128">The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server.</span></span> <span data-ttu-id="bad7c-129">Raadpleeg de volgende onderwerpen voor meer informatie over het instellen van Outlook Anywhere voor Exchange Server 2010, Exchange 2007 en Exchange 2003:</span><span class="sxs-lookup"><span data-stu-id="bad7c-129">For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>
    
  - [<span data-ttu-id="bad7c-130">Exchange 2010: Outlook Anywhere inschakelen</span><span class="sxs-lookup"><span data-stu-id="bad7c-130">Exchange 2010: Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=187249)
    
  - [<span data-ttu-id="bad7c-131">Exchange 2007: Outlook Anywhere inschakelen</span><span class="sxs-lookup"><span data-stu-id="bad7c-131">Exchange 2007: How to Enable Outlook Anywhere</span></span>](https://go.microsoft.com/fwlink/?LinkID=167210)
    
  - [<span data-ttu-id="bad7c-132">Exchange 2003: Implementatiescenario's voor RPC via HTTP</span><span class="sxs-lookup"><span data-stu-id="bad7c-132">Exchange 2003: Deployment Scenarios for RPC over HTTP</span></span>](https://go.microsoft.com/fwlink/?LinkID=73657)
    
  - [<span data-ttu-id="bad7c-133">Outlook Anywhere configureren met Exchange 2003</span><span class="sxs-lookup"><span data-stu-id="bad7c-133">How to Configure Outlook Anywhere with Exchange 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=167209)
    
    > [!IMPORTANT]
    > <span data-ttu-id="bad7c-134">De configuratie van Outlook Anywhere moet worden geconfigureerd met een certificaat dat is uitgegeven door een vertrouwde certificeringsinstantie (CA).</span><span class="sxs-lookup"><span data-stu-id="bad7c-134">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA).</span></span> <span data-ttu-id="bad7c-135">Het kan niet worden geconfigureerd met een zelfondertekend certificaat.</span><span class="sxs-lookup"><span data-stu-id="bad7c-135">It can't be configured with a self-signed certificate.</span></span> <span data-ttu-id="bad7c-136">Zie [SSL configureren voor Outlook voor](https://go.microsoft.com/fwlink/?LinkID=80875)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-136">For more information, see [How to Configure SSL for Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875).</span></span> 
  
- <span data-ttu-id="bad7c-137">**Controleer of u verbinding kunt maken met uw Exchange-organisatie met Outlook Anywhere.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-137">**Verify that you can connect to your Exchange organization using Outlook Anywhere.**</span></span> <span data-ttu-id="bad7c-138">Ga op een van de volgende manieren te werk om uw verbindingsinstellingen te testen:</span><span class="sxs-lookup"><span data-stu-id="bad7c-138">Try one of these methods to test your connection settings:</span></span>
    
  - <span data-ttu-id="bad7c-139">Gebruik Microsoft Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw on-premises Exchange-postvak.</span><span class="sxs-lookup"><span data-stu-id="bad7c-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>
    
  - <span data-ttu-id="bad7c-140">Gebruik Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) om uw verbindingsinstellingen te testen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-140">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings.</span></span> <span data-ttu-id="bad7c-141">Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-141">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>
    
  - <span data-ttu-id="bad7c-142">Voer de volgende opdrachten uit in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bad7c-142">Run the following commands in Exchange Online PowerShell.</span></span>
    
  ```
  $Credentials = Get-Credential
  ```

  ```
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="bad7c-143">**Een on-premises gebruikersaccount toewijzen de benodigde machtigingen voor toegang tot postvakken in uw Exchange-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="bad7c-144">Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel migratie beheerder genoemd), moet de juiste machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad7c-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="bad7c-145">Dit gebruikersaccount wordt gebruikt voor het maken van een migratie-eindpunt naar uw on-premises organisatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>
    
    <span data-ttu-id="bad7c-146">In de volgende lijst worden de beheerdersbevoegdheden weergegeven die nodig zijn voor het migreren van postvakken via een cutover-migratie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-146">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration.</span></span> <span data-ttu-id="bad7c-147">U kunt drie opties kiezen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-147">There are three possible options.</span></span>
    
  - <span data-ttu-id="bad7c-148">De migratie beheerder moet lid zijn van de groep **Domain Admins** in Active Directory in de on-premises organisatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>
    
    <span data-ttu-id="bad7c-149">Of</span><span class="sxs-lookup"><span data-stu-id="bad7c-149">Or</span></span>
    
  - <span data-ttu-id="bad7c-150">De migratiebeheerder moet voor elk on-premises postvak de machtiging **FullAccess** krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>
    
    <span data-ttu-id="bad7c-151">Of</span><span class="sxs-lookup"><span data-stu-id="bad7c-151">Or</span></span>
    
  - <span data-ttu-id="bad7c-152">De migratie beheerder moet de machtiging **receive as** krijgen toegewezen voor de on-premises postvakdatabase waarin de postvakken van gebruikers worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>
    
- <span data-ttu-id="bad7c-153">**Unified Messaging uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-153">**Disable Unified Messaging.**</span></span> <span data-ttu-id="bad7c-154">Als de on-premises postvakken die u wilt migreren, zijn ingeschakeld voor Unified Messaging (UM), moet u UM uitschakelen voor de postvakken voordat u ze migreert.</span><span class="sxs-lookup"><span data-stu-id="bad7c-154">If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them.</span></span> <span data-ttu-id="bad7c-155">U kunt vervolgens UM inschakelen voor de postvakken nadat de migratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="bad7c-155">You can then enable UM on the mailboxes after the migration is complete.</span></span>
    
- <span data-ttu-id="bad7c-156">**Beveiligingsgroepen en gemachtigden** De e-mail Migratieservice kan niet detecteren of on-premises Active Directory-groepen beveiligingsgroepen zijn, zodat het niet kan worden gemigreerd groepen als beveiligingsgroepen in Microsoft 365 te kunnen inrichten.</span><span class="sxs-lookup"><span data-stu-id="bad7c-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="bad7c-157">Als u beveiligingsgroepen wilt hebben in uw Microsoft 365-Tenant, moet u eerst een lege beveiligingsgroep met e-mail inrichten in uw Microsoft 365-Tenant voordat u de cutover-migratie start.</span><span class="sxs-lookup"><span data-stu-id="bad7c-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="bad7c-158">Daarnaast worden met deze migratiemethode alleen postvakken, e-mailgebruikers, e-mailcontactpersonen en groepen die e-mail gebruiken, verplaatst.</span><span class="sxs-lookup"><span data-stu-id="bad7c-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="bad7c-159">Als een ander Active Directory-object, zoals een gebruiker die niet is gemigreerd naar Microsoft 365, is toegewezen als manager of gemachtigde voor een object dat wordt gemigreerd, moet deze uit het object worden verwijderd voordat u de migratie vermigreert.</span><span class="sxs-lookup"><span data-stu-id="bad7c-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>
    
### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="bad7c-160">Stap 2: een migratie-eindpunt maken</span><span class="sxs-lookup"><span data-stu-id="bad7c-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="bad7c-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="bad7c-162">Voor het migreren van e-mail is Microsoft 365 nodig om verbinding te maken en te communiceren met het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="bad7c-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="bad7c-163">Hiervoor maakt Microsoft 365 gebruik van een migratie-eindpunt.</span><span class="sxs-lookup"><span data-stu-id="bad7c-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="bad7c-164">Voor het maken van een migratie-eindpunt van Outlook Anywhere voor cutover-migratie, moet u eerst [verbinding maken met Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="bad7c-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="bad7c-165">Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.</span><span class="sxs-lookup"><span data-stu-id="bad7c-165">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="bad7c-166">Voer de volgende opdrachten uit in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bad7c-166">Run the following commands in Exchange Online PowerShell:</span></span>
  
```
$Credentials = Get-Credential
```

<span data-ttu-id="bad7c-167">In het voorbeeld wordt de cmdlet [test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) gebruikt om de verbindingsinstellingen te verkrijgen en te testen op de on-premises Exchange-Server en worden vervolgens deze verbindingsinstellingen gebruikt om het migratie-eindpunt te maken met de naam ' CutoverEndpoint '.</span><span class="sxs-lookup"><span data-stu-id="bad7c-167">The example uses the [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>
  
```
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="bad7c-168">Met de cmdlet **New-MigrationEndpoint** kunt u een database opgeven voor de service die u wilt gebruiken met de optie **-TargetDatabase** .</span><span class="sxs-lookup"><span data-stu-id="bad7c-168">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option.</span></span> <span data-ttu-id="bad7c-169">Anders wordt een database willekeurig toegewezen op de site van de AD FS-2,0 (Active Directory Federation Services) waar het postvak van het beheer zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="bad7c-169">Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="bad7c-170">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="bad7c-170">Verify it worked</span></span>

<span data-ttu-id="bad7c-171">In Exchange Online PowerShell voert u de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt van CutoverEndpoint:</span><span class="sxs-lookup"><span data-stu-id="bad7c-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>
  
```
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="bad7c-172">Stap 3: de cutover-migratiebatch maken</span><span class="sxs-lookup"><span data-stu-id="bad7c-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="bad7c-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="bad7c-174">U kunt de **New-MigrationBatch-** cmdlet in Exchange Online PowerShell gebruiken om een migratie batch voor een cutover-migratie te maken.</span><span class="sxs-lookup"><span data-stu-id="bad7c-174">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration.</span></span> <span data-ttu-id="bad7c-175">U kunt een migratie batch maken en deze automatisch starten door de parameter van automatisch _starten_ op te nemen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-175">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="bad7c-176">U kunt de migratie batch ook maken en deze vervolgens handmatig opnieuw starten met behulp van de cmdlet **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="bad7c-176">Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="bad7c-177">In het volgende voorbeeld wordt een migratie batch met de naam CutoverBatch en gebruikt het migratie-eindpunt dat in de vorige stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="bad7c-177">This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="bad7c-178">In dit voorbeeld wordt ook een migratie batch met de naam ' CutoverBatch ' gemaakt en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="bad7c-178">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span> <span data-ttu-id="bad7c-179">Aangezien de parameter  _autostart_ niet is opgenomen, moet de migratie batch handmatig worden gestart op het migratie dashboard of met behulp van de cmdlet **Start-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="bad7c-179">Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="bad7c-180">Zoals eerder vermeld, kan slechts één cutover-migratie batch bestaan.</span><span class="sxs-lookup"><span data-stu-id="bad7c-180">As previously stated, only one cutover migration batch can exist at a time.</span></span>
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="bad7c-181">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="bad7c-181">Verify it worked</span></span>

<span data-ttu-id="bad7c-182">Als u wilt controleren of u een migratie batch voor een cutover-migratie hebt gemaakt, voert u de volgende opdracht uit in Exchange Online PowerShell om informatie over de nieuwe migratie batch weer te geven:</span><span class="sxs-lookup"><span data-stu-id="bad7c-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>
  
```
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="bad7c-183">Stap 4: de cutover-migratiebatch starten</span><span class="sxs-lookup"><span data-stu-id="bad7c-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="bad7c-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="bad7c-185">Voer de volgende opdracht uit om de migratie batch te starten in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bad7c-185">To start the migration batch in Exchange Online PowerShell, run the following command.</span></span> <span data-ttu-id="bad7c-186">Hiermee maakt u een migratie batch met de naam ' CutoverBatch '.</span><span class="sxs-lookup"><span data-stu-id="bad7c-186">This will create a migration batch called "CutoverBatch".</span></span>
  
```
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="bad7c-187">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="bad7c-187">Verify it worked</span></span>

<span data-ttu-id="bad7c-188">Als een migratie batch is gestart, wordt de status van het migratie dashboard opgegeven als synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-188">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing.</span></span> <span data-ttu-id="bad7c-189">Voer de volgende opdracht uit om te controleren of u een migratie batch met behulp van Exchange Online PowerShell hebt gestart:</span><span class="sxs-lookup"><span data-stu-id="bad7c-189">To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>
  
```
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="bad7c-190">Stap 5: uw e-mail doorsturen naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="bad7c-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="bad7c-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="bad7c-192">E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="bad7c-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="bad7c-193">Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="bad7c-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="bad7c-194">Nu de e-mail migratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record te laten verwijzen naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bad7c-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="bad7c-195">Hiermee zorgt u ervoor dat e-mail wordt afgeleverd bij uw Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="bad7c-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="bad7c-196">Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="bad7c-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="bad7c-197">Veel DNS-providers hebben specifieke instructies voor het [wijzigen van uw MX-record](https://go.microsoft.com/fwlink/p/?LinkId=279163).</span><span class="sxs-lookup"><span data-stu-id="bad7c-197">For many DNS providers, there are specific instructions to [change your MX record](https://go.microsoft.com/fwlink/p/?LinkId=279163).</span></span> <span data-ttu-id="bad7c-198">Als uw DNS-provider niet is opgenomen, of als u een idee wilt krijgen van de algemene instructies, worden ook [algemene MX-record instructies ](https://go.microsoft.com/fwlink/?LinkId=397449) weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bad7c-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="bad7c-199">Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend.</span><span class="sxs-lookup"><span data-stu-id="bad7c-199">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="bad7c-200">Wacht ten minste 72 uur voordat u verder gaat met de volgende taak: [stap 6: de cutover-migratie batch verwijderen](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span><span class="sxs-lookup"><span data-stu-id="bad7c-200">Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span> 
  
### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="bad7c-201">Stap 6: de cutover-migratiebatch verwijderen</span><span class="sxs-lookup"><span data-stu-id="bad7c-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="bad7c-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="bad7c-203">Nadat u de MX-record hebt gewijzigd en gecontroleerd of alle e-mail wordt gerouteerd naar Microsoft 365-postvakken, waarschuwt u de gebruikers dat hun e-mailbericht naar Microsoft 365 gaat.</span><span class="sxs-lookup"><span data-stu-id="bad7c-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="bad7c-204">Vervolgens kunt u de cutover-migratie batch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="bad7c-205">Controleer het volgende voordat u de migratiebatch verwijdert.</span><span class="sxs-lookup"><span data-stu-id="bad7c-205">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="bad7c-206">Alle gebruikers gebruiken Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="bad7c-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="bad7c-207">Wanneer de batch is verwijderd, wordt e-mail die is verzonden naar postvakken op de on-premises Exchange-Server niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="bad7c-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="bad7c-208">Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail direct naar hem is verzonden.</span><span class="sxs-lookup"><span data-stu-id="bad7c-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="bad7c-209">Zorg ervoor dat de waarde in het vak laatst gesynchroniseerde tijd voor de migratie batch uitgebreid is dan wanneer de e-mail direct naar Microsoft 365-postvakken wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="bad7c-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="bad7c-210">Voer de volgende opdracht uit om de CutoverBatch-migratie batch in Exchange Online PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="bad7c-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>
  
```
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="bad7c-211">Sectie 7: gebruikerslicenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="bad7c-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="bad7c-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="bad7c-213">**Activeer Microsoft 365-gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="bad7c-214">Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="bad7c-215">Zie [licenties toewijzen of intrekken](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)als u een licentie wilt toewijzen in het microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="bad7c-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
  
### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="bad7c-216">Stap 8: post-migratietaken voltooien</span><span class="sxs-lookup"><span data-stu-id="bad7c-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="bad7c-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="bad7c-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="bad7c-218">**Maak een automatische detectie-DNS-record zodat gebruikers gemakkelijk toegang hebben tot hun postvakken.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="bad7c-219">Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een automatische detectie-DNS-record voor uw Microsoft 365-organisatie configureren zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients.</span><span class="sxs-lookup"><span data-stu-id="bad7c-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="bad7c-220">Deze nieuwe DNS-record voor automatisch opsporen moet de naam van de naamruimte gebruiken die u gebruikt voor uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="bad7c-221">Als bijvoorbeeld de naamruimte in de Cloud cloud.contoso.com is, is de DNS-record voor Autodiscover die u moet maken autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bad7c-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>
    
    <span data-ttu-id="bad7c-222">Als u uw Exchange-Server bijneemt, moet u er ook voor zorgen dat automatisch opsporen DNS CNAME-record moet verwijzen naar Microsoft 365 binnen interne en externe DNS na de migratie, zodat de Outlook-client verbinding kan maken met het juiste postvak.</span><span class="sxs-lookup"><span data-stu-id="bad7c-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="bad7c-223">In Exchange 2007, Exchange 2010 en Exchange 2013 moet u ook instellen `Set-ClientAccessServer AutodiscoverInternalConnectionURI` `Null` .</span><span class="sxs-lookup"><span data-stu-id="bad7c-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span> 
  
    <span data-ttu-id="bad7c-224">Microsoft 365 gebruikt een CNAME-record om de Autodiscover-service voor Outlook en mobiele clients te implementeren.</span><span class="sxs-lookup"><span data-stu-id="bad7c-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="bad7c-225">De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:</span><span class="sxs-lookup"><span data-stu-id="bad7c-225">The Autodiscover CNAME record must contain the following information:</span></span>
    
  - <span data-ttu-id="bad7c-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="bad7c-226">**Alias:** autodiscover</span></span>
    
  - <span data-ttu-id="bad7c-227">**Doel:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="bad7c-227">**Target:** autodiscover.outlook.com</span></span>
    
    <span data-ttu-id="bad7c-228">Zie [DNS-records toevoegen om uw domein te verbinden](https://go.microsoft.com/fwlink/p/?LinkId=535028)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="bad7c-228">For more information, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=535028).</span></span>
    
- <span data-ttu-id="bad7c-229">**On-premises Exchange-servers buiten bedrijf stellen.**</span><span class="sxs-lookup"><span data-stu-id="bad7c-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="bad7c-230">Nadat u hebt gecontroleerd of alle e-mailberichten rechtstreeks naar de 365-postvakken van Microsoft worden gerouteerd en u uw on-premises e-mail organisatie niet langer hoeft te onderhouden of niet meer wilt plannen om een SSO-oplossing (eenmalige aanmelding) te implementeren, kunt u Exchange van uw servers verwijderen en uw on-premises Exchange-organisatie verwijderen.</span><span class="sxs-lookup"><span data-stu-id="bad7c-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>
    
    <span data-ttu-id="bad7c-231">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="bad7c-231">For more information, see the following:</span></span>
    
  - [<span data-ttu-id="bad7c-232">Exchange 2010 wijzigen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="bad7c-232">Modify or Remove Exchange 2010</span></span>](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [<span data-ttu-id="bad7c-233">Een Exchange 2007-organisatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="bad7c-233">How to Remove an Exchange 2007 Organization</span></span>](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [<span data-ttu-id="bad7c-234">Exchange Server 2003 verwijderen</span><span class="sxs-lookup"><span data-stu-id="bad7c-234">How to Uninstall Exchange Server 2003</span></span>](https://go.microsoft.com/fwlink/?LinkID=56561)
    

