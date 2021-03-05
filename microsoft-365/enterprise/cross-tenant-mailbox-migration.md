---
title: Migratie van postvakken tussen tenants
description: Postvakken verplaatsen tussen Microsoft 365- of Office 365-tenants.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: d81e272cfe50aa8379135406cbe538fbc8a18cb5
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454227"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migratie van postvakken tussen tenants (preview)

Voorheen, wanneer een Exchange Online-tenant postvakken moest verplaatsen naar een andere tenant in dezelfde Exchange Online-service, moesten ze deze volledig offboarden naar on-premises en ze vervolgens onboarden naar een nieuwe tenant. Met de nieuwe functie voor migratie van postvakken op verschillende tenants kunnen tenantbeheerders in zowel de bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen. Hiermee verwijdert u de noodzaak om postvakken aan de board- en onboard-app toe te laten.

Doorgaans moet u tijdens fusies of overnames gebruikers en inhoud naar een nieuwe tenant kunnen verplaatsen. Wanneer de beheerder van de doelten tenant de overstap uitvoert, heet dit een pull-move, vergelijkbaar met on-premises onboarding-migraties voor de cloud.

Exchange-postvakken op meerdere tenants worden volledig zelf gebruikt door tenantbeheerders, met behulp van bekende interfaces die kunnen worden geschreven in de grotere werkstromen die nodig zijn om gebruikers over te brengen naar de nieuwe organisatie. Beheerders kunnen de cmdlet, beschikbaar via de beheerrol Postvakken verplaatsen, gebruiken om het verplaatsen tussen `New-MigrationBatch` tenants uit te voeren. Het overstapproces omvat tenantautorisatiecontroles tijdens postvaksynchronisatie en -finalisatie. 
 
Gebruikers die migreren, moeten in de doelten tenant Exchange Online aanwezig zijn als MailUsers, gemarkeerd met specifieke kenmerken om het migreren tussen tenants mogelijk te maken. Het systeem mislukt voor gebruikers die niet correct zijn ingesteld in de doel-tenant.  

Wanneer de bewegingen zijn voltooid, wordt het bronsysteempostvak geconverteerd naar MailUser en wordt het targetAddress (weergegeven als ExternalEmailAddress in Exchange) voorzien van een stempel met het routeringsadres naar de doelten tenant. Met deze procedure wordt de oudere MailUser in de bronten tenant verlaat en bestaat er een periode van co-aanwezigheid en e-mailroutering. Wanneer bedrijfsprocessen zijn toegestaan, kan de bronten tenant MailUser verwijderen of converteren naar een e-mailcontactcontact. 

Migraties van Exchange-postvakken tussen tenants worden alleen ondersteund voor tenants in de hybride omgeving of in de cloud, of een combinatie van deze twee.

In dit artikel wordt het proces voor het verplaatsen van postvakken tussen tenants beschreven en vindt u richtlijnen voor het voorbereiden van de bron- en doelten tenants voor het verplaatsen van inhoud.  

## <a name="preparing-source-and-target-tenants"></a>Bron- en doelten tenants voorbereiden

Voor de migratiefunctie voor Exchange-postvakken tussen tenants zijn autorisatie en bereik voor migraties tussen tenants vereist. Met de Azure Enterprise-toepassing en Key Vault-opslagoplossingen kunnen tenantbeheerders nu zowel autorisatie als het beperken van migraties van Exchange Online-postvakken van de ene tenant naar de andere beheren. Bij het verplaatsen van postvakken tussen tenants wordt een uitnodiging en toestemmingsmodel ondersteund voor het maken van een Azure Active Directory-toepassing (Azure AD) die wordt gebruikt voor verificatie tussen een tenantpaar. Extra onderdelen, zoals een organisatierelatie en een migratie-eindpunt, zijn ook vereist.

Deze sectie bevat niet de specifieke stappen die nodig zijn voor het voorbereiden van de MailUser-gebruikersobjecten in de doelmap en bevat ook niet de voorbeeldopdracht om een migratiebatch in te dienen. Zie [Doelgebruikersobjecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.

## <a name="prerequisites"></a>Vereisten

Voor de functie voor het verplaatsen van postvakken tussen tenants moet [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) een tenantpaarsspecifieke Azure-toepassing tot stand brengen om het certificaat/geheim dat wordt gebruikt voor verificatie en geautoriseerde postvakmigratie van de ene tenant naar de andere veilig op te slaan en te openen, waardoor alle vereisten voor het delen van certificaten/geheimen tussen tenants worden verwijderd. 

Voordat u begint, moet u de benodigde machtigingen hebben om de implementatiescripts uit te voeren om Azure Key Vault, Move Mailbox-toepassing, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren. Doorgaans heeft een globale beheerder toestemming om alle configuratiestappen uit te voeren.

Bovendien zijn beveiligingsgroepen met e-mail in de bron tenant vereist voordat de installatie wordt uitgevoerd. Deze groepen worden gebruikt om een bereik op te geven in de lijst met postvakken die van de bronten tenant (of soms resourceten tenant genoemd) naar de doelten tenant kunnen worden verplaatst. Hierdoor kan de beheerder van de bronten tenant de specifieke set postvakken beperken of een bereik instellen dat moet worden verplaatst, zodat onbedoelde gebruikers niet kunnen worden gemigreerd. Geneste groepen worden niet ondersteund.

U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken gaat verplaatsen) om hun Microsoft 365-tenant-id te verkrijgen. Deze tenant-id wordt gebruikt in het veld `DomainName` Organisatierelatie.

