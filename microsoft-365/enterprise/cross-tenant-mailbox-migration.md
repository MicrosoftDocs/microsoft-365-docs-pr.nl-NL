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
ms.openlocfilehash: f9a4b7679a33d6722336ee5412e4992389ba915f
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694411"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="df4ab-103">Migratie van postvakken tussen tenants (voorbeeld)</span><span class="sxs-lookup"><span data-stu-id="df4ab-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="df4ab-104">Als eerder een Exchange Online-tenant postvakken moest verplaatsen naar een andere tenant in dezelfde Exchange Online-service, moesten ze ze volledig buiten gebruik maken van on-premises en vervolgens aan boord brengen naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="df4ab-105">Met de nieuwe functie voor migratie van postvakken tussen tenants kunnen tenantbeheerders in zowel bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="df4ab-106">Hierdoor hoeft u geen postvakken aan boord of aan boord meer te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="df4ab-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="df4ab-107">Meestal hebt u tijdens fusies of afstotingen de mogelijkheid nodig om gebruikers en inhoud over te zetten naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="df4ab-108">Wanneer de doeltenderbeheerder de move uitvoert, wordt dit een pull move genoemd, vergelijkbaar met on-premises migraties voor cloud-onboarding.</span><span class="sxs-lookup"><span data-stu-id="df4ab-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="df4ab-109">Cross-tenant Exchange postvakbewegingen worden volledig selfservice door tenantbeheerders gebruikt, met behulp van bekende interfaces die kunnen worden gescript in de grotere werkstromen die nodig zijn om gebruikers over te zetten naar hun nieuwe organisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="df4ab-110">Beheerders kunnen de cmdlet, die beschikbaar is via de beheerrol Postvakken verplaatsen, gebruiken om bewegingen `New-MigrationBatch` tussen tenants uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="df4ab-111">Het verhuisproces omvat tenantautorisatiecontroles tijdens postvaksynchronisatie en -finalisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="df4ab-112">Gebruikers die migreren, moeten aanwezig zijn in het doeltendersysteem Exchange Online MailUsers, gemarkeerd met specifieke kenmerken om de migraties tussen tenants in te stellen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="df4ab-113">Het systeem wordt niet verplaatst voor gebruikers die niet correct zijn ingesteld in de doel tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="df4ab-114">Wanneer de bewegingen zijn voltooid, wordt het bronsysteempostvak geconverteerd naar MailUser en wordt targetAddress (weergegeven als ExternalEmailAddress in Exchange) gestempeld met het routeringsadres naar de doeltenator.</span><span class="sxs-lookup"><span data-stu-id="df4ab-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="df4ab-115">Dit proces laat de oudere MailUser achter in de brontenator en zorgt voor een periode van co-existence en e-mailroutering.</span><span class="sxs-lookup"><span data-stu-id="df4ab-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="df4ab-116">Wanneer bedrijfsprocessen het toestaan, kan de brontenator MailUser verwijderen of converteren naar een e-mailcontactcontact.</span><span class="sxs-lookup"><span data-stu-id="df4ab-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="df4ab-117">Cross-tenant Exchange postvakmigraties worden alleen ondersteund voor tenants in hybride of cloud, of een combinatie van de twee.</span><span class="sxs-lookup"><span data-stu-id="df4ab-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="df4ab-118">In dit artikel wordt het proces beschreven voor het verplaatsen van postvakken met verschillende tenants en worden richtlijnen gegeven voor het voorbereiden van bron- en doelten tenants voor de inhoudsverzet.</span><span class="sxs-lookup"><span data-stu-id="df4ab-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="df4ab-119">Bron- en doelten tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="df4ab-119">Preparing source and target tenants</span></span>

<span data-ttu-id="df4ab-120">Voor de functie voor Exchange migratie van postvakken is autorisatie en scoping vereist voor migraties tussen tenants.</span><span class="sxs-lookup"><span data-stu-id="df4ab-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="df4ab-121">Met de Azure Enterprise-toepassing en key vault-opslagoplossingen kunnen tenantbeheerders nu zowel autorisatie als scoping van Exchange Online-postvakmigraties van de ene tenant naar de andere beheren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="df4ab-122">Het verplaatsen van postvakken met meerdere tenant Azure Active Directory s ondersteunt een uitnodigings- en toestemmingsmodel om een azure AD-toepassing (Azure AD) te maken die wordt gebruikt voor verificatie tussen een tenantpaar.</span><span class="sxs-lookup"><span data-stu-id="df4ab-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="df4ab-123">Aanvullende onderdelen, zoals een organisatierelatie en een migratie-eindpunt, zijn ook vereist.</span><span class="sxs-lookup"><span data-stu-id="df4ab-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="df4ab-124">Deze sectie bevat niet de specifieke stappen die nodig zijn om de gebruikersobjecten van MailUser voor te bereiden in de doelmap, en bevat ook niet de voorbeeldopdracht om een migratiebatch in te dienen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="df4ab-125">Zie [Doelgebruikersobjecten voorbereiden voor migratie](#prepare-target-user-objects-for-migration) voor deze informatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df4ab-126">Vereisten</span><span class="sxs-lookup"><span data-stu-id="df4ab-126">Prerequisites</span></span>

<span data-ttu-id="df4ab-127">Voor de functie voor het verplaatsen van postvakken met verschillende tenants is [Azure Key Vault](/azure/key-vault/basic-concepts) vereist om een tenantpaarspecifieke Azure-toepassing te maken voor het veilig opslaan en openen van het certificaat/geheim dat wordt gebruikt voor het verifiëren en autoriseren van postvakmigratie van de ene tenant naar de andere, waardoor alle vereisten voor het delen van certificaten/geheimen tussen tenants worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="df4ab-128">Voordat u begint, moet u de benodigde machtigingen hebben om de implementatiescripts uit te voeren om Azure Key Vault, De toepassing Postvak verplaatsen, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="df4ab-129">Globale beheerder heeft meestal toestemming om alle configuratiestappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="df4ab-130">Daarnaast zijn beveiligingsgroepen met e-mail in de bron tenant vereist voordat de installatie wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="df4ab-131">Deze groepen worden gebruikt voor het bereik van de lijst met postvakken die kunnen worden verplaatst van de brontender (of soms resourceten tenant genoemd) naar de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="df4ab-132">Hierdoor kan de beheerder van de brontender de specifieke set postvakken beperken of beperken die moeten worden verplaatst, zodat onbedoelde gebruikers niet kunnen worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="df4ab-133">Geneste groepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="df4ab-133">Nested groups are not supported.</span></span>

