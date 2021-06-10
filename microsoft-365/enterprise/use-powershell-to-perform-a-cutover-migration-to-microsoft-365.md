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
description: Lees hoe u PowerShell gebruikt om de inhoud van een bron-e-mailsysteem in één keer te verplaatsen door een cutover-migratie uit te voeren naar Microsoft 365.
ms.openlocfilehash: 6e59ac4d590208e0faed22e94cabe05601b17f18
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581056"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Een cutover-migratie naar Microsoft 365 uitvoeren met PowerShell

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt de inhoud van gebruikerspostvakken migreren van een bron-e-mailsysteem om Microsoft 365 allemaal tegelijk te migreren met behulp van een cutover-migratie. In dit artikel vindt u een overzicht van de taken voor een cutover-migratie per e-mail Exchange Online PowerShell.

Door het onderwerp te bekijken, [Wat u](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)moet weten over een cutover-e-mailmigratie naar Microsoft 365, kunt u een overzicht krijgen van het migratieproces. Wanneer u vertrouwd bent met de inhoud van dit artikel, gebruikt u dit om postvakken van het ene e-mailsysteem naar het andere te migreren.

> [!NOTE]
> U kunt het beheercentrum Exchange ook gebruiken om een cutover-migratie uit te voeren. Zie [Een cutover-migratie van e-mail](/Exchange/mailbox-migration/cutover-migration-to-office-365)uitvoeren naar Microsoft 365.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Wat moet u weten voordat u begint?

Geschatte tijd om deze taak te voltooien: 2-5 minuten om een migratiebatch te maken. Nadat de migratiebatch is gestart, is de duur van de migratie afhankelijk van het aantal postvakken in de batch, de grootte van elk postvak en de beschikbare netwerkcapaciteit. Zie Migratieprestaties voor informatie over andere factoren die van invloed zijn op hoe lang het duurt om postvakken naar Microsoft 365 [te migreren.](/Exchange/mailbox-migration/office-365-migration-best-practices)

U moet beschikken over bepaalde machtigingen om deze procedure of procedures te kunnen uitvoeren. Als u wilt zien welke machtigingen u nodig hebt, ziet u de vermelding 'Migratie' in een tabel in het onderwerp [Machtigingen geadresseerden.](/exchange/recipients-permissions-exchange-2013-help)

Als u de Exchange Online PowerShell-cmdlets wilt gebruiken, moet u zich aanmelden en de cmdlets importeren in uw lokale Windows PowerShell sessie. Zie [Verbinding maken om Exchange Online externe PowerShell te gebruiken voor](/powershell/exchange/connect-to-exchange-online-powershell) instructies.

Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)

## <a name="migration-steps"></a>Migratiestappen

### <a name="step-1-prepare-for-a-cutover-migration"></a>Stap 1: Voorbereiden op een cutover-migratie
<a name="BK_Step1"> </a>

- **Voeg uw on-premises Exchange toe als een geaccepteerd domein van uw Microsoft 365 organisatie.** De migratieservice gebruikt het SMTP-adres van uw on-premises postvakken om de gebruikers-id en het e-mailadres van Microsoft Online Services te maken voor de nieuwe Microsoft 365 postvakken. De migratie mislukt als uw Exchange domein geen geaccepteerd domein of het primaire domein van uw Microsoft 365 is. Zie Uw domein verifiëren [voor meer informatie.](../admin/setup/add-domain.md)

