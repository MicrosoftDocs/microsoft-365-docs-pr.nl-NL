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
description: Informatie over het gebruik van PowerShell voor het uitvoeren van een IMAP-migratie (Internet mail Access Protocol) naar Microsoft 365.
ms.openlocfilehash: 67621ecfca7ec323a73b91a530f848dd7571f9b2
ms.sourcegitcommit: bcb88a6171f9e7bdb5b2d8c03cd628d11c5e7bbf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/14/2020
ms.locfileid: "48464442"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a><span data-ttu-id="c0864-103">PowerShell gebruiken om een IMAP-migratie naar Microsoft 365 uit te voeren</span><span class="sxs-lookup"><span data-stu-id="c0864-103">Use PowerShell to perform an IMAP migration to Microsoft 365</span></span>

<span data-ttu-id="c0864-104">*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c0864-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c0864-105">Als onderdeel van de implementatie van Microsoft 365, kunt u ervoor kiezen om de inhoud van postvakken van gebruikers te migreren van een IMAP-e-mail service (Internet mail Access Protocol) naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-105">As part of the process of deploying Microsoft 365, you can choose to migrate the contents of user mailboxes from an Internet Mail Access Protocol (IMAP) email service to Microsoft 365.</span></span> <span data-ttu-id="c0864-106">In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van een IMAP-migratie via Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0864-106">This article walks you through the tasks for an email IMAP migration by using Exchange Online PowerShell.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c0864-107">U kunt ook het Exchange-Beheercentrum gebruiken om een IMAP-migratie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c0864-107">You can also use the Exchange admin center to perform an IMAP migration.</span></span> <span data-ttu-id="c0864-108">Zie [IMAP-postvakken migreren](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span><span class="sxs-lookup"><span data-stu-id="c0864-108">See [Migrate your IMAP mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=536685).</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c0864-109">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c0864-109">What do you need to know before you begin?</span></span>

