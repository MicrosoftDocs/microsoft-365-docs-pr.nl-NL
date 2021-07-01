---
title: PowerShell gebruiken om een IMAP-migratie naar Microsoft 365 uit te voeren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Meer informatie over het gebruik van PowerShell om een IMAP-migratie (Internet Mail Access Protocol) uit te voeren naar Microsoft 365.
ms.openlocfilehash: 679cf222d7474349907d1c21f38a30b5fd86f798
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229633"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="ae267-103">PowerShell gebruiken om een IMAP-migratie naar Microsoft 365 uit te voeren</span><span class="sxs-lookup"><span data-stu-id="ae267-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="ae267-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ae267-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="ae267-105">Als onderdeel van het implementatieproces van Microsoft 365 kunt u ervoor kiezen om de inhoud van gebruikerspostvakken te migreren van een IMAP-e-mailservice (Internet Mail Access Protocol) naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="ae267-106">In dit artikel vindt u een overzicht van de taken voor een E-mail-IMAP-migratie met Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae267-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="ae267-107">U kunt ook het Exchange gebruiken om een IMAP-migratie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ae267-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="ae267-108">Zie [Uw IMAP-postvakken migreren.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="ae267-108">See [Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ae267-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="ae267-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="ae267-110">Geschatte tijd om deze taak te voltooien: 2-5 minuten om een migratiebatch te maken.</span><span class="sxs-lookup"><span data-stu-id="ae267-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="ae267-111">Nadat de migratiebatch is gestart, is de duur van de migratie afhankelijk van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit.</span><span class="sxs-lookup"><span data-stu-id="ae267-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="ae267-112">Zie Migratieprestaties voor informatie over andere factoren die van invloed zijn op hoe lang het duurt om postvakken naar Microsoft 365 [te migreren.](/Exchange/mailbox-migration/office-365-migration-best-practices)</span><span class="sxs-lookup"><span data-stu-id="ae267-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).</span></span>

<span data-ttu-id="ae267-113">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ae267-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="ae267-114">Als u wilt zien welke machtigingen u nodig hebt, ziet u de vermelding 'Migratie' in een tabel in het onderwerp [Machtigingen geadresseerden.](/exchange/recipients-permissions-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="ae267-114">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](/exchange/recipients-permissions-exchange-2013-help) topic.</span></span>

<span data-ttu-id="ae267-115">Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell sessie.</span><span class="sxs-lookup"><span data-stu-id="ae267-115">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="ae267-116">Zie [Verbinding maken om Exchange Online externe PowerShell te gebruiken voor](/powershell/exchange/connect-to-exchange-online-powershell) instructies.</span><span class="sxs-lookup"><span data-stu-id="ae267-116">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

<span data-ttu-id="ae267-117">Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="ae267-117">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="ae267-118">De volgende beperkingen zijn van toepassing op IMAP-migraties:</span><span class="sxs-lookup"><span data-stu-id="ae267-118">The following restrictions apply to IMAP migrations:</span></span>

- <span data-ttu-id="ae267-119">Alleen items in het Postvak IN of andere e-mailmappen van een gebruiker kunnen worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="ae267-119">Only items in a user's inbox or other mail folders can be migrated.</span></span> <span data-ttu-id="ae267-120">U kunt contactpersonen, agenda-items of taken niet migreren.</span><span class="sxs-lookup"><span data-stu-id="ae267-120">You can't migrate contacts, calendar items, or tasks.</span></span>

- <span data-ttu-id="ae267-121">Er kunnen maximaal 500.000 items worden gemigreerd vanuit het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ae267-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>

- <span data-ttu-id="ae267-122">De maximale berichtgrootte die kan worden gemigreerd, is 35 MB.</span><span class="sxs-lookup"><span data-stu-id="ae267-122">The maximum message size that can be migrated is 35 MB.</span></span>

