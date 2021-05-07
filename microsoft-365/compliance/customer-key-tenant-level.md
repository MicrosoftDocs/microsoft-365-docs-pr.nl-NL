---
title: Klantsleutel voor Microsoft 365 op tenantniveau (openbare preview)
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Meer informatie over het instellen van klantcode voor uw gegevens binnen Microsoft 365 op tenantniveau.
ms.openlocfilehash: 90ad08059d6b71583850368a70e32167b9defe88
ms.sourcegitcommit: d3f8c69519c593b1580cfa7187ce085a99b8a846
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162861"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Overzicht van klantsleutel voor Microsoft 365 op tenantniveau (openbare preview)

Met behulp van de door u op te geven sleutels kunt u een dep (Data Encryption Policy) maken en deze toewijzen aan de tenant. De tenantbrede DEP die u maakt, versleutelt de volgende gegevens:

- Teams chatberichten (1:1 chats, groepschats, vergaderingschats en kanaalgesprekken)
- Teams mediaberichten (afbeeldingen, codefragmenten, videoberichten, audioberichten, wikiafbeeldingen)
- Teams gespreks- en vergaderingsopnamen die zijn opgeslagen in Teams opslag
- Teams chatmeldingen
- Teams chatsuggesties van Cortana
- Teams statusberichten
- Gebruikers- en signaalgegevens voor Exchange Online
- Exchange Online postvakken die nog niet zijn versleuteld klantcode-DEP's op toepassingsniveau
- MIP-gegevens komen exact overeen met EDM-gegevens (gegevensbestandsschema's, regelpakketten en de zouten die worden gebruikt om de gevoelige gegevens te hashen)

Voor Microsoft Information Protection en Microsoft Teams versleutelt Klantsleutel op tenantniveau nieuwe gegevens vanaf het moment dat u de DEP aan de tenant toewijst. Openbare preview biedt geen ondersteuning voor het versleutelen van eerdere gegevens. Voor Exchange Online versleutelt Customer Key alle bestaande en nieuwe gegevens.

U kunt meerdere DEP's per tenant maken, maar u kunt slechts één DEP tegelijk toewijzen. Wanneer u het DEP toewijst, wordt de versleuteling automatisch gestart, maar duurt het enige tijd, afhankelijk van de grootte van de tenant.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Beleid op tenantniveau voegt bredere controle toe aan klantsleutel voor Microsoft 365

Als u klantsleutel al hebt ingesteld voor Exchange Online en Sharepoint Online, past de nieuwe openbare preview op tenantniveau als eerste in de lijst.

Met het versleutelingsbeleid op tenantniveau dat u maakt, worden alle gegevens voor de Microsoft Teams en Exchange Online in Microsoft 365. Als u echter Exchange Online klantsleutelDEP's al aan afzonderlijke postvakken hebt toegewezen, worden deze DEP's niet overgenomen door het tenantbeleid. Het beleid op tenantniveau versleutelt alleen postvakken die nog geen klantcode-DEP op postvakniveau zijn toegewezen. Wanneer u een gebruikerspostvak versleutelt met behulp van een dep op tenantniveau, wordt alle inhoud versleuteld. Zie [Serviceversleuteling met klantsleutel](customer-key-overview.md)voor informatie over wat wordt versleuteld met een DEP op toepassingsniveau.

## <a name="data-that-isnt-encrypted-with-customer-key-at-the-tenant-level"></a>Gegevens die niet zijn versleuteld met klantsleutel op tenantniveau

Klantsleutel versleutelt de volgende typen gegevens niet op tenantniveau. In plaats Microsoft 365 andere typen versleuteling gebruikt om deze gegevens te beveiligen.

- Exchange onlinepostvakken die u al hebt versleuteld met behulp van een klantcodedep op toepassingsniveau. Postvakken die niet zijn toegewezen aan een KLANTCODE-DEP, worden versleuteld met behulp van de TENANT-dep op tenantniveau. Deze indeling betekent dat sommige postvakken mogelijk zijn versleuteld met een DEP op tenantniveau en sommige postvakken zijn versleuteld met DEP's op toepassingsniveau.
- SharePoint en OneDrive voor Bedrijven klantcode gebruiken op toepassingsniveau. Eén DEP versleutelt inhoud in SharePoint voor één geo.
- Microsoft Teams bestanden en sommige Teams gespreks- en vergaderingsopnamen die zijn opgeslagen in OneDrive voor Bedrijven en SharePoint worden versleuteld door een SharePoint OnlineDEP.

Werkbelastingen of scenario's die momenteel niet worden ondersteund door Customer Key voor Microsoft 365.

- Andere Microsoft 365 werkbelastingen zoals Yammer, Planner, en dergelijke.
- Teams Livegebeurtenissen en Q&A in Live Events. Voor Teams is dit scenario het enige scenario dat niet is versleuteld door Klantsleutel op tenantniveau.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Klantsleutel instellen op tenantniveau (openbare preview)

Deze stappen zijn vergelijkbaar, maar niet identiek aan de stappen voor het instellen van klantsleutel op toepassingsniveau. Gebruik deze openbare preview alleen met testgegevens in testtententen. Gebruik deze release niet met productiegegevens of in uw productieomgeving. Als u al een productie-implementatie van klantsleutel hebt, gebruikt u deze stappen om Klantsleutel in te stellen op tenantniveau in een testomgeving. Nadat u een TENANT-dep op tenantniveau hebt toegewezen aan uw tenant, kunt u het validatieproces starten en contact opnemen met m365ck@microsoft.com vragen of zorgen. U kunt ook gedocumenteerde validatiestappen vinden in het openbare voorbeeld van Validatie-instructies voor [gegevens-at-restversleuteling voor Microsoft 365.](https://aka.ms/CustomerKey/PublicPreviewValidation)

U voltooit de meeste van deze taken door op afstand verbinding te maken met Azure PowerShell. Voor de beste resultaten gebruikt u versie 4.4.0 of hoger van Azure PowerShell.

Voordat u begint:

- U moet een werk- of schoolaccount met de rol compliancebeheerder gebruiken om Klantsleutel in te stellen op tenantniveau.
- Zorg ervoor dat u over de juiste licenties voor uw organisatie hebt. Gebruik een betaald, gefactureerd Azure-abonnement met een Enterprise Agreement of een cloudserviceprovider. Azure-abonnementen die zijn gekocht met abonnementen voor betalen terwijl u gaat of een creditcard gebruiken, worden niet ondersteund voor Klantcode. Vanaf 1 april 2020 wordt klantsleutel in Office 365 aangeboden in Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance en Microsoft 365 E5 Information Protection & Governance SKU's. Office 365 Advanced Compliance SKU is niet meer beschikbaar voor nieuwe licenties. Bestaande Office 365 Advanced Compliance licenties blijven worden ondersteund. Hoewel de service kan worden ingeschakeld met minimaal één gebruiker met de juiste licentie onder de tenant, moet u ervoor zorgen dat alle gebruikers die profiteren van de service over de juiste licenties beschikt.

### <a name="create-two-new-azure-subscriptions"></a>Twee nieuwe Azure-abonnementen maken

Klantsleutel vereist twee sleutels voor elk gegevensversleutelingsbeleid (DEP). Als u twee sleutels wilt maken, moet u twee Azure-abonnementen maken. Als aanbevolen training raadt Microsoft aan dat u afzonderlijke leden van uw organisatie hebt om één sleutel in elk abonnement te configureren. Gebruik deze Azure-abonnementen alleen om versleutelingssleutels voor Microsoft 365. Door deze richtlijnen te volgen, kunt u uw organisatie beschermen als een van uw operatoren per ongeluk, opzettelijk of met opzet de sleutels waarvoor ze verantwoordelijk zijn, verwijdert of anderszins onjuist bemant.

Er is geen praktische limiet voor het aantal Azure-abonnementen dat u voor uw organisatie kunt maken. Met deze best practice kunt u de impact van menselijke fouten minimaliseren en tegelijkertijd de resources beheren die door Klantsleutel worden gebruikt.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure-abonnementen registreren om een verplichte bewaarperiode te gebruiken

Het tijdelijke of permanente verlies van hoofdversleutelingssleutels kan storend of zelfs catastrofaal zijn voor de servicebewerking en kan leiden tot gegevensverlies. Om deze reden vereisen de resources die met Klantsleutel worden gebruikt, een sterke beveiliging. Alle Azure-resources die worden gebruikt met Customer Key bieden beschermingsmechanismen buiten de standaardconfiguratie. Azure-abonnementen kunnen worden gelabeld of geregistreerd op een manier die onmiddellijke en onherroepelijke annulering voorkomt. Dit proces wordt ook wel registratie voor een verplichte bewaarperiode genoemd. De stappen die nodig zijn om Azure-abonnementen te registreren voor een verplichte bewaarperiode, vereisen samenwerking met Microsoft. Dit proces kan maximaal vijf werkdagen duren. Voorheen werd dit proces ook wel 'Niet annuleren' genoemd.
  
Voordat u contact op neemt met Microsoft 365 team, moet u de volgende stappen uitvoeren voor elk Azure-abonnement dat u gebruikt met klantcode. Zorg ervoor dat u de [Azure PowerShell Az-module](/powershell/azure/new-azureps-module-az) hebt geïnstalleerd voordat u begint.

1. Meld u aan met Azure PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

2. Voer de Register-AzProviderFeature cmdlet uit om uw abonnementen te registreren om een verplichte bewaarperiode te gebruiken. Voer deze actie uit voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Neem contact op met Microsoft om het proces bij [m365ck@microsoft.com.](mailto:m365ck@microsoft.com) Neem de volgende inhoud op in uw e-mail:

   **Onderwerp**: Klantcode voor \<*Your tenant's fully-qualified domain name*\>

   **Body**: Abonnement-1D's waarvoor u de verplichte bewaarperiode wilt laten afsluiten.
   De uitvoer van Get-AzProviderFeature voor elk abonnement.

   De SLA (Service Level Agreement) voor het voltooien van dit proces is vijf werkdagen nadat Microsoft is geïnformeerd (en geverifieerd) dat u uw abonnementen hebt geregistreerd om een verplichte bewaarperiode te gebruiken.

4. Nadat u een melding van Microsoft hebt ontvangen dat de registratie is voltooid, controleert u de status van uw registratie door de opdracht Get-AzProviderFeature uitvoeren als volgt. Als dit is geverifieerd, Get-AzProviderFeature opdracht een waarde als resultaat **geregistreerd** voor de eigenschap **Registratiestaat.** Voer deze actie uit voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Als u het proces wilt voltooien, kunt u de opdracht Register-AzResourceProvider uitvoeren. Voer deze actie uit voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Een premium Azure Key Vault maken in elk abonnement

De stappen voor het maken van een sleutelkluis worden beschreven in Aan de slag met [Azure Key Vault,](/azure/key-vault/general/overview)die u begeleidt bij het installeren en starten van Azure PowerShell, het maken van verbinding met uw Azure-abonnement, het maken van een resourcegroep en het maken van een sleutelkluis in die resourcegroep.
  
Wanneer u een sleutelkluis maakt, moet u een SKU kiezen: standaard of Premium. Met de SKU-standaard kunnen Azure Key Vault-sleutels worden beveiligd met software - er is geen HSM-sleutelbeveiliging (Hardware Security Module) en met de Premium-SKU kunnen HSM's worden gebruikt ter bescherming van Key Vault-sleutels. Klantsleutel accepteert sleutelkluizen die SKU gebruiken, maar Microsoft raadt ten zeerste aan dat u alleen de Premium SKU gebruikt. De kosten van bewerkingen met sleutels van beide typen zijn hetzelfde, dus het enige verschil in kosten is de kosten per maand voor elke met HSM beveiligde sleutel. Zie [Key Vault-prijzen](https://azure.microsoft.com/pricing/details/key-vault/) voor meer informatie.
  
> [!IMPORTANT]
> Gebruik de Premium SKU-sleutelkluizen en HSM-beveiligde sleutels voor productiegegevens en gebruik alleen standaard SKU-sleutelkluizen en -sleutels voor test- en validatiedoeleinden.

Gebruik een gemeenschappelijk voorvoegsel voor sleutelkluizen en voeg een afkorting toe van het gebruik en het bereik van de sleutelkluis en -sleutels. Voor de Contoso-service waar de gewelven zich bijvoorbeeld in Noord-Amerika bevinden, is een mogelijk paar namen Contoso-O365-NA-VaultA1 en Contoso-O365-NA-VaultA2. Kluisnamen zijn wereldwijd unieke tekenreeksen binnen Azure, dus mogelijk moet u variaties van de gewenste namen proberen voor het geval de gewenste namen al worden geclaimd door andere Azure-klanten. Nadat de kluisnamen zijn geconfigureerd, kunnen de namen van de kluis niet worden gewijzigd. De beste manier is om een schriftelijk plan voor de installatie te hebben en een tweede persoon te gebruiken om te controleren of het plan correct wordt uitgevoerd.

Maak indien mogelijk uw kluizen in niet-gekoppelde regio's. Gekoppelde Azure-regio's bieden hoge beschikbaarheid voor servicefoutdomeinen. Daarom kunnen regionale paren worden gebruikt als elkaars back-upgebied. Een Azure-resource die in één regio wordt geplaatst, krijgt automatisch fouttolerantie via het gekoppelde gebied. Als u regio's kiest voor twee kluizen die worden gebruikt in een gegevensversleutelingsbeleid waarin de regio's zijn gekoppeld, wordt slechts een totaal van twee beschikbaarheidsregio's gebruikt. De meeste regio's hebben slechts twee regio's, dus het is nog niet mogelijk om niet-gekoppelde regio's te selecteren. Kies indien mogelijk twee niet-gekoppelde regio's voor de twee kluizen die worden gebruikt met een gegevensversleutelingsbeleid. Dit scenario profiteert van een totaal van vier regio's met beschikbaarheid. Zie Business Continuity and Disaster Recovery (BCDR): Azure Paired Regions for a current list of regional pairs [(Business continuity and disaster recovery( BCDR): Azure Paired Regions (Business Continuity and Disaster Recovery( BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) (Business Continuity and Disaster Recovery) voor een huidige lijst met regionale paren.

### <a name="assign-permissions-to-each-key-vault"></a>Machtigingen toewijzen aan elke sleutelkluis

Voor elke sleutelkluis moet u drie afzonderlijke sets machtigingen voor klantsleutel definiëren, afhankelijk van uw implementatie. U moet bijvoorbeeld één set machtigingen definiëren voor elk van deze machtigingen:
  
- **Key vault administrators** that will perform day-to-day management of your key vault for your organization. Deze taken omvatten back-up maken, maken, krijgen, importeren, lijst en herstellen.

  > [!IMPORTANT]
  > De set machtigingen die is toegewezen aan beheerders van de sleutelkluis, bevat niet de machtiging om sleutels te verwijderen. Dit is opzettelijk en een belangrijke oefening. Het verwijderen van versleutelingssleutels gebeurt meestal niet, omdat hierdoor gegevens permanent worden vernietigd. Als een goede gewoonte, verleent u deze machtiging niet standaard aan beheerders van de sleutelkluis. Reserveer dit in plaats daarvan voor sleutelkluiscontribuanten en wijs deze alleen op korte termijn toe aan een beheerder zodra een duidelijk begrip van de gevolgen is begrepen.
  
  Als u deze machtigingen wilt toewijzen aan een gebruiker in uw organisatie, meld u zich aan bij uw Azure-abonnement met Azure PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

   Voer de Set-AzKeyVaultAccessPolicy cmdlet uit om de benodigde machtigingen toe te wijzen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Bijvoorbeeld:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Key vault contributors** that can change permissions on the Azure Key Vault itself. U moet deze machtigingen wijzigen wanneer werknemers uw team verlaten of lid worden, of in de zeldzame situatie dat de beheerders van de sleutelkluis rechtmatig machtigingen nodig hebben om een sleutel te verwijderen of te herstellen. Aan deze set sleutelkluisbijdragers moet de rol Inzender in uw sleutelkluis worden verleend. U kunt deze rol toewijzen met Behulp van Azure Resource Manager. Zie Toegangsbeheer gebruiken Role-Based [toegang](/azure/active-directory/role-based-access-control-configure) tot uw Azure-abonnementsbronnen voor gedetailleerde stappen. De beheerder die een abonnement maakt, heeft deze standaardtoegang en de mogelijkheid om andere beheerders toe te wijzen aan de rol Inzender.

- **Microsoft 365 gegevens bij de restversleutelingsservice** die het werk van klantsleutel op tenantniveau doen. Als u toestemming wilt geven Microsoft 365 u de **cmdlet Set-AzKeyVaultAccessPolicy** uit met de volgende syntaxis:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Waarbij:

  - *de naam van* de kluis is de naam van de sleutelkluis die u hebt gemaakt.

  Voorbeeld: Voor de Microsoft 365 bij restversleutelingsservice, vervangt u *Microsoft 365 appID* door`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Soft Delete inschakelen en vervolgens bevestigen in uw sleutelkluizen

Wanneer u snel uw sleutels kunt herstellen, is de kans kleiner dat u te maken krijgt met een uitgebreide servicestoring als gevolg van per ongeluk of met opzet verwijderde sleutels. Schakel deze configuratie in, ook wel Soft Delete genoemd, in voordat u uw sleutels kunt gebruiken met klantsleutel. Als u Soft Delete inschakelen, kunt u sleutels of kluizen binnen 90 dagen na verwijdering herstellen zonder ze terug te moeten halen uit een back-up.
  
Als u Soft Delete wilt inschakelen in uw sleutelkluizen, gaat u als volgende stappen te werk:
  
1. Meld u aan bij uw Azure-abonnement met Windows PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

2. Voer de [Get-AzKeyVault-cmdlet](/powershell/module/az.keyvault/get-azkeyvault) uit. In dit voorbeeld is *de naam van de* kluis de naam van de sleutelkluis waarvoor u soft delete inschakelen:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bevestig dat soft delete is geconfigureerd voor de sleutelkluis door de **Get-AzKeyVault-cmdlet** uit te lopen. Als soft delete correct is geconfigureerd voor de sleutelkluis, geeft de eigenschap _Soft Delete Enabled_ een waarde van **Waar als resultaat:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Een sleutel toevoegen aan elke sleutelkluis door een sleutel te maken of te importeren

Er zijn twee manieren om sleutels toe te voegen aan een Azure Key Vault. u kunt een sleutel rechtstreeks in de Sleutelkluis maken of u kunt een sleutel importeren. Het rechtstreeks maken van een sleutel in Key Vault is de minder ingewikkelde methode, terwijl het importeren van een sleutel totale controle biedt over de manier waarop de sleutel wordt gegenereerd. Gebruik de RSA-toetsen. Azure Key Vault biedt geen ondersteuning voor het terugpakken en uitpakken met elliptische curvetoetsen.
  
Als u een sleutel rechtstreeks in de sleutelkluis wilt maken, kunt u de [cmdlet Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) als volgt uitvoeren:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Waarbij:

- *de naam van* de kluis is de naam van de sleutelkluis waarin u de sleutel wilt maken.

- *sleutelnaam* is de naam die u de nieuwe sleutel wilt geven.

  > [!TIP]
  > Naamtoetsen met een vergelijkbare naamgevingsconventie zoals hierboven beschreven voor sleutelkluizen. Op deze manier wordt in hulpmiddelen die alleen de sleutelnaam laten zien, de tekenreeks zelfbeschreven.
  
Als u de sleutel wilt beveiligen met een HSM, moet u **HSM** opgeven als de waarde van de parameter _Doel,_ anders geeft u **Software op.**

Bijvoorbeeld:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Het herstelniveau van uw sleutels controleren

Microsoft 365 vereist dat het Azure Key Vault-abonnement is ingesteld op Niet annuleren en dat de sleutels die door Klantsleutel worden gebruikt, soft delete hebben ingeschakeld. U kunt deze instellingen bevestigen door te kijken naar het herstelniveau op uw toetsen.
  
Als u het herstelniveau van een sleutel wilt controleren, Azure PowerShell u de Get-AzKeyVaultKey als volgt uit:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Als  de eigenschap Herstelniveau iets anders retourneert dan een waarde van **Herstelbaar+ProtectedSubscription,** moet u dit artikel bekijken en ervoor zorgen dat u alle stappen hebt gevolgd om het abonnement in de lijst Niet annuleren te zetten en dat u 'soft delete' hebt ingeschakeld in elk van uw sleutelkluizen. Stuur vervolgens een schermafbeelding van de uitvoer `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` van in e-mail naar m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Back-up maken van Azure Key Vault

Direct na het maken of wijzigen van een sleutel kunt u een back-up maken van de sleutel en kopieën van de back-up opslaan, zowel online als offline. Maak geen verbinding met offlinekopieen met een netwerk. Bewaar ze in plaats daarvan in een fysieke veilige of commerciële opslaglocatie. Ten minste één kopie van de back-up moet worden opgeslagen op een locatie die toegankelijk is als er een ramp gebeurt. De back-up blobs zijn het enige middel om sleutelmateriaal te herstellen als een Sleutelkluissleutel permanent wordt vernietigd of anderszins niet meer kan worden gebruikt. Sleutels die extern zijn in Azure Key Vault en zijn geïmporteerd in Azure Key Vault komen niet in aanmerking als back-up, omdat de metagegevens die nodig zijn om de sleutel te gebruiken, niet aanwezig zijn met de externe sleutel. Alleen een back-up van Azure Key Vault kan worden gebruikt voor het herstellen van bewerkingen met klantsleutel. Het is dus essentieel dat u een back-up maakt van Azure Key Vault zodra een sleutel is geüpload of gemaakt.
  
Als u een back-up wilt maken van een Azure Key Vault-sleutel, moet u de [cmdlet Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) als volgt uitvoeren:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Zorg ervoor dat het achtervoegsel wordt gebruikt in het `.backup` uitvoerbestand.
  
Het uitvoerbestand dat het resultaat is van deze cmdlet, is versleuteld en kan niet buiten Azure Key Vault worden gebruikt. De back-up kan alleen worden hersteld naar het Azure-abonnement waaruit de back-up is gemaakt.
  
Bijvoorbeeld:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Configuratie-instellingen voor Azure Key Vault valideren

Validatie uitvoeren voordat u toetsen in een DEP gebruikt, is optioneel, maar ten zeerste aanbevolen. Als u met name stappen gebruikt om uw sleutels en kluizen in te stellen, anders dan de sleutels die in dit onderwerp worden beschreven, moet u de status van uw Azure Key Vault-resources valideren voordat u Klantcode configureert.
  
Als u wilt controleren of de sleutels zijn ingeschakeld, kunt u de sleutelbewerkingen terugpakken en uitpakken:
  
Voer de [Get-AzKeyVault-cmdlet](/powershell/module/az.keyvault/get-azkeyvault) als volgt uit:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Zoek in de uitvoer naar het Access-beleid en naar de Microsoft 365 app-id (GUID). Alle drie bewerkingen, ophalen, terugpakkenKey en uitpakkenKey, moeten worden weergegeven onder Machtigingen voor sleutels.
  
Als de configuratie van het toegangsbeleid onjuist is, kunt u de Set-AzKeyVaultAccessPolicy als volgt uitvoeren:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Voorbeeld: Voor de Microsoft 365 bij restversleutelingsservice, vervangt u *Microsoft 365 appID* door`c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Als u wilt controleren of er geen vervaldatum is ingesteld voor uw sleutels, moet u de [cmdlet Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) als volgt uitvoeren:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Een verlopen sleutel kan niet worden gebruikt door De klantsleutel en bewerkingen die worden uitgevoerd met een verlopen sleutel, mislukken en kunnen leiden tot een servicestoring. Het is ten zeerste raadzaam dat sleutels die worden gebruikt met klantcode, geen vervaldatum hebben. Een vervaldatum, eenmaal ingesteld, kan niet worden verwijderd, maar kan worden gewijzigd in een andere datum. Als een sleutel moet worden gebruikt met een vervaldatumset, wijzigt u de vervaldatum in 31-12-9999. Toetsen met een vervaldatum die is ingesteld op een andere datum dan 31-12-9999, worden niet door Microsoft 365 gevalideerd.
  
Als u een vervaldatum wilt wijzigen die is ingesteld op een andere waarde dan 31-12-9999, moet u de [cmdlet Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) als volgt uitvoeren:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>De URI verkrijgen voor elke Azure Key Vault-toets

Nadat u alle stappen in Azure hebt voltooid om uw sleutelkluizen in te stellen en uw sleutels hebt toegevoegd, kunt u de volgende opdracht uitvoeren om de URI voor de sleutel in elke sleutelkluis te krijgen. U moet deze URL's gebruiken wanneer u elke DEP later maakt en toewijst, dus sla deze informatie op een veilige plaats op. Vergeet niet om deze opdracht eenmaal uit te voeren voor elke sleutelkluis.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Het versleutelingsbeleid voor klantsleutels instellen voor uw tenant

U moet machtigingen hebben toegewezen voordat u deze cmdlets kunt uitvoeren. Hoewel in dit artikel alle parameters voor de cmdlets worden vermeld, hebt u mogelijk geen toegang tot bepaalde parameters als deze niet zijn opgenomen in de machtigingen die aan u zijn toegewezen. Zie De machtigingen zoeken die nodig zijn voor het uitvoeren van een cmdlet of parameter in uw organisatie als u de machtigingen wilt zoeken die nodig zijn voor het uitvoeren van een [cmdlet Exchange cmdlet.](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions)

### <a name="create-policy"></a>Beleid maken

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

Beschrijving: Schakel compliancebeheerder in om een nieuw dep-beleid (Data Encryption Policy) te maken met twee AKV-hoofdsleutels. Wanneer u een beleid hebt gemaakt, kunt u vervolgens een beleid Set-M365DataAtRestEncryptionPolicyAssignment cmdlet. Bij de eerste toewijzing van sleutels of nadat u de toetsen hebt gedraaid, kan het tot 24 uur duren voordat de nieuwe toetsen van kracht worden. Als het langer dan 24 uur duurt voordat de nieuwe DEP van kracht wordt, neemt u contact op met Microsoft.

Voorbeeld:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parameters:

| Naam | Beschrijving | Optioneel (Y/N) |
|----------|----------|---------|
|Naam|Vriendelijke naam van het gegevensversleutelingsbeleid|N|
|AzureKeyIDs|Geeft twee URI-waarden van de Azure Key Vault-sleutels op, gescheiden door een komma, om te koppelen aan het gegevensversleutelingsbeleid|N|
|Beschrijving|Beschrijving van het gegevensversleutelingsbeleid|N|

### <a name="assign-policy"></a>Beleid toewijzen

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

Beschrijving: Deze cmdlet wordt gebruikt voor het configureren van standaardbeleid voor gegevensversleuteling. Dit beleid wordt gebruikt om gegevens vervolgens te versleutelen voor alle ondersteuningswerkbelastingen.

Voorbeeld:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

Parameters:

| Naam | Beschrijving | Optioneel (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|Hiermee geeft u het gegevensversleutelingsbeleid op dat moet worden toegewezen. geef de beleidsnaam of de beleids-id op.|N|

### <a name="modify-or-refresh-policy"></a>Beleid wijzigen of vernieuwen

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Beschrijving: De cmdlet kan worden gebruikt om een bestaand beleid te wijzigen of te vernieuwen. Het kan ook worden gebruikt om een beleid in of uit te schakelen. Bij de eerste toewijzing van sleutels of nadat u de toetsen hebt gedraaid, kan het tot 24 uur duren voordat de nieuwe toetsen van kracht worden. Als het langer dan 24 uur duurt voordat de nieuwe DEP van kracht wordt, neemt u contact op met Microsoft.

Voorbeelden:

Een gegevensversleutelingsbeleid uitschakelen.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Een gegevensversleutelingsbeleid vernieuwen.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

Parameters:

| Naam | Beschrijving | Optioneel (Y/N) |
|----------|----------|---------|
|-Identiteit|Hiermee geeft u het gegevensversleutelingsbeleid op dat u wilt wijzigen.|N|
|-Vernieuwen|Gebruik de schakelknop Vernieuwen om het gegevensversleutelingsbeleid bij te werken nadat u een van de bijbehorende sleutels in de Azure Key Vault hebt gedraaid. U hoeft geen waarde op te geven met deze schakelknop.|Y|
|-Ingeschakeld|Met de parameter Ingeschakeld wordt het gegevensversleutelingsbeleid in- of uitgeschakeld. Voordat u een beleid uit schakelt, moet u het uit uw tenant verwijderen. Geldige waarden zijn:</br > $true: Het beleid is ingeschakeld</br > $false: Het beleid is uitgeschakeld.|Y|
|-Naam|De parameter Naam geeft de unieke naam voor het gegevensversleutelingsbeleid aan.|Y|
|-Beschrijving|De parameter Beschrijving geeft een optionele beschrijving voor het gegevensversleutelingsbeleid aan.|Y|

### <a name="get-policy-details"></a>Beleidsdetails bekijken

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Beschrijving: Deze cmdlet bevat alle M365DataAtRest-versleutelingsbeleidsregels die zijn gemaakt voor de tenant of details over een specifiek beleid.

Voorbeelden:

In dit voorbeeld wordt een overzichtslijst met M365DatAtRest-versleutelingsbeleid in de organisatie weergegeven.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

Dit voorbeeld retourneert gedetailleerde informatie voor het gegevensversleutelingsbeleid met de naam 'NAM-beleid'.

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parameters:

| Naam | Beschrijving | Optioneel (Y/N) |
|----------|----------|---------|
|-Identiteit|Hiermee geeft u het gegevensversleutelingsbeleid op waar u de details voor wilt gebruiken.|Y|

### <a name="get-policy-assignment-info"></a>Informatie over beleidstoewijzingen

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Beschrijving: Deze cmdlet bevat het beleid dat momenteel aan de tenant is toegewezen.

## <a name="offboarding-from-customer-key-at-the-tenant-level"></a>Offboarding van klantsleutel op tenantniveau

Als u wilt terugkeren naar door Microsoft beheerde sleutels, kunt u dit doen. Wanneer u offboard bent, worden uw gegevens opnieuw versleuteld met behulp van standaardversleuteling die door elke afzonderlijke werkbelasting wordt ondersteund. Zo ondersteunt Exchange Online standaardversleuteling met behulp van door Microsoft beheerde sleutels.

Als u besluit om uw tenant van klantsleutel op tenantniveau te verwijderen, wordt een [e-mail](mailto:m365ck@microsoft.com) m365ck@microsoft.com met een verzoek om de service voor de tenant uit te schakelen.

> [!IMPORTANT]
> Offboarding is niet hetzelfde als een gegevens purge. Met een gegevens purge worden de gegevens van uw organisatie definitief verwijderd uit Microsoft 365, offboarding niet. U kunt geen gegevens verwijderen voor een tenantbeleid. Zie Uw sleutels intrekken en het proces voor het gegevensre purgepad starten voor informatie over het pad voor [gegevensre purge.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)

## <a name="about-the-availability-key"></a>Informatie over de beschikbaarheidscode

Zie Meer informatie over de beschikbaarheidscode voor meer informatie over [de beschikbaarheidscode.](customer-key-availability-key-understand.md)

## <a name="key-rotation"></a>Draaiing van toetsen

Zie Een klantsleutel of een beschikbaarheidssleutel rollen of draaien voor informatie over het draaien of rollen van sleutels die u gebruikt met [klantcode.](customer-key-availability-key-roll.md) Wanneer u de DEP bij werkt om de nieuwe versie van de toetsen te gebruiken, wordt de Set-M365DataAtRestEncryptionPolicy cmdlet uitgevoerd, zoals eerder in dit artikel is beschreven.

## <a name="related-articles"></a>Verwante artikelen

- [Serviceversleuteling met klantsleutel](customer-key-overview.md)

- [Een klantsleutel of een beschikbaarheidssleutel rollen of draaien](customer-key-availability-key-roll.md)

- [Meer informatie over de beschikbaarheidssleutel](customer-key-availability-key-understand.md)

- [Serviceversleuteling](office-365-service-encryption.md)
