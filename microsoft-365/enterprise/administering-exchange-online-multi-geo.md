---
title: Exchange Online-postvakken beheren in een multige geo-omgeving
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-mar2020
localization_priority: normal
description: Informatie over het beheren van multige geo-instellingen van Exchange Online in uw Microsoft 365-omgeving met PowerShell.
ms.openlocfilehash: 83889b4582d2e305b2cb9f07a64307e85d30be77
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406040"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Exchange Online-postvakken beheren in een multige geo-omgeving

Exchange Online PowerShell is vereist voor het weergeven en configureren van meerdere geografische eigenschappen in uw Microsoft 365-omgeving. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als je verbinding wilt maken met Exchange Online PowerShell.

U hebt de [Microsoft Azure Active Directory PowerShell-module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 of hoger in v1.x nodig om de eigenschap **PreferredDataLocation** op gebruikersobjecten te zien. Gebruikersobjecten die via AAD Connect in AAD zijn gesynchroniseerd, kunnen hun **PreferredDataLocation-waarde** niet rechtstreeks wijzigen via AAD PowerShell. Gebruikersobjecten in de cloud kunnen worden gewijzigd via AAD PowerShell. Zie Connect to PowerShell (Verbinding maken met PowerShell) als u verbinding wilt maken met Azure AD [PowerShell.](connect-to-microsoft-365-powershell.md)

In Exchange Online-omgevingen met meerdere geografische omgevingen hoeft u geen handmatige stappen uit te voeren om geo's toe te voegen aan uw tenant. Nadat u het bericht in het berichtencentrum hebt ontvangen dat multige geo gereed is voor Exchange Online, zijn alle beschikbare geo's gereed en geconfigureerd voor gebruik.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Rechtstreeks verbinding maken met een geografische locatie met Exchange Online PowerShell

Normaal gesproken maakt Exchange Online PowerShell verbinding met de centrale geografische locatie. Maar u kunt ook rechtstreeks verbinding maken met geografische satellietlocaties. Vanwege prestatieverbeteringen is het raadzaam om rechtstreeks verbinding te maken met de geografische satellietlocatie als u alleen gebruikers op die locatie beheert.

De vereisten voor het installeren en gebruiken van de EXO V2-module worden beschreven in [de EXO V2-module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)installeren en onderhouden.

Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de *ConnectionUri-parameter* anders dan de normale verbindingsinstructies. De rest van de opdrachten en waarden zijn hetzelfde.

U moet de waarde toevoegen aan het einde `?email=<emailaddress>` van de _ConnectionUri-waarde._ `<emailaddress>` is het e-mailadres van **een postvak** op de doellocatie. Uw machtigingen voor dat postvak of de relatie met uw referenties zijn geen factor. Met het e-mailadres wordt aan Exchange Online PowerShell alleen verteld waar verbinding moet worden gemaakt.

Klanten van Microsoft 365 of Microsoft 365 GCC hoeven meestal de _ConnectionUri-parameter_ niet te gebruiken om verbinding te maken met Exchange Online PowerShell. Maar als u verbinding wilt maken met een specifieke geografische locatie, moet u de _ConnectionUri-parameter_ gebruiken zodat u deze in de waarde `?email=<emailaddress>` kunt gebruiken.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Verbinding maken met een geografische locatie in Exchange Online PowerShell

De volgende verbindingsinstructies werken voor accounts die al dan niet zijn geconfigureerd voor meervoudige verificatie (MFA).

1. Laad in een Windows PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. In het volgende voorbeeld admin@contoso.onmicrosoft.com het beheerdersaccount en is de doellocatie de locatie olga@contoso.onmicrosoft.com postvak.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Voer het wachtwoord voor de admin@contoso.onmicrosoft.com in de prompt die wordt weergegeven. Als het account is geconfigureerd voor MFA, moet u ook de beveiligingscode invoeren.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>De beschikbare geografische locaties bekijken die zijn geconfigureerd in uw Exchange Online-organisatie

Voer de volgende opdracht uit in Exchange Online PowerShell om de lijst met geconfigureerde geografische locaties in Microsoft 365 Multi-Geo weer te geven:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>De centrale geografische locatie voor uw Exchange Online-organisatie weergeven

Voer de volgende opdracht uit in Exchange Online PowerShell om de centrale geografische locatie van uw tenant weer te geven:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>De geografische locatie van een postvak zoeken

Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende multi geo-gerelateerde eigenschappen voor postvakken weergegeven:

- **Database:** de eerste drie letters van de databasenaam komen overeen met de geografische code, die u vertelt waar het postvak zich momenteel bevindt. Voor onlinearchiefpostvakken moet de **eigenschap ArchiveDatabase** worden gebruikt.

- **MailboxRegion:** geeft de geografische locatiecode aan die is ingesteld door de beheerder (gesynchroniseerd vanuit **PreferredDataLocation** in Azure AD).

- **MailboxRegionLastUpdateTime:** geeft aan wanneer MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).