Als u de tenant-id van een abonnement wilt verkrijgen, meld u zich aan bij het Microsoft 365-beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klik op het kopieerpictogram voor de eigenschap Tenant-id om deze naar het Klembord te kopiëren.

Dit proces werkt als eerste.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Tenant voorbereiden op de migratie van postvakken.":::

[Bekijk een grotere versie van deze afbeelding.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Tenants voorbereiden

Op hoog niveau vinden de volgende configuratieacties plaats bij het uitvoeren van de installatiescripts.

De doel tenant voorbereiden:

1. Als er geen bestaande Azure-resourcegroep wordt verstrekt, wordt er een nieuwe gemaakt (SCRIPT).
2. Als er geen bestaande Key Vault wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).
3. Er wordt een nieuw Access-beleid gemaakt voor de Office 365 Exchange Online Mailbox Migration-toepassing (SCRIPT).
4. Er wordt een nieuw certificaat gemaakt (of een bestaand certificaat, indien opgegeven) om het geheim van de migratietoepassing (SCRIPT) te bewaren.
5. Er wordt een nieuwe Azure AD-toepassing (SCRIPT) gemaakt.
6. Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).
7. Machtigingen voor postvakmigratie worden toegewezen aan de toepassing (SCRIPT).
8. Het implementatiescript wordt onderbroken totdat de doelbeheerder toestemming geeft voor de eigen toepassing (SCRIPT).
9. De doelten tenantbeheerder gaat akkoord met de machtigingen die aan de toepassing worden gegeven (MANUAL).
10. Er wordt een organisatierelatie gemaakt met de doel-tenant (SCRIPT).
11. Er wordt een migratie-eindpunt gemaakt om postvakken op te halen naar de doelten tenant (SCRIPT).

De bron tenant voorbereiden:

1. De bronten tenantbeheerder accepteert toestemming voor de uitnodiging voor de toepassing Postvakmigratie vanuit de doelten tenant (MANUAL).
2. De bronten tenantbeheerder maakt een beveiligingsgroep met e-mail in de tenant voor de lijst met postvakken die mogen worden verplaatst door de migratietoepassing (MANUAL).
3. Er wordt een organisatierelatie gemaakt met de doel tenant die opgeeft dat de postvakmigratietoepassing moet worden gebruikt voor OAuth-verificatie om de aanvraag voor verplaatsen (SCRIPT) te accepteren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Stapsgewijse instructies voor de doel tenantbeheerder

1. Download het SetupCrossTenantRelationshipForTargetTenant.ps1 voor het instellen van de doel tenant vanuit de [GitHub-opslagplaats.](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 
2. Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer op waaruit u het script wilt uitvoeren.
3. Maak een externe PowerShell-verbinding met de Exchange Online-doel tenant. Zorg er nogmaals voor dat u de benodigde machtigingen hebt om de implementatiescripts uit te voeren om de Azure Key Vault-opslag en -certificaat, de toepassing Move Mailbox, EXO Migration Endpoint en de EXO-organisatierelatie te configureren.
4. Wijzig de map met bestanden naar de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw externe PowerShell-sessie.
5. Voer het script uit met de volgende parameters en waarden.

    | Parameter | Value | Vereist of Optioneel
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Doel tenantdomein, zoals fabrikam \. onmicrosoft.com. | Vereist |
    | -ResourceTenantDomain                       | Bronten tenantdomein, zoals contoso \. onmicrosoft.com. | Vereist |
    | -ResourceTenantAdminEmail                   | Het e-mailadres van de beheerder van de bron tenant. Dit is de bronbeheerder van de tenant die instemt met het gebruik van de postvakmigratietoepassing die is verzonden door de doelbeheerder. Dit is de beheerder die de uitnodiging per e-mail voor de toepassing ontvangt. | Vereist |
    | -ResourceTenantId                           | Bron-tenant-organisatie-id (GUID). | Vereist |
    | -SubscriptionId                             | Het Azure-abonnement dat moet worden gebruikt voor het maken van bronnen. | Vereist |
    | -ResourceGroup                              | De naam van de Azure-resourcegroep die de Sleutel kluis bevat of deze bevat. | Vereist |
    | -KeyVaultName                               | Azure Key Vault-exemplaar dat het certificaat/geheim van uw postvakmigratietoepassing opgeslagen. | Vereist |
    | -CertificateName                            | De naam van het certificaat bij het genereren of zoeken naar certificaten in de Key Vault. | Vereist |
    | -CertificateSubject                         | Naam van het Azure Key Vault-certificaat, zoals CN=contoso_fabrikam. | Vereist |
    | -ExistingApplicationId                      | Te gebruiken e-mailmigratietoepassing als er al een is gemaakt. | Optioneel |
    | -AzureAppPermissions                        | De benodigde machtigingen voor het verlenen van machtigingen aan de postvakmigratietoepassing, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph om met deze toepassing een uitnodiging voor een toestemmingskoppeling naar de resourceten tenant te verzenden). | Vereist |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter voor het gebruik van de toepassing die is gemaakt voor migratie en die moet worden gebruikt voor het verzenden van uitnodigingen voor toestemmingskoppelingen naar de bron tenantbeheerder. Als deze niet aanwezig is, wordt gevraagd om de referenties van de doelbeheerder om verbinding te maken met Azure Invitation Manager en de uitnodiging te verzenden als doelbeheerder. | Optioneel |
    | -KeyVaultAuditStorageAccountName            | Het opslagaccount waar de auditlogboeken van Key Vault worden opgeslagen. | Optioneel |
    | -KeyVaultAuditStorageResourceGroup          | De resourcegroep met het opslagaccount voor het opslaan van auditlogboeken voor Key Vault. | Optioneel |
    ||||

    >[!Note]
    > Zorg ervoor dat u de Azure AD PowerShell-module hebt geïnstalleerd voordat u de scripts gaat uitvoeren. Raadpleeg hier ![ voor ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) installatiestappen

