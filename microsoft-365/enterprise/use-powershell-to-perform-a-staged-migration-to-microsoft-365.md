---
title: Een gefaseerde migratie naar Microsoft 365 uitvoeren met PowerShell
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
description: Meer informatie over het gebruik van PowerShell om inhoud te verplaatsen van een bron-e-mailsysteem in de tijd met behulp van een gefaseerd migratie naar Microsoft 365.
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924790"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Een gefaseerde migratie naar Microsoft 365 uitvoeren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt de inhoud van gebruikerspostvakken migreren van een bron-e-mailsysteem naar Microsoft 365 met een gefaseerd migratie.
  
In dit artikel vindt u een aantal taken voor een gefaseerd e-mailmigratie met Exchange Online PowerShell. Het onderwerp Wat [u moet weten over](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)een gefaseerd e-mailmigratie, geeft u een overzicht van het migratieproces. Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.
  
> [!NOTE]
> U kunt het beheercentrum Exchange ook gebruiken om gefaseerd migratie uit te voeren. Zie [Een gefaseerd migratie van e-mail](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)naar Microsoft 365. 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd om deze taak te voltooien: 2-5 minuten om een migratiebatch te maken. Nadat de migratiebatch is gestart, is de duur van de migratie afhankelijk van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie Migratieprestaties voor informatie over andere factoren die van invloed zijn op hoe lang het duurt om postvakken naar Microsoft 365 [te migreren.](/Exchange/mailbox-migration/office-365-migration-best-practices)
  
U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Zie de vermelding 'Migratie' in het onderwerp [Geadresseerdenmachtigingen](/exchange/recipients-permissions-exchange-2013-help) als u wilt zien welke machtigingen u nodig hebt.
  
Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell sessie. Zie [Verbinding maken om Exchange Online externe PowerShell te gebruiken voor](/powershell/exchange/connect-to-exchange-online-powershell) instructies.
  
Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)
  
## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-a-staged-migration"></a>Stap 1: Voorbereiden op een gefaseerd migratie

Voordat u postvakken migreert naar Microsoft 365 met behulp van een gefaseerd migratie, moet u enkele wijzigingen aanbrengen in uw Exchange omgeving.
  
 **Outlook Anywhere op uw on-premises Exchange Server configureren** De e-mailmigratieservice maakt gebruik van Outlook Anywhere (ook wel RPC via HTTP genoemd) om verbinding te maken met uw on-premises Exchange Server. Zie de volgende informatie over het instellen Outlook Anywhere voor Exchange Server 2007 en Exchange 2003:
  
- [Exchange 2007: Outlook Anywhere inschakelen](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [Outlook Anywhere configureren met Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> U moet met uw Outlook Anywhere-configuratie een certificaat gebruiken dat is uitgegeven door een vertrouwde certificeringsinstantie (CA). Outlook Anywhere kan niet worden geconfigureerd met een zelfondertekend certificaat. Zie [SSL configureren voor Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)) voor meer informatie. 
  
 **Optioneel: Controleren of u met Outlook Anywhere verbinding kunt maken met uw Exchange-organisatie** Probeer een van de volgende methoden om uw verbindingsinstellingen te controleren.
  
- Gebruik Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw lokale Exchange-postvak.
    
- Gebruik de [Microsoft Remote Connectivity Analyzer om](https://https://testconnectivity.microsoft.com/) uw verbindingsinstellingen te testen. Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.
    
- Voer de volgende opdrachten uit in Exchange Online PowerShell:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Machtigingen instellen** Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel de migratiebeheerder genoemd) moet de benodigde machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365. Dit gebruikersaccount wordt gebruikt wanneer u verbinding maakt met uw e-mailsysteem door later in deze procedure een migratie-eindpunt te maken ([stap 3: Een migratie-eindpunt maken).](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint)
  
De beheerder moet een van de volgende machtigingensets hebben om de postvakken te migreren:
  
- Lid zijn van de **groep Domeinbeheerders** in Active Directory in de on-premises organisatie.
    
    of
    
- U krijgt de **machtiging FullAccess** toegewezen voor elk on-premises postvak en de machtiging **WriteProperty** om de eigenschap **TargetAddress** te wijzigen in de on-premises gebruikersaccounts.
    
    of
    
- U krijgt de machtiging **Ontvangen als** toegewezen voor de on-premises postvakdatabase waarin gebruikerspostvakken en de machtiging **WriteProperty** worden opgeslagen om de eigenschap **TargetAddress** te wijzigen in de on-premises gebruikersaccounts.
    
Zie Machtigingen toewijzen voor het migreren van postvakken naar Microsoft 365 voor instructies over het instellen [van deze machtigingen.](/Exchange/mailbox-migration/assign-permissions-for-migration)
  
 **Unified Messaging (UM) uitschakelen** Als UM is ingeschakeld voor de on-premises postvakken die u wilt migreren, schakelt u UM voor de migratie uit. Schakel UM voor de postvakken in wanneer de migratie is voltooid. Zie Unified Messaging uitschakelen voor de stappen voor het instellen[van de stappen.](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80))
  
 **Gebruik adreslijstsynchronisatie om nieuwe gebruikers te maken in Microsoft 365.** U gebruikt adreslijstsynchronisatie om alle on-premises gebruikers in uw Microsoft 365 maken.
  
