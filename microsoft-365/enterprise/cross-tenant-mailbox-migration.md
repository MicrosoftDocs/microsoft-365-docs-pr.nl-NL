---
title: Migratie van postvakken tussen tenants
description: Postvakken verplaatsen tussen Microsoft 365-of Office 365-tenants.
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
ms.openlocfilehash: 63eab8c44651bfc2865e9bf6c577c1ebe13381fc
ms.sourcegitcommit: 21b0ea5715e20b4ab13719eb18c97fadb49b563d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49624764"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migratie van cross-Tenant postvak (preview)

Eerder, wanneer een Exchange Online-Tenant nodig heeft om postvakken te verplaatsen naar een andere Tenant in dezelfde Exchange Online-service, moeten ze ze volledig verwijderen naar on-premises en ze vervolgens op een nieuwe Tenant plaatsen. Met de nieuwe functie voor het migreren van postvakken kunnen tenantbeheerders van de bron-en doel tenants postvakken verplaatsen tussen de tenants met minimale infrastructuur afhankelijkheden in hun on-premises systemen. Hiermee verwijdert u de postvakken die u niet nodig hebt.

Voor de samenvoeging of divestitures hebt u meestal de mogelijkheid om gebruikers en inhoud te verplaatsen naar een nieuwe Tenant. Wanneer de doel tenantbeheerder de verhuizing uitvoert, wordt de overstap een pull-verhuizing genoemd, vergelijkbaar met de on-premises voor de Cloud onboarding-migraties.

Cross-Tenant Exchange postvak verplaatste wordt volledig selfservice voor tenantbeheerders, met behulp van bekende interfaces die scripts kunnen worden omgezet in de grotere werkstromen die nodig zijn om gebruikers over te dragen aan hun nieuwe organisatie. Beheerders kunnen de `New-MigrationBatch` cmdlet gebruiken, die beschikbaar is via de beheerfunctie postvakken verplaatsen, om cross-tenants te verplaatsen. Het verplaatsings proces omvat Tenant autorisatie controles tijdens het synchroniseren van uw e-mail en voltooien. 
 
Gebruikers die worden gemigreerd, moeten presenteren in het doel Tenant Exchange Online systeem als e-gebruikers, gemarkeerd met specifieke kenmerken om het verplaatsen van de cross-Tenant te activeren. Het systeem gaat niet naar gebruikers die niet correct zijn ingesteld in de doel Tenant.  

Wanneer de verhuizingen zijn voltooid, wordt het postvak van het bronsysteem geconverteerd naar mail-gebruiker en wordt het targetAddress (weergegeven als ExternalEmailAddress in Exchange) voorzien van een stempel met het routerings adres voor de doel Tenant. Hiermee laat u de oude e-mail gebruiker in de bron Tenant overstappen, en kunt u gedurende een bepaalde periode voor het samenwerken van e-mailberichten en e-mail routering. Wanneer bedrijfsprocessen zijn toegestaan, kan de bron Tenant de bron-mail gebruiker verwijderen of deze converteren naar een e-mail contactpersoon. 

Migraties van Exchange-postvak voor meerdere tenants worden ondersteund voor tenants in hybride of Cloud, of een willekeurige combinatie van beide.

In dit artikel wordt het proces beschreven voor het doorsturen van berichten via meerdere tenants en vindt u informatie over het voorbereiden van bron-en doel tenants voor de verhuizing van inhoud.  

## <a name="preparing-source-and-target-tenants"></a>Bron-en doel tenants voorbereiden

Voor de migratie functie voor het cross-Tenant Exchange-postvak is autorisatie en scope vereist voor migraties van cross tenants. Met de implementatie van de Azure Enterprise-toepassing en de belangrijkste oplossingen voor de opslag van een archief met grote en grote archieven kunnen tenantbeheerders de autorisatie en het bereik van Exchange Online-postvak migraties van de ene Tenant naar een andere beheren. Het postvak voor de ondersteuning van cross-tenants biedt ondersteuning voor het maken van een verzoek om Azure Active Directory (Azure AD) voor verificatie tussen een Tenant paar. Er zijn ook extra onderdelen, zoals een organisatie relatie en een migratie-eindpunt vereist.