6. Het script wordt onderbroken en u wordt gevraagd de migratietoepassing voor Exchange-postvakken die tijdens dit proces is gemaakt, te accepteren of in te stemmen. Hier volgt een voorbeeld.

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. Er wordt een URL weergegeven in de externe PowerShell-sessie. Kopieer de verstrekte koppeling voor uw tenant toestemming en plak deze in een webbrowser.

8. Meld u aan met uw globale-beheerdersreferenties. Wanneer het volgende scherm wordt weergegeven, selecteert u **Accepteren.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialoogvenster Machtigingen accepteren":::

9. Ga terug naar de externe PowerShell-sessie en druk op Enter om verder te gaan.

10. De overige installatieobjecten worden door het script geconfigureerd. Hier volgt een voorbeeld.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

De configuratie van de doelbeheerder is nu voltooid.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Stapsgewijse instructies voor de bronbeheerder van de tenant

1.  Meld u aan bij uw postvak als de -ResourceTenantAdminEmail die is opgegeven door de doelbeheerder tijdens de installatie. Zoek de e-mailuitnodiging van de doelten tenant en selecteer vervolgens **de knop Aan de** slag.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialoogvenster U bent uitgenodigd":::

2. Selecteer **Accepteren om** de uitnodiging te accepteren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster voor het accepteren van machtigingen":::

   > [!NOTE]
   > Als u dit e-mailbericht niet ontvangt of niet kunt vinden, heeft de doel tenantbeheerder een rechtstreekse URL gekregen die u kan worden gegeven om de uitnodiging te accepteren. De URL moet in het afschrift van de externe PowerShell-sessie van de doel tenantbeheerder staan.

3. Maak in het Microsoft 365-beheercentrum of een externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om de lijst met postvakken te beheren die door de doelten tenant mogen worden gehaald (verplaatst) van de bronten tenant naar de doelten tenant. U hoeft deze groep niet van tevoren te vullen, maar er moet ten minste één groep zijn opgegeven om de installatiestappen (script) uit te voeren. Nest-groepen worden niet ondersteund. 

4. Download hier SetupCrossTenantRelationshipForResourceTenant.ps1 script voor het instellen van de bron tenant in de GitHub-opslagplaats: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) 

5. Maak een externe PowerShell-verbinding met de bronten tenant met uw Exchange-beheerdersmachtigingen. Globale beheerdersmachtigingen zijn niet vereist voor het configureren van de bronten tenant, alleen de doelten tenant vanwege het proces voor het maken van Azure-toepassingen.

6. Wijzig de map in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw externe PowerShell-sessie.

7. Voer het script uit met de volgende vereiste parameters en waarden.

    | Parameter | Value |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Beveiligingsgroep met e-mail die door de bronten tenant is gemaakt voor de identiteiten/postvakken die binnen het migratiebereik vallen. |
    | -ResourceTenantDomain | De domeinnaam van de bronten tenant, zoals contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure-toepassings-id (GUID) van de toepassing die voor de migratie wordt gebruikt. Toepassings-id beschikbaar via je Azure Portal (Azure AD, Enterprise-toepassingen, app-naam, toepassings-id) of opgenomen in je uitnodigingse-mail.  |
    | -TargetTenantDomain | De domeinnaam van de doel tenant, zoals fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Tenant-id van de doel-tenant. Bijvoorbeeld: de tenant-id van Azure AD van contoso \. onmicrosoft.com tenant. |
    |||

    Hier volgt een voorbeeld.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

De configuratie van de bronbeheerder is nu voltooid.

### <a name="verify-setup"></a>Installatie controleren

Controleer of de organisatierelaties in zowel de bron- als doelten tenants en het migratie-eindpunt in het doel goed zijn gemaakt.

#### <a name="target-tenant"></a>Doel tenant

