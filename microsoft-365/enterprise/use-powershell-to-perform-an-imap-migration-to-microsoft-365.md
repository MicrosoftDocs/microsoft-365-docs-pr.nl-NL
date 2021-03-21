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
description: Meer informatie over het gebruik van PowerShell om een IMAP-migratie (Internet Mail Access Protocol) naar Microsoft 365 uit te voeren.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924766"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>PowerShell gebruiken om een IMAP-migratie naar Microsoft 365 uit te voeren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als onderdeel van het implementatieproces van Microsoft 365 kunt u ervoor kiezen om de inhoud van gebruikerspostvakken te migreren van een IMAP-e-mailservice (Internet Mail Access Protocol) naar Microsoft 365. In dit artikel vindt u een overzicht van de taken voor een E-mail-IMAP-migratie met Exchange Online PowerShell. 
  
> [!NOTE]
> U kunt ook het Exchange-beheercentrum gebruiken om een IMAP-migratie uit te voeren. Zie [Uw IMAP-postvakken migreren.](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes) 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd om deze taak te voltooien: 2-5 minuten om een migratiebatch te maken. Nadat de migratiebatch is gestart, is de duur van de migratie afhankelijk van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie Migratieprestaties voor informatie over andere factoren die van invloed zijn [](/Exchange/mailbox-migration/office-365-migration-best-practices)op hoe lang het duurt om postvakken te migreren naar Microsoft 365.
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Als u wilt zien welke machtigingen u nodig hebt, ziet u de vermelding 'Migratie' in een tabel in het onderwerp [Machtigingen geadresseerden.](/exchange/recipients-permissions-exchange-2013-help)
  
Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [Verbinding maken met Exchange Online met behulp van externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) voor instructies.
  
Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)
  
De volgende beperkingen zijn van toepassing op IMAP-migraties:
  
- Alleen items in het Postvak IN of andere e-mailmappen van een gebruiker kunnen worden gemigreerd. U kunt contactpersonen, agenda-items of taken niet migreren.
    
- Er kunnen maximaal 500.000 items worden gemigreerd vanuit het postvak van een gebruiker.
    
- De maximale berichtgrootte die kan worden gemigreerd, is 35 MB.
    
## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-an-imap-migration"></a>Stap 1: Voorbereiden op een IMAP-migratie
<a name="BK_Step1"> </a>

- **Als u een domein voor uw IMAP-organisatie hebt, voegt u dit toe als een geaccepteerd domein van uw Microsoft 365-organisatie.** Als u hetzelfde domein wilt gebruiken dat u al hebt voor uw Microsoft 365-postvakken, moet u dit eerst als geaccepteerd domein toevoegen aan Microsoft 365. Nadat u deze hebt toegevoegd, kunt u uw gebruikers maken in Microsoft 365. Zie Uw domein verifiëren[voor meer informatie.](../admin/setup/add-domain.md)
    
- **Voeg elke gebruiker toe aan Microsoft 365, zodat deze een postvak heeft.** Zie Gebruikers toevoegen[aan Microsoft 365 voor Bedrijven](../admin/add-users/add-users.md)voor instructies.
    
- **Verkrijg de FQDN van de IMAP-server.** U moet de volledig gekwalificeerde domeinnaam (FQDN) (ook wel de volledige computernaam genoemd) van de IMAP-server verstrekken waar u postvakgegevens van migreert wanneer u een IMAP-migratie-eindpunt maakt. Gebruik een IMAP-client of de opdracht PING om te controleren of u de FQDN kunt gebruiken om met de IMAP-server op internet te communiceren.
    
- **Configureer de firewall om IMAP-verbindingen toe te staan.** Mogelijk moet u poorten openen in de firewall van de organisatie die de IMAP-server host, zodat netwerkverkeer dat afkomstig is uit het Microsoft-datacenter tijdens de migratie, de organisatie kan invoeren die de IMAP-server host. Zie URL's en IP-adresbereiken van Exchange Online voor een lijst met IP-adressen die door Microsoft-datacenters [worden gebruikt.](./urls-and-ip-address-ranges.md)
    
- **Wijs de beheerdersaccountmachtigingen toe voor toegang tot postvakken in uw IMAP-organisatie.** Als u beheerdersreferenties in het CSV-bestand gebruikt, moet de account die u gebruikt beschikken over de vereiste machtigingen om toegang te kunnen krijgen tot de lokale postvakken. De machtigingen die nodig zijn voor toegang tot gebruikerspostvakken, worden bepaald door de specifieke IMAP-server. 
    
