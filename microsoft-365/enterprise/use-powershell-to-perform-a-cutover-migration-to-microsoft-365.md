---
title: Een cutover-migratie naar Microsoft 365 uitvoeren met PowerShell
ms.author: kvice
author: kelleyvice-msft
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
description: Informatie over het gebruik van PowerShell om de inhoud van een bron-e-mailsysteem in één keer te verplaatsen door een cutover-migratie uit te voeren naar Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581056"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a><span data-ttu-id="d13c2-103">Een cutover-migratie naar Microsoft 365 uitvoeren met PowerShell</span><span class="sxs-lookup"><span data-stu-id="d13c2-103">Use PowerShell to perform a cutover migration to Microsoft 365</span></span>

<span data-ttu-id="d13c2-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="d13c2-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="d13c2-105">U kunt de inhoud van gebruikerspostvakken in één keer migreren van een bron-e-mailsysteem naar Microsoft 365 met behulp van een cutover-migratie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-105">You can migrate the contents of user mailboxes from a source email system to Microsoft 365 all at once by using a cutover migration.</span></span> <span data-ttu-id="d13c2-106">In dit artikel vindt u een overzicht van de taken voor een cutover-migratie per e-mail met Behulp van Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d13c2-106">This article walks you through the tasks for an email cutover migration by using Exchange Online PowerShell.</span></span>

<span data-ttu-id="d13c2-107">Als u het onderwerp Wat u moet weten over een cutover-e-mailmigratie naar [Microsoft 365,](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)kunt u een overzicht krijgen van het migratieproces.</span><span class="sxs-lookup"><span data-stu-id="d13c2-107">By reviewing the topic, [What you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration), you can get an overview of the migration process.</span></span> <span data-ttu-id="d13c2-108">Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.</span><span class="sxs-lookup"><span data-stu-id="d13c2-108">When you're comfortable with the contents of that article, use this one to begin migrating mailboxes from one email system to another.</span></span>

> [!NOTE]
> <span data-ttu-id="d13c2-109">U kunt ook het Exchange-beheercentrum gebruiken om een cutover-migratie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d13c2-109">You can also use the Exchange admin center to perform a cutover migration.</span></span> <span data-ttu-id="d13c2-110">Zie [Een cutover-migratie van e-mail uitvoeren naar Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="d13c2-110">See [Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d13c2-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="d13c2-111">What do you need to know before you begin?</span></span>

