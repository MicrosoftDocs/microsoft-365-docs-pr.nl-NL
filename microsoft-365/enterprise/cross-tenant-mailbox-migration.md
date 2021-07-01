---
title: Migratie van postvakken tussen tenants
description: Postvakken verplaatsen tussen Microsoft 365 of Office 365 tenants.
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
ms.openlocfilehash: 4541cd425a8f666f6f0b513dd18cb92c2d6c7c60
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230029"
---
# <a name="cross-tenant-mailbox-migration-preview"></a>Migratie van postvakken tussen tenants (voorbeeld)

Als eerder een Exchange Online-tenant postvakken moest verplaatsen naar een andere tenant in dezelfde Exchange Online-service, moesten ze ze volledig buiten gebruik maken van on-premises en vervolgens aan boord brengen naar een nieuwe tenant. Met de nieuwe functie voor migratie van postvakken tussen tenants kunnen tenantbeheerders in zowel bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen. Hierdoor hoeft u geen postvakken aan boord of aan boord meer te gebruiken.

Meestal hebt u tijdens fusies of afstotingen de mogelijkheid nodig om gebruikers en inhoud over te zetten naar een nieuwe tenant. Wanneer de doeltenderbeheerder de move uitvoert, wordt dit een pull move genoemd, vergelijkbaar met on-premises migraties voor cloud-onboarding.

Cross-tenant Exchange postvakbewegingen worden volledig selfservice door tenantbeheerders gebruikt, met behulp van bekende interfaces die kunnen worden gescript in de grotere werkstromen die nodig zijn om gebruikers over te zetten naar hun nieuwe organisatie. Beheerders kunnen de cmdlet, die beschikbaar is via de beheerrol Postvakken verplaatsen, gebruiken om bewegingen `New-MigrationBatch` tussen tenants uit te voeren. Het verhuisproces omvat tenantautorisatiecontroles tijdens postvaksynchronisatie en -finalisatie.

Gebruikers die migreren, moeten aanwezig zijn in het doeltendersysteem Exchange Online MailUsers, gemarkeerd met specifieke kenmerken om de migraties tussen tenants in te stellen. Het systeem wordt niet verplaatst voor gebruikers die niet correct zijn ingesteld in de doel tenant.

Wanneer de bewegingen zijn voltooid, wordt het bronsysteempostvak geconverteerd naar MailUser en wordt targetAddress (weergegeven als ExternalEmailAddress in Exchange) gestempeld met het routeringsadres naar de doeltenator. Dit proces laat de oudere MailUser achter in de brontenator en zorgt voor een periode van co-existence en e-mailroutering. Wanneer bedrijfsprocessen het toestaan, kan de brontenator MailUser verwijderen of converteren naar een e-mailcontactcontact.

Cross-tenant Exchange postvakmigraties worden alleen ondersteund voor tenants in hybride of cloud, of een combinatie van de twee.

In dit artikel wordt het proces beschreven voor het verplaatsen van postvakken met verschillende tenants en worden richtlijnen gegeven voor het voorbereiden van bron- en doelten tenants voor de inhoudsverzet.

## <a name="preparing-source-and-target-tenants"></a>Bron- en doelten tenants voorbereiden

Voor de functie voor Exchange migratie van postvakken is autorisatie en scoping vereist voor migraties tussen tenants. Met de Azure Enterprise-toepassing en key vault-opslagoplossingen kunnen tenantbeheerders nu zowel autorisatie als scoping van Exchange Online-postvakmigraties van de ene tenant naar de andere beheren. Het verplaatsen van postvakken met meerdere tenant Azure Active Directory s ondersteunt een uitnodigings- en toestemmingsmodel om een azure AD-toepassing (Azure AD) te maken die wordt gebruikt voor verificatie tussen een tenantpaar. Aanvullende onderdelen, zoals een organisatierelatie en een migratie-eindpunt, zijn ook vereist.

Deze sectie bevat niet de specifieke stappen die nodig zijn om de gebruikersobjecten van MailUser voor te bereiden in de doelmap, en bevat ook niet de voorbeeldopdracht om een migratiebatch in te dienen. Zie [Doelgebruikersobjecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.

## <a name="prerequisites"></a>Vereisten

Voor de functie voor het verplaatsen van postvakken met verschillende tenants is [Azure Key Vault](/azure/key-vault/basic-concepts) vereist om een tenantpaarspecifieke Azure-toepassing te maken voor het veilig opslaan en openen van het certificaat/geheim dat wordt gebruikt voor het verifiëren en autoriseren van postvakmigratie van de ene tenant naar de andere, waardoor alle vereisten voor het delen van certificaten/geheimen tussen tenants worden verwijderd.

Voordat u begint, moet u de benodigde machtigingen hebben om de implementatiescripts uit te voeren om Azure Key Vault, De toepassing Postvak verplaatsen, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren. Globale beheerder heeft meestal toestemming om alle configuratiestappen uit te voeren.

Daarnaast zijn beveiligingsgroepen met e-mail in de bron tenant vereist voordat de installatie wordt uitgevoerd. Deze groepen worden gebruikt voor het bereik van de lijst met postvakken die kunnen worden verplaatst van de brontender (of soms resourceten tenant genoemd) naar de doelten tenant. Hierdoor kan de beheerder van de brontender de specifieke set postvakken beperken of beperken die moeten worden verplaatst, zodat onbedoelde gebruikers niet kunnen worden gemigreerd. Geneste groepen worden niet ondersteund.

U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken verplaatst) om hun tenant-id Microsoft 365 verkrijgen. Deze tenant-id wordt gebruikt in het veld `DomainName` Organisatierelatie.