- **Als u de Exchange Online PowerShell-cmdlets** wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [Verbinding maken met Exchange Online met behulp van externe PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) voor instructies.
    
    Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)
    
- **Controleer of u verbinding kunt maken met uw IMAP-server.** Voer de volgende opdracht uit in Exchange Online PowerShell om de verbindingsinstellingen naar uw IMAP-server te testen.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Voor de waarde van de **parameter** Poort is het gebruikelijk om 143 te gebruiken voor niet-versleutelde of TLS-verbindingen (Transport Layer Security) en om 993 te gebruiken voor SSL-verbindingen.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Stap 2: Een CSV-bestand maken voor een IMAP-migratiebatch
<a name="BK_Step2"> </a>

Identificeer de groep gebruikers van wie u postvakken wilt migreren in een IMAP-migratiebatch. Elke rij in het CSV-bestand bevat informatie die nodig is om verbinding te maken met een postvak in het IMAP-berichtensysteem.
  
Hier volgen de vereiste kenmerken voor elke gebruiker: 
  
- **EmailAddress** geeft de gebruikers-id voor het Microsoft 365-postvak van de gebruiker aan.
    
- **UserName** geeft de aanmeldingsnaam op die het account moet gebruiken om toegang te krijgen tot het postvak op de IMAP-server.
    
- **Wachtwoord** geeft het wachtwoord voor het account op in de **kolom UserName.**
    
Hier volgt een voorbeeld van de indeling van het CSV-bestand. In dit voorbeeld worden drie postvakken gemigreerd:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Voor het kenmerk **UserName** kunt u naast de gebruikersnaam ook de referenties gebruiken van een account dat de benodigde machtigingen heeft gekregen voor toegang tot postvakken op de IMAP-server. Hieronder volgen enkele van de specifieke indelingen die voor sommige IMAP-servers worden gebruikt:
  
 **Microsoft Exchange:**
  
Als u e-mail vanaf de IMAP-implementatie voor Microsoft Exchange migreert, gebruikt u de notatie **Domain/Admin_UserName/User_UserName** voor het **UserName** -kenmerk in het CSV-bestand. Stel dat u e-mail migreert van Exchange voor Terry Adams, Ann Beebe en Paul Cannon. U hebt een e-mailbeheerderaccount, waarbij de gebruikersnaam **mailadmin** is en het wachtwoord **P \@ ssw0rd is.** Het CSV-bestand ziet er dan als volgt uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot:**
  
Voor IMAP-servers die SasL (Simple Authentication and Security Layer) ondersteunen, zoals een Dovecot IMAP-server, gebruikt u de indeling **User_UserName*Admin_UserName,** waarbij het sterretje (*) een configureerbaar scheidingsteken is. Stel dat u de e-mail van dezelfde gebruikers migreert van een Dovecot IMAP-server met de beheerdersreferenties **mailadmin** en **P \@ ssw0rd.** Het CSV-bestand ziet er dan als volgt uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint:**
  
Als u e-mail migreert van Mirapoint Message Server, gebruikt u de indeling **#user \@ domein#Admin_UserName#** voor de beheerdersreferenties. Als u e-mail wilt migreren van Mirapoint met de beheerdersreferenties **mailadmin** en **P \@ ssw0rd,** ziet uw CSV-bestand er als volgende uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Sommige bron-e-mailsystemen, zoals Courier IMAP, ondersteunen het gebruik van postvakbeheerdersreferenties niet om postvakken te migreren naar Microsoft 365. In plaats daarvan kunt u het bron-e-mailsysteem instellen voor het gebruik van virtuele gedeelde mappen. Door virtuele gedeelde mappen te gebruiken, kunt u de referenties van de postvakbeheerder gebruiken om toegang te krijgen tot postvakken van gebruikers in het bron-e-mailsysteem. Zie [Gedeelde mappen](https://go.microsoft.com/fwlink/p/?LinkId=398870) voor meer informatie over het configureren van virtuele gedeelde mappen voor Courier IMAP.
  
Als u postvakken wilt migreren nadat u virtuele gedeelde mappen in het bron-e-mailsysteem hebt ingesteld, moet u het optionele kenmerk **UserRoot** opnemen in het migratiebestand. Dit kenmerk bevat de locatie van het postvak van elke gebruiker in de structuur van virtuele gedeelde mappen op het bron-e-mailsysteem. Het pad naar het postvak van Terry is bijvoorbeeld /users/terry.adams.
  
Hier volgt een voorbeeld van een CSV-bestand dat het kenmerk **UserRoot** bevat:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Stap 3: Een IMAP-migratie-eindpunt maken
<a name="BK_Step3"> </a>