Gebruik de volgende syntaxis om deze eigenschappen voor een postvak weer te geven:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Als u bijvoorbeeld de geografische locatiegegevens voor de postvakgegevens chris@contoso.onmicrosoft.com, moet u de volgende opdracht uitvoeren:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

De uitvoer van de opdracht ziet er zo uit:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Als de geografische locatiecode in de databasenaam niet overeenkomen met de waarde voor **MailboxRegion,** wordt het postvak automatisch in een wachtrij geplaatst en verplaatst naar de geografische locatie die wordt opgegeven door de waarde voor **PostvakRegio** (Exchange Online zoekt naar een niet-overeenkomende waarde tussen deze eigenschapswaarden).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Een bestaand postvak in de cloud verplaatsen naar een specifieke geografische locatie

Een gebruiker die alleen in de cloud werkt, is een gebruiker die niet wordt gesynchroniseerd met de tenant via AAD Connect. Deze gebruiker is rechtstreeks in Azure AD gemaakt. Gebruik de cmdlets **Get-MsolUser** en **Set-MsolUser** in de Azure AD-module voor Windows PowerShell om de geografische locatie weer te geven waar het postvak van een gebruiker die alleen in de cloud wordt opgeslagen, wordt opgeslagen.

Als u de **PreferredDataLocation-waarde voor** een gebruiker wilt bekijken, gebruikt u deze syntaxis in Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Als u bijvoorbeeld de **waarde PreferredDataLocation** voor de michelle@contoso.onmicrosoft.com gebruiker wilt zien, moet u de volgende opdracht uitvoeren:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Gebruik de volgende syntaxis in Azure AD PowerShell om de **waarde PreferredDataLocation** te wijzigen voor een gebruikersobject in de cloud:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Als u bijvoorbeeld de **waarde PreferredDataLocation** wilt instellen op de geografische waarde van de Europese Unie (EUR) voor de michelle@contoso.onmicrosoft.com gebruiker, moet u de volgende opdracht uitvoeren:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten vanuit on-premises Active Directory. U moet de waarde **van PreferredDataLocation** in Active Directory wijzigen en synchroniseren met AAD Connect. Zie Azure [Active Directory Connect-synchronisatie: Voorkeursgegevenslocatie configureren voor Microsoft 365-bronnen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)voor meer informatie.
>
> - Hoe lang het duurt om een postvak een nieuwe geografische locatie te geven, hangt af van verschillende factoren:
>
>   - De grootte en het type van het postvak.
>   - Het aantal postvakken dat wordt verplaatst.
>   - De beschikbaarheid van resources verplaatsen.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Een inactief postvak verplaatsen naar een specifieke geografische locatie

U kunt inactieve postvakken die blijven behouden voor nalevingsdoeleinden (bijvoorbeeld postvakken bij het bewaren van postvakken met een juridische procedure) niet verplaatsen door de **PreferredDataLocation-waarde te** wijzigen. Als u een inactief postvak wilt verplaatsen naar een ander geografisch gebied, gaat u als volgt te werk:

1. Herstel het inactieve postvak. Zie Een [inactief postvak herstellen voor instructies.](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)