In deze sectie vindt u niet de specifieke stappen die nodig zijn voor het voorbereiden van de gebruikersobjecten van de gebruiker in de doeldirectory, noch de optie voorbeeld van het verzenden van een migratie batch. Zie [doelgebruikers objecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.

## <a name="prerequisites"></a>Vereisten

Voor de functie voor het verplaatsen van het postvak in van de cross-Tenant is [Azure Key](https://docs.microsoft.com/azure/key-vault/basic-concepts) Secret vereist om een voor de Tenant gekoppelde Azure-toepassing te zorgen voor het veilig opslaan en openen van het certificaat dat wordt gebruikt voor de verificatie van en de migratie van postvakken van de ene Tenant naar de andere. 

Voordat u begint, controleert u of u de benodigde machtigingen hebt voor het uitvoeren van de implementatiescripts om Azure-sleutel kluis te configureren, Postvak toepassing te verplaatsen, EXO-migratie-eindpunt en de EXO-organisatie relatie. Een globale beheerder heeft meestal de machtiging alle configuratiestappen uit te voeren.

Daarnaast zijn er ook beveiligingsgroepen met e-mail in de bron Tenant vereist voordat u Setup uitvoert. Deze groepen worden gebruikt voor het bereik van de lijst met postvakken die vanuit de bron (of soms ook resource genoemd) kunnen worden verplaatst naar de doel Tenant. Hierdoor kan de tenantbeheerder de specifieke set postvakken die moeten worden verplaatst, beperken of bereiken, zodat onbedoelde gebruikers niet worden gemigreerd. Geneste groepen worden niet ondersteund.

U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken gaat verplaatsen) om de Microsoft 365-Tenant-ID te verkrijgen. Deze Tenant-ID wordt gebruikt in het veldrelatie tussen organisaties `DomainName` .

Als u de Tenant-ID van een abonnement wilt verkrijgen, meldt u zich aan bij het Microsoft 365-Beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klik op het Kopieer pictogram voor de eigenschap Tenant-ID om dit naar het Klembord te kopiëren.

Dit is de werking van het proces.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Tenant voorbereiding voor migratie van postvakken.":::

[Bekijk een grotere versie van deze afbeelding](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a>Tenants voorbereiden

Op een hoog niveau worden de volgende configuratieacties uitgevoerd tijdens het uitvoeren van de installatiescripts.

De doel Tenant voorbereiden:

1. Als er geen bestaande Azure-resource groep wordt opgegeven, wordt een nieuwe groep gemaakt (SCRIPT).
2. Als er geen bestaande sleutel kluis wordt opgegeven, wordt er een nieuwe sleutel gemaakt (SCRIPT).
3. Er wordt een nieuw toegangsbeleid gemaakt voor de Office 365 Exchange Online Mailbox Migration Application (SCRIPT).
4. Er wordt een nieuw certificaat gemaakt (of een bestaande, indien opgegeven), om het geheim te houden voor de migratietoepassing (SCRIPT).
5. Er is een nieuwe Azure AD-toepassing gemaakt (SCRIPT).
6. Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).
7. Machtigingen voor migratie van postvakken zijn toegewezen aan de toepassing (SCRIPT).
8. Het implementatiescript wordt onderbroken totdat de doel beheerder de eigen toepassing (SCRIPT) heeft doorgestuurd.
9. De doel tenantbeheerder verzendt de machtigingen die aan de toepassing zijn toegewezen (handmatig).
10. Er is een organisatie relatie gemaakt met de doel Tenant (SCRIPT).
11. Er wordt een migratie-eindpunt gemaakt om postvakken te verzamelen in de doel Tenant (SCRIPT).

De bron Tenant voorbereiden:

1. De bron tenantbeheerder accepteert toestemming voor de uitnodiging voor de migratietoepassing van een postvak via de doel Tenant (handmatig).
2. Met de bron tenantbeheerder maakt u een beveiligingsgroep met een e-mail functie in de Tenant, zodat deze de lijst met postvakken mag bevatten die door de migratietoepassing mag worden verplaatst (handmatig).
3. Er wordt een organisatie relatie gemaakt met de doel Tenant die de migratietoepassing voor postvakken voor de migratie van postvakken moet gebruiken om de verplaatsingsaanvraag te accepteren (SCRIPT).

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Stapsgewijze instructies voor de doel tenantbeheerder

1. Download het SetupCrossTenantRelationshipForTargetTenant.ps1-script voor de instellingen van de doel Tenant in de [github-bibliotheek](https://github.com/microsoft/cross-tenant/releases/tag/Preview). 
2. Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer op waar u het script wilt uitvoeren.
3. Maak een externe PowerShell-verbinding met de doel Tenant van Exchange Online. Zorg er ook voor dat u over de benodigde machtigingen beschikt om de implementatiescripts uit te voeren om de opslag en het certificaat van de Azure-sleutel kluis te kunnen configureren, Postvak toepassing, migratie-eindpunt EXO en de EXO-organisatie relatie.
4. Wijzig de map met de bestands map in de naam van het script of Controleer of het script momenteel is opgeslagen op de locatie die u in de externe PowerShell-sessie hebt opgeslagen.
5. Voer het script uit met de volgende parameters en waarden.

    | Tabelwaardeparameter | Value | Vereist of optioneel
    |---------------------------------------------|-----------------|--------------|
    | -ResourceTenantDomain                       | Bron Tenant domein, bijvoorbeeld fabrikam.onmicrosoft.com. | Vereist |
    | -ResourceTenantAdminEmail                   | E-mailadres van de bron tenantbeheerder. Dit is de bron tenantbeheerder die wordt doorgestuurd naar het gebruik van de migratietoepassing voor postvakken die van de doel beheerder is verzonden. De beheerder die de e-mail uitnodiging voor de toepassing ontvangt. | Vereist |
    | -TargetTenantDomain                         | Het doel Tenant domein, bijvoorbeeld contoso.onmicrosoft.com. | Vereist |
    | -ResourceTenantId                           | Bron Tenant-ID (GUID). | Vereist |
    | -SubscriptionId                             | Het Azure-abonnement dat moet worden gebruikt voor het maken van bronnen. | Vereist |
    | -ResourceGroup                              | Naam van Azure-resourcegroep die de sleutel kluis bevat of bevat. | Vereist |
    | -De kluizen                               | Azure Key Secret-exemplaar waarin het certificaat voor de migratietoepassing van uw postvak wordt opgeslagen. | Vereist |
    | -Certificaatpad                            | Certificaatnaam bij het genereren van of zoeken naar een certificaat in de sleutel kluis. | Vereist |
    | -CertificateSubject                         | Naam van onderwerp van Azure-sleutel kluis certificaat, zoals CN = contoso_fabrikam. | Vereist |
    | -ExistingApplicationId                      | De e-mail migratietoepassing die moet worden gebruikt als er al een is gemaakt. | Optioneel |
    | -AzureAppPermissions                        | De machtigingen die u nodig hebt voor de migratietoepassing voor het postvak, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph voor het gebruik van deze toepassing om een uitnodiging te verzenden aan de Tenant). | Vereist |
    | -UseAppAndCertGeneratedForSendingInvitation | De parameter voor het gebruik van de toepassing die is gemaakt voor de migratie die moet worden gebruikt voor het verzenden van een uitnodiging voor de koppeling naar de bron Tenant. Als dit niet het geval is, wordt u gevraagd om de referenties van de doel beheerder verbinding te maken met Azure uitnodiging Manager en de uitnodiging te verzenden als doel beheerder. | Optioneel |
    | -KeyVaultAuditStorageAccountName            | Het opslagaccount waar de auditlogboeken van belangrijke kluizen zijn opgeslagen. | Optioneel |
    | -KeyVaultAuditStorageResourceGroup          | De resourcegroep die het opslagaccount bevat voor het opslaan van belangrijke auditlogboeken. | Optioneel |
    ||||

    >[!Note]
    > Controleer of u de Azure AD PowerShell-module hebt geïnstalleerd voordat u de scripts uitvoert. Kijk ![ hier voor de ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) installatiestappen

6. Het script wordt onderbroken en u vraagt of u de migratietoepassing voor Exchange-postvakken die u tijdens dit proces hebt gemaakt, moet accepteren of u ermee akkoord te gaan. Hier volgt een voorbeeld.

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

7. Er wordt een URL weergegeven in de externe PowerShell-sessie. Kopieer de koppeling van de Tenant en plak deze in een webbrowser.

8. Meld u aan met uw globale-beheerdersreferenties. Wanneer het volgende scherm wordt weergegeven, selecteert u **accepteren**.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Het dialoogvenster Machtigingen accepteren":::

9. Ga terug naar de externe PowerShell-sessie en druk op ENTER om door te gaan.

10. Met het script worden de overige instel objecten geconfigureerd. Hier volgt een voorbeeld.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

De installatie van doel beheerders is nu voltooid.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Stap-voor-stap-instructies voor de bron tenantbeheerder

1.  Meld u aan bij uw postvak als het ResourceTenantAdminEmail dat door de doel beheerder is opgegeven tijdens de installatie. Zoek de e-mail uitnodiging van de doel Tenant en selecteer vervolgens de knop **aan de slag** .

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="U bent uitgenodigd voor het dialoogvenster":::

2. Selecteer **accepteren** om de uitnodiging te accepteren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster voor het accepteren van machtigingen":::

   > [!NOTE]
   > Als u dit e-mailbericht niet ontvangt of als u het niet kunt vinden, wordt de doel tenantbeheerder een directe URL gegeven waarnaar u de uitnodiging kunt accepteren. De URL moet in de naam van de externe PowerShell-sessie van de doel tenantbeheerder staan.

3. Maak in het Microsoft 365-Beheercentrum of een externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om te bepalen welke postvakken door de doelgroep van de bron zijn toegestaan om (te verplaatsen) van de bron Tenant naar de doel Tenant. U hoeft deze groep niet vooraf in te vullen, maar er moet minimaal één groep worden opgegeven om de instellingsstappen (script) uit te voeren. Neste groepen worden niet ondersteund. 

4. Download het SetupCrossTenantRelationshipForTargetResource.ps1-script voor de configuratie van de bron-Tenant vanuit de GitHub-bibliotheek: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) . 