Als u de tenant-id van een abonnement wilt verkrijgen, meld u zich aan bij de Microsoft 365-beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) . Klik op het kopieerpictogram voor de eigenschap Tenant-id om het naar het klembord te kopiëren.

Dit is hoe het proces werkt.

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Tenantvoorbereiding voor postvakmigratie.":::

[Zie een grotere versie van deze afbeelding.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
-->

### <a name="prepare-tenants"></a>Tenants voorbereiden

Op hoog niveau vinden de volgende configuratieacties plaats bij het uitvoeren van de installatiescripts.

De doel tenant voorbereiden:

1. Als er geen bestaande Azure Resource Group wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).
2. Als er geen bestaande Sleutelkluis wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).
3. Er wordt een nieuw Access-beleid gemaakt voor de Office 365 Exchange Online postvakmigratietoepassing (SCRIPT).
4. Er wordt een nieuw certificaat gemaakt (of een bestaand certificaat, indien opgegeven) om het geheim van de migratietoepassing (SCRIPT) te bewaren.
5. Er wordt een nieuwe Azure AD-toepassing gemaakt (SCRIPT).
6. Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).
7. Machtigingen voor postvakmigratie worden toegewezen aan de toepassing (SCRIPT).
8. Het implementatiescript wordt onderbroken totdat de doelbeheerder toestemming geeft voor de eigen toepassing (SCRIPT).
9. De doeltenderbeheerder stemt in met de machtigingen die aan de toepassing zijn verleend (HANDMATIG).
10. Er wordt een organisatierelatie gemaakt met de doel tenant (SCRIPT).
11. Er wordt een migratie-eindpunt gemaakt om postvakken naar de doeltender (SCRIPT) te trekken.

De bron tenant voorbereiden:

1. De bronten tenantbeheerder accepteert toestemming voor de uitnodiging voor de toepassing Postvakmigratie van de doelten tenant (MANUAL).
2. De bronten tenantbeheerder maakt een beveiligingsgroep met e-mail in de tenant om de lijst met postvakken te bevatten die mogen worden verplaatst door de migratietoepassing (MANUAL).
3. Er wordt een organisatierelatie gemaakt met de doel tenant die de postvakmigratietoepassing opgeeft, moet worden gebruikt voor OAuth-verificatie om de aanvraag voor verplaatsen (SCRIPT) te accepteren.

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a>Stapsgewijs instructies voor de doel tenantbeheerder

1. Download het SetupCrossTenantRelationshipForTargetTenant.ps1 script voor het instellen van de doel tenant vanuit [de GitHub repository.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)
2. Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer waaruit u het script gaat uitvoeren.
3. Maak een externe PowerShell-verbinding met de Exchange Online doel tenant. Zorg er nogmaals voor dat u de benodigde machtigingen hebt om de implementatiescripts uit te voeren om de opslag en het certificaat van de Azure Key Vault, De toepassing Postvak verplaatsen, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren.
4. Wijzig de adreslijst van de bestandsmap in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw Externe PowerShell-sessie.
5. Voer het script uit met de volgende parameters en waarden.

    | Parameter | Waarde | Vereist of Optioneel
    |---------------------------------------------|-----------------|--------------|
    | -TargetTenantDomain                         | Doel tenantdomein, zoals fabrikam \. onmicrosoft.com. | Vereist |
    | -ResourceTenantDomain                       | Bronten tenantdomein, zoals contoso \. onmicrosoft.com. | Vereist |
    | -ResourceTenantAdminEmail                   | Het e-mailadres van de bron tenantbeheerder. Dit is de bron tenantbeheerder die instemt met het gebruik van de postvakmigratietoepassing die is verzonden van de doelbeheerder. Dit is de beheerder die de e-mail uitnodigen voor de toepassing ontvangt. | Vereist |
    | -ResourceTenantId                           | Brontenderorganisatie-id (GUID). | Vereist |
    | -SubscriptionId                             | Het Azure-abonnement dat u kunt gebruiken voor het maken van resources. | Vereist |
    | -ResourceGroup                              | Azure resource group name that contains or will contain the Key Vault. | Vereist |
    | -KeyVaultName                               | Azure Key Vault instance that will store your mailbox migration application certificate/secret. | Vereist |
    | -CertificateName                            | Certificaatnaam bij het genereren of zoeken naar certificaat in de sleutelkluis. | Vereist |
    | -CertificateSubject                         | Onderwerpnaam van Azure Key Vault-certificaat, zoals CN=contoso_fabrikam. | Vereist |
    | -AzureResourceLocation                      | De locatie van de Azure-resourcegroep en de sleutelkluis. | Vereist |
    | -ExistingApplicationId                      | E-mailmigratietoepassing die u wilt gebruiken als er al een is gemaakt. | Optioneel |
    | -AzureAppPermissions                        | De machtigingen die moeten worden gegeven aan de postvakmigratietoepassing, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph voor het gebruik van deze toepassing om een uitnodiging voor een toestemmingskoppeling naar resourceten tenant te verzenden). | Vereist |
    | -UseAppAndCertGeneratedForSendingInvitation | Parameter voor het gebruik van de toepassing die is gemaakt voor migratie om te worden gebruikt voor het verzenden van uitnodiging voor toestemmingskoppelingen naar de bron tenantbeheerder. Als u deze niet presenteert, wordt gevraagd of de doelbeheerder de referenties heeft om verbinding te maken met Azure Invitation Manager en de uitnodiging te verzenden als doelbeheerder. | Optioneel |
    | -KeyVaultAuditStorageAccountName            | Het opslagaccount waarin de auditlogboeken van Key Vault werden opgeslagen. | Optioneel |
    | -KeyVaultAuditStorageResourceGroup          | De resourcegroep met het opslagaccount voor het opslaan van auditlogboeken van Key Vault. | Optioneel |
    ||||

    >[!Note]
    > Zorg ervoor dat u de Azure AD PowerShell-module hebt geïnstalleerd voordat de scripts worden uitgevoerd. Raadpleeg hier voor ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) installatiestappen

