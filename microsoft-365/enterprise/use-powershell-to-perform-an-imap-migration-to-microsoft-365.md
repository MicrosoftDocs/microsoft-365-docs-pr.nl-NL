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
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>PowerShell gebruiken om een IMAP-migratie naar Microsoft 365 uit te voeren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Als onderdeel van de implementatie van Microsoft 365, kunt u ervoor kiezen om de inhoud van postvakken van gebruikers te migreren van een IMAP-e-mail service (Internet mail Access Protocol) naar Microsoft 365. In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van een IMAP-migratie via Exchange Online PowerShell. 
  
> [!NOTE]
> U kunt ook het Exchange-Beheercentrum gebruiken om een IMAP-migratie uit te voeren. Zie [IMAP-postvakken migreren](https://go.microsoft.com/fwlink/p/?LinkId=536685). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd voor het voltooien van deze taak: 2-5 minuten om een migratie batch te maken. Nadat de migratie batch is gestart, wordt de duur van de migratie verschillend gemaakt op basis van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie [migratie prestaties](https://go.microsoft.com/fwlink/p/?LinkId=275079)voor informatie over andere factoren die van invloed zijn op de manier waarop u postvakken gaat migreren naar microsoft 365.
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Als u wilt zien welke machtigingen u nodig hebt, raadpleegt u de vermelding ' Migration ' in een tabel in het onderwerp [machtigingen voor geadresseerden](https://go.microsoft.com/fwlink/p/?LinkId=534105) .
  
Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
De volgende beperkingen zijn van toepassing op IMAP-migraties:
  
- Alleen items in het postvak in van een gebruiker of andere e-mailmappen kunnen worden gemigreerd. U kunt contactpersonen, agenda-items en taken niet migreren.
    
- Er kunnen maximaal 500.000 items worden gemigreerd vanuit het postvak van een gebruiker.
    
- De maximale grootte van berichten die kan worden gemigreerd is 35 MB.
    
## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-an-imap-migration"></a>Stap 1: een IMAP-migratie voorbereiden
<a name="BK_Step1"> </a>

- **Als u een domein hebt voor uw IMAP-organisatie, voegt u dit toe als een geaccepteerd domein van uw Microsoft 365-organisatie.** Als u het domein dat u al hebt gebruikt voor uw Microsoft 365-postvakken wilt gebruiken, moet u het eerst als een geaccepteerd domein toevoegen aan Microsoft 365. Nadat u de gebruikers hebt toegevoegd, kunt u uw gebruikers maken in Microsoft 365. Zie[uw domein verifiëren](https://go.microsoft.com/fwlink/p/?LinkId=534110)voor meer informatie.
    
- **Voeg een gebruiker toe aan Microsoft 365 zodat ze een postvak hebben.** Zie[gebruikers toevoegen aan Microsoft 365 voor bedrijven](https://go.microsoft.com/fwlink/p/?LinkId=535065)voor instructies.
    
- **Download de FQDN van de IMAP-server**. U moet de FQDN (Fully Qualified Domain Name)-naam (FULLy Qualified Domain Name) van de IMAP-server (ook wel de volledige computernaam genoemd) geven waarvan u postvakgegevens migreert wanneer u een IMAP-migratie-eindpunt gaat maken. Gebruik een IMAP-client of de opdracht PING om te controleren of u de FQDN kunt gebruiken om met de IMAP-server op internet te communiceren.
    
- **Configureer de firewall om IMAP-verbindingen toe te staan**. Het kan zijn dat u poorten in de firewall van de organisatie waarop de IMAP-server is gehost, moet openen, zodat het netwerkverkeer dat afkomstig is van het Microsoft datacenter via de migratie, wordt toegestaan voor de organisatie van de IMAP-server. Zie [url's en IP-](https://go.microsoft.com/fwlink/p/?LinkId=535066)adresbereiken voor Exchange Online voor een lijst met IP-adressen die worden gebruikt in Microsoft-datacenters.
    
- **Wijs de machtigingen van de beheerdersaccount toe voor toegang tot postvakken in de IMAP-organisatie**. Als u beheerdersreferenties in het CSV-bestand gebruikt, moet de account die u gebruikt beschikken over de vereiste machtigingen om toegang te kunnen krijgen tot de lokale postvakken. Welke machtigingen zijn vereist voor toegang tot postvakken van gebruikers wordt bepaald door de desbetreffende IMAP-server. 
    
- **Als u de Exchange Online PowerShell-cmdlets wilt gebruiken**, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.
    
    Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
    
- **Controleer of u verbinding kunt maken met de IMAP-server**. Voer de volgende opdracht uit in Exchange Online PowerShell om de verbindingsinstellingen te testen op de IMAP-server.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Voor de waarde van de **poort** parameter moet u 143 gebruiken voor niet-gecodeerde of TLS-verbindingen (Transport Layer Security) en gebruikt u 993 voor SSL-verbindingen.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Stap 2: een CSV-bestand maken voor een IMAP-migratie batch
<a name="BK_Step2"> </a>

Identificeer de groep gebruikers van wie u de postvakken die u wilt migreren in een IMAP-migratie batch. Elke rij in het CSV-bestand bevat gegevens die nodig zijn om verbinding te maken met een postvak in het IMAP-berichtensysteem.
  
Hier volgen de vereiste kenmerken voor elke gebruiker: 
  
- **EmailAddress** geeft de gebruikers-id voor het microsoft 365-postvak van de gebruiker op.
    
- **Gebruikersnaam** geeft de aanmeldingsnaam aan voor het account dat moet worden gebruikt om toegang te krijgen tot het postvak op de IMAP-server.
    
- **Password** Hiermee wordt het wachtwoord voor het account in de kolom **gebruikersnaam** aangegeven.
    
Hier volgt een voorbeeld van de indeling van het CSV-bestand. In dit voorbeeld worden drie postvakken gemigreerd:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Naast de gebruikersnaam van het kenmerk **username** , kunt u de referenties van een account gebruiken aan de beschikbare machtigingen voor toegang tot postvakken op de IMAP-server, zoals in de volgende specifieke indelingen voor sommige IMAP-servers:
  
 **Microsoft Exchange:**
  
Als u e-mail vanaf de IMAP-implementatie voor Microsoft Exchange migreert, gebruikt u de notatie **Domain/Admin_UserName/User_UserName** voor het **UserName** -kenmerk in het CSV-bestand. Stel dat u e-mail migreert van Exchange voor Terry Adams, Ann Beebe en Paul Cannon. U hebt een e-mail beheerder account, waarbij de gebruikersnaam e **-beheerder is en het** wachtwoord **P \@ ssw0rd**. Het CSV-bestand ziet er dan als volgt uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot**
  
Voor IMAP-servers die ondersteuning bieden voor eenvoudige verificatie en beveiligingslagen (SASL), zoals een dovecot-IMAP-server, gebruikt u de notatie **User_UserName * Admin_UserName**, waarbij het sterretje (*) een te configureren scheidingsteken is. Stel dat u de e-mail van deze gebruikers migreert van een IMAP-server van dovecot met behulp van de beheerdersreferenties **mailadmin** en **P \@ ssw0rd**. Het CSV-bestand ziet er dan als volgt uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint**
  
Als u e-mail migreert van Mirapoint bericht server, gebruikt u de indeling **#user \@ domein # Admin_UserName #** voor de beheerdersreferenties. Als u e-mail wilt migreren van Mirapoint met behulp van de beheerdersreferenties **mailadmin** en **P \@ SSW0RD**, ziet het CSV-bestand er als volgt uit:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Sommige bron-e-mail systemen, zoals Courier IMAP, ondersteunen geen postvak beheerdersreferenties voor het migreren van postvakken naar Microsoft 365. In plaats daarvan kunt u het bron-e-mailsysteem instellen voor het gebruik van virtuele gedeelde mappen. Met behulp van virtuele gedeelde mappen kunt u de referenties van de Postvak beheerder gebruiken voor toegang tot postvakken van gebruikers in het bron-e-mailsysteem. Zie [Gedeelde mappen](https://go.microsoft.com/fwlink/p/?LinkId=398870) voor meer informatie over het configureren van virtuele gedeelde mappen voor Courier IMAP.
  
Als u postvakken wilt migreren nadat u virtuele gedeelde mappen in het bron-e-mailsysteem hebt ingesteld, moet u het optionele kenmerk **UserRoot** opnemen in het migratiebestand. Dit kenmerk bevat de locatie van het postvak van elke gebruiker in de structuur van virtuele gedeelde mappen op het bron-e-mailsysteem. Het pad naar het postvak van Terry is bijvoorbeeld/users/Terry.Adams.
  
Hier volgt een voorbeeld van een CSV-bestand dat het kenmerk **UserRoot** bevat:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Stap 3: een IMAP-migratie-eindpunt maken
<a name="BK_Step3"> </a>

Voor het migreren van e-mail is Microsoft 365 nodig om verbinding te maken en te communiceren met het bron-e-mailsysteem. Hiervoor maakt Microsoft 365 gebruik van een migratie-eindpunt. Het migratie-eindpunt definieert ook het aantal te migreren postvakken, en het aantal postvakken dat moet worden gesynchroniseerd tijdens de incrementele synchronisatie, wat zich elke 24 uur voordoet. Als u een migratie-eindpunt wilt maken voor IMAP-migratie, moet u eerst [verbinding maken met Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
Voer de volgende opdracht uit als u het migratie-eindpunt van de IMAP-migratie met de naam ' IMAPEndpoint ' in Exchange Online PowerShell wilt maken:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

U kunt ook parameters toevoegen om gelijktijdige migraties, gelijktijdige migraties en de te gebruiken poort te specificeren. Met de volgende Exchange Online PowerShell-opdracht maakt u een IMAP-migratie-eindpunt met de naam ' IMAPEndpoint ' die ondersteuning biedt voor gelijktijdige migraties van 50 en maximaal 25 gelijktijdige incrementele synchronisaties. Ook wordt het eindpunt geconfigureerd voor gebruik van poort 143 voor TLS-versleuteling.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Zie[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)voor meer informatie over de **New-MigrationEndpoint** -cmdlet.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de IMAPEndpoint:
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Stap 4: een IMAP-migratie batch maken en starten
<a name="BK_Step4"> </a>

U kunt de [New-MigrationBatch-](https://go.microsoft.com/fwlink/p/?LinkId=536439) cmdlet gebruiken om een migratie batch voor een IMAP-migratie te maken. U kunt een migratie batch maken en deze automatisch starten door de parameter van automatisch _starten_ op te nemen. U kunt de migratie batch ook maken en deze vervolgens achteraf starten met behulp van de cmdlet[Start-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536440) .
  
Met de volgende Exchange Online PowerShell-opdracht start u automatisch de migratie batch met de naam ' IMAPBatch1 ' met behulp van het IMAP-eindpunt ' IMAPEndpoint ':
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de cmdlet [Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441) uit om informatie weer te geven over ' IMAPBatch1 ':
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Stap 5: uw e-mail doorsturen naar Microsoft 365
<a name="BK_Step5"> </a>

E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd. Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem. Nu de e-mail migratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record te laten verwijzen naar Microsoft 365. Hiermee zorgt u ervoor dat e-mail wordt afgeleverd bij uw Microsoft 365-postvakken. Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent. 
  
Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record. Als uw DNS-provider niet is opgenomen, of als u een idee wilt krijgen van de algemene instructies, worden ook [algemene MX-record instructies ](https://go.microsoft.com/fwlink/?LinkId=397449) weergegeven.
  
Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend. Wacht ten minste 72 uur voordat u verder gaat met de volgende taak: stap 6: IMAP-migratie batch verwijderen. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Stap 6: IMAP-migratie batch verwijderen
<a name="BK_Step6"> </a>

Nadat u de MX-record hebt gewijzigd en gecontroleerd of alle e-mail wordt gerouteerd naar Microsoft 365-postvakken, waarschuwt u de gebruikers dat hun e-mailbericht naar Microsoft 365 gaat. Vervolgens kunt u de IMAP-migratie batch verwijderen. Controleer het volgende voordat u de migratiebatch verwijdert.
  
- Alle gebruikers gebruiken Microsoft 365-postvakken. Wanneer de batch is verwijderd, wordt e-mail die is verzonden naar postvakken op de on-premises Exchange-Server niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.
    
- Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail direct naar hem is verzonden. Zorg ervoor dat de waarde in het vak laatst gesynchroniseerde tijd voor de migratie batch uitgebreid is dan wanneer de e-mail direct naar Microsoft 365-postvakken wordt verzonden.
    
Voer de volgende opdracht uit om de IMAPBatch1-migratie batch uit Exchange Online PowerShell te verwijderen:
  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Zie[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)voor meer informatie over de **Remove-MigrationBatch** -cmdlet.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de IMAPBatch1:
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

Met de opdracht wordt de migratie batch met de status **verwijderd**geretourneerd, of wordt een foutmelding weergegeven met de mededeling dat de batch niet kan worden gevonden en gecontroleerd of de batch is verwijderd.
  
Zie[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)voor meer informatie over de cmdlet **Get-MigrationBatch** .
  
## <a name="see-also"></a>Zie ook

[Probleemoplossing voor IMAP-migratie](https://go.microsoft.com/fwlink/p/?LinkId=536482)