Als u e-mail wilt migreren, moet Microsoft 365 verbinding maken met en communiceren met het bron-e-mailsysteem. Hiervoor gebruikt Microsoft 365 een migratie-eindpunt. Het migratie-eindpunt definieert ook het aantal postvakken dat tegelijk moet worden gemigreerd en het aantal postvakken dat tegelijk moet worden gesynchroniseerd tijdens incrementele synchronisatie, wat eenmaal per 24 uur plaatsvindt. Als u een migratie-eindpunt wilt maken voor IMAP-migratie, maakt u [eerst verbinding met Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell) 
  
Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)
  
Voer de volgende opdracht uit als u het IMAP-migratie-eindpunt 'IMAPEndpoint' wilt maken in Exchange Online PowerShell:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

U kunt ook parameters toevoegen om gelijktijdige migraties, gelijktijdige incrementele migraties en de te gebruiken poort op te geven. Met de volgende Exchange Online PowerShell-opdracht wordt een IMAP-migratie-eindpunt gemaakt met de naam 'IMAPEndpoint' dat 50 gelijktijdige migraties en maximaal 25 gelijktijdige incrementele synchronisaties ondersteunt. Het eindpunt wordt ook geconfigureerd voor het gebruik van poort 143 voor TLS-versleuteling.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Zie [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)voor meer informatie over de **cmdlet New-MigrationEndpoint** .
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over het 'IMAPEndpoint':
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Stap 4: een IMAP-migratiebatch maken en starten
<a name="BK_Step4"> </a>

U kunt de [cmdlet New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) gebruiken om een migratiebatch te maken voor een IMAP-migratie. U kunt een migratiebatch maken en deze automatisch starten door de _parameter AutoStart op te_ nemen. U kunt ook de migratiebatch maken en daarna starten met de[cmdlet Start-MigrationBatch.](/powershell/module/exchange/start-migrationbatch)
  
Met de volgende Exchange Online PowerShell-opdracht wordt automatisch de migratiebatch met de naam 'IMAPBatch1' starten met het IMAP-eindpunt genaamd 'IMAPEndpoint':
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de [cmdlet Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch) uit om informatie weer te geven over de 'IMAPBatch1':
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Stap 5: Uw e-mail door sturen naar Microsoft 365
<a name="BK_Step5"> </a>

E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd. Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem. Nu de e-mailmigratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record aan te wijzen op Microsoft 365. Dit helpt ervoor te zorgen dat e-mail wordt bezorgd in uw Microsoft 365-postvakken. Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent. 
  
Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record. Als uw DNS-provider niet is opgenomen of als u een idee wilt krijgen van de algemene aanwijzingen, worden ook algemene [MX-recordinstructies ](https://go.microsoft.com/fwlink/?LinkId=397449) verstrekt.
  
Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend. Wacht ten minste 72 uur voordat u naar de volgende taak gaat: Stap 6: IMAP-migratiebatch verwijderen. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Stap 6: IMAP-migratiebatch verwijderen
<a name="BK_Step6"> </a>

Nadat u de MX-record hebt gewijzigd en hebt gecontroleerd of alle e-mail wordt doorgestuurd naar Microsoft 365-postvakken, meldt u de gebruikers dat hun e-mail naar Microsoft 365 gaat. Hierna kunt u de IMAP-migratiebatch verwijderen. Controleer het volgende voordat u de migratiebatch verwijdert.
  
- Alle gebruikers gebruiken Microsoft 365-postvakken. Nadat de batch is verwijderd, wordt e-mail die naar postvakken op de on-premises Exchange Server wordt verzonden, niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.
    
- Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail rechtstreeks naar hen werd verzonden. Als u dit wilt doen, moet u ervoor zorgen dat de waarde in het vak Laatst gesynchroniseerde tijd voor de migratiebatch recenter is dan wanneer e-mail rechtstreeks naar Microsoft 365-postvakken is gerouteerd.
    
Voer de volgende opdracht uit om de migratiebatch1 -batch IMAPBatch1 uit Exchange Online PowerShell te verwijderen:
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Zie [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)voor meer informatie over de cmdlet **Remove-MigrationBatch** .
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de 'IMAPBatch1':
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

De opdracht retourneert de migratiebatch met de status **Verwijderen,** of de opdracht retourneert een fout waarin wordt aangegeven dat de migratiebatch niet kan worden gevonden en dat de batch is verwijderd.
  
Zie [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)voor meer informatie over de cmdlet **Get-MigrationBatch.**
  
## <a name="see-also"></a>Zie ook

[Probleemoplosser voor IMAP-migratie](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)