6. Het script wordt onderbroken en u wordt gevraagd of u akkoord wilt gaan met de Exchange postvakmigratietoepassing die tijdens dit proces is gemaakt. Hier volgt een voorbeeld.

    ```powershell
    PS C:\PowerShell\> # Note: the below User.Invite.All permission is optional, and will only be used to retrieve access token to send invitation email to source tenant
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureResourceLocation "Brazil Southeast" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - User.Invite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```

7. Er wordt een URL weergegeven in de Externe PowerShell-sessie. Kopieer de koppeling die is verstrekt voor uw tenant-toestemming en plak deze in een webbrowser.

8. Meld u aan met uw globale beheerdersreferenties. Wanneer het volgende scherm wordt weergegeven, selecteert u **Accepteren.**

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialoogvenster Machtigingen accepteren":::

9. Ga terug naar de Externe PowerShell-sessie en druk op Enter om door te gaan.

10. Het script configureert de overige installatieobjecten. Hier volgt een voorbeeld.

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

De instelling van de doelbeheerder is nu voltooid.

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a>Stapsgewijs instructies voor de bron tenantbeheerder

1.  Meld u aan bij uw postvak als de -ResourceTenantAdminEmail die is opgegeven door de doelbeheerder tijdens de installatie. Zoek de e-mailuitnodiging van de doel tenant en selecteer vervolgens **de Aan de slag** knop.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="U bent uitgenodigd dialoogvenster":::

2. Selecteer **Accepteren om** de uitnodiging te accepteren.

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster om machtigingen te accepteren":::

   > [!NOTE]
   > Als u deze e-mail niet ontvangt of niet kunt vinden, heeft de doel tenantbeheerder een directe URL gekregen die u kan krijgen om de uitnodiging te accepteren. De URL moet in het afschrift van de Externe PowerShell-sessie van de doel tenantbeheerder staan.

3. Maak in de Microsoft 365-beheercentrum of een externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om de lijst met postvakken te bepalen die door de doelten tenant zijn toegestaan om van de bronten tenant naar de doeltender te gaan (verplaatsen). U hoeft deze groep niet van tevoren in te vullen, maar er moet ten minste één groep beschikbaar zijn om de installatiestappen (script) uit te voeren. Nestgroepen worden niet ondersteund.

4. Download het SetupCrossTenantRelationshipForResourceTenant.ps1 script voor de installatie van de bron tenant in GitHub archief: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .

5. Maak een externe PowerShell-verbinding met de bronten tenant met uw Exchange beheerdersmachtigingen. Globale beheerdersmachtigingen zijn niet vereist om de bronten tenant te configureren, alleen de doelten tenant vanwege het proces voor het maken van Azure-toepassingen.

6. Wijzig de adreslijst in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw Externe PowerShell-sessie.

7. Voer het script uit met de volgende vereiste parameters en waarden.

    | Parameter | Waarde |
    |-----|------|
    | -SourceMailboxMovePublishedScopes | Beveiligingsgroep met e-mail die is gemaakt door bronten tenant voor de identiteiten/postvakken die binnen het migratiebereik vallen. |
    | -ResourceTenantDomain | Bronten tenantdomeinnaam, zoals contoso \. onmicrosoft.com. |
    | -ApplicationId | Azure Application ID (GUID) van de toepassing die voor migratie wordt gebruikt. Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.  |
    | -TargetTenantDomain | Doel tenantdomeinnaam, zoals fabrikam \. onmicrosoft.com. |
    | -TargetTenantId | Tenant-id van de doel tenant. Bijvoorbeeld de Azure AD-tenant-id van contoso \. onmicrosoft.com tenant. |
    |||

    Hier volgt een voorbeeld.
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

De installatie van de bronbeheerder is nu voltooid.

### <a name="verify-setup"></a>Installatie verifiëren

Controleer of de organisatierelaties in zowel bron- als doelten tenants en het migratie-eindpunt in het doel zijn gemaakt.

#### <a name="target-tenant"></a>Doel tenant

**Organisatierelatie**

Controleer of het object organisatierelatie is gemaakt en geconfigureerd met deze opdracht.

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

Controleer of het migratie-eindpuntobject met deze opdracht is gemaakt en geconfigureerd.

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

Controleer of het object organisatierelatie is gemaakt en geconfigureerd met deze opdracht.

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

#### <a name="verify-setup-script"></a>Installatiescript controleren

