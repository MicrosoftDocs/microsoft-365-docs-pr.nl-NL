---
title: Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren
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
description: Meer informatie over het beheren van multi-geografische instellingen van Exchange Online in uw Microsoft 365-omgeving met PowerShell.
ms.openlocfilehash: 63eb1957611fd57e216012435188a6ddd1b232d3
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49552005"
---
# <a name="administering-exchange-online-mailboxes-in-a-multi-geo-environment"></a>Postvakken van Exchange Online in een omgeving met meerdere geografische gebieden beheren

Exchange Online PowerShell is vereist voor het weergeven en configureren van meervoudige geo-eigenschappen in uw Microsoft 365-omgeving. Zie [Verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) als u verbinding wilt maken met Exchange Online PowerShell.

U hebt [Microsoft Azure Active Directory PowerShell module](https://social.technet.microsoft.com/wiki/contents/articles/28552.microsoft-azure-active-directory-powershell-module-version-release-history.aspx) v 1.1.166.0 of hoger nodig in v1. x om de eigenschap **PreferredDataLocation** voor gebruikersobjecten weer te geven. Gebruikersobjecten die zijn gesynchroniseerd via AAD Connect in AAD, kunnen hun **PreferredDataLocation** -waarde niet rechtstreeks wijzigen via Aad PowerShell. Gebruikersobjecten in de Cloud kunnen met behulp van AAD PowerShell worden gewijzigd. Als u verbinding wilt maken met Azure AD PowerShell, raadpleegt [u verbinding maken met PowerShell](connect-to-microsoft-365-powershell.md).

## <a name="connect-directly-to-a-geo-location-using-exchange-online-powershell"></a>Direct verbinding maken met een geo-locatie met Exchange Online PowerShell

Meestal maakt Exchange Online PowerShell verbinding met de centrale geo-locatie. Maar u kunt ook rechtstreeks verbinding maken met satelliet locaties. Vanwege prestatieverbeteringen wordt u aangeraden direct verbinding te maken met de geografische locatie van de satelliet wanneer u alleen gebruikers op die locatie beheert.

De vereisten voor het installeren en gebruiken van de module EXO v2 worden beschreven in [de Exo V2-module installeren en onderhouden](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module).

Als u Exchange Online PowerShell wilt verbinden met een specifieke geografische locatie, is de parameter *ConnectionUri* niet gelijk aan de reguliere verbindings instructies. De rest van de opdrachten en waarden zijn hetzelfde.

U moet de waarde specifiek toevoegen `?email=<emailaddress>` aan het einde van de _ConnectionUri_ -waarde. `<emailaddress>` het e-mailadres van **een** postvak in de geografische doellocatie. Uw machtigingen voor dit postvak of de relatie met uw referenties zijn geen factor. het e-mailadres vertelt Exchange Online PowerShell waar verbinding moet worden gemaakt.

Voor klanten met Microsoft 365 of Microsoft 365 GCC, hoeft u de _ConnectionUri_ -parameter meestal niet te gebruiken om verbinding te maken met Exchange Online PowerShell. Als u verbinding wilt maken met een specifieke geografische locatie, moet u _ConnectionUri_ -parameter gebruiken, zodat u `?email=<emailaddress>` deze kunt gebruiken in de waarde.

### <a name="connect-to-a-geo-location-in-exchange-online-powershell"></a>Verbinding maken met een geografische locatie in Exchange Online PowerShell

De volgende verbindings instructies werken voor accounts die niet zijn geconfigureerd voor multi-factor Authentication (MFA).

1. Laad in een Windows PowerShell-venster de module EXO V2 door de volgende opdracht uit te voeren:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

2. In het volgende voorbeeld is admin@contoso.onmicrosoft.com het beheerdersaccount en is de geografische locatie van de doellocatie de plaats waar het postvak olga@contoso.onmicrosoft.com zich bevindt.

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName admin@contoso.onmicrosoft.com -ConnectionUri https://outlook.office365.com/powershell?email=olga@contoso.onmicrosoft.com
   ```

3. Voer het wachtwoord in voor de admin@contoso.onmicrosoft.com in de prompt die wordt weergegeven. Als het account is geconfigureerd voor MFA, moet u ook de beveiligingscode invoeren.

## <a name="view-the-available-geo-locations-that-are-configured-in-your-exchange-online-organization"></a>De beschikbare geo-locaties weergeven die zijn geconfigureerd in uw Exchange Online-organisatie

Voer de volgende opdracht uit in PowerShell van Exchange Online voor een overzicht van de geconfigureerde geografische locaties in Microsoft 365 multi-geo:

```powershell
Get-OrganizationConfig | Select -ExpandProperty AllowedMailboxRegions | Format-Table
```

## <a name="view-the-central-geo-location-for-your-exchange-online-organization"></a>De centrale geo-locatie voor uw Exchange Online-organisatie weergeven

Voer de volgende opdracht uit in Exchange Online PowerShell als u de centrale geografische locatie van de Tenant wilt weergeven:

```powershell
Get-OrganizationConfig | Select DefaultMailboxRegion
```

## <a name="find-the-geo-location-of-a-mailbox"></a>De geografische locatie van een postvak zoeken

Met de cmdlet **Get-Mailbox** in Exchange Online PowerShell worden de volgende eigenschappen met betrekking tot multi-geografische eigenschappen weergegeven voor postvakken:

- **Database**: de eerste drie letters van de database naam komen overeen met de geografische code, waarmee wordt aangegeven waar het postvak zich momenteel bevindt. Voor online archief postvakken moet de eigenschap **ArchiveDatabase** worden gebruikt.

- **MailboxRegion**: geeft de geografische locatie code aan die door de beheerder is ingesteld (gesynchroniseerd van **PREFERREDDATALOCATION** in azure AD).

- **MailboxRegionLastUpdateTime**: geeft aan wanneer de MailboxRegion voor het laatst is bijgewerkt (automatisch of handmatig).

Gebruik de volgende syntaxis om de eigenschappen van een postvak te bekijken:

```powershell
Get-Mailbox -Identity <MailboxIdentity> | Format-List Database,MailboxRegion*
```

Voer de volgende opdracht uit als u de gegevens van de geografische locatie voor de Postvak chris@contoso.onmicrosoft.com wilt weergeven:

```powershell
Get-Mailbox -Identity chris@contoso.onmicrosoft.com | Format-List Database, MailboxRegion*
```

De uitvoer van de opdracht ziet er als volgt uit:

```powershell
Database                    : EURPR03DG077-db007
MailboxRegion               : EUR
MailboxRegionLastUpdateTime : 2/6/2018 8:21:01 PM
```

> [!NOTE]
> Als de geo-vestigingcode in de databasenaam niet overeenkomt met de waarde van **MailboxRegion** , wordt het postvak automatisch toegevoegd aan een wachtrij voor hernoemen en wordt verplaatst naar de geo-locatie die is opgegeven via de **MailboxRegion** -waarde (Exchange Online zoekt de waarden van deze eigenschap niet.

## <a name="move-an-existing-cloud-only-mailbox-to-a-specific-geo-location"></a>Een bestaand postvak met alleen de Cloud naar een specifieke geografische locatie verplaatsen

Een gebruiker met Cloud is een gebruiker die niet is gesynchroniseerd met de Tenant via AAD Connect. Deze gebruiker is rechtstreeks gemaakt in azure AD. Met de cmdlet **Get-MsolUser** en **set-MsolUser** in de Azure ad-module voor Windows PowerShell kunt u de geografische locatie weergeven of opgeven waarop het postvak van de gebruikers van de Cloud wordt opgeslagen.

Als u de **PreferredDataLocation** waarde voor een gebruiker wilt bekijken, gebruikt u deze syntaxis in azure AD PowerShell:

```powershell
Get-MsolUser -UserPrincipalName <UserPrincipalName> | Format-List UserPrincipalName,PreferredDataLocation
```

Voer de volgende opdracht uit als u de **PreferredDataLocation** waarde voor het gebruikers Michelle@contoso.onmicrosoft.com wilt bekijken:

```powershell
Get-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com | Format-List
```

Gebruik de volgende syntaxis in azure AD PowerShell om de **PreferredDataLocation** -waarde voor een gebruikersobject in de cloud te wijzigen:

```powershell
Set-MsolUser -UserPrincipalName <UserPrincipalName> -PreferredDataLocation <GeoLocationCode>
```

Voer de volgende opdracht uit om de **PreferredDataLocation** waarde in te stellen op de Europese Unie (USD) Geo voor de gebruikers Michelle@contoso.onmicrosoft.com:

```powershell
Set-MsolUser -UserPrincipalName michelle@contoso.onmicrosoft.com -PreferredDataLocation EUR
```

> [!NOTE]
>
> - Zoals eerder vermeld, kunt u deze procedure niet gebruiken voor gesynchroniseerde gebruikersobjecten uit on-premises Active Directory. U moet de **PreferredDataLocation** waarde in Active Directory wijzigen en synchroniseren met behulp van Aad Connect. Zie voor meer informatie [Azure Active Directory Connect Sync: voorkeur gegevenslocatie voor Microsoft 365-bronnen configureren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-preferreddatalocation).
>
> - Hoe lang het duurt om een postvak te verplaatsen naar een nieuwe geografische locatie, is afhankelijk van verschillende factoren:
>
>   - De grootte en het type van het postvak.
>   - Het aantal postvakken dat wordt verplaatst.
>   - De beschikbaarheid van bronnen voor verhuizing.

### <a name="move-an-inactive-mailbox-to-a-specific-geo"></a>Een inactief postvak naar een specifieke geo verplaatsen

Het is niet mogelijk om niet-actieve postvakken te verplaatsen die worden bewaard voor nalevings functies (bijvoorbeeld postvakken op de aangifte voor de geschil) door hun **PreferredDataLocation** waarde te wijzigen. Voer de volgende stappen uit om een inactief postvak naar een andere geografische plaats te verplaatsen:

1. Herstel het inactief postvak. Zie [een inactief postvak herstellen](https://docs.microsoft.com/microsoft-365/compliance/recover-an-inactive-mailbox)voor instructies.

2. Voorkomen dat de assistent voor beheerde mappen het herstelde postvak verwerkt door te vervangen door \<MailboxIdentity\> de naam, alias, account of het e-mailadres van het postvak en de volgende opdracht uit te voeren in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $true
    ```

3. Wijs een licentie voor **Exchange Online plan 2** toe aan het hersteld postvak. Deze stap is vereist voor het terugplaatsen van het postvak op het in de wachtstand van een zaak. Zie [licenties toewijzen aan gebruikers](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)voor instructies.

4. Configureer de **PreferredDataLocation** -waarde in het postvak, zoals beschreven in de vorige sectie.

5. Nadat u hebt bevestigd dat het postvak naar de nieuwe geografische locatie is verplaatst, plaatst u het herstelde postvak weer op de plaats van het betreffende geschil. Zie voor instructies [een postvak in plaats van de rechtszaken](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold#place-a-mailbox-on-litigation-hold).

6. Nadat u hebt gecontroleerd of het bericht over de bewaring is ingevoerd, kunt u de Managed folder-assistent opnieuw uitvoeren door de \<MailboxIdentity\> naam, alias, account of het e-mailadres van het postvak te vervangen door de volgende opdracht uit te voeren in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell):

    ```powershell
    Set-Mailbox <MailboxIdentity> -ElcProcessingDisabled $false
    ```

7. Maak het postvak opnieuw inactief door het gebruikersaccount dat is gekoppeld aan het postvak te verwijderen. Zie [een gebruiker van uw organisatie verwijderen](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)voor instructies. In deze stap wordt ook de licentie voor Exchange Online plan 2 vrijgegeven voor andere gebruiksdoeleinden.

**Opmerking**: wanneer u een inactief postvak naar een andere geografische locatie verplaatst, kan dit gevolgen hebben voor de zoekresultaten van inhoud of de mogelijkheid om te zoeken in het postvak van de voormalige geografische locatie. Zie [inhoud zoeken en exporteren in meerdere geo-omgevingen](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries#searching-and-exporting-content-in-multi-geo-environments)voor meer informatie.

## <a name="create-new-cloud-mailboxes-in-a-specific-geo-location"></a>Nieuwe Cloud postvakken maken op een specifieke geografische locatie

Voer een van de volgende stappen uit als u een nieuw postvak op een specifieke geografische locatie wilt maken:

- Configureer de **PreferredDataLocation** waarde zoals beschreven in het vorige [postvak van een bestaande Cloud naar een specifieke geo-locatie](#move-an-existing-cloud-only-mailbox-to-a-specific-geo-location) sectie verplaatsen *voordat* u het postvak maakt in Exchange Online. U kunt bijvoorbeeld de **PreferredDataLocation** -waarde configureren voor een gebruiker voordat u een licentie toewijst.

- Wijs tegelijkertijd een licentie toe aan de **PreferredDataLocation** -waarde.

Gebruik de volgende syntaxis in azure AD PowerShell voor het maken van een nieuwe, in de Cloud gerichte gebruiker (niet AAD Connected) op een specifieke geografische locatie.

```powershell
New-MsolUser -UserPrincipalName <UserPrincipalName> -DisplayName "<Display Name>" [-FirstName <FirstName>] [-LastName <LastName>] [-Password <Password>] [-LicenseAssignment <AccountSkuId>] -PreferredDataLocation <GeoLocationCode>
```

In dit voorbeeld wordt een nieuwe gebruikersaccount gemaakt voor Elizabeth Brunner met de volgende waarden:

- UPN (User Principal Name): ebrunner@contoso.onmicrosoft.com
- Voornaam: Elizabeth
- Achternaam: Brunner
- Weergavenaam: Elizabeth Brunner
- Wachtwoord: willekeurig gegenereerd en wordt weergegeven in de resultaten van de opdracht (omdat we de *wachtwoord* parameters niet gebruiken)
- Licentie: `contoso:ENTERPRISEPREMIUM` (E5)
- Locatie: Australië (AUS)

```powershell
New-MsolUser -UserPrincipalName ebrunner@contoso.onmicrosoft.com -DisplayName "Elizabeth Brunner" -FirstName Elizabeth -LastName Brunner -LicenseAssignment contoso:ENTERPRISEPREMIUM -PreferredDataLocation AUS
```

Als u meer wilt weten over het maken van nieuwe gebruikersaccounts en het vinden van LicenseAssignment-waarden in azure AD PowerShell, raadpleegt u [gebruikersaccounts maken met PowerShell](create-user-accounts-with-microsoft-365-powershell.md) en [licenties en services weergeven met PowerShell](view-licenses-and-services-with-microsoft-365-powershell.md).

> [!NOTE]
> Als u Exchange Online PowerShell gebruikt om een postvak in te schakelen en het postvak rechtstreeks moet maken op de geografische locatie die in **PreferredDataLocation** is opgegeven, moet u een cmdlet van Exchange Online gebruiken, zoals **inschakelen-postvak** of **Nieuw-postvak** rechtstreeks op de Cloud-service. Als u de **Enable-RemoteMailbox-** cmdlet in on-premises Exchange PowerShell gebruikt, wordt het postvak gemaakt in de centrale geo-locatie.

## <a name="onboard-existing-on-premises-mailboxes-in-a-specific-geo-location"></a>Bestaande on-premises postvakken in een specifieke geografische locatie opvullen

U kunt de standaardhulpprogramma's en [-](https://docs.microsoft.com/powershell/module/exchange/new-migrationbatch) processen voor onboarding gebruiken voor het migreren van een postvak vanuit een on-premises Exchange-organisatie naar Exchange Online, inclusief het [migratie dashboard in het](https://support.office.com/article/d164b35c-f624-4f83-ac58-b7cae96ab331)Exchange Online PowerShell.

De eerste stap bestaat uit het controleren van een gebruikersobject, en de juiste **PreferredDataLocation** waarde is geconfigureerd in azure AD. Met de hulpmiddelen voor onboarding wordt de **PreferredDataLocation** waarde bepaald en worden de postvakken direct naar de opgegeven geografische locatie gemigreerd.

U kunt ook de volgende stappen uitvoeren om postvakken rechtstreeks op te zetten op een specifieke geo-locatie met behulp van de [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/new-moverequest) -cmdlet in Exchange Online PowerShell.

1. Controleer of het gebruikersobject bestaat voor elk postvak en dat **PreferredDataLocation** is ingesteld op de gewenste waarde in azure AD. De waarde van **PreferredDataLocation** wordt gesynchroniseerd met het **MailboxRegion** -kenmerk van het bijbehorende e-mail gebruikersobject in Exchange Online.

2. Verbind rechtstreeks met de specifieke geografische locatie van de satelliet met de verbindings instructies van eerder in dit artikel.

3. In Exchange Online PowerShell slaat u de on-premises beheerdersreferenties op die wordt gebruikt om een migratie van een postvak in een variabele uit te voeren door de volgende opdracht uit te voeren:

   ```powershell
   $RC = Get-Credential
   ```

4. Maak in Exchange Online PowerShell een nieuwe **nieuwe MoveRequest** die vergelijkbaar is met het volgende voorbeeld:

   ```powershell
   New-MoveRequest -Remote -RemoteHostName mail.contoso.com -RemoteCredential $RC -Identity user@contoso.com -TargetDeliveryDomain <YourAppropriateDomain>
   ```

5. Herhaal stap #4 voor elk postvak dat u wilt migreren van on-premises Exchange naar de geografische locatie van de satelliet waarmee u momenteel bent verbonden.

6. Als u extra postvakken moet migreren naar verschillende geografische locaties, herhaalt u stappen 2 tot en met 4 voor elke specifieke locatie.

## <a name="multi-geo-reporting"></a>Meerdere geografische rapporten

Met de **rapporten voor meerdere geografische gebruik** in het microsoft 365-Beheercentrum wordt het aantal gebruikers per geo-locatie weergegeven. In het rapport wordt de distributie van gebruikers weergegeven voor de huidige maand en de historische gegevens voor de afgelopen zes maanden.

## <a name="see-also"></a>Zie ook

[Microsoft 365 beheren met PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