5. Maak een externe PowerShell-verbinding met de bron Tenant met uw beheerdersmachtigingen voor Exchange. Globale beheerdersmachtigingen zijn niet vereist voor het configureren van de bron Tenant, alleen de doel Tenant vanwege het maken van Azure-toepassingen.

6. Wijzig de adreslijst in de naam van het script of Controleer of het script op de locatie in de externe PowerShell-sessie momenteel is opgeslagen.

7. Voer het script uit met de volgende vereiste parameters en waarden.

    | Tabelwaardeparameter | Value |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Beveiligingsgroep met e-mail gemaakt door bron Tenant voor de identiteiten/postvakken die binnen het bereik van de migratie liggen. |
    | -ResourceTenantDomain | Naam Tenant domeinnaam, bijvoorbeeld fabrikam.onmicrosoft.com. |
    | -TargetTenantDomain | De naam van het doel Tenant domein, bijvoorbeeld contoso.onmicrosoft.com. |
    | -ApplicationId | De ID van de Azure-toepassing van de toepassing die wordt gebruikt voor de migratie. Toepassings-ID beschikbaar via uw Azure-Portal (Azure AD, Enterprise-toepassingen, app-naam, toepassings-ID) of die is opgenomen in de e-mail van de uitnodiging.  |
    | -TargetTenantId | Tenant-ID van de doel Tenant. Bijvoorbeeld de naam van een Azure AD-Tenant van contoso.onmicrosoft.com Tenant. |
    |||

    Hier volgt een voorbeeld.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