**Organisatierelatie**

Controleer of het organisatierelatieobject met deze opdracht is gemaakt en geconfigureerd.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Hier is een voorbeeld:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Migratie-eindpunt**

Controleer of het migratie-eindpuntobject is gemaakt en geconfigureerd met deze opdracht.

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

Hier volgt een voorbeeld.

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a>Bron tenant

**Organisatierelatie**

Controleer of het organisatierelatieobject met deze opdracht is gemaakt en geconfigureerd.

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

Hier volgt een voorbeeld.

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a>Setup-script controleren

Als u fouten ziet tijdens de configuratie van de bron- of doelten tenants, kunt u het VerifySetup.ps1 uitvoeren in [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en de uitvoer controleren.

Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier is een voorbeeld van VerifySetup.ps1 de bron tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Postvakken terug verplaatsen naar de oorspronkelijke bron

Als een postvak wordt terug verplaatst naar de oorspronkelijke bronten tenant is vereist, moet dezelfde reeks stappen en scripts worden uitgevoerd in zowel nieuwe als nieuwe doelten tenants. Het bestaande object Organisatierelatie wordt bijgewerkt of toegevoegd, niet opnieuw gemaakt.

## <a name="prepare-target-user-objects-for-migration"></a>Doelgebruikersobjecten voorbereiden voor migratie

Gebruikers die migreren, moeten aanwezig zijn in de doelten tenant en het Exchange Online-systeem (als MailUsers) die zijn gemarkeerd met specifieke kenmerken om het migreren tussen tenants mogelijk te maken. Het systeem mislukt voor gebruikers die niet correct zijn ingesteld in de doel-tenant. In de volgende sectie worden de vereisten voor het MailUser-object voor de doelten tenant begegevens begegevens voor gesteld.

### <a name="prerequisites"></a>Vereisten
  
U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.  

1. Als een postvak uit een bronorganisatie wordt verplaatst, moet u een MailUser-object inrichten in de doelorganisatie: 

   - De doel-mailgebruiker moet deze kenmerken hebben uit het bronpostvak of zijn toegewezen aan het nieuwe gebruikersobject:
      - ExchangeGUID (directe stroom van bron naar doel) - De postvak-GUID moet overeenkomen. Het verplaatsproces gaat niet door als dit niet aanwezig is in het doelobject. 
      - ArchiveGUID (directe stroom van bron naar doel) - De archief-GUID moet overeenkomen. Het verplaatsproces gaat niet door als dit niet aanwezig is in het doelobject. (Dit is alleen vereist als archief is ingeschakeld voor het bronpostvak). 
      - LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress. De overstapprocessen gaan niet door als dit niet aanwezig is in het doelobject. 
      - UserPrincipalName: de UPN komt overeen met de NIEUWE identiteit of het doelbedrijf van de gebruiker (bijvoorbeeld user@northwindtraders.onmicrosoft.com). 
      - Primair SMTP-adres: het primaire SMTP-adres wordt afgestemd op het NIEUWE bedrijf van de gebruiker (bijvoorbeeld user@northwind.com). 
      - TargetAddress/ExternalEmailAddress: MailUser verwijst naar het huidige postvak van de gebruiker dat wordt gehost in de bronten tenant (bijvoorbeeld user@contoso.onmicrosoft.com). Wanneer u deze waarde toewijst, controleert u of u primarySMTPAddress hebt of toewijst, anders wordt met deze waarde het PrimarySMTPAddress ingesteld, waardoor fouten in het verplaatsen optreden. 
      - U kunt geen oudere SMTP-proxyadressen uit het bronpostvak toevoegen aan de e-mailuser. Zo kunt u bijvoorbeeld geen contoso.com in de fabrikam.onmicrosoft.com tenantobjecten). Domeinen zijn alleen gekoppeld aan één Azure AD- of Exchange Online-tenant.
 
     Voorbeeld **van een** MailUser-object:
 
     | Attribuut             | Value                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     Voorbeeld **van het postvakobject:**

     | Attribuut             | Value                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | LaraN                                                                    |
     | RecipientType         | UserMailbox                                                              |
     | RecipientTypeDetails  | UserMailbox                                                              |
     | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
     | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  |
     | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
     |                       | SMTP:Lara.Newton@contoso.com          |
     |||

   - Er kunnen al aanvullende kenmerken zijn opgenomen in exchange hybrid write back. Zo niet, dan moeten deze worden opgenomen. 
   - msExchBlockedSendersHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.
   - msExchSafeRecipientsHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.
   - msExchSafeSendersHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.