<span data-ttu-id="d13c2-112">Geschatte tijd om deze taak te voltooien: 2-5 minuten om een migratiebatch te maken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-112">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="d13c2-113">Nadat de migratiebatch is gestart, is de duur van de migratie afhankelijk van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit.</span><span class="sxs-lookup"><span data-stu-id="d13c2-113">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="d13c2-114">Zie Migratieprestaties voor informatie over andere factoren die van invloed zijn [](/Exchange/mailbox-migration/office-365-migration-best-practices)op hoe lang het duurt om postvakken te migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d13c2-114">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="d13c2-115">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d13c2-115">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="d13c2-116">Als u wilt zien welke machtigingen u nodig hebt, ziet u de vermelding 'Migratie' in een tabel in het onderwerp [Machtigingen geadresseerden.](/exchange/recipients-permissions-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="d13c2-116">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="d13c2-117">Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-117">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="d13c2-118">Zie [Verbinding maken met Exchange Online met behulp van externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="d13c2-118">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="d13c2-119">Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="d13c2-119">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

## <a name="migration-steps"></a><span data-ttu-id="d13c2-120">Migratiestappen</span><span class="sxs-lookup"><span data-stu-id="d13c2-120">Migration steps</span></span>

### <a name="step-1-prepare-for-a-cutover-migration"></a><span data-ttu-id="d13c2-121">Stap 1: Voorbereiden op een cutover-migratie</span><span class="sxs-lookup"><span data-stu-id="d13c2-121">Step 1: Prepare for a cutover migration</span></span>
<span data-ttu-id="d13c2-122"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-122"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="d13c2-123">**Voeg uw on-premises Exchange-organisatie toe als een geaccepteerd domein van uw Microsoft 365-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-123">**Add your on-premises Exchange organization as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="d13c2-124">De migratieservice gebruikt het SMTP-adres van uw on-premises postvakken om de gebruikers-id en het e-mailadres van Microsoft Online Services te maken voor de nieuwe Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-124">The migration service uses the SMTP address of your on-premises mailboxes to create the Microsoft Online Services user ID and email address for the new Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d13c2-125">De migratie mislukt als uw Exchange-domein geen geaccepteerd domein of het primaire domein van uw Microsoft 365-organisatie is.</span><span class="sxs-lookup"><span data-stu-id="d13c2-125">Migration will fail if your Exchange domain isn't an accepted domain or the primary domain of your Microsoft 365 organization.</span></span> <span data-ttu-id="d13c2-126">Zie Uw domein verifiëren [voor meer informatie.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="d13c2-126">For more information, see [Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="d13c2-127">**Configureer Outlook Anywhere op uw on-premises Exchange-server.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-127">**Configure Outlook Anywhere on your on-premises Exchange server.**</span></span> <span data-ttu-id="d13c2-128">De e-mailmigratieservice gebruikt RPC via HTTP of Outlook Anywhere om verbinding te maken met uw on-premises Exchange-server.</span><span class="sxs-lookup"><span data-stu-id="d13c2-128">The email migration service uses RPC over HTTP, or Outlook Anywhere, to connect to your on-premises Exchange server.</span></span> <span data-ttu-id="d13c2-129">Raadpleeg de volgende onderwerpen voor meer informatie over het instellen van Outlook Anywhere voor Exchange Server 2010, Exchange 2007 en Exchange 2003:</span><span class="sxs-lookup"><span data-stu-id="d13c2-129">For information about how to set up Outlook Anywhere for Exchange 2010, Exchange 2007, and Exchange 2003, see the following:</span></span>

  - <span data-ttu-id="d13c2-130">[Exchange 2010: Outlook Anywhere inschakelen](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="d13c2-130">[Exchange 2010: Enable Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))</span></span>

  - <span data-ttu-id="d13c2-131">[Exchange 2007: Outlook Anywhere inschakelen](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="d13c2-131">[Exchange 2007: How to Enable Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))</span></span>

  - <span data-ttu-id="d13c2-132">[Exchange 2003: Implementatiescenario's voor RPC via HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="d13c2-132">[Exchange 2003: Deployment Scenarios for RPC over HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))</span></span>

  - <span data-ttu-id="d13c2-133">[Outlook overal configureren met Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="d13c2-133">[How to Configure Outlook Anywhere with Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d13c2-134">Uw Outlook Anywhere-configuratie moet zijn geconfigureerd met een certificaat dat is uitgegeven door een vertrouwde certificeringsinstantie (CA).</span><span class="sxs-lookup"><span data-stu-id="d13c2-134">Your Outlook Anywhere configuration must be configured with a certificate issued by a trusted certification authority (CA).</span></span> <span data-ttu-id="d13c2-135">Het kan niet worden geconfigureerd met een zelf ondertekend certificaat.</span><span class="sxs-lookup"><span data-stu-id="d13c2-135">It can't be configured with a self-signed certificate.</span></span> <span data-ttu-id="d13c2-136">Zie SSL configureren voor Outlook Anywhere voor [meer informatie.](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="d13c2-136">For more information, see [How to Configure SSL for Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).</span></span>

- <span data-ttu-id="d13c2-137">**Controleer of u verbinding kunt maken met uw Exchange-organisatie met Outlook Anywhere.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-137">**Verify that you can connect to your Exchange organization using Outlook Anywhere.**</span></span> <span data-ttu-id="d13c2-138">Probeer een van deze methoden om uw verbindingsinstellingen te testen:</span><span class="sxs-lookup"><span data-stu-id="d13c2-138">Try one of these methods to test your connection settings:</span></span>

  - <span data-ttu-id="d13c2-139">Gebruik Microsoft Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw on-premises Exchange-postvak.</span><span class="sxs-lookup"><span data-stu-id="d13c2-139">Use Microsoft Outlook from outside your corporate network to connect to your on-premises Exchange mailbox.</span></span>

  - <span data-ttu-id="d13c2-140">Gebruik de Microsoft [Exchange Remote Connectivity Analyzer om](https://www.testexchangeconnectivity.com/) uw verbindingsinstellingen te testen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-140">Use the Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) to test your connection settings.</span></span> <span data-ttu-id="d13c2-141">Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-141">Use the Outlook Anywhere (RPC over HTTP) or Outlook Autodiscover tests.</span></span>

  - <span data-ttu-id="d13c2-142">Voer de volgende opdrachten uit in Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d13c2-142">Run the following commands in Exchange Online PowerShell.</span></span>

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- <span data-ttu-id="d13c2-143">**Wijs een on-premises gebruikersaccount de benodigde machtigingen toe voor toegang tot postvakken in uw Exchange-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-143">**Assign an on-premises user account the necessary permissions to access mailboxes in your Exchange organization.**</span></span> <span data-ttu-id="d13c2-144">Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel de migratiebeheerder genoemd) moet de benodigde machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d13c2-144">The on-premises user account that you use to connect to your on-premises Exchange organization (also called the migration administrator) must have the necessary permissions to access the on-premises mailboxes that you want to migrate to Microsoft 365.</span></span> <span data-ttu-id="d13c2-145">Dit gebruikersaccount wordt gebruikt om een migratie-eindpunt naar uw on-premises organisatie te maken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-145">This user account is used to create a migration endpoint to your on-premises organization.</span></span>

    <span data-ttu-id="d13c2-146">In de volgende lijst ziet u de beheerdersbevoegdheden die nodig zijn voor het migreren van postvakken met een cutover-migratie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-146">The following list shows the administrative privileges required to migrate mailboxes using a cutover migration.</span></span> <span data-ttu-id="d13c2-147">Er zijn drie mogelijke opties.</span><span class="sxs-lookup"><span data-stu-id="d13c2-147">There are three possible options.</span></span>

  - <span data-ttu-id="d13c2-148">De migratiebeheerder moet lid zijn van de groep **Domeinbeheerders** in Active Directory in de on-premises organisatie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-148">The migration administrator must be a member of the **Domain Admins** group in Active Directory in the on-premises organization.</span></span>

    <span data-ttu-id="d13c2-149">Of</span><span class="sxs-lookup"><span data-stu-id="d13c2-149">Or</span></span>

  - <span data-ttu-id="d13c2-150">De migratiebeheerder moet voor elk on-premises postvak de machtiging **FullAccess** krijgen toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-150">The migration administrator must be assigned the **FullAccess** permission for each on-premises mailbox.</span></span>

    <span data-ttu-id="d13c2-151">Of</span><span class="sxs-lookup"><span data-stu-id="d13c2-151">Or</span></span>

  - <span data-ttu-id="d13c2-152">Aan de migratiebeheerder moet de machtiging **Ontvangen als** zijn toegewezen voor de on-premises postvakdatabase waarin de postvakken van gebruikers zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-152">The migration administrator must be assigned the **Receive As** permission on the on-premises mailbox database that stores the user mailboxes.</span></span>

- <span data-ttu-id="d13c2-153">**Unified Messaging uitschakelen.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-153">**Disable Unified Messaging.**</span></span> <span data-ttu-id="d13c2-154">Als de on-premises postvakken die u migreert, zijn ingeschakeld voor Unified Messaging (UM), moet u UM in de postvakken uitschakelen voordat u ze migreert.</span><span class="sxs-lookup"><span data-stu-id="d13c2-154">If the on-premises mailboxes you're migrating are enabled for Unified Messaging (UM), you have to disable UM on the mailboxes before you migrate them.</span></span> <span data-ttu-id="d13c2-155">U kunt um vervolgens inschakelen op de postvakken nadat de migratie is voltooid.</span><span class="sxs-lookup"><span data-stu-id="d13c2-155">You can then enable UM on the mailboxes after the migration is complete.</span></span>

- <span data-ttu-id="d13c2-156">**Beveiligingsgroepen en gedelegeerden** De e-mailmigratieservice kan niet detecteren of on-premises Active Directory-groepen beveiligingsgroepen zijn of niet, dus kunnen gemigreerde groepen niet worden ingericht als beveiligingsgroepen in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d13c2-156">**Security Groups and Delegates** The email migration service cannot detect whether on-premises Active Directory groups are security groups or not, so it cannot provision any migrated groups as security groups in Microsoft 365.</span></span> <span data-ttu-id="d13c2-157">Als u beveiligingsgroepen wilt hebben in uw Microsoft 365-tenant, moet u eerst een lege beveiligingsgroep met e-mail inrichten in uw Microsoft 365-tenant voordat u de cutover-migratie start.</span><span class="sxs-lookup"><span data-stu-id="d13c2-157">If you want to have security groups in your Microsoft 365 tenant, you must first provision an empty mail-enabled security group in your Microsoft 365 tenant before starting the cutover migration.</span></span> <span data-ttu-id="d13c2-158">Daarnaast worden met deze migratiemethode alleen postvakken, e-mailgebruikers, e-mailcontactpersonen en groepen die e-mail gebruiken, verplaatst.</span><span class="sxs-lookup"><span data-stu-id="d13c2-158">Additionally, this migration method only moves mailboxes, mail users, mail contacts, and mail-enabled groups.</span></span> <span data-ttu-id="d13c2-159">Als een ander Active Directory-object, zoals een gebruiker die niet is gemigreerd naar Microsoft 365, als manager of gedelegeerde is toegewezen aan een object dat wordt gemigreerd, moeten ze uit het object worden verwijderd voordat u migreert.</span><span class="sxs-lookup"><span data-stu-id="d13c2-159">If any other Active Directory object, such as user that is not migrated to Microsoft 365, is assigned as a manager or delegate to an object being migrated, they must be removed from the object before you migrate.</span></span>

### <a name="step-2-create-a-migration-endpoint"></a><span data-ttu-id="d13c2-160">Stap 2: Een migratie-eindpunt maken</span><span class="sxs-lookup"><span data-stu-id="d13c2-160">Step 2: Create a migration endpoint</span></span>
<span data-ttu-id="d13c2-161"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-161"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="d13c2-162">Als u e-mail wilt migreren, moet Microsoft 365 verbinding maken en communiceren met het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="d13c2-162">To migrate email successfully, Microsoft 365 needs to connect and communicate with the source email system.</span></span> <span data-ttu-id="d13c2-163">Hiervoor gebruikt Microsoft 365 een migratie-eindpunt.</span><span class="sxs-lookup"><span data-stu-id="d13c2-163">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="d13c2-164">Als u een Outlook Anywhere-migratie-eindpunt wilt maken voor cutover-migratie, maakt u [eerst verbinding met Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="d13c2-164">To create an Outlook Anywhere migration endpoint for cutover migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="d13c2-165">Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="d13c2-165">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="d13c2-166">Voer de volgende opdrachten uit in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d13c2-166">Run the following commands in Exchange Online PowerShell:</span></span>

```powershell
$Credentials = Get-Credential
```

<span data-ttu-id="d13c2-167">In het voorbeeld wordt de [cmdlet Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) gebruikt om de verbindingsinstellingen voor de on-premises Exchange-server te verkrijgen en te testen. Vervolgens worden deze verbindingsinstellingen gebruikt om het migratie-eindpunt 'CutoverEndpoint' te maken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-167">The example uses the [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) cmdlet to obtain and test the connection settings to the on-premises Exchange server, and then uses those connection settings to create the migration endpoint called "CutoverEndpoint".</span></span>

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> <span data-ttu-id="d13c2-168">De **cmdlet New-MigrationEndpoint** kan worden gebruikt om een database op te geven die de service moet gebruiken met de optie **-TargetDatabase.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-168">The **New-MigrationEndpoint** cmdlet can be used to specify a database for the service to use by using the **-TargetDatabase** option.</span></span> <span data-ttu-id="d13c2-169">Anders wordt een database willekeurig toegewezen vanuit de AD FS 2.0-site (Active Directory Federation Services) waar het managementpostvak zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="d13c2-169">Otherwise a database is randomly assigned from the Active Directory Federation Services (AD FS) 2.0 site where the management mailbox is located.</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="d13c2-170">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="d13c2-170">Verify it worked</span></span>

<span data-ttu-id="d13c2-171">Voer in Exchange Online PowerShell de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt CutoverEndpoint:</span><span class="sxs-lookup"><span data-stu-id="d13c2-171">In Exchange Online PowerShell, run the following command to display information about the "CutoverEndpoint" migration endpoint:</span></span>

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a><span data-ttu-id="d13c2-172">Stap 3: de cutover-migratiebatch maken</span><span class="sxs-lookup"><span data-stu-id="d13c2-172">Step 3: Create the cutover migration batch</span></span>
<span data-ttu-id="d13c2-173"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-173"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="d13c2-174">U kunt de **cmdlet New-MigrationBatch** in Exchange Online PowerShell gebruiken om een migratiebatch te maken voor een cutover-migratie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-174">You can use the **New-MigrationBatch** cmdlet in Exchange Online PowerShell to create a migration batch for a cutover migration.</span></span> <span data-ttu-id="d13c2-175">U kunt een migratiebatch maken en deze automatisch starten door de _parameter AutoStart op te_ nemen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-175">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="d13c2-176">U kunt ook de migratiebatch maken en daarna handmatig starten met de **cmdlet Start-MigrationBatch.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-176">Alternatively, you can create the migration batch and then manually start it afterwards by using the **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="d13c2-177">In dit voorbeeld wordt een migratiebatch gemaakt met de naam 'CutoverBatch' en wordt het migratie-eindpunt gebruikt dat is gemaakt in de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="d13c2-177">This example creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

<span data-ttu-id="d13c2-178">In dit voorbeeld wordt ook een migratiebatch gemaakt met de naam 'CutoverBatch' en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="d13c2-178">This example also creates a migration batch called "CutoverBatch" and uses the migration endpoint that was created in the previous step.</span></span> <span data-ttu-id="d13c2-179">Omdat de _parameter AutoStart_ niet is opgenomen, moet de migratiebatch handmatig worden gestart op het migratiedashboard of met de cmdlet **Start-MigrationBatch.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-179">Because the  _AutoStart_ parameter isn't included, the migration batch has to be manually started on the migration dashboard or by using **Start-MigrationBatch** cmdlet.</span></span> <span data-ttu-id="d13c2-180">Zoals eerder vermeld, kan er slechts één cutover-migratiebatch tegelijk bestaan.</span><span class="sxs-lookup"><span data-stu-id="d13c2-180">As previously stated, only one cutover migration batch can exist at a time.</span></span>

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a><span data-ttu-id="d13c2-181">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="d13c2-181">Verify it worked</span></span>

<span data-ttu-id="d13c2-182">Als u wilt controleren of u een migratiebatch voor een cutover-migratie hebt gemaakt, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell om informatie weer te geven over de nieuwe migratiebatch:</span><span class="sxs-lookup"><span data-stu-id="d13c2-182">To verify that you've successfully created a migration batch for a cutover migration, run the following command in Exchange Online PowerShell to display information about the new migration batch:</span></span>

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a><span data-ttu-id="d13c2-183">Stap 4: de cutover-migratiebatch starten</span><span class="sxs-lookup"><span data-stu-id="d13c2-183">Step 4: Start the cutover migration batch</span></span>
<span data-ttu-id="d13c2-184"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-184"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="d13c2-185">Voer de volgende opdracht uit om de migratiebatch in Exchange Online PowerShell te starten.</span><span class="sxs-lookup"><span data-stu-id="d13c2-185">To start the migration batch in Exchange Online PowerShell, run the following command.</span></span> <span data-ttu-id="d13c2-186">Hiermee wordt een migratiebatch met de naam 'CutoverBatch' aan het maken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-186">This will create a migration batch called "CutoverBatch".</span></span>

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a><span data-ttu-id="d13c2-187">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="d13c2-187">Verify it worked</span></span>

<span data-ttu-id="d13c2-188">Als een migratiebatch is gestart, wordt de status op het migratiedashboard opgegeven als Synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="d13c2-188">If a migration batch is successfully started, its status on the migration dashboard is specified as Syncing.</span></span> <span data-ttu-id="d13c2-189">Voer de volgende opdracht uit om te controleren of u een migratiebatch hebt gestart met Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d13c2-189">To verify that you've successfully started a migration batch using Exchange Online PowerShell, run the following command:</span></span>

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="d13c2-190">Stap 5: Uw e-mail door sturen naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d13c2-190">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="d13c2-191"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-191"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="d13c2-192">E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="d13c2-192">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="d13c2-193">Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="d13c2-193">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="d13c2-194">Nu de e-mailmigratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record aan te wijzen op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d13c2-194">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="d13c2-195">Dit helpt ervoor te zorgen dat e-mail wordt bezorgd in uw Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-195">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d13c2-196">Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="d13c2-196">By moving the MX record, you can also you turn off your old email system when you're ready.</span></span>

<span data-ttu-id="d13c2-197">Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="d13c2-197">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="d13c2-198">Voor het geval uw DNS-provider niet is opgenomen of als u een idee wilt krijgen van de algemene richtlijnen, worden ook de [algemene instructies voor MX-records](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) verstrekt.</span><span class="sxs-lookup"><span data-stu-id="d13c2-198">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) are provided as well.</span></span>

<span data-ttu-id="d13c2-199">Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend.</span><span class="sxs-lookup"><span data-stu-id="d13c2-199">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="d13c2-200">Wacht ten minste 72 uur voordat u verdergaat met de volgende taak: [Stap 6: De cutover-migratiebatch verwijderen.](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6)</span><span class="sxs-lookup"><span data-stu-id="d13c2-200">Wait at least 72 hours before you proceed to the next task: [Step 6: Delete the cutover migration batch](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).</span></span>

### <a name="step-6-delete-the-cutover-migration-batch"></a><span data-ttu-id="d13c2-201">Stap 6: de cutover-migratiebatch verwijderen</span><span class="sxs-lookup"><span data-stu-id="d13c2-201">Step 6: Delete the cutover migration batch</span></span>
<span data-ttu-id="d13c2-202"><a name="Bk_step6"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-202"><a name="Bk_step6"> </a></span></span>

<span data-ttu-id="d13c2-203">Nadat u de MX-record hebt gewijzigd en hebt gecontroleerd of alle e-mail wordt doorgestuurd naar Microsoft 365-postvakken, meldt u de gebruikers dat hun e-mail naar Microsoft 365 gaat.</span><span class="sxs-lookup"><span data-stu-id="d13c2-203">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="d13c2-204">Hierna kunt u de cutover-migratiebatch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-204">After this, you can delete the cutover migration batch.</span></span> <span data-ttu-id="d13c2-205">Controleer het volgende voordat u de migratiebatch verwijdert.</span><span class="sxs-lookup"><span data-stu-id="d13c2-205">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="d13c2-206">Alle gebruikers gebruiken Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-206">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="d13c2-207">Nadat de batch is verwijderd, wordt e-mail die naar postvakken op de on-premises Exchange Server wordt verzonden, niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="d13c2-207">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="d13c2-208">Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail rechtstreeks naar hen werd verzonden.</span><span class="sxs-lookup"><span data-stu-id="d13c2-208">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="d13c2-209">Als u dit wilt doen, moet u ervoor zorgen dat de waarde in het vak Laatst gesynchroniseerde tijd voor de migratiebatch recenter is dan wanneer e-mail rechtstreeks naar Microsoft 365-postvakken is gerouteerd.</span><span class="sxs-lookup"><span data-stu-id="d13c2-209">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="d13c2-210">Voer de volgende opdracht uit om de migratiebatch 'CutoverBatch' in Exchange Online PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="d13c2-210">To delete the "CutoverBatch" migration batch in Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a><span data-ttu-id="d13c2-211">Sectie 7: Gebruikerslicenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="d13c2-211">Section 7: Assign user licenses</span></span>
<span data-ttu-id="d13c2-212"><a name="BK_Step7"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-212"><a name="BK_Step7"> </a></span></span>

 <span data-ttu-id="d13c2-213">**Activeer Microsoft 365-gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-213">**Activate Microsoft 365 user accounts for the migrated accounts by assigning licenses.**</span></span> <span data-ttu-id="d13c2-214">Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-214">If you don't assign a license, the mailbox is disabled when the grace period ends (30 days).</span></span> <span data-ttu-id="d13c2-215">Zie Licenties toewijzen of niet toewijzen als u [](../admin/manage/assign-licenses-to-users.md)een licentie wilt toewijzen in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="d13c2-215">To assign a license in the Microsoft 365 admin center, see [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).</span></span>

### <a name="step-8-complete-post-migration-tasks"></a><span data-ttu-id="d13c2-216">Stap 8: Taken na de migratie voltooien</span><span class="sxs-lookup"><span data-stu-id="d13c2-216">Step 8: Complete post-migration tasks</span></span>
<span data-ttu-id="d13c2-217"><a name="BK_Step8"> </a></span><span class="sxs-lookup"><span data-stu-id="d13c2-217"><a name="BK_Step8"> </a></span></span>

- <span data-ttu-id="d13c2-218">**Maak een AutoDiscover DNS-record, zodat gebruikers gemakkelijk bij hun postvakken kunnen komen.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-218">**Create an Autodiscover DNS record so users can easily get to their mailboxes.**</span></span> <span data-ttu-id="d13c2-219">Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een AUTODISCOVER-DNS-record configureren voor uw Microsoft 365-organisatie, zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients.</span><span class="sxs-lookup"><span data-stu-id="d13c2-219">After all on-premises mailboxes are migrated to Microsoft 365, you can configure an Autodiscover DNS record for your Microsoft 365 organization to enable users to easily connect to their new Microsoft 365 mailboxes with Outlook and mobile clients.</span></span> <span data-ttu-id="d13c2-220">Deze nieuwe AUTODISCOVER DNS-record moet dezelfde naamruimte gebruiken die u gebruikt voor uw Microsoft 365-organisatie.</span><span class="sxs-lookup"><span data-stu-id="d13c2-220">This new Autodiscover DNS record has to use the same namespace that you're using for your Microsoft 365 organization.</span></span> <span data-ttu-id="d13c2-221">Als de naamruimte in de cloud bijvoorbeeld cloud.contoso.com, wordt de DNS-record voor automatisch zoeken die u moet maken, autodiscover.cloud.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d13c2-221">For example, if your cloud-based namespace is cloud.contoso.com, the Autodiscover DNS record you need to create is autodiscover.cloud.contoso.com.</span></span>

    <span data-ttu-id="d13c2-222">Als u uw Exchange Server houdt, moet u er ook voor zorgen dat de DNS-CNAME-record voor automatisch vinden naar Microsoft 365 moet wijzen in zowel interne als externe DNS na de migratie, zodat de Outlook-client verbinding maakt met het juiste postvak.</span><span class="sxs-lookup"><span data-stu-id="d13c2-222">If you keep your Exchange Server, you should also make sure that Autodiscover DNS CNAME record has to point to Microsoft 365 in both internal and external DNS after the migration so that the Outlook client will to connect to the correct mailbox.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d13c2-223">In Exchange 2007, Exchange 2010 en Exchange 2013 moet u ook instellen `Set-ClientAccessServer AutodiscoverInternalConnectionURI` op `Null` .</span><span class="sxs-lookup"><span data-stu-id="d13c2-223">In Exchange 2007, Exchange 2010, and Exchange 2013 you should also set `Set-ClientAccessServer AutodiscoverInternalConnectionURI` to `Null`.</span></span>

    <span data-ttu-id="d13c2-224">Microsoft 365 gebruikt een CNAME-record om de Autodiscover-service voor Outlook en mobiele clients te implementeren.</span><span class="sxs-lookup"><span data-stu-id="d13c2-224">Microsoft 365 uses a CNAME record to implement the Autodiscover service for Outlook and mobile clients.</span></span> <span data-ttu-id="d13c2-225">De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:</span><span class="sxs-lookup"><span data-stu-id="d13c2-225">The Autodiscover CNAME record must contain the following information:</span></span>

  - <span data-ttu-id="d13c2-226">**Alias:** autodiscover</span><span class="sxs-lookup"><span data-stu-id="d13c2-226">**Alias:** autodiscover</span></span>

  - <span data-ttu-id="d13c2-227">**Doel:** autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="d13c2-227">**Target:** autodiscover.outlook.com</span></span>

    <span data-ttu-id="d13c2-228">Zie DNS-records toevoegen [om uw domein te verbinden voor meer informatie.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="d13c2-228">For more information, see [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="d13c2-229">**On-premises Exchange-servers buiten bedrijf stellen.**</span><span class="sxs-lookup"><span data-stu-id="d13c2-229">**Decommission on-premises Exchange servers.**</span></span> <span data-ttu-id="d13c2-230">Nadat u hebt geverifieerd dat alle e-mail rechtstreeks naar de Microsoft 365-postvakken wordt gerouteerd en u uw on-premises e-mailorganisatie niet meer hoeft te onderhouden of niet van plan bent eenmalige aanmeldingsoplossing (SSO) te implementeren, kunt u Exchange van uw servers verwijderen en uw on-premises Exchange-organisatie verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d13c2-230">After you've verified that all email is being routed directly to the Microsoft 365 mailboxes, and you no longer need to maintain your on-premises email organization or don't plan on implementing a single sign-on (SSO) solution, you can uninstall Exchange from your servers and remove your on-premises Exchange organization.</span></span>

    <span data-ttu-id="d13c2-231">Zie de volgende onderwerpen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="d13c2-231">For more information, see the following:</span></span>

  - <span data-ttu-id="d13c2-232">[Exchange 2010 wijzigen of verwijderen](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span><span class="sxs-lookup"><span data-stu-id="d13c2-232">[Modify or Remove Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))</span></span>

  - <span data-ttu-id="d13c2-233">[Een Exchange 2007-organisatie verwijderen](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span><span class="sxs-lookup"><span data-stu-id="d13c2-233">[How to Remove an Exchange 2007 Organization](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))</span></span>

  - <span data-ttu-id="d13c2-234">[Exchange Server 2003 verwijderen](/previous-versions/tn-archive/bb125110(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="d13c2-234">[How to Uninstall Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))</span></span>