De installatie van bronbeheer is nu voltooid.

### <a name="verify-setup"></a>Controleer de installatie

Controleer of de organisatie relaties in de bron-en doel tenants en het migratie-eindpunt in de doelsite zijn gemaakt.

#### <a name="target-tenant"></a>Doel Tenant

**Organisatie relatie**

Controleer of het organisatie relatie object is gemaakt en geconfigureerd met deze opdracht.

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
Hier ziet u een voorbeeld:

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

**Migratie-eindpunt**

Controleer of het migratie-eindpunt object is gemaakt en geconfigureerd met deze opdracht.

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

#### <a name="source-tenant"></a>Bron Tenant

**Organisatie relatie**

Controleer of het organisatie relatie object is gemaakt en geconfigureerd met deze opdracht.

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

### <a name="move-mailboxes-back-to-the-original-source"></a>Postvakken terug verplaatsen naar de oorspronkelijke bron

Als een postvak weer naar de oorspronkelijke bron Tenant gaat, moet dezelfde reeks stappen en scripts worden uitgevoerd in zowel nieuwe bron als nieuwe doel tenants. Het bestaande organisatie relatie object wordt bijgewerkt of toegevoegd en wordt niet opnieuw gemaakt.

## <a name="prepare-target-user-objects-for-migration"></a>Doelgebruikers objecten voorbereiden voor migratie

Gebruikers die worden gemigreerd, moeten presenteren in de doel Tenant en het Exchange Online-systeem (als e-mail gebruikers) die zijn gemarkeerd met specifieke kenmerken om de verhuizing van de cross-Tenant te activeren. Het systeem gaat niet naar gebruikers die niet correct zijn ingesteld in de doel Tenant. In het volgende gedeelte vindt u meer informatie over de vereisten voor de MailUser-objecten voor de doel Tenant.

### <a name="prerequisites"></a>Vereisten
  
U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.  