2. Als het bronpostvak litigationhold is en het bronpostvak Herstelbare items groter is dan de standaarddatabase (30 GB), worden de items niet verplaatst omdat het doelquotum kleiner is dan de grootte van het bronpostvak. U kunt het doelobject MailUser bijwerken om de ELC-postvakvlaggen van de bronomgeving over te brengen naar de doelomgeving, waardoor het doelsysteem het quotum voor MailUser uitbreidt naar 100 GB, zodat de gebruiker naar de doelomgeving kan worden verplaatst. Deze instructies werken alleen voor hybride identiteiten met Azure AD Connect, omdat de opdrachten om de ELC-vlaggen te stempelen niet worden getoond aan tenantbeheerders.

    >[!Note]
    > VOORBEELD: ZOALS HET IS, GEEN GARANTIE<br/>Dit script gaat uit van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory (om het ADUser-object van een stempel te voorzien). Als voor de bron herstel van rechtszaken of herstel van één item is ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Niet-hybride doelten tenants kunnen het quotum voor de map Herstelbare items voor de MailUsers wijzigen vóór de migratie door de volgende opdracht uit te voeren om het in-en uit te voeren voor het in- en uit wacht plaatsen van postorders voor het MailUser-object en het quotum te verhogen naar 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` GB: Houd er rekening mee dat dit niet werkt voor tenants in hybride omgevingen.

4. Gebruikers in de doelorganisatie moeten een licentie hebben voor de juiste Exchange Online-abonnementen die van toepassing zijn op de organisatie. U kunt een licentie toepassen op voor de overstap van een postvak, maar ALLEEN wanneer de doel-MailUser correct is ingesteld met ExchangeGUID- en proxyadressen. Wanneer een licentie wordt toegepast voordat ExchangeGUID wordt toegepast, wordt een nieuw postvak ingericht in de doelorganisatie. 

    > [!Note]
    > Wanneer u een licentie op een Postvak- of MailUser-object aanvraagt, worden alle SMTP-proxyAddresses van het SMTP-type geconvergeerd, zodat alleen geverifieerde domeinen worden opgenomen in de matrix Exchange EmailAddresses. 

5. U moet ervoor zorgen dat de doel-MailUser geen exchangeguid heeft die niet overeen komt met bron-ExchangeGuid. Dit kan gebeuren als de doel-mail-mail-gebruiker eerder een licentie voor Exchange Online had en een postvak heeft ingericht. Als de doel-MailUser eerder een licentie had voor of een ExchangeGuid had die niet overeen komt met bron-ExchangeGuid, moet u de cloud-e-mail opschonen. Voor deze cloud-me-meus kunt u `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Dit proces is onomkeerbaar. Als het object een softDeleted-postvak heeft, kan het na dit punt niet meer worden hersteld. Als ze zijn gewuit, kunt u de juiste ExchangeGuid echter synchroniseren met het doelobject, zodat MRS het bronpostvak verbindt met het nieuwe doelpostvak. (Reference EHLO blog on the new parameter.)  

    Met deze opdracht kunt u objecten zoeken die eerder postvakken waren.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    Hier volgt een voorbeeld. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Met deze opdracht kunt u het snel verwijderde postvak wissen.

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    Hier volgt een voorbeeld.

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a>Postvakmigraties uitvoeren

Migraties van Exchange-postvakken tussen tenants worden ingediend als migratiebatchs die worden gestart vanuit de doelten tenant. Dit is vergelijkbaar met de manier waarop migratiebatch's tijdens het overstappen van Exchange on-premises naar Microsoft 365 werken. 

### <a name="create-migration-batches"></a>Migratiebatch's maken

Hier is een voorbeeld van een cmdlet met een migratiebatch voor het starten van moves.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Het e-mailadres in het CSV-bestand moet het adres zijn dat is opgegeven in de doel tenant, niet de bron-tenant.

Het indienen van migratiebatch wordt ook ondersteund vanuit het nieuwe Exchange-beheercentrum bij het selecteren van de optie voor meerdere tenants.

#### <a name="update-on-premises-mailusers"></a>On-premises MailUsers bijwerken

Nadat het postvak is verplaatst van bron naar doel, moet u ervoor zorgen dat de on-premises e-mailgebruikers, zowel Bron als doel, worden bijgewerkt met het nieuwe targetAddress. In de voorbeelden wordt targetDeliveryDomain gebruikt in de move **contoso.onmicrosoft.com.** Werk de e-mailgebruikers bij met dit targetAddress.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Moeten RemoteMailboxes in de bron on-premises na de overstap worden bijgewerkt?**

Ja, u moet het targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de on-premises brongebruikers bijwerken wanneer het brontenderpostvak wordt verplaatst naar de doelten tenant.  Hoewel e-mailroutering de verwijzingen kan volgen tussen meerdere e-mailgebruikers met verschillende targetAddresses, moeten de zoekactie voor vrij/bezet voor e-mailgebruikers zijn gericht op de locatie van de postvakgebruiker. Zoekactie voor vrij/bezet zit niet achter meerdere omleidingen. 

**Wordt de inhoud van de Teams-chatmap gemigreerd tussen tenants?**  

Nee, de inhoud van de Teams-chatmap migreert niet tussen tenants.  

**Hoe kan ik alleen moves zien die zich tussen tenants bewegen, niet mijn onboarding- en off-boarding moves?**

Gebruik de `-flags` parameter. Hier volgt een voorbeeld.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Kunt u voorbeeldscripts geven voor het kopiëren van kenmerken die worden gebruikt bij het testen?**

