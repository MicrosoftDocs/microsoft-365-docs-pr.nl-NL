---
title: Migratie van e-mailberichten tussen tenants
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
ms.openlocfilehash: f649a72dc5569e8aec46347df295aa3ff9d93613
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177147"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="2a203-103">Migratie van cross-Tenant postvak (preview)</span><span class="sxs-lookup"><span data-stu-id="2a203-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="2a203-104">Eerder, wanneer een Exchange Online-Tenant nodig heeft om postvakken te verplaatsen naar een andere Tenant in dezelfde Exchange Online-service, moeten ze ze volledig verwijderen naar on-premises en ze vervolgens op een nieuwe Tenant plaatsen.</span><span class="sxs-lookup"><span data-stu-id="2a203-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="2a203-105">Met de nieuwe functie voor het migreren van postvakken kunnen tenantbeheerders van de bron-en doel tenants postvakken verplaatsen tussen de tenants met minimale infrastructuur afhankelijkheden in hun on-premises systemen.</span><span class="sxs-lookup"><span data-stu-id="2a203-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="2a203-106">Hiermee verwijdert u de verwijderen en de interne postvakken.</span><span class="sxs-lookup"><span data-stu-id="2a203-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="2a203-107">Voor de samenvoeging of divestitures hebt u meestal de mogelijkheid om gebruikers en inhoud te verplaatsen naar een nieuwe Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="2a203-108">Wanneer de doel tenantbeheerder de verhuizing uitvoert, wordt de overstap een pull-verhuizing genoemd, vergelijkbaar met de on-premises voor de Cloud onboarding-migraties.</span><span class="sxs-lookup"><span data-stu-id="2a203-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="2a203-109">Cross-Tenant Exchange postvak verplaatste wordt volledig selfservice voor tenantbeheerders, met behulp van bekende interfaces die scripts kunnen worden omgezet in de grotere werkstromen die nodig zijn om gebruikers over te dragen aan hun nieuwe organisatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="2a203-110">Beheerders kunnen de `New-MigrationBatch` cmdlet gebruiken, die beschikbaar is via de beheerfunctie postvakken verplaatsen, om cross-tenants te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="2a203-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="2a203-111">Het verplaatsings proces omvat Tenant autorisatie controles tijdens het synchroniseren van uw e-mail en voltooien.</span><span class="sxs-lookup"><span data-stu-id="2a203-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="2a203-112">Gebruikers die worden gemigreerd, moeten presenteren in het doel Tenant Exchange Online systeem als e-gebruikers, gemarkeerd met specifieke kenmerken om het verplaatsen van de cross-Tenant te activeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2a203-113">Het systeem gaat niet naar gebruikers die niet correct zijn ingesteld in de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="2a203-114">Wanneer de verhuizingen zijn voltooid, wordt het postvak van het bronsysteem geconverteerd naar mail-gebruiker en wordt het targetAddress (weergegeven als ExternalEmailAddress in Exchange) voorzien van een stempel met het routerings adres voor de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="2a203-115">Hiermee laat u de oude e-mail gebruiker in de bron Tenant overstappen, en kunt u gedurende een bepaalde periode voor het samenwerken van e-mailberichten en e-mail routering.</span><span class="sxs-lookup"><span data-stu-id="2a203-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="2a203-116">Wanneer bedrijfsprocessen zijn toegestaan, kan de bron Tenant de bron-mail gebruiker verwijderen of deze converteren naar een e-mail contactpersoon.</span><span class="sxs-lookup"><span data-stu-id="2a203-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="2a203-117">Migraties van Exchange-postvak voor meerdere tenants worden ondersteund voor tenants in hybride of Cloud, of een willekeurige combinatie van beide.</span><span class="sxs-lookup"><span data-stu-id="2a203-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="2a203-118">In dit artikel wordt het proces beschreven voor het doorsturen van berichten via meerdere tenants en vindt u informatie over het voorbereiden van bron-en doel tenants voor de verhuizing van inhoud.</span><span class="sxs-lookup"><span data-stu-id="2a203-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="2a203-119">Bron-en doel tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="2a203-119">Preparing source and target tenants</span></span>

<span data-ttu-id="2a203-120">Voor de migratie functie voor het cross-Tenant Exchange-postvak is autorisatie en scope vereist voor migraties van cross tenants.</span><span class="sxs-lookup"><span data-stu-id="2a203-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="2a203-121">Met de implementatie van de Azure Enterprise-toepassing en de belangrijkste oplossingen voor de opslag van een archief met grote en grote archieven kunnen tenantbeheerders de autorisatie en het bereik van Exchange Online-postvak migraties van de ene Tenant naar een andere beheren.</span><span class="sxs-lookup"><span data-stu-id="2a203-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="2a203-122">Het postvak voor de ondersteuning van cross-tenants biedt ondersteuning voor het maken van een verzoek om Azure Active Directory (Azure AD) voor verificatie tussen een Tenant paar.</span><span class="sxs-lookup"><span data-stu-id="2a203-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="2a203-123">Er zijn ook extra onderdelen, zoals een organisatie relatie en een migratie-eindpunt vereist.</span><span class="sxs-lookup"><span data-stu-id="2a203-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="2a203-124">In deze sectie vindt u niet de specifieke stappen die nodig zijn voor het voorbereiden van de gebruikersobjecten van de gebruiker in de doeldirectory, noch de optie voorbeeld van het verzenden van een migratie batch.</span><span class="sxs-lookup"><span data-stu-id="2a203-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="2a203-125">Zie [doelgebruikers objecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a203-126">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2a203-126">Prerequisites</span></span>

<span data-ttu-id="2a203-127">Voor de functie voor het verplaatsen van het postvak in van de cross-Tenant is [Azure Key](https://docs.microsoft.com/azure/key-vault/basic-concepts) Secret vereist om een voor de Tenant gekoppelde Azure-toepassing te zorgen voor het veilig opslaan en openen van het certificaat dat wordt gebruikt voor de verificatie van en de migratie van postvakken van de ene Tenant naar de andere.</span><span class="sxs-lookup"><span data-stu-id="2a203-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="2a203-128">Voordat u begint, controleert u of u de benodigde machtigingen hebt voor het uitvoeren van de implementatiescripts om Azure-sleutel kluis te configureren, Postvak toepassing te verplaatsen, EXO-migratie-eindpunt en de EXO-organisatie relatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="2a203-129">Een globale beheerder heeft meestal de machtiging alle configuratiestappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="2a203-130">Daarnaast zijn er ook beveiligingsgroepen met e-mail in de bron Tenant vereist voordat u Setup uitvoert.</span><span class="sxs-lookup"><span data-stu-id="2a203-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="2a203-131">Deze groepen worden gebruikt voor het bereik van de lijst met postvakken die vanuit de bron (of soms ook resource genoemd) kunnen worden verplaatst naar de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="2a203-132">Hierdoor kan de tenantbeheerder de specifieke set postvakken die moeten worden verplaatst, beperken of bereiken, zodat onbedoelde gebruikers niet worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="2a203-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="2a203-133">Geneste groepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="2a203-133">Nested groups are not supported.</span></span>

<span data-ttu-id="2a203-134">U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken gaat verplaatsen) om de Microsoft 365-Tenant-ID te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="2a203-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="2a203-135">Deze Tenant-ID wordt gebruikt in het veldrelatie tussen organisaties `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="2a203-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="2a203-136">Als u de Tenant-ID van een abonnement wilt verkrijgen, meldt u zich aan bij het Microsoft 365-Beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="2a203-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="2a203-137">Klik op het Kopieer pictogram voor de eigenschap Tenant-ID om dit naar het Klembord te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="2a203-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="2a203-138">Dit is de werking van het proces.</span><span class="sxs-lookup"><span data-stu-id="2a203-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg" alt-text="Tenant voorbereiding voor migratie van postvakken.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="2a203-140">Tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="2a203-140">Prepare tenants</span></span>