Als u fouten ontvangt tijdens de configuratie van de bron- of doelten tenants, kunt u het script VerifySetup.ps1 op GitHub uitvoeren [en](https://github.com/microsoft/cross-tenant/releases/tag/Preview) de uitvoer controleren.

Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier volgen een voorbeeld van VerifySetup.ps1 bron tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a>Postvakken terug naar de oorspronkelijke bron verplaatsen

Als een postvak terug moet gaan naar de oorspronkelijke brontender, moeten dezelfde stappen en scripts worden uitgevoerd in zowel nieuwe bron- als nieuwe doelten tenants. Het bestaande object Organisatierelatie wordt bijgewerkt of toegevoegd, niet opnieuw gemaakt.

## <a name="prepare-target-user-objects-for-migration"></a>Doelgebruikersobjecten voorbereiden op migratie

Gebruikers die migreren, moeten aanwezig zijn in de doeltender en het Exchange Online (zoals MailUsers) die zijn gemarkeerd met specifieke kenmerken om de cross-tenantverzet in te stellen. Het systeem wordt niet verplaatst voor gebruikers die niet correct zijn ingesteld in de doel tenant. In de volgende sectie worden de objectvereisten voor MailUser voor de doeltenator be detaillering.

### <a name="prerequisites"></a>Vereisten

U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.

1. Voor postvakken die vanuit een bronorganisatie worden verplaatst, moet u een MailUser-object inrichten in de doelorganisatie:

   - De doelmailgebruiker moet deze kenmerken uit het bronpostvak hebben of zijn toegewezen aan het nieuwe object Gebruiker:
      - ExchangeGUID (directe stroom van bron naar doel) – De postvak-GUID moet overeenkomen. Het verplaatsen gaat niet door als dit niet aanwezig is op het doelobject.
      - ArchiveGUID (direct flow from source to target) – The archive GUID must match. Het verplaatsen gaat niet door als dit niet aanwezig is op het doelobject. (Dit is alleen vereist als het bronpostvak Archiveren is ingeschakeld).
      - LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress. De verhuisprocessen gaan niet door als dit niet aanwezig is op het doelobject.
      - UserPrincipalName: UPN wordt uitgelijnd op de nieuwe identiteit of het doelbedrijf van de gebruiker (bijvoorbeeld user@northwindtraders.onmicrosoft.com).
      - Primair SMTPAddress- Primair SMTP-adres wordt uitgelijnd op het nieuwe bedrijf van de gebruiker (bijvoorbeeld user@northwind.com).
      - TargetAddress/ExternalEmailAddress: MailUser verwijst naar het huidige postvak van de gebruiker dat wordt gehost in bronten tenant (bijvoorbeeld user@contoso.onmicrosoft.com). Wanneer u deze waarde toewijst, controleert u of u ook PrimarySMTPAddress hebt of toewijst, anders wordt met deze waarde het PrimarySMTPAddress ingesteld, waardoor fouten worden verplaatst.
      - U kunt geen oudere smtp-proxyadressen uit het bronpostvak toevoegen aan doelmailuser. U kunt bijvoorbeeld geen contoso.com in de fabrikam.onmicrosoft.com tenantobjecten). Domeinen zijn alleen gekoppeld aan één Azure AD- of Exchange Online tenant.

     Voorbeeld **van het** object MailUser:

     | Attribuut             | Waarde                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | Alias                 | Laran                                                                                                                    |
     | RecipientType         | MailUser                                                                                                                 |
     | RecipientTypeDetails  | MailUser                                                                                                                 |
     | UserPrincipalName     | LaraN@northwintraders.onmicrosoft.com                                                                                    |
     | PrimarySmtpAddress    | Lara.Newton@northwind.com                                                                                                |
     | ExternalEmailAddress  | SMTP:LaraN@contoso.onmicrosoft.com                                                                                       |
     | ExchangeGuid          | 1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8                                                                                     |
     | LegacyExchangeDN      | /o=First Organization/ou=Exchange Administrative Group                                                                   |
     |                       | (FYDIBOHF23SPDLT)/cn=Ontvangers/cn=74e5385fce4b46d19006876949855035Lara                                                  |
     | EmailAddresses        | x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190  |
     |                       | 7273f1f9-Lara                                                                                                            |
     |                       | smtp:LaraN@northwindtraders.onmicrosoft.com                                                                              |
     |                       | SMTP:Lara.Newton@northwind.com                                                                                           |
     |||

     **Voorbeeldbron** Postvakobject:

     | Attribuut             | Waarde                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | Alias                 | Laran                                                                    |
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

   - Er kunnen extra kenmerken worden opgenomen in Exchange hybride schrijf al. Zo niet, dan moeten ze worden opgenomen.
   - msExchBlockedSendersHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.
   - msExchSafeRecipientsHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.
   - msExchSafeSendersHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.

2. Als het bronpostvak Op LitigationHold staat en de grootte van het bronpostvak Herstelbare items groter is dan de standaardwaarde van onze database (30 GB), worden de bewegingen niet doorgeslagen omdat het doelquotum kleiner is dan de grootte van het bronpostvak. U kunt het doelobject MailUser bijwerken om de vlag van het ELC-postvak over te zetten van de bronomgeving naar het doel, waardoor het doelsysteem wordt ingesteld om het quotum van de MailUser uit te breiden naar 100 GB, zodat de overgang naar het doel mogelijk wordt. Deze instructies werken alleen voor hybride identiteit met Azure AD-Verbinding maken, omdat de opdrachten om de ELC-vlaggen te stempelen niet worden blootgesteld aan tenantbeheerders.

    >[!Note]
    > VOORBEELD: ZOALS HET IS, GEEN GARANTIE<br/>In dit script wordt uit gegaan van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory (om het ADUser-object te stempelen). Als bron een geschil of herstel van één item heeft ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.

    ```powershell
    $ELCValue = 0
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}}
    ```