> [!Note]
> VOORBEELD: ZOALS HET IS, GEEN GARANTIE<br/>Dit script gaat uit van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory Domain Services (om het ADUser-object te stempelen). Als voor de bron herstel van rechtszaken of herstel van één item is ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
**Hoe krijgen we toegang tot Outlook op dag 1 nadat het postvak voor gebruik is verplaatst?**

Aangezien slechts één tenant eigenaar kan zijn van een domein, wordt het voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doelten tenant wanneer het verplaatsen van het postvak is voltooid. alleen de domeinen die aan de nieuwe tenant zijn gekoppeld. Outlook gebruikt de nieuwe UPN-gebruikers om zich te verifiëren bij de service en het Outlook-profiel verwacht dat het oude primaire SMTPAddress zal overeenkomen met het postvak in het doelsysteem. Aangezien het oude adres niet in het doelsysteem staat, wordt er geen verbinding gemaakt met het Outlook-profiel om het zojuist verplaatste postvak te vinden. 

Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN-adres, primaire SMTP-adres en opnieuw synchroniseren van OST-inhoud. 

> [!Note]
> Plan dienovereenkomstig terwijl u uw gebruikers batcht voor voltooiing. U moet rekening houden met het netwerkgebruik en de capaciteit wanneer Outlook-clientprofielen worden gemaakt en de volgende OST- en OAB-bestanden worden gedownload naar clients. 
 
**Van welke Exchange-rollen voor RBAC moet ik lid zijn om een overstap tussen tenants in te stellen of te voltooien?**
 
Er is een matrix van rollen die zijn gebaseerd op aanname van gedelegeerde taken bij het uitvoeren van de overstap van een postvak. Op dit moment zijn twee rollen vereist:  

- De eerste rol is voor een een tijdsinstellingstaak die de autorisatie bepaalt voor het verplaatsen van inhoud naar of buiten de organisatiegrens van de tenant of organisatie. Omdat het uit de organisatie halen van gegevens een zeer belangrijke taak is voor alle bedrijven, hebben we gekozen voor de meest toegewezen rol van Organisatiebeheerder (OrgAdmin). Deze rol moet een nieuwe OrganizationRelationship wijzigen of instellen die definieert -MailboxMoveCapability met de externe organisatie. Alleen OrgAdmin kan de instelling MailboxMoveCapability wijzigen, terwijl andere kenmerken van OrganizationRelationhip kunnen worden beheerd door de beheerder van Federatief delen. 
 
- De rol van het uitvoeren van de feitelijke opdrachten voor verplaatsen kan worden gedelegeerd aan een functie op lager niveau. De rol van Postvakken verplaatsen wordt toegewezen aan de mogelijkheid postvakken in of uit de organisatie te verplaatsen met behulp van de `-RemoteTenant` parameter.  

**Hoe richten we ons op het GESELECTEERDE SMTP-adres voor targetAddress (TargetDeliveryDomain) voor het geconverteerde postvak (naar mailuser-conversie)?**
 
Exchange-postvak wordt verplaatst door gebruik te maken van MRS- het targetAddress voor het oorspronkelijke bronpostvak wanneer het wordt ge converteerd naar een MailUser door een e-mailadres (proxyAddress) op het doelobject te koppelen. Tijdens het proces wordt de waarde -TargetDeliveryDomain doorgegeven in de opdracht Verplaatsen en wordt vervolgens gecontroleerd op een overeenkomende proxy voor dat domein aan de doelzijde. Wanneer we een overeenkomst vinden, wordt het overeenkomende proxyAddress gebruikt om het object ExternalEmailAddress (targetAddress) in te stellen voor het geconverteerde postvak (nu MailUser).
 
**Hoe worden postvakmachtigingen overstappen?**

Postvakmachtigingen zijn Verzenden namens en Postvaktoegang: 

- Met Verzenden namens (AD:publicDelegates) wordt de DN opgeslagen van geadresseerden die als gemachtigde toegang hebben tot het postvak van een gebruiker. Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de postvakovergang. Als publicDelegates is ingesteld voor het bronpostvak, moet u de restamp van de publicDelegates op het doelpostvak opnieuw instellen nadat de conversie van de gebruiker met gebruikers met gebruikers met postvak is voltooid in de doelomgeving door de ingebouwde postvakconversie uit te `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` zetten. 
 
- Postvakmachtigingen die zijn opgeslagen in het postvak worden samen met het postvak verplaatst wanneer zowel de principal als de gedelegeerde naar het doelsysteem worden verplaatst. Zo krijgt de gebruiker TestUser_7 FullAccess aan de postvakgegevens TestUser_8 in de tenant SourceCompany.onmicrosoft.com. Nadat het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doelmap. Voorbeelden waarin *Gebruik wordt gemaakt van Get-MailboxPermission* TestUser_7 in zowel de bron- als doelten tenants worden hieronder weergegeven. Exchange-cmdlets worden vooraf vooraf laten gaan door bron en doel. 
 