2. Voorkom dat beheerde mapassistent het herstelde postvak verwerkt door het te vervangen door de naam, alias, het account of het e-mailadres van het postvak en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Wijs een **licentie voor Exchange Online Abonnement 2** toe aan het herstelde postvak. Deze stap is vereist om het postvak weer in de wacht te zetten bij juridische procedure. Zie Licenties toewijzen [aan gebruikers voor instructies.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

4. Configureer de **PreferredDataLocation-waarde** voor het postvak, zoals beschreven in de vorige sectie.

5. Nadat u hebt bevestigd dat het postvak is verplaatst naar de nieuwe geografische locatie, zet u het herstelde postvak weer in de postvak in de juridische procedure. Zie Postvak in de wacht zetten [voor juridische procedures voor instructies.](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold)

6. Nadat u hebt gecontroleerd of de Postvak IN van postvakgegevens is geplaatst, laat u de Beheerde mapassistent het postvak opnieuw verwerken door het postvak te vervangen door de naam, alias, het account of het e-mailadres van het postvak en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Maak het postvak opnieuw inactief door het gebruikersaccount te verwijderen dat aan het postvak is gekoppeld. Zie Een gebruiker [uit uw organisatie verwijderen voor instructies.](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user) Met deze stap wordt ook de licentie voor Exchange Online (Abonnement 2) voor ander gebruik uitgebracht.

**Opmerking:** wanneer u een inactief postvak naar een andere geografische locatie verplaatst, kan dit van invloed zijn op zoekresultaten voor inhoud of de mogelijkheid om in het postvak te zoeken vanaf de voormalige geografische locatie. Zie Zoeken en exporteren [van inhoud in Multi-Geo-omgevingen](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)voor meer informatie.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Nieuwe postvakken in de cloud maken op een specifieke geografische locatie

Als u een nieuw postvak wilt maken op een specifieke geografische locatie, moet u een van de volgende stappen volgen:

- Configureer de **waarde PreferredDataLocation** zoals is beschreven in de vorige  sectie Een bestaand [postvak](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) in de cloud verplaatsen naar een specifieke geografische locatie voordat u het postvak in Exchange Online maakt. Configureer bijvoorbeeld de **waarde PreferredDataLocation** voor een gebruiker voordat u een licentie toewijst.

- Wijs een licentie toe op het moment dat u de **waarde van PreferredDataLocation in** stelt.

Als u een nieuwe gebruiker met een cloudlicentie wilt maken (niet gesynchroniseerd met AAD Connect) op een specifieke geografische locatie, gebruikt u de volgende syntaxis in Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

In dit voorbeeld wordt een nieuw gebruikersaccount voor Elizabeth Bwaarden aangemaakt met de volgende waarden:

- User principal name: ebrunner@contoso.onmicrosoft.com
- Voornaam: Elizabeth
- Achternaam: B goed
- Weergavenaam: Elizabeth Bweergave
- Wachtwoord: willekeurig gegenereerd en weergegeven in de resultaten van de opdracht (omdat we de parameter *Password niet* gebruiken)
- Licentie: `contoso:ENTERPRISEPREMIUM` (E5)
- Locatie: Australië (Australië)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Zie Gebruikersaccounts maken met [PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en licenties en services weergeven met PowerShell voor meer informatie over het maken van nieuwe gebruikersaccounts en het zoeken naar de waarden voor LicenseAssignment in Azure AD [PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

> [!NOTE]
> Als u Exchange Online PowerShell gebruikt om een postvak in teschakelen en u het postvak rechtstreeks wilt maken op de geografische locatie die is opgegeven in **PreferredDataLocation,** moet u een Exchange Online-cmdlet zoals **Enable-Mailbox** of **New-Mailbox** rechtstreeks gebruiken voor de cloudservice. Als u de cmdlet **Enable-RemoteMailbox** gebruikt in on-premises Exchange PowerShell, wordt het postvak gemaakt op de centrale geografische locatie.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Bestaande on-premises postvakken in een specifieke geografische locatie onboarden

U kunt de standaard-onboarding-hulpprogramma's en -processen gebruiken om een postvak te migreren van een on-premises Exchange-organisatie naar Exchange Online, inclusief het migratiedashboard in het Exchange-exchange-programma en de cmdlet [New-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) in Exchange Online PowerShell. [](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)

De eerste stap bestaat uit het controleren van een gebruikersobject voor elk postvak dat moet worden onboarded en controleren of de juiste **PreferredDataLocation-waarde** is geconfigureerd in Azure AD. De onboarding-hulpprogramma's houden zich aan de **waarde preferredDataLocation** en migreren de postvakken rechtstreeks naar de opgegeven geografische locatie.

U kunt ook de volgende stappen gebruiken om postvakken rechtstreeks in een specifieke geografische locatie in te voeren met de cmdlet [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) in Exchange Online PowerShell.

1. Controleer of het gebruikersobject bestaat voor elk postvak dat moet worden onboarded en of **PreferredDataLocation** is ingesteld op de gewenste waarde in Azure AD. De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het kenmerk **MailboxRegion** van het bijbehorende e-mailgebruikersobject in Exchange Online.

2. Maak rechtstreeks verbinding met de specifieke geografische satellietlocatie aan de hand van de verbindingsinstructies eerder in dit onderwerp.

3. Sla in Exchange Online PowerShell de lokale beheerdersreferenties op die worden gebruikt voor het uitvoeren van een postvakmigratie in een variabele door de volgende opdracht uit te voeren:

   ```powershell
   $RC = Get-Credential
   ```

4. Maak in Exchange Online PowerShell een nieuwe **New-MoveRequest** zoals in het volgende voorbeeld:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische satellietlocatie die u momenteel hebt verbonden.

6. Als u extra postvakken wilt migreren naar verschillende geografische satellietlocaties, herhaalt u stap 2 tot en met 4 voor elke specifieke locatie.

## <a name="multi-geo-reporting"></a>Multi-geo reporting

**Rapporten over multige geoverbruik** in het Microsoft 365-beheercentrum geven het aantal gebruikers per geografische locatie weer. In het rapport wordt de gebruikersdistributie voor de huidige maand weergegeven en worden historische gegevens voor de afgelopen zes maanden weergegeven.

## <a name="see-also"></a>Zie ook

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