U moet de gebruikers een licentie geven nadat ze zijn gemaakt. Nadat de gebruikers zijn gemaakt, hebt u 30 dagen om licenties toe te voegen. Zie Stap [8: Taken na de migratie voltooien](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration)voor stappen om licenties toe te voegen.
  
 U kunt het synchronisatieprogramma Microsoft Azure Active Directory (Azure AD) of de Microsoft Azure AD Sync Services gebruiken om uw on-premises gebruikers te synchroniseren en te maken in Microsoft 365. Nadat postvakken zijn gemigreerd naar Microsoft 365, beheert u gebruikersaccounts in uw on-premises organisatie en worden ze gesynchroniseerd met uw Microsoft 365 organisatie. Zie Adreslijstintegratie voor[meer informatie.](/previous-versions/azure/azure-services/jj573653(v=azure.100))
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Stap 2: Een CSV-bestand maken voor een gefaseerd migratiebatch

Nadat u de gebruikers hebt gevonden van wie u on-premises postvakken wilt migreren naar Microsoft 365, gebruikt u een CSV-bestand (door komma's gescheiden waarde) om een migratiebatch te maken. Elke rij in het CSV-bestand, die door Microsoft 365 wordt gebruikt om de migratie uit te voeren, bevat informatie over een on-premises postvak. 
  
> [!NOTE]
> Er is geen limiet voor het aantal postvakken dat u kunt migreren naar Microsoft 365 gefaseerd migreren. Het CSV-bestand voor een migratiebatch kan maximaal 2000 rijen bevatten. Als u meer dan 2000 postvakken wilt migreren, moet u extra CSV-bestanden maken en elk bestand gebruiken om een nieuwe migratiebatch te maken. 
  
 **Ondersteunde kenmerken**
  
Het CSV-bestand voor een gefaseerde migratie ondersteunt de volgende drie kenmerken. Elke rij in het CSV-bestand komt overeen met een postvak en moet een waarde bevatten voor elk van deze kenmerken.
  
|**Kenmerk**|**Omschrijving**|**Vereist?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Bevat het primaire SMTP-e-mailadres, bijvoorbeeld pilarp@contoso.com, voor on-premises postvakken.  <br/> Gebruik het primaire SMTP-adres voor on-premises postvakken en niet voor gebruikers-ID's uit de Microsoft 365. Als het on-premises domein bijvoorbeeld de naam contoso.com heeft, maar het Microsoft 365-e-maildomein de naam service.contoso.com heeft, gebruikt u de contoso.com-domeinnaam voor e-mailadressen in het CSV-bestand.  <br/> |Vereist  <br/> |
|Password  <br/> |Het wachtwoord dat moet worden ingesteld voor het nieuwe Microsoft 365 postvak. Alle wachtwoordbeperkingen die worden toegepast op uw Microsoft 365 zijn ook van toepassing op de wachtwoorden in het CSV-bestand.  <br/> |Optioneel  <br/> |
|ForceChangePassword  <br/> |Hiermee geeft u aan of een gebruiker het wachtwoord moet wijzigen wanneer hij of zij zich de eerste keer bij het nieuwe postvak Microsoft 365 aanmelden. Gebruik **True** of **False** voor de waarde van deze parameter. <br/> > [!NOTE]> Als u één aanmeldingsoplossing (SSO) hebt geïmplementeerd door Active Directory Federation Services (AD FS) of hoger te  implementeren in uw on-premises organisatie, moet u False gebruiken voor de waarde van het **ForceChangePassword-kenmerk.**          |Optioneel  <br/> |
   
 **CSV-bestandsindeling**
  
Hier volgt een voorbeeld van de indeling van het CSV-bestand. In dit voorbeeld worden drie on-premises postvakken gemigreerd naar Microsoft 365.
  
De eerste rij oftewel veldnamenrij van het CSV-bestand bevat de namen van de kenmerken, oftewel velden die in de volgende rijen worden opgegeven. De namen van kenmerken worden gescheiden door komma's.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Elke rij onder de veldnamenrij staat voor één gebruiker en bevat de informatie die wordt gebruikt om het postvak van de gebruiker te migreren. De kenmerkwaarden in elke rij moeten in dezelfde volgorde staan als de kenmerknamen in de veldnamenrij. 
  
Gebruik een teksteditor of een toepassing zoals Excel om het CSV-bestand te maken. Sla het bestand op als een CSV- of TXT-bestand.
  
> [!NOTE]
> Als het CSV-bestand niet-ASCII-tekens of speciale tekens bevat, moet u het CSV-bestand opslaan met UTF-8 of andere Unicode-codering. Afhankelijk van de toepassing kan het opslaan van het CSV-bestand met UTF-8 of andere Unicode-codering eenvoudiger zijn wanneer de systeem locale van de computer overeenkomt met de taal die in het CSV-bestand wordt gebruikt. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Stap 3: Een migratie-eindpunt maken
<a name="BK_Endpoint"> </a>

Als u e-mail wilt migreren, Microsoft 365 verbinding maken en communiceren met het bron-e-mailsysteem. Hiervoor wordt Microsoft 365 een migratie-eindpunt gebruikt. Als u een Outlook anywhere-migratie-eindpunt wilt maken met Behulp van PowerShell, maakt u voor gefaseerd migreren eerst [verbinding met Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell) 
  
Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)
  
