---
title: Postvakken Exchange Online in een multi-geo-omgeving beheren
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
description: Meer informatie over het beheren Exchange Online multi-geo-instellingen in Microsoft 365 omgeving met PowerShell.
ms.openlocfilehash: c8f06318313c4192fc2b3a289727933c5a54f3ad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905582"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Postvakken Exchange Online in een multi-geo-omgeving beheren

Exchange Online PowerShell is vereist voor het weergeven en configureren van multigeo-eigenschappen in uw Microsoft 365 omgeving. Zie [Verbinding maken met Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

U hebt de [Microsoft Azure Active Directory PowerShell-module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v1.1.166.0 of hoger in v1.x nodig om de eigenschap **PreferredDataLocation** op gebruikersobjecten te zien. Gebruikersobjecten die via AAD Verbinding maken in AAD kunnen hun **PreferredDataLocation-waarde** niet rechtstreeks via AAD PowerShell wijzigen. Gebruikersobjecten in de cloud kunnen worden gewijzigd via AAD PowerShell. Als u verbinding wilt maken met Azure AD PowerShell, Verbinding maken [PowerShell.](connect-to-microsoft-365-powershell.md)

In Exchange Online multi-geoomgevingen hoeft u geen handmatige stappen uit te voeren om geo's toe te voegen aan uw tenant. Nadat u het Berichtcentrumbericht hebt ontvangen met de melding dat multi-geo gereed is voor gebruik Exchange Online, zijn alle beschikbare geo's gereed en geconfigureerd voor gebruik.

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Verbinding maken rechtstreeks naar een geografische locatie met Exchange Online PowerShell

Meestal wordt Exchange Online PowerShell verbonden met de centrale geografische locatie. Maar u kunt ook rechtstreeks verbinding maken met satellietlocatielocaties. Vanwege prestatieverbeteringen raden we u aan rechtstreeks verbinding te maken met de satellietlocatie als u alleen gebruikers op die locatie beheert.

De vereisten voor het installeren en gebruiken van de EXO V2-module worden beschreven in [De EXO V2-module installeren](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module)en onderhouden.

Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de *parameter ConnectionUri* anders dan de normale verbindingsinstructies. De rest van de opdrachten en waarden zijn hetzelfde.

U moet met name de waarde toevoegen `?email=<emailaddress>` aan het einde van de _ConnectionUri-waarde._ `<emailaddress>` is het e-mailadres van **een postvak** in de doellocatie. Uw machtigingen voor dat postvak of de relatie met uw referenties zijn geen factor. Het e-mailadres geeft gewoon aan Exchange Online PowerShell waar u verbinding kunt maken.

Microsoft 365 of Microsoft 365 GCC klanten hoeven meestal de _parameter ConnectionUri_ niet te gebruiken om verbinding te maken met Exchange Online PowerShell. Maar als u verbinding wilt maken met een specifieke geografische locatie, moet u _de parameter ConnectionUri_ gebruiken, zodat u deze `?email=<emailaddress>` in de waarde kunt gebruiken.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Verbinding maken naar een geografische locatie in Exchange Online PowerShell

De volgende verbindingsinstructies werken voor accounts die wel of niet zijn geconfigureerd voor meervoudige verificatie (MFA).

1. Laad in Windows PowerShell venster de EXO V2-module door de volgende opdracht uit te voeren:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. In het volgende voorbeeld admin@contoso.onmicrosoft.com het beheerdersaccount en de doellocatie is de locatie waar het postvak olga@contoso.onmicrosoft.com zich bevindt.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Voer het wachtwoord voor de admin@contoso.onmicrosoft.com in de prompt die wordt weergegeven. Als het account is geconfigureerd voor MFA, moet u ook de beveiligingscode invoeren.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>De beschikbare geografische locaties weergeven die zijn geconfigureerd in uw Exchange Online organisatie

Als u de lijst met geconfigureerde geografische locaties in Microsoft 365 Multi-Geo wilt bekijken, voer u de volgende opdracht uit in Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>De centrale geografische locatie voor uw Exchange Online weergeven

Als u de centrale geografische locatie van uw tenant wilt bekijken, voer u de volgende opdracht uit in Exchange Online PowerShell:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>De geografische locatie van een postvak zoeken

Met **de cmdlet Postvak** in Exchange Online PowerShell worden de volgende multi-geogerelateerde eigenschappen voor postvakken weergegeven:

- **Database:** de eerste 3 letters van de databasenaam komen overeen met de geocode, die u vertelt waar het postvak zich momenteel bevindt. Voor Postvakken voor onlinearchiveren moet de eigenschap **ArchiveDatabase** worden gebruikt.

- **Postvakregio:** geeft de geolocatiecode op die is ingesteld door de beheerder (gesynchroniseerd vanuit **PreferredDataLocation** in Azure AD).

- **PostvakRegionLastUpdateTime:** geeft aan wanneer PostvakRegio voor het laatst is bijgewerkt (automatisch of handmatig).

Als u deze eigenschappen voor een postvak wilt zien, gebruikt u de volgende syntaxis:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Als u bijvoorbeeld de geografische locatiegegevens voor het postvak wilt chris@contoso.onmicrosoft.com, voer dan de volgende opdracht uit:

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
> Als de geolocatiecode in de databasenaam niet overeenkomen met de waarde **PostvakRegio,** wordt het postvak automatisch in een verplaatsingswachtrij geplaatst en verplaatst naar de geografische locatie die is opgegeven met de waarde **Postvakregio** (Exchange Online zoekt naar een onjuiste overeenkomst tussen deze eigenschapswaarden).

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Een bestaand postvak in de cloud verplaatsen naar een specifieke geografische locatie

Een cloudgebruiker is een gebruiker die niet is gesynchroniseerd met de tenant via AAD-Verbinding maken. Deze gebruiker is rechtstreeks gemaakt in Azure AD. Gebruik de **get-MsolUser-** en **Set-MsolUser-cmdlets** in de Azure AD-module voor Windows PowerShell om de geografische locatie te bekijken of op te geven waar het postvak van een cloudgebruiker wordt opgeslagen.

Als u de **waarde PreferredDataLocation** voor een gebruiker wilt weergeven, gebruikt u deze syntaxis in Azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Als u bijvoorbeeld de **waarde PreferredDataLocation** voor de gebruiker michelle@contoso.onmicrosoft.com, voer dan de volgende opdracht uit:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Gebruik de volgende syntaxis in Azure AD PowerShell om de **waarde PreferredDataLocation** voor een gebruikersobject in de cloud te wijzigen:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Voer bijvoorbeeld de volgende opdracht uit als u de **waarde PreferredDataLocation** wilt instellen op de geo van de Europese Unie (EUR) voor de michelle@contoso.onmicrosoft.com gebruiker:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten van on-premises Active Directory. U moet de waarde **PreferredDataLocation** wijzigen in Active Directory en deze synchroniseren met AAD-Verbinding maken. Zie voor meer informatie [Azure Active Directory Verbinding maken synchronisatie: Gewenste gegevenslocatie configureren voor Microsoft 365 resources.](/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation)
>
> - Hoe lang het duurt om een postvak te verplaatsen naar een nieuwe geografische locatie, hangt af van verschillende factoren:
>
>   - De grootte en het type postvak.
>   - Het aantal postvakken dat wordt verplaatst.
>   - De beschikbaarheid van resources verplaatsen.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Een inactief postvak naar een specifiek geo verplaatsen

U kunt niet inactieve postvakken verplaatsen die zijn bewaard voor nalevingsdoeleinden (bijvoorbeeld postvakken in De bewaarplaats voor rechtszaken) door de **PreferredDataLocation-waarde te** wijzigen. Als u een inactief postvak naar een ander geo wilt verplaatsen, gaat u als volgt te werk:

1. Herstel het inactieve postvak. Zie Een [inactief postvak](../compliance/recover-an-inactive-mailbox.md)herstellen voor instructies.

2. Voorkom dat de beheerde mapassistent het herstelde postvak verwerkt door de naam, alias, account of e-mailadres van het postvak te vervangen en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Wijs een **Exchange Online abonnement 2 toe** aan het herstelde postvak. Deze stap is vereist om het postvak weer in de wacht te zetten voor rechtszaken. Zie Licenties [toewijzen aan gebruikers](../admin/manage/assign-licenses-to-users.md)voor instructies.

4. Configureer **de waarde PreferredDataLocation** in het postvak zoals beschreven in de vorige sectie.

5. Nadat u hebt bevestigd dat het postvak is verplaatst naar de nieuwe geografische locatie, zet u het herstelde postvak weer in de procesvoering. Zie Een postvak in de wacht houden [voor rechtszaken voor instructies.](../compliance/create-a-litigation-hold.md#place-a-mailbox-on-litigation-hold)

6. Nadat u hebt gecontroleerd of de procedure is uitgevoerd, kunt u toestaan dat de assistent voor beheerde mappen het postvak opnieuw verwerkt door de naam, alias, account of e-mailadres van het postvak te vervangen en de volgende opdracht uit te voeren \<MailboxIdentity\> in [Exchange Online PowerShell:](/powershell/exchange/connect-to-exchange-online-powershell)

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Maak het postvak opnieuw inactief door het gebruikersaccount te verwijderen dat aan het postvak is gekoppeld. Zie Een gebruiker [uit uw organisatie verwijderen voor instructies.](../admin/add-users/delete-a-user.md) Met deze stap wordt ook de Exchange Online abonnement 2 voor andere toepassingen uitgebracht.

**Opmerking:** Wanneer u een inactief postvak naar een andere geografische locatie verplaatst, kan dit van invloed zijn op de zoekresultaten van inhoud of op de mogelijkheid om het postvak te doorzoeken vanaf de voormalige geografische locatie. Zie Inhoud zoeken en [exporteren in Multi-Geo-omgevingen](../compliance/set-up-compliance-boundaries.md#searching-and-exporting-content-in-multi-geo-environments)voor meer informatie.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Nieuwe cloudpostvakken maken op een specifieke geografische locatie

Als u een nieuw postvak wilt maken op een specifieke geografische locatie, moet u een van de volgende stappen doen:

- Configureer **de waarde PreferredDataLocation** zoals beschreven in het vorige Een  bestaand [postvak](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) alleen in de cloud verplaatsen naar een specifieke sectie voor geografische locatie voordat u het postvak in Exchange Online. Configureer bijvoorbeeld de **waarde PreferredDataLocation** op een gebruiker voordat u een licentie toewijst.

- Wijs een licentie toe op hetzelfde moment dat u de **waarde PreferredDataLocation** in stelt.

Als u een nieuwe gebruiker met een cloudlicentie wilt maken (niet AAD Verbinding maken gesynchroniseerd) op een specifieke geografische locatie, gebruikt u de volgende syntaxis in Azure AD PowerShell:

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

In dit voorbeeld maakt u een nieuw gebruikersaccount voor Elizabeth Brunner met de volgende waarden:

- Gebruikersnaam: ebrunner@contoso.onmicrosoft.com
- Voornaam: Elizabeth
- Achternaam: Brunner
- Weergavenaam: Elizabeth Brunner
- Wachtwoord: willekeurig gegenereerd en weergegeven in de resultaten van de opdracht (omdat we de parameter *Wachtwoord* niet gebruiken)
- Licentie: `contoso:ENTERPRISEPREMIUM` (E5)
- Locatie: Australië (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Zie Gebruikersaccounts maken met [PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en Licenties en services weergeven met PowerShell voor meer informatie over het maken van nieuwe gebruikersaccounts en het vinden van LicenseAssignment-waarden in Azure AD [PowerShell.](view-licenses-and-services-with-microsoft-365-powershell.md)

> [!NOTE]
> Als u Exchange Online PowerShell gebruikt om een postvak in te stellen en het postvak rechtstreeks op de geolocatie wilt maken die is opgegeven in **PreferredDataLocation,** moet u een cmdlet van Exchange Online, zoals **Postvak** inschakelen of **Nieuw-postvak,** rechtstreeks tegen de cloudservice gebruiken. Als u de **cmdlet Enable-RemoteMailbox** gebruikt in on-premises Exchange PowerShell, wordt het postvak gemaakt op de centrale geografische locatie.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Bestaande on-premises postvakken in een specifieke geografische locatie onboarden

U kunt de standaardhulpmiddelen en -processen voor onboarding gebruiken om een postvak te migreren van een on-premises Exchange-organisatie naar Exchange Online, waaronder het migratiedashboard in het [EAC](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)en de cmdlet [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch) in Exchange Online PowerShell.

De eerste stap is om te controleren of er een gebruikersobject bestaat voor elk postvak dat moet worden onboarded en of de juiste **PreferredDataLocation-waarde** is geconfigureerd in Azure AD. De onboarding-hulpprogramma's respecteren de **PreferredDataLocation-waarde** en migreren de postvakken rechtstreeks naar de opgegeven geografische locatie.

U kunt ook de volgende stappen gebruiken om postvakken rechtstreeks op een specifieke geografische locatie aan te nemen met de cmdlet [New-MoveRequest](/powershell/module/exchange/new-moverequest) in Exchange Online PowerShell.

1. Controleer of het gebruikersobject bestaat voor elk postvak dat moet worden onboarded en of **PreferredDataLocation** is ingesteld op de gewenste waarde in Azure AD. De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het **kenmerk Postvakregio van** het bijbehorende e-mailgebruikersobject in Exchange Online.

2. Verbinding maken rechtstreeks naar de specifieke satellietlocatie via de verbindingsinstructies van eerder in dit onderwerp.

3. Sla Exchange Online PowerShell de on-premises beheerdersreferenties op die worden gebruikt om een postvakmigratie uit te voeren in een variabele door de volgende opdracht uit te voeren:

   ```powershell
   $RC = Get-Credential
   ```

4. Maak Exchange Online PowerShell een nieuwe **nieuwe moveRequest,** vergelijkbaar met het volgende voorbeeld:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de satellietlocatie met wie u momenteel verbonden bent.

6. Als u extra postvakken wilt migreren naar verschillende satellietlocaties, herhaalt u stap 2 tot en met 4 voor elke specifieke locatie.

## <a name="multi-geo-reporting"></a>Multi-georapportage

**Met rapporten voor multigeogebruik** in het Microsoft 365 beheercentrum wordt het aantal gebruikers weergegeven op geografische locatie. In het rapport wordt de distributie van gebruikers voor de huidige maand weergegeven en worden historische gegevens voor de afgelopen 6 maanden weergegeven.

## <a name="see-also"></a>Zie ook

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)