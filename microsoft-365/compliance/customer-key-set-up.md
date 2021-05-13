---
title: Klantsleutel instellen
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
description: Meer informatie over het instellen van klantcode voor Microsoft 365.
ms.openlocfilehash: e187c01a355cc9b926e892cb3326b5a527c714a4
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52344672"
---
# <a name="set-up-customer-key"></a>Klantsleutel instellen

Met De klantsleutel kunt u de versleutelingssleutels van uw organisatie bepalen en vervolgens Microsoft 365 configureren om uw gegevens in rust te versleutelen in de datacenters van Microsoft. Met andere woorden: met Klantsleutel kunnen klanten een versleutelingslaag toevoegen die aan hen toebehoort, met hun sleutels.

Stel Azure in voordat u klantcode kunt gebruiken voor Office 365. In dit artikel worden de stappen beschreven die u moet volgen om de vereiste Azure-resources te maken en te configureren en worden vervolgens de stappen beschreven voor het instellen van klantsleutel in Office 365. Nadat u Azure hebt ingesteld, bepaalt u welk beleid en dus welke sleutels u wilt toewijzen om gegevens te versleutelen in verschillende Microsoft 365 werkbelastingen in uw organisatie. Zie Serviceversleuteling met klantsleutel in Office 365 voor meer informatie over klantsleutel of voor [een algemeen overzicht.](customer-key-overview.md)
  
> [!IMPORTANT]
> We raden u ten zeerste aan de aanbevolen procedures in dit artikel te volgen. Deze worden genoemd als **TIP** en **BELANGRIJK.** Klantsleutel geeft u controle over hoofdversleutelingssleutels waarvan het bereik net zo groot kan zijn als uw hele organisatie. Dit betekent dat fouten die zijn gemaakt met deze sleutels een grote impact kunnen hebben en kunnen leiden tot serviceonderbrekingen of onherroepelijk verlies van uw gegevens.
  
## <a name="before-you-set-up-customer-key"></a>Voordat u klantsleutel in stelt

Voordat u aan de slag gaat, moet u ervoor zorgen dat u de juiste Azure-abonnementen en -licenties voor uw organisatie hebt. Gebruik betaalde Azure-abonnementen met een Enterprise Agreement of een cloudserviceprovider. Betalingen op basis van creditcard worden niet geaccepteerd. Goedkeuren en instellen van de accountbehoeften voor facturering. Abonnementen die u hebt via Gratis, Proefabonnementen, Sponsoring, MSDN-abonnementen en abonnementen onder Oudere ondersteuning komen niet in aanmerking.

Office 365 E5, Microsoft 365 E5, Microsoft 365 E5 Compliance en Microsoft 365 E5 Information Protection & Governance SKU's bieden klantsleutel. Office 365 Advanced Compliance SKU is niet meer beschikbaar voor het aanschaffen van nieuwe licenties. Bestaande Office 365 Advanced Compliance licenties blijven worden ondersteund.

Als u de concepten en procedures in dit artikel wilt begrijpen, bekijkt u de [documentatie van de Azure Key Vault.](/azure/key-vault/) U kunt ook vertrouwd raken met de termen die worden gebruikt in Azure, bijvoorbeeld [Azure AD-tenant.](/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)
  
Als u meer ondersteuning nodig hebt buiten de documentatie, neem dan contact op met Microsoft Consulting Services (MCS), Premier Field Engineering (PFE) of een Microsoft-partner voor hulp. Als u feedback wilt geven over de klantsleutel, inclusief de documentatie, stuurt u uw ideeën, suggesties en perspectieven naar customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>Overzicht van de stappen voor het instellen van klantcode

Als u Klantsleutel wilt instellen, voltooit u deze taken in de weergegeven volgorde. De rest van dit artikel bevat gedetailleerde instructies voor elke taak of koppelingen naar meer informatie voor elke stap in het proces.
  
**In Azure en Microsoft FastTrack:**
  
U voltooit de meeste van deze taken door op afstand verbinding te maken met Azure PowerShell. Voor de beste resultaten gebruikt u versie 4.4.0 of hoger van Azure PowerShell.
  