1. Als u een postvak van een bronorganisatie verplaatst, moet u een e-mail gebruikersobject in de doelorganisatie inrichten: 
   - De doelgebruiker moet deze kenmerken hebben van het bronpostvak of toegewezen aan het nieuwe gebruikersobject:
      - ExchangeGUID (directe stroom van bron naar doel): de GUID van het postvak moet overeenkomen. Het verplaatsings proces wordt niet voortgezet als dit niet aanwezig is op het doelobject. 
      - ArchiveGUID (directe stroom van bron naar doel): de archief-GUID moet overeenkomen. Het verplaatsings proces wordt niet voortgezet als dit niet aanwezig is in het doelobject. (Dit is alleen vereist als het bronpostvak archief is ingeschakeld). 
      - LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> "): de LegacyExchangeDN moet aanwezig zijn op de doel MailUser als x500: proxyAddress. De verplaatsings processen worden niet uitgevoerd als dit niet voor het doelobject wordt weergegeven. 
      - UserPrincipalName: UPN wordt uitgelijnd met de nieuwe identiteit van de gebruiker of het doelbedrijf (bijvoorbeeld user@northwindtraders.onmicrosoft.com). 
      - Primaire SMTPAddress – het primaire SMTP-adres wordt uitgelijnd met het nieuwe bedrijf van de gebruiker (bijvoorbeeld user@northwind.com). 
      - TargetAddress/ExternalEmailAddress: e-gebruikers verwijzen naar het huidige postvak van de gebruiker dat wordt gehost in de bron Tenant (bijvoorbeeld user@contoso.onmicrosoft.com). Wanneer u deze waarde toewijst, controleert u of u ook aan de PrimarySMTPAddress of met deze waarde wordt het PrimarySMTPAddress ingesteld waarmee verplaatsings fouten worden veroorzaakt. 
      - U kunt geen oudere SMTP-proxyadressen van het bronpostvak toevoegen aan de gebruiker. U kunt contoso.com bijvoorbeeld niet bijhouden voor de gebruiker E-mail in fabrikam.onmicrosoft.com-Tenant objecten). Domeinen zijn gekoppeld aan één Azure AD-of Exchange Online-Tenant.
 
    Voorbeeld van een **doel** -MailUser-object:
 
    | Attribuut             | Value                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | Alias                 | LaraN                                                                                                                    |
    | RecipientType         | Sharedmailbox                                                                                                                 |
    | RecipientTypeDetails  | Sharedmailbox                                                                                                                 |
    | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
    | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
    | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
    | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
    | LegacyExchangeDN      | /o = eerste organisatie/OE = Exchange-beheergroep                                                                   |
    |                       | (FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = 74e5385fce4b46d19006876949855035Lara                                                  |
    | EmailAddresses        | x500:/o = First organisatie/ou = Exchange-beheergroep (FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = d11ec1a2cacd4f81858c8190  |
    |                       | 7273f1f9-Lara                                                                                                            |
    |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
    |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
    |||

   Voorbeeld van een **bron** postvak:

   | Attribuut             | Value                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | Alias                 | LaraN                                                                    |
   | RecipientType         | User Mailbox                                                              |
   | RecipientTypeDetails  | User Mailbox                                                              |
   | UserPrincipalName     | LaraN@contoso.onmicrosoft.com                                            |
   | PrimarySmtpAddress    | Lara.Newton@contoso.com                                                  |
   | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                     |
   | LegacyExchangeDN      | /o = eerste organisatie/OE = Exchange-beheergroep                   |
   |                       | (FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = d11ec1a2cacd4f81858c81907273f1f9Lara  |
   | EmailAddresses        | smtp:LaraN@contoso.onmicrosoft.com 
   |                       | SMTP:Lara.Newton@contoso.com          |
   |||

   - Er kunnen nog geen extra kenmerken worden opgenomen in een hybride Exchange-weergegeven. Als dat niet zo is, moeten ze ook worden opgenomen. 
   - msExchBlockedSendersHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.
   - msExchSafeRecipientsHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.
   - msExchSafeSendersHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.

2. Als het bronpostvak zich in LitigationHold bevindt en de grootte van de bronvermeldingen voor herstelbare items groter is dan de standaarddatabase (30 GB), wordt de verhuizing niet voortgezet, aangezien de doel quota kleiner is dan de grootte van het bronpostvak. U kunt het doel-e-mail gebruikersobject bijwerken om de vlaggen van het ELC-postvak van de bronomgeving naar het doel te laten uitvouwen, zodat het doelsysteem de quota van de e-mail gebruiker tot 100 GB uitbreidt, zodat de site naar het doel wordt verplaatst. Deze instructies werken alleen voor hybride identiteit met Azure AD Connect, aangezien de opdrachten voor de stempel van de ELC-vlaggen niet zichtbaar zijn voor tenantbeheerders.

    >[!Note]
    > VOORBEELD: ALS DAT IS, GEEN GARANTIE<br/>In dit script wordt uitgegaan van een verbinding met beide bronpostvak (om bronwaarden te verkrijgen) en de on-premises Active Directory (voor het maken van een stempel van het object ADUser). Als er voor de bron een actie-item voor zaken of eenmalige aanmelding is ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de Dumpster grootte van de bestemmings account groter tot 100 GB.

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. Niet-hybride doel tenants kunnen de quota voor de map herstelbare items voor de mailgebruikers voorafgaand aan de migratie wijzigen door de volgende opdracht uit te voeren om het doorsturen van berichten in het object MailUser te activeren en de quota te verhogen tot 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Opmerking Dit werkt niet voor tenants in hybride.

4. Gebruikers in de doelorganisatie moeten een licentie hebben met de juiste Exchange Online-abonnementen die van toepassing zijn op de organisatie. U kunt een licentie vóór het verplaatsen van een postvak toepassen, maar slechts eenmaal dat de doel-e-mail gebruiker juist is ingesteld met ExchangeGUID en proxyadressen. Wanneer u een licentie toepast voordat de ExchangeGUID is toegepast, wordt het nieuwe postvak in de doelorganisatie weergegeven. 

    > [!Note]
    > Wanneer u een licentie toepast op een postvak of e-mail-object, worden alle SMTP-proxyAddresses gemigreerd, zodat alleen geverifieerde domeinen worden opgenomen in de van de Exchange-records. 

5. U moet ervoor zorgen dat de doelgebruiker geen eerdere ExchangeGuid heeft die niet overeenkomen met de bron ExchangeGuid. Dit kan gebeuren als de doelgebruiker e-mail eerder een licentie voor Exchange Online is en een postvak is ingericht. Als de doel-mailgebruiker eerder een licentie voor of een ExchangeGuid heeft die niet overeenkomt met de bron ExchangeGuid, moet u een opschooning van de Cloud gebruiker E-mail uitvoeren. Voor deze Cloud converteren e kunt u de opdracht uitvoeren `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .  

    > [!Caution]
    > Dit proces is onomkeerbaar. Als het object een softDeleted-postvak heeft, kunt u dit na dit punt niet meer herstellen. Als dit is uitgeschakeld, kunt u echter het juiste ExchangeGuid synchroniseren met het doelobject en moet u het bronpostvak verbinden met het nieuw gemaakte doel postvak. (Naslaggids voor naslaginformatie over de nieuwe parameter.)  

    Objecten met eerder postvakken zoeken met deze opdracht.

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```

    Hier volgt een voorbeeld. 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    Wis de tijdelijke handmatig verwijderde postvak met deze opdracht.

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

## <a name="perform-mailbox-migrations"></a>Postvak migraties uitvoeren

Migraties van Exchange-postvak van cross-Tenant worden verzonden als migratie batches die zijn geïnitieerd via de doel Tenant. Dit is vergelijkbaar met de manier waarop migratie batches voor onderweg worden gebruikt wanneer ze worden gemigreerd van Exchange on-premises naar Microsoft 365. 

### <a name="create-migration-batches"></a>Migratie batches maken

Hier ziet u een voorbeeld van een batchgewijze migratie batch voor het verplaatsen van de overstap.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Het e-mailadres in het CSV-bestand moet de naam zijn die is opgegeven in de doel Tenant, niet de bron Tenant.

Het verzenden van migratie batches wordt ook ondersteund door het nieuwe Exchange-Beheercentrum wanneer u de optie Cross-Tenant selecteert.

#### <a name="update-on-premises-mailusers"></a>On-premises mailgebruikers bijwerken

Wanneer het postvak van de bron naar het doel wordt verplaatst, moet u ervoor zorgen dat de on-premises e-mail gebruikers, zowel bron als doel, worden bijgewerkt met het nieuwe targetAddress. In de voorbeelden wordt de targetDeliveryDomain gebruikt in de **contoso.onmicrosoft.com**. Werk de e-mail gebruikers bij met dit targetAddress.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Moeten we na de verhuizing RemoteMailboxes bijwerken in de bron on-premises?**

Ja, u moet het bericht targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de on-premises bron gebruikers bijwerken wanneer het bron Tenant postvak wordt verplaatst naar de doel Tenant.  Hoewel e-mail routering de verwijzingen kan volgen voor meerdere e-mail gebruikers met verschillende gegevens, moet u beschikbaarheidsinfo voor e-mail gebruikers richten op de locatie van de gebruiker van het postvak. Zoeken naar beschikbaarheidsinfo gaat niet over meerdere redirecties. 

**Migreert de inhoud van de map teams-chat cross-Tenant?**  

Nee, de inhoud van de map teams-chatberichten wordt niet gemigreerd naar een andere Tenant.  

**Hoe kan ik de verplaatsingen van een zelfstandige verplaatsingen zien, niet mijn onboarding en uit de boarding?**

Gebruik de `-flags` parameter. Hier volgt een voorbeeld.

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

**Kunt u voorbeeldscripts opgeven voor het kopiëren van kenmerken die worden gebruikt voor testen?**

> [!Note]
> VOORBEELD: ALS DAT IS, GEEN GARANTIE<br/>In dit script wordt uitgegaan van een verbinding met beide bronpostvak (om bronwaarden te verkrijgen) en de on-premises Active Directory Domain Services (voor het maken van een stempel van het object ADUser). Als er voor de bron een actie-item voor zaken of eenmalige aanmelding is ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de Dumpster grootte van de bestemmings account groter tot 100 GB.

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
**Hoe krijg ik toegang tot Outlook op dag 1 nadat het postvak gebruiken is verplaatst?**

Aangezien slechts één Tenant eigenaar kan zijn van een domein, wordt de voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doel Tenant wanneer het postvak wordt verplaatst. alleen de domeinen die zijn gekoppeld aan de nieuwe Tenant. Outlook gebruikt de nieuwe UPN voor verificatie bij de service en het Outlook-profiel verwacht de oudere primaire SMTPAddress zodat deze overeenkomt met het postvak in het doelsysteem. Aangezien het oude adres niet in het doelsysteem staat, maakt het Outlook-profiel geen verbinding met het zojuist verplaatste postvak. 

Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN, het primaire SMTP-adres en de OST-inhoud opnieuw synchroniseren. 

> [!Note]
> Plan de uitvoering van de gebruikers voor verdere uitvoering. U moet beschikken over de mogelijkheid om netwerk gebruik te maken van de clientprofielen van Outlook en de volgende OST-en OAB-bestanden worden gedownload naar clients. 
 
**Welke Exchange-gebruikers van de domein///////dat heb ik nodig om een verplaatsing tussen meerdere tenants in te stellen of te voltooien?**
 
Er is een matrix met rollen op basis van de hypothese met gedelegeerde rechten tijdens het uitvoeren van een Postvak verplaatsen. Momenteel zijn er twee rollen nodig:  

- De eerste functie is voor een eenmalige instel taak waarmee de autorisatie van het verplaatsen van inhoud in of uit de begrenzing van uw Tenant/organisatie wordt vastgelegd. Aangezien het verplaatsen van gegevens uit uw organisatie besturingselement een belangrijke rol heeft voor alle bedrijven, hebben we gecommuniceerd met de best toegewezen rol van de beheerder van de organisatie (OrgAdmin). Deze rol moet een nieuw OrganizationRelationship wijzigen of instellen waarmee de MailboxMoveCapability van de externe organisatie wordt gedefinieerd. Alleen de OrgAdmin kan de instelling MailboxMoveCapability wijzigen, terwijl andere kenmerken van het OrganizationRelationhip kunnen worden beheerd door de beheerder van federatieve delen. 
 
- De rol van het uitvoeren van de feitelijke verplaatsingsopdrachten kan worden gedelegeerd aan een functie op een lager niveau. Met behulp van de parameter wordt de functie voor het verplaatsen van postvakken binnen of buiten de organisatie toegewezen `-RemoteTenant` .  

**Hoe kan ik de naam van het SMTP-adres voor targetAddress (TargetDeliveryDomain) op het geconverteerde postvak selecteren (voor e-mail gebruikers converteren)?**
 
Het Exchange-postvak wordt verplaatst met MEVR. het oorspronkelijke bronpostvak voor de conversie naar een e-mailadres (proxyAddress) op het doelobject. Wanneer het proces is voltooid, wordt de TargetDeliveryDomain-waarde die is doorgegeven aan de opdracht verplaatsen, gecontroleerd op de doelzijde van dit domein. Wanneer er een overeenkomst wordt gevonden, wordt het overeenkomende proxyAddress gebruikt voor het instellen van het ExternalEmailAddress (targetAddress) voor het geconverteerde postvak (Now Mail User).
 
**Hoe wordt de overgang van postvak machtigingen gewijzigd?**

Postvak machtigingen omvatten verzenden namens en Postvak toegang: 

- Verzenden namens (AD: publicDelegates) Hiermee wordt de DN van geadresseerden opgeslagen die toegang hebben tot het postvak van een gebruiker als gemachtigde. Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de overgang van het postvak. Als het bronpostvak is ingesteld op publicDelegates, moet u het publicDelegates op het doel postvak opnieuw instellen nadat de gebruiker E-mail voor de conversie van een postvak in de doelomgeving is voltooid met behulp van de `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` opdracht. 
 
- Postvak machtigingen die zijn opgeslagen in het postvak, worden verplaatst met het postvak wanneer zowel de primaire als de gemachtigde worden verplaatst naar het doelsysteem. De gebruiker TestUser_7 heeft bijvoorbeeld machtiging fullaccess, TestUser_8 in de Tenant SourceCompany.onmicrosoft.com. Wanneer het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doeldirectory. Voorbeelden van het gebruik van *Get-mailboxpermission kunt* voor TestUser_7 in de bron-en doel tenants worden hieronder weergegeven. Exchange-cmdlets worden volgens de bron en het doel met bovenstaande stappen opgelost. 
 
Hier ziet u een voorbeeld van de uitvoer van de Postvak machtiging voordat u deze verplaatst. 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier ziet u een voorbeeld van de uitvoer van de Postvak machtiging na de verhuizing. 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> Het postvak en de Agendamachtigingen voor de cross-Tenant worden niet ondersteund. U moet principals en gemachtigden indelen in geconsolideerde verplaatsings batches, zodat deze verbonden postvakken op hetzelfde moment van de bron Tenant worden overgezet. 

**Welke X500-proxy moet worden toegevoegd aan de doeladressen van de doelgebruiker om de migratie mogelijk te maken?**  

Voor de migratie van het migratie postvak moet de LegacyExchangeDN-waarde van het bronpostvak object worden vastgelegd als een x500 e-mailadres in het doel MailUser object.  

Voorbeeld:  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> Naast deze X500-proxy, moet u alle X500-proxy's uit het postvak in de bron naar het postvak in de doelversie kopiëren.  

**Is Azure-sleutel kluis vereist en wanneer worden transacties uitgevoerd?**  

Ja, een Azure-abonnement is vereist om de sleutel kluis te gebruiken voor het opslaan van het certificaat om migratie te verlenen. In tegenstelling tot onboarding-migraties waarbij gebruikersnaam & wachtwoord worden gebruikt voor het verifiëren van de bron, migratie van cross-Tenant berichten gebruikmaken van OAuth en dit certificaat als geheime/referentie. De toegang tot de belangrijke kluis moet in alle postvak migraties worden bijgehouden, aangezien deze eenmaal aan het begin en eenmaal einde van de migratie wordt gebruikt, en eenmaal per 24 uur tijdens de incrementele synchronisatie tijden. U kunt [hier]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)AKV kostprijsberekenings Details bekijken.  

**Hebt u aanbevelingen voor batches?**  

Voer niet langer 2000 postvakken per batch. U wordt ten zeerste aangeraden om batches van twee weken vóór de bijsnijd datum te versturen omdat er geen gevolgen zijn voor de eindgebruikers tijdens de synchronisatie. Als u hulp nodig hebt bij het aantal postvakken in 50.000, kunt u contact opnemen met de distributielijst technische feedback op crosstenantmigrationpreview@service.microsoft.com.

**Wat moet ik doen als ik service versleuteling met de klant sleutelgebruik?**

Het postvak wordt gedecodeerd voordat het wordt verplaatst. Zorg ervoor dat de klantcode is geconfigureerd in de doel Tenant, indien deze nog niet is vereist. Zie [hier](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) voor meer informatie.  

**Wat is de geschatte migratie tijd?**

Om u te helpen bij het plannen van de migratie [, ziet u in de onderstaande tabel](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) de richtlijnen voor het verwachten van de migratie van bulk-postvaken of afzonderlijke migraties om te voltooien. Deze ramingen zijn gebaseerd op een gegevensanalyse van vorige klanten migraties. Aangezien elke omgeving uniek is, kan de exacte migratie snelheid variëren.  

Let op: deze functie is momenteel beschikbaar in de preview-versie en de SLA en elk van de toepasselijke service niveaus gelden niet voor eventuele prestaties of beschikbaarheidsproblemen tijdens de preview-status van deze functie.

## <a name="known-issues"></a>Bekende problemen  

-  **Probleem: automatisch uitgevouwen archieven kunnen niet worden gemigreerd.** De functie voor migratie van cross tenants ondersteunt migraties van het primaire postvak en het archief postvak voor een bepaalde gebruiker. Als de gebruiker in de bron maar een automatisch uitgevouwen archief heeft dat meer dan één archief postvak heeft, kan de extra archiefmap niet worden gemigreerd.

- **Probleem: Cloud mailgebruikerss met een niet-eigenaar SMTP-proxyAddress blokkeren met een achtergrond bewegen.** Als u op de site van een doel Tenant een gebruiker maakt, moet u ervoor zorgen dat alle SMTP-proxyadressen deel uitmaken van de doel Tenant. Als er een SMTP-proxyAddress bestaat voor de doelgebruiker die niet behoort tot de lokale Tenant, wordt de conversie van de mail-gebruiker naar Postvak voorkomen. Dit komt door onze zekerheid dat postvak objecten alleen e-mail kunnen verzenden van domeinen waarvoor de Tenant gezaghebbend is (domeinen die door de Tenant worden geclaimd): 

   - Wanneer u gebruikers van on-premises via Azure AD Connect synchroniseert, dient u on-premises e-mail gebruikersobjecten in te richten met ExternalEmailAddress die verwijzen naar de bron Tenant met het postvak (laran@contoso.onmicrosoft.com) en u stemt het PrimarySMTPAddress toe als een domein in de doel Tenant (Lara.Newton@northwind.com). Deze waarden worden gesynchroniseerd met de Tenant en een juiste e-mail gebruiker wordt ingericht en klaar voor de migratie. Hier ziet u een voorbeeld van een object.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > Het *contoso.onmicrosoft.com* -adres is *niet* aanwezig in de matrix EmailAddress/proxyAddresses.

- **Probleem: gebruikersobjecten met een externe primaire SMTP-adres worden gewijzigd/opnieuw ingesteld op intern geclaimde domeinen**

   MailUser Objects zijn pointers naar niet-lokale postvakken. In het geval van cross-Tenant migraties gebruiken we MailUser Objects om het bronpostvak (vanuit de perspectief van de doelorganisatie) of het doel postvak (vanuit het perspectief van de bronorganisatie) te vertegenwoordigen. De e-mail gebruikers hebben een ExternalEmailAddress (targetAddress) die verwijzen naar het SMTP-adres van het feitelijke postvak (ProxyTest@fabrikam.onmicrosoft.com) en primarySMTP dat staat voor het weergegeven SMTP-adres van de gebruikers van het postvak in de adreslijst. In sommige organisaties wordt het primaire SMTP-adres weergegeven als een extern SMTP-adres, niet als een adres dat eigendom is van de lokale Tenant (zoals fabrikam.com in plaats van contoso.com).  Wanneer bijvoorbeeld een Exchange-serviceplan-object wordt toegepast op de e-mail gebruiker via licentiebewerkingen, wordt het primaire SMTP-adres gewijzigd in de weergave van een domein dat is geverifieerd door de lokale organisatie (contoso.com). Er zijn twee mogelijke redenen:
   
   - Wanneer een Exchange-serviceplan wordt toegepast op een e-mail gebruiker, begint het Azure AD-proces om te zorgen dat er geen e-mailberichten, spoofing of e-mailberichten vanuit een andere Tenant kunnen worden verzonden. Alle SMTP-adressen in een object van de geadresseerde met deze serviceplannen worden verwijderd als het adres niet door de lokale organisatie wordt geverifieerd. Zoals in het voorbeeld het geval is, is het onFabikam.com-domein niet geverifieerd door de contoso.onmicrosoft.com-Tenant, zodat de reiniging dit fabrikam.com domein verwijdert. Als u dit externe domein wilt behouden voor de migratie, moet u vóór de migratie of na migratie eerst uw migratie processen wijzigen in stripesets na voltooiing of voor de overstap om ervoor te zorgen dat de gebruikers op de verwachte manier de juiste plaats hebben. U moet ervoor zorgen dat het postvak object juist is gelicentieerd voor geen invloed heeft op de e-mail service.<br/><br/>Een voorbeeld van een script om de serviceplannen te verwijderen van een MailUser in de Contoso.onmicrosoft.com-Tenant wordt hier weergegeven.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       Resultaten van de set ServicePlans worden hier weergegeven.

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
 
       De PrimarySMTPAddress van de gebruiker is niet meer te reinigen. Het fabrikam.com-domein is niet eigendom van de contoso.onmicrosoft.com-Tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.

       Hier volgt een voorbeeld.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - Wanneer msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), worden bij on-premises gebruikers die worden gemigreerd naar de doel Tenant, de proxy-opmaak logica in azure verwijdert en de primarySMTP opnieuw ingesteld op een domein met eigenaar. Door msExchRemoteRecipientType te wissen in de on-premises MailUser, is de logica voor de reiniging van de proxy niet langer van toepassing. <br/><br>Hieronder ziet u de volledige set service abonnementen die Exchange Online omvatten.

   | Naam                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery-opslag (500 GB)               |
   | Klanten-lockbox                                  |
   | Preventie van gegevensverlies                              |
   | Exchange Enterprise CAL'S-Services (EOP, DLP)       |
   | Basisprincipes van Exchange                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (abonnement 1)                          |
   | Exchange Online (abonnement 2)                          |
   | Exchange Online Archiving voor Exchange Online     |
   | Exchange Online Archiving voor Exchange Server     |
   | Invoegtoepassing Exchange Online inactief gebruikers              |
   | Exchange Online kiosk                             |
   | Multi-geografische Exchange Online                         |
   | Exchange Online Abonnement 1                            |
   | POP voor Exchange Online                               |
   | Exchange Online Protection                        |
   | Informatie belemmeringen                              |
   | Information Protection voor Office 365-Premium   |
   | Information Protection voor Office 365-Standard  |
   | Inzichten op MyAnalytics                           |
   | Geavanceerde controle voor Microsoft 365                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (volledig)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender voor Office 365 (abonnement 1)    |
   | Microsoft Defender voor Office 365 (abonnement 2)    |
   | Toegangsbeheer voor Office 365-bevoegdheden           |
   | Premium-codering in Office 365                  |
    