Voer de volgende opdrachten Outlook als u een Outlook-migratie-eindpunt met de naam 'StagedEndpoint' wilt maken in Exchange Online PowerShell:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Zie [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint)voor meer informatie over de **cmdlet New-MigrationEndpoint** .
  
> [!NOTE]
> De **cmdlet New-MigrationEndpoint** kan worden gebruikt om een database op te geven die de service moet gebruiken met de optie **-TargetDatabase.** Anders wordt een database willekeurig toegewezen vanuit de AD FS 2.0-site (Active Directory Federation Services) waar het managementpostvak zich bevindt.
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer Exchange Online PowerShell de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt 'StagedEndpoint':
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Stap 4: Een fasemigratiebatch maken en starten
<a name="BK_Endpoint"> </a>

U kunt de **cmdlet New-MigrationBatch** in Exchange Online PowerShell gebruiken om een migratiebatch te maken voor een cutover-migratie. U kunt een migratiebatch maken en deze automatisch starten door de _parameter AutoStart op te_ nemen. U kunt ook de migratiebatch maken en daarna handmatig starten met de **cmdlet Start-MigrationBatch.** In dit voorbeeld wordt een migratiebatch met de naam 'GefaseerdBatch1' gemaakt en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

In dit voorbeeld wordt ook een migratiebatch gemaakt met de naam 'GefaseerdBatch1' en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt. Omdat de _parameter AutoStart_ niet is opgenomen, moet de migratiebatch handmatig worden gestart op het migratiedashboard of met de cmdlet **Start-MigrationBatch.** Zoals eerder vermeld, kan er slechts één cutover-migratiebatch tegelijk bestaan.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de 'StagedBatch1':
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

U kunt ook controleren of de batch is gestart door de volgende opdracht uit te voeren:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Zie [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)voor meer informatie over de cmdlet **Get-MigrationBatch.**
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Stap 5: On-premises postvakken converteren naar gebruikers met e-mail
<a name="BK_Endpoint"> </a>

Wanneer u een reeks postvakken hebt gemigreerd, moeten gebruikers op de een of andere manier toegang krijgen tot hun e-mail. Een gebruiker van wie het postvak is gemigreerd, heeft nu zowel een on-premises postvak als een postvak in Microsoft 365. Gebruikers met een postvak in Microsoft 365 ontvangen geen nieuwe e-mail meer in hun on-premises postvak. 
  