3. Niet-hybride doelten tenants kunnen het quotum wijzigen in de map Herstelbare items voor de MailUsers vóór de migratie door de volgende opdracht uit te voeren om De procedure in te stellen voor het object MailUser en het quotum te verhogen tot 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` . Houd er rekening mee dat dit niet werkt voor tenants in hybride versies.

4. Gebruikers in de doelorganisatie moeten een licentie hebben met Exchange Online abonnementen die van toepassing zijn op de organisatie. U kunt een licentie toepassen op voorhand van een postvakverhuis, maar alleen wanneer de doelmailuser correct is ingesteld met ExchangeGUID- en proxyadressen. Het toepassen van een licentie voordat de ExchangeGUID wordt toegepast, resulteert in een nieuw postvak dat is ingericht in de doelorganisatie.

    > [!Note]
    > Wanneer u een licentie op een postvak- of MailUser-object toe te passen, worden alle SMTP-type proxyAddresses geschuurd om ervoor te zorgen dat alleen geverifieerde domeinen worden opgenomen in de Exchange EmailAddresses-matrix.

5. U moet ervoor zorgen dat de doelmailuser geen eerdere ExchangeGuid heeft die niet overeenkomen met de Bron ExchangeGuid. Dit kan gebeuren als de doel-meu eerder een licentie voor Exchange Online en een postvak heeft ingericht. Als de doelmailuser eerder een licentie had voor of een ExchangeGuid had die niet overeen komt met de Source ExchangeGuid, moet u een opschoning van de cloud-meu uitvoeren. Voor deze cloud-MEUs's kunt u `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` uitvoeren.

    > [!Caution]
    > Dit proces is onomkeerbaar. Als het object een zacht Verwijderd postvak heeft, kan het na dit punt niet meer worden hersteld. Wanneer dit is geweend, kunt u echter de juiste ExchangeGuid synchroniseren met het doelobject en wordt het bronpostvak door MRS verbonden met het nieuwe doelpostvak. (Reference EHLO blog on the new parameter.)

    Met deze opdracht kunt u objecten zoeken die voorheen postvakken waren.

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

    Met deze opdracht kunt u het zacht verwijderde postvak wissen.

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

Cross-tenant Exchange postvakmigraties worden verzonden als migratiebatchs die zijn gestart vanuit de doelten tenant. Dit is vergelijkbaar met de manier waarop on-boarding migratiebatchs werken bij het migreren van Exchange on-premises naar Microsoft 365.

### <a name="create-migration-batches"></a>Migratiebatchs maken

Hier is een voorbeeld van de migratiebatch cmdlet voor het starten van moves.

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> Het e-mailadres in het CSV-bestand moet het e-mailadres zijn dat is opgegeven in de doel tenant, niet de bron tenant.

Migratiebatchinzending wordt ook ondersteund vanuit het nieuwe Exchange beheercentrum bij het selecteren van de optie voor meerdere tenants.

#### <a name="update-on-premises-mailusers"></a>On-premises MailUsers bijwerken

Zodra het postvak van bron naar doel wordt verplaatst, moet u ervoor zorgen dat de on-premises e-mailgebruikers, zowel Bron als doel, worden bijgewerkt met het nieuwe doelAdres. In de voorbeelden is het doelDeliveryDomain dat in de move wordt **gebruikt, contoso.onmicrosoft.com.** Werk de e-mailgebruikers bij met deze targetAddress.

## <a name="frequently-asked-questions"></a>Veelgestelde vragen

**Moeten we RemoteMailboxes on-premises bijwerken in de bron na de verhuizing?**

Ja, u moet het targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de lokale brongebruikers bijwerken wanneer het brontenderpostvak wordt verplaatst naar doelten tenant.  Hoewel e-mailroutering de verwijzingen kan volgen voor meerdere e-mailgebruikers met verschillende doelAdressen, moeten vrije/bezet zoekactie voor e-mailgebruikers zich richten op de locatie van de postvakgebruiker. Bij vrije/bezet zoekactie worden niet meerdere omleidingen achtervolgd.

**Worden Teams vergaderingen gemigreerd tussen tenants?**

De vergaderingen worden verplaatst, maar de URL Teams vergadering wordt niet bijgewerkt wanneer items cross-tenant migreren. Aangezien de URL ongeldig is in de doel tenant, moet u de Teams verwijderen en opnieuw maken.

**Migreert de Teams inhoud van de chatmap cross-tenant?**

Nee, de inhoud Teams chatmap wordt niet gemigreerd tussen tenants.

**Hoe kan ik alleen bewegingen zien die cross-tenant-moves zijn, niet mijn onboarding- en off-boarding-moves?**

Gebruik de `-flags` parameter. Hier volgt een voorbeeld.

```powershell
Get-MoveRequest -Flags "CrossTenant"
```

**Kunt u voorbeeldscripts geven voor het kopiëren van kenmerken die worden gebruikt bij het testen?**

> [!Note]
> VOORBEELD: ZOALS HET IS, GEEN GARANTIE<br/>In dit script wordt ervan uit gegaan dat er verbinding is met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory Domain Services (om het ADUser-object te stempelen). Als bron een geschil of herstel van één item heeft ingeschakeld, stelt u dit in op het doelaccount.  Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.

```powershell
#Dumps out the test mailboxes from SourceTenant
#Note, the filter applied on Get-Mailbox is for an attribute set on CustomAttribute1 = "ProjectKermit"
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################
$outFileUsers = "$home\desktop\userstomigrate.txt"
$outFileUsersXML = "$home\desktop\userstomigrate.xml"
#output the test objects
Get-Mailbox -Filter "CustomAttribute1 -like 'ProjectKermit'" -ResultSize Unlimited | Select-Object -ExpandProperty Alias | Out-File $outFileUsers
$mailboxes = Get-Content $outFileUsers
$mailboxes | ForEach-Object {Get-Mailbox $_} | Select-Object PrimarySMTPAddress,Alias,SamAccountName,FirstName,LastName,DisplayName,Name,ExchangeGuid,ArchiveGuid,LegacyExchangeDn,EmailAddresses | Export-Clixml $outFileUsersXML

#################################################################
#Copy the file $outfile to the desktop of the target on-premises
#then run the below to create MEU in Target
#################################################################
$mailboxes = Import-Clixml $home\desktop\userstomigrate.xml

