---
title: Stap 1. Uw Microsoft 365 for Enterprise-tenants
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Het implementeren en beheren van enkele of meerdere Microsoft 365-tenants, met opties voor meervoudige geografische en verplaatsings locaties.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908511"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="b13bc-104">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="b13bc-104">Step 1.</span></span> <span data-ttu-id="b13bc-105">Uw Microsoft 365 for Enterprise-tenants</span><span class="sxs-lookup"><span data-stu-id="b13bc-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="b13bc-106">Een van uw eerste Tenant beslissingen is wat u moet hebben.</span><span class="sxs-lookup"><span data-stu-id="b13bc-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="b13bc-107">Elke Microsoft 365-Tenant is DISTINCT, Unique en los van alle andere Microsoft 365-tenants.</span><span class="sxs-lookup"><span data-stu-id="b13bc-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="b13bc-108">De bijbehorende Azure AD-Tenant is ook uniek en apart van alle andere Microsoft 365-tenants.</span><span class="sxs-lookup"><span data-stu-id="b13bc-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="b13bc-109">Eén Tenant</span><span class="sxs-lookup"><span data-stu-id="b13bc-109">Single tenant</span></span>
<span data-ttu-id="b13bc-110">Als u één Tenant gebruikt, worden veel aspecten van het gebruik van Microsoft 365 eenvoudiger.</span><span class="sxs-lookup"><span data-stu-id="b13bc-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="b13bc-111">Eén Tenant betekent één Azure AD-Tenant met één set accounts, groepen en beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="b13bc-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="b13bc-112">U kunt de machtigingen voor het delen van bronnen in uw organisatie via deze centrale identiteitsprovider doen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="b13bc-113">Eén Tenant biedt de meeste functies-rijke en vereenvoudigde samenwerking en productiviteits ervaring voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b13bc-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="b13bc-114">Hier ziet u een voorbeeld met de standaardlocatie en de Azure AD-Tenant van een Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Eén Microsoft 365-Tenant met de Azure AD-Tenant](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="b13bc-116">Meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="b13bc-116">Multiple tenants</span></span>

<span data-ttu-id="b13bc-117">Er zijn verschillende redenen waarom uw organisatie meerdere tenants heeft:</span><span class="sxs-lookup"><span data-stu-id="b13bc-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="b13bc-118">Beheerders isolatie</span><span class="sxs-lookup"><span data-stu-id="b13bc-118">Administrative isolation</span></span>
- <span data-ttu-id="b13bc-119">Gecentraliseerd</span><span class="sxs-lookup"><span data-stu-id="b13bc-119">Decentralized IT</span></span>
- <span data-ttu-id="b13bc-120">Historische beslissingen</span><span class="sxs-lookup"><span data-stu-id="b13bc-120">Historical decisions</span></span>
- <span data-ttu-id="b13bc-121">Samenvoegbewerkingen, acquisities of divestitures</span><span class="sxs-lookup"><span data-stu-id="b13bc-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="b13bc-122">Scheiding van huisstijl voor conglomeraat organisaties wissen</span><span class="sxs-lookup"><span data-stu-id="b13bc-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="b13bc-123">Voorbereidingen voor productie, testen of sandbox-tenants</span><span class="sxs-lookup"><span data-stu-id="b13bc-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="b13bc-124">Hier ziet u een voorbeeld van een organisatie met twee tenants (Tenant A en Tenant B) in hetzelfde standaardgebied geo.</span><span class="sxs-lookup"><span data-stu-id="b13bc-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="b13bc-125">Elke Tenant als afzonderlijke Azure AD-Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-125">Each tenant as a separate Azure AD tenant.</span></span>

![Meerdere Microsoft 365-tenants met hun eigen Azure AD-tenants](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="b13bc-127">Wanneer er meerdere tenants zijn, gelden er beperkingen en aanvullende aandachtspunten wanneer u ze beheert en services levert voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b13bc-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="b13bc-128">Samenwerking tussen verschillende tenants</span><span class="sxs-lookup"><span data-stu-id="b13bc-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="b13bc-129">Als u wilt dat uw gebruikers effectiever samenwerken in verschillende Microsoft 365-tenants op een veilige manier, kunt u gebruikmaken van een centrale locatie voor het delen van bestanden en gesprekken, agenda's delen, met behulp van CHATBERICHTEN, audio/video bellen en het beveiligen van toegang tot bronnen en toepassingen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="b13bc-130">Zie [samenwerken via Microsoft 365 tussen tenants](../enterprise/microsoft-365-inter-tenant-collaboration.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="b13bc-131">Migratie van cross-Tenant postvak (preview)</span><span class="sxs-lookup"><span data-stu-id="b13bc-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="b13bc-132">Voordat u Exchange Online-postvakken tussen tenants verplaatst, moet u, voordat u migratie van cross-tenants migreert, volledig verwijderen van de huidige Tenant (de bron Tenant) naar on-premises en ze vervolgens op een nieuwe Tenant (de doel Tenant) plaatsen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="b13bc-133">Met de nieuwe functie voor het migreren van postvakken kunnen tenantbeheerders van de bron-en doel tenants postvakken verplaatsen tussen de tenants met minimale infrastructuur afhankelijkheden in hun on-premises systemen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="b13bc-134">Hiermee verwijdert u de postvakken die u niet nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b13bc-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="b13bc-135">Hieronder vindt u twee voorbeelden van tenants en hun postvakken vóór migratie van postvakken van cross tenants.</span><span class="sxs-lookup"><span data-stu-id="b13bc-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Meerdere Microsoft 365-tenants en hun postvakken](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="b13bc-137">In deze afbeelding hebben twee afzonderlijke tenants eigen domeinen en set Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="b13bc-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="b13bc-138">Dit is de doel Tenant (Tenant A) na migratie van cross-Tenant berichten.</span><span class="sxs-lookup"><span data-stu-id="b13bc-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![De doel Tenant na migratie van cross-Tenant Postvak](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="b13bc-140">In deze afbeelding heeft één Tenant beide domeinen en beide sets Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="b13bc-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="b13bc-141">Zie voor meer informatie [migratie van migratie](../enterprise/cross-tenant-mailbox-migration.md)via een Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="b13bc-142">Tenant-naar-tenant-migraties</span><span class="sxs-lookup"><span data-stu-id="b13bc-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="b13bc-143">Er zijn diverse architecturale benaderingen voor fusies, verwervingen, divestitures en andere scenario's waarmee u een bestaande Microsoft 365-Tenant kunt migreren naar een nieuwe Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="b13bc-144">Zie [Microsoft 365 Tenant-to-Tenant-migraties](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)voor uitgebreide informatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="b13bc-145">Meerdere geografische voor een Tenant</span><span class="sxs-lookup"><span data-stu-id="b13bc-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="b13bc-146">Met Microsoft 365 in Microsoft kunt u gegevens op de rest van de andere datacenter geo-locaties inrichten en bewaren die u hebt gekozen om te voldoen aan de vereisten voor gegevens woonplaats en tegelijk de wereldwijde implementatie van de moderne productiviteits ervaringen met uw werknemers ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="b13bc-147">In een omgeving met meerdere geografische locaties bestaat uw Microsoft 365-Tenant uit een standaard-of centrale locatie waar uw Microsoft 365-abonnement oorspronkelijk is gemaakt en een of meer satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="b13bc-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="b13bc-148">In een Tenant met meerdere geo-gebruikers is de informatie over geo-locaties, groepen en gebruikers informatie gemastereerd in een wereldwijde Azure AD-Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="b13bc-149">Aangezien uw Tenant gegevens centraal worden gemigreerd en op elke geografische locatie worden gesynchroniseerd, worden de samenwerking van gebruikers die zich in uw bedrijf bevinden, via de locaties gedeeld.</span><span class="sxs-lookup"><span data-stu-id="b13bc-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="b13bc-150">Hier ziet u een voorbeeld van een organisatie met de standaardlocatie in Europe en de vestiging van een satelliet in Noord-Amerika.</span><span class="sxs-lookup"><span data-stu-id="b13bc-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="b13bc-151">Beide locaties delen dezelfde wereldwijde Azure AD-Tenant voor de afzonderlijke Microsoft 365-Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Voorbeeld van een meervoudige geo Microsoft 365-Tenant](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="b13bc-153">Zie [Microsoft 365 multi-geo](../enterprise/microsoft-365-multi-geo.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="b13bc-154">Kerngegevens verplaatsen naar een nieuw datacenter-geo</span><span class="sxs-lookup"><span data-stu-id="b13bc-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="b13bc-155">Microsoft gaat verder met het openen van nieuwe datacenter GEOS voor Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="b13bc-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="b13bc-156">Met deze nieuwe datacenter-GEOS kunt u capaciteit en de berekenings bronnen voor onze aanhoudende klantvraag en gebruiks groei toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="b13bc-157">Daarnaast biedt de nieuwe datacenter GEOS een in-geo data woonplaats voor de primaire klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="b13bc-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="b13bc-158">Hoewel het openen van een nieuw datacenter geo geen invloed heeft op uw gegevens en de kerngegevens die zijn opgeslagen in een al bestaand datacenter, is Microsoft u in staat een vroegtijdige migratie van de kern klantgegevens van uw organisatie bij elkaar te betrekken voor een nieuw datacenter-geo.</span><span class="sxs-lookup"><span data-stu-id="b13bc-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="b13bc-159">Hier ziet u een voorbeeld waarin een Microsoft 365-Tenant van de Europese Unie (EU) datacenter naar de naam van het Verenigd Koninkrijk (VK) is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="b13bc-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Voorbeeld van het verplaatsen van een Microsoft 365-Tenant tussen datacenter GEOS](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="b13bc-161">Zie [Core Data verplaatsen naar nieuwe Microsoft 365 datacenter GEOS](../enterprise/moving-data-to-new-datacenter-geos.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="b13bc-162">Producten en licenties voor een Tenant</span><span class="sxs-lookup"><span data-stu-id="b13bc-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="b13bc-163">Uw Microsoft 365-Tenant wordt gemaakt wanneer u uw eerste product koopt, zoals Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="b13bc-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="b13bc-164">Samen met het product zijn licenties, dat maandelijks of jaarlijks kosten in rekening worden gebracht.</span><span class="sxs-lookup"><span data-stu-id="b13bc-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="b13bc-165">Een beheerder wijst vervolgens een beschikbare licentie van een van uw producten toe aan een gebruikersaccount, hetzij direct of via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="b13bc-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="b13bc-166">Afhankelijk van de bedrijfsbehoeften van uw organisatie, hebt u mogelijk een set producten, elk met een eigen groep licenties.</span><span class="sxs-lookup"><span data-stu-id="b13bc-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="b13bc-167">Het bepalen van de set producten en het aantal licenties waarvoor elke planning moet worden gepland:</span><span class="sxs-lookup"><span data-stu-id="b13bc-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="b13bc-168">Zorg ervoor dat er voldoende licenties zijn voor de gebruikersaccounts waarvoor u geavanceerde functies nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b13bc-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="b13bc-169">Hiermee kunt u voorkomen dat licenties worden uitgevoerd of te veel niet-toegewezen licenties zijn, op basis van wijzigingen in het personeel van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="b13bc-170">Resultaten van stap 1</span><span class="sxs-lookup"><span data-stu-id="b13bc-170">Results of Step 1</span></span>

<span data-ttu-id="b13bc-171">Voor uw Microsoft 365 for Enterprise-tenants hebt u het volgende vastgesteld:</span><span class="sxs-lookup"><span data-stu-id="b13bc-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="b13bc-172">Hoeveel tenants u hebt of nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b13bc-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="b13bc-173">U moet voor iedere Tenant de producten en licenties aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="b13bc-174">Of een Tenant moet meerdere geo moet zijn om te voldoen aan de vereisten voor data-woonplaats.</span><span class="sxs-lookup"><span data-stu-id="b13bc-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="b13bc-175">Of u de samenwerking tussen tenants moet instellen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="b13bc-176">Of u één Tenant naar een andere Tenant moet migreren.</span><span class="sxs-lookup"><span data-stu-id="b13bc-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="b13bc-177">Of u de kerngegevens van een datacenter naar een andere datacenter moet verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="b13bc-178">Hier ziet u een voorbeeld van een nieuwe Tenant.</span><span class="sxs-lookup"><span data-stu-id="b13bc-178">Here is an example of a new tenant.</span></span>

![Voorbeeld van een nieuwe Tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="b13bc-180">In deze afbeelding is de Tenant:</span><span class="sxs-lookup"><span data-stu-id="b13bc-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="b13bc-181">Een standaardlocatie die overeenstemt met een Microsoft 365 datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="b13bc-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="b13bc-182">Een reeks producten en licenties.</span><span class="sxs-lookup"><span data-stu-id="b13bc-182">A set of products and licenses.</span></span>
- <span data-ttu-id="b13bc-183">De set Cloud productiviteitstoepassingen, waarvan sommige specifiek zijn voor producten.</span><span class="sxs-lookup"><span data-stu-id="b13bc-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="b13bc-184">Een Azure AD-Tenant die globale beheerdersaccounts en een initiële DNS-domeinnaam bevat.</span><span class="sxs-lookup"><span data-stu-id="b13bc-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="b13bc-185">Wanneer we de extra stappen van deze oplossing doorlopen, wordt deze afbeelding opgebouwd.</span><span class="sxs-lookup"><span data-stu-id="b13bc-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="b13bc-186">Voortdurende onderhoud voor tenants</span><span class="sxs-lookup"><span data-stu-id="b13bc-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="b13bc-187">Het kan zijn dat u het volgende moet doen:</span><span class="sxs-lookup"><span data-stu-id="b13bc-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="b13bc-188">Een nieuwe Tenant toevoegen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-188">Add a new tenant.</span></span>
- <span data-ttu-id="b13bc-189">Voeg nieuwe producten toe aan een Tenant met een initieel aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="b13bc-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="b13bc-190">Wijzig de reeks licenties voor een product in een Tenant zodat u deze kunt aanpassen aan de vereisten voor het wijzigen van de werknemer.</span><span class="sxs-lookup"><span data-stu-id="b13bc-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="b13bc-191">Verplaats uw kerngegevens van een Tenant naar een nieuwe datacenter-geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="b13bc-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="b13bc-192">Voeg een meervoudige geo voor de woonplaats-vereisten voor data.</span><span class="sxs-lookup"><span data-stu-id="b13bc-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="b13bc-193">Samenwerking tussen tenants instellen.</span><span class="sxs-lookup"><span data-stu-id="b13bc-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="b13bc-194">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b13bc-194">Next step</span></span>

<span data-ttu-id="b13bc-195">[![. Optimaliseer uw Tenant voor netwerktoegang](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="b13bc-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="b13bc-196">Ga verder met [netwerken](tenant-management-networking.md) om optimaal netwerk van uw werknemers in te stellen voor microsoft 365-cloudservices.</span><span class="sxs-lookup"><span data-stu-id="b13bc-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
