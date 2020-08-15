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
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>PowerShell gebruiken om een cutover-migratie uit te voeren naar Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met een cutover-migratie kunt u de inhoud van postvakken van gebruikers in één keer van het bron-e-mailsysteem migreren naar Microsoft 365. In dit artikel wordt u begeleid bij het uitvoeren van de taken voor een e-cutover-migratie via Exchange Online PowerShell. 
  
Als u het onderwerp controleert, [wat u moet weten over een cutover-e-mail migratie naar Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536688), krijgt u een overzicht van het migratieproces. Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.
  
> [!NOTE]
> U kunt ook het Exchange-Beheercentrum gebruiken om een cutover-migratie uit te voeren. Zie [een cutover-migratie uitvoeren van e-mail naar Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd voor het voltooien van deze taak: 2-5 minuten om een migratie batch te maken. Nadat de migratie batch is gestart, wordt de duur van de migratie verschillend gemaakt op basis van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie [migratie prestaties](https://go.microsoft.com/fwlink/p/?LinkId=275079)voor informatie over andere factoren die van invloed zijn op de manier waarop u postvakken gaat migreren naar microsoft 365.
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Als u wilt zien welke machtigingen u nodig hebt, raadpleegt u de vermelding ' Migration ' in een tabel in het onderwerp [machtigingen voor geadresseerden](https://go.microsoft.com/fwlink/p/?LinkId=534105) .
  
Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-a-cutover-migration"></a>Stap 1: een cutover-migratie voorbereiden
<a name="BK_Step1"> </a>

- **Voeg uw on-premises Exchange-organisatie toe als een geaccepteerd domein van uw Microsoft 365-organisatie.** De Migratieservice gebruikt het SMTP-adres van uw on-premises postvakken om de gebruikers-ID en het e-mailadres van Microsoft Online Services te maken voor de nieuwe postvakken van Microsoft 365. De migratie mislukt als uw Exchange-domein geen geaccepteerd domein of het primaire domein van uw Microsoft 365-organisatie is. Zie [uw domein verifiëren](https://go.microsoft.com/fwlink/p/?LinkId=534110)voor meer informatie.
    
- **Configureer Outlook op een plaats op uw on-premises Exchange-Server.** De e-mail Migratieservice maakt gebruik van RPC via HTTP, of Outlook Anywhere, om verbinding te maken met uw on-premises Exchange-Server. Raadpleeg de volgende onderwerpen voor meer informatie over het instellen van Outlook Anywhere voor Exchange Server 2010, Exchange 2007 en Exchange 2003:
    
  - [Exchange 2010: Outlook Anywhere inschakelen](https://go.microsoft.com/fwlink/?LinkID=187249)
    
  - [Exchange 2007: Outlook Anywhere inschakelen](https://go.microsoft.com/fwlink/?LinkID=167210)
    
  - [Exchange 2003: Implementatiescenario's voor RPC via HTTP](https://go.microsoft.com/fwlink/?LinkID=73657)
    
  - [Outlook Anywhere configureren met Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
    > [!IMPORTANT]
    > De configuratie van Outlook Anywhere moet worden geconfigureerd met een certificaat dat is uitgegeven door een vertrouwde certificeringsinstantie (CA). Het kan niet worden geconfigureerd met een zelfondertekend certificaat. Zie [SSL configureren voor Outlook voor](https://go.microsoft.com/fwlink/?LinkID=80875)meer informatie. 
  
- **Controleer of u verbinding kunt maken met uw Exchange-organisatie met Outlook Anywhere.** Ga op een van de volgende manieren te werk om uw verbindingsinstellingen te testen:
    
  - Gebruik Microsoft Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw on-premises Exchange-postvak.
    
  - Gebruik Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) om uw verbindingsinstellingen te testen. Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.
    
  - Voer de volgende opdrachten uit in Exchange Online PowerShell.
    
  ```
  $Credentials = Get-Credential
  ```

  ```
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Een on-premises gebruikersaccount toewijzen de benodigde machtigingen voor toegang tot postvakken in uw Exchange-organisatie.** Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel migratie beheerder genoemd), moet de juiste machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365. Dit gebruikersaccount wordt gebruikt voor het maken van een migratie-eindpunt naar uw on-premises organisatie.
    
    In de volgende lijst worden de beheerdersbevoegdheden weergegeven die nodig zijn voor het migreren van postvakken via een cutover-migratie. U kunt drie opties kiezen.
    
  - De migratie beheerder moet lid zijn van de groep **Domain Admins** in Active Directory in de on-premises organisatie.
    
    Of
    
  - De migratiebeheerder moet voor elk on-premises postvak de machtiging **FullAccess** krijgen toegewezen.
    
    Of
    
  - De migratie beheerder moet de machtiging **receive as** krijgen toegewezen voor de on-premises postvakdatabase waarin de postvakken van gebruikers worden opgeslagen.
    
- **Unified Messaging uitschakelen.** Als de on-premises postvakken die u wilt migreren, zijn ingeschakeld voor Unified Messaging (UM), moet u UM uitschakelen voor de postvakken voordat u ze migreert. U kunt vervolgens UM inschakelen voor de postvakken nadat de migratie is voltooid.
    
- **Beveiligingsgroepen en gemachtigden** De e-mail Migratieservice kan niet detecteren of on-premises Active Directory-groepen beveiligingsgroepen zijn, zodat het niet kan worden gemigreerd groepen als beveiligingsgroepen in Microsoft 365 te kunnen inrichten. Als u beveiligingsgroepen wilt hebben in uw Microsoft 365-Tenant, moet u eerst een lege beveiligingsgroep met e-mail inrichten in uw Microsoft 365-Tenant voordat u de cutover-migratie start. Daarnaast worden met deze migratiemethode alleen postvakken, e-mailgebruikers, e-mailcontactpersonen en groepen die e-mail gebruiken, verplaatst. Als een ander Active Directory-object, zoals een gebruiker die niet is gemigreerd naar Microsoft 365, is toegewezen als manager of gemachtigde voor een object dat wordt gemigreerd, moet deze uit het object worden verwijderd voordat u de migratie vermigreert.
    
### <a name="step-2-create-a-migration-endpoint"></a>Stap 2: een migratie-eindpunt maken
<a name="BK_Step2"> </a>

Voor het migreren van e-mail is Microsoft 365 nodig om verbinding te maken en te communiceren met het bron-e-mailsysteem. Hiervoor maakt Microsoft 365 gebruik van een migratie-eindpunt. Voor het maken van een migratie-eindpunt van Outlook Anywhere voor cutover-migratie, moet u eerst [verbinding maken met Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
Voer de volgende opdrachten uit in Exchange Online PowerShell:
  
```
$Credentials = Get-Credential
```

In het voorbeeld wordt de cmdlet [test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) gebruikt om de verbindingsinstellingen te verkrijgen en te testen op de on-premises Exchange-Server en worden vervolgens deze verbindingsinstellingen gebruikt om het migratie-eindpunt te maken met de naam ' CutoverEndpoint '.
  
```
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Met de cmdlet **New-MigrationEndpoint** kunt u een database opgeven voor de service die u wilt gebruiken met de optie **-TargetDatabase** . Anders wordt een database willekeurig toegewezen op de site van de AD FS-2,0 (Active Directory Federation Services) waar het postvak van het beheer zich bevindt.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

In Exchange Online PowerShell voert u de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt van CutoverEndpoint:
  
```
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Stap 3: de cutover-migratiebatch maken
<a name="BK_Step3"> </a>

U kunt de **New-MigrationBatch-** cmdlet in Exchange Online PowerShell gebruiken om een migratie batch voor een cutover-migratie te maken. U kunt een migratie batch maken en deze automatisch starten door de parameter van automatisch _starten_ op te nemen. U kunt de migratie batch ook maken en deze vervolgens handmatig opnieuw starten met behulp van de cmdlet **Start-MigrationBatch** . In het volgende voorbeeld wordt een migratie batch met de naam CutoverBatch en gebruikt het migratie-eindpunt dat in de vorige stap is gemaakt.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

In dit voorbeeld wordt ook een migratie batch met de naam ' CutoverBatch ' gemaakt en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt. Aangezien de parameter  _autostart_ niet is opgenomen, moet de migratie batch handmatig worden gestart op het migratie dashboard of met behulp van de cmdlet **Start-MigrationBatch** . Zoals eerder vermeld, kan slechts één cutover-migratie batch bestaan.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Als u wilt controleren of u een migratie batch voor een cutover-migratie hebt gemaakt, voert u de volgende opdracht uit in Exchange Online PowerShell om informatie over de nieuwe migratie batch weer te geven:
  
```
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Stap 4: de cutover-migratiebatch starten
<a name="BK_Step4"> </a>

Voer de volgende opdracht uit om de migratie batch te starten in Exchange Online PowerShell. Hiermee maakt u een migratie batch met de naam ' CutoverBatch '.
  
```
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Als een migratie batch is gestart, wordt de status van het migratie dashboard opgegeven als synchronisatie. Voer de volgende opdracht uit om te controleren of u een migratie batch met behulp van Exchange Online PowerShell hebt gestart:
  
```
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Stap 5: uw e-mail doorsturen naar Microsoft 365
<a name="BK_Step5"> </a>

E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd. Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem. Nu de e-mail migratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record te laten verwijzen naar Microsoft 365. Hiermee zorgt u ervoor dat e-mail wordt afgeleverd bij uw Microsoft 365-postvakken. Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent. 
  
Veel DNS-providers hebben specifieke instructies voor het [wijzigen van uw MX-record](https://go.microsoft.com/fwlink/p/?LinkId=279163). Als uw DNS-provider niet is opgenomen, of als u een idee wilt krijgen van de algemene instructies, worden ook [algemene MX-record instructies ](https://go.microsoft.com/fwlink/?LinkId=397449) weergegeven.
  
Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend. Wacht ten minste 72 uur voordat u verder gaat met de volgende taak: [stap 6: de cutover-migratie batch verwijderen](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6). 
  
### <a name="step-6-delete-the-cutover-migration-batch"></a>Stap 6: de cutover-migratiebatch verwijderen
<a name="Bk_step6"> </a>

Nadat u de MX-record hebt gewijzigd en gecontroleerd of alle e-mail wordt gerouteerd naar Microsoft 365-postvakken, waarschuwt u de gebruikers dat hun e-mailbericht naar Microsoft 365 gaat. Vervolgens kunt u de cutover-migratie batch verwijderen. Controleer het volgende voordat u de migratiebatch verwijdert.
  
- Alle gebruikers gebruiken Microsoft 365-postvakken. Wanneer de batch is verwijderd, wordt e-mail die is verzonden naar postvakken op de on-premises Exchange-Server niet gekopieerd naar de bijbehorende Microsoft 365-postvakken.
    
- Microsoft 365-postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail direct naar hem is verzonden. Zorg ervoor dat de waarde in het vak laatst gesynchroniseerde tijd voor de migratie batch uitgebreid is dan wanneer de e-mail direct naar Microsoft 365-postvakken wordt verzonden.
    
Voer de volgende opdracht uit om de CutoverBatch-migratie batch in Exchange Online PowerShell te verwijderen:
  
```
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Sectie 7: gebruikerslicenties toewijzen
<a name="BK_Step7"> </a>

 **Activeer Microsoft 365-gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen.** Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen. Zie [licenties toewijzen of intrekken](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)als u een licentie wilt toewijzen in het microsoft 365-Beheercentrum.
  
### <a name="step-8-complete-post-migration-tasks"></a>Stap 8: post-migratietaken voltooien
<a name="BK_Step8"> </a>

- **Maak een automatische detectie-DNS-record zodat gebruikers gemakkelijk toegang hebben tot hun postvakken.** Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een automatische detectie-DNS-record voor uw Microsoft 365-organisatie configureren zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients. Deze nieuwe DNS-record voor automatisch opsporen moet de naam van de naamruimte gebruiken die u gebruikt voor uw Microsoft 365-organisatie. Als bijvoorbeeld de naamruimte in de Cloud cloud.contoso.com is, is de DNS-record voor Autodiscover die u moet maken autodiscover.cloud.contoso.com.
    
    Als u uw Exchange-Server bijneemt, moet u er ook voor zorgen dat automatisch opsporen DNS CNAME-record moet verwijzen naar Microsoft 365 binnen interne en externe DNS na de migratie, zodat de Outlook-client verbinding kan maken met het juiste postvak.
    
    > [!NOTE]
    >  In Exchange 2007, Exchange 2010 en Exchange 2013 moet u ook instellen `Set-ClientAccessServer AutodiscoverInternalConnectionURI` `Null` . 
  
    Microsoft 365 gebruikt een CNAME-record om de Autodiscover-service voor Outlook en mobiele clients te implementeren. De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:
    
  - **Alias:** autodiscover
    
  - **Doel:** autodiscover.outlook.com
    
    Zie [DNS-records toevoegen om uw domein te verbinden](https://go.microsoft.com/fwlink/p/?LinkId=535028)voor meer informatie.
    
- **On-premises Exchange-servers buiten bedrijf stellen.** Nadat u hebt gecontroleerd of alle e-mailberichten rechtstreeks naar de 365-postvakken van Microsoft worden gerouteerd en u uw on-premises e-mail organisatie niet langer hoeft te onderhouden of niet meer wilt plannen om een SSO-oplossing (eenmalige aanmelding) te implementeren, kunt u Exchange van uw servers verwijderen en uw on-premises Exchange-organisatie verwijderen.
    
    Zie de volgende onderwerpen voor meer informatie:
    
  - [Exchange 2010 wijzigen of verwijderen](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Een Exchange 2007-organisatie verwijderen](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Exchange Server 2003 verwijderen](https://go.microsoft.com/fwlink/?LinkID=56561)
    