foreach ($m in $mailboxes) {
    $organization = "@contoso.onmicrosoft.com"
    $mosi = $m.Alias+$organization
    $Password = [System.Web.Security.Membership]::GeneratePassword(16,4) | ConvertTo-SecureString -AsPlainText -Force
    $x500 = "x500:" +$m.LegacyExchangeDn
    $tmpUser = New-MailUser -MicrosoftOnlineServicesID $mosi -PrimarySmtpAddress $mosi -ExternalEmailAddress $m.PrimarySmtpAddress -FirstName $m.FirstName -LastName $m.LastName -Name $m.Name -DisplayName $m.DisplayName -Alias $m.Alias -Password $Password
    $tmpUser | Set-MailUser -EmailAddresses @{add=$x500} -ExchangeGuid $m.ExchangeGuid -ArchiveGuid $m.ArchiveGuid -CustomAttribute1 "ProjectKermit"
    $tmpx500 = $m.EmailAddresses | ?{$_ -match "x500"}
    $tmpx500 | %{Set-MailUser $m.Alias -EmailAddresses @{add="$_"}}
    }

#################################################################
# On AADSync machine, run AADSync
#################################################################
Start-ADSyncSyncCycle

#AADSync and FWDSync will create the target MEUs in the Target tenant
```
**Hoe krijgen we toegang tot Outlook dag 1 nadat het postvak voor gebruik is verplaatst?**

Aangezien slechts één tenant eigenaar kan zijn van een domein, wordt het voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doelten tenant wanneer het postvak wordt verplaatst. alleen de domeinen die zijn gekoppeld aan de nieuwe tenant. Outlook gebruikt de nieuwe UPN-gebruikers om zich te verifiëren bij de service en het Outlook-profiel verwacht dat het oudere primaire SMTPAddress wordt gevonden dat past bij het postvak in het doelsysteem. Aangezien het oudere adres niet in het doelsysteem staat, wordt er geen verbinding gemaakt met het Outlook-profiel om het zojuist verplaatste postvak te vinden.

Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN- en primaire SMTP-adres en ost-inhoud opnieuw synchroniseren.

> [!Note]
> Plan dezenovereenkomstig terwijl u uw gebruikers batcht voor voltooiing. U moet rekening houden met het netwerkgebruik en de capaciteit wanneer Outlook clientprofielen worden gemaakt en de volgende OST- en OAB-bestanden worden gedownload naar clients.

**Waar Exchange RBAC-rollen moet ik lid van zijn om een cross-tenantverzet in te stellen of te voltooien?**

Er is een matrix met rollen op basis van de aanname van gedelegeerde taken bij het uitvoeren van een postvakverhuis. Er zijn momenteel twee rollen vereist:

- De eerste rol is voor een een time setup-taak die de machtiging voor het verplaatsen van inhoud naar of buiten de tenant-organisatiegrens bepaalt. Aangezien het verplaatsen van gegevens uit uw organisatiebeheer een kritieke zorg is voor alle bedrijven, hebben we gekozen voor de hoogste toegewezen rol van Organisatiebeheerder (OrgAdmin). Deze rol moet een nieuwe Organisatierelationship wijzigen of instellen die definieert -MailboxMoveCapability met de externe organisatie. Alleen orgAdmin kan de instelling Postvakverzetbaarheid wijzigen, terwijl andere kenmerken op de OrganizationRelationhip kunnen worden beheerd door de beheerder van Federatief delen.

- De rol van het uitvoeren van de werkelijke opdrachten voor verplaatsen kan worden gedelegeerd aan een functie op lager niveau. Aan de rol van Postvakken verplaatsen wordt de mogelijkheid toegewezen om postvakken in of uit de organisatie te verplaatsen met behulp van de `-RemoteTenant` parameter.

**Hoe wordt het SMTP-adres geselecteerd voor targetAddress (TargetDeliveryDomain) in het geconverteerde postvak (naar MailUser-conversie)?**

Exchange met MRS maakt u het doeladres op het oorspronkelijke bronpostvak bij het converteren naar een MailUser door een e-mailadres (proxyAddress) op het doelobject te koppelen. Tijdens het proces wordt de waarde -TargetDeliveryDomain doorgegeven in de opdracht Verplaatsen en wordt vervolgens gecontroleerd op een overeenkomende proxy voor dat domein aan de doelzijde. Wanneer we een overeenkomst vinden, wordt de overeenkomende proxyAddress gebruikt om het object ExternalEmailAddress (targetAddress) in te stellen op het geconverteerde postvak (nu MailUser).

**Hoe kunnen postvakmachtigingen overstappen?**

Postvakmachtigingen zijn Verzenden namens en Postvaktoegang:

- Send On Behalf Of (AD:publicDelegates) slaat de DN op van geadresseerden met toegang tot het postvak van een gebruiker als gemachtigde. Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de postvakovergang. Als het bronpostvak openbareDelegates-set heeft, moet u de publicDelegates opnieuw op het doelpostvak opnieuwampen zodra de conversie van DEU naar postvak is voltooid in de doelomgeving door het uitvoeren `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` van .

- Postvakmachtigingen die zijn opgeslagen in het postvak, worden samen met het postvak verplaatst wanneer zowel de hoofdsom als de gedelegeerde naar het doelsysteem worden verplaatst. De gebruiker krijgt bijvoorbeeld TestUser_7 FullAccess toegewezen aan het postvak TestUser_8 in de tenant SourceCompany.onmicrosoft.com. Nadat het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doelmap. Voorbeelden met *Get-MailboxPermission* voor TestUser_7 in zowel bron- als doelten tenants worden hieronder weergegeven. Exchange cmdlets worden voorafgevoegd met bron en doel dienovereenkomstig.

Hier is een voorbeeld van de uitvoer van de postvakmachtiging vóór een verhuizing.

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
Hier is een voorbeeld van de uitvoer van de postvakmachtiging na de verhuizing.

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```