Hier is een voorbeeld van de uitvoer van de postvakmachtiging voor een overstap. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier is een voorbeeld van de uitvoer van de postvakmachtiging na de overstap. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Postvak- en agendamachtigingen tussen tenants worden NIET ondersteund. U moet principals en gedelegeerden organiseren in de samengevoegde move batches, zodat deze verbonden postvakken op hetzelfde moment vanuit de bronten tenant worden overgeslagen. 

**Welke X500-proxy moet worden toegevoegd aan de doelproxyadressen van MailUser om migratie in teschakelen?**  

Voor de migratie van postvakken tussen tenants moet de LegacyExchangeDN-waarde van het bronpostvakobject worden voorzien van een stempel als een x500-e-mailadres op het doelobject MailUser.  

Voorbeeld:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Naast deze X500-proxy moet u alle X500-proxy's uit het postvak in de bron kopiëren naar het postvak in de doelserver.  

**Waar kan ik problemen oplossen als het niet werkt?**  

Begin met het uitvoeren VerifySetup.ps1 script op [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en controleer de uitvoer.

Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier is een eExample van het uitvoeren VerifySetup.ps1 op de bron tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kunnen de bron- en doel tenant dezelfde domeinnaam gebruiken?**  

Nee. De domeinnamen van de bron- en doel tenant moeten uniek zijn. Bijvoorbeeld een brondomein van contoso.com en het doeldomein van fourthcoffee.com.

**Worden gedeelde postvakken verplaatst en werken ze nog steeds?**

Ja, maar we behouden alleen de store-machtigingen zoals beschreven in deze artikelen:

- [Microsoft Docs | Machtigingen voor geadresseerden beheren in Exchange Online](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | Exchange- en Outlook-postvakmachtigingen verlenen in Office 365 Dedicated](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Is Azure Key Vault vereist en wanneer worden transacties uitgevoerd?**  

Ja, een Azure-abonnement is vereist om Key Vault te gebruiken voor het opslaan van het certificaat om migratie te autor toen dit werd geautoriseerd. In tegenstelling tot onboarding-migraties, waarbij gebruikersnaam & wachtwoord wordt gebruikt voor verificatie bij de bron, maken migraties van postvakken tussen tenants gebruik van OAuth en dit certificaat als het geheim of de referenties. Toegang tot de Key Vault moet worden behouden in alle postvakmigraties, aangezien deze eenmaal aan het begin en het einde van de migratie wordt gebruikt, en ook eenmaal per 24 uur tijdens incrementele synchronisatietijden. U kunt de kostendetails van AKV hier [bekijken.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)  

**Hebt u aanbevelingen voor batches?**  

Niet meer dan 2000 postvakken per batch. We raden u ten zeerste aan batches twee weken vóór de cut-over datum in te dienen, aangezien dit geen gevolgen heeft voor de eindgebruikers tijdens de synchronisatie. Als u richtlijnen nodig hebt voor postvakken met een hoeveelheid van meer dan 50.000, kunt u contact op met de distributielijst voor technische feedback op crosstenantmigrationpreview@service.microsoft.com.

**Wat moet ik doen als ik Serviceversleuteling gebruik met de klantsleutel?**

Het postvak wordt ontsleuteld voordat u het verplaatst. Zorg ervoor dat de klantsleutel in de doel-tenant is geconfigureerd als deze nog steeds vereist is. Zie [hier](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) voor meer informatie.  

**Wat is de geschatte migratietijd?**

Om u te helpen bij [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) het plannen van de migratie, bevat de onderstaande tabel de richtlijnen voor het voltooien van bulkpostvakken of afzonderlijke migraties. Deze schattingen zijn gebaseerd op een gegevensanalyse van eerdere klantmigraties. Omdat elke omgeving uniek is, kan de exacte migratiesnelheid variëren.  

Houd er wel aan dat deze functie momenteel wordt weergegeven als preview en in de SLA en dat de toepasselijke serviceniveaus niet van toepassing zijn op prestatie- of beschikbaarheidsproblemen tijdens de preview-status van deze functie.

## <a name="known-issues"></a>Bekende problemen  

-  **Probleem: Automatisch uitvbreed archieven kunnen niet worden gemigreerd.** De migratiefunctie voor verschillende tenants ondersteunt migraties van het primaire postvak en archiefpostvak voor een specifieke gebruiker. Als de gebruiker in de bron echter een automatisch uit breiden archief heeft, dat wil zeggen meer dan één archiefpostvak, kan de functie de extra archieven niet migreren en mislukt deze.

- **Probleem: Cloud MailUsers met smtp-proxyAddress van niet-eigendom, blokkeren MRS verplaatst de achtergrond.** Bij het maken van mailUser-objecten voor de doelten tenant moet u ervoor zorgen dat alle SMTP-proxyadressen deel uitmaken van de doelten tenantorganisatie. Als er een SMTP-proxyAddress bestaat voor de doel-e-mailgebruiker die geen deel uitmaken van de lokale tenant, wordt de conversie van MailUser naar Mailbox voorkomen. Dit komt doordat we er zeker van zijn dat postvakobjecten alleen e-mail kunnen verzenden van domeinen waarvoor de tenant gezaghebbend is (domeinen die door de tenant worden geclaimd): 

   - Wanneer u gebruikers synchroniseert vanuit een on-premises omgeving met behulp van Azure AD Connect, inrichting van on-premises MailUser-objecten waarbij ExternalEmailAddress verwijst naar de bronten tenant waarin het postvak bestaat (laran@contoso.onmicrosoft.com) en u het PrimarySMTPAddress stempelt als een domein dat zich in de doelten tenant (Lara.Newton@northwind.com) bevindt. Deze waarden worden gesynchroniseerd naar de tenant en een geschikte e-mailgebruiker wordt ingericht en klaar voor migratie. Hier wordt een voorbeeldobject weergegeven.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Het *contoso.onmicrosoft.com* adres is *niet aanwezig* in de matrix EmailAddresses/proxyAddresses.

- **Probleem: MailUser-objecten met 'externe' primaire SMTP-adressen worden gewijzigd/ opnieuw ingesteld op 'interne' geclaimde domeinen van het bedrijf**

   MailUser-objecten zijn pointers naar niet-lokale postvakken. In het geval van migraties van postvakken tussen tenants gebruiken we MailUser-objecten om het bronpostvak (vanuit het perspectief van de doelorganisatie) of het doelpostvak (vanuit het perspectief van de bronorganisatie) voor te stellen. De MailUsers hebben een ExternalEmailAddress (targetAddress) die wijst naar het SMTP-adres van het werkelijke postvak (ProxyTest@fabrikam.onmicrosoft.com) en primarySMTP-adres dat het weergegeven SMTP-adres van de postvakgebruiker in de adreslijst vertegenwoordigt. Sommige organisaties kiezen ervoor om het primaire SMTP-adres weer te geven als een extern SMTP-adres, niet als een adres dat eigendom is van of is geverifieerd door de lokale tenant (zoals fabrikam.com in plaats van als contoso.com).  Wanneer echter een object van een Exchange-serviceplan is toegepast op MailUser via licentiebewerkingen, wordt het primaire SMTP-adres gewijzigd, zodat het wordt gebruikt als een domein dat is geverifieerd door de lokale organisatie (contoso.com). Er zijn twee mogelijke redenen:
   
   - Wanneer een Exchange-serviceplan wordt toegepast op een MailUser, wordt tijdens het Azure AD-proces proxyvernieuwing gestart om ervoor te zorgen dat de lokale organisatie geen e-mail kan verzenden, spoofing of e-mail vanuit een andere tenant kan verzenden. SMTP-adressen op een object van een ontvanger met deze serviceplannen worden verwijderd als het adres niet wordt geverifieerd door de lokale organisatie. Zoals in het voorbeeld het geval is, wordt het Fabikam.com NIET geverifieerd door de contoso.onmicrosoft.com-tenant, dus wordt dat domein door de fabrikam.com verwijderd. Als u dit externe domein wilt blijven gebruiken in MailUser, vóór de migratie of na de migratie, moet u uw migratieprocessen wijzigen in het gebruik van licenties nadat de overstap is voltooid of vóór de overstap om ervoor te zorgen dat de verwachte externe huisstijl is toegepast op de gebruikers. U moet ervoor zorgen dat het postvakobject een juiste licentie heeft, zodat dit geen gevolgen heeft voor de e-mailservice.<br/><br/>Hier wordt een voorbeeldscript weergegeven voor het verwijderen van de serviceplannen voor een MailUser in Contoso.onmicrosoft.com tenant.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Resultaten in de set serviceplannen die is toegewezen, worden hier weergegeven.

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       Het PrimarySMTPAddress van de gebruiker wordt niet meer gekapt. Het fabrikam.com domein is niet eigendom van de contoso.onmicrosoft.com-tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.

       Hier volgt een voorbeeld.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Als msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), worden voor on-premises MailUsers die naar de doeltenant worden gemigreerd, door proxyverzendenlogica in Azure niet-eigen domeinen verwijderd en wordt het primarySMTP opnieuw ingesteld op een domein dat eigendom is. Door het wissen van msExchRemoteRecipientType in de on-premises MailUser, is de proxy scrub-logica niet meer van toepassing. <br/><br>Hieronder vindt u de volledige set mogelijke serviceplannen met Exchange Online.

   | Naam                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery-opslag (500 GB)               |
   | Klanten-lockbox                                  |
   | Preventie van gegevensverlies                              |
   | Exchange Enterprise CAL Services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (Abonnement 1)                          |
   | Exchange Online (Abonnement 2)                          |
   | Exchange Online Archiving voor Exchange Online     |
   | Exchange Online Archiving voor Exchange Server     |
   | Inactieve gebruikersinvoegvoeging in Exchange Online              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Abonnement 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | Informatiebarrières                              |
   | Information Protection voor Office 365 - Premium   |
   | Information Protection voor Office 365 - Standard  |
   | Inzichten van MyAnalytics                           |
   | Geavanceerde controle van Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (volledig)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender voor Office 365 (abonnement 1)    |
   | Microsoft Defender voor Office 365 (abonnement 2)    |
   | Office 365 Privileged Access Management           |
   | Premium-versleuteling in Office 365                  |
    