## <a name="migration-steps"></a><span data-ttu-id="ae267-123">Migratiestappen</span><span class="sxs-lookup"><span data-stu-id="ae267-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="ae267-124">Stap 1: Voorbereiden op een IMAP-migratie</span><span class="sxs-lookup"><span data-stu-id="ae267-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="ae267-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="ae267-126">**Als u een domein voor uw IMAP-organisatie hebt, voegt u dit toe als een geaccepteerd domein van uw Microsoft 365 organisatie.**</span><span class="sxs-lookup"><span data-stu-id="ae267-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="ae267-127">Als u hetzelfde domein wilt gebruiken dat u al hebt voor uw Microsoft 365 postvakken, moet u dit eerst als geaccepteerd domein toevoegen aan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="ae267-128">Nadat u het hebt toegevoegd, kunt u uw gebruikers maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="ae267-129">Zie Uw domein verifiëren[voor meer informatie.](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="ae267-129">For more information, see[Verify your domain](../admin/setup/add-domain.md).</span></span>

- <span data-ttu-id="ae267-130">**Voeg elke gebruiker toe aan Microsoft 365 zodat deze een postvak heeft.**</span><span class="sxs-lookup"><span data-stu-id="ae267-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="ae267-131">Zie Gebruikers toevoegen[aan Microsoft 365 voor bedrijven voor instructies.](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="ae267-131">For instructions, see[Add users to Microsoft 365 for business](../admin/add-users/add-users.md).</span></span>

- <span data-ttu-id="ae267-132">**Verkrijg de FQDN van de IMAP-server.**</span><span class="sxs-lookup"><span data-stu-id="ae267-132">**Obtain the FQDN of the IMAP server**.</span></span> <span data-ttu-id="ae267-133">U moet de volledig gekwalificeerde domeinnaam (FQDN) (ook wel de volledige computernaam genoemd) van de IMAP-server verstrekken waar u postvakgegevens van migreert wanneer u een IMAP-migratie-eindpunt maakt.</span><span class="sxs-lookup"><span data-stu-id="ae267-133">You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint.</span></span> <span data-ttu-id="ae267-134">Gebruik een IMAP-client of de opdracht PING om te controleren of u de FQDN kunt gebruiken om met de IMAP-server op internet te communiceren.</span><span class="sxs-lookup"><span data-stu-id="ae267-134">Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>