> [!Note]
> Machtigingen voor postvak met een kruis tenant en agenda worden NIET ondersteund. U moet principals en gedelegeerden organiseren in samengevoegde verplaatste batches, zodat deze verbonden postvakken tegelijk vanuit de bronten tenant worden overgeslagen.

**Welke X500-proxy moet worden toegevoegd aan de doel-MailUser-proxyadressen om migratie in te stellen?**

Voor de migratie van een postvak met verschillende tenants moet de LegacyExchangeDN-waarde van het bronpostvakobject worden afgestempeld als een x500-e-mailadres op het doelobject MailUser.

Voorbeeld:
```powershell
LegacyExchangeDN value on source mailbox is:
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara

so the x500 email address to be added to target MailUser object would be:
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara
```

> [!Note]
> Naast deze X500-proxy moet u alle X500-proxy's uit het postvak in de bron kopiëren naar het postvak in het doel.

**Waar kan ik problemen oplossen als het niet werkt?**

Begin met het uitvoeren van VerifySetup.ps1 script op [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en controleer de uitvoer.

Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

Hier is een eExample van het uitvoeren van VerifySetup.ps1 op de bron tenant:

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

**Kunnen de bron en doel tenant dezelfde domeinnaam gebruiken?**

Nee. De bron- en doel tenantdomeinnamen moeten uniek zijn. Bijvoorbeeld een brondomein van contoso.com en het doeldomein van fourthcoffee.com.

**Worden gedeelde postvakken verplaatst en werken ze nog steeds?**

Ja, maar we behouden alleen de winkelmachtigingen zoals beschreven in deze artikelen:

- [Microsoft Docs | Machtigingen voor geadresseerden beheren in Exchange Online](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [Microsoft Support | Machtigingen voor postvakken Exchange en Outlook in Office 365 toegewezen](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

**Is Azure Key Vault vereist en wanneer worden transacties uitgevoerd?**

Ja, een Azure-abonnement is vereist om Key Vault te gebruiken om het certificaat op te slaan om migratie te machtigen. In tegenstelling tot onboarding-migraties die gebruikersnaam & wachtwoord gebruiken om zich te verifiëren bij de bron, gebruiken migraties tussen tenantpostvakken OAuth en dit certificaat als geheim/referentie. Toegang tot de Sleutelkluis moet gedurende alle postvakmigraties worden behouden, omdat deze eenmaal aan het begin en het einde van de migratie wordt gebruikt, evenals eenmaal per 24 uur tijdens incrementele synchronisatietijden. U kunt hier de kostendetails van AKV [bekijken.](https://azure.microsoft.com/en-us/pricing/details/key-vault/)

**Hebt u aanbevelingen voor batches?**

Niet meer dan 2000 postvakken per batch. We raden ten zeerste aan om batches twee weken vóór de cut-overdatum in te dienen, omdat er geen gevolgen zijn voor de eindgebruikers tijdens de synchronisatie. Als u richtlijnen nodig hebt voor postvakken van meer dan 50.000, kunt u contact op met de distributielijst voor technische feedback op crosstenantmigrationpreview@service.microsoft.com.

**Wat moet ik doen als ik Serviceversleuteling gebruik met klantsleutel?**

Het postvak wordt ontsleuteld voordat u het verplaatst. Controleer of de klantsleutel is geconfigureerd in de doel tenant als deze nog steeds vereist is. Zie [hier](../compliance/customer-key-overview.md) voor meer informatie.

**Wat is de geschatte migratietijd?**

Om u te helpen bij [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) het plannen van uw migratie, bevat de tabel hier de richtlijnen over wanneer bulkpostvakmigraties of afzonderlijke migraties moeten worden voltooid. Deze schattingen zijn gebaseerd op een gegevensanalyse van eerdere klantmigraties. Omdat elke omgeving uniek is, kan de exacte migratiesnelheid variëren.

Vergeet niet dat deze functie momenteel in de preview-versie staat en dat de SLA en de toepasselijke serviceniveaus niet van toepassing zijn op prestatie- of beschikbaarheidsproblemen tijdens de preview-status van deze functie.

## <a name="known-issues"></a>Bekende problemen

-  **Probleem: Automatisch uitveerde archieven kunnen niet worden gemigreerd.** De migratiefunctie voor verschillende tenants ondersteunt migraties van het primaire postvak en archiefpostvak voor een specifieke gebruiker. Als de gebruiker in de bron echter een automatisch uitgebouwd archief heeft, wat meer dan één archiefpostvak betekent, kan de functie de extra archieven niet migreren en mislukt deze.

- **Probleem: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.** Wanneer u doelten tenant MailUser-objecten maakt, moet u ervoor zorgen dat alle SMTP-proxyadressen behoren tot de doeltenatororganisatie. Als er een SMTP-proxyAddress bestaat op de doelmailgebruiker die niet tot de lokale tenant behoort, wordt de conversie van de MailUser naar Postvak voorkomen. Dit komt door onze garantie dat postvakobjecten alleen e-mail kunnen verzenden van domeinen waarvoor de tenant gezaghebbend is (domeinen die door de tenant worden geclaimd):

   - Wanneer u gebruikers synchroniseert vanuit on-premises gebruik van Azure AD Verbinding maken, kunt u on-premises MailUser-objecten inrichten met ExternalEmailAddress die verwijst naar de brontenator waar het postvak bestaat (laran@contoso.onmicrosoft.com) en u stempelt het PrimarySMTPAddress als een domein dat zich in de doeltenator bevindt (Lara.Newton@northwind.com). Deze waarden worden gesynchroniseerd met de tenant en een geschikte e-mailgebruiker is ingericht en klaar voor migratie. Hier wordt een voorbeeldobject weergegeven.
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses
     ExternalEmailAddress               EmailAddresses
     --------------------               --------------
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com}
     ```

   > [!Note]
   > Het *contoso.onmicrosoft.com* adres is *niet aanwezig* in de matrix EmailAddresses/proxyAddresses.

- **Probleem: MailUser-objecten met 'externe' primaire SMTP-adressen worden gewijzigd /opnieuw ingesteld op 'interne' geclaimde domeinen van het bedrijf**

   MailUser-objecten zijn aanwijzers naar niet-lokale postvakken. In het geval van migraties tussen tenantpostvakken gebruiken we MailUser-objecten om het bronpostvak (vanuit het perspectief van de doelorganisatie) of het doelpostvak weer te geven (vanuit het perspectief van de bronorganisatie). De MailUsers hebben een ExternalEmailAddress (targetAddress) die wijst naar het smtp-adres van het werkelijke postvak (ProxyTest@fabrikam.onmicrosoft.com) en het primaireSMTP-adres dat het weergegeven SMTP-adres van de postvakgebruiker in de adreslijst vertegenwoordigt. Sommige organisaties kiezen ervoor om het primaire SMTP-adres weer te geven als een extern SMTP-adres, niet als een adres dat eigendom is van/wordt geverifieerd door de lokale tenant (zoals fabrikam.com in plaats van als contoso.com).  Wanneer echter een Exchange-serviceplanobject via licentiebewerkingen op de MailUser wordt toegepast, wordt het primaire SMTP-adres gewijzigd om weer te geven als een domein dat is geverifieerd door de lokale organisatie (contoso.com). Er zijn twee mogelijke redenen:

   - Wanneer een Exchange-serviceplan wordt toegepast op een MailUser, wordt het Azure AD-proces gestart met het afdwingen van proxyschrof om ervoor te zorgen dat de lokale organisatie geen e-mail kan verzenden, spoofing of e-mail van een andere tenant. Elk SMTP-adres op een geadresseerdeobject met deze serviceplannen wordt verwijderd als het adres niet wordt geverifieerd door de lokale organisatie. Zoals in het voorbeeld het geval is, wordt het Fabikam.com niet geverifieerd door de contoso.onmicrosoft.com tenant, dus wordt het fabrikam.com verwijderd. Als u dit externe domein op MailUser wilt blijven gebruiken, vóór de migratie of na de migratie, moet u uw migratieprocessen wijzigen om licenties te strippen nadat de verhuizing is voltooid of vóór de verhuizing om ervoor te zorgen dat de verwachte externe huisstijl is toegepast op de gebruikers. U moet ervoor zorgen dat het postvakobject een juiste licentie heeft om de e-mailservice niet te beïnvloeden.<br/><br/>Hier wordt een voorbeeldscript weergegeven om de serviceplannen op een MailUser in Contoso.onmicrosoft.com tenant te verwijderen.

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION"
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo
    ```

       De resultaten in de set serviceplannen die zijn toegewezen, worden hier weergegeven.

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

       Het PrimarySMTPAddress van de gebruiker wordt niet meer geschuurd. Het fabrikam.com domein is niet eigendom van de contoso.onmicrosoft.com tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.

       Hier volgt een voorbeeld.

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress
    ------------------        -------------------------               --------------------
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com
    ```

   - Wanneer msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), voor on-premises MailUsers die worden gemigreerd naar de doeltenant, worden met de proxyschrootlogica in Azure niet-geeigende domeinen verwijderd en wordt de primaireSMTP opnieuw ingesteld op een eigendomsdomein. Door msExchRemoteRecipientType in de on-premises MailUser te wissen, is de proxyscrublogica niet meer van toepassing. <br/><br>Hieronder vindt u de volledige set mogelijke serviceplannen met Exchange Online.

   | Naam                                              |
   |---------------------------------------------------|
   | Advanced eDiscovery Storage (500 GB)               |
   | Klanten-lockbox                                  |
   | Preventie van gegevensverlies                              |
   | Exchange Enterprise CAL-services (EOP, DLP)       |
   | Exchange Essentials                               |
   | Exchange Foundation                               |
   | Exchange Online (P1)                              |
   | Exchange Online (Abonnement 1)                          |
   | Exchange Online (Abonnement 2)                          |
   | Exchange Online Archiving voor Exchange Online     |
   | Exchange Online Archiving voor Exchange Server     |
   | Exchange Online Inactieve gebruikersinvoegvoeging              |
   | Exchange Online Kiosk                             |
   | Exchange Online Multi-Geo                         |
   | Exchange Online Abonnement 1                            |
   | Exchange Online POP                               |
   | Exchange Online Protection                        |
   | Informatiebarrières                              |
   | Informatiebeveiliging voor Office 365 - Premium   |
   | Informatiebeveiliging voor Office 365 - Standaard  |
   | Insights door MyAnalytics                           |
   | Microsoft 365 Geavanceerd controleren                   |
   | Microsoft Bookings                                |
   | Microsoft Business Center                         |
   | Microsoft MyAnalytics (Volledig)                      |
   | Office 365 Advanced eDiscovery                    |
   | Microsoft Defender voor Office 365 (Abonnement 1)    |
   | Microsoft Defender voor Office 365 (Abonnement 2)    |
   | Office 365 Privileged Access Management           |
   | Premium Versleuteling in Office 365                  |