Omdat u nog niet klaar bent met uw migraties, bent u nog niet klaar om alle gebruikers door te sturen naar Microsoft 365 e-mail. Wat moet u doen voor personen die beide mogelijkheden hebben? U kunt de on-premises postvakken die u al hebt gemigreerd wijzigen in gebruikers met e-mail. Wanneer u van een postvak verandert in een gebruiker met e-mail, kunt u de gebruiker naar Microsoft 365 e-mail sturen in plaats van naar het on-premises postvak te gaan. 
  
Een andere belangrijke reden om on-premises postvakken te converteren naar gebruikers met e-mail is het behouden van proxyadressen uit de Microsoft 365-postvakken door proxyadressen te kopiëren naar de gebruikers met e-mail. Op die manier kunt u gebruikers in de cloud vanuit uw on-premises organisatie beheren met behulp van Active Directory. Als u besluit uw on-premises Exchange Server-organisatie buiten bedrijf te stellen nadat alle postvakken naar Microsoft 365 zijn gemigreerd, blijven de proxyadressen die u hebt gekopieerd naar de gebruikers met e-mail in uw on-premises Active Directory.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Stap 6: Een gefaseerd migratiebatch verwijderen
<a name="BK_Endpoint"> </a>

 Nadat alle postvakken in een migratiebatch zijn gemigreerd en u de on-premises postvakken in de batch hebt geconverteerd naar gebruikers met e-mail, kunt u een gefaseerd migratiebatch verwijderen. Controleer of e-mail wordt doorgestuurd naar de Microsoft 365 postvakken in de migratiebatch. Wanneer u een gefaseerd migratiebatch verwijdert, worden alle records met betrekking tot de migratiebatch door de migratieservice opschoond en wordt de migratiebatch verwijderd.
  
Als u de migratiebatch1-migratiebatch 'Gefaseerd' wilt verwijderen in Exchange Online PowerShell, voer u de volgende opdracht uit.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Zie [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch)voor meer informatie over de cmdlet **Remove-MigrationBatch** .
  
#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer de volgende opdracht uit in Exchange Online PowerShell om informatie weer te geven over de 'IMAPBatch1':
  
```powershell
Get-MigrationBatch StagedBatch1
```

De opdracht retourneert de migratiebatch met de status **Verwijderen,** of de opdracht retourneert een fout waarin wordt aangegeven dat de migratiebatch niet kan worden gevonden en dat de batch is verwijderd.
  
Zie [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)voor meer informatie over de cmdlet **Get-MigrationBatch.**
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Stap7: Licenties toewijzen aan Microsoft 365 gebruikers
<a name="BK_Endpoint"> </a>

Activeer Microsoft 365 gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen. Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen. Als u een licentie wilt toewijzen in het Microsoft 365 beheercentrum, zie Licenties toewijzen of [niet toewijzen.](../admin/manage/assign-licenses-to-users.md)
  
### <a name="step-8-complete-post-migration-tasks"></a>Stap 8: Taken na de migratie voltooien
<a name="BK_Postmigration"> </a>

- **Maak een AutoDiscover DNS-record, zodat gebruikers gemakkelijk bij hun postvakken kunnen komen.** Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een AUTODISCOVER DNS-record configureren voor uw Microsoft 365-organisatie, zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients. Deze nieuwe AUTODISCOVER DNS-record moet dezelfde naamruimte gebruiken die u gebruikt voor uw Microsoft 365 organisatie. Als de naamruimte in de cloud bijvoorbeeld cloud.contoso.com, wordt de DNS-record voor automatisch zoeken die u moet maken, autodiscover.cloud.contoso.com.
    
    Microsoft 365 CNAME-record gebruikt om de Autodiscover-service te implementeren voor Outlook en mobiele clients. De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:
    
  - **Alias:** autodiscover
    
  - **Doel:** autodiscover.outlook.com
    
    Zie DNS-records toevoegen [om uw domein te verbinden voor meer informatie.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)
    
- **On-premises Exchange-servers buiten bedrijf stellen.** Nadat u hebt geverifieerd dat alle e-mail rechtstreeks naar de Microsoft 365-postvakken wordt gerouteerd en u uw on-premises e-mailorganisatie niet meer hoeft te onderhouden of niet van plan bent een SSO-oplossing te implementeren, kunt u Exchange verwijderen van uw servers en uw on-premises Exchange-organisatie verwijderen.
    
    Zie de volgende onderwerpen voor meer informatie:
    
  - [Exchange 2010 wijzigen of verwijderen](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [Een Exchange 2007-organisatie verwijderen](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [Exchange Server 2003 verwijderen](/previous-versions/tn-archive/bb125110(v=exchg.65))