- <span data-ttu-id="ae267-135">**Configureer de firewall om IMAP-verbindingen toe te staan.**</span><span class="sxs-lookup"><span data-stu-id="ae267-135">**Configure the firewall to allow IMAP connections**.</span></span> <span data-ttu-id="ae267-136">Mogelijk moet u poorten openen in de firewall van de organisatie die de IMAP-server host, zodat netwerkverkeer dat afkomstig is uit het Microsoft-datacenter tijdens de migratie, de organisatie kan invoeren die de IMAP-server host.</span><span class="sxs-lookup"><span data-stu-id="ae267-136">You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server.</span></span> <span data-ttu-id="ae267-137">Zie voor een lijst met IP-adressen die door Microsoft-datacenters worden gebruikt [Exchange Online URL's en IP-adresbereiken.](./urls-and-ip-address-ranges.md)</span><span class="sxs-lookup"><span data-stu-id="ae267-137">For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](./urls-and-ip-address-ranges.md).</span></span>

- <span data-ttu-id="ae267-138">**Wijs de beheerdersaccountmachtigingen toe voor toegang tot postvakken in uw IMAP-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="ae267-138">**Assign the administrator account permissions to access mailboxes in your IMAP organization**.</span></span> <span data-ttu-id="ae267-139">Als u beheerdersreferenties in het CSV-bestand gebruikt, moet de account die u gebruikt beschikken over de vereiste machtigingen om toegang te kunnen krijgen tot de lokale postvakken.</span><span class="sxs-lookup"><span data-stu-id="ae267-139">If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes.</span></span> <span data-ttu-id="ae267-140">De machtigingen die nodig zijn voor toegang tot gebruikerspostvakken, worden bepaald door de specifieke IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="ae267-140">The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span>

- <span data-ttu-id="ae267-141">**Als u de Exchange Online PowerShell-cmdlets** wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell sessie.</span><span class="sxs-lookup"><span data-stu-id="ae267-141">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="ae267-142">Zie [Verbinding maken om Exchange Online externe PowerShell te gebruiken voor](/powershell/exchange/connect-to-exchange-online-powershell) instructies.</span><span class="sxs-lookup"><span data-stu-id="ae267-142">See [Connect to Exchange Online using remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) for instructions.</span></span>

    <span data-ttu-id="ae267-143">Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="ae267-143">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

- <span data-ttu-id="ae267-144">**Controleer of u verbinding kunt maken met uw IMAP-server.**</span><span class="sxs-lookup"><span data-stu-id="ae267-144">**Verify that you can connect to your IMAP server**.</span></span> <span data-ttu-id="ae267-145">Voer de volgende opdracht uit in Exchange Online PowerShell om de verbindingsinstellingen met uw IMAP-server te testen.</span><span class="sxs-lookup"><span data-stu-id="ae267-145">Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>

  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="ae267-146">Voor de waarde van de **parameter** Poort is het gebruikelijk om 143 te gebruiken voor niet-versleutelde of TLS-verbindingen (Transport Layer Security) en om 993 te gebruiken voor SSL-verbindingen.</span><span class="sxs-lookup"><span data-stu-id="ae267-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>

### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="ae267-147">Stap 2: Een CSV-bestand maken voor een IMAP-migratiebatch</span><span class="sxs-lookup"><span data-stu-id="ae267-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="ae267-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="ae267-149">Identificeer de groep gebruikers van wie u postvakken wilt migreren in een IMAP-migratiebatch.</span><span class="sxs-lookup"><span data-stu-id="ae267-149">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch.</span></span> <span data-ttu-id="ae267-150">Elke rij in het CSV-bestand bevat informatie die nodig is om verbinding te maken met een postvak in het IMAP-berichtensysteem.</span><span class="sxs-lookup"><span data-stu-id="ae267-150">Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>

<span data-ttu-id="ae267-151">Hier volgen de vereiste kenmerken voor elke gebruiker:</span><span class="sxs-lookup"><span data-stu-id="ae267-151">Here are the required attributes for each user:</span></span>

- <span data-ttu-id="ae267-152">**In EmailAddress** wordt de gebruikers-id opgegeven voor het postvak van Microsoft 365 gebruiker.</span><span class="sxs-lookup"><span data-stu-id="ae267-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>

- <span data-ttu-id="ae267-153">**UserName** geeft de aanmeldingsnaam op die het account moet gebruiken om toegang te krijgen tot het postvak op de IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="ae267-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>

- <span data-ttu-id="ae267-154">**Wachtwoord** geeft het wachtwoord voor het account op in de **kolom UserName.**</span><span class="sxs-lookup"><span data-stu-id="ae267-154">**Password** specifies the password for the account in the **UserName** column.</span></span>

<span data-ttu-id="ae267-155">Hier volgt een voorbeeld van de indeling van het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="ae267-155">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="ae267-156">In dit voorbeeld worden drie postvakken gemigreerd:</span><span class="sxs-lookup"><span data-stu-id="ae267-156">In this example, three mailboxes are migrated:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="ae267-157">Voor het kenmerk **UserName** kunt u naast de gebruikersnaam ook de referenties gebruiken van een account dat de benodigde machtigingen heeft gekregen voor toegang tot postvakken op de IMAP-server. Hieronder volgen enkele van de specifieke indelingen die voor sommige IMAP-servers worden gebruikt:</span><span class="sxs-lookup"><span data-stu-id="ae267-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>

 <span data-ttu-id="ae267-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="ae267-158">**Microsoft Exchange:**</span></span>

<span data-ttu-id="ae267-159">Als u e-mail vanaf de IMAP-implementatie voor Microsoft Exchange migreert, gebruikt u de notatie **Domain/Admin_UserName/User_UserName** voor het **UserName** -kenmerk in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="ae267-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="ae267-160">Stel dat u e-mail migreert van Exchange voor Terry Adams, Ann Beebe en Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="ae267-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="ae267-161">U hebt een e-mailbeheerderaccount, waarbij de gebruikersnaam **mailadmin** is en het wachtwoord **P \@ ssw0rd is.**</span><span class="sxs-lookup"><span data-stu-id="ae267-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="ae267-162">Het CSV-bestand ziet er dan als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ae267-162">Here's what your CSV file would look like:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="ae267-163">**Dovecot:**</span><span class="sxs-lookup"><span data-stu-id="ae267-163">**Dovecot:**</span></span>

<span data-ttu-id="ae267-164">Voor IMAP-servers die SasL (Simple Authentication and Security Layer) ondersteunen, zoals een Dovecot IMAP-server, gebruikt u de indeling **User_UserName\*Admin_UserName,** waarbij het sterretje (\*) een configureerbaar scheidingsteken is.</span><span class="sxs-lookup"><span data-stu-id="ae267-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="ae267-165">Stel dat u de e-mail van dezelfde gebruikers migreert van een Dovecot IMAP-server met de beheerdersreferenties **mailadmin** en **P \@ ssw0rd.**</span><span class="sxs-lookup"><span data-stu-id="ae267-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="ae267-166">Het CSV-bestand ziet er dan als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="ae267-166">Here's what your CSV file would look like:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="ae267-167">**Mirapoint:**</span><span class="sxs-lookup"><span data-stu-id="ae267-167">**Mirapoint:**</span></span>

<span data-ttu-id="ae267-168">Als u e-mail migreert van Mirapoint Message Server, gebruikt u de indeling **#user \@ domein#Admin_UserName#** voor de beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="ae267-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="ae267-169">Als u e-mail wilt migreren van Mirapoint met de beheerdersreferenties **mailadmin** en **P \@ ssw0rd,** ziet uw CSV-bestand er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="ae267-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>

```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="ae267-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="ae267-170">**Courier IMAP:**</span></span>

<span data-ttu-id="ae267-171">Sommige bron-e-mailsystemen, zoals Courier IMAP, ondersteunen het gebruik van postvakbeheerdersreferenties niet om postvakken te migreren naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="ae267-172">In plaats daarvan kunt u het bron-e-mailsysteem instellen voor het gebruik van virtuele gedeelde mappen.</span><span class="sxs-lookup"><span data-stu-id="ae267-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="ae267-173">Door virtuele gedeelde mappen te gebruiken, kunt u de referenties van de postvakbeheerder gebruiken om toegang te krijgen tot postvakken van gebruikers in het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="ae267-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="ae267-174">Zie [Gedeelde mappen](https://go.microsoft.com/fwlink/p/?LinkId=398870) voor meer informatie over het configureren van virtuele gedeelde mappen voor Courier IMAP.</span><span class="sxs-lookup"><span data-stu-id="ae267-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>

<span data-ttu-id="ae267-175">Als u postvakken wilt migreren nadat u virtuele gedeelde mappen in het bron-e-mailsysteem hebt ingesteld, moet u het optionele kenmerk **UserRoot** opnemen in het migratiebestand.</span><span class="sxs-lookup"><span data-stu-id="ae267-175">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file.</span></span> <span data-ttu-id="ae267-176">Dit kenmerk bevat de locatie van het postvak van elke gebruiker in de structuur van virtuele gedeelde mappen op het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="ae267-176">This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system.</span></span> <span data-ttu-id="ae267-177">Het pad naar het postvak van Terry is bijvoorbeeld /users/terry.adams.</span><span class="sxs-lookup"><span data-stu-id="ae267-177">For example, the path to Terry's mailbox is /users/terry.adams.</span></span>

<span data-ttu-id="ae267-178">Hier volgt een voorbeeld van een CSV-bestand dat het kenmerk **UserRoot** bevat:</span><span class="sxs-lookup"><span data-stu-id="ae267-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>

```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="ae267-179">Stap 3: Een IMAP-migratie-eindpunt maken</span><span class="sxs-lookup"><span data-stu-id="ae267-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="ae267-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="ae267-181">Als u e-mail wilt migreren, Microsoft 365 verbinding maken met en communiceren met het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="ae267-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="ae267-182">Hiervoor wordt Microsoft 365 een migratie-eindpunt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ae267-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="ae267-183">Het migratie-eindpunt definieert ook het aantal postvakken dat tegelijk moet worden gemigreerd en het aantal postvakken dat tegelijk moet worden gesynchroniseerd tijdens incrementele synchronisatie, wat eenmaal per 24 uur plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="ae267-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="ae267-184">Als u een migratie-eindpunt wilt maken voor IMAP-migratie, maakt u eerst [verbinding met Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="ae267-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="ae267-185">Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)</span><span class="sxs-lookup"><span data-stu-id="ae267-185">For a full list of migration commands, see [Move and migration cmdlets](/powershell/exchange/).</span></span>

<span data-ttu-id="ae267-186">Voer de volgende opdracht uit als u het IMAP-migratie-eindpunt IMAPEndpoint wilt maken in Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ae267-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="ae267-187">U kunt ook parameters toevoegen om gelijktijdige migraties, gelijktijdige incrementele migraties en de te gebruiken poort op te geven.</span><span class="sxs-lookup"><span data-stu-id="ae267-187">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use.</span></span> <span data-ttu-id="ae267-188">Met de Exchange Online PowerShell wordt een IMAP-migratie-eindpunt gemaakt met de naam 'IMAPEndpoint' dat 50 gelijktijdige migraties en maximaal 25 gelijktijdige incrementele synchronisaties ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="ae267-188">The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations.</span></span> <span data-ttu-id="ae267-189">Het eindpunt wordt ook geconfigureerd voor het gebruik van poort 143 voor TLS-versleuteling.</span><span class="sxs-lookup"><span data-stu-id="ae267-189">It also configures the endpoint to use port 143 for TLS encryption.</span></span>

```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="ae267-190">Zie [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)voor meer informatie over de **cmdlet New-MigrationEndpoint** .</span><span class="sxs-lookup"><span data-stu-id="ae267-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="ae267-191">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="ae267-191">Verify it worked</span></span>

<span data-ttu-id="ae267-192">Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over het 'IMAPEndpoint':</span><span class="sxs-lookup"><span data-stu-id="ae267-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>

```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="ae267-193">Stap 4: een IMAP-migratiebatch maken en starten</span><span class="sxs-lookup"><span data-stu-id="ae267-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="ae267-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="ae267-195">U kunt de [cmdlet New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) gebruiken om een migratiebatch te maken voor een IMAP-migratie.</span><span class="sxs-lookup"><span data-stu-id="ae267-195">You can use the [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) cmdlet to create a migration batch for an IMAP migration.</span></span> <span data-ttu-id="ae267-196">U kunt een migratiebatch maken en deze automatisch starten door de _parameter AutoStart op te_ nemen.</span><span class="sxs-lookup"><span data-stu-id="ae267-196">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="ae267-197">U kunt ook de migratiebatch maken en daarna starten met de[cmdlet Start-MigrationBatch.](/powershell/module/exchange/start-migrationbatch)</span><span class="sxs-lookup"><span data-stu-id="ae267-197">Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch) cmdlet.</span></span>

<span data-ttu-id="ae267-198">De volgende Exchange Online PowerShell-opdracht start automatisch de migratiebatch genaamd 'IMAPBatch1' met het IMAP-eindpunt genaamd 'IMAPEndpoint':</span><span class="sxs-lookup"><span data-stu-id="ae267-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>

```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="ae267-199">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="ae267-199">Verify it worked</span></span>

<span data-ttu-id="ae267-200">Voer de [cmdlet Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) uit om informatie weer te geven over de 'IMAPBatch1':</span><span class="sxs-lookup"><span data-stu-id="ae267-200">Run the [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) cmdlet to display information about the "IMAPBatch1":</span></span>

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="ae267-201">U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="ae267-201">You can also verify that the batch has started by running the following command:</span></span>

```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="ae267-202">Stap 5: Uw e-mail door Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ae267-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="ae267-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="ae267-204">E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="ae267-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="ae267-205">Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="ae267-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="ae267-206">Nu de e-mailmigratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record op Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="ae267-207">Dit helpt ervoor te zorgen dat e-mail wordt bezorgd in Microsoft 365 postvakken.</span><span class="sxs-lookup"><span data-stu-id="ae267-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ae267-208">Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="ae267-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span>

<span data-ttu-id="ae267-209">Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="ae267-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="ae267-210">Voor het geval uw DNS-provider niet is opgenomen of als u een idee wilt krijgen van de algemene richtlijnen, worden ook de [algemene instructies voor MX-records](https://go.microsoft.com/fwlink/?LinkId=397449) verstrekt.</span><span class="sxs-lookup"><span data-stu-id="ae267-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>

<span data-ttu-id="ae267-211">Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend.</span><span class="sxs-lookup"><span data-stu-id="ae267-211">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="ae267-212">Wacht ten minste 72 uur voordat u naar de volgende taak gaat: Stap 6: IMAP-migratiebatch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ae267-212">Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span>

### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="ae267-213">Stap 6: IMAP-migratiebatch verwijderen</span><span class="sxs-lookup"><span data-stu-id="ae267-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="ae267-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="ae267-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="ae267-215">Nadat u de MX-record hebt gewijzigd en hebt gecontroleerd of alle e-mail wordt doorgestuurd naar Microsoft 365 postvakken, meldt u de gebruikers dat hun e-mail wordt Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae267-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="ae267-216">Hierna kunt u de IMAP-migratiebatch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ae267-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="ae267-217">Controleer het volgende voordat u de migratiebatch verwijdert.</span><span class="sxs-lookup"><span data-stu-id="ae267-217">Verify the following before you delete the migration batch.</span></span>

- <span data-ttu-id="ae267-218">Alle gebruikers gebruiken Microsoft 365 postvakken.</span><span class="sxs-lookup"><span data-stu-id="ae267-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="ae267-219">Nadat de batch is verwijderd, wordt e-mail die naar postvakken op de on-premises Exchange Server verzonden, niet gekopieerd naar de bijbehorende Microsoft 365 postvakken.</span><span class="sxs-lookup"><span data-stu-id="ae267-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>

- <span data-ttu-id="ae267-220">Microsoft 365 postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail rechtstreeks naar deze postvakken werd verzonden.</span><span class="sxs-lookup"><span data-stu-id="ae267-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="ae267-221">Als u dit wilt doen, moet u ervoor zorgen dat de waarde in het vak Laatst gesynchroniseerde tijd voor de migratiebatch recenter is dan toen e-mail rechtstreeks werd gerouteerd naar Microsoft 365 postvakken.</span><span class="sxs-lookup"><span data-stu-id="ae267-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="ae267-222">Voer de volgende opdracht uit om de migratiebatch1 van IMAPBatch1 uit Exchange Online PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="ae267-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>

```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="ae267-223">Zie [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)voor meer informatie over de cmdlet **Remove-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="ae267-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).</span></span>

#### <a name="verify-it-worked"></a><span data-ttu-id="ae267-224">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="ae267-224">Verify it worked</span></span>

<span data-ttu-id="ae267-225">Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de 'IMAPBatch1':</span><span class="sxs-lookup"><span data-stu-id="ae267-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>

```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="ae267-226">De opdracht retourneert de migratiebatch met de status **Verwijderen,** of de opdracht retourneert een fout waarin wordt aangegeven dat de migratiebatch niet kan worden gevonden en dat de batch is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ae267-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>

<span data-ttu-id="ae267-227">Zie [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)voor meer informatie over de cmdlet **Get-MigrationBatch.**</span><span class="sxs-lookup"><span data-stu-id="ae267-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).</span></span>

## <a name="see-also"></a><span data-ttu-id="ae267-228">Zie ook</span><span class="sxs-lookup"><span data-stu-id="ae267-228">See also</span></span>

[<span data-ttu-id="ae267-229">Probleemoplosser voor IMAP-migratie</span><span class="sxs-lookup"><span data-stu-id="ae267-229">IMAP Migration Troubleshooter</span></span>](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)