<span data-ttu-id="df4ab-134">U moet ook communiceren met uw vertrouwde partnerbedrijf (met wie u postvakken verplaatst) om hun tenant-id Microsoft 365 verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="df4ab-135">Deze tenant-id wordt gebruikt in het veld `DomainName` Organisatierelatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="df4ab-136">Als u de tenant-id van een abonnement wilt verkrijgen, meld u zich aan bij het Microsoft 365 beheercentrum en gaat u naar [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="df4ab-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="df4ab-137">Klik op het kopieerpictogram voor de eigenschap Tenant-id om het naar het klembord te kopiëren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="df4ab-138">Dit is hoe het proces werkt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Tenantvoorbereiding voor postvakmigratie.":::

<span data-ttu-id="df4ab-140">[Zie een grotere versie van deze afbeelding.](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)</span><span class="sxs-lookup"><span data-stu-id="df4ab-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="df4ab-141">Tenants voorbereiden</span><span class="sxs-lookup"><span data-stu-id="df4ab-141">Prepare tenants</span></span>

<span data-ttu-id="df4ab-142">Op hoog niveau vinden de volgende configuratieacties plaats bij het uitvoeren van de installatiescripts.</span><span class="sxs-lookup"><span data-stu-id="df4ab-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="df4ab-143">De doel tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="df4ab-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="df4ab-144">Als er geen bestaande Azure Resource Group wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="df4ab-145">Als er geen bestaande Sleutelkluis wordt geleverd, wordt er een nieuwe gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="df4ab-146">Er wordt een nieuw Access-beleid gemaakt voor de Office 365 Exchange Online postvakmigratietoepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="df4ab-147">Er wordt een nieuw certificaat gemaakt (of een bestaand certificaat, indien opgegeven) om het geheim van de migratietoepassing (SCRIPT) te bewaren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="df4ab-148">Er wordt een nieuwe Azure AD-toepassing gemaakt (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="df4ab-149">Het certificaat/geheim wordt geüpload naar de migratietoepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="df4ab-150">Machtigingen voor postvakmigratie worden toegewezen aan de toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="df4ab-151">Het implementatiescript wordt onderbroken totdat de doelbeheerder toestemming geeft voor de eigen toepassing (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="df4ab-152">De doeltenderbeheerder stemt in met de machtigingen die aan de toepassing zijn verleend (HANDMATIG).</span><span class="sxs-lookup"><span data-stu-id="df4ab-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="df4ab-153">Er wordt een organisatierelatie gemaakt met de doel tenant (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="df4ab-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="df4ab-154">Er wordt een migratie-eindpunt gemaakt om postvakken naar de doeltender (SCRIPT) te trekken.</span><span class="sxs-lookup"><span data-stu-id="df4ab-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="df4ab-155">De bron tenant voorbereiden:</span><span class="sxs-lookup"><span data-stu-id="df4ab-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="df4ab-156">De bronten tenantbeheerder accepteert toestemming voor de uitnodiging voor de toepassing Postvakmigratie van de doelten tenant (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="df4ab-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="df4ab-157">De bronten tenantbeheerder maakt een beveiligingsgroep met e-mail in de tenant om de lijst met postvakken te bevatten die mogen worden verplaatst door de migratietoepassing (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="df4ab-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="df4ab-158">Er wordt een organisatierelatie gemaakt met de doel tenant die de postvakmigratietoepassing opgeeft, moet worden gebruikt voor OAuth-verificatie om de aanvraag voor verplaatsen (SCRIPT) te accepteren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="df4ab-159">Stapsgewijs instructies voor de doel tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="df4ab-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="df4ab-160">Download het SetupCrossTenantRelationshipForTargetTenant.ps1 script voor het instellen van de doel tenant vanuit [de GitHub repository.](https://github.com/microsoft/cross-tenant/releases/tag/Preview)</span><span class="sxs-lookup"><span data-stu-id="df4ab-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="df4ab-161">Sla het script (SetupCrossTenantRelationshipForTargetTenant.ps1) op de computer waaruit u het script gaat uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="df4ab-162">Maak een externe PowerShell-verbinding met de Exchange Online doel tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="df4ab-163">Zorg er nogmaals voor dat u de benodigde machtigingen hebt om de implementatiescripts uit te voeren om de opslag en het certificaat van de Azure Key Vault, De toepassing Postvak verplaatsen, EXO-migratie-eindpunt en de EXO-organisatierelatie te configureren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="df4ab-164">Wijzig de adreslijst van de bestandsmap in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw Externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="df4ab-165">Voer het script uit met de volgende parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="df4ab-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="df4ab-166">Parameter</span><span class="sxs-lookup"><span data-stu-id="df4ab-166">Parameter</span></span> | <span data-ttu-id="df4ab-167">Waarde</span><span class="sxs-lookup"><span data-stu-id="df4ab-167">Value</span></span> | <span data-ttu-id="df4ab-168">Vereist of Optioneel</span><span class="sxs-lookup"><span data-stu-id="df4ab-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="df4ab-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="df4ab-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="df4ab-170">Doel tenantdomein, zoals fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="df4ab-171">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-171">Required</span></span> |
    | <span data-ttu-id="df4ab-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="df4ab-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="df4ab-173">Bronten tenantdomein, zoals contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="df4ab-174">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-174">Required</span></span> |
    | <span data-ttu-id="df4ab-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="df4ab-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="df4ab-176">Het e-mailadres van de bron tenantbeheerder.</span><span class="sxs-lookup"><span data-stu-id="df4ab-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="df4ab-177">Dit is de bron tenantbeheerder die instemt met het gebruik van de postvakmigratietoepassing die is verzonden van de doelbeheerder. Dit is de beheerder die de e-mail uitnodigen voor de toepassing ontvangt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="df4ab-178">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-178">Required</span></span> |
    | <span data-ttu-id="df4ab-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="df4ab-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="df4ab-180">Brontenderorganisatie-id (GUID).</span><span class="sxs-lookup"><span data-stu-id="df4ab-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="df4ab-181">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-181">Required</span></span> |
    | <span data-ttu-id="df4ab-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="df4ab-182">-SubscriptionId</span></span>                             | <span data-ttu-id="df4ab-183">Het Azure-abonnement dat u kunt gebruiken voor het maken van resources.</span><span class="sxs-lookup"><span data-stu-id="df4ab-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="df4ab-184">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-184">Required</span></span> |
    | <span data-ttu-id="df4ab-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="df4ab-185">-ResourceGroup</span></span>                              | <span data-ttu-id="df4ab-186">Azure resource group name that contains or will contain the Key Vault.</span><span class="sxs-lookup"><span data-stu-id="df4ab-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="df4ab-187">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-187">Required</span></span> |
    | <span data-ttu-id="df4ab-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="df4ab-188">-KeyVaultName</span></span>                               | <span data-ttu-id="df4ab-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span><span class="sxs-lookup"><span data-stu-id="df4ab-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="df4ab-190">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-190">Required</span></span> |
    | <span data-ttu-id="df4ab-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="df4ab-191">-CertificateName</span></span>                            | <span data-ttu-id="df4ab-192">Certificaatnaam bij het genereren of zoeken naar certificaat in de sleutelkluis.</span><span class="sxs-lookup"><span data-stu-id="df4ab-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="df4ab-193">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-193">Required</span></span> |
    | <span data-ttu-id="df4ab-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="df4ab-194">-CertificateSubject</span></span>                         | <span data-ttu-id="df4ab-195">Onderwerpnaam van Azure Key Vault-certificaat, zoals CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="df4ab-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="df4ab-196">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-196">Required</span></span> |
    | <span data-ttu-id="df4ab-197">-AzureResourceLocation</span><span class="sxs-lookup"><span data-stu-id="df4ab-197">-AzureResourceLocation</span></span>                      | <span data-ttu-id="df4ab-198">De locatie van de Azure-resourcegroep en de sleutelkluis.</span><span class="sxs-lookup"><span data-stu-id="df4ab-198">The location of the Azure resource group and key vault.</span></span> | <span data-ttu-id="df4ab-199">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-199">Required</span></span> |
    | <span data-ttu-id="df4ab-200">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="df4ab-200">-ExistingApplicationId</span></span>                      | <span data-ttu-id="df4ab-201">E-mailmigratietoepassing die u wilt gebruiken als er al een is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-201">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="df4ab-202">Optioneel</span><span class="sxs-lookup"><span data-stu-id="df4ab-202">Optional</span></span> |
    | <span data-ttu-id="df4ab-203">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="df4ab-203">-AzureAppPermissions</span></span>                        | <span data-ttu-id="df4ab-204">De machtigingen die moeten worden gegeven aan de postvakmigratietoepassing, zoals Exchange of MSGraph (Exchange voor het verplaatsen van postvakken, MSGraph voor het gebruik van deze toepassing om een uitnodiging voor een toestemmingskoppeling naar resourceten tenant te verzenden).</span><span class="sxs-lookup"><span data-stu-id="df4ab-204">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="df4ab-205">Vereist</span><span class="sxs-lookup"><span data-stu-id="df4ab-205">Required</span></span> |
    | <span data-ttu-id="df4ab-206">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="df4ab-206">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="df4ab-207">Parameter voor het gebruik van de toepassing die is gemaakt voor migratie om te worden gebruikt voor het verzenden van uitnodiging voor toestemmingskoppelingen naar de bron tenantbeheerder. Als u deze niet presenteert, wordt gevraagd of de doelbeheerder de referenties heeft om verbinding te maken met Azure Invitation Manager en de uitnodiging te verzenden als doelbeheerder.</span><span class="sxs-lookup"><span data-stu-id="df4ab-207">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="df4ab-208">Optioneel</span><span class="sxs-lookup"><span data-stu-id="df4ab-208">Optional</span></span> |
    | <span data-ttu-id="df4ab-209">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="df4ab-209">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="df4ab-210">Het opslagaccount waarin de auditlogboeken van Key Vault werden opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-210">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="df4ab-211">Optioneel</span><span class="sxs-lookup"><span data-stu-id="df4ab-211">Optional</span></span> |
    | <span data-ttu-id="df4ab-212">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="df4ab-212">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="df4ab-213">De resourcegroep met het opslagaccount voor het opslaan van auditlogboeken van Key Vault.</span><span class="sxs-lookup"><span data-stu-id="df4ab-213">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="df4ab-214">Optioneel</span><span class="sxs-lookup"><span data-stu-id="df4ab-214">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="df4ab-215">Zorg ervoor dat u de Azure AD PowerShell-module hebt geïnstalleerd voordat de scripts worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-215">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="df4ab-216">Raadpleeg hier voor ![ ](/powershell/azure/install-az-ps?view=azps-5.1.0) installatiestappen</span><span class="sxs-lookup"><span data-stu-id="df4ab-216">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="df4ab-217">Het script wordt onderbroken en u wordt gevraagd of u akkoord wilt gaan met de Exchange postvakmigratietoepassing die tijdens dit proces is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-217">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="df4ab-218">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-218">Here is an example.</span></span>

    ```powershell
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
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="df4ab-219">Er wordt een URL weergegeven in de Externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-219">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="df4ab-220">Kopieer de koppeling die is verstrekt voor uw tenant-toestemming en plak deze in een webbrowser.</span><span class="sxs-lookup"><span data-stu-id="df4ab-220">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="df4ab-221">Meld u aan met uw globale beheerdersreferenties.</span><span class="sxs-lookup"><span data-stu-id="df4ab-221">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="df4ab-222">Wanneer het volgende scherm wordt weergegeven, selecteert u **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="df4ab-222">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Dialoogvenster Machtigingen accepteren":::

9. <span data-ttu-id="df4ab-224">Ga terug naar de Externe PowerShell-sessie en druk op Enter om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="df4ab-224">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="df4ab-225">Het script configureert de overige installatieobjecten.</span><span class="sxs-lookup"><span data-stu-id="df4ab-225">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="df4ab-226">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-226">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="df4ab-227">De instelling van de doelbeheerder is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="df4ab-227">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="df4ab-228">Stapsgewijs instructies voor de bron tenantbeheerder</span><span class="sxs-lookup"><span data-stu-id="df4ab-228">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="df4ab-229">Meld u aan bij uw postvak als de -ResourceTenantAdminEmail die is opgegeven door de doelbeheerder tijdens de installatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-229">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="df4ab-230">Zoek de e-mailuitnodiging van de doel tenant en selecteer vervolgens **de Aan de slag** knop.</span><span class="sxs-lookup"><span data-stu-id="df4ab-230">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="U bent uitgenodigd dialoogvenster":::

2. <span data-ttu-id="df4ab-232">Selecteer **Accepteren om** de uitnodiging te accepteren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-232">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Dialoogvenster om machtigingen te accepteren":::

   > [!NOTE]
   > <span data-ttu-id="df4ab-234">Als u deze e-mail niet ontvangt of niet kunt vinden, heeft de doel tenantbeheerder een directe URL gekregen die u kan krijgen om de uitnodiging te accepteren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-234">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="df4ab-235">De URL moet in het afschrift van de Externe PowerShell-sessie van de doel tenantbeheerder staan.</span><span class="sxs-lookup"><span data-stu-id="df4ab-235">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="df4ab-236">Maak in het Microsoft 365-beheercentrum of in een Externe PowerShell-sessie een of meer beveiligingsgroepen met e-mail om de lijst met postvakken te beheren die door de doeltender mogen worden verwijderd (verplaatst) van de bronten tenant naar de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-236">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="df4ab-237">U hoeft deze groep niet van tevoren in te vullen, maar er moet ten minste één groep beschikbaar zijn om de installatiestappen (script) uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-237">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="df4ab-238">Nestgroepen worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="df4ab-238">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="df4ab-239">Download het SetupCrossTenantRelationshipForResourceTenant.ps1 script voor de installatie van de bron tenant in GitHub archief: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="df4ab-239">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="df4ab-240">Maak een externe PowerShell-verbinding met de bronten tenant met uw Exchange beheerdersmachtigingen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-240">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="df4ab-241">Globale beheerdersmachtigingen zijn niet vereist om de bronten tenant te configureren, alleen de doelten tenant vanwege het proces voor het maken van Azure-toepassingen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-241">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="df4ab-242">Wijzig de adreslijst in de scriptlocatie of controleer of het script momenteel is opgeslagen op de locatie in uw Externe PowerShell-sessie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-242">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="df4ab-243">Voer het script uit met de volgende vereiste parameters en waarden.</span><span class="sxs-lookup"><span data-stu-id="df4ab-243">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="df4ab-244">Parameter</span><span class="sxs-lookup"><span data-stu-id="df4ab-244">Parameter</span></span> | <span data-ttu-id="df4ab-245">Waarde</span><span class="sxs-lookup"><span data-stu-id="df4ab-245">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="df4ab-246">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="df4ab-246">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="df4ab-247">Beveiligingsgroep met e-mail die is gemaakt door bronten tenant voor de identiteiten/postvakken die binnen het migratiebereik vallen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-247">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="df4ab-248">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="df4ab-248">-ResourceTenantDomain</span></span> | <span data-ttu-id="df4ab-249">Bronten tenantdomeinnaam, zoals contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-249">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="df4ab-250">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="df4ab-250">-ApplicationId</span></span> | <span data-ttu-id="df4ab-251">Azure Application ID (GUID) van de toepassing die voor migratie wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-251">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="df4ab-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span><span class="sxs-lookup"><span data-stu-id="df4ab-252">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="df4ab-253">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="df4ab-253">-TargetTenantDomain</span></span> | <span data-ttu-id="df4ab-254">Doel tenantdomeinnaam, zoals fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-254">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="df4ab-255">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="df4ab-255">-TargetTenantId</span></span> | <span data-ttu-id="df4ab-256">Tenant-id van de doel tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-256">Tenant ID of the target tenant.</span></span> <span data-ttu-id="df4ab-257">Bijvoorbeeld de Azure AD-tenant-id van contoso \. onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-257">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="df4ab-258">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-258">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="df4ab-259">De installatie van de bronbeheerder is nu voltooid.</span><span class="sxs-lookup"><span data-stu-id="df4ab-259">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="df4ab-260">Installatie verifiëren</span><span class="sxs-lookup"><span data-stu-id="df4ab-260">Verify setup</span></span>

<span data-ttu-id="df4ab-261">Controleer of de organisatierelaties in zowel bron- als doelten tenants en het migratie-eindpunt in het doel zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-261">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="df4ab-262">Doel tenant</span><span class="sxs-lookup"><span data-stu-id="df4ab-262">Target tenant</span></span>

<span data-ttu-id="df4ab-263">**Organisatierelatie**</span><span class="sxs-lookup"><span data-stu-id="df4ab-263">**Organization relationship**</span></span>

<span data-ttu-id="df4ab-264">Controleer of het object organisatierelatie is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="df4ab-264">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="df4ab-265">Hier is een voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="df4ab-265">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="df4ab-266">**Migratie-eindpunt**</span><span class="sxs-lookup"><span data-stu-id="df4ab-266">**Migration endpoint**</span></span>

<span data-ttu-id="df4ab-267">Controleer of het migratie-eindpuntobject met deze opdracht is gemaakt en geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-267">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="df4ab-268">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-268">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="df4ab-269">Bron tenant</span><span class="sxs-lookup"><span data-stu-id="df4ab-269">Source tenant</span></span>

<span data-ttu-id="df4ab-270">**Organisatierelatie**</span><span class="sxs-lookup"><span data-stu-id="df4ab-270">**Organization relationship**</span></span>

<span data-ttu-id="df4ab-271">Controleer of het object organisatierelatie is gemaakt en geconfigureerd met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="df4ab-271">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="df4ab-272">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-272">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="df4ab-273">Installatiescript controleren</span><span class="sxs-lookup"><span data-stu-id="df4ab-273">Verify Setup Script</span></span>

<span data-ttu-id="df4ab-274">Als u fouten ontvangt tijdens de configuratie van de bron- of doelten tenants, kunt u het script VerifySetup.ps1 op GitHub uitvoeren [en](https://github.com/microsoft/cross-tenant/releases/tag/Preview) de uitvoer controleren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-274">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="df4ab-275">Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:</span><span class="sxs-lookup"><span data-stu-id="df4ab-275">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="df4ab-276">Hier volgen een voorbeeld van VerifySetup.ps1 bron tenant:</span><span class="sxs-lookup"><span data-stu-id="df4ab-276">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="df4ab-277">Postvakken terug naar de oorspronkelijke bron verplaatsen</span><span class="sxs-lookup"><span data-stu-id="df4ab-277">Move mailboxes back to the original source</span></span>

<span data-ttu-id="df4ab-278">Als een postvak terug moet gaan naar de oorspronkelijke brontender, moeten dezelfde stappen en scripts worden uitgevoerd in zowel nieuwe bron- als nieuwe doelten tenants.</span><span class="sxs-lookup"><span data-stu-id="df4ab-278">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="df4ab-279">Het bestaande object Organisatierelatie wordt bijgewerkt of toegevoegd, niet opnieuw gemaakt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-279">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="df4ab-280">Doelgebruikersobjecten voorbereiden op migratie</span><span class="sxs-lookup"><span data-stu-id="df4ab-280">Prepare target user objects for migration</span></span>

<span data-ttu-id="df4ab-281">Gebruikers die migreren, moeten aanwezig zijn in de doeltender en het Exchange Online (zoals MailUsers) die zijn gemarkeerd met specifieke kenmerken om de cross-tenantverzet in te stellen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-281">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="df4ab-282">Het systeem wordt niet verplaatst voor gebruikers die niet correct zijn ingesteld in de doel tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-282">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="df4ab-283">In de volgende sectie worden de objectvereisten voor MailUser voor de doeltenator be detaillering.</span><span class="sxs-lookup"><span data-stu-id="df4ab-283">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="df4ab-284">Vereisten</span><span class="sxs-lookup"><span data-stu-id="df4ab-284">Prerequisites</span></span>
  
<span data-ttu-id="df4ab-285">U moet ervoor zorgen dat de volgende objecten en kenmerken zijn ingesteld in de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-285">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="df4ab-286">Voor postvakken die vanuit een bronorganisatie worden verplaatst, moet u een MailUser-object inrichten in de doelorganisatie:</span><span class="sxs-lookup"><span data-stu-id="df4ab-286">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="df4ab-287">De doelmailgebruiker moet deze kenmerken uit het bronpostvak hebben of zijn toegewezen aan het nieuwe object Gebruiker:</span><span class="sxs-lookup"><span data-stu-id="df4ab-287">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="df4ab-288">ExchangeGUID (directe stroom van bron naar doel) – De postvak-GUID moet overeenkomen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-288">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="df4ab-289">Het verplaatsen gaat niet door als dit niet aanwezig is op het doelobject.</span><span class="sxs-lookup"><span data-stu-id="df4ab-289">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="df4ab-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span><span class="sxs-lookup"><span data-stu-id="df4ab-290">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="df4ab-291">Het verplaatsen gaat niet door als dit niet aanwezig is op het doelobject.</span><span class="sxs-lookup"><span data-stu-id="df4ab-291">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="df4ab-292">(Dit is alleen vereist als het bronpostvak Archiveren is ingeschakeld).</span><span class="sxs-lookup"><span data-stu-id="df4ab-292">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="df4ab-293">LegacyExchangeDN (flow as proxyAddress, "x500: <LegacyExchangeDN> ") – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="df4ab-293">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="df4ab-294">De verhuisprocessen gaan niet door als dit niet aanwezig is op het doelobject.</span><span class="sxs-lookup"><span data-stu-id="df4ab-294">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="df4ab-295">UserPrincipalName: UPN wordt uitgelijnd op de nieuwe identiteit of het doelbedrijf van de gebruiker (bijvoorbeeld user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-295">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="df4ab-296">Primair SMTPAddress- Primair SMTP-adres wordt uitgelijnd op het nieuwe bedrijf van de gebruiker (bijvoorbeeld user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-296">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="df4ab-297">TargetAddress/ExternalEmailAddress: MailUser verwijst naar het huidige postvak van de gebruiker dat wordt gehost in bronten tenant (bijvoorbeeld user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-297">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="df4ab-298">Wanneer u deze waarde toewijst, controleert u of u ook PrimarySMTPAddress hebt of toewijst, anders wordt met deze waarde het PrimarySMTPAddress ingesteld, waardoor fouten worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="df4ab-298">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="df4ab-299">U kunt geen oudere smtp-proxyadressen uit het bronpostvak toevoegen aan doelmailuser.</span><span class="sxs-lookup"><span data-stu-id="df4ab-299">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="df4ab-300">U kunt bijvoorbeeld geen contoso.com in de fabrikam.onmicrosoft.com tenantobjecten).</span><span class="sxs-lookup"><span data-stu-id="df4ab-300">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="df4ab-301">Domeinen zijn alleen gekoppeld aan één Azure AD- of Exchange Online tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-301">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="df4ab-302">Voorbeeld **van het** object MailUser:</span><span class="sxs-lookup"><span data-stu-id="df4ab-302">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="df4ab-303">Attribuut</span><span class="sxs-lookup"><span data-stu-id="df4ab-303">Attribute</span></span>             | <span data-ttu-id="df4ab-304">Waarde</span><span class="sxs-lookup"><span data-stu-id="df4ab-304">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="df4ab-305">Alias</span><span class="sxs-lookup"><span data-stu-id="df4ab-305">Alias</span></span>                 | <span data-ttu-id="df4ab-306">Laran</span><span class="sxs-lookup"><span data-stu-id="df4ab-306">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="df4ab-307">RecipientType</span><span class="sxs-lookup"><span data-stu-id="df4ab-307">RecipientType</span></span>         | <span data-ttu-id="df4ab-308">MailUser</span><span class="sxs-lookup"><span data-stu-id="df4ab-308">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="df4ab-309">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="df4ab-309">RecipientTypeDetails</span></span>  | <span data-ttu-id="df4ab-310">MailUser</span><span class="sxs-lookup"><span data-stu-id="df4ab-310">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="df4ab-311">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="df4ab-311">UserPrincipalName</span></span>     | <span data-ttu-id="df4ab-312">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-312">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="df4ab-313">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="df4ab-313">PrimarySmtpAddress</span></span>    | <span data-ttu-id="df4ab-314">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-314">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="df4ab-315">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="df4ab-315">ExternalEmailAddress</span></span>  | <span data-ttu-id="df4ab-316">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-316">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="df4ab-317">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="df4ab-317">ExchangeGuid</span></span>          | <span data-ttu-id="df4ab-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="df4ab-318">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="df4ab-319">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="df4ab-319">LegacyExchangeDN</span></span>      | <span data-ttu-id="df4ab-320">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="df4ab-320">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="df4ab-321">(FYDIBOHF23SPDLT)/cn=Ontvangers/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="df4ab-321">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="df4ab-322">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="df4ab-322">EmailAddresses</span></span>        | <span data-ttu-id="df4ab-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="df4ab-323">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="df4ab-324">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="df4ab-324">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="df4ab-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-325">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="df4ab-326">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-326">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="df4ab-327">**Voorbeeldbron** Postvakobject:</span><span class="sxs-lookup"><span data-stu-id="df4ab-327">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="df4ab-328">Attribuut</span><span class="sxs-lookup"><span data-stu-id="df4ab-328">Attribute</span></span>             | <span data-ttu-id="df4ab-329">Waarde</span><span class="sxs-lookup"><span data-stu-id="df4ab-329">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="df4ab-330">Alias</span><span class="sxs-lookup"><span data-stu-id="df4ab-330">Alias</span></span>                 | <span data-ttu-id="df4ab-331">Laran</span><span class="sxs-lookup"><span data-stu-id="df4ab-331">LaraN</span></span>                                                                    |
     | <span data-ttu-id="df4ab-332">RecipientType</span><span class="sxs-lookup"><span data-stu-id="df4ab-332">RecipientType</span></span>         | <span data-ttu-id="df4ab-333">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="df4ab-333">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="df4ab-334">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="df4ab-334">RecipientTypeDetails</span></span>  | <span data-ttu-id="df4ab-335">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="df4ab-335">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="df4ab-336">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="df4ab-336">UserPrincipalName</span></span>     | <span data-ttu-id="df4ab-337">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-337">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="df4ab-338">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="df4ab-338">PrimarySmtpAddress</span></span>    | <span data-ttu-id="df4ab-339">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-339">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="df4ab-340">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="df4ab-340">ExchangeGuid</span></span>          | <span data-ttu-id="df4ab-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="df4ab-341">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="df4ab-342">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="df4ab-342">LegacyExchangeDN</span></span>      | <span data-ttu-id="df4ab-343">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="df4ab-343">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="df4ab-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="df4ab-344">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="df4ab-345">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="df4ab-345">EmailAddresses</span></span>        | <span data-ttu-id="df4ab-346">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-346">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="df4ab-347">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="df4ab-347">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="df4ab-348">Er kunnen extra kenmerken worden opgenomen in Exchange hybride schrijf al.</span><span class="sxs-lookup"><span data-stu-id="df4ab-348">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="df4ab-349">Zo niet, dan moeten ze worden opgenomen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-349">If not, they should be included.</span></span> 
   - <span data-ttu-id="df4ab-350">msExchBlockedSendersHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df4ab-350">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="df4ab-351">msExchSafeRecipientsHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df4ab-351">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="df4ab-352">msExchSafeSendersHash: schrijft veilige en geblokkeerde afzendergegevens van clients terug naar on-premises Active Directory.</span><span class="sxs-lookup"><span data-stu-id="df4ab-352">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="df4ab-353">Als het bronpostvak Op LitigationHold staat en de grootte van het bronpostvak Herstelbare items groter is dan de standaardwaarde van onze database (30 GB), worden de bewegingen niet doorgeslagen omdat het doelquotum kleiner is dan de grootte van het bronpostvak.</span><span class="sxs-lookup"><span data-stu-id="df4ab-353">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="df4ab-354">U kunt het doelobject MailUser bijwerken om de vlag van het ELC-postvak over te zetten van de bronomgeving naar het doel, waardoor het doelsysteem wordt ingesteld om het quotum van de MailUser uit te breiden naar 100 GB, zodat de overgang naar het doel mogelijk wordt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-354">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="df4ab-355">Deze instructies werken alleen voor hybride identiteit met Azure AD-Verbinding maken, omdat de opdrachten om de ELC-vlaggen te stempelen niet worden blootgesteld aan tenantbeheerders.</span><span class="sxs-lookup"><span data-stu-id="df4ab-355">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="df4ab-356">VOORBEELD: ZOALS HET IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="df4ab-356">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="df4ab-357">In dit script wordt uit gegaan van een verbinding met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory (om het ADUser-object te stempelen).</span><span class="sxs-lookup"><span data-stu-id="df4ab-357">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="df4ab-358">Als bron een geschil of herstel van één item heeft ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="df4ab-358">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="df4ab-359">Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="df4ab-359">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="df4ab-360">Niet-hybride doelten tenants kunnen het quotum wijzigen in de map Herstelbare items voor de MailUsers vóór de migratie door de volgende opdracht uit te voeren om De procedure in te stellen voor het object MailUser en het quotum te verhogen tot 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="df4ab-360">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="df4ab-361">Houd er rekening mee dat dit niet werkt voor tenants in hybride versies.</span><span class="sxs-lookup"><span data-stu-id="df4ab-361">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="df4ab-362">Gebruikers in de doelorganisatie moeten een licentie hebben met Exchange Online abonnementen die van toepassing zijn op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-362">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="df4ab-363">U kunt een licentie toepassen op voorhand van een postvakverhuis, maar alleen wanneer de doelmailuser correct is ingesteld met ExchangeGUID- en proxyadressen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-363">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="df4ab-364">Het toepassen van een licentie voordat de ExchangeGUID wordt toegepast, resulteert in een nieuw postvak dat is ingericht in de doelorganisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-364">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="df4ab-365">Wanneer u een licentie op een postvak- of MailUser-object toe te passen, worden alle SMTP-type proxyAddresses geschuurd om ervoor te zorgen dat alleen geverifieerde domeinen worden opgenomen in de Exchange EmailAddresses-matrix.</span><span class="sxs-lookup"><span data-stu-id="df4ab-365">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="df4ab-366">U moet ervoor zorgen dat de doelmailuser geen eerdere ExchangeGuid heeft die niet overeenkomen met de Bron ExchangeGuid.</span><span class="sxs-lookup"><span data-stu-id="df4ab-366">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="df4ab-367">Dit kan gebeuren als de doel-meu eerder een licentie voor Exchange Online en een postvak heeft ingericht.</span><span class="sxs-lookup"><span data-stu-id="df4ab-367">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="df4ab-368">Als de doelmailuser eerder een licentie had voor of een ExchangeGuid had die niet overeen komt met de Source ExchangeGuid, moet u een opschoning van de cloud-meu uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-368">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="df4ab-369">Voor deze cloud-MEUs's kunt u `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-369">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="df4ab-370">Dit proces is onomkeerbaar.</span><span class="sxs-lookup"><span data-stu-id="df4ab-370">This process is irreversible.</span></span> <span data-ttu-id="df4ab-371">Als het object een zacht Verwijderd postvak heeft, kan het na dit punt niet meer worden hersteld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-371">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="df4ab-372">Wanneer dit is geweend, kunt u echter de juiste ExchangeGuid synchroniseren met het doelobject en wordt het bronpostvak door MRS verbonden met het nieuwe doelpostvak.</span><span class="sxs-lookup"><span data-stu-id="df4ab-372">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="df4ab-373">(Reference EHLO blog on the new parameter.)</span><span class="sxs-lookup"><span data-stu-id="df4ab-373">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="df4ab-374">Met deze opdracht kunt u objecten zoeken die voorheen postvakken waren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-374">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="df4ab-375">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-375">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="df4ab-376">Met deze opdracht kunt u het zacht verwijderde postvak wissen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-376">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="df4ab-377">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-377">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="df4ab-378">Postvakmigraties uitvoeren</span><span class="sxs-lookup"><span data-stu-id="df4ab-378">Perform mailbox migrations</span></span>

<span data-ttu-id="df4ab-379">Cross-tenant Exchange postvakmigraties worden verzonden als migratiebatchs die zijn gestart vanuit de doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-379">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="df4ab-380">Dit is vergelijkbaar met de manier waarop on-boarding migratiebatchs werken bij het migreren van Exchange on-premises naar Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="df4ab-380">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="df4ab-381">Migratiebatchs maken</span><span class="sxs-lookup"><span data-stu-id="df4ab-381">Create Migration batches</span></span>

<span data-ttu-id="df4ab-382">Hier is een voorbeeld van de migratiebatch cmdlet voor het starten van moves.</span><span class="sxs-lookup"><span data-stu-id="df4ab-382">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="df4ab-383">Het e-mailadres in het CSV-bestand moet het e-mailadres zijn dat is opgegeven in de doel tenant, niet de bron tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-383">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="df4ab-384">Migratiebatchinzending wordt ook ondersteund vanuit het nieuwe Exchange beheercentrum bij het selecteren van de optie voor meerdere tenants.</span><span class="sxs-lookup"><span data-stu-id="df4ab-384">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="df4ab-385">On-premises MailUsers bijwerken</span><span class="sxs-lookup"><span data-stu-id="df4ab-385">Update on-premises MailUsers</span></span>

<span data-ttu-id="df4ab-386">Zodra het postvak van bron naar doel wordt verplaatst, moet u ervoor zorgen dat de on-premises e-mailgebruikers, zowel Bron als doel, worden bijgewerkt met het nieuwe doelAdres.</span><span class="sxs-lookup"><span data-stu-id="df4ab-386">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="df4ab-387">In de voorbeelden is het doelDeliveryDomain dat in de move wordt **gebruikt, contoso.onmicrosoft.com.**</span><span class="sxs-lookup"><span data-stu-id="df4ab-387">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="df4ab-388">Werk de e-mailgebruikers bij met deze targetAddress.</span><span class="sxs-lookup"><span data-stu-id="df4ab-388">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="df4ab-389">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="df4ab-389">Frequently asked questions</span></span>

<span data-ttu-id="df4ab-390">**Moeten we RemoteMailboxes on-premises bijwerken in de bron na de verhuizing?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-390">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="df4ab-391">Ja, u moet het targetAddress (RemoteRoutingAddress/ExternalEmailAddress) van de lokale brongebruikers bijwerken wanneer het brontenderpostvak wordt verplaatst naar doelten tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-391">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="df4ab-392">Hoewel e-mailroutering de verwijzingen kan volgen voor meerdere e-mailgebruikers met verschillende doelAdressen, moeten vrije/bezet zoekactie voor e-mailgebruikers zich richten op de locatie van de postvakgebruiker.</span><span class="sxs-lookup"><span data-stu-id="df4ab-392">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="df4ab-393">Bij vrije/bezet zoekactie worden niet meerdere omleidingen achtervolgd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-393">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="df4ab-394">**Worden Teams vergaderingen gemigreerd tussen tenants?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-394">**Do Teams meetings migrate cross-tenant?**</span></span>  

<span data-ttu-id="df4ab-395">De vergaderingen worden verplaatst, maar de URL Teams vergadering wordt niet bijgewerkt wanneer items cross-tenant migreren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-395">The meetings will move however the Teams meeting URL does not update when items migrate cross-tenant.</span></span> <span data-ttu-id="df4ab-396">Aangezien de URL ongeldig is in de doel tenant, moet u de Teams verwijderen en opnieuw maken.</span><span class="sxs-lookup"><span data-stu-id="df4ab-396">Since the URL will be invalid in the target tenant you will need to remove and recreate the Teams meetings.</span></span>

<span data-ttu-id="df4ab-397">**Migreert de Teams inhoud van de chatmap cross-tenant?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-397">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="df4ab-398">Nee, de inhoud Teams chatmap wordt niet gemigreerd tussen tenants.</span><span class="sxs-lookup"><span data-stu-id="df4ab-398">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="df4ab-399">**Hoe kan ik alleen bewegingen zien die cross-tenant-moves zijn, niet mijn onboarding- en off-boarding-moves?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-399">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="df4ab-400">Gebruik de `-flags` parameter.</span><span class="sxs-lookup"><span data-stu-id="df4ab-400">Use the `-flags` parameter.</span></span> <span data-ttu-id="df4ab-401">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-401">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="df4ab-402">**Kunt u voorbeeldscripts geven voor het kopiëren van kenmerken die worden gebruikt bij het testen?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-402">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="df4ab-403">VOORBEELD: ZOALS HET IS, GEEN GARANTIE</span><span class="sxs-lookup"><span data-stu-id="df4ab-403">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="df4ab-404">In dit script wordt ervan uit gegaan dat er verbinding is met zowel het bronpostvak (om bronwaarden op te halen) als het doel on-premises Active Directory Domain Services (om het ADUser-object te stempelen).</span><span class="sxs-lookup"><span data-stu-id="df4ab-404">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="df4ab-405">Als bron een geschil of herstel van één item heeft ingeschakeld, stelt u dit in op het doelaccount.</span><span class="sxs-lookup"><span data-stu-id="df4ab-405">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="df4ab-406">Hierdoor wordt de grootte van de container van het doelaccount vergroot tot 100 GB.</span><span class="sxs-lookup"><span data-stu-id="df4ab-406">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="df4ab-407">**Hoe krijgen we toegang tot Outlook dag 1 nadat het postvak voor gebruik is verplaatst?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-407">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="df4ab-408">Aangezien slechts één tenant eigenaar kan zijn van een domein, wordt het voormalige primaire SMTPAddress niet gekoppeld aan de gebruiker in de doelten tenant wanneer het postvak wordt verplaatst. alleen de domeinen die zijn gekoppeld aan de nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-408">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="df4ab-409">Outlook gebruikt de nieuwe UPN-gebruikers om zich te verifiëren bij de service en het Outlook-profiel verwacht dat het oudere primaire SMTPAddress wordt gevonden dat past bij het postvak in het doelsysteem.</span><span class="sxs-lookup"><span data-stu-id="df4ab-409">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="df4ab-410">Aangezien het oudere adres niet in het doelsysteem staat, wordt er geen verbinding gemaakt met het Outlook-profiel om het zojuist verplaatste postvak te vinden.</span><span class="sxs-lookup"><span data-stu-id="df4ab-410">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="df4ab-411">Voor deze eerste implementatie moeten gebruikers hun profiel opnieuw opbouwen met hun nieuwe UPN- en primaire SMTP-adres en ost-inhoud opnieuw synchroniseren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-411">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="df4ab-412">Plan dezenovereenkomstig terwijl u uw gebruikers batcht voor voltooiing.</span><span class="sxs-lookup"><span data-stu-id="df4ab-412">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="df4ab-413">U moet rekening houden met het netwerkgebruik en de capaciteit wanneer Outlook clientprofielen worden gemaakt en de volgende OST- en OAB-bestanden worden gedownload naar clients.</span><span class="sxs-lookup"><span data-stu-id="df4ab-413">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="df4ab-414">**Waar Exchange RBAC-rollen moet ik lid van zijn om een cross-tenantverzet in te stellen of te voltooien?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-414">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="df4ab-415">Er is een matrix met rollen op basis van de aanname van gedelegeerde taken bij het uitvoeren van een postvakverhuis.</span><span class="sxs-lookup"><span data-stu-id="df4ab-415">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="df4ab-416">Er zijn momenteel twee rollen vereist:</span><span class="sxs-lookup"><span data-stu-id="df4ab-416">Currently, two roles are required:</span></span>  

- <span data-ttu-id="df4ab-417">De eerste rol is voor een een time setup-taak die de machtiging voor het verplaatsen van inhoud naar of buiten de tenant-organisatiegrens bepaalt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-417">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="df4ab-418">Aangezien het verplaatsen van gegevens uit uw organisatiebeheer een kritieke zorg is voor alle bedrijven, hebben we gekozen voor de hoogste toegewezen rol van Organisatiebeheerder (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="df4ab-418">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="df4ab-419">Deze rol moet een nieuwe Organisatierelationship wijzigen of instellen die definieert -MailboxMoveCapability met de externe organisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-419">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="df4ab-420">Alleen orgAdmin kan de instelling Postvakverzetbaarheid wijzigen, terwijl andere kenmerken op de OrganizationRelationhip kunnen worden beheerd door de beheerder van Federatief delen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-420">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="df4ab-421">De rol van het uitvoeren van de werkelijke opdrachten voor verplaatsen kan worden gedelegeerd aan een functie op lager niveau.</span><span class="sxs-lookup"><span data-stu-id="df4ab-421">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="df4ab-422">Aan de rol van Postvakken verplaatsen wordt de mogelijkheid toegewezen om postvakken in of uit de organisatie te verplaatsen met behulp van de `-RemoteTenant` parameter.</span><span class="sxs-lookup"><span data-stu-id="df4ab-422">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="df4ab-423">**Hoe wordt het SMTP-adres geselecteerd voor targetAddress (TargetDeliveryDomain) in het geconverteerde postvak (naar MailUser-conversie)?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-423">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="df4ab-424">Exchange met MRS maakt u het doeladres op het oorspronkelijke bronpostvak bij het converteren naar een MailUser door een e-mailadres (proxyAddress) op het doelobject te koppelen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-424">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="df4ab-425">Tijdens het proces wordt de waarde -TargetDeliveryDomain doorgegeven in de opdracht Verplaatsen en wordt vervolgens gecontroleerd op een overeenkomende proxy voor dat domein aan de doelzijde.</span><span class="sxs-lookup"><span data-stu-id="df4ab-425">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="df4ab-426">Wanneer we een overeenkomst vinden, wordt de overeenkomende proxyAddress gebruikt om het object ExternalEmailAddress (targetAddress) in te stellen op het geconverteerde postvak (nu MailUser).</span><span class="sxs-lookup"><span data-stu-id="df4ab-426">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="df4ab-427">**Hoe kunnen postvakmachtigingen overstappen?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-427">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="df4ab-428">Postvakmachtigingen zijn Verzenden namens en Postvaktoegang:</span><span class="sxs-lookup"><span data-stu-id="df4ab-428">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="df4ab-429">Send On Behalf Of (AD:publicDelegates) slaat de DN op van geadresseerden met toegang tot het postvak van een gebruiker als gemachtigde.</span><span class="sxs-lookup"><span data-stu-id="df4ab-429">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="df4ab-430">Deze waarde wordt opgeslagen in Active Directory en wordt momenteel niet verplaatst als onderdeel van de postvakovergang.</span><span class="sxs-lookup"><span data-stu-id="df4ab-430">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="df4ab-431">Als het bronpostvak openbareDelegates-set heeft, moet u de publicDelegates opnieuw op het doelpostvak opnieuwampen zodra de conversie van DEU naar postvak is voltooid in de doelomgeving door het uitvoeren `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` van .</span><span class="sxs-lookup"><span data-stu-id="df4ab-431">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="df4ab-432">Postvakmachtigingen die zijn opgeslagen in het postvak, worden samen met het postvak verplaatst wanneer zowel de hoofdsom als de gedelegeerde naar het doelsysteem worden verplaatst.</span><span class="sxs-lookup"><span data-stu-id="df4ab-432">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="df4ab-433">De gebruiker krijgt bijvoorbeeld TestUser_7 FullAccess toegewezen aan het postvak TestUser_8 in de tenant SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-433">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="df4ab-434">Nadat het postvak is verplaatst naar TargetCompany.onmicrosoft.com, worden dezelfde machtigingen ingesteld in de doelmap.</span><span class="sxs-lookup"><span data-stu-id="df4ab-434">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="df4ab-435">Voorbeelden met *Get-MailboxPermission* voor TestUser_7 in zowel bron- als doelten tenants worden hieronder weergegeven.</span><span class="sxs-lookup"><span data-stu-id="df4ab-435">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="df4ab-436">Exchange cmdlets worden voorafgevoegd met bron en doel dienovereenkomstig.</span><span class="sxs-lookup"><span data-stu-id="df4ab-436">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="df4ab-437">Hier is een voorbeeld van de uitvoer van de postvakmachtiging vóór een verhuizing.</span><span class="sxs-lookup"><span data-stu-id="df4ab-437">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="df4ab-438">Hier is een voorbeeld van de uitvoer van de postvakmachtiging na de verhuizing.</span><span class="sxs-lookup"><span data-stu-id="df4ab-438">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="df4ab-439">Machtigingen voor postvak met een kruis tenant en agenda worden NIET ondersteund.</span><span class="sxs-lookup"><span data-stu-id="df4ab-439">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="df4ab-440">U moet principals en gedelegeerden organiseren in samengevoegde verplaatste batches, zodat deze verbonden postvakken tegelijk vanuit de bronten tenant worden overgeslagen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-440">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="df4ab-441">**Welke X500-proxy moet worden toegevoegd aan de doel-MailUser-proxyadressen om migratie in te stellen?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-441">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="df4ab-442">Voor de migratie van een postvak met verschillende tenants moet de LegacyExchangeDN-waarde van het bronpostvakobject worden afgestempeld als een x500-e-mailadres op het doelobject MailUser.</span><span class="sxs-lookup"><span data-stu-id="df4ab-442">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="df4ab-443">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="df4ab-443">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="df4ab-444">Naast deze X500-proxy moet u alle X500-proxy's uit het postvak in de bron kopiëren naar het postvak in het doel.</span><span class="sxs-lookup"><span data-stu-id="df4ab-444">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="df4ab-445">**Waar kan ik problemen oplossen als het niet werkt?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-445">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="df4ab-446">Begin met het uitvoeren van VerifySetup.ps1 script op [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) en controleer de uitvoer.</span><span class="sxs-lookup"><span data-stu-id="df4ab-446">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="df4ab-447">Hier is een voorbeeld van het uitvoeren van VerifySetup.ps1 op de doel tenant:</span><span class="sxs-lookup"><span data-stu-id="df4ab-447">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="df4ab-448">Hier is een eExample van het uitvoeren van VerifySetup.ps1 op de bron tenant:</span><span class="sxs-lookup"><span data-stu-id="df4ab-448">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="df4ab-449">**Kunnen de bron en doel tenant dezelfde domeinnaam gebruiken?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-449">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="df4ab-450">Nee.</span><span class="sxs-lookup"><span data-stu-id="df4ab-450">No.</span></span> <span data-ttu-id="df4ab-451">De bron- en doel tenantdomeinnamen moeten uniek zijn.</span><span class="sxs-lookup"><span data-stu-id="df4ab-451">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="df4ab-452">Bijvoorbeeld een brondomein van contoso.com en het doeldomein van fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-452">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="df4ab-453">**Worden gedeelde postvakken verplaatst en werken ze nog steeds?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-453">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="df4ab-454">Ja, maar we behouden alleen de winkelmachtigingen zoals beschreven in deze artikelen:</span><span class="sxs-lookup"><span data-stu-id="df4ab-454">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="df4ab-455">Microsoft Docs | Machtigingen voor geadresseerden beheren in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="df4ab-455">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="df4ab-456">Microsoft Support | Machtigingen voor postvakken Exchange en Outlook in Office 365 toegewezen</span><span class="sxs-lookup"><span data-stu-id="df4ab-456">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="df4ab-457">**Is Azure Key Vault vereist en wanneer worden transacties uitgevoerd?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-457">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="df4ab-458">Ja, een Azure-abonnement is vereist om Key Vault te gebruiken om het certificaat op te slaan om migratie te machtigen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-458">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="df4ab-459">In tegenstelling tot onboarding-migraties die gebruikersnaam & wachtwoord gebruiken om zich te verifiëren bij de bron, gebruiken migraties tussen tenantpostvakken OAuth en dit certificaat als geheim/referentie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-459">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="df4ab-460">Toegang tot de Sleutelkluis moet gedurende alle postvakmigraties worden behouden, omdat deze eenmaal aan het begin en het einde van de migratie wordt gebruikt, evenals eenmaal per 24 uur tijdens incrementele synchronisatietijden.</span><span class="sxs-lookup"><span data-stu-id="df4ab-460">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="df4ab-461">U kunt hier de kostendetails van AKV [bekijken.]( https://azure.microsoft.com/en-us/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="df4ab-461">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="df4ab-462">**Hebt u aanbevelingen voor batches?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-462">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="df4ab-463">Niet meer dan 2000 postvakken per batch.</span><span class="sxs-lookup"><span data-stu-id="df4ab-463">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="df4ab-464">We raden ten zeerste aan om batches twee weken vóór de cut-overdatum in te dienen, omdat er geen gevolgen zijn voor de eindgebruikers tijdens de synchronisatie. Als u richtlijnen nodig hebt voor postvakken van meer dan 50.000, kunt u contact op met de distributielijst voor technische feedback op crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="df4ab-464">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="df4ab-465">**Wat moet ik doen als ik Serviceversleuteling gebruik met klantsleutel?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-465">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="df4ab-466">Het postvak wordt ontsleuteld voordat u het verplaatst.</span><span class="sxs-lookup"><span data-stu-id="df4ab-466">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="df4ab-467">Controleer of de klantsleutel is geconfigureerd in de doel tenant als deze nog steeds vereist is.</span><span class="sxs-lookup"><span data-stu-id="df4ab-467">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="df4ab-468">Zie [hier](../compliance/customer-key-overview.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-468">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="df4ab-469">**Wat is de geschatte migratietijd?**</span><span class="sxs-lookup"><span data-stu-id="df4ab-469">**What is the estimated migration time?**</span></span>

<span data-ttu-id="df4ab-470">Om u te helpen bij [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) het plannen van uw migratie, bevat de tabel hier de richtlijnen over wanneer bulkpostvakmigraties of afzonderlijke migraties moeten worden voltooid.</span><span class="sxs-lookup"><span data-stu-id="df4ab-470">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="df4ab-471">Deze schattingen zijn gebaseerd op een gegevensanalyse van eerdere klantmigraties.</span><span class="sxs-lookup"><span data-stu-id="df4ab-471">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="df4ab-472">Omdat elke omgeving uniek is, kan de exacte migratiesnelheid variëren.</span><span class="sxs-lookup"><span data-stu-id="df4ab-472">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="df4ab-473">Vergeet niet dat deze functie momenteel in de preview-versie staat en dat de SLA en de toepasselijke serviceniveaus niet van toepassing zijn op prestatie- of beschikbaarheidsproblemen tijdens de preview-status van deze functie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-473">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="df4ab-474">Bekende problemen</span><span class="sxs-lookup"><span data-stu-id="df4ab-474">Known issues</span></span>  

-  <span data-ttu-id="df4ab-475">**Probleem: Automatisch uitveerde archieven kunnen niet worden gemigreerd.**</span><span class="sxs-lookup"><span data-stu-id="df4ab-475">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="df4ab-476">De migratiefunctie voor verschillende tenants ondersteunt migraties van het primaire postvak en archiefpostvak voor een specifieke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="df4ab-476">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="df4ab-477">Als de gebruiker in de bron echter een automatisch uitgebouwd archief heeft, wat meer dan één archiefpostvak betekent, kan de functie de extra archieven niet migreren en mislukt deze.</span><span class="sxs-lookup"><span data-stu-id="df4ab-477">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="df4ab-478">**Probleem: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span><span class="sxs-lookup"><span data-stu-id="df4ab-478">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="df4ab-479">Wanneer u doelten tenant MailUser-objecten maakt, moet u ervoor zorgen dat alle SMTP-proxyadressen behoren tot de doeltenatororganisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-479">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="df4ab-480">Als er een SMTP-proxyAddress bestaat op de doelmailgebruiker die niet tot de lokale tenant behoort, wordt de conversie van de MailUser naar Postvak voorkomen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-480">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="df4ab-481">Dit komt door onze garantie dat postvakobjecten alleen e-mail kunnen verzenden van domeinen waarvoor de tenant gezaghebbend is (domeinen die door de tenant worden geclaimd):</span><span class="sxs-lookup"><span data-stu-id="df4ab-481">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="df4ab-482">Wanneer u gebruikers synchroniseert vanuit on-premises gebruik van Azure AD Verbinding maken, kunt u on-premises MailUser-objecten inrichten met ExternalEmailAddress die verwijst naar de brontenator waar het postvak bestaat (laran@contoso.onmicrosoft.com) en u stempelt het PrimarySMTPAddress als een domein dat zich in de doeltenator bevindt (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-482">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="df4ab-483">Deze waarden worden gesynchroniseerd met de tenant en een geschikte e-mailgebruiker is ingericht en klaar voor migratie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-483">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="df4ab-484">Hier wordt een voorbeeldobject weergegeven.</span><span class="sxs-lookup"><span data-stu-id="df4ab-484">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="df4ab-485">Het *contoso.onmicrosoft.com* adres is *niet aanwezig* in de matrix EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="df4ab-485">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="df4ab-486">**Probleem: MailUser-objecten met 'externe' primaire SMTP-adressen worden gewijzigd /opnieuw ingesteld op 'interne' geclaimde domeinen van het bedrijf**</span><span class="sxs-lookup"><span data-stu-id="df4ab-486">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="df4ab-487">MailUser-objecten zijn aanwijzers naar niet-lokale postvakken.</span><span class="sxs-lookup"><span data-stu-id="df4ab-487">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="df4ab-488">In het geval van migraties tussen tenantpostvakken gebruiken we MailUser-objecten om het bronpostvak (vanuit het perspectief van de doelorganisatie) of het doelpostvak weer te geven (vanuit het perspectief van de bronorganisatie).</span><span class="sxs-lookup"><span data-stu-id="df4ab-488">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="df4ab-489">De MailUsers hebben een ExternalEmailAddress (targetAddress) die wijst naar het smtp-adres van het werkelijke postvak (ProxyTest@fabrikam.onmicrosoft.com) en het primaireSMTP-adres dat het weergegeven SMTP-adres van de postvakgebruiker in de adreslijst vertegenwoordigt.</span><span class="sxs-lookup"><span data-stu-id="df4ab-489">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="df4ab-490">Sommige organisaties kiezen ervoor om het primaire SMTP-adres weer te geven als een extern SMTP-adres, niet als een adres dat eigendom is van/wordt geverifieerd door de lokale tenant (zoals fabrikam.com in plaats van als contoso.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-490">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="df4ab-491">Wanneer echter een Exchange-serviceplanobject via licentiebewerkingen op de MailUser wordt toegepast, wordt het primaire SMTP-adres gewijzigd om weer te geven als een domein dat is geverifieerd door de lokale organisatie (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="df4ab-491">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="df4ab-492">Er zijn twee mogelijke redenen:</span><span class="sxs-lookup"><span data-stu-id="df4ab-492">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="df4ab-493">Wanneer een Exchange-serviceplan wordt toegepast op een MailUser, wordt het Azure AD-proces gestart met het afdwingen van proxyschrof om ervoor te zorgen dat de lokale organisatie geen e-mail kan verzenden, spoofing of e-mail van een andere tenant.</span><span class="sxs-lookup"><span data-stu-id="df4ab-493">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="df4ab-494">Elk SMTP-adres op een geadresseerdeobject met deze serviceplannen wordt verwijderd als het adres niet wordt geverifieerd door de lokale organisatie.</span><span class="sxs-lookup"><span data-stu-id="df4ab-494">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="df4ab-495">Zoals in het voorbeeld het geval is, wordt het Fabikam.com niet geverifieerd door de contoso.onmicrosoft.com tenant, dus wordt het fabrikam.com verwijderd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-495">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="df4ab-496">Als u dit externe domein op MailUser wilt blijven gebruiken, vóór de migratie of na de migratie, moet u uw migratieprocessen wijzigen om licenties te strippen nadat de verhuizing is voltooid of vóór de verhuizing om ervoor te zorgen dat de verwachte externe huisstijl is toegepast op de gebruikers.</span><span class="sxs-lookup"><span data-stu-id="df4ab-496">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="df4ab-497">U moet ervoor zorgen dat het postvakobject een juiste licentie heeft om de e-mailservice niet te beïnvloeden.</span><span class="sxs-lookup"><span data-stu-id="df4ab-497">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="df4ab-498">Hier wordt een voorbeeldscript weergegeven om de serviceplannen op een MailUser in Contoso.onmicrosoft.com tenant te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="df4ab-498">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="df4ab-499">De resultaten in de set serviceplannen die zijn toegewezen, worden hier weergegeven.</span><span class="sxs-lookup"><span data-stu-id="df4ab-499">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="df4ab-500">Het PrimarySMTPAddress van de gebruiker wordt niet meer geschuurd.</span><span class="sxs-lookup"><span data-stu-id="df4ab-500">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="df4ab-501">Het fabrikam.com domein is niet eigendom van de contoso.onmicrosoft.com tenant en blijft bestaan als het primaire SMTP-adres dat wordt weergegeven in de adreslijst.</span><span class="sxs-lookup"><span data-stu-id="df4ab-501">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="df4ab-502">Hier volgt een voorbeeld.</span><span class="sxs-lookup"><span data-stu-id="df4ab-502">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="df4ab-503">Wanneer msExchRemoteRecipientType is ingesteld op 8 (DeprovisionMailbox), voor on-premises MailUsers die worden gemigreerd naar de doeltenant, worden met de proxyschrootlogica in Azure niet-geeigende domeinen verwijderd en wordt de primaireSMTP opnieuw ingesteld op een eigendomsdomein.</span><span class="sxs-lookup"><span data-stu-id="df4ab-503">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="df4ab-504">Door msExchRemoteRecipientType in de on-premises MailUser te wissen, is de proxyscrublogica niet meer van toepassing.</span><span class="sxs-lookup"><span data-stu-id="df4ab-504">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="df4ab-505">Hieronder vindt u de volledige set mogelijke serviceplannen met Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="df4ab-505">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="df4ab-506">Naam</span><span class="sxs-lookup"><span data-stu-id="df4ab-506">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="df4ab-507">Advanced eDiscovery Storage (500 GB)</span><span class="sxs-lookup"><span data-stu-id="df4ab-507">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="df4ab-508">Klanten-lockbox</span><span class="sxs-lookup"><span data-stu-id="df4ab-508">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="df4ab-509">Preventie van gegevensverlies</span><span class="sxs-lookup"><span data-stu-id="df4ab-509">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="df4ab-510">Exchange Enterprise CAL-services (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="df4ab-510">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="df4ab-511">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="df4ab-511">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="df4ab-512">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="df4ab-512">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="df4ab-513">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="df4ab-513">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="df4ab-514">Exchange Online (Abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="df4ab-514">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="df4ab-515">Exchange Online (Abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="df4ab-515">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="df4ab-516">Exchange Online Archiving voor Exchange Online</span><span class="sxs-lookup"><span data-stu-id="df4ab-516">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="df4ab-517">Exchange Online Archiving voor Exchange Server</span><span class="sxs-lookup"><span data-stu-id="df4ab-517">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="df4ab-518">Exchange Online Inactieve gebruikersinvoegvoeging</span><span class="sxs-lookup"><span data-stu-id="df4ab-518">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="df4ab-519">Exchange Online Kiosk</span><span class="sxs-lookup"><span data-stu-id="df4ab-519">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="df4ab-520">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="df4ab-520">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="df4ab-521">Exchange Online Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="df4ab-521">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="df4ab-522">Exchange Online POP</span><span class="sxs-lookup"><span data-stu-id="df4ab-522">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="df4ab-523">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="df4ab-523">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="df4ab-524">Informatiebarrières</span><span class="sxs-lookup"><span data-stu-id="df4ab-524">Information Barriers</span></span>                              |
   | <span data-ttu-id="df4ab-525">Informatiebeveiliging voor Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="df4ab-525">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="df4ab-526">Informatiebeveiliging voor Office 365 - Standaard</span><span class="sxs-lookup"><span data-stu-id="df4ab-526">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="df4ab-527">Inzichten van MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="df4ab-527">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="df4ab-528">Microsoft 365 Geavanceerd controleren</span><span class="sxs-lookup"><span data-stu-id="df4ab-528">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="df4ab-529">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="df4ab-529">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="df4ab-530">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="df4ab-530">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="df4ab-531">Microsoft MyAnalytics (Volledig)</span><span class="sxs-lookup"><span data-stu-id="df4ab-531">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="df4ab-532">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="df4ab-532">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="df4ab-533">Microsoft Defender voor Office 365 (Abonnement 1)</span><span class="sxs-lookup"><span data-stu-id="df4ab-533">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="df4ab-534">Microsoft Defender voor Office 365 (Abonnement 2)</span><span class="sxs-lookup"><span data-stu-id="df4ab-534">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="df4ab-535">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="df4ab-535">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="df4ab-536">Premium Versleuteling in Office 365</span><span class="sxs-lookup"><span data-stu-id="df4ab-536">Premium Encryption in Office 365</span></span>                  |
