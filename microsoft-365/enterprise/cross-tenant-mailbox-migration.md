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
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="37ae0-103">Migratie van postvakken tussen tenants (preview)</span><span class="sxs-lookup"><span data-stu-id="37ae0-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="37ae0-104">Voorheen, wanneer een Exchange Online-tenant postvakken moest verplaatsen naar een andere tenant in dezelfde Exchange Online-service, moesten ze deze volledig offboarden naar on-premises en ze vervolgens onboarden naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="37ae0-105">Met de nieuwe functie voor migratie van postvakken op verschillende tenants kunnen tenantbeheerders in zowel de bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="37ae0-106">Hiermee verwijdert u de noodzaak om postvakken aan de board- en onboard-app toe te laten.</span><span class="sxs-lookup"><span data-stu-id="37ae0-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="37ae0-107">Doorgaans moet u tijdens fusies of overnames gebruikers en inhoud naar een nieuwe tenant kunnen verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="37ae0-108">Wanneer de beheerder van de doelten tenant de overstap uitvoert, heet dit een pull-move, vergelijkbaar met on-premises onboarding-migraties voor de cloud.</span><span class="sxs-lookup"><span data-stu-id="37ae0-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="37ae0-109">Exchange-postvakken op meerdere tenants worden volledig zelf gebruikt door tenantbeheerders, met behulp van bekende interfaces die kunnen worden geschreven in de grotere werkstromen die nodig zijn om gebruikers over te brengen naar de nieuwe organisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="37ae0-110">Beheerders kunnen de cmdlet, beschikbaar via de beheerrol Postvakken verplaatsen, gebruiken om het verplaatsen tussen `New-MigrationBatch` tenants uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="37ae0-111">Het overstapproces omvat tenantautorisatiecontroles tijdens postvaksynchronisatie en -finalisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="37ae0-112">Gebruikers die migreren, moeten in de doelten tenant Exchange Online aanwezig zijn als MailUsers, gemarkeerd met specifieke kenmerken om het migreren tussen tenants mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="37ae0-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="37ae0-113">Het systeem mislukt voor gebruikers die niet correct zijn ingesteld in de doel-tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="37ae0-114">Wanneer de bewegingen zijn voltooid, wordt het bronsysteempostvak geconverteerd naar MailUser en wordt het targetAddress (weergegeven als ExternalEmailAddress in Exchange) voorzien van een stempel met het routeringsadres naar de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="37ae0-115">Met deze procedure wordt de oudere MailUser in de bronten tenant verlaat en bestaat er een periode van co-aanwezigheid en e-mailroutering.</span><span class="sxs-lookup"><span data-stu-id="37ae0-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="37ae0-116">Wanneer bedrijfsprocessen zijn toegestaan, kan de bronten tenant MailUser verwijderen of converteren naar een e-mailcontactcontact.</span><span class="sxs-lookup"><span data-stu-id="37ae0-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="37ae0-117">Migraties van Exchange-postvakken tussen tenants worden alleen ondersteund voor tenants in de hybride omgeving of in de cloud, of een combinatie van deze twee.</span><span class="sxs-lookup"><span data-stu-id="37ae0-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="37ae0-118">In dit artikel wordt het proces voor het verplaatsen van postvakken tussen tenants beschreven en vindt u richtlijnen voor het voorbereiden van de bron- en doelten tenants voor het verplaatsen van inhoud.</span><span class="sxs-lookup"><span data-stu-id="37ae0-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="37ae0-119">Bron- en doelten tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="37ae0-119">Preparing source and target tenants</span></span>

<span data-ttu-id="37ae0-120">Voor de migratiefunctie voor Exchange-postvakken tussen tenants zijn autorisatie en bereik voor migraties tussen tenants vereist.</span><span class="sxs-lookup"><span data-stu-id="37ae0-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="37ae0-121">Met de Azure Enterprise-toepassing en Key Vault-opslagoplossingen kunnen tenantbeheerders nu zowel autorisatie als het beperken van migraties van Exchange Online-postvakken van de ene tenant naar de andere beheren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="37ae0-122">Bij het verplaatsen van postvakken tussen tenants wordt een uitnodiging en toestemmingsmodel ondersteund voor het maken van een Azure Active Directory-toepassing (Azure AD) die wordt gebruikt voor verificatie tussen een tenantpaar.</span><span class="sxs-lookup"><span data-stu-id="37ae0-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="37ae0-123">Extra onderdelen, zoals een organisatierelatie en een migratie-eindpunt, zijn ook vereist.</span><span class="sxs-lookup"><span data-stu-id="37ae0-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="37ae0-124">Deze sectie bevat niet de specifieke stappen die nodig zijn voor het voorbereiden van de MailUser-gebruikersobjecten in de doelmap en bevat ook niet de voorbeeldopdracht om een migratiebatch in te dienen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="37ae0-125">Zie [Doelgebruikersobjecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="37ae0-126">Vereisten</span><span class="sxs-lookup"><span data-stu-id="37ae0-126">Prerequisites</span></span>

<span data-ttu-id="37ae0-127">Voor de functie voor het verplaatsen van postvakken tussen tenants moet [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) een tenantpaarsspecifieke Azure-toepassing tot stand brengen om het certificaat/geheim dat wordt gebruikt voor verificatie en geautoriseerde postvakmigratie van de ene tenant naar de andere veilig op te slaan en te openen, waardoor alle vereisten voor het delen van certificaten/geheimen tussen tenants worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="37ae0-128">Voordat u begint, moet u de benodigde machtigingen hebben om de implementatiescripts uit te voeren om Azure Key Vault, Move Mailbox-toepassing, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="37ae0-129">Doorgaans heeft een globale beheerder toestemming om alle configuratiestappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="37ae0-130">Bovendien zijn beveiligingsgroepen met e-mail in de bron tenant vereist voordat de installatie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="37ae0-131">Deze groepen worden gebruikt om een bereik op te geven in de lijst met postvakken die van de bronten tenant (of soms resourceten tenant genoemd) naar de doelten tenant kunnen worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="37ae0-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="37ae0-132">Hierdoor kan de beheerder van de bronten tenant de specifieke set postvakken beperken of een bereik instellen dat moet worden verplaatst, zodat onbedoelde gebruikers niet kunnen worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="37ae0-133">Geneste groepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="37ae0-133">Nested groups are not supported.</span></span>

<span data-ttu-id="37ae0-134">U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken gaat verplaatsen) om hun Microsoft 365-tenant-id te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="37ae0-135">Deze tenant-id wordt gebruikt in het veld `DomainName` Organisatierelatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="37ae0-136">Als u de tenant-id van een abonnement wilt verkrijgen, meld u zich aan bij het Microsoft 365-beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="37ae0-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="37ae0-137">Klik op het kopieerpictogram voor de eigenschap Tenant-id om deze naar het Klembord te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="37ae0-138">Dit proces werkt als eerste.</span><span class="sxs-lookup"><span data-stu-id="37ae0-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Tenant voorbereiden op de migratie van postvakken.":::