<span data-ttu-id="2a203-141">Op een hoog niveau worden de volgende configuratieacties uitgevoerd tijdens het uitvoeren van de installatiescripts.</span><span class="sxs-lookup"><span data-stu-id="2a203-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="2a203-142">De doel Tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="2a203-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="2a203-143">Als er geen bestaande Azure-resource groep wordt opgegeven, wordt een nieuwe groep gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="2a203-144">Als er geen bestaande sleutel kluis wordt opgegeven, wordt er een nieuwe sleutel gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="2a203-145">Er wordt een nieuw toegangsbeleid gemaakt voor de Office 365 Exchange Online Mailbox Migration Application (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="2a203-146">Er wordt een nieuw certificaat gemaakt (of een bestaande, indien opgegeven), om het geheim te houden voor de migratietoepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="2a203-147">Er is een nieuwe Azure AD-toepassing gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="2a203-148">Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="2a203-149">Machtigingen voor migratie van postvakken zijn toegewezen aan de toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="2a203-150">Het implementatiescript wordt onderbroken totdat de doel beheerder de eigen toepassing (SCRIPT) heeft doorgestuurd.</span><span class="sxs-lookup"><span data-stu-id="2a203-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="2a203-151">De doel tenantbeheerder verzendt de machtigingen die aan de toepassing zijn toegewezen (handmatig).</span><span class="sxs-lookup"><span data-stu-id="2a203-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="2a203-152">Er is een organisatie relatie gemaakt met de doel Tenant (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="2a203-153">Er wordt een migratie-eindpunt gemaakt om postvakken te verzamelen in de doel Tenant (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="2a203-154">De bron Tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="2a203-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="2a203-155">De bron tenantbeheerder accepteert toestemming voor de uitnodiging voor de migratietoepassing van een postvak via de doel Tenant (handmatig).</span><span class="sxs-lookup"><span data-stu-id="2a203-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="2a203-156">Met de bron tenantbeheerder maakt u een beveiligingsgroep met een e-mail functie in de Tenant, zodat deze de lijst met postvakken mag bevatten die door de migratietoepassing mag worden verplaatst (handmatig).</span><span class="sxs-lookup"><span data-stu-id="2a203-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="2a203-157">Er wordt een organisatie relatie gemaakt met de doel Tenant die de migratietoepassing voor postvakken voor de migratie van postvakken moet gebruiken om de verplaatsingsaanvraag te accepteren (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="2a203-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="2a203-158">Stapsgewijze instructies voor de doel tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="2a203-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="2a203-159">Download het SetupCrossTenantRelationshipForTargetTenant.ps1-script voor de instellingen van de doel Tenant in de [github-bibliotheek](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="2a203-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="2a203-160">Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer op waar u het script wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="2a203-161">Maak een externe PowerShell-verbinding met de doel Tenant van Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2a203-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="2a203-162">Zorg er ook voor dat u over de benodigde machtigingen beschikt om de implementatiescripts uit te voeren om de opslag en het certificaat van de Azure-sleutel kluis te kunnen configureren, Postvak toepassing, migratie-eindpunt EXO en de EXO-organisatie relatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="2a203-163">Wijzig de map met de bestands map in de naam van het script of Controleer of het script momenteel is opgeslagen op de locatie die u in de externe PowerShell-sessie hebt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2a203-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="2a203-164">Voer het script uit met de volgende parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="2a203-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="2a203-165">Tabelwaardeparameter</span><span class="sxs-lookup"><span data-stu-id="2a203-165">Parameter</span></span> | <span data-ttu-id="2a203-166">Value</span><span class="sxs-lookup"><span data-stu-id="2a203-166">Value</span></span> | <span data-ttu-id="2a203-167">Vereist of optioneel</span><span class="sxs-lookup"><span data-stu-id="2a203-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="2a203-168">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2a203-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="2a203-169">Tenant domein voor bronnen, zoals fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a203-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="2a203-170">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-170">Required</span></span> |
    | <span data-ttu-id="2a203-171">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="2a203-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="2a203-172">E-mailadres van de bron tenantbeheerder.</span><span class="sxs-lookup"><span data-stu-id="2a203-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="2a203-173">Dit is de bron tenantbeheerder die wordt doorgestuurd naar het gebruik van de migratietoepassing voor postvakken die van de doel beheerder is verzonden. De beheerder die de e-mail uitnodiging voor de toepassing ontvangt.</span><span class="sxs-lookup"><span data-stu-id="2a203-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="2a203-174">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-174">Required</span></span> |
    | <span data-ttu-id="2a203-175">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2a203-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="2a203-176">Het doel Tenant domein, bijvoorbeeld contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a203-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="2a203-177">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-177">Required</span></span> |
    | <span data-ttu-id="2a203-178">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="2a203-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="2a203-179">Bron Tenant-ID (GUID).</span><span class="sxs-lookup"><span data-stu-id="2a203-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="2a203-180">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-180">Required</span></span> |
    | <span data-ttu-id="2a203-181">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="2a203-181">-SubscriptionId</span></span>                             | <span data-ttu-id="2a203-182">Het Azure-abonnement dat moet worden gebruikt voor het maken van bronnen.</span><span class="sxs-lookup"><span data-stu-id="2a203-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="2a203-183">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-183">Required</span></span> |
    | <span data-ttu-id="2a203-184">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2a203-184">-ResourceGroup</span></span>                              | <span data-ttu-id="2a203-185">Naam van Azure-resourcegroep die de sleutel kluis bevat of bevat.</span><span class="sxs-lookup"><span data-stu-id="2a203-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="2a203-186">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-186">Required</span></span> |
    | <span data-ttu-id="2a203-187">-De kluizen</span><span class="sxs-lookup"><span data-stu-id="2a203-187">-KeyVaultName</span></span>                               | <span data-ttu-id="2a203-188">Azure Key Secret-exemplaar waarin het certificaat voor de migratietoepassing van uw postvak wordt opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2a203-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="2a203-189">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-189">Required</span></span> |
    | <span data-ttu-id="2a203-190">-Certificaatpad</span><span class="sxs-lookup"><span data-stu-id="2a203-190">-CertificateName</span></span>                            | <span data-ttu-id="2a203-191">Certificaatnaam bij het genereren van of zoeken naar een certificaat in de sleutel kluis.</span><span class="sxs-lookup"><span data-stu-id="2a203-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="2a203-192">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-192">Required</span></span> |
    | <span data-ttu-id="2a203-193">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="2a203-193">-CertificateSubject</span></span>                         | <span data-ttu-id="2a203-194">Naam van onderwerp van Azure-sleutel kluis certificaat, zoals CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="2a203-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="2a203-195">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-195">Required</span></span> |
    | <span data-ttu-id="2a203-196">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="2a203-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="2a203-197">De e-mail migratietoepassing die moet worden gebruikt als er al een is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2a203-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="2a203-198">Optioneel</span><span class="sxs-lookup"><span data-stu-id="2a203-198">Optional</span></span> |
    | <span data-ttu-id="2a203-199">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="2a203-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="2a203-200">De machtigingen die u nodig hebt voor de migratietoepassing voor het postvak, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph voor het gebruik van deze toepassing om een uitnodiging te verzenden aan de Tenant).</span><span class="sxs-lookup"><span data-stu-id="2a203-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="2a203-201">Vereist</span><span class="sxs-lookup"><span data-stu-id="2a203-201">Required</span></span> |
    | <span data-ttu-id="2a203-202">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="2a203-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="2a203-203">De parameter voor het gebruik van de toepassing die is gemaakt voor de migratie die moet worden gebruikt voor het verzenden van een uitnodiging voor de koppeling naar de bron Tenant. Als dit niet het geval is, wordt u gevraagd om de referenties van de doel beheerder verbinding te maken met Azure uitnodiging Manager en de uitnodiging te verzenden als doel beheerder.</span><span class="sxs-lookup"><span data-stu-id="2a203-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="2a203-204">Optioneel</span><span class="sxs-lookup"><span data-stu-id="2a203-204">Optional</span></span> |
    | <span data-ttu-id="2a203-205">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="2a203-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="2a203-206">Het opslagaccount waar de auditlogboeken van belangrijke kluizen zijn opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2a203-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="2a203-207">Optioneel</span><span class="sxs-lookup"><span data-stu-id="2a203-207">Optional</span></span> |
    | <span data-ttu-id="2a203-208">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="2a203-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="2a203-209">De resourcegroep die het opslagaccount bevat voor het opslaan van belangrijke auditlogboeken.</span><span class="sxs-lookup"><span data-stu-id="2a203-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="2a203-210">Optioneel</span><span class="sxs-lookup"><span data-stu-id="2a203-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="2a203-211">Het script wordt onderbroken en u vraagt of u de migratietoepassing voor Exchange-postvakken die u tijdens dit proces hebt gemaakt, moet accepteren of u ermee akkoord te gaan.</span><span class="sxs-lookup"><span data-stu-id="2a203-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="2a203-212">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-212">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. <span data-ttu-id="2a203-213">Er wordt een URL weergegeven in de externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="2a203-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="2a203-214">Kopieer de koppeling van de Tenant en plak deze in een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="2a203-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="2a203-215">Meld u aan met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="2a203-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="2a203-216">Wanneer het volgende scherm wordt weergegeven, selecteert u **accepteren**.</span><span class="sxs-lookup"><span data-stu-id="2a203-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Het dialoogvenster Machtigingen accepteren":::
    
9. <span data-ttu-id="2a203-218">Ga terug naar de externe PowerShell-sessie en druk op ENTER om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="2a203-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="2a203-219">Met het script worden de overige instel objecten geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="2a203-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="2a203-220">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="2a203-221">De installatie van doel beheerders is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="2a203-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="2a203-222">Stap-voor-stap-instructies voor de bron tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="2a203-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="2a203-223">Meld u aan bij uw postvak als het ResourceTenantAdminEmail dat door de doel beheerder is opgegeven tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="2a203-224">Zoek de e-mail uitnodiging van de doel Tenant en selecteer vervolgens de knop **aan de slag** .</span><span class="sxs-lookup"><span data-stu-id="2a203-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Het dialoogvenster invided":::

2. <span data-ttu-id="2a203-226">Selecteer **accepteren** om de uitnodiging te accepteren.</span><span class="sxs-lookup"><span data-stu-id="2a203-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster voor het accepteren van machtigingen voor":::

   > [!NOTE]
   > <span data-ttu-id="2a203-228">Als u dit e-mailbericht niet ontvangt of als u het niet kunt vinden, wordt de doel tenantbeheerder een directe URL gegeven waarnaar u de uitnodiging kunt accepteren.</span><span class="sxs-lookup"><span data-stu-id="2a203-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="2a203-229">De URL moet in de naam van de externe PowerShell-sessie van de doel tenantbeheerder staan.</span><span class="sxs-lookup"><span data-stu-id="2a203-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="2a203-230">Maak in het Microsoft 365-Beheercentrum of een externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om te bepalen welke postvakken door de doelgroep van de bron zijn toegestaan om (te verplaatsen) van de bron Tenant naar de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="2a203-231">U hoeft deze groep niet vooraf in te vullen, maar er moet minimaal één groep worden opgegeven om de instellingsstappen (script) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="2a203-232">Neste groepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="2a203-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="2a203-233">Download het SetupCrossTenantRelationshipForTargetResource.ps1 script voor de configuratie van de bron-Tenant vanuit de GitHub [-bibliotheek.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="2a203-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="2a203-234">Maak een externe PowerShell-verbinding met de bron Tenant met uw beheerdersmachtigingen voor Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a203-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="2a203-235">Globale beheerdersmachtigingen zijn niet vereist voor het configureren van de bron Tenant, alleen de doel Tenant vanwege het maken van Azure-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="2a203-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="2a203-236">Wijzig de adreslijst in de naam van het script of Controleer of het script op de locatie in de externe PowerShell-sessie momenteel is opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="2a203-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="2a203-237">Voer het script uit met de volgende vereiste parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="2a203-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="2a203-238">Tabelwaardeparameter</span><span class="sxs-lookup"><span data-stu-id="2a203-238">Parameter</span></span> | <span data-ttu-id="2a203-239">Value</span><span class="sxs-lookup"><span data-stu-id="2a203-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="2a203-240">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="2a203-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="2a203-241">Beveiligingsgroep met e-mail gemaakt door bron Tenant voor de identiteiten/postvakken die binnen het bereik van de migratie liggen.</span><span class="sxs-lookup"><span data-stu-id="2a203-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="2a203-242">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2a203-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="2a203-243">Naam van bron Tenant domein, bijvoorbeeld fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a203-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2a203-244">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="2a203-244">-TargetTenantDomain</span></span> | <span data-ttu-id="2a203-245">De naam van het doel Tenant domein, bijvoorbeeld contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a203-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="2a203-246">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="2a203-246">-ApplicationId</span></span> | <span data-ttu-id="2a203-247">De ID van de Azure-toepassing van de toepassing die wordt gebruikt voor de migratie.</span><span class="sxs-lookup"><span data-stu-id="2a203-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="2a203-248">Toepassings-ID beschikbaar via uw Azure-Portal (Azure AD, Enterprise-toepassingen, app-naam, toepassings-ID) of die is opgenomen in de e-mail van de uitnodiging.</span><span class="sxs-lookup"><span data-stu-id="2a203-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="2a203-249">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="2a203-249">-TargetTenantId</span></span> | <span data-ttu-id="2a203-250">Tenant-ID van de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="2a203-251">Bijvoorbeeld de naam van een Azure AD-Tenant van Contoso \. onmicrosoft.com Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="2a203-252">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="2a203-253">De installatie van bronbeheer is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="2a203-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="2a203-254">Controleer de installatie</span><span class="sxs-lookup"><span data-stu-id="2a203-254">Verify setup</span></span>

<span data-ttu-id="2a203-255">Controleer of de organisatie relaties in de bron-en doel tenants en het migratie-eindpunt in de doelsite zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2a203-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="2a203-256">Doel Tenant</span><span class="sxs-lookup"><span data-stu-id="2a203-256">Target tenant</span></span>

<span data-ttu-id="2a203-257">**Organisatie relatie**</span><span class="sxs-lookup"><span data-stu-id="2a203-257">**Organization relationship**</span></span>

<span data-ttu-id="2a203-258">Controleer of het organisatie relatie object is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="2a203-259">Hier ziet u een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="2a203-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="2a203-260">**Migratie-eindpunt**</span><span class="sxs-lookup"><span data-stu-id="2a203-260">**Migration endpoint**</span></span>

<span data-ttu-id="2a203-261">Controleer of het migratie-eindpunt object is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="2a203-262">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="2a203-263">Bron Tenant</span><span class="sxs-lookup"><span data-stu-id="2a203-263">Source tenant</span></span>

<span data-ttu-id="2a203-264">**Organisatie relatie**</span><span class="sxs-lookup"><span data-stu-id="2a203-264">**Organization relationship**</span></span>

<span data-ttu-id="2a203-265">Controleer of het organisatie relatie object is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="2a203-266">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="2a203-267">Postvakken terug verplaatsen naar de oorspronkelijke bron</span><span class="sxs-lookup"><span data-stu-id="2a203-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="2a203-268">Als een postvak weer naar de oorspronkelijke bron Tenant gaat, moet dezelfde reeks stappen en scripts worden uitgevoerd in zowel nieuwe bron als nieuwe doel tenants.</span><span class="sxs-lookup"><span data-stu-id="2a203-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="2a203-269">Het bestaande organisatie relatie object wordt bijgewerkt of toegevoegd en wordt niet opnieuw gemaakt.</span><span class="sxs-lookup"><span data-stu-id="2a203-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="2a203-270">Doelgebruikers objecten voorbereiden voor migratie</span><span class="sxs-lookup"><span data-stu-id="2a203-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="2a203-271">Gebruikers die worden gemigreerd, moeten presenteren in de doel Tenant en het Exchange Online-systeem (als e-mail gebruikers) die zijn gemarkeerd met specifieke kenmerken om de verhuizing van de cross-Tenant te activeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="2a203-272">Het systeem gaat niet naar gebruikers die niet correct zijn ingesteld in de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="2a203-273">In het volgende gedeelte vindt u meer informatie over de vereisten voor de MailUser-objecten voor de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="2a203-274">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2a203-274">Prerequisites</span></span>
  
<span data-ttu-id="2a203-275">U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="2a203-276">Als u een postvak van een bronorganisatie verplaatst, moet u een e-mail gebruikersobject in de doelorganisatie inrichten:</span><span class="sxs-lookup"><span data-stu-id="2a203-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="2a203-277">De doelgebruiker moet deze kenmerken hebben van het bronpostvak of toegewezen aan het nieuwe gebruikersobject:</span><span class="sxs-lookup"><span data-stu-id="2a203-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="2a203-278">ExchangeGUID (directe stroom van bron naar doel): de GUID van het postvak moet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="2a203-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="2a203-279">Het verplaatsings proces wordt niet voortgezet als dit niet aanwezig is op het doelobject.</span><span class="sxs-lookup"><span data-stu-id="2a203-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="2a203-280">ArchiveGUID (directe stroom van bron naar doel): de archief-GUID moet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="2a203-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="2a203-281">Het verplaatsings proces wordt niet voortgezet als dit niet aanwezig is in het doelobject.</span><span class="sxs-lookup"><span data-stu-id="2a203-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="2a203-282">(Dit is alleen vereist als het bronpostvak archief is ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="2a203-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="2a203-283">LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> "): de LegacyExchangeDN moet aanwezig zijn op de doel MailUser als x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="2a203-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="2a203-284">De verplaatsings processen worden niet uitgevoerd als dit niet voor het doelobject wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="2a203-285">UserPrincipalName: UPN wordt uitgelijnd met de nieuwe identiteit van de gebruiker of het doelbedrijf (bijvoorbeeld user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2a203-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="2a203-286">Primaire SMTPAddress – het primaire SMTP-adres wordt uitgelijnd met het nieuwe bedrijf van de gebruiker (bijvoorbeeld user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="2a203-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="2a203-287">TargetAddress/ExternalEmailAddress: e-gebruikers verwijzen naar het huidige postvak van de gebruiker dat wordt gehost in de bron Tenant (bijvoorbeeld user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="2a203-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="2a203-288">Wanneer u deze waarde toewijst, controleert u of u ook aan de PrimarySMTPAddress of met deze waarde wordt het PrimarySMTPAddress ingesteld waarmee verplaatsings fouten worden veroorzaakt.</span><span class="sxs-lookup"><span data-stu-id="2a203-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="2a203-289">U kunt geen oudere SMTP-proxyadressen van het bronpostvak toevoegen aan de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2a203-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="2a203-290">U kunt contoso.com bijvoorbeeld niet bijhouden voor de gebruiker E-mail in fabrikam.onmicrosoft.com-Tenant objecten).</span><span class="sxs-lookup"><span data-stu-id="2a203-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="2a203-291">Domeinen zijn gekoppeld aan één Azure AD-of Exchange Online-Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="2a203-292">Voorbeeld van een **doel** -MailUser-object:</span><span class="sxs-lookup"><span data-stu-id="2a203-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="2a203-293">Attribuut</span><span class="sxs-lookup"><span data-stu-id="2a203-293">Attribute</span></span>             | <span data-ttu-id="2a203-294">Value</span><span class="sxs-lookup"><span data-stu-id="2a203-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="2a203-295">Alias</span><span class="sxs-lookup"><span data-stu-id="2a203-295">Alias</span></span>                 | <span data-ttu-id="2a203-296">LaraN</span><span class="sxs-lookup"><span data-stu-id="2a203-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="2a203-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2a203-297">RecipientType</span></span>         | <span data-ttu-id="2a203-298">Sharedmailbox</span><span class="sxs-lookup"><span data-stu-id="2a203-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="2a203-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2a203-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="2a203-300">Sharedmailbox</span><span class="sxs-lookup"><span data-stu-id="2a203-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="2a203-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2a203-301">UserPrincipalName</span></span>     | <span data-ttu-id="2a203-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a203-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="2a203-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2a203-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2a203-304">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2a203-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="2a203-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="2a203-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="2a203-306">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a203-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="2a203-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2a203-307">ExchangeGuid</span></span>          | <span data-ttu-id="2a203-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2a203-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="2a203-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2a203-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="2a203-310">/o = eerste organisatie/OE = Exchange-beheergroep</span><span class="sxs-lookup"><span data-stu-id="2a203-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="2a203-311">(FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="2a203-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="2a203-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2a203-312">EmailAddresses</span></span>        | <span data-ttu-id="2a203-313">x500:/o = First organisatie/ou = Exchange-beheergroep (FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="2a203-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="2a203-314">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="2a203-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="2a203-315">SMTP: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a203-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="2a203-316">SMTP: Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="2a203-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="2a203-317">Voorbeeld van een **bron** postvak:</span><span class="sxs-lookup"><span data-stu-id="2a203-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="2a203-318">Attribuut</span><span class="sxs-lookup"><span data-stu-id="2a203-318">Attribute</span></span>             | <span data-ttu-id="2a203-319">Value</span><span class="sxs-lookup"><span data-stu-id="2a203-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="2a203-320">Alias</span><span class="sxs-lookup"><span data-stu-id="2a203-320">Alias</span></span>                 | <span data-ttu-id="2a203-321">LaraN</span><span class="sxs-lookup"><span data-stu-id="2a203-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="2a203-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="2a203-322">RecipientType</span></span>         | <span data-ttu-id="2a203-323">User Mailbox</span><span class="sxs-lookup"><span data-stu-id="2a203-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="2a203-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="2a203-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="2a203-325">User Mailbox</span><span class="sxs-lookup"><span data-stu-id="2a203-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="2a203-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="2a203-326">UserPrincipalName</span></span>     | <span data-ttu-id="2a203-327">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a203-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="2a203-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="2a203-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="2a203-329">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a203-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="2a203-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="2a203-330">ExchangeGuid</span></span>          | <span data-ttu-id="2a203-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="2a203-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="2a203-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="2a203-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="2a203-333">/o = eerste organisatie/OE = Exchange-beheergroep</span><span class="sxs-lookup"><span data-stu-id="2a203-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="2a203-334">(FYDIBOHF23SPDLT)/cn = Geadresseerden/cn = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="2a203-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="2a203-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="2a203-335">EmailAddresses</span></span>        | <span data-ttu-id="2a203-336">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a203-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="2a203-337">SMTP: Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="2a203-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="2a203-338">Er kunnen nog geen extra kenmerken worden opgenomen in een hybride Exchange-weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="2a203-339">Als dat niet zo is, moeten ze ook worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="2a203-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="2a203-340">msExchBlockedSendersHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a203-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2a203-341">msExchSafeRecipientsHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a203-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="2a203-342">msExchSafeSendersHash: schrijft online veilig en geblokkeerde gegevens van afzenders van klanten naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a203-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="2a203-343">Als het bronpostvak zich in LitigationHold bevindt en de grootte van de bronvermeldingen voor herstelbare items groter is dan de standaarddatabase (30 GB), wordt de verhuizing niet voortgezet, aangezien de doel quota kleiner is dan de grootte van het bronpostvak.</span><span class="sxs-lookup"><span data-stu-id="2a203-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="2a203-344">U kunt het doel-e-mail gebruikersobject bijwerken om de vlaggen van het ELC-postvak van de bronomgeving naar het doel te laten uitvouwen, zodat het doelsysteem de quota van de e-mail gebruiker tot 100 GB uitbreidt, zodat de site naar het doel wordt verplaatst.</span><span class="sxs-lookup"><span data-stu-id="2a203-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="2a203-345">Deze instructies werken alleen voor hybride identiteit met Azure AD Connect, aangezien de opdrachten voor de stempel van de ELC-vlaggen niet zichtbaar zijn voor tenantbeheerders.</span><span class="sxs-lookup"><span data-stu-id="2a203-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="2a203-346">VOORBEELD: ALS DAT IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="2a203-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2a203-347">In dit script wordt uitgegaan van een verbinding met beide bronpostvak (om bronwaarden te verkrijgen) en de on-premises Active Directory (voor het maken van een stempel van het object ADUser).</span><span class="sxs-lookup"><span data-stu-id="2a203-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="2a203-348">Als er voor de bron een actie-item voor zaken of eenmalige aanmelding is ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="2a203-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2a203-349">Hierdoor wordt de Dumpster grootte van de bestemmings account groter tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="2a203-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="2a203-350">Niet-hybride doel tenants kunnen de quota voor de map herstelbare items voor de mailgebruikers voorafgaand aan de migratie wijzigen door de volgende opdracht uit te voeren om het doorsturen van berichten in het object MailUser te activeren en de quota te verhogen tot 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="2a203-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="2a203-351">Opmerking Dit werkt niet voor tenants in hybride.</span><span class="sxs-lookup"><span data-stu-id="2a203-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="2a203-352">Gebruikers in de doelorganisatie moeten een licentie hebben met de juiste Exchange Online-abonnementen die van toepassing zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="2a203-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="2a203-353">U kunt een licentie vóór het verplaatsen van een postvak toepassen, maar slechts eenmaal dat de doel-e-mail gebruiker juist is ingesteld met ExchangeGUID en proxyadressen.</span><span class="sxs-lookup"><span data-stu-id="2a203-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="2a203-354">Wanneer u een licentie toepast voordat de ExchangeGUID is toegepast, wordt het nieuwe postvak in de doelorganisatie weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="2a203-355">Wanneer u een licentie toepast op een postvak of e-mail-object, worden alle SMTP-proxyAddresses gemigreerd, zodat alleen geverifieerde domeinen worden opgenomen in de van de Exchange-records.</span><span class="sxs-lookup"><span data-stu-id="2a203-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="2a203-356">U moet ervoor zorgen dat de doelgebruiker geen eerdere ExchangeGuid heeft die niet overeenkomen met de bron ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="2a203-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="2a203-357">Dit kan gebeuren als de doelgebruiker e-mail eerder een licentie voor Exchange Online is en een postvak is ingericht.</span><span class="sxs-lookup"><span data-stu-id="2a203-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="2a203-358">Als de doel-mailgebruiker eerder een licentie voor of een ExchangeGuid heeft die niet overeenkomt met de bron ExchangeGuid, moet u een opschooning van de Cloud gebruiker E-mail uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2a203-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="2a203-359">Voor deze Cloud converteren e kunt u de opdracht uitvoeren `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="2a203-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="2a203-360">Dit proces is onomkeerbaar.</span><span class="sxs-lookup"><span data-stu-id="2a203-360">This process is irreversible.</span></span> <span data-ttu-id="2a203-361">Als het object een softDeleted-postvak heeft, kunt u dit na dit punt niet meer herstellen.</span><span class="sxs-lookup"><span data-stu-id="2a203-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="2a203-362">Als dit is uitgeschakeld, kunt u echter het juiste ExchangeGuid synchroniseren met het doelobject en moet u het bronpostvak verbinden met het nieuw gemaakte doel postvak.</span><span class="sxs-lookup"><span data-stu-id="2a203-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="2a203-363">(Naslaggids voor naslaginformatie over de nieuwe parameter.)</span><span class="sxs-lookup"><span data-stu-id="2a203-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="2a203-364">Objecten met eerder postvakken zoeken met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="2a203-365">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="2a203-366">Wis de tijdelijke handmatig verwijderde postvak met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="2a203-367">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="2a203-368">Postvak migraties uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2a203-368">Perform mailbox migrations</span></span>

<span data-ttu-id="2a203-369">Migraties van Exchange-postvak van cross-Tenant worden verzonden als migratie batches die zijn geïnitieerd via de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="2a203-370">Dit is vergelijkbaar met de manier waarop migratie batches voor onderweg worden gebruikt wanneer ze worden gemigreerd van Exchange on-premises naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2a203-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="2a203-371">Migratie batches maken</span><span class="sxs-lookup"><span data-stu-id="2a203-371">Create Migration batches</span></span>

<span data-ttu-id="2a203-372">Hier ziet u een voorbeeld van een batchgewijze migratie batch voor het verplaatsen van de overstap.</span><span class="sxs-lookup"><span data-stu-id="2a203-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="2a203-373">Het e-mailadres in het CSV-bestand moet de naam zijn die is opgegeven in de doel Tenant, niet de bron Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="2a203-374">Het verzenden van migratie batches wordt ook ondersteund door het nieuwe Exchange-Beheercentrum wanneer u de optie Cross-Tenant selecteert.</span><span class="sxs-lookup"><span data-stu-id="2a203-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="2a203-375">On-premises mailgebruikers bijwerken</span><span class="sxs-lookup"><span data-stu-id="2a203-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="2a203-376">Wanneer het postvak van de bron naar het doel wordt verplaatst, moet u ervoor zorgen dat de on-premises e-mail gebruikers, zowel bron als doel, worden bijgewerkt met het nieuwe targetAddress.</span><span class="sxs-lookup"><span data-stu-id="2a203-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="2a203-377">In de voorbeelden wordt de targetDeliveryDomain in de verhuizing van **contoso \. onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="2a203-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="2a203-378">Werk de e-mail gebruikers bij met dit targetAddress.</span><span class="sxs-lookup"><span data-stu-id="2a203-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="2a203-379">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="2a203-379">Frequently asked questions</span></span>
 
<span data-ttu-id="2a203-380">**Moeten we na de verhuizing RemoteMailboxes bijwerken in de bron on-premises?**</span><span class="sxs-lookup"><span data-stu-id="2a203-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="2a203-381">Ja, u moet het bericht targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de on-premises bron gebruikers bijwerken wanneer het bron Tenant postvak wordt verplaatst naar de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="2a203-382">Hoewel e-mail routering de verwijzingen kan volgen voor meerdere e-mail gebruikers met verschillende gegevens, moet u beschikbaarheidsinfo voor e-mail gebruikers richten op de locatie van de gebruiker van het postvak.</span><span class="sxs-lookup"><span data-stu-id="2a203-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="2a203-383">Zoeken naar beschikbaarheidsinfo gaat niet over meerdere redirecties.</span><span class="sxs-lookup"><span data-stu-id="2a203-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="2a203-384">**Migreert de inhoud van de map teams-chat cross-Tenant?**</span><span class="sxs-lookup"><span data-stu-id="2a203-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="2a203-385">Nee, de inhoud van de map teams-chatberichten wordt niet gemigreerd naar een andere Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="2a203-386">**Hoe kan ik de verplaatsingen van een zelfstandige verplaatsings informatie weergeven, niet mijn onboarding en offboarding verplaatsen?**</span><span class="sxs-lookup"><span data-stu-id="2a203-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="2a203-387">Gebruik de `-flags` parameter.</span><span class="sxs-lookup"><span data-stu-id="2a203-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="2a203-388">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="2a203-389">**Kunt u voorbeeldscripts opgeven voor het kopiëren van kenmerken die worden gebruikt voor testen?**</span><span class="sxs-lookup"><span data-stu-id="2a203-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="2a203-390">VOORBEELD: ALS DAT IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="2a203-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="2a203-391">In dit script wordt uitgegaan van een verbinding met beide bronpostvak (om bronwaarden te verkrijgen) en de on-premises Active Directory Domain Services (voor het maken van een stempel van het object ADUser).</span><span class="sxs-lookup"><span data-stu-id="2a203-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="2a203-392">Als er voor de bron een actie-item voor zaken of eenmalige aanmelding is ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="2a203-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="2a203-393">Hierdoor wordt de Dumpster grootte van de bestemmings account groter tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="2a203-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="2a203-394">**Hoe krijg ik toegang tot Outlook op dag 1 nadat het postvak gebruiken is verplaatst?**</span><span class="sxs-lookup"><span data-stu-id="2a203-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="2a203-395">Aangezien slechts één Tenant eigenaar kan zijn van een domein, wordt de voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doel Tenant wanneer het postvak wordt verplaatst. alleen de domeinen die zijn gekoppeld aan de nieuwe Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="2a203-396">Outlook gebruikt de nieuwe UPN voor verificatie bij de service en het Outlook-profiel verwacht de oudere primaire SMTPAddress zodat deze overeenkomt met het postvak in het doelsysteem.</span><span class="sxs-lookup"><span data-stu-id="2a203-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="2a203-397">Aangezien het oude adres niet in het doelsysteem staat, maakt het Outlook-profiel geen verbinding met het zojuist verplaatste postvak.</span><span class="sxs-lookup"><span data-stu-id="2a203-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="2a203-398">Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN, het primaire SMTP-adres en de OST-inhoud opnieuw synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="2a203-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="2a203-399">Plan de uitvoering van de gebruikers voor verdere uitvoering.</span><span class="sxs-lookup"><span data-stu-id="2a203-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="2a203-400">U moet beschikken over de mogelijkheid om netwerk gebruik te maken van de clientprofielen van Outlook en de volgende OST-en OAB-bestanden worden gedownload naar clients.</span><span class="sxs-lookup"><span data-stu-id="2a203-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="2a203-401">**Welke Exchange-gebruikers van de domein///////dat heb ik nodig om een verplaatsing tussen meerdere tenants in te stellen of te voltooien?**</span><span class="sxs-lookup"><span data-stu-id="2a203-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="2a203-402">Er is een matrix met rollen op basis van de hypothese met gedelegeerde rechten tijdens het uitvoeren van een Postvak verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="2a203-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="2a203-403">Momenteel zijn er twee rollen nodig:</span><span class="sxs-lookup"><span data-stu-id="2a203-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="2a203-404">De eerste functie is voor een eenmalige instel taak waarmee de autorisatie van het verplaatsen van inhoud in of uit de begrenzing van uw Tenant/organisatie wordt vastgelegd.</span><span class="sxs-lookup"><span data-stu-id="2a203-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="2a203-405">Aangezien het verplaatsen van gegevens uit uw organisatie besturingselement een belangrijke rol heeft voor alle bedrijven, hebben we gecommuniceerd met de best toegewezen rol van de beheerder van de organisatie (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="2a203-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="2a203-406">Deze rol moet een nieuw OrganizationRelationship wijzigen of instellen waarmee de MailboxMoveCapability van de externe organisatie wordt gedefinieerd.</span><span class="sxs-lookup"><span data-stu-id="2a203-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="2a203-407">Alleen de OrgAdmin kan de instelling MailboxMoveCapability wijzigen, terwijl andere kenmerken van het OrganizationRelationhip kunnen worden beheerd door de beheerder van federatieve delen.</span><span class="sxs-lookup"><span data-stu-id="2a203-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="2a203-408">De rol van het uitvoeren van de feitelijke verplaatsingsopdrachten kan worden gedelegeerd aan een functie op een lager niveau.</span><span class="sxs-lookup"><span data-stu-id="2a203-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="2a203-409">Met behulp van de parameter wordt de functie voor het verplaatsen van postvakken binnen of buiten de organisatie toegewezen `-RemoteTenant` .</span><span class="sxs-lookup"><span data-stu-id="2a203-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="2a203-410">**Hoe kan ik de naam van het SMTP-adres voor targetAddress (TargetDeliveryDomain) op het geconverteerde postvak selecteren (voor e-mail gebruikers converteren)?**</span><span class="sxs-lookup"><span data-stu-id="2a203-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="2a203-411">Het Exchange-postvak wordt verplaatst met MEVR. het oorspronkelijke bronpostvak voor de conversie naar een e-mailadres (proxyAddress) op het doelobject.</span><span class="sxs-lookup"><span data-stu-id="2a203-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="2a203-412">Wanneer het proces is voltooid, wordt de TargetDeliveryDomain-waarde die is doorgegeven aan de opdracht verplaatsen, gecontroleerd op de doelzijde van dit domein.</span><span class="sxs-lookup"><span data-stu-id="2a203-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="2a203-413">Wanneer er een overeenkomst wordt gevonden, wordt het overeenkomende proxyAddress gebruikt voor het instellen van het ExternalEmailAddress (targetAddress) voor het geconverteerde postvak (Now Mail User).</span><span class="sxs-lookup"><span data-stu-id="2a203-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="2a203-414">**Hoe wordt de overgang van postvak machtigingen gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="2a203-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="2a203-415">Postvak machtigingen omvatten verzenden namens en Postvak toegang:</span><span class="sxs-lookup"><span data-stu-id="2a203-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="2a203-416">Verzenden namens (AD: publicDelegates) Hiermee wordt de DN van geadresseerden opgeslagen die toegang hebben tot het postvak van een gebruiker als gemachtigde.</span><span class="sxs-lookup"><span data-stu-id="2a203-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="2a203-417">Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de overgang van het postvak.</span><span class="sxs-lookup"><span data-stu-id="2a203-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="2a203-418">Als het bronpostvak is ingesteld op publicDelegates, moet u het publicDelegates op het doel postvak opnieuw instellen nadat de gebruiker E-mail voor de conversie van een postvak in de doelomgeving is voltooid met behulp van de `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` opdracht.</span><span class="sxs-lookup"><span data-stu-id="2a203-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="2a203-419">Postvak machtigingen die zijn opgeslagen in het postvak, worden verplaatst met het postvak wanneer zowel de primaire als de gemachtigde worden verplaatst naar het doelsysteem.</span><span class="sxs-lookup"><span data-stu-id="2a203-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="2a203-420">De gebruiker TestUser_7 heeft bijvoorbeeld machtiging fullaccess, TestUser_8 in de Tenant SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="2a203-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="2a203-421">Wanneer het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doeldirectory.</span><span class="sxs-lookup"><span data-stu-id="2a203-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="2a203-422">Voorbeelden van het gebruik van *Get-mailboxpermission kunt* voor TestUser_7 in de bron-en doel tenants worden hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="2a203-423">Exchange-cmdlets worden volgens de bron en het doel met bovenstaande stappen opgelost.</span><span class="sxs-lookup"><span data-stu-id="2a203-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="2a203-424">Hier ziet u een voorbeeld van de uitvoer van de Postvak machtiging voordat u deze verplaatst.</span><span class="sxs-lookup"><span data-stu-id="2a203-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="2a203-425">Hier ziet u een voorbeeld van de uitvoer van de Postvak machtiging na de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="2a203-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="2a203-426">Het postvak en de Agendamachtigingen voor de cross-Tenant worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="2a203-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="2a203-427">U moet principals en gemachtigden indelen in geconsolideerde verplaatsings batches, zodat deze verbonden postvakken op hetzelfde moment van de bron Tenant worden overgezet.</span><span class="sxs-lookup"><span data-stu-id="2a203-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="2a203-428">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="2a203-428">Known issues</span></span> 

-  <span data-ttu-id="2a203-429">**Probleem: automatisch uitgevouwen archieven kunnen niet worden gemigreerd.**</span><span class="sxs-lookup"><span data-stu-id="2a203-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="2a203-430">De functie voor migratie van cross tenants ondersteunt migraties van het primaire postvak en het archief postvak voor een bepaalde gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2a203-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="2a203-431">Als de gebruiker in de bron maar een automatisch uitgevouwen archief heeft dat meer dan één archief postvak heeft, kan de extra archiefmap niet worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="2a203-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="2a203-432">**Probleem: Cloud mailgebruikerss met een niet-eigenaar SMTP-proxyAddress blokkeren met een achtergrond bewegen.**</span><span class="sxs-lookup"><span data-stu-id="2a203-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="2a203-433">Als u op de site van een doel Tenant een gebruiker maakt, moet u ervoor zorgen dat alle SMTP-proxyadressen deel uitmaken van de doel Tenant.</span><span class="sxs-lookup"><span data-stu-id="2a203-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="2a203-434">Als er een SMTP-proxyAddress bestaat voor de doelgebruiker die niet behoort tot de lokale Tenant, wordt de conversie van de mail-gebruiker naar Postvak voorkomen.</span><span class="sxs-lookup"><span data-stu-id="2a203-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="2a203-435">Dit komt door onze zekerheid dat postvak objecten alleen e-mail kunnen verzenden van domeinen waarvoor de Tenant gezaghebbend is (domeinen die door de Tenant worden geclaimd):</span><span class="sxs-lookup"><span data-stu-id="2a203-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="2a203-436">Wanneer u gebruikers van on-premises via Azure AD Connect synchroniseert, dient u on-premises e-mail gebruikersobjecten in te richten met ExternalEmailAddress die verwijzen naar de bron Tenant, waarbij het postvak bestaat (laran@contoso \. onmicrosoft.com) en u het PrimarySmtpAddress stempelt als een domein in de doel Tenant (Lara.Newton@northwind \. com).</span><span class="sxs-lookup"><span data-stu-id="2a203-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="2a203-437">Deze waarden worden gesynchroniseerd met de Tenant en een juiste e-mail gebruiker wordt ingericht en klaar voor de migratie.</span><span class="sxs-lookup"><span data-stu-id="2a203-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="2a203-438">Hier ziet u een voorbeeld van een object.</span><span class="sxs-lookup"><span data-stu-id="2a203-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="2a203-439">Het \* \. com-adres contoso. onmicrosoft\* is *niet* aanwezig in de matrix EmailAddress/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="2a203-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="2a203-440">**Probleem: gebruikersobjecten met een externe primaire SMTP-adres worden gewijzigd/opnieuw ingesteld op intern geclaimde domeinen**</span><span class="sxs-lookup"><span data-stu-id="2a203-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="2a203-441">MailUser Objects zijn pointers naar niet-lokale postvakken.</span><span class="sxs-lookup"><span data-stu-id="2a203-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="2a203-442">In het geval van cross-Tenant migraties gebruiken we MailUser Objects om het bronpostvak (vanuit de perspectief van de doelorganisatie) of het doel postvak (vanuit het perspectief van de bronorganisatie) te vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="2a203-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="2a203-443">De e-mail gebruikers hebben een ExternalEmailAddress (targetAddress) die verwijzen naar het SMTP-adres van het feitelijke postvak (ProxyTest \@ fabrikam \. onmicrosoft.com) en primarySMTP-adres dat staat voor het weergegeven SMTP-adres van de gebruikers van het postvak in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2a203-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="2a203-444">In sommige organisaties wordt het primaire SMTP-adres weergegeven als een extern SMTP-adres, niet als een adres dat eigendom is van de lokale Tenant (zoals fabrikam.com in plaats van contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2a203-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="2a203-445">Wanneer bijvoorbeeld een Exchange-serviceplan-object wordt toegepast op de e-mail gebruiker via licentiebewerkingen, wordt het primaire SMTP-adres gewijzigd in de weergave van een domein dat is geverifieerd door de lokale organisatie (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2a203-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="2a203-446">Er zijn twee mogelijke redenen:</span><span class="sxs-lookup"><span data-stu-id="2a203-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="2a203-447">Wanneer een Exchange-serviceplan wordt toegepast op een e-mail gebruiker, begint het Azure AD-proces om te zorgen dat er geen e-mailberichten, spoofing of e-mailberichten vanuit een andere Tenant kunnen worden verzonden.</span><span class="sxs-lookup"><span data-stu-id="2a203-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="2a203-448">Alle SMTP-adressen in een object van de geadresseerde met deze serviceplannen worden verwijderd als het adres niet door de lokale organisatie wordt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="2a203-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="2a203-449">Zoals in het voorbeeld is dit het geval dat het com-domein van Fabikam \. niet wordt geverifieerd door de contoso \. onmicrosoft.com-Tenant, zodat de reinigings het \. com-domein van Fabrikam verwijdert.</span><span class="sxs-lookup"><span data-stu-id="2a203-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="2a203-450">Als u dit externe domein wilt behouden voor de migratie, moet u vóór de migratie of na migratie eerst uw migratie processen wijzigen in stripesets na voltooiing of voor de overstap om ervoor te zorgen dat de gebruikers op de verwachte manier de juiste plaats hebben.</span><span class="sxs-lookup"><span data-stu-id="2a203-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="2a203-451">U moet ervoor zorgen dat het postvak object juist is gelicentieerd voor geen invloed heeft op de e-mail service.</span><span class="sxs-lookup"><span data-stu-id="2a203-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="2a203-452">Een voorbeeld van een script voor het verwijderen van de serviceplannen voor een MailUser in de contoso \. onmicrosoft.com-Tenant wordt hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="2a203-453">Resultaten van de set ServicePlans worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2a203-453">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="2a203-454">De PrimarySMTPAddress van de gebruiker is niet meer te reinigen.</span><span class="sxs-lookup"><span data-stu-id="2a203-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="2a203-455">Het fabrikam.com-domein is niet eigendom van de contoso.onmicrosoft.com-Tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="2a203-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="2a203-456">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="2a203-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="2a203-457">Wanneer msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), worden bij on-premises gebruikers die worden gemigreerd naar de doel Tenant, de proxy-opmaak logica in azure verwijdert en de primarySMTP opnieuw ingesteld op een domein met eigenaar.</span><span class="sxs-lookup"><span data-stu-id="2a203-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="2a203-458">Door msExchRemoteRecipientType te wissen in de on-premises MailUser, is de logica voor de reiniging van de proxy niet langer van toepassing.</span><span class="sxs-lookup"><span data-stu-id="2a203-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="2a203-459">Hieronder ziet u de volledige set service abonnementen die Exchange Online omvatten.</span><span class="sxs-lookup"><span data-stu-id="2a203-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="2a203-460">Naam</span><span class="sxs-lookup"><span data-stu-id="2a203-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="2a203-461">Advanced eDiscovery-opslag (500 GB)</span><span class="sxs-lookup"><span data-stu-id="2a203-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="2a203-462">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="2a203-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="2a203-463">Preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="2a203-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="2a203-464">Exchange Enterprise CAL'S-Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="2a203-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="2a203-465">Basisprincipes van Exchange</span><span class="sxs-lookup"><span data-stu-id="2a203-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="2a203-466">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="2a203-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="2a203-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="2a203-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="2a203-468">Exchange Online (abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="2a203-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="2a203-469">Exchange Online (abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="2a203-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="2a203-470">Exchange Online Archiving voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2a203-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="2a203-471">Exchange Online Archiving voor Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2a203-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="2a203-472">Invoegtoepassing Exchange Online inactief gebruikers</span><span class="sxs-lookup"><span data-stu-id="2a203-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="2a203-473">Exchange Online kiosk</span><span class="sxs-lookup"><span data-stu-id="2a203-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="2a203-474">Multi-geografische Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2a203-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="2a203-475">Exchange Online Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="2a203-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="2a203-476">POP voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2a203-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="2a203-477">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a203-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="2a203-478">Informatie belemmeringen</span><span class="sxs-lookup"><span data-stu-id="2a203-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="2a203-479">Information Protection voor Office 365-Premium</span><span class="sxs-lookup"><span data-stu-id="2a203-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="2a203-480">Information Protection voor Office 365-Standard</span><span class="sxs-lookup"><span data-stu-id="2a203-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="2a203-481">Inzichten op MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="2a203-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="2a203-482">Geavanceerde controle voor Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2a203-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="2a203-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="2a203-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="2a203-484">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="2a203-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="2a203-485">Microsoft MyAnalytics (volledig)</span><span class="sxs-lookup"><span data-stu-id="2a203-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="2a203-486">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="2a203-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="2a203-487">Office 365 Advanced Threat Protection (abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="2a203-487">Office 365 Advanced Threat Protection (Plan 1)</span></span>    |
   | <span data-ttu-id="2a203-488">Office 365 Advanced Threat Protection (abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="2a203-488">Office 365 Advanced Threat Protection (Plan 2)</span></span>    |
   | <span data-ttu-id="2a203-489">Toegangsbeheer voor Office 365-bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="2a203-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="2a203-490">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="2a203-490">Outlook Customer Manager</span></span>                          |
   | <span data-ttu-id="2a203-491">Premium-codering in Office 365</span><span class="sxs-lookup"><span data-stu-id="2a203-491">Premium Encryption in Office 365</span></span>                  |
   || 
 