- [Twee nieuwe Azure-abonnementen maken](#create-two-new-azure-subscriptions)

- [Een aanvraag indienen om klantcode te activeren voor Office 365](#submit-a-request-to-activate-customer-key-for-office-365)
 
- [Azure-abonnementen registreren om een verplichte bewaarperiode te gebruiken](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  Registratie kan één tot vijf werkdagen duren.

- [Een premium Azure Key Vault maken in elk abonnement](#create-a-premium-azure-key-vault-in-each-subscription)

- [Machtigingen toewijzen aan elke sleutelkluis](#assign-permissions-to-each-key-vault)

- [Zorg ervoor dat soft delete is ingeschakeld in uw sleutelkluizen](#make-sure-soft-delete-is-enabled-on-your-key-vaults)

- [Een sleutel toevoegen aan elke sleutelkluis door een sleutel te maken of te importeren](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [Het herstelniveau van uw sleutels controleren](#check-the-recovery-level-of-your-keys)

- [Back-up maken van Azure Key Vault](#back-up-azure-key-vault)

- [Configuratie-instellingen voor Azure Key Vault valideren](#validate-azure-key-vault-configuration-settings)

- [De URI verkrijgen voor elke Azure Key Vault-toets](#obtain-the-uri-for-each-azure-key-vault-key)
  
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Taken uitvoeren in Azure Key Vault en Microsoft FastTrack voor klantcode

Voltooi deze taken in Azure Key Vault. U moet deze stappen voltooien voor alle DEP's die u gebruikt met klantcode.
  
### <a name="create-two-new-azure-subscriptions"></a>Twee nieuwe Azure-abonnementen maken

Klantcode vereist twee Azure-abonnementen. Microsoft raadt u aan om nieuwe Azure-abonnementen te maken voor gebruik met klantcode. Azure Key Vault-sleutels kunnen alleen worden geautoriseerd voor toepassingen in dezelfde Azure Active Directory-tenant (Microsoft Azure Active Directory), u moet de nieuwe abonnementen maken met dezelfde Azure AD-tenant die wordt gebruikt bij uw organisatie waar de DEP's worden toegewezen. Gebruik bijvoorbeeld uw werk- of schoolaccount met globale beheerdersbevoegdheden in uw organisatie. Zie Registreren voor Azure als organisatie voor [gedetailleerde stappen.](/azure/active-directory/fundamentals/sign-up-organization)
  
> [!IMPORTANT]
> Klantsleutel vereist twee sleutels voor elk gegevensversleutelingsbeleid (DEP). Hiervoor moet u twee Azure-abonnementen maken. Als aanbevolen training raadt Microsoft aan dat u afzonderlijke leden van uw organisatie hebt om één sleutel in elk abonnement te configureren. Gebruik deze Azure-abonnementen alleen om versleutelingssleutels te beheren voor Office 365. Hiermee beschermt u uw organisatie voor het geval een van uw operatoren per ongeluk, opzettelijk of met opzet de sleutels waarvoor ze verantwoordelijk zijn, verwijdert of anderszins onjuist bemant.

Er is geen praktische limiet voor het aantal Azure-abonnementen dat u voor uw organisatie kunt maken. Als u deze best practices volgt, wordt de impact van menselijke fouten geminimaliseerd en wordt het beheer van de resources die door Klantsleutel worden gebruikt, geminimaliseerd.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Een aanvraag indienen om klantcode te activeren voor Office 365

Nadat u de twee nieuwe Azure-abonnementen hebt gemaakt, moet u de juiste aanvraag voor een klantcode-aanbieding indienen in de [Microsoft FastTrack-portal.](https://fasttrack.microsoft.com/) De selecties die u maakt in het aanbiedingsformulier over de geautoriseerde aanduidingen binnen uw organisatie, zijn essentieel en noodzakelijk voor het voltooien van de registratie van klantsleutels. De functionarissen in de geselecteerde rollen binnen uw organisatie zorgen voor de echtheid van elk verzoek om alle sleutels in te trekken en te vernietigen die worden gebruikt met een gegevensversleutelingsbeleid voor klantsleutels. U moet deze stap eenmaal doen voor elk DEP-type klantsleutel dat u voor uw organisatie wilt gebruiken.

**Het FastTrack-team biedt geen hulp bij Klantcode. Office 365 gebruikt de FastTrack-portal om u toe te staan het formulier in te dienen en ons te helpen de relevante aanbiedingen voor Klantcode bij te houden. Nadat u de FastTrack-aanvraag hebt ingediend, kunt u contact op nemen met het bijbehorende onboardingteam van de klantsleutel om het onboardingproces te starten.**
  
Als u een aanbieding wilt indienen om klantcode te activeren, gaat u als volgende stappen te werk:
  
1. Meld u aan bij de [Microsoft FastTrack-portal](https://fasttrack.microsoft.com/)met een werk- of schoolaccount met globale beheerdersmachtigingen in uw organisatie.

2. Wanneer u bent aangemeld, selecteert u het juiste domein.

3. Kies voor het geselecteerde domein **Services aanvragen** op de bovenste navigatiebalk en bekijk de lijst met beschikbare aanbiedingen.

4. Kies de informatiekaart voor de aanbieding die op u van toepassing is:

   - **Meerdere Microsoft 365 werkbelastingen:** Kies de **Help voor versleutelingssleutel aanvragen voor Microsoft 365** aanbieding.

   - **Exchange Online en Skype voor Bedrijven:** Kies de **Help voor versleutelingssleutel aanvragen voor Exchange** aanbieding.

   - **SharePoint online, OneDrive en Teams bestanden:** Kies de **Help voor versleutelingssleutel** aanvragen voor SharePoint en OneDrive voor Bedrijven aanbieding.

5. Nadat u de aanbiedingsdetails hebt bekeken, kiest u **Doorgaan naar stap 2.**

6. Vul alle toepasselijke details en gevraagde informatie in op het aanbiedingsformulier. Let vooral op uw selecties waarvoor u de verantwoordelijken van uw organisatie wilt machtigen om de permanente en onomkeerbare vernietiging van versleutelingssleutels en gegevens goed te keuren. Nadat u het formulier hebt voltooid, kiest u **Verzenden.**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure-abonnementen registreren om een verplichte bewaarperiode te gebruiken

Het tijdelijke of permanente verlies van hoofdversleutelingssleutels kan storend of zelfs catastrofaal zijn voor de servicebewerking en kan leiden tot gegevensverlies. Om deze reden vereisen de resources die met Klantsleutel worden gebruikt, een sterke beveiliging. Alle Azure-resources die worden gebruikt met Customer Key bieden beschermingsmechanismen buiten de standaardconfiguratie. U kunt Azure-abonnementen taggen of registreren voor een *verplichte bewaarperiode.* Een verplichte bewaarperiode voorkomt onmiddellijke en onherroepelijke annulering van uw Azure-abonnement. De stappen die nodig zijn om Azure-abonnementen te registreren voor een verplichte bewaarperiode, vereisen samenwerking met het Microsoft 365 team. Dit proces kan één tot vijf werkdagen duren. Voorheen werd de verplichte bewaarperiode ook wel 'Niet annuleren' genoemd.
  
Voordat u contact op neemt met Microsoft 365 team, moet u de volgende stappen uitvoeren voor elk Azure-abonnement dat u gebruikt met klantcode. Zorg ervoor dat u de [Azure PowerShell Az-module](/powershell/azure/new-azureps-module-az) hebt geïnstalleerd voordat u begint.
  
1. Meld u aan met Azure PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

2. Voer de Register-AzProviderFeature cmdlet uit om uw abonnementen te registreren om een verplichte bewaarperiode te gebruiken. Voltooi deze actie voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Neem contact op met Microsoft om het proces te voltooien.

   - Voor het inschakelen van klantcode voor het toewijzen van DEP aan afzonderlijke Exchange Online postvakken, kunt u contact [opnemen met exock@microsoft.com.](mailto:exock@microsoft.com)

   - Voor het inschakelen van klantcode voor het toewijzen van DEP's om SharePoint Online en OneDrive voor Bedrijven-inhoud (inclusief Teams-bestanden) voor alle tenantgebruikers te versleutelen, neem dan contact [op met spock@microsoft.com.](mailto:spock@microsoft.com)

   - Neem contact op met m365-ck@service.microsoft.com voor het inschakelen van klantsleutel voor het toewijzen van DEP's voor het versleutelen van inhoud voor meerdere Microsoft 365-workloads (Exchange Online, Teams, MIP EDM) [voor alle](mailto:m365-ck@service.microsoft.com)tenantgebruikers.

- Neem de volgende informatie op in uw e-mail:

   **Onderwerp**: Klantcode voor \<*Your tenant's fully qualified domain name*\>

   **Body:** Neem de abonnement-1D's op waarvoor u de verplichte bewaarperiode en de uitvoer van Get-AzProviderFeature voor elk abonnement wilt voltooien.

   De SLA (Service Level Agreement) voor het voltooien van dit proces is vijf werkdagen nadat Microsoft is geïnformeerd (en geverifieerd) dat u uw abonnementen hebt geregistreerd om een verplichte bewaarperiode te gebruiken.

4. Nadat u een melding van Microsoft hebt ontvangen dat de registratie is voltooid, controleert u de status van uw registratie door de opdracht Get-AzProviderFeature uitvoeren als volgt. Als dit is geverifieerd, Get-AzProviderFeature opdracht een waarde als resultaat **geregistreerd** voor de eigenschap **Registratiestaat.** Voltooi deze stap voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Als u het proces wilt voltooien, kunt u de opdracht Register-AzResourceProvider uitvoeren. Voltooi deze stap voor elk abonnement.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Een premium Azure Key Vault maken in elk abonnement

De stappen voor het maken van een sleutelkluis worden beschreven in Aan de slag met [Azure Key Vault,](/azure/key-vault/general/overview)die u begeleidt bij het installeren en starten van Azure PowerShell, het maken van verbinding met uw Azure-abonnement, het maken van een resourcegroep en het maken van een sleutelkluis in die resourcegroep.
  
Wanneer u een sleutelkluis maakt, moet u een SKU kiezen: standaard of Premium. Met de standaard-SKU kunnen Azure Key Vault-sleutels worden beveiligd met software - er is geen HSM-sleutelbeveiliging (Hardware Security Module) en met de Premium-SKU kunnen HSM's worden gebruikt ter bescherming van Key Vault-sleutels. Klantsleutel accepteert sleutelkluizen die SKU gebruiken, maar Microsoft raadt ten zeerste aan dat u alleen de Premium SKU gebruikt. De kosten van bewerkingen met sleutels van beide typen zijn hetzelfde, dus het enige verschil in kosten is de kosten per maand voor elke met HSM beveiligde sleutel. Zie [Key Vault-prijzen](https://azure.microsoft.com/pricing/details/key-vault/) voor meer informatie.
  
> [!IMPORTANT]
> Gebruik de Premium SKU-sleutelkluizen en HSM-beveiligde sleutels voor productiegegevens en gebruik alleen standaard SKU-sleutelkluizen en -sleutels voor test- en validatiedoeleinden.
  
Voor elke Microsoft 365 waarmee u klantsleutel gebruikt, maakt u een sleutelkluis in elk van de twee Azure-abonnementen die u hebt gemaakt. Als u bijvoorbeeld klantsleutel wilt inschakelen om DEP's te gebruiken voor Exchange Online, SharePoint Online en scenario's met meerdere werkbelastingen, maakt u drie paar sleutelkluizen.
  
Gebruik een naamgevingsconventie voor sleutelkluizen die het beoogde gebruik van de DEP weerspiegelen waarmee u de kluizen koppelt. Zie de onderstaande sectie Aanbevolen procedures voor het benoemen van aanbevelingen voor conventies.
  
Maak een aparte, gekoppelde set kluizen voor elk gegevensversleutelingsbeleid. Voor Exchange Online wordt het bereik van een gegevensversleutelingsbeleid door u gekozen wanneer u het beleid aan postvak toewijst. Aan een postvak kan slechts één beleid zijn toegewezen en u kunt maximaal 50 beleidsregels maken. Het bereik van een SharePoint onlinebeleid bevat alle gegevens binnen een organisatie op een geografische locatie of _geografische locatie._ Het bereik voor een beleid met meerdere werkbelastingen omvat alle gegevens in de ondersteunde werkbelastingen voor alle gebruikers.

Het maken van sleutelkluizen vereist ook het maken van Azure-resourcegroepen, aangezien sleutelkluizen opslagcapaciteit (hoewel klein) nodig hebben en key vault logging, indien ingeschakeld, ook opgeslagen gegevens genereert. Als aanbevolen praktijk raadt Microsoft aan afzonderlijke beheerders te gebruiken om elke resourcegroep te beheren, met het beheer dat is uitgelijnd met de set beheerders die alle gerelateerde klantcodebronnen beheert.
  
> [!IMPORTANT]
> Als u de beschikbaarheid wilt maximaliseren, zet u uw sleutelkluizen in regio's dicht bij uw Microsoft 365-service Als uw Exchange Online-organisatie bijvoorbeeld in Noord-Amerika is, zet u uw sleutelkluizen in Noord-Amerika. Als uw Exchange Online in Europa is, zet u uw sleutelkluizen in Europa.
>
> Gebruik een gemeenschappelijk voorvoegsel voor sleutelkluizen en voeg een afkorting toe van het gebruik en het bereik van de sleutelkluis en -sleutels (bijvoorbeeld voor de Contoso-SharePoint-service waar de kluizen zich in Noord-Amerika bevinden, een mogelijk paar namen is Contoso-CK-SP-NA-VaultA1 en Contoso-CK-SP-NA-VaultA2. Kluisnamen zijn wereldwijd unieke tekenreeksen binnen Azure, dus mogelijk moet u variaties van de gewenste namen proberen voor het geval de gewenste namen al worden geclaimd door andere Azure-klanten. Vanaf juli 2017 kunnen kluisnamen niet meer worden gewijzigd, dus het is een goede gewoonte om een schriftelijk plan voor de installatie te hebben en een tweede persoon te gebruiken om te controleren of het plan correct wordt uitgevoerd.
>
> Maak indien mogelijk uw kluizen in niet-gekoppelde regio's. Gekoppelde Azure-regio's bieden hoge beschikbaarheid voor servicefoutdomeinen. Daarom kunnen regionale paren worden gebruikt als elkaars back-upgebied. Dit betekent dat een Azure-resource die in één regio is geplaatst, automatisch fouttolerantie krijgt via het gekoppelde gebied. Daarom betekent het kiezen van regio's voor twee kluizen die worden gebruikt in een gegevensversleutelingsbeleid waarbij de regio's zijn gekoppeld, dat er slechts twee regio's van beschikbaarheid worden gebruikt. De meeste regio's hebben slechts twee regio's, dus het is nog niet mogelijk om niet-gekoppelde regio's te selecteren. Kies indien mogelijk twee niet-gekoppelde regio's voor de twee kluizen die worden gebruikt met een gegevensversleutelingsbeleid. Dit komt ten goede aan een totaal van vier regio's met beschikbaarheid. Zie Business Continuity and Disaster Recovery (BCDR): Azure Paired Regions for a current list of regional pairs [(Business continuity and disaster recovery( BCDR): Azure Paired Regions (Business Continuity and Disaster Recovery( BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) (Business Continuity and Disaster Recovery) voor een huidige lijst met regionale paren.
  
### <a name="assign-permissions-to-each-key-vault"></a>Machtigingen toewijzen aan elke sleutelkluis

U moet drie afzonderlijke sets machtigingen definiëren voor elke sleutelkluis, afhankelijk van uw implementatie. U moet bijvoorbeeld één set machtigingen definiëren voor elk van de volgende machtigingen:
  
- **Key vault administrators** that do day-to-day management of your key vault for your organization. Deze taken omvatten back-up maken, maken, krijgen, importeren, lijst en herstellen.

  > [!IMPORTANT]
  > De set machtigingen die is toegewezen aan beheerders van de sleutelkluis, bevat niet de machtiging om sleutels te verwijderen. Dit is opzettelijk en een belangrijke oefening. Het verwijderen van versleutelingssleutels gebeurt meestal niet, omdat hierdoor gegevens permanent worden vernietigd. Als een goede gewoonte, verleent u deze machtiging niet standaard aan beheerders van de sleutelkluis. Reserveer dit in plaats daarvan voor sleutelkluiscontribuanten en wijs deze alleen op korte termijn toe aan een beheerder zodra een duidelijk begrip van de gevolgen is begrepen.
  
  Als u deze machtigingen wilt toewijzen aan een gebruiker in uw organisatie, meld u zich aan bij uw Azure-abonnement met Azure PowerShell. Zie Aanmelden met Azure PowerShell voor [instructies.](/powershell/azure/authenticate-azureps)

- Voer de Set-AzKeyVaultAccessPolicy cmdlet uit om de benodigde machtigingen toe te wijzen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Bijvoorbeeld:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Key vault contributors** that can change permissions on the Azure Key Vault itself. U moet deze machtigingen wijzigen wanneer werknemers uw team verlaten of lid worden. In de zeldzame situatie dat de beheerders van de sleutelkluis rechtmatig toestemming nodig hebben om een sleutel te verwijderen of te herstellen, moet u ook de machtigingen wijzigen. Aan deze set sleutelkluisbijdragers moet de rol **Inzender** in uw sleutelkluis worden verleend. U kunt deze rol toewijzen met Behulp van Azure Resource Manager. Zie Toegangsbeheer Role-Based Toegangsbeheer gebruiken om toegang tot uw Azure-abonnementsbronnen te beheren voor [gedetailleerde stappen.](/azure/active-directory/role-based-access-control-configure) De beheerder die een abonnement maakt, heeft impliciet deze toegang en de mogelijkheid om andere beheerders toe te wijzen aan de rol Inzender.

- **Machtigingen** voor Microsoft 365 voor elke sleutelkluis die u voor Klantsleutel gebruikt, moet u wrapKey geven, uitpakkenKey en machtigingen krijgen voor de bijbehorende Microsoft 365 Service Principal. 

Voer de cmdlet **Set-AzKeyVaultAccessPolicy** uit met de volgende syntaxis om toestemming te geven voor Microsoft 365 service principal:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   Waarbij:

   - *de naam van* de kluis is de naam van de sleutelkluis die u hebt gemaakt.
   - Voor Exchange Online en Skype voor Bedrijven, vervangt u *Office 365 appID* door`00000002-0000-0ff1-ce00-000000000000`
   - Voor SharePoint Online, OneDrive voor Bedrijven en Teams, vervangt u *Office 365 appID* door`00000003-0000-0ff1-ce00-000000000000`
   - Voor beleid met meerdere werkbelastingen (Exchange, Teams, MIP EDM) dat van toepassing is op alle tenantgebruikers, vervangt u Office 365 *appID* door`c066d759-24ae-40e7-a56f-027002b5d3e4`

  Voorbeeld: Machtigingen instellen voor Exchange Online en Skype voor Bedrijven:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  Voorbeeld: Machtigingen instellen voor SharePoint Online, OneDrive voor Bedrijven en Teams bestanden:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="make-sure-soft-delete-is-enabled-on-your-key-vaults"></a>Zorg ervoor dat soft delete is ingeschakeld in uw sleutelkluizen

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

Er zijn twee manieren om sleutels toe te voegen aan een Azure Key Vault. u kunt een sleutel rechtstreeks in de Sleutelkluis maken of u kunt een sleutel importeren. Het maken van een sleutel rechtstreeks in Key Vault is minder ingewikkeld, maar het importeren van een sleutel biedt totale controle over de manier waarop de sleutel wordt gegenereerd. Gebruik de RSA-toetsen. Azure Key Vault biedt geen ondersteuning voor het terugpakken en uitpakken met elliptische curvetoetsen.
  
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
Add-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

Als u een sleutel rechtstreeks in uw sleutelkluis wilt importeren, moet u een nCipher nShield Hardware Security Module hebben.
  
Sommige organisaties geven de voorkeur aan deze methode om de herkomst van hun sleutels vast te stellen en deze methode bevat ook de volgende verklaringen:
  
- De hulpprogramma's die voor import worden gebruikt, omvatten de bevestiging van nCipher dat de sleutel Exchange-toets (KEK) die wordt gebruikt om de sleutel te versleutelen die u genereert, niet kan worden geëxporteerd en wordt gegenereerd in een echte HSM die is gemaakt door nCipher.

- De toolset bevat een bevestiging van nCipher dat de beveiligingswereld van Azure Key Vault ook is gegenereerd op een echte HSM die door nCipher is gemaakt. Deze bevestiging bewijst dat Microsoft ook legitieme nCipher-hardware gebruikt.

Neem contact op met uw beveiligingsgroep om te bepalen of de bovenstaande bevestigingen vereist zijn. Zie HSM-beveiligde sleutels genereren en overdragen voor Azure Key Vault voor gedetailleerde stappen om een on-premises sleutel te maken en deze te importeren in uw [sleutelkluis.](/azure/key-vault/keys/hsm-protected-keys) Gebruik de Azure-instructies om een sleutel te maken in elke sleutelkluis.
  
### <a name="check-the-recovery-level-of-your-keys"></a>Het herstelniveau van uw sleutels controleren

Microsoft 365 vereist dat het Azure Key Vault-abonnement is ingesteld op Niet annuleren en dat de sleutels die door Klantsleutel worden gebruikt, soft delete hebben ingeschakeld. U kunt de instellingen voor abonnementen bevestigen door te kijken naar het herstelniveau op uw toetsen.
  
Als u het herstelniveau van een sleutel wilt controleren, Azure PowerShell u de Get-AzKeyVaultKey als volgt uit:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Als  de eigenschap Herstelniveau iets anders retourneert dan een waarde van **Herstelbaar+ProtectedSubscription,** moet u ervoor zorgen dat u het abonnement op de lijst Niet annuleren hebt geplaatst en dat u soft delete hebt ingeschakeld op elk van uw sleutelkluizen.
  
### <a name="back-up-azure-key-vault"></a>Back-up maken van Azure Key Vault

Direct na het maken of wijzigen van een sleutel, voert u een back-up uit en kunt u kopieën van de back-up opslaan, zowel online als offline. Maak geen verbinding met offlinekopieen met een netwerk. Bewaar ze in plaats daarvan op een offlinelocatie, zoals in een fysieke veilige of commerciële opslaglocatie. Ten minste één kopie van de back-up moet worden opgeslagen op een locatie die toegankelijk is als er een ramp optreedt. De back-up blobs zijn het enige middel om sleutelmateriaal te herstellen als een Sleutelkluissleutel permanent wordt vernietigd of anderszins niet meer kan worden gebruikt. Sleutels die extern zijn in Azure Key Vault en zijn geïmporteerd in Azure Key Vault komen niet in aanmerking als back-up omdat de metagegevens die nodig zijn voor klantcode om de sleutel te gebruiken, niet aanwezig zijn met de externe sleutel. Alleen een back-up van Azure Key Vault kan worden gebruikt voor het herstellen van bewerkingen met klantsleutel. Daarom moet u een back-up van Azure Key Vault maken nadat u een sleutel hebt geüpload of gemaakt.
  
Als u een back-up wilt maken van een Azure Key Vault-sleutel, moet u de [cmdlet Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) als volgt uitvoeren:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Zorg ervoor dat het achtervoegsel wordt gebruikt in het `.backup` uitvoerbestand.
  
Het uitvoerbestand dat het resultaat is van deze cmdlet, is versleuteld en kan niet buiten Azure Key Vault worden gebruikt. De back-up kan alleen worden hersteld naar het Azure-abonnement waaruit de back-up is gemaakt.
  
> [!TIP]
> Kies voor het uitvoerbestand een combinatie van de naam van de kluis en de sleutelnaam. Hierdoor wordt de bestandsnaam automatisch beschreven. Het zorgt er ook voor dat back-upbestandsnamen niet botsen.
  
Bijvoorbeeld:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-CK-EX-NA-VaultA1 -Name Contoso-CK-EX-NA-VaultA1-Key001 -OutputFile Contoso-CK-EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Configuratie-instellingen voor Azure Key Vault valideren

Valideren voordat u toetsen in een DEP gebruikt, is optioneel, maar ten zeerste aanbevolen. Als u stappen gebruikt om andere sleutels en kluizen in te stellen dan de sleutels die in dit artikel worden beschreven, valideert u de status van uw Azure Key Vault-resources voordat u Klantsleutel configureert.
  
Controleer of uw sleutels zijn `get` ingeschakeld en of bewerkingen zijn `wrapKey` `unwrapKey` ingeschakeld:
  
Voer de [Get-AzKeyVault-cmdlet](/powershell/module/az.keyvault/get-azkeyvault) als volgt uit:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Zoek in de uitvoer naar het Access-beleid en naar de Exchange Online-identiteit (GUID) of de SharePoint Online-identiteit (GUID). Alle drie de bovenstaande machtigingen moeten worden weergegeven onder Machtigingen voor sleutels.
  
Als de configuratie van het toegangsbeleid onjuist is, kunt u de Set-AzKeyVaultAccessPolicy als volgt uitvoeren:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

Bijvoorbeeld voor Exchange Online en Skype voor Bedrijven:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

Bijvoorbeeld voor SharePoint Online en OneDrive voor Bedrijven:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-CK-SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

Als u wilt controleren of er geen vervaldatum is ingesteld voor uw sleutels, moet u de [cmdlet Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) als volgt uitvoeren:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Klantcode kan geen verlopen sleutel gebruiken. Bewerkingen die worden uitgevoerd met een verlopen sleutel, mislukken en kunnen leiden tot een servicestoring. Het is ten zeerste raadzaam dat sleutels die worden gebruikt met klantcode, geen vervaldatum hebben. Een vervaldatum, eenmaal ingesteld, kan niet worden verwijderd, maar kan worden gewijzigd in een andere datum. Als een sleutel moet worden gebruikt met een vervaldatumset, wijzigt u de vervaldatum in 31-12-9999. Toetsen met een vervaldatum die is ingesteld op een andere datum dan 31-12-9999, worden niet door Microsoft 365 gevalideerd.
  
Als u een vervaldatum wilt wijzigen die is ingesteld op een andere waarde dan 31-12-9999, moet u de [cmdlet Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) als volgt uitvoeren:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> Stel geen vervaldatums in op versleutelingssleutels die u gebruikt met klantcode.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>De URI verkrijgen voor elke Azure Key Vault-toets

Nadat u de sleutelkluizen hebt ingesteld en uw sleutels hebt toegevoegd, kunt u de volgende opdracht uitvoeren om de URI voor de sleutel in elke sleutelkluis te krijgen. U gebruikt deze URL's wanneer u elke DEP later maakt en toewijst, dus sla deze informatie op een veilige plaats op. Voer deze opdracht eenmaal uit voor elke sleutelkluis.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="next-steps"></a>Volgende stappen

Nadat u de stappen in dit artikel hebt voltooid, kunt u dep's maken en toewijzen. Zie Klantsleutel beheren [voor instructies.](customer-key-manage.md)

## <a name="related-articles"></a>Verwante artikelen

- [Serviceversleuteling met klantsleutel](customer-key-overview.md)

- [Klantcode beheren](customer-key-manage.md)

- [Een klantsleutel of een beschikbaarheidssleutel rollen of draaien](customer-key-availability-key-roll.md)

- [Meer informatie over de beschikbaarheidssleutel](customer-key-availability-key-understand.md)

- [Serviceversleuteling](office-365-service-encryption.md)