<span data-ttu-id="37ae0-140">[Bekijk een grotere versie van deze afbeelding.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="37ae0-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="37ae0-141">Tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="37ae0-141">Prepare tenants</span></span>

<span data-ttu-id="37ae0-142">Op hoog niveau vinden de volgende configuratieacties plaats bij het uitvoeren van de installatiescripts.</span><span class="sxs-lookup"><span data-stu-id="37ae0-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="37ae0-143">De doel tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="37ae0-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="37ae0-144">Als er geen bestaande Azure-resourcegroep wordt verstrekt, wordt er een nieuwe gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="37ae0-145">Als er geen bestaande Key Vault wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="37ae0-146">Er wordt een nieuw Access-beleid gemaakt voor de Office 365 Exchange Online Mailbox Migration-toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="37ae0-147">Er wordt een nieuw certificaat gemaakt (of een bestaand certificaat, indien opgegeven) om het geheim van de migratietoepassing (SCRIPT) te bewaren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="37ae0-148">Er wordt een nieuwe Azure AD-toepassing (SCRIPT) gemaakt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="37ae0-149">Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="37ae0-150">Machtigingen voor postvakmigratie worden toegewezen aan de toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="37ae0-151">Het implementatiescript wordt onderbroken totdat de doelbeheerder toestemming geeft voor de eigen toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="37ae0-152">De doelten tenantbeheerder gaat akkoord met de machtigingen die aan de toepassing worden gegeven (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="37ae0-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="37ae0-153">Er wordt een organisatierelatie gemaakt met de doel-tenant (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="37ae0-154">Er wordt een migratie-eindpunt gemaakt om postvakken op te halen naar de doelten tenant (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="37ae0-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="37ae0-155">De bron tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="37ae0-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="37ae0-156">De bronten tenantbeheerder accepteert toestemming voor de uitnodiging voor de toepassing Postvakmigratie vanuit de doelten tenant (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="37ae0-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="37ae0-157">De bronten tenantbeheerder maakt een beveiligingsgroep met e-mail in de tenant voor de lijst met postvakken die mogen worden verplaatst door de migratietoepassing (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="37ae0-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="37ae0-158">Er wordt een organisatierelatie gemaakt met de doel tenant die opgeeft dat de postvakmigratietoepassing moet worden gebruikt voor OAuth-verificatie om de aanvraag voor verplaatsen (SCRIPT) te accepteren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="37ae0-159">Stapsgewijse instructies voor de doel tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="37ae0-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="37ae0-160">Download het SetupCrossTenantRelationshipForTargetTenant.ps1 voor het instellen van de doel tenant vanuit de [GitHub-opslagplaats.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="37ae0-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="37ae0-161">Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer op waaruit u het script wilt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="37ae0-162">Maak een externe PowerShell-verbinding met de Exchange Online-doel tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="37ae0-163">Zorg er nogmaals voor dat u de benodigde machtigingen hebt om de implementatiescripts uit te voeren om de Azure Key Vault-opslag en -certificaat, de toepassing Move Mailbox, EXO Migration Endpoint en de EXO-organisatierelatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="37ae0-164">Wijzig de map met bestanden naar de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="37ae0-165">Voer het script uit met de volgende parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="37ae0-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="37ae0-166">Parameter</span></span> | <span data-ttu-id="37ae0-167">Value</span><span class="sxs-lookup"><span data-stu-id="37ae0-167">Value</span></span> | <span data-ttu-id="37ae0-168">Vereist of Optioneel</span><span class="sxs-lookup"><span data-stu-id="37ae0-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="37ae0-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="37ae0-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="37ae0-170">Doel tenantdomein, zoals fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="37ae0-171">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-171">Required</span></span> |
    | <span data-ttu-id="37ae0-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="37ae0-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="37ae0-173">Bronten tenantdomein, zoals contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="37ae0-174">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-174">Required</span></span> |
    | <span data-ttu-id="37ae0-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="37ae0-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="37ae0-176">Het e-mailadres van de beheerder van de bron tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="37ae0-177">Dit is de bronbeheerder van de tenant die instemt met het gebruik van de postvakmigratietoepassing die is verzonden door de doelbeheerder. Dit is de beheerder die de uitnodiging per e-mail voor de toepassing ontvangt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="37ae0-178">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-178">Required</span></span> |
    | <span data-ttu-id="37ae0-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="37ae0-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="37ae0-180">Bron-tenant-organisatie-id (GUID).</span><span class="sxs-lookup"><span data-stu-id="37ae0-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="37ae0-181">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-181">Required</span></span> |
    | <span data-ttu-id="37ae0-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="37ae0-182">-SubscriptionId</span></span>                             | <span data-ttu-id="37ae0-183">Het Azure-abonnement dat moet worden gebruikt voor het maken van bronnen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="37ae0-184">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-184">Required</span></span> |
    | <span data-ttu-id="37ae0-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="37ae0-185">-ResourceGroup</span></span>                              | <span data-ttu-id="37ae0-186">De naam van de Azure-resourcegroep die de Sleutel kluis bevat of deze bevat.</span><span class="sxs-lookup"><span data-stu-id="37ae0-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="37ae0-187">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-187">Required</span></span> |
    | <span data-ttu-id="37ae0-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="37ae0-188">-KeyVaultName</span></span>                               | <span data-ttu-id="37ae0-189">Azure Key Vault-exemplaar dat het certificaat/geheim van uw postvakmigratietoepassing opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="37ae0-190">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-190">Required</span></span> |
    | <span data-ttu-id="37ae0-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="37ae0-191">-CertificateName</span></span>                            | <span data-ttu-id="37ae0-192">De naam van het certificaat bij het genereren of zoeken naar certificaten in de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="37ae0-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="37ae0-193">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-193">Required</span></span> |
    | <span data-ttu-id="37ae0-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="37ae0-194">-CertificateSubject</span></span>                         | <span data-ttu-id="37ae0-195">Naam van het Azure Key Vault-certificaat, zoals CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="37ae0-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="37ae0-196">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-196">Required</span></span> |
    | <span data-ttu-id="37ae0-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="37ae0-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="37ae0-198">Te gebruiken e-mailmigratietoepassing als er al een is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="37ae0-199">Optioneel</span><span class="sxs-lookup"><span data-stu-id="37ae0-199">Optional</span></span> |
    | <span data-ttu-id="37ae0-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="37ae0-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="37ae0-201">De benodigde machtigingen voor het verlenen van machtigingen aan de postvakmigratietoepassing, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph om met deze toepassing een uitnodiging voor een toestemmingskoppeling naar de resourceten tenant te verzenden).</span><span class="sxs-lookup"><span data-stu-id="37ae0-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="37ae0-202">Vereist</span><span class="sxs-lookup"><span data-stu-id="37ae0-202">Required</span></span> |
    | <span data-ttu-id="37ae0-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="37ae0-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="37ae0-204">Parameter voor het gebruik van de toepassing die is gemaakt voor migratie en die moet worden gebruikt voor het verzenden van uitnodigingen voor toestemmingskoppelingen naar de bron tenantbeheerder. Als deze niet aanwezig is, wordt gevraagd om de referenties van de doelbeheerder om verbinding te maken met Azure Invitation Manager en de uitnodiging te verzenden als doelbeheerder.</span><span class="sxs-lookup"><span data-stu-id="37ae0-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="37ae0-205">Optioneel</span><span class="sxs-lookup"><span data-stu-id="37ae0-205">Optional</span></span> |
    | <span data-ttu-id="37ae0-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="37ae0-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="37ae0-207">Het opslagaccount waar de auditlogboeken van Key Vault worden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="37ae0-208">Optioneel</span><span class="sxs-lookup"><span data-stu-id="37ae0-208">Optional</span></span> |
    | <span data-ttu-id="37ae0-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="37ae0-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="37ae0-210">De resourcegroep met het opslagaccount voor het opslaan van auditlogboeken voor Key Vault.</span><span class="sxs-lookup"><span data-stu-id="37ae0-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="37ae0-211">Optioneel</span><span class="sxs-lookup"><span data-stu-id="37ae0-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="37ae0-212">Zorg ervoor dat u de Azure AD PowerShell-module hebt geïnstalleerd voordat u de scripts gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="37ae0-213">Raadpleeg hier ![ voor ](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) installatiestappen</span><span class="sxs-lookup"><span data-stu-id="37ae0-213">Please refer to ![here](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="37ae0-214">Het script wordt onderbroken en u wordt gevraagd de migratietoepassing voor Exchange-postvakken die tijdens dit proces is gemaakt, te accepteren of in te stemmen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="37ae0-215">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-215">Here is an example.</span></span>

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

7. <span data-ttu-id="37ae0-216">Er wordt een URL weergegeven in de externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="37ae0-217">Kopieer de verstrekte koppeling voor uw tenant toestemming en plak deze in een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="37ae0-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="37ae0-218">Meld u aan met uw globale-beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="37ae0-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="37ae0-219">Wanneer het volgende scherm wordt weergegeven, selecteert u **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="37ae0-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialoogvenster Machtigingen accepteren":::

9. <span data-ttu-id="37ae0-221">Ga terug naar de externe PowerShell-sessie en druk op Enter om verder te gaan.</span><span class="sxs-lookup"><span data-stu-id="37ae0-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="37ae0-222">De overige installatieobjecten worden door het script geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="37ae0-223">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="37ae0-224">De configuratie van de doelbeheerder is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="37ae0-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="37ae0-225">Stapsgewijse instructies voor de bronbeheerder van de tenant</span><span class="sxs-lookup"><span data-stu-id="37ae0-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="37ae0-226">Meld u aan bij uw postvak als de -ResourceTenantAdminEmail die is opgegeven door de doelbeheerder tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="37ae0-227">Zoek de e-mailuitnodiging van de doelten tenant en selecteer vervolgens **de knop Aan de** slag.</span><span class="sxs-lookup"><span data-stu-id="37ae0-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Dialoogvenster U bent uitgenodigd":::

2. <span data-ttu-id="37ae0-229">Selecteer **Accepteren om** de uitnodiging te accepteren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster voor het accepteren van machtigingen":::

   > [!NOTE]
   > <span data-ttu-id="37ae0-231">Als u dit e-mailbericht niet ontvangt of niet kunt vinden, heeft de doel tenantbeheerder een rechtstreekse URL gekregen die u kan worden gegeven om de uitnodiging te accepteren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="37ae0-232">De URL moet in het afschrift van de externe PowerShell-sessie van de doel tenantbeheerder staan.</span><span class="sxs-lookup"><span data-stu-id="37ae0-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="37ae0-233">Maak in het Microsoft 365-beheercentrum of een externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om de lijst met postvakken te beheren die door de doelten tenant mogen worden gehaald (verplaatst) van de bronten tenant naar de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="37ae0-234">U hoeft deze groep niet van tevoren te vullen, maar er moet ten minste één groep zijn opgegeven om de installatiestappen (script) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="37ae0-235">Nest-groepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="37ae0-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="37ae0-236">Download hier SetupCrossTenantRelationshipForResourceTenant.ps1 script voor het instellen van de bron tenant in de GitHub-opslagplaats: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="37ae0-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="37ae0-237">Maak een externe PowerShell-verbinding met de bronten tenant met uw Exchange-beheerdersmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="37ae0-238">Globale beheerdersmachtigingen zijn niet vereist voor het configureren van de bronten tenant, alleen de doelten tenant vanwege het proces voor het maken van Azure-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="37ae0-239">Wijzig de map in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="37ae0-240">Voer het script uit met de volgende vereiste parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="37ae0-241">Parameter</span><span class="sxs-lookup"><span data-stu-id="37ae0-241">Parameter</span></span> | <span data-ttu-id="37ae0-242">Value</span><span class="sxs-lookup"><span data-stu-id="37ae0-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="37ae0-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="37ae0-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="37ae0-244">Beveiligingsgroep met e-mail die door de bronten tenant is gemaakt voor de identiteiten/postvakken die binnen het migratiebereik vallen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="37ae0-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="37ae0-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="37ae0-246">De domeinnaam van de bronten tenant, zoals contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="37ae0-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="37ae0-247">-ApplicationId</span></span> | <span data-ttu-id="37ae0-248">Azure-toepassings-id (GUID) van de toepassing die voor de migratie wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="37ae0-249">Toepassings-id beschikbaar via je Azure Portal (Azure AD, Enterprise-toepassingen, app-naam, toepassings-id) of opgenomen in je uitnodigingse-mail.</span><span class="sxs-lookup"><span data-stu-id="37ae0-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="37ae0-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="37ae0-250">-TargetTenantDomain</span></span> | <span data-ttu-id="37ae0-251">De domeinnaam van de doel tenant, zoals fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="37ae0-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="37ae0-252">-TargetTenantId</span></span> | <span data-ttu-id="37ae0-253">Tenant-id van de doel-tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="37ae0-254">Bijvoorbeeld: de tenant-id van Azure AD van contoso \. onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="37ae0-255">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="37ae0-256">De configuratie van de bronbeheerder is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="37ae0-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="37ae0-257">Installatie controleren</span><span class="sxs-lookup"><span data-stu-id="37ae0-257">Verify setup</span></span>

<span data-ttu-id="37ae0-258">Controleer of de organisatierelaties in zowel de bron- als doelten tenants en het migratie-eindpunt in het doel goed zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="37ae0-259">Doel tenant</span><span class="sxs-lookup"><span data-stu-id="37ae0-259">Target tenant</span></span>

<span data-ttu-id="37ae0-260">**Organisatierelatie**</span><span class="sxs-lookup"><span data-stu-id="37ae0-260">**Organization relationship**</span></span>

<span data-ttu-id="37ae0-261">Controleer of het organisatierelatieobject met deze opdracht is gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="37ae0-262">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="37ae0-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="37ae0-263">**Migratie-eindpunt**</span><span class="sxs-lookup"><span data-stu-id="37ae0-263">**Migration endpoint**</span></span>

<span data-ttu-id="37ae0-264">Controleer of het migratie-eindpuntobject is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="37ae0-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="37ae0-265">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="37ae0-266">Bron tenant</span><span class="sxs-lookup"><span data-stu-id="37ae0-266">Source tenant</span></span>

<span data-ttu-id="37ae0-267">**Organisatierelatie**</span><span class="sxs-lookup"><span data-stu-id="37ae0-267">**Organization relationship**</span></span>

<span data-ttu-id="37ae0-268">Controleer of het organisatierelatieobject met deze opdracht is gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="37ae0-269">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="37ae0-270">Setup-script controleren</span><span class="sxs-lookup"><span data-stu-id="37ae0-270">Verify Setup Script</span></span>

<span data-ttu-id="37ae0-271">Als u fouten ziet tijdens de configuratie van de bron- of doelten tenants, kunt u het VerifySetup.ps1 uitvoeren in [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en de uitvoer controleren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="37ae0-272">Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:</span><span class="sxs-lookup"><span data-stu-id="37ae0-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="37ae0-273">Hier is een voorbeeld van VerifySetup.ps1 de bron tenant:</span><span class="sxs-lookup"><span data-stu-id="37ae0-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="37ae0-274">Postvakken terug verplaatsen naar de oorspronkelijke bron</span><span class="sxs-lookup"><span data-stu-id="37ae0-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="37ae0-275">Als een postvak wordt terug verplaatst naar de oorspronkelijke bronten tenant is vereist, moet dezelfde reeks stappen en scripts worden uitgevoerd in zowel nieuwe als nieuwe doelten tenants.</span><span class="sxs-lookup"><span data-stu-id="37ae0-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="37ae0-276">Het bestaande object Organisatierelatie wordt bijgewerkt of toegevoegd, niet opnieuw gemaakt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="37ae0-277">Doelgebruikersobjecten voorbereiden voor migratie</span><span class="sxs-lookup"><span data-stu-id="37ae0-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="37ae0-278">Gebruikers die migreren, moeten aanwezig zijn in de doelten tenant en het Exchange Online-systeem (als MailUsers) die zijn gemarkeerd met specifieke kenmerken om het migreren tussen tenants mogelijk te maken.</span><span class="sxs-lookup"><span data-stu-id="37ae0-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="37ae0-279">Het systeem mislukt voor gebruikers die niet correct zijn ingesteld in de doel-tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="37ae0-280">In de volgende sectie worden de vereisten voor het MailUser-object voor de doelten tenant begegevens begegevens voor gesteld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="37ae0-281">Vereisten</span><span class="sxs-lookup"><span data-stu-id="37ae0-281">Prerequisites</span></span>
  
<span data-ttu-id="37ae0-282">U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="37ae0-283">Als een postvak uit een bronorganisatie wordt verplaatst, moet u een MailUser-object inrichten in de doelorganisatie:</span><span class="sxs-lookup"><span data-stu-id="37ae0-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="37ae0-284">De doel-mailgebruiker moet deze kenmerken hebben uit het bronpostvak of zijn toegewezen aan het nieuwe gebruikersobject:</span><span class="sxs-lookup"><span data-stu-id="37ae0-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="37ae0-285">ExchangeGUID (directe stroom van bron naar doel) - De postvak-GUID moet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="37ae0-286">Het verplaatsproces gaat niet door als dit niet aanwezig is in het doelobject.</span><span class="sxs-lookup"><span data-stu-id="37ae0-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="37ae0-287">ArchiveGUID (directe stroom van bron naar doel) - De archief-GUID moet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="37ae0-288">Het verplaatsproces gaat niet door als dit niet aanwezig is in het doelobject.</span><span class="sxs-lookup"><span data-stu-id="37ae0-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="37ae0-289">(Dit is alleen vereist als archief is ingeschakeld voor het bronpostvak).</span><span class="sxs-lookup"><span data-stu-id="37ae0-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="37ae0-290">LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="37ae0-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="37ae0-291">De overstapprocessen gaan niet door als dit niet aanwezig is in het doelobject.</span><span class="sxs-lookup"><span data-stu-id="37ae0-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="37ae0-292">UserPrincipalName: de UPN komt overeen met de NIEUWE identiteit of het doelbedrijf van de gebruiker (bijvoorbeeld user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="37ae0-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="37ae0-293">Primair SMTP-adres: het primaire SMTP-adres wordt afgestemd op het NIEUWE bedrijf van de gebruiker (bijvoorbeeld user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="37ae0-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="37ae0-294">TargetAddress/ExternalEmailAddress: MailUser verwijst naar het huidige postvak van de gebruiker dat wordt gehost in de bronten tenant (bijvoorbeeld user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="37ae0-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="37ae0-295">Wanneer u deze waarde toewijst, controleert u of u primarySMTPAddress hebt of toewijst, anders wordt met deze waarde het PrimarySMTPAddress ingesteld, waardoor fouten in het verplaatsen optreden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="37ae0-296">U kunt geen oudere SMTP-proxyadressen uit het bronpostvak toevoegen aan de e-mailuser.</span><span class="sxs-lookup"><span data-stu-id="37ae0-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="37ae0-297">Zo kunt u bijvoorbeeld geen contoso.com in de fabrikam.onmicrosoft.com tenantobjecten).</span><span class="sxs-lookup"><span data-stu-id="37ae0-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="37ae0-298">Domeinen zijn alleen gekoppeld aan één Azure AD- of Exchange Online-tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="37ae0-299">Voorbeeld **van een** MailUser-object:</span><span class="sxs-lookup"><span data-stu-id="37ae0-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="37ae0-300">Attribuut</span><span class="sxs-lookup"><span data-stu-id="37ae0-300">Attribute</span></span>             | <span data-ttu-id="37ae0-301">Value</span><span class="sxs-lookup"><span data-stu-id="37ae0-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="37ae0-302">Alias</span><span class="sxs-lookup"><span data-stu-id="37ae0-302">Alias</span></span>                 | <span data-ttu-id="37ae0-303">LaraN</span><span class="sxs-lookup"><span data-stu-id="37ae0-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="37ae0-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="37ae0-304">RecipientType</span></span>         | <span data-ttu-id="37ae0-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="37ae0-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="37ae0-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="37ae0-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="37ae0-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="37ae0-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="37ae0-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="37ae0-308">UserPrincipalName</span></span>     | <span data-ttu-id="37ae0-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="37ae0-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="37ae0-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="37ae0-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="37ae0-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="37ae0-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="37ae0-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="37ae0-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="37ae0-314">ExchangeGuid</span></span>          | <span data-ttu-id="37ae0-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="37ae0-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="37ae0-316">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="37ae0-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="37ae0-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="37ae0-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="37ae0-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="37ae0-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="37ae0-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="37ae0-319">EmailAddresses</span></span>        | <span data-ttu-id="37ae0-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="37ae0-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="37ae0-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="37ae0-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="37ae0-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="37ae0-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="37ae0-324">Voorbeeld **van het postvakobject:**</span><span class="sxs-lookup"><span data-stu-id="37ae0-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="37ae0-325">Attribuut</span><span class="sxs-lookup"><span data-stu-id="37ae0-325">Attribute</span></span>             | <span data-ttu-id="37ae0-326">Value</span><span class="sxs-lookup"><span data-stu-id="37ae0-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="37ae0-327">Alias</span><span class="sxs-lookup"><span data-stu-id="37ae0-327">Alias</span></span>                 | <span data-ttu-id="37ae0-328">LaraN</span><span class="sxs-lookup"><span data-stu-id="37ae0-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="37ae0-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="37ae0-329">RecipientType</span></span>         | <span data-ttu-id="37ae0-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="37ae0-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="37ae0-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="37ae0-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="37ae0-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="37ae0-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="37ae0-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="37ae0-333">UserPrincipalName</span></span>     | <span data-ttu-id="37ae0-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="37ae0-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="37ae0-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="37ae0-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="37ae0-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="37ae0-337">ExchangeGuid</span></span>          | <span data-ttu-id="37ae0-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="37ae0-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="37ae0-339">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="37ae0-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="37ae0-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="37ae0-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="37ae0-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="37ae0-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="37ae0-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="37ae0-342">EmailAddresses</span></span>        | <span data-ttu-id="37ae0-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="37ae0-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="37ae0-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="37ae0-345">Er kunnen al aanvullende kenmerken zijn opgenomen in exchange hybrid write back.</span><span class="sxs-lookup"><span data-stu-id="37ae0-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="37ae0-346">Zo niet, dan moeten deze worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="37ae0-347">msExchBlockedSendersHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37ae0-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="37ae0-348">msExchSafeRecipientsHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37ae0-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="37ae0-349">msExchSafeSendersHash: gegevens van veilige en geblokkeerde afzenders van clients worden teruggeboekt naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="37ae0-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="37ae0-350">Als het bronpostvak litigationhold is en het bronpostvak Herstelbare items groter is dan de standaarddatabase (30 GB), worden de items niet verplaatst omdat het doelquotum kleiner is dan de grootte van het bronpostvak.</span><span class="sxs-lookup"><span data-stu-id="37ae0-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="37ae0-351">U kunt het doelobject MailUser bijwerken om de ELC-postvakvlaggen van de bronomgeving over te brengen naar de doelomgeving, waardoor het doelsysteem het quotum voor MailUser uitbreidt naar 100 GB, zodat de gebruiker naar de doelomgeving kan worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="37ae0-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="37ae0-352">Deze instructies werken alleen voor hybride identiteiten met Azure AD Connect, omdat de opdrachten om de ELC-vlaggen te stempelen niet worden getoond aan tenantbeheerders.</span><span class="sxs-lookup"><span data-stu-id="37ae0-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="37ae0-353">VOORBEELD: ZOALS HET IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="37ae0-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="37ae0-354">Dit script gaat uit van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory (om het ADUser-object van een stempel te voorzien).</span><span class="sxs-lookup"><span data-stu-id="37ae0-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="37ae0-355">Als voor de bron herstel van rechtszaken of herstel van één item is ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="37ae0-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="37ae0-356">Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="37ae0-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="37ae0-357">Niet-hybride doelten tenants kunnen het quotum voor de map Herstelbare items voor de MailUsers wijzigen vóór de migratie door de volgende opdracht uit te voeren om het in-en uit te voeren voor het in- en uit wacht plaatsen van postorders voor het MailUser-object en het quotum te verhogen naar 100 `Set-MailUser -EnableLitigationHoldForMigration $TRUE` GB:</span><span class="sxs-lookup"><span data-stu-id="37ae0-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="37ae0-358">Houd er rekening mee dat dit niet werkt voor tenants in hybride omgevingen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="37ae0-359">Gebruikers in de doelorganisatie moeten een licentie hebben voor de juiste Exchange Online-abonnementen die van toepassing zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="37ae0-360">U kunt een licentie toepassen op voor de overstap van een postvak, maar ALLEEN wanneer de doel-MailUser correct is ingesteld met ExchangeGUID- en proxyadressen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="37ae0-361">Wanneer een licentie wordt toegepast voordat ExchangeGUID wordt toegepast, wordt een nieuw postvak ingericht in de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="37ae0-362">Wanneer u een licentie op een Postvak- of MailUser-object aanvraagt, worden alle SMTP-proxyAddresses van het SMTP-type geconvergeerd, zodat alleen geverifieerde domeinen worden opgenomen in de matrix Exchange EmailAddresses.</span><span class="sxs-lookup"><span data-stu-id="37ae0-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="37ae0-363">U moet ervoor zorgen dat de doel-MailUser geen exchangeguid heeft die niet overeen komt met bron-ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="37ae0-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="37ae0-364">Dit kan gebeuren als de doel-mail-mail-gebruiker eerder een licentie voor Exchange Online had en een postvak heeft ingericht.</span><span class="sxs-lookup"><span data-stu-id="37ae0-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="37ae0-365">Als de doel-MailUser eerder een licentie had voor of een ExchangeGuid had die niet overeen komt met bron-ExchangeGuid, moet u de cloud-e-mail opschonen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="37ae0-366">Voor deze cloud-me-meus kunt u `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="37ae0-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="37ae0-367">Dit proces is onomkeerbaar.</span><span class="sxs-lookup"><span data-stu-id="37ae0-367">This process is irreversible.</span></span> <span data-ttu-id="37ae0-368">Als het object een softDeleted-postvak heeft, kan het na dit punt niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="37ae0-369">Als ze zijn gewuit, kunt u de juiste ExchangeGuid echter synchroniseren met het doelobject, zodat MRS het bronpostvak verbindt met het nieuwe doelpostvak.</span><span class="sxs-lookup"><span data-stu-id="37ae0-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="37ae0-370">(Reference EHLO blog on the new parameter.)</span><span class="sxs-lookup"><span data-stu-id="37ae0-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="37ae0-371">Met deze opdracht kunt u objecten zoeken die eerder postvakken waren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="37ae0-372">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="37ae0-373">Met deze opdracht kunt u het snel verwijderde postvak wissen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="37ae0-374">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="37ae0-375">Postvakmigraties uitvoeren</span><span class="sxs-lookup"><span data-stu-id="37ae0-375">Perform mailbox migrations</span></span>

<span data-ttu-id="37ae0-376">Migraties van Exchange-postvakken tussen tenants worden ingediend als migratiebatchs die worden gestart vanuit de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="37ae0-377">Dit is vergelijkbaar met de manier waarop migratiebatch's tijdens het overstappen van Exchange on-premises naar Microsoft 365 werken.</span><span class="sxs-lookup"><span data-stu-id="37ae0-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="37ae0-378">Migratiebatch's maken</span><span class="sxs-lookup"><span data-stu-id="37ae0-378">Create Migration batches</span></span>

<span data-ttu-id="37ae0-379">Hier is een voorbeeld van een cmdlet met een migratiebatch voor het starten van moves.</span><span class="sxs-lookup"><span data-stu-id="37ae0-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="37ae0-380">Het e-mailadres in het CSV-bestand moet het adres zijn dat is opgegeven in de doel tenant, niet de bron-tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="37ae0-381">Het indienen van migratiebatch wordt ook ondersteund vanuit het nieuwe Exchange-beheercentrum bij het selecteren van de optie voor meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="37ae0-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="37ae0-382">On-premises MailUsers bijwerken</span><span class="sxs-lookup"><span data-stu-id="37ae0-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="37ae0-383">Nadat het postvak is verplaatst van bron naar doel, moet u ervoor zorgen dat de on-premises e-mailgebruikers, zowel Bron als doel, worden bijgewerkt met het nieuwe targetAddress.</span><span class="sxs-lookup"><span data-stu-id="37ae0-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="37ae0-384">In de voorbeelden wordt targetDeliveryDomain gebruikt in de move **contoso.onmicrosoft.com.**</span><span class="sxs-lookup"><span data-stu-id="37ae0-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="37ae0-385">Werk de e-mailgebruikers bij met dit targetAddress.</span><span class="sxs-lookup"><span data-stu-id="37ae0-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="37ae0-386">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="37ae0-386">Frequently asked questions</span></span>

<span data-ttu-id="37ae0-387">**Moeten RemoteMailboxes in de bron on-premises na de overstap worden bijgewerkt?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="37ae0-388">Ja, u moet het targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de on-premises brongebruikers bijwerken wanneer het brontenderpostvak wordt verplaatst naar de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="37ae0-389">Hoewel e-mailroutering de verwijzingen kan volgen tussen meerdere e-mailgebruikers met verschillende targetAddresses, moeten de zoekactie voor vrij/bezet voor e-mailgebruikers zijn gericht op de locatie van de postvakgebruiker.</span><span class="sxs-lookup"><span data-stu-id="37ae0-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="37ae0-390">Zoekactie voor vrij/bezet zit niet achter meerdere omleidingen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="37ae0-391">**Wordt de inhoud van de Teams-chatmap gemigreerd tussen tenants?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-391">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="37ae0-392">Nee, de inhoud van de Teams-chatmap migreert niet tussen tenants.</span><span class="sxs-lookup"><span data-stu-id="37ae0-392">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="37ae0-393">**Hoe kan ik alleen moves zien die zich tussen tenants bewegen, niet mijn onboarding- en off-boarding moves?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-393">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="37ae0-394">Gebruik de `-flags` parameter.</span><span class="sxs-lookup"><span data-stu-id="37ae0-394">Use the `-flags` parameter.</span></span> <span data-ttu-id="37ae0-395">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-395">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="37ae0-396">**Kunt u voorbeeldscripts geven voor het kopiëren van kenmerken die worden gebruikt bij het testen?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-396">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="37ae0-397">VOORBEELD: ZOALS HET IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="37ae0-397">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="37ae0-398">Dit script gaat uit van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory Domain Services (om het ADUser-object te stempelen).</span><span class="sxs-lookup"><span data-stu-id="37ae0-398">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="37ae0-399">Als voor de bron herstel van rechtszaken of herstel van één item is ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="37ae0-399">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="37ae0-400">Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="37ae0-400">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="37ae0-401">**Hoe krijgen we toegang tot Outlook op dag 1 nadat het postvak voor gebruik is verplaatst?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-401">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="37ae0-402">Aangezien slechts één tenant eigenaar kan zijn van een domein, wordt het voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doelten tenant wanneer het verplaatsen van het postvak is voltooid. alleen de domeinen die aan de nieuwe tenant zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-402">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="37ae0-403">Outlook gebruikt de nieuwe UPN-gebruikers om zich te verifiëren bij de service en het Outlook-profiel verwacht dat het oude primaire SMTPAddress zal overeenkomen met het postvak in het doelsysteem.</span><span class="sxs-lookup"><span data-stu-id="37ae0-403">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="37ae0-404">Aangezien het oude adres niet in het doelsysteem staat, wordt er geen verbinding gemaakt met het Outlook-profiel om het zojuist verplaatste postvak te vinden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-404">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="37ae0-405">Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN-adres, primaire SMTP-adres en opnieuw synchroniseren van OST-inhoud.</span><span class="sxs-lookup"><span data-stu-id="37ae0-405">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="37ae0-406">Plan dienovereenkomstig terwijl u uw gebruikers batcht voor voltooiing.</span><span class="sxs-lookup"><span data-stu-id="37ae0-406">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="37ae0-407">U moet rekening houden met het netwerkgebruik en de capaciteit wanneer Outlook-clientprofielen worden gemaakt en de volgende OST- en OAB-bestanden worden gedownload naar clients.</span><span class="sxs-lookup"><span data-stu-id="37ae0-407">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="37ae0-408">**Van welke Exchange-rollen voor RBAC moet ik lid zijn om een overstap tussen tenants in te stellen of te voltooien?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-408">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="37ae0-409">Er is een matrix van rollen die zijn gebaseerd op aanname van gedelegeerde taken bij het uitvoeren van de overstap van een postvak.</span><span class="sxs-lookup"><span data-stu-id="37ae0-409">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="37ae0-410">Op dit moment zijn twee rollen vereist:</span><span class="sxs-lookup"><span data-stu-id="37ae0-410">Currently, two roles are required:</span></span>  

- <span data-ttu-id="37ae0-411">De eerste rol is voor een een tijdsinstellingstaak die de autorisatie bepaalt voor het verplaatsen van inhoud naar of buiten de organisatiegrens van de tenant of organisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-411">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="37ae0-412">Omdat het uit de organisatie halen van gegevens een zeer belangrijke taak is voor alle bedrijven, hebben we gekozen voor de meest toegewezen rol van Organisatiebeheerder (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="37ae0-412">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="37ae0-413">Deze rol moet een nieuwe OrganizationRelationship wijzigen of instellen die definieert -MailboxMoveCapability met de externe organisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-413">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="37ae0-414">Alleen OrgAdmin kan de instelling MailboxMoveCapability wijzigen, terwijl andere kenmerken van OrganizationRelationhip kunnen worden beheerd door de beheerder van Federatief delen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-414">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="37ae0-415">De rol van het uitvoeren van de feitelijke opdrachten voor verplaatsen kan worden gedelegeerd aan een functie op lager niveau.</span><span class="sxs-lookup"><span data-stu-id="37ae0-415">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="37ae0-416">De rol van Postvakken verplaatsen wordt toegewezen aan de mogelijkheid postvakken in of uit de organisatie te verplaatsen met behulp van de `-RemoteTenant` parameter.</span><span class="sxs-lookup"><span data-stu-id="37ae0-416">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="37ae0-417">**Hoe richten we ons op het GESELECTEERDE SMTP-adres voor targetAddress (TargetDeliveryDomain) voor het geconverteerde postvak (naar mailuser-conversie)?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-417">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="37ae0-418">Exchange-postvak wordt verplaatst door gebruik te maken van MRS- het targetAddress voor het oorspronkelijke bronpostvak wanneer het wordt ge converteerd naar een MailUser door een e-mailadres (proxyAddress) op het doelobject te koppelen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-418">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="37ae0-419">Tijdens het proces wordt de waarde -TargetDeliveryDomain doorgegeven in de opdracht Verplaatsen en wordt vervolgens gecontroleerd op een overeenkomende proxy voor dat domein aan de doelzijde.</span><span class="sxs-lookup"><span data-stu-id="37ae0-419">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="37ae0-420">Wanneer we een overeenkomst vinden, wordt het overeenkomende proxyAddress gebruikt om het object ExternalEmailAddress (targetAddress) in te stellen voor het geconverteerde postvak (nu MailUser).</span><span class="sxs-lookup"><span data-stu-id="37ae0-420">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="37ae0-421">**Hoe worden postvakmachtigingen overstappen?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-421">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="37ae0-422">Postvakmachtigingen zijn Verzenden namens en Postvaktoegang:</span><span class="sxs-lookup"><span data-stu-id="37ae0-422">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="37ae0-423">Met Verzenden namens (AD:publicDelegates) wordt de DN opgeslagen van geadresseerden die als gemachtigde toegang hebben tot het postvak van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="37ae0-423">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="37ae0-424">Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de postvakovergang.</span><span class="sxs-lookup"><span data-stu-id="37ae0-424">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="37ae0-425">Als publicDelegates is ingesteld voor het bronpostvak, moet u de restamp van de publicDelegates op het doelpostvak opnieuw instellen nadat de conversie van de gebruiker met gebruikers met gebruikers met postvak is voltooid in de doelomgeving door de ingebouwde postvakconversie uit te `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` zetten.</span><span class="sxs-lookup"><span data-stu-id="37ae0-425">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="37ae0-426">Postvakmachtigingen die zijn opgeslagen in het postvak worden samen met het postvak verplaatst wanneer zowel de principal als de gedelegeerde naar het doelsysteem worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="37ae0-426">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="37ae0-427">Zo krijgt de gebruiker TestUser_7 FullAccess aan de postvakgegevens TestUser_8 in de tenant SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-427">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="37ae0-428">Nadat het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doelmap.</span><span class="sxs-lookup"><span data-stu-id="37ae0-428">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="37ae0-429">Voorbeelden waarin *Gebruik wordt gemaakt van Get-MailboxPermission* TestUser_7 in zowel de bron- als doelten tenants worden hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="37ae0-429">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="37ae0-430">Exchange-cmdlets worden vooraf vooraf laten gaan door bron en doel.</span><span class="sxs-lookup"><span data-stu-id="37ae0-430">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="37ae0-431">Hier is een voorbeeld van de uitvoer van de postvakmachtiging voor een overstap.</span><span class="sxs-lookup"><span data-stu-id="37ae0-431">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="37ae0-432">Hier is een voorbeeld van de uitvoer van de postvakmachtiging na de overstap.</span><span class="sxs-lookup"><span data-stu-id="37ae0-432">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="37ae0-433">Postvak- en agendamachtigingen tussen tenants worden NIET ondersteund.</span><span class="sxs-lookup"><span data-stu-id="37ae0-433">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="37ae0-434">U moet principals en gedelegeerden organiseren in de samengevoegde move batches, zodat deze verbonden postvakken op hetzelfde moment vanuit de bronten tenant worden overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-434">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="37ae0-435">**Welke X500-proxy moet worden toegevoegd aan de doelproxyadressen van MailUser om migratie in teschakelen?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-435">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="37ae0-436">Voor de migratie van postvakken tussen tenants moet de LegacyExchangeDN-waarde van het bronpostvakobject worden voorzien van een stempel als een x500-e-mailadres op het doelobject MailUser.</span><span class="sxs-lookup"><span data-stu-id="37ae0-436">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="37ae0-437">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="37ae0-437">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="37ae0-438">Naast deze X500-proxy moet u alle X500-proxy's uit het postvak in de bron kopiëren naar het postvak in de doelserver.</span><span class="sxs-lookup"><span data-stu-id="37ae0-438">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="37ae0-439">**Waar kan ik problemen oplossen als het niet werkt?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-439">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="37ae0-440">Begin met het uitvoeren VerifySetup.ps1 script op [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en controleer de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="37ae0-440">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="37ae0-441">Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:</span><span class="sxs-lookup"><span data-stu-id="37ae0-441">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="37ae0-442">Hier is een eExample van het uitvoeren VerifySetup.ps1 op de bron tenant:</span><span class="sxs-lookup"><span data-stu-id="37ae0-442">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="37ae0-443">**Kunnen de bron- en doel tenant dezelfde domeinnaam gebruiken?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-443">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="37ae0-444">Nee.</span><span class="sxs-lookup"><span data-stu-id="37ae0-444">No.</span></span> <span data-ttu-id="37ae0-445">De domeinnamen van de bron- en doel tenant moeten uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="37ae0-445">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="37ae0-446">Bijvoorbeeld een brondomein van contoso.com en het doeldomein van fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-446">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="37ae0-447">**Worden gedeelde postvakken verplaatst en werken ze nog steeds?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-447">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="37ae0-448">Ja, maar we behouden alleen de store-machtigingen zoals beschreven in deze artikelen:</span><span class="sxs-lookup"><span data-stu-id="37ae0-448">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="37ae0-449">Microsoft Docs | Machtigingen voor geadresseerden beheren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="37ae0-449">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="37ae0-450">Microsoft Support | Exchange- en Outlook-postvakmachtigingen verlenen in Office 365 Dedicated</span><span class="sxs-lookup"><span data-stu-id="37ae0-450">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="37ae0-451">**Is Azure Key Vault vereist en wanneer worden transacties uitgevoerd?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-451">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="37ae0-452">Ja, een Azure-abonnement is vereist om Key Vault te gebruiken voor het opslaan van het certificaat om migratie te autor toen dit werd geautoriseerd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-452">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="37ae0-453">In tegenstelling tot onboarding-migraties, waarbij gebruikersnaam & wachtwoord wordt gebruikt voor verificatie bij de bron, maken migraties van postvakken tussen tenants gebruik van OAuth en dit certificaat als het geheim of de referenties.</span><span class="sxs-lookup"><span data-stu-id="37ae0-453">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="37ae0-454">Toegang tot de Key Vault moet worden behouden in alle postvakmigraties, aangezien deze eenmaal aan het begin en het einde van de migratie wordt gebruikt, en ook eenmaal per 24 uur tijdens incrementele synchronisatietijden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-454">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="37ae0-455">U kunt de kostendetails van AKV hier [bekijken.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="37ae0-455">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="37ae0-456">**Hebt u aanbevelingen voor batches?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-456">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="37ae0-457">Niet meer dan 2000 postvakken per batch.</span><span class="sxs-lookup"><span data-stu-id="37ae0-457">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="37ae0-458">We raden u ten zeerste aan batches twee weken vóór de cut-over datum in te dienen, aangezien dit geen gevolgen heeft voor de eindgebruikers tijdens de synchronisatie. Als u richtlijnen nodig hebt voor postvakken met een hoeveelheid van meer dan 50.000, kunt u contact op met de distributielijst voor technische feedback op crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="37ae0-458">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="37ae0-459">**Wat moet ik doen als ik Serviceversleuteling gebruik met de klantsleutel?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-459">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="37ae0-460">Het postvak wordt ontsleuteld voordat u het verplaatst.</span><span class="sxs-lookup"><span data-stu-id="37ae0-460">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="37ae0-461">Zorg ervoor dat de klantsleutel in de doel-tenant is geconfigureerd als deze nog steeds vereist is.</span><span class="sxs-lookup"><span data-stu-id="37ae0-461">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="37ae0-462">Zie [hier](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-462">See [here](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) for more information.</span></span>  

<span data-ttu-id="37ae0-463">**Wat is de geschatte migratietijd?**</span><span class="sxs-lookup"><span data-stu-id="37ae0-463">**What is the estimated migration time?**</span></span>

<span data-ttu-id="37ae0-464">Om u te helpen bij [](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) het plannen van de migratie, bevat de onderstaande tabel de richtlijnen voor het voltooien van bulkpostvakken of afzonderlijke migraties.</span><span class="sxs-lookup"><span data-stu-id="37ae0-464">To help you plan your migration, the table present [here](https://docs.microsoft.com/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="37ae0-465">Deze schattingen zijn gebaseerd op een gegevensanalyse van eerdere klantmigraties.</span><span class="sxs-lookup"><span data-stu-id="37ae0-465">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="37ae0-466">Omdat elke omgeving uniek is, kan de exacte migratiesnelheid variëren.</span><span class="sxs-lookup"><span data-stu-id="37ae0-466">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="37ae0-467">Houd er wel aan dat deze functie momenteel wordt weergegeven als preview en in de SLA en dat de toepasselijke serviceniveaus niet van toepassing zijn op prestatie- of beschikbaarheidsproblemen tijdens de preview-status van deze functie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-467">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="37ae0-468">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="37ae0-468">Known issues</span></span>  

-  <span data-ttu-id="37ae0-469">**Probleem: Automatisch uitvbreed archieven kunnen niet worden gemigreerd.**</span><span class="sxs-lookup"><span data-stu-id="37ae0-469">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="37ae0-470">De migratiefunctie voor verschillende tenants ondersteunt migraties van het primaire postvak en archiefpostvak voor een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="37ae0-470">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="37ae0-471">Als de gebruiker in de bron echter een automatisch uit breiden archief heeft, dat wil zeggen meer dan één archiefpostvak, kan de functie de extra archieven niet migreren en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="37ae0-471">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="37ae0-472">**Probleem: Cloud MailUsers met smtp-proxyAddress van niet-eigendom, blokkeren MRS verplaatst de achtergrond.**</span><span class="sxs-lookup"><span data-stu-id="37ae0-472">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="37ae0-473">Bij het maken van mailUser-objecten voor de doelten tenant moet u ervoor zorgen dat alle SMTP-proxyadressen deel uitmaken van de doelten tenantorganisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-473">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="37ae0-474">Als er een SMTP-proxyAddress bestaat voor de doel-e-mailgebruiker die geen deel uitmaken van de lokale tenant, wordt de conversie van MailUser naar Mailbox voorkomen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-474">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="37ae0-475">Dit komt doordat we er zeker van zijn dat postvakobjecten alleen e-mail kunnen verzenden van domeinen waarvoor de tenant gezaghebbend is (domeinen die door de tenant worden geclaimd):</span><span class="sxs-lookup"><span data-stu-id="37ae0-475">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="37ae0-476">Wanneer u gebruikers synchroniseert vanuit een on-premises omgeving met behulp van Azure AD Connect, inrichting van on-premises MailUser-objecten waarbij ExternalEmailAddress verwijst naar de bronten tenant waarin het postvak bestaat (laran@contoso.onmicrosoft.com) en u het PrimarySMTPAddress stempelt als een domein dat zich in de doelten tenant (Lara.Newton@northwind.com) bevindt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-476">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="37ae0-477">Deze waarden worden gesynchroniseerd naar de tenant en een geschikte e-mailgebruiker wordt ingericht en klaar voor migratie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-477">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="37ae0-478">Hier wordt een voorbeeldobject weergegeven.</span><span class="sxs-lookup"><span data-stu-id="37ae0-478">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="37ae0-479">Het *contoso.onmicrosoft.com* adres is *niet aanwezig* in de matrix EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="37ae0-479">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="37ae0-480">**Probleem: MailUser-objecten met 'externe' primaire SMTP-adressen worden gewijzigd/ opnieuw ingesteld op 'interne' geclaimde domeinen van het bedrijf**</span><span class="sxs-lookup"><span data-stu-id="37ae0-480">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="37ae0-481">MailUser-objecten zijn pointers naar niet-lokale postvakken.</span><span class="sxs-lookup"><span data-stu-id="37ae0-481">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="37ae0-482">In het geval van migraties van postvakken tussen tenants gebruiken we MailUser-objecten om het bronpostvak (vanuit het perspectief van de doelorganisatie) of het doelpostvak (vanuit het perspectief van de bronorganisatie) voor te stellen.</span><span class="sxs-lookup"><span data-stu-id="37ae0-482">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="37ae0-483">De MailUsers hebben een ExternalEmailAddress (targetAddress) die wijst naar het SMTP-adres van het werkelijke postvak (ProxyTest@fabrikam.onmicrosoft.com) en primarySMTP-adres dat het weergegeven SMTP-adres van de postvakgebruiker in de adreslijst vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-483">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="37ae0-484">Sommige organisaties kiezen ervoor om het primaire SMTP-adres weer te geven als een extern SMTP-adres, niet als een adres dat eigendom is van of is geverifieerd door de lokale tenant (zoals fabrikam.com in plaats van als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="37ae0-484">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="37ae0-485">Wanneer echter een object van een Exchange-serviceplan is toegepast op MailUser via licentiebewerkingen, wordt het primaire SMTP-adres gewijzigd, zodat het wordt gebruikt als een domein dat is geverifieerd door de lokale organisatie (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="37ae0-485">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="37ae0-486">Er zijn twee mogelijke redenen:</span><span class="sxs-lookup"><span data-stu-id="37ae0-486">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="37ae0-487">Wanneer een Exchange-serviceplan wordt toegepast op een MailUser, wordt tijdens het Azure AD-proces proxyvernieuwing gestart om ervoor te zorgen dat de lokale organisatie geen e-mail kan verzenden, spoofing of e-mail vanuit een andere tenant kan verzenden.</span><span class="sxs-lookup"><span data-stu-id="37ae0-487">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="37ae0-488">SMTP-adressen op een object van een ontvanger met deze serviceplannen worden verwijderd als het adres niet wordt geverifieerd door de lokale organisatie.</span><span class="sxs-lookup"><span data-stu-id="37ae0-488">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="37ae0-489">Zoals in het voorbeeld het geval is, wordt het Fabikam.com NIET geverifieerd door de contoso.onmicrosoft.com-tenant, dus wordt dat domein door de fabrikam.com verwijderd.</span><span class="sxs-lookup"><span data-stu-id="37ae0-489">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="37ae0-490">Als u dit externe domein wilt blijven gebruiken in MailUser, vóór de migratie of na de migratie, moet u uw migratieprocessen wijzigen in het gebruik van licenties nadat de overstap is voltooid of vóór de overstap om ervoor te zorgen dat de verwachte externe huisstijl is toegepast op de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="37ae0-490">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="37ae0-491">U moet ervoor zorgen dat het postvakobject een juiste licentie heeft, zodat dit geen gevolgen heeft voor de e-mailservice.</span><span class="sxs-lookup"><span data-stu-id="37ae0-491">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="37ae0-492">Hier wordt een voorbeeldscript weergegeven voor het verwijderen van de serviceplannen voor een MailUser in Contoso.onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="37ae0-492">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="37ae0-493">Resultaten in de set serviceplannen die is toegewezen, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="37ae0-493">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="37ae0-494">Het PrimarySMTPAddress van de gebruiker wordt niet meer gekapt.</span><span class="sxs-lookup"><span data-stu-id="37ae0-494">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="37ae0-495">Het fabrikam.com domein is niet eigendom van de contoso.onmicrosoft.com-tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="37ae0-495">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="37ae0-496">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="37ae0-496">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="37ae0-497">Als msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), worden voor on-premises MailUsers die naar de doeltenant worden gemigreerd, door proxyverzendenlogica in Azure niet-eigen domeinen verwijderd en wordt het primarySMTP opnieuw ingesteld op een domein dat eigendom is.</span><span class="sxs-lookup"><span data-stu-id="37ae0-497">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="37ae0-498">Door het wissen van msExchRemoteRecipientType in de on-premises MailUser, is de proxy scrub-logica niet meer van toepassing.</span><span class="sxs-lookup"><span data-stu-id="37ae0-498">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="37ae0-499">Hieronder vindt u de volledige set mogelijke serviceplannen met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="37ae0-499">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="37ae0-500">Naam</span><span class="sxs-lookup"><span data-stu-id="37ae0-500">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="37ae0-501">Advanced eDiscovery-opslag (500 GB)</span><span class="sxs-lookup"><span data-stu-id="37ae0-501">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="37ae0-502">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="37ae0-502">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="37ae0-503">Preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="37ae0-503">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="37ae0-504">Exchange Enterprise CAL Services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="37ae0-504">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="37ae0-505">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="37ae0-505">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="37ae0-506">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="37ae0-506">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="37ae0-507">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="37ae0-507">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="37ae0-508">Exchange Online (Abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="37ae0-508">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="37ae0-509">Exchange Online (Abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="37ae0-509">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="37ae0-510">Exchange Online Archiving voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="37ae0-510">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="37ae0-511">Exchange Online Archiving voor Exchange Server</span><span class="sxs-lookup"><span data-stu-id="37ae0-511">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="37ae0-512">Inactieve gebruikersinvoegvoeging in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="37ae0-512">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="37ae0-513">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="37ae0-513">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="37ae0-514">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="37ae0-514">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="37ae0-515">Exchange Online Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="37ae0-515">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="37ae0-516">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="37ae0-516">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="37ae0-517">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="37ae0-517">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="37ae0-518">Informatiebarrières</span><span class="sxs-lookup"><span data-stu-id="37ae0-518">Information Barriers</span></span>                              |
   | <span data-ttu-id="37ae0-519">Information Protection voor Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="37ae0-519">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="37ae0-520">Information Protection voor Office 365 - Standard</span><span class="sxs-lookup"><span data-stu-id="37ae0-520">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="37ae0-521">Inzichten van MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="37ae0-521">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="37ae0-522">Geavanceerde controle van Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="37ae0-522">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="37ae0-523">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="37ae0-523">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="37ae0-524">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="37ae0-524">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="37ae0-525">Microsoft MyAnalytics (volledig)</span><span class="sxs-lookup"><span data-stu-id="37ae0-525">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="37ae0-526">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="37ae0-526">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="37ae0-527">Microsoft Defender voor Office 365 (abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="37ae0-527">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="37ae0-528">Microsoft Defender voor Office 365 (abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="37ae0-528">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="37ae0-529">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="37ae0-529">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="37ae0-530">Premium-versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="37ae0-530">Premium Encryption in Office 365</span></span>                  |
    