- **Configureer Outlook Anywhere op uw on-premises Exchange server.** De e-mailmigratieservice gebruikt RPC via HTTP of Outlook Anywhere om verbinding te maken met uw on-premises Exchange server. Raadpleeg de volgende onderwerpen voor meer informatie over het instellen van Outlook Anywhere voor Exchange Server 2010, Exchange 2007 en Exchange 2003:

  - [Exchange 2010: Outlook Anywhere inschakelen](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Outlook Anywhere inschakelen](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: Implementatiescenario's voor RPC via HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Overal configureren Outlook met Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Uw Outlook Anywhere-configuratie moet zijn geconfigureerd met een certificaat dat is uitgegeven door een vertrouwde certificeringsinstantie (CA). Het kan niet worden geconfigureerd met een zelf ondertekend certificaat. Zie SSL configureren [voor Outlook anywhere voor meer informatie.](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80))

- **Controleer of u verbinding kunt maken met uw Exchange organisatie met Outlook Anywhere.** Probeer een van deze methoden om uw verbindingsinstellingen te testen:

  - Gebruik Microsoft Outlook van buiten uw bedrijfsnetwerk om verbinding te maken met uw on-premises Exchange postvak.

  - Gebruik de Microsoft [Exchange Remote Connectivity Analyzer](https://www.testexchangeconnectivity.com/) om uw verbindingsinstellingen te testen. Gebruik de tests van Outlook Anywhere (RPC via HTTP) of Outlook Automatisch opsporen.

  - Voer de volgende opdrachten uit in Exchange Online PowerShell.

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Wijs een on-premises gebruikersaccount de benodigde machtigingen toe voor toegang tot postvakken in uw Exchange organisatie.** Het on-premises gebruikersaccount dat u gebruikt om verbinding te maken met uw on-premises Exchange-organisatie (ook wel de migratiebeheerder genoemd) moet de benodigde machtigingen hebben voor toegang tot de on-premises postvakken die u wilt migreren naar Microsoft 365. Dit gebruikersaccount wordt gebruikt om een migratie-eindpunt naar uw on-premises organisatie te maken.

    In de volgende lijst ziet u de beheerdersbevoegdheden die nodig zijn voor het migreren van postvakken met een cutover-migratie. Er zijn drie mogelijke opties.

  - De migratiebeheerder moet lid zijn van de groep **Domeinbeheerders** in Active Directory in de on-premises organisatie.

    Of

  - De migratiebeheerder moet voor elk on-premises postvak de machtiging **FullAccess** krijgen toegewezen.

    Of

  - Aan de migratiebeheerder moet de machtiging **Ontvangen als** zijn toegewezen voor de on-premises postvakdatabase waarin de postvakken van gebruikers zijn opgeslagen.

- **Unified Messaging uitschakelen.** Als de on-premises postvakken die u migreert, zijn ingeschakeld voor Unified Messaging (UM), moet u UM in de postvakken uitschakelen voordat u ze migreert. U kunt um vervolgens inschakelen op de postvakken nadat de migratie is voltooid.

- **Beveiligingsgroepen en gedelegeerden** De e-mailmigratieservice kan niet detecteren of on-premises Active Directory-groepen beveiligingsgroepen zijn of niet, dus kunnen gemigreerde groepen niet worden ingericht als beveiligingsgroepen in Microsoft 365. Als u beveiligingsgroepen wilt hebben in uw Microsoft 365 tenant, moet u eerst een lege beveiligingsgroep met e-mail inrichten in uw Microsoft 365 tenant voordat u de cutover-migratie start. Daarnaast worden met deze migratiemethode alleen postvakken, e-mailgebruikers, e-mailcontactpersonen en groepen die e-mail gebruiken, verplaatst. Als een ander Active Directory-object, zoals een gebruiker die niet naar Microsoft 365 is gemigreerd, als manager of gedelegeerde is toegewezen aan een object dat wordt gemigreerd, moeten ze uit het object worden verwijderd voordat u migreert.

### <a name="step-2-create-a-migration-endpoint"></a>Stap 2: Een migratie-eindpunt maken
<a name="BK_Step2"> </a>

Als u e-mail wilt migreren, Microsoft 365 verbinding maken en communiceren met het bron-e-mailsysteem. Hiervoor wordt Microsoft 365 een migratie-eindpunt gebruikt. Als u een Outlook anywhere-migratie-eindpunt voor cutover-migratie wilt maken, maakt u eerst [verbinding met Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

Zie Cmdlets verplaatsen en migreren voor een volledige lijst met [migratieopdrachten.](/powershell/exchange/)

Voer de volgende opdrachten uit in Exchange Online PowerShell:

```powershell
$Credentials = Get-Credential
```

In het voorbeeld wordt de [cmdlet Test-MigrationServerBeschikbaarheid](/powershell/module/exchange/test-migrationserveravailability) gebruikt om de verbindingsinstellingen voor de on-premises Exchange-server te verkrijgen en te testen. Vervolgens worden deze verbindingsinstellingen gebruikt om het migratie-eindpunt 'CutoverEndpoint' te maken.

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> De **cmdlet New-MigrationEndpoint** kan worden gebruikt om een database op te geven die de service moet gebruiken met de optie **-TargetDatabase.** Anders wordt een database willekeurig toegewezen vanuit de AD FS 2.0-site (Active Directory Federation Services) waar het managementpostvak zich bevindt.

#### <a name="verify-it-worked"></a>Controleren of het werkt

Voer Exchange Online PowerShell de volgende opdracht uit om informatie weer te geven over het migratie-eindpunt CutoverEndpoint:

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Stap 3: de cutover-migratiebatch maken
<a name="BK_Step3"> </a>

U kunt de **cmdlet New-MigrationBatch** in Exchange Online PowerShell gebruiken om een migratiebatch te maken voor een cutover-migratie. U kunt een migratiebatch maken en deze automatisch starten door de _parameter AutoStart op te_ nemen. U kunt ook de migratiebatch maken en daarna handmatig starten met de **cmdlet Start-MigrationBatch.** In dit voorbeeld wordt een migratiebatch gemaakt met de naam 'CutoverBatch' en wordt het migratie-eindpunt gebruikt dat is gemaakt in de vorige stap.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

In dit voorbeeld wordt ook een migratiebatch gemaakt met de naam 'CutoverBatch' en wordt het migratie-eindpunt gebruikt dat in de vorige stap is gemaakt. Omdat de _parameter AutoStart_ niet is opgenomen, moet de migratiebatch handmatig worden gestart op het migratiedashboard of met de cmdlet **Start-MigrationBatch.** Zoals eerder vermeld, kan er slechts één cutover-migratiebatch tegelijk bestaan.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Als u wilt controleren of u een migratiebatch voor een cutover-migratie hebt gemaakt, moet u de volgende opdracht uitvoeren in Exchange Online PowerShell om informatie weer te geven over de nieuwe migratiebatch:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Stap 4: de cutover-migratiebatch starten
<a name="BK_Step4"> </a>

Als u de migratiebatch wilt starten in Exchange Online PowerShell, voer u de volgende opdracht uit. Hiermee wordt een migratiebatch met de naam 'CutoverBatch' aan het maken.

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Controleren of het werkt

Als een migratiebatch is gestart, wordt de status op het migratiedashboard opgegeven als Synchroniseren. Voer de volgende opdracht uit om te controleren of u een migratiebatch hebt gestart Exchange Online PowerShell:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Stap 5: Uw e-mail door Microsoft 365
<a name="BK_Step5"> </a>

E-mailsystemen gebruiken een DNS-record, een zogenaamde MX-record, om te achterhalen waar e-mails moeten worden bezorgd. Tijdens het e-mailmigratieproces wijst de MX-record naar het bron-e-mailsysteem. Nu de e-mailmigratie naar Microsoft 365 is voltooid, is het tijd om uw MX-record op Microsoft 365. Dit helpt ervoor te zorgen dat e-mail wordt bezorgd in Microsoft 365 postvakken. Door de MX-record te verplaatsen, kunt u ook uw oude e-mailsysteem uitschakelen wanneer u klaar bent.

Veel DNS-providers hebben specifieke instructies voor het wijzigen van uw MX-record. Voor het geval uw DNS-provider niet is opgenomen of als u een idee wilt krijgen van de algemene richtlijnen, worden ook de [algemene instructies voor MX-records](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) verstrekt.

Het kan tot 72 uur duren voordat in de e-mailsystemen van uw klanten en partners de gewijzigde MX-record wordt herkend. Wacht ten minste 72 uur voordat u verdergaat met de volgende taak: [Stap 6: De cutover-migratiebatch verwijderen.](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6)

### <a name="step-6-delete-the-cutover-migration-batch"></a>Stap 6: de cutover-migratiebatch verwijderen
<a name="Bk_step6"> </a>

Nadat u de MX-record hebt gewijzigd en hebt gecontroleerd of alle e-mail wordt doorgestuurd naar Microsoft 365 postvakken, meldt u de gebruikers dat hun e-mail wordt Microsoft 365. Hierna kunt u de cutover-migratiebatch verwijderen. Controleer het volgende voordat u de migratiebatch verwijdert.

- Alle gebruikers gebruiken Microsoft 365 postvakken. Nadat de batch is verwijderd, wordt e-mail die naar postvakken op de on-premises Exchange Server verzonden, niet gekopieerd naar de bijbehorende Microsoft 365 postvakken.

- Microsoft 365 postvakken zijn ten minste eenmaal gesynchroniseerd nadat e-mail rechtstreeks naar deze postvakken werd verzonden. Als u dit wilt doen, moet u ervoor zorgen dat de waarde in het vak Laatst gesynchroniseerde tijd voor de migratiebatch recenter is dan toen e-mail rechtstreeks werd gerouteerd naar Microsoft 365 postvakken.

Als u de migratiebatch 'CutoverBatch' wilt verwijderen in Exchange Online PowerShell, gaat u als volgt te werk:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Sectie 7: Gebruikerslicenties toewijzen
<a name="BK_Step7"> </a>

 **Activeer Microsoft 365 gebruikersaccounts voor de gemigreerde accounts door licenties toe te wijzen.** Als u geen licentie toewijst, wordt het postvak uitgeschakeld wanneer de respijtperiode (30 dagen) is afgelopen. Als u een licentie wilt toewijzen in het Microsoft 365 beheercentrum, zie Licenties toewijzen of [niet toewijzen.](../admin/manage/assign-licenses-to-users.md)

### <a name="step-8-complete-post-migration-tasks"></a>Stap 8: Taken na de migratie voltooien
<a name="BK_Step8"> </a>

- **Maak een AutoDiscover DNS-record, zodat gebruikers gemakkelijk bij hun postvakken kunnen komen.** Nadat alle on-premises postvakken zijn gemigreerd naar Microsoft 365, kunt u een AUTODISCOVER DNS-record configureren voor uw Microsoft 365-organisatie, zodat gebruikers eenvoudig verbinding kunnen maken met hun nieuwe Microsoft 365-postvakken met Outlook en mobiele clients. Deze nieuwe AUTODISCOVER DNS-record moet dezelfde naamruimte gebruiken die u gebruikt voor uw Microsoft 365 organisatie. Als de naamruimte in de cloud bijvoorbeeld cloud.contoso.com, wordt de DNS-record voor automatisch zoeken die u moet maken, autodiscover.cloud.contoso.com.

    Als u uw Exchange Server houdt, moet u er ook voor zorgen dat autodiscover DNS CNAME-record na de migratie moet wijzen naar Microsoft 365 in zowel interne als externe DNS, zodat de Outlook-client verbinding maakt met het juiste postvak.

    > [!NOTE]
    >  In Exchange 2007, Exchange 2010 en Exchange 2013 moet u ook instellen `Set-ClientAccessServer AutodiscoverInternalConnectionURI` op `Null` .

    Microsoft 365 CNAME-record gebruikt om de Autodiscover-service te implementeren voor Outlook en mobiele clients. De CNAME-record voor Automatisch opsporen moet de volgende informatie bevatten:

  - **Alias:** autodiscover

  - **Doel:** autodiscover.outlook.com

    Zie DNS-records toevoegen [om uw domein te verbinden voor meer informatie.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

- **On-premises Exchange-servers buiten bedrijf stellen.** Nadat u hebt geverifieerd dat alle e-mail rechtstreeks naar de Microsoft 365-postvakken wordt gerouteerd en u uw on-premises e-mailorganisatie niet meer hoeft te onderhouden of niet van plan bent een enkele aanmeldingsoplossing (SSO) te implementeren, kunt u Exchange van uw servers verwijderen en uw on-premises Exchange-organisatie verwijderen.

    Zie de volgende onderwerpen voor meer informatie:

  - [Exchange 2010 wijzigen of verwijderen](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Een Exchange 2007-organisatie verwijderen](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Exchange Server 2003 verwijderen](/previous-versions/tn-archive/bb125110(v=exchg.65))