<span data-ttu-id="c0864-110">Geschatte tijd voor het voltooien van deze taak: 2-5 minuten om een migratie batch te maken.</span><span class="sxs-lookup"><span data-stu-id="c0864-110">Estimated time to complete this task: 2-5 minutes to create a migration batch.</span></span> <span data-ttu-id="c0864-111">Nadat de migratie batch is gestart, wordt de duur van de migratie verschillend gemaakt op basis van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit.</span><span class="sxs-lookup"><span data-stu-id="c0864-111">After the migration batch is started, the duration of the migration will vary based on the number of mailboxes in the batch, the size of each mailbox, and your available network capacity.</span></span> <span data-ttu-id="c0864-112">Zie [migratie prestaties](https://go.microsoft.com/fwlink/p/?LinkId=275079)voor informatie over andere factoren die van invloed zijn op de manier waarop u postvakken gaat migreren naar microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-112">For information about other factors that affect how long it takes to migrate mailboxes to Microsoft 365, see [Migration Performance](https://go.microsoft.com/fwlink/p/?LinkId=275079).</span></span>
  
<span data-ttu-id="c0864-113">U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="c0864-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="c0864-114">Als u wilt zien welke machtigingen u nodig hebt, raadpleegt u de vermelding ' Migration ' in een tabel in het onderwerp [machtigingen voor geadresseerden](https://go.microsoft.com/fwlink/p/?LinkId=534105) .</span><span class="sxs-lookup"><span data-stu-id="c0864-114">To see what permissions you need, see the "Migration" entry in a table in the [Recipients Permissions](https://go.microsoft.com/fwlink/p/?LinkId=534105) topic.</span></span>
  
<span data-ttu-id="c0864-115">Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="c0864-115">To use the Exchange Online PowerShell cmdlets, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="c0864-116">Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c0864-116">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
  
<span data-ttu-id="c0864-117">Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.</span><span class="sxs-lookup"><span data-stu-id="c0864-117">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="c0864-118">De volgende beperkingen zijn van toepassing op IMAP-migraties:</span><span class="sxs-lookup"><span data-stu-id="c0864-118">The following restrictions apply to IMAP migrations:</span></span>
  
- <span data-ttu-id="c0864-119">Alleen items in het postvak in van een gebruiker of andere e-mailmappen kunnen worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="c0864-119">Only items in a user's inbox or other mail folders can be migrated.</span></span> <span data-ttu-id="c0864-120">U kunt contactpersonen, agenda-items en taken niet migreren.</span><span class="sxs-lookup"><span data-stu-id="c0864-120">You can't migrate contacts, calendar items, or tasks.</span></span>
    
- <span data-ttu-id="c0864-121">Er kunnen maximaal 500.000 items worden gemigreerd vanuit het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="c0864-121">A maximum of 500,000 items can be migrated from a user's mailbox.</span></span>
    
- <span data-ttu-id="c0864-122">De maximale grootte van berichten die kan worden gemigreerd is 35 MB.</span><span class="sxs-lookup"><span data-stu-id="c0864-122">The maximum message size that can be migrated is 35 MB.</span></span>
    
## <a name="migration-steps"></a><span data-ttu-id="c0864-123">Migratiestappen</span><span class="sxs-lookup"><span data-stu-id="c0864-123">Migration steps</span></span>

### <a name="step-1-prepare-for-an-imap-migration"></a><span data-ttu-id="c0864-124">Stap 1: een IMAP-migratie voorbereiden</span><span class="sxs-lookup"><span data-stu-id="c0864-124">Step 1: Prepare for an IMAP migration</span></span>
<span data-ttu-id="c0864-125"><a name="BK_Step1"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-125"><a name="BK_Step1"> </a></span></span>

- <span data-ttu-id="c0864-126">**Als u een domein hebt voor uw IMAP-organisatie, voegt u dit toe als een geaccepteerd domein van uw Microsoft 365-organisatie.**</span><span class="sxs-lookup"><span data-stu-id="c0864-126">**If you have a domain for you IMAP organization, add it as an accepted domain of your Microsoft 365 organization.**</span></span> <span data-ttu-id="c0864-127">Als u het domein dat u al hebt gebruikt voor uw Microsoft 365-postvakken wilt gebruiken, moet u het eerst als een geaccepteerd domein toevoegen aan Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-127">If you want to use the same domain you already own for your Microsoft 365 mailboxes, you first have to add it as an accepted domain to Microsoft 365.</span></span> <span data-ttu-id="c0864-128">Nadat u de gebruikers hebt toegevoegd, kunt u uw gebruikers maken in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-128">After you have added it, you can create your users in Microsoft 365.</span></span> <span data-ttu-id="c0864-129">Zie[uw domein verifiëren](https://go.microsoft.com/fwlink/p/?LinkId=534110)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c0864-129">For more information, see[Verify your domain](https://go.microsoft.com/fwlink/p/?LinkId=534110).</span></span>
    
- <span data-ttu-id="c0864-130">**Voeg een gebruiker toe aan Microsoft 365 zodat ze een postvak hebben.**</span><span class="sxs-lookup"><span data-stu-id="c0864-130">**Add each user to Microsoft 365 so that they have a mailbox.**</span></span> <span data-ttu-id="c0864-131">Zie[gebruikers toevoegen aan Microsoft 365 voor bedrijven](https://go.microsoft.com/fwlink/p/?LinkId=535065)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c0864-131">For instructions, see[Add users to Microsoft 365 for business](https://go.microsoft.com/fwlink/p/?LinkId=535065).</span></span>
    
- <span data-ttu-id="c0864-132">**Download de FQDN van de IMAP-server**.</span><span class="sxs-lookup"><span data-stu-id="c0864-132">**Obtain the FQDN of the IMAP server**.</span></span> <span data-ttu-id="c0864-133">U moet de FQDN (Fully Qualified Domain Name)-naam (FULLy Qualified Domain Name) van de IMAP-server (ook wel de volledige computernaam genoemd) geven waarvan u postvakgegevens migreert wanneer u een IMAP-migratie-eindpunt gaat maken.</span><span class="sxs-lookup"><span data-stu-id="c0864-133">You need to provide the fully qualified domain name (FQDN) (also called the full computer name) of the IMAP server that you will migrate mailbox data from when you create an IMAP migration endpoint.</span></span> <span data-ttu-id="c0864-134">Gebruik een IMAP-client of de opdracht PING om te controleren of u de FQDN kunt gebruiken om met de IMAP-server op internet te communiceren.</span><span class="sxs-lookup"><span data-stu-id="c0864-134">Use an IMAP client or the PING command to verify that you can use the FQDN to communicate with the IMAP server over the Internet.</span></span>
    
- <span data-ttu-id="c0864-135">**Configureer de firewall om IMAP-verbindingen toe te staan**.</span><span class="sxs-lookup"><span data-stu-id="c0864-135">**Configure the firewall to allow IMAP connections**.</span></span> <span data-ttu-id="c0864-136">Het kan zijn dat u poorten in de firewall van de organisatie waarop de IMAP-server is gehost, moet openen, zodat het netwerkverkeer dat afkomstig is van het Microsoft datacenter via de migratie, wordt toegestaan voor de organisatie van de IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="c0864-136">You might have to open ports in the firewall of the organization that hosts the IMAP server so network traffic originating from the Microsoft datacenter during the migration is allowed to enter the organization that hosts the IMAP server.</span></span> <span data-ttu-id="c0864-137">Zie [url's en IP-](https://go.microsoft.com/fwlink/p/?LinkId=535066)adresbereiken voor Exchange Online voor een lijst met IP-adressen die worden gebruikt in Microsoft-datacenters.</span><span class="sxs-lookup"><span data-stu-id="c0864-137">For a list of IP addresses used by Microsoft datacenters, see [Exchange Online URLs and IP Address Ranges](https://go.microsoft.com/fwlink/p/?LinkId=535066).</span></span>
    
- <span data-ttu-id="c0864-138">**Wijs de machtigingen van de beheerdersaccount toe voor toegang tot postvakken in de IMAP-organisatie**.</span><span class="sxs-lookup"><span data-stu-id="c0864-138">**Assign the administrator account permissions to access mailboxes in your IMAP organization**.</span></span> <span data-ttu-id="c0864-139">Als u beheerdersreferenties in het CSV-bestand gebruikt, moet de account die u gebruikt beschikken over de vereiste machtigingen om toegang te kunnen krijgen tot de lokale postvakken.</span><span class="sxs-lookup"><span data-stu-id="c0864-139">If you use administrator credentials in the CSV file, the account that you use must have the necessary permissions to access the on-premises mailboxes.</span></span> <span data-ttu-id="c0864-140">Welke machtigingen zijn vereist voor toegang tot postvakken van gebruikers wordt bepaald door de desbetreffende IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="c0864-140">The permissions required to access user mailboxes is determined by the particular IMAP server.</span></span> 
    
- <span data-ttu-id="c0864-141">**Als u de Exchange Online PowerShell-cmdlets wilt gebruiken**, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="c0864-141">**To use the Exchange Online PowerShell cmdlets**, you need to sign in and import the cmdlets into your local Windows PowerShell session.</span></span> <span data-ttu-id="c0864-142">Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="c0864-142">See [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) for instructions.</span></span>
    
    <span data-ttu-id="c0864-143">Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.</span><span class="sxs-lookup"><span data-stu-id="c0864-143">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
    
- <span data-ttu-id="c0864-144">**Controleer of u verbinding kunt maken met de IMAP-server**.</span><span class="sxs-lookup"><span data-stu-id="c0864-144">**Verify that you can connect to your IMAP server**.</span></span> <span data-ttu-id="c0864-145">Voer de volgende opdracht uit in Exchange Online PowerShell om de verbindingsinstellingen te testen op de IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="c0864-145">Run the following command in Exchange Online PowerShell to test the connection settings to your IMAP server.</span></span>
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    <span data-ttu-id="c0864-146">Voor de waarde van de **poort** parameter moet u 143 gebruiken voor niet-gecodeerde of TLS-verbindingen (Transport Layer Security) en gebruikt u 993 voor SSL-verbindingen.</span><span class="sxs-lookup"><span data-stu-id="c0864-146">For the value of the **Port** parameter, it's typical to use 143 for unencrypted or Transport Layer Security (TLS) connections and to use 993 for SSL connections.</span></span>
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a><span data-ttu-id="c0864-147">Stap 2: een CSV-bestand maken voor een IMAP-migratie batch</span><span class="sxs-lookup"><span data-stu-id="c0864-147">Step 2: Create a CSV file for an IMAP migration batch</span></span>
<span data-ttu-id="c0864-148"><a name="BK_Step2"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-148"><a name="BK_Step2"> </a></span></span>

<span data-ttu-id="c0864-149">Identificeer de groep gebruikers van wie u de postvakken die u wilt migreren in een IMAP-migratie batch.</span><span class="sxs-lookup"><span data-stu-id="c0864-149">Identify the group of users whose mailboxes you want to migrate in an IMAP migration batch.</span></span> <span data-ttu-id="c0864-150">Elke rij in het CSV-bestand bevat gegevens die nodig zijn om verbinding te maken met een postvak in het IMAP-berichtensysteem.</span><span class="sxs-lookup"><span data-stu-id="c0864-150">Each row in the CSV file contains information necessary to connect to a mailbox in the IMAP messaging system.</span></span>
  
<span data-ttu-id="c0864-151">Hier volgen de vereiste kenmerken voor elke gebruiker:</span><span class="sxs-lookup"><span data-stu-id="c0864-151">Here are the required attributes for each user:</span></span> 
  
- <span data-ttu-id="c0864-152">**EmailAddress** geeft de gebruikers-id voor het microsoft 365-postvak van de gebruiker op.</span><span class="sxs-lookup"><span data-stu-id="c0864-152">**EmailAddress** specifies the user ID for the user's Microsoft 365 mailbox.</span></span>
    
- <span data-ttu-id="c0864-153">**Gebruikersnaam** geeft de aanmeldingsnaam aan voor het account dat moet worden gebruikt om toegang te krijgen tot het postvak op de IMAP-server.</span><span class="sxs-lookup"><span data-stu-id="c0864-153">**UserName** specifies the logon name for the account to use to access the mailbox on the IMAP server.</span></span>
    
- <span data-ttu-id="c0864-154">**Password** Hiermee wordt het wachtwoord voor het account in de kolom **gebruikersnaam** aangegeven.</span><span class="sxs-lookup"><span data-stu-id="c0864-154">**Password** specifies the password for the account in the **UserName** column.</span></span>
    
<span data-ttu-id="c0864-155">Hier volgt een voorbeeld van de indeling van het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="c0864-155">Here's an example of the format for the CSV file.</span></span> <span data-ttu-id="c0864-156">In dit voorbeeld worden drie postvakken gemigreerd:</span><span class="sxs-lookup"><span data-stu-id="c0864-156">In this example, three mailboxes are migrated:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

<span data-ttu-id="c0864-157">Naast de gebruikersnaam van het kenmerk **username** , kunt u de referenties van een account gebruiken aan de beschikbare machtigingen voor toegang tot postvakken op de IMAP-server, zoals in de volgende specifieke indelingen voor sommige IMAP-servers:</span><span class="sxs-lookup"><span data-stu-id="c0864-157">For the **UserName** attribute, in addition to the user name, you can use the credentials of an account that has been assigned the necessary permissions to access mailboxes on the IMAP server, the following are some of the specific formats used for some of the IMAP servers:</span></span>
  
 <span data-ttu-id="c0864-158">**Microsoft Exchange:**</span><span class="sxs-lookup"><span data-stu-id="c0864-158">**Microsoft Exchange:**</span></span>
  
<span data-ttu-id="c0864-159">Als u e-mail vanaf de IMAP-implementatie voor Microsoft Exchange migreert, gebruikt u de notatie **Domain/Admin_UserName/User_UserName** voor het **UserName** -kenmerk in het CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="c0864-159">If you're migrating email from the IMAP implementation for Microsoft Exchange, use the format **Domain/Admin_UserName/User_UserName** for the **UserName** attribute in the CSV file.</span></span> <span data-ttu-id="c0864-160">Stel dat u e-mail migreert van Exchange voor Terry Adams, Ann Beebe en Paul Cannon.</span><span class="sxs-lookup"><span data-stu-id="c0864-160">Let's say you're migrating email from Exchange for Terry Adams, Ann Beebe, and Paul Cannon.</span></span> <span data-ttu-id="c0864-161">U hebt een e-mail beheerder account, waarbij de gebruikersnaam e **-beheerder is en het** wachtwoord **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="c0864-161">You have a mail administrator account, where the user name is **mailadmin** and the password is **P\@ssw0rd**.</span></span> <span data-ttu-id="c0864-162">Het CSV-bestand ziet er dan als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c0864-162">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 <span data-ttu-id="c0864-163">**Dovecot**</span><span class="sxs-lookup"><span data-stu-id="c0864-163">**Dovecot:**</span></span>
  
<span data-ttu-id="c0864-164">Voor IMAP-servers die ondersteuning bieden voor eenvoudige verificatie en beveiligingslagen (SASL), zoals een dovecot-IMAP-server, gebruikt u de notatie **User_UserName \* Admin_UserName**, waarbij het sterretje (\*) een te configureren scheidingsteken is.</span><span class="sxs-lookup"><span data-stu-id="c0864-164">For IMAP servers that support Simple Authentication and Security Layer (SASL), such as a Dovecot IMAP server, use the format **User_UserName\*Admin_UserName**, where the asterisk ( \* ) is a configurable separator character.</span></span> <span data-ttu-id="c0864-165">Stel dat u de e-mail van deze gebruikers migreert van een IMAP-server van dovecot met behulp van de beheerdersreferenties **mailadmin** en **P \@ ssw0rd**.</span><span class="sxs-lookup"><span data-stu-id="c0864-165">Let's say you're migrating those same users' email from a Dovecot IMAP server using the administrator credentials **mailadmin** and **P\@ssw0rd**.</span></span> <span data-ttu-id="c0864-166">Het CSV-bestand ziet er dan als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c0864-166">Here's what your CSV file would look like:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 <span data-ttu-id="c0864-167">**Mirapoint**</span><span class="sxs-lookup"><span data-stu-id="c0864-167">**Mirapoint:**</span></span>
  
<span data-ttu-id="c0864-168">Als u e-mail migreert van Mirapoint bericht server, gebruikt u de indeling **#user \@ domein # Admin_UserName #** voor de beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="c0864-168">If you're migrating email from Mirapoint Message Server, use the format **#user\@domain#Admin_UserName#** for the administrator credentials.</span></span> <span data-ttu-id="c0864-169">Als u e-mail wilt migreren van Mirapoint met behulp van de beheerdersreferenties **mailadmin** en **P \@ SSW0RD**, ziet het CSV-bestand er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="c0864-169">To migrate email from Mirapoint using the administrator credentials **mailadmin** and **P\@ssw0rd**, your CSV file would look like this:</span></span>
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 <span data-ttu-id="c0864-170">**Courier IMAP:**</span><span class="sxs-lookup"><span data-stu-id="c0864-170">**Courier IMAP:**</span></span>
  
<span data-ttu-id="c0864-171">Sommige bron-e-mail systemen, zoals Courier IMAP, ondersteunen geen postvak beheerdersreferenties voor het migreren van postvakken naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-171">Some source email systems, such as Courier IMAP, don't support using mailbox admin credentials to migrate mailboxes to Microsoft 365.</span></span> <span data-ttu-id="c0864-172">In plaats daarvan kunt u het bron-e-mailsysteem instellen voor het gebruik van virtuele gedeelde mappen.</span><span class="sxs-lookup"><span data-stu-id="c0864-172">Instead, you can set up your source email system to use virtual shared folders.</span></span> <span data-ttu-id="c0864-173">Met behulp van virtuele gedeelde mappen kunt u de referenties van de Postvak beheerder gebruiken voor toegang tot postvakken van gebruikers in het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="c0864-173">By using virtual shared folders, you can use the mailbox admin credentials to access user mailboxes on the source email system.</span></span> <span data-ttu-id="c0864-174">Zie [Gedeelde mappen](https://go.microsoft.com/fwlink/p/?LinkId=398870) voor meer informatie over het configureren van virtuele gedeelde mappen voor Courier IMAP.</span><span class="sxs-lookup"><span data-stu-id="c0864-174">For more information about how to configure virtual shared folders for Courier IMAP, see [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).</span></span>
  
<span data-ttu-id="c0864-175">Als u postvakken wilt migreren nadat u virtuele gedeelde mappen in het bron-e-mailsysteem hebt ingesteld, moet u het optionele kenmerk **UserRoot** opnemen in het migratiebestand.</span><span class="sxs-lookup"><span data-stu-id="c0864-175">To migrate mailboxes after you set up virtual shared folders on your source email system, you have to include the optional attribute **UserRoot** in the migration file.</span></span> <span data-ttu-id="c0864-176">Dit kenmerk bevat de locatie van het postvak van elke gebruiker in de structuur van virtuele gedeelde mappen op het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="c0864-176">This attribute specifies the location of each user's mailbox in the virtual shared folder structure on the source email system.</span></span> <span data-ttu-id="c0864-177">Het pad naar het postvak van Terry is bijvoorbeeld/users/Terry.Adams.</span><span class="sxs-lookup"><span data-stu-id="c0864-177">For example, the path to Terry's mailbox is /users/terry.adams.</span></span>
  
<span data-ttu-id="c0864-178">Hier volgt een voorbeeld van een CSV-bestand dat het kenmerk **UserRoot** bevat:</span><span class="sxs-lookup"><span data-stu-id="c0864-178">Here's an example of a CSV file that contains the **UserRoot** attribute:</span></span>
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a><span data-ttu-id="c0864-179">Stap 3: een IMAP-migratie-eindpunt maken</span><span class="sxs-lookup"><span data-stu-id="c0864-179">Step 3: Create an IMAP migration endpoint</span></span>
<span data-ttu-id="c0864-180"><a name="BK_Step3"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-180"><a name="BK_Step3"> </a></span></span>

<span data-ttu-id="c0864-181">Voor het migreren van e-mail is Microsoft 365 nodig om verbinding te maken en te communiceren met het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="c0864-181">To migrate email successfully, Microsoft 365 needs to connect to and communicate with the source email system.</span></span> <span data-ttu-id="c0864-182">Hiervoor maakt Microsoft 365 gebruik van een migratie-eindpunt.</span><span class="sxs-lookup"><span data-stu-id="c0864-182">To do this, Microsoft 365 uses a migration endpoint.</span></span> <span data-ttu-id="c0864-183">Het migratie-eindpunt definieert ook het aantal te migreren postvakken, en het aantal postvakken dat moet worden gesynchroniseerd tijdens de incrementele synchronisatie, wat zich elke 24 uur voordoet.</span><span class="sxs-lookup"><span data-stu-id="c0864-183">The migration endpoint also defines the number of mailboxes to migrate simultaneously and the number of mailboxes to synchronize simultaneously during incremental synchronization, which occurs once every 24 hours.</span></span> <span data-ttu-id="c0864-184">Als u een migratie-eindpunt wilt maken voor IMAP-migratie, moet u eerst [verbinding maken met Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span><span class="sxs-lookup"><span data-stu-id="c0864-184">To create a migration end point for IMAP migration, first [connect to Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121).</span></span> 
  
<span data-ttu-id="c0864-185">Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.</span><span class="sxs-lookup"><span data-stu-id="c0864-185">For a full list of migration commands, see [Move and migration cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).</span></span>
  
<span data-ttu-id="c0864-186">Voer de volgende opdracht uit als u het migratie-eindpunt van de IMAP-migratie met de naam ' IMAPEndpoint ' in Exchange Online PowerShell wilt maken:</span><span class="sxs-lookup"><span data-stu-id="c0864-186">To create the IMAP migration endpoint called "IMAPEndpoint" in Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

<span data-ttu-id="c0864-187">U kunt ook parameters toevoegen om gelijktijdige migraties, gelijktijdige migraties en de te gebruiken poort te specificeren.</span><span class="sxs-lookup"><span data-stu-id="c0864-187">You can also add parameters to specify concurrent migrations, concurrent incremental migrations, and the port to use.</span></span> <span data-ttu-id="c0864-188">Met de volgende Exchange Online PowerShell-opdracht maakt u een IMAP-migratie-eindpunt met de naam ' IMAPEndpoint ' die ondersteuning biedt voor gelijktijdige migraties van 50 en maximaal 25 gelijktijdige incrementele synchronisaties.</span><span class="sxs-lookup"><span data-stu-id="c0864-188">The following Exchange Online PowerShell command creates an IMAP migration endpoint called "IMAPEndpoint" that supports 50 concurrent migrations and up to 25 concurrent incremental synchronizations.</span></span> <span data-ttu-id="c0864-189">Ook wordt het eindpunt geconfigureerd voor gebruik van poort 143 voor TLS-versleuteling.</span><span class="sxs-lookup"><span data-stu-id="c0864-189">It also configures the endpoint to use port 143 for TLS encryption.</span></span>
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

<span data-ttu-id="c0864-190">Zie[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)voor meer informatie over de **New-MigrationEndpoint** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c0864-190">For more information about the **New-MigrationEndpoint** cmdlet, see[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="c0864-191">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="c0864-191">Verify it worked</span></span>

<span data-ttu-id="c0864-192">Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de IMAPEndpoint:</span><span class="sxs-lookup"><span data-stu-id="c0864-192">Run the following command in Exchange Online PowerShell to display information about the "IMAPEndpoint":</span></span>
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a><span data-ttu-id="c0864-193">Stap 4: een IMAP-migratie batch maken en starten</span><span class="sxs-lookup"><span data-stu-id="c0864-193">Step 4: Create and start an IMAP migration batch</span></span>
<span data-ttu-id="c0864-194"><a name="BK_Step4"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-194"><a name="BK_Step4"> </a></span></span>

<span data-ttu-id="c0864-195">U kunt de [New-MigrationBatch-](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet gebruiken om een migratie batch voor een IMAP-migratie te maken.</span><span class="sxs-lookup"><span data-stu-id="c0864-195">You can use the [New-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet to create a migration batch for an IMAP migration.</span></span> <span data-ttu-id="c0864-196">U kunt een migratie batch maken en deze automatisch starten door de parameter van automatisch _starten_ op te nemen.</span><span class="sxs-lookup"><span data-stu-id="c0864-196">You can create a migration batch and start it automatically by including the _AutoStart_ parameter.</span></span> <span data-ttu-id="c0864-197">U kunt de migratie batch ook maken en deze vervolgens achteraf starten met behulp van de cmdlet[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) .</span><span class="sxs-lookup"><span data-stu-id="c0864-197">Alternatively, you can create the migration batch and then start it afterwards by using the[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) cmdlet.</span></span>
  
<span data-ttu-id="c0864-198">Met de volgende Exchange Online PowerShell-opdracht start u automatisch de migratie batch met de naam ' IMAPBatch1 ' met behulp van het IMAP-eindpunt ' IMAPEndpoint ':</span><span class="sxs-lookup"><span data-stu-id="c0864-198">The following Exchange Online PowerShell command will automatically start the migration batch called "IMAPBatch1" using the IMAP endpoint called "IMAPEndpoint":</span></span>
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a><span data-ttu-id="c0864-199">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="c0864-199">Verify it worked</span></span>

<span data-ttu-id="c0864-200">Voer de cmdlet [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) uit om informatie weer te geven over ' IMAPBatch1 ':</span><span class="sxs-lookup"><span data-stu-id="c0864-200">Run the [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) cmdlet to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

<span data-ttu-id="c0864-201">U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="c0864-201">You can also verify that the batch has started by running the following command:</span></span>
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a><span data-ttu-id="c0864-202">Stap 5: uw e-mail doorsturen naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c0864-202">Step 5: Route your email to Microsoft 365</span></span>
<span data-ttu-id="c0864-203"><a name="BK_Step5"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-203"><a name="BK_Step5"> </a></span></span>

<span data-ttu-id="c0864-204">E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd.</span><span class="sxs-lookup"><span data-stu-id="c0864-204">Email systems use a DNS record called an MX record to figure out where to deliver emails.</span></span> <span data-ttu-id="c0864-205">Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem.</span><span class="sxs-lookup"><span data-stu-id="c0864-205">During the email migration process, your MX record was pointing to your source email system.</span></span> <span data-ttu-id="c0864-206">Nu de e-mail migratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record te laten verwijzen naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c0864-206">Now that the email migration to Microsoft 365 is complete, it's time to point your MX record at Microsoft 365.</span></span> <span data-ttu-id="c0864-207">Hiermee zorgt u ervoor dat e-mail wordt afgeleverd bij uw Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="c0864-207">This helps make sure that email is delivered to your Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c0864-208">Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="c0864-208">By moving the MX record, you can also turn off your old email system when you're ready.</span></span> 
  
<span data-ttu-id="c0864-209">Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record.</span><span class="sxs-lookup"><span data-stu-id="c0864-209">For many DNS providers, there are specific instructions to change your MX record.</span></span> <span data-ttu-id="c0864-210">Als uw DNS-provider niet is opgenomen, of als u een idee wilt krijgen van de algemene instructies, worden ook [algemene MX-record instructies ](https://go.microsoft.com/fwlink/?LinkId=397449) weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c0864-210">If your DNS provider isn't included, or if you want to get a sense of the general directions, [general MX record instructions ](https://go.microsoft.com/fwlink/?LinkId=397449) are provided as well.</span></span>
  
<span data-ttu-id="c0864-211">Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend.</span><span class="sxs-lookup"><span data-stu-id="c0864-211">It can take up to 72 hours for the email systems of your customers and partners to recognize the changed MX record.</span></span> <span data-ttu-id="c0864-212">Wacht ten minste 72 uur voordat u verder gaat met de volgende taak: stap 6: IMAP-migratie batch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c0864-212">Wait at least 72 hours before you proceed to the next task: Step 6: Delete IMAP migration batch.</span></span> 
  
### <a name="step-6-delete-imap-migration-batch"></a><span data-ttu-id="c0864-213">Stap 6: IMAP-migratie batch verwijderen</span><span class="sxs-lookup"><span data-stu-id="c0864-213">Step 6: Delete IMAP migration batch</span></span>
<span data-ttu-id="c0864-214"><a name="BK_Step6"> </a></span><span class="sxs-lookup"><span data-stu-id="c0864-214"><a name="BK_Step6"> </a></span></span>

<span data-ttu-id="c0864-215">Nadat u de MX-record hebt gewijzigd en gecontroleerd of alle e-mail wordt gerouteerd naar Microsoft 365-postvakken, waarschuwt u de gebruikers dat hun e-mailbericht naar Microsoft 365 gaat.</span><span class="sxs-lookup"><span data-stu-id="c0864-215">After you change the MX record and verify that all email is being routed to Microsoft 365 mailboxes, notify the users that their mail is going to Microsoft 365.</span></span> <span data-ttu-id="c0864-216">Vervolgens kunt u de IMAP-migratie batch verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c0864-216">After this, you can delete the IMAP migration batch.</span></span> <span data-ttu-id="c0864-217">Controleer het volgende voordat u de migratiebatch verwijdert.</span><span class="sxs-lookup"><span data-stu-id="c0864-217">Verify the following before you delete the migration batch.</span></span>
  
- <span data-ttu-id="c0864-218">Alle gebruikers gebruiken Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="c0864-218">All users are using Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c0864-219">Wanneer de batch is verwijderd, wordt e-mail die is verzonden naar postvakken op de on-premises Exchange-Server niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.</span><span class="sxs-lookup"><span data-stu-id="c0864-219">After the batch is deleted, mail sent to mailboxes on the on-premises Exchange Server isn't copied to the corresponding Microsoft 365 mailboxes.</span></span>
    
- <span data-ttu-id="c0864-220">Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail direct naar hem is verzonden.</span><span class="sxs-lookup"><span data-stu-id="c0864-220">Microsoft 365 mailboxes were synchronized at least once after mail began being sent directly to them.</span></span> <span data-ttu-id="c0864-221">Zorg ervoor dat de waarde in het vak laatst gesynchroniseerde tijd voor de migratie batch uitgebreid is dan wanneer de e-mail direct naar Microsoft 365-postvakken wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="c0864-221">To do this, make sure that the value in the Last Synced Time box for the migration batch is more recent than when mail started being routed directly to Microsoft 365 mailboxes.</span></span>
    
<span data-ttu-id="c0864-222">Voer de volgende opdracht uit om de IMAPBatch1-migratie batch uit Exchange Online PowerShell te verwijderen:</span><span class="sxs-lookup"><span data-stu-id="c0864-222">To delete the "IMAPBatch1" migration batch from Exchange Online PowerShell, run the following command:</span></span>
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

<span data-ttu-id="c0864-223">Zie[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)voor meer informatie over de **Remove-MigrationBatch** -cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c0864-223">For more information about the **Remove-MigrationBatch** cmdlet, see[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481).</span></span>
  
#### <a name="verify-it-worked"></a><span data-ttu-id="c0864-224">Controleren of het werkt</span><span class="sxs-lookup"><span data-stu-id="c0864-224">Verify it worked</span></span>

<span data-ttu-id="c0864-225">Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de IMAPBatch1:</span><span class="sxs-lookup"><span data-stu-id="c0864-225">Run the following command in Exchange Online PowerShell to display information about the "IMAPBatch1":</span></span>
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

<span data-ttu-id="c0864-226">Met de opdracht wordt de migratie batch met de status **verwijderd**geretourneerd, of wordt een foutmelding weergegeven met de mededeling dat de batch niet kan worden gevonden en gecontroleerd of de batch is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="c0864-226">The command will return either the migration batch with a status of **Removing**, or it will return an error stating that migration batch couldn't be found, verifying that the batch was deleted.</span></span>
  
<span data-ttu-id="c0864-227">Zie[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)voor meer informatie over de cmdlet **Get-MigrationBatch** .</span><span class="sxs-lookup"><span data-stu-id="c0864-227">For more information about the **Get-MigrationBatch** cmdlet, see[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c0864-228">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c0864-228">See also</span></span>

[<span data-ttu-id="c0864-229">Probleemoplossing voor IMAP-migratie</span><span class="sxs-lookup"><span data-stu-id="c0864-229">IMAP Migration Troubleshooter</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=536482)

