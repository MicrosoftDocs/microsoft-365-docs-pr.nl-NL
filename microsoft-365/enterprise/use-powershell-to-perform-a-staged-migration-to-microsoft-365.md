---
title: PowerShell gebruiken om een gefaseerde migratie uit te voeren naar Microsoft 365
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
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Meer informatie over het gebruik van PowerShell voor het verplaatsen van inhoud van een bron-e-mailsysteem via een gefaseerde migratie naar Microsoft 365.
ms.openlocfilehash: ebf2067fe7ae9fc2d2b58d0aa804c7843295b38a
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689099"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>PowerShell gebruiken om een gefaseerde migratie uit te voeren naar Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met een gefaseerde migratie kunt u de inhoud van postvakken van gebruikers in het bron-e-mailsysteem naar Microsoft 365 in de loop van de tijd migreren.
  
In dit artikel wordt u stapsgewijs begeleid bij het uitvoeren van taken met betrekking tot een gefaseerde e-mail migratie met Exchange Online PowerShell. [Wat u moet weten over een gefaseerde e-mail migratie](https://go.microsoft.com/fwlink/p/?LinkId=536487), biedt u een overzicht van het migratieproces. Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.
  
> [!NOTE]
> U kunt ook het Exchange-Beheercentrum gebruiken om gefaseerde migratie uit te voeren. Zie [een gefaseerde migratie van e-mail naar Microsoft 365 uitvoeren](https://go.microsoft.com/fwlink/p/?LinkId=536687). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd voor het voltooien van deze taak: 2-5 minuten om een migratie batch te maken. Nadat de migratie batch is gestart, wordt de duur van de migratie verschillend gemaakt op basis van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie [migratie prestaties](https://go.microsoft.com/fwlink/p/?LinkId=275079)voor informatie over andere factoren die van invloed zijn op de manier waarop u postvakken gaat migreren naar microsoft 365.
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Als u wilt zien welke machtigingen u nodig hebt, raadpleegt u de vermelding ' migratie ' in het onderwerp met [machtigingen voor geadresseerden](https://go.microsoft.com/fwlink/p/?LinkId=534105) .
  
Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell-sessie. Zie [verbinding maken met Exchange Online via externe PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=534121) voor instructies.
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-a-staged-migration"></a>Stap 1: een gefaseerde migratie voorbereiden

Voordat u postvakken migreert naar Microsoft 365 met behulp van een gefaseerde migratie, moet u een paar wijzigingen aanbrengen in uw Exchange-omgeving.
  
 **Outlook Anywhere op uw on-premises Exchange Server configureren** De e-mailmigratieservice maakt gebruik van Outlook Anywhere (ook wel RPC via HTTP genoemd) om verbinding te maken met uw on-premises Exchange Server. Voor informatie over het instellen van Outlook voor Exchange Server 2007 en Exchange 2003 raadpleegt u het volgende:
  
- [Exchange 2007: Outlook Anywhere inschakelen](https://go.microsoft.com/fwlink/?LinkID=167210)
    
- [Outlook Anywhere configureren met Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
> [!IMPORTANT]
> U moet met uw Outlook Anywhere-configuratie een certificaat gebruiken dat is uitgegeven door een vertrouwde certificeringsinstantie (CA). Outlook Anywhere kan niet worden geconfigureerd met een zelfondertekend certificaat. Zie [SSL configureren voor Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875) voor meer informatie. 
  
 **Optioneel: Controleren of u met Outlook Anywhere verbinding kunt maken met uw Exchange-organisatie** Probeer een van de volgende methoden om uw verbindingsinstellingen te controleren.
  
- Gebruik Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw lokale Exchange-postvak.
    
- Gebruik [Microsoft Remote Connectivity Analyzer](https://https://testconnectivity.microsoft.com/) om uw verbindingsinstellingen te testen. Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.
    
- Voer de volgende opdrachten uit in Exchange Online PowerShell:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Machtigingen instellen** Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel migratie beheerder genoemd), moet de juiste machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365. Dit gebruikersaccount wordt gebruikt wanneer u verbinding maakt met uw e-mailsysteem door een migratie-eindpunt te maken later in deze procedure ([stap 3: een migratie-eindpunt maken](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ).
  
De beheerder moet een van de volgende machtigingensets hebben om de postvakken te migreren:
  
- Lid zijn van de groep **Domain Admins** in Active Directory in de on-premises organisatie.
    
    of
    
- De machtigingen voor **machtiging fullaccess** worden toegewezen voor elk on-premises postvak en de **machtiging Write Property** -machtiging om de eigenschap **TargetAddress** te wijzigen voor de on-premises gebruikersaccounts.
    
    of
    
- U krijgt de machtiging **receive as** toegewezen voor de on-premises postvakdatabase waarin postvakken van gebruikers worden opgeslagen en de **machtiging Write Property** -machtiging voor het wijzigen van de eigenschap **TargetAddress** voor de on-premises gebruikersaccounts.
    
Zie [machtigingen toewijzen om postvakken te migreren naar Microsoft 365](https://go.microsoft.com/fwlink/?LinkId=521656)voor meer informatie over het instellen van deze machtigingen.
  
 **Unified Messaging (UM) uitschakelen** Als UM is ingeschakeld voor de on-premises postvakken die u wilt migreren, schakelt u UM voor de migratie uit. Schakel UM voor de postvakken in wanneer de migratie is voltooid. Zie[Unified Messaging uitschakelen](https://go.microsoft.com/fwlink/?LinkId=521891)voor instructies.
  
 **Gebruik adreslijstsynchronisatie om nieuwe gebruikers te maken in Microsoft 365.** U gebruikt adreslijstsynchronisatie om alle on-premises gebruikers in uw Microsoft 365-organisatie te maken.
  
U moet de gebruikers een licentie verlenen nadat ze zijn gemaakt. Nadat de gebruikers zijn gemaakt, hebt u 30 dagen om licenties toe te voegen. Voor de stappen voor het toevoegen van licenties raadpleegt u [stap 8: post-migratietaken voltooien](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 U kunt het synchronisatie hulpmiddel voor Microsoft Azure Active Directory (Azure AD) of de Microsoft Azure AD-synchronisatie Services gebruiken om uw on-premises gebruikers te synchroniseren en te maken in Microsoft 365. Wanneer postvakken zijn gemigreerd naar Microsoft 365, beheert u gebruikersaccounts in uw on-premises organisatie en ze worden gesynchroniseerd met uw Microsoft 365-organisatie. Zie voor meer informatie[Directory-integratie](https://go.microsoft.com/fwlink/?LinkId=521788) .
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Stap 2: een CSV-bestand maken voor een gefaseerde migratie batch

Nadat u de gebruikers hebt geïdentificeerd van wie on-premises postvakken u wilt migreren naar Microsoft 365, gebruikt u een bestand met door komma's gescheiden waarden (CSV) om een migratie batch te maken. Elke rij in het CSV-bestand, dat door Microsoft 365 wordt gebruikt om de migratie uit te voeren, bevat informatie over een on-premises postvak. 
  
> [!NOTE]
> Er geldt geen limiet voor het aantal postvakken dat u kunt migreren naar Microsoft 365 met een gefaseerde migratie. Het CSV-bestand voor een migratiebatch kan maximaal 2000 rijen bevatten. Als u meer dan 2000 postvakken wilt migreren, moet u extra CSV-bestanden maken en elk bestand gebruiken om een nieuwe migratiebatch te maken. 
  
 **Ondersteunde kenmerken**
  
Het CSV-bestand voor een gefaseerde migratie ondersteunt de volgende drie kenmerken. Elke rij in het CSV-bestand komt overeen met een postvak en moet een waarde bevatten voor elk van deze kenmerken.
  
|**Kenmerk**|**Omschrijving**|**Vereist?**|
|:-----|:-----|:-----|
|Email  <br/> |Bevat het primaire SMTP-e-mailadres, bijvoorbeeld pilarp@contoso.com, voor on-premises postvakken.  <br/> Gebruik het primaire SMTP-adres voor on-premises postvakken en geen gebruikers-Id's van Microsoft 365. Als het on-premises domein bijvoorbeeld de naam contoso.com is, maar het Microsoft 365-e-mail domein met de naam service.contoso.com is, gebruikt u de domeinnaam contoso.com voor e-mailadressen in het CSV-bestand.  <br/> |Vereist  <br/> |
|Password  <br/> |Het wachtwoord dat moet worden ingesteld voor het nieuwe postvak van Microsoft 365. Eventuele wachtwoordbeperkingen die gelden voor uw Microsoft 365-organisatie gelden ook voor de wachtwoorden die zijn opgenomen in het CSV-bestand.  <br/> |Optioneel  <br/> |
|ForceChangePassword gebruiken  <br/> |Hiermee wordt opgegeven of een gebruiker het wachtwoord moet wijzigen voor de eerste keer dat hij of zij zich aanmeldt met het nieuwe Microsoft 365-postvak. Gebruik **True** of **False** voor de waarde van deze parameter. <br/> > [!NOTE]> als u een oplossing voor eenmalige aanmelding (SSO) hebt geïmplementeerd door Active Directory Federation Services (AD FS) of hoger te implementeren in uw on-premises organisatie, moet u **False** gebruiken voor de waarde van het kenmerk **ForceChangePassword gebruiken** .          |Optioneel  <br/> |
   
 **CSV-bestandsindeling**
  
Hier volgt een voorbeeld van de indeling van het CSV-bestand. In dit voorbeeld worden twee on-premises postvakken gemigreerd naar Microsoft 365.
  
De eerste rij oftewel veldnamenrij van het CSV-bestand bevat de namen van de kenmerken, oftewel velden die in de volgende rijen worden opgegeven. De namen van kenmerken worden gescheiden door komma's.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Elke rij onder de veldnamenrij staat voor één gebruiker en bevat de informatie die wordt gebruikt om het postvak van de gebruiker te migreren. De kenmerkwaarden in elke rij moeten in dezelfde volgorde staan als de kenmerknamen in de veldnamenrij. 
  
Gebruik een willekeurige teksteditor of een toepassing als Excel om het CSV-bestand te maken. Sla het bestand op als een CSV- of TXT-bestand.
  
> [!NOTE]
> Als het CSV-bestand niet-ASCII-tekens of speciale tekens bevat, moet u het CSV-bestand opslaan met UTF-8 of andere Unicode-codering. Afhankelijk van de toepassing, kunt u het CSV-bestand met UTF-8-of andere Unicode-codering eenvoudiger maken wanneer de systeemtaal van de computer overeenkomt met de taal die wordt gebruikt in het CSV-bestand. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Stap 3: een migratie-eindpunt maken
<a name="BK_Endpoint"> </a>

Voor het migreren van e-mail is Microsoft 365 nodig om verbinding te maken en te communiceren met het bron-e-mailsysteem. Hiervoor maakt Microsoft 365 gebruik van een migratie-eindpunt. Voor het maken van een migratie-eindpunt van Outlook met behulp van PowerShell, moet u eerst [verbinding maken met Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Zie [cmdlets voor verplaatsen en migreren](https://go.microsoft.com/fwlink/p/?LinkId=534750)voor een volledige lijst met migratie opdrachten.
  
Voer de volgende opdrachten uit om een Outlook Anywhere-migratie-eindpunt te maken met de naam ' StagedEndpoint ' in Exchange Online PowerShell:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Zie[New-MigrationEndpoint](https://go.microsoft.com/fwlink/p/?LinkId=536437)voor meer informatie over de **New-MigrationEndpoint** -cmdlet.
  
> [!NOTE]
> Met de cmdlet **New-MigrationEndpoint** kunt u een database opgeven voor de service die u wilt gebruiken met de optie **-TargetDatabase** . Anders wordt een database willekeurig toegewezen op de site van de AD FS-2,0 (Active Directory Federation Services) waar het postvak van het beheer zich bevindt.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

In Exchange Online PowerShell voert u de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt van StagedEndpoint:
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Stap 4: een migratie batch voor stage maken en starten
<a name="BK_Endpoint"> </a>

U kunt de **New-MigrationBatch-** cmdlet in Exchange Online PowerShell gebruiken om een migratie batch voor een cutover-migratie te maken. U kunt een migratie batch maken en deze automatisch starten door de parameter van automatisch _starten_ op te nemen. U kunt de migratie batch ook maken en deze vervolgens handmatig opnieuw starten met behulp van de cmdlet **Start-MigrationBatch** . In het volgende voorbeeld wordt een migratie batch met de naam StagedBatch1 en gebruikt het migratie-eindpunt dat in de vorige stap is gemaakt.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

In dit voorbeeld wordt ook een migratie batch met de naam ' StagedBatch1 ' gemaakt en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt. Aangezien de parameter  _autostart_ niet is opgenomen, moet de migratie batch handmatig worden gestart op het migratie dashboard of met behulp van de cmdlet **Start-MigrationBatch** . Zoals eerder vermeld, kan slechts één cutover-migratie batch bestaan.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de StagedBatch1:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Zie[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)voor meer informatie over de cmdlet **Get-MigrationBatch** .
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Stap 5: on-premises postvakken converteren naar gebruikers met e-mail
<a name="BK_Endpoint"> </a>

Wanneer u een reeks postvakken hebt gemigreerd, moeten gebruikers op de een of andere manier toegang krijgen tot hun e-mail. Een gebruiker wiens postvak is gemigreerd, heeft nu zowel een on-premises postvak als een postvak in Microsoft 365. Gebruikers die een postvak hebben in Microsoft 365, ontvangen geen nieuwe e-mail in hun on-premises postvak. 
  
Aangezien u niet met uw migraties bent gewerkt, bent u nog niet klaar om alle gebruikers naar Microsoft 365 voor hun e-mail te leiden. Wat moet u doen voor personen die beide mogelijkheden hebben? U kunt de on-premises postvakken die u al hebt gemigreerd wijzigen in gebruikers met e-mail. Wanneer u van een postvak overschakelt naar een gebruiker met e-mail, kunt u de gebruiker naar Microsoft 365 voor hun e-mail sturen in plaats van naar het on-premises postvak van de gebruiker te schakelen. 
  
Een andere belangrijke reden om on-premises postvakken te converteren naar gebruikers met e-mail is door de proxyadressen van de Microsoft 365-postvakken te kopiëren en de e-mail gebruikers te kopiëren. Op die manier kunt u gebruikers in de cloud vanuit uw on-premises organisatie beheren met behulp van Active Directory. Ook als u uw on-premises Exchange Server-organisatie wilt deactiveren nadat alle postvakken zijn gemigreerd naar Microsoft 365, blijven de proxyadressen die u hebt gekopieerd naar de gebruikers voor e-mail in uw on-premises Active Directory staan.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Stap 6: een gefaseerde migratie batch verwijderen
<a name="BK_Endpoint"> </a>

 Nadat alle postvakken in een migratie batch zijn gemigreerd en u de on-premises postvakken in de batch naar gebruikers met e-mail hebt geconverteerd, bent u klaar om een gefaseerde migratie batch te verwijderen. Controleer of e-mail wordt doorgestuurd naar de Microsoft 365-postvakken in de migratie batch. Wanneer u een gefaseerde migratie batch verwijdert, worden alle records met betrekking tot de migratie batch gewist met de Migratieservice en wordt de migratie batch verwijderd.
  
Voer de volgende opdracht uit om de StagedBatch1-migratie batch in Exchange Online PowerShell te verwijderen.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Zie[Remove-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536481)voor meer informatie over de **Remove-MigrationBatch** -cmdlet.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de IMAPBatch1:
  
```powershell
Get-MigrationBatch StagedBatch1
```

Met de opdracht wordt de migratie batch met de status **verwijderd**geretourneerd, of wordt een foutmelding weergegeven met de mededeling dat de batch niet kan worden gevonden en gecontroleerd of de batch is verwijderd.
  
Zie[Get-MigrationBatch](https://go.microsoft.com/fwlink/p/?LinkId=536441)voor meer informatie over de cmdlet **Get-MigrationBatch** .
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Step7: licenties toewijzen aan Microsoft 365-gebruikers
<a name="BK_Endpoint"> </a>

Activeer Microsoft 365-gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen. Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen. Zie [licenties toewijzen of intrekken](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)als u een licentie wilt toewijzen in het microsoft 365-Beheercentrum.
  
### <a name="step-8-complete-post-migration-tasks"></a>Stap 8: post-migratietaken voltooien
<a name="BK_Postmigration"> </a>

- **Maak een automatische detectie-DNS-record zodat gebruikers gemakkelijk toegang hebben tot hun postvakken.** Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een automatische detectie-DNS-record voor uw Microsoft 365-organisatie configureren zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients. Deze nieuwe DNS-record voor automatisch opsporen moet de naam van de naamruimte gebruiken die u gebruikt voor uw Microsoft 365-organisatie. Als bijvoorbeeld de naamruimte in de Cloud cloud.contoso.com is, is de DNS-record voor Autodiscover die u moet maken autodiscover.cloud.contoso.com.
    
    Microsoft 365 gebruikt een CNAME-record om de Autodiscover-service voor Outlook en mobiele clients te implementeren. De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:
    
  - **Alias:** autodiscover
    
  - **Doel:** autodiscover.outlook.com
    
    Zie [DNS-records toevoegen om uw domein te verbinden](https://go.microsoft.com/fwlink/p/?LinkId=535028)voor meer informatie.
    
- **On-premises Exchange-servers buiten bedrijf stellen.** Nadat u hebt gecontroleerd of alle e-mailberichten rechtstreeks worden gerouteerd naar de Microsoft 365-postvakken en u uw on-premises e-mail organisatie niet langer hoeft te onderhouden of niet meer wilt doen met het implementeren van een SSO-oplossing, kunt u Exchange van uw servers verwijderen en uw on-premises Exchange-organisatie verwijderen.
    
    Zie de volgende onderwerpen voor meer informatie:
    
  - [Exchange 2010 wijzigen of verwijderen](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Een Exchange 2007-organisatie verwijderen](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Exchange Server 2003 verwijderen](https://go.microsoft.com/fwlink/?LinkID=56561)
    

