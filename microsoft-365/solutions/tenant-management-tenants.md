---
title: Stap 1. Uw Microsoft 365 voor enterprise-tenants
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
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Een of meer Microsoft 365-tenants implementeren en beheren, met opties voor multige geo-locaties en locaties waar u zich kunt verplaatsen.
ms.openlocfilehash: 4d9bd685fce6fb2f11b8e17bebae6460e0c10bd2
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406382"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="7699b-104">Stap 1.</span><span class="sxs-lookup"><span data-stu-id="7699b-104">Step 1.</span></span> <span data-ttu-id="7699b-105">Uw Microsoft 365 voor enterprise-tenants</span><span class="sxs-lookup"><span data-stu-id="7699b-105">Your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="7699b-106">Een van uw eerste tenantbeslissingen is hoeveel u er moet hebben.</span><span class="sxs-lookup"><span data-stu-id="7699b-106">One of your first tenant decisions is how many to have.</span></span> <span data-ttu-id="7699b-107">Elke Microsoft 365-tenant is uniek en gescheiden van alle andere Microsoft 365-tenants.</span><span class="sxs-lookup"><span data-stu-id="7699b-107">Each Microsoft 365 tenant is distinct, unique, and separate from all other Microsoft 365 tenants.</span></span> <span data-ttu-id="7699b-108">De bijbehorende Azure AD-tenant is ook uniek en gescheiden van alle andere Microsoft 365-tenants.</span><span class="sxs-lookup"><span data-stu-id="7699b-108">It’s corresponding Azure AD tenant is also distinct, unique, and separate from all other Microsoft 365 tenants.</span></span>

## <a name="single-tenant"></a><span data-ttu-id="7699b-109">Eén tenant</span><span class="sxs-lookup"><span data-stu-id="7699b-109">Single tenant</span></span>
<span data-ttu-id="7699b-110">Eén tenant vereenvoudigt veel aspecten van het gebruik van Microsoft 365 in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7699b-110">Having a single tenant simplifies many aspects of your organization’s use of Microsoft 365.</span></span> <span data-ttu-id="7699b-111">Eén tenant betekent één Azure AD-tenant met één set accounts, groepen en beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="7699b-111">A single tenant means a single Azure AD tenant with a single set of accounts, groups, and policies.</span></span> <span data-ttu-id="7699b-112">Machtigingen en het delen van resources binnen uw organisatie kunnen worden uitgevoerd via deze centrale identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="7699b-112">Permissions and sharing of resources across your organization can be done through this central identity provider.</span></span>

<span data-ttu-id="7699b-113">Eén tenant biedt de meest uitgebreide en vereenvoudigde samenwerkings- en productiviteitservaring voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7699b-113">A single tenant provides the most feature-rich and simplified collaboration and productivity experience for your users.</span></span>

<span data-ttu-id="7699b-114">Hier is een voorbeeld met de standaardlocatie en Azure AD-tenant van een Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-114">Here is an example showing the default location and Azure AD tenant of a Microsoft 365 tenant.</span></span>

![Eén Microsoft 365-tenant met de Azure AD-tenant](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a><span data-ttu-id="7699b-116">Meerdere tenants</span><span class="sxs-lookup"><span data-stu-id="7699b-116">Multiple tenants</span></span>

<span data-ttu-id="7699b-117">Er zijn diverse redenen waarom uw organisatie meerdere tenants kan hebben:</span><span class="sxs-lookup"><span data-stu-id="7699b-117">There are many reasons why your organization could have multiple tenants:</span></span>

- <span data-ttu-id="7699b-118">Administratieve isolatie</span><span class="sxs-lookup"><span data-stu-id="7699b-118">Administrative isolation</span></span>
- <span data-ttu-id="7699b-119">Autoriserende IT</span><span class="sxs-lookup"><span data-stu-id="7699b-119">Decentralized IT</span></span>
- <span data-ttu-id="7699b-120">Historische beslissingen</span><span class="sxs-lookup"><span data-stu-id="7699b-120">Historical decisions</span></span>
- <span data-ttu-id="7699b-121">Fusies, overnames of verkoop</span><span class="sxs-lookup"><span data-stu-id="7699b-121">Mergers, acquisitions, or divestitures</span></span>
- <span data-ttu-id="7699b-122">Scheiding van huisstijl voor conglomeratie-organisaties duidelijk maken</span><span class="sxs-lookup"><span data-stu-id="7699b-122">Clear separation of branding for conglomerate organizations</span></span>
- <span data-ttu-id="7699b-123">Pre-productie-, test- of sandbox-tenants</span><span class="sxs-lookup"><span data-stu-id="7699b-123">Pre-production, test, or sandbox tenants</span></span>

<span data-ttu-id="7699b-124">Hier is een voorbeeld van een organisatie die twee tenants (Tenant A en Tenant B) heeft in hetzelfde standaard datacenter geo.</span><span class="sxs-lookup"><span data-stu-id="7699b-124">Here is an example of an organization that has two tenants (Tenant A and Tenant B) in the same default datacenter geo.</span></span> <span data-ttu-id="7699b-125">Elke tenant als een afzonderlijke Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-125">Each tenant as a separate Azure AD tenant.</span></span>

![Meerdere Microsoft 365-tenants met hun eigen Azure AD-tenants](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

<span data-ttu-id="7699b-127">Als u meerdere tenants hebt, zijn er beperkingen en extra overwegingen bij het beheren van deze tenants en het leveren van services aan uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="7699b-127">When you have multiple tenants, there are restrictions and additional considerations when managing them and providing services to your users.</span></span>

### <a name="inter-tenant-collaboration"></a><span data-ttu-id="7699b-128">Samenwerking tussen verschillende tenants</span><span class="sxs-lookup"><span data-stu-id="7699b-128">Inter-tenant collaboration</span></span>

<span data-ttu-id="7699b-129">Als u wilt dat uw gebruikers op een veilige manier efficiënter samenwerken tussen verschillende Microsoft 365-tenants, kunt u samenwerken tussen tenants door een centrale locatie te gebruiken voor bestanden en gesprekken, agenda's te delen, chatberichten te gebruiken, audio-/videogesprekken te gebruiken voor communicatie en de toegang tot resources en toepassingen te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="7699b-129">If you want your users to collaborate more effectively across different Microsoft 365 tenants in a secure manner, inter-tenant collaboration options include using a central location for files and conversations, sharing calendars, using IM, audio/video calls for communication, and securing access to resources and applications.</span></span>

<span data-ttu-id="7699b-130">Zie microsoft [365](../enterprise/microsoft-365-inter-tenant-collaboration.md)samenwerking tussen verschillende tenants voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7699b-130">For more information, see [Microsoft 365 inter-tenant collaboration](../enterprise/microsoft-365-inter-tenant-collaboration.md).</span></span>

### <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="7699b-131">Migratie van postvakken tussen tenants (preview)</span><span class="sxs-lookup"><span data-stu-id="7699b-131">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="7699b-132">Vóór migratie van postvakken op verschillende tenants (in preview) moet u bij het verplaatsen van Exchange Online-postvakken tussen tenants het postvak van een gebruiker volledig offboarden van de huidige tenant (de bronten tenant) naar de on-premises tenant en ze vervolgens onboarden naar een nieuwe tenant (de doelten tenant).</span><span class="sxs-lookup"><span data-stu-id="7699b-132">Prior to cross-tenant mailbox migration (in preview), when moving Exchange Online mailboxes between tenants, you have to completely offboard a user mailbox from their current tenant (the source tenant) to on-premises and then onboard them to a new tenant (the target tenant).</span></span> <span data-ttu-id="7699b-133">Met de nieuwe functie voor migratie van postvakken op verschillende tenants kunnen tenantbeheerders in zowel de bron- als doelten tenants postvakken verplaatsen tussen de tenants met minimale infrastructuurafhankelijkheden in hun on-premises systemen.</span><span class="sxs-lookup"><span data-stu-id="7699b-133">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="7699b-134">Hiermee verwijdert u de noodzaak om postvakken aan de andere bord- en onboard-app toe te laten.</span><span class="sxs-lookup"><span data-stu-id="7699b-134">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="7699b-135">Hier volgen twee voorbeeldtententen en hun postvakken vóór de migratie van postvakken tussen tenants.</span><span class="sxs-lookup"><span data-stu-id="7699b-135">Here are two example tenants and their mailboxes before cross-tenant mailbox migration.</span></span>

![Meerdere Microsoft 365-tenants en hun postvakken](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

<span data-ttu-id="7699b-137">In deze afbeelding hebben twee afzonderlijke tenants hun eigen domeinen en set Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="7699b-137">In this illustration, two separate tenants have their own domains and set of Exchange mailboxes.</span></span>

<span data-ttu-id="7699b-138">Hier is de doel tenant (Tenant A) na de migratie van postvakken tussen tenants.</span><span class="sxs-lookup"><span data-stu-id="7699b-138">Here is the target tenant (Tenant A) after cross-tenant mailbox migration.</span></span>

![De doel tenant na migratie van postvakken tussen tenants](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

<span data-ttu-id="7699b-140">In deze afbeelding heeft één tenant zowel domeinen als beide sets Exchange-postvakken.</span><span class="sxs-lookup"><span data-stu-id="7699b-140">In this illustration, a single tenant has both domains and both sets of Exchange mailboxes.</span></span>

<span data-ttu-id="7699b-141">Zie Postvakmigratie tussen [tenants voor meer informatie.](../enterprise/cross-tenant-mailbox-migration.md)</span><span class="sxs-lookup"><span data-stu-id="7699b-141">For more information, see [Cross-tenant mailbox migration](../enterprise/cross-tenant-mailbox-migration.md).</span></span>

### <a name="tenant-to-tenant-migrations"></a><span data-ttu-id="7699b-142">Tenant-naar-tenant-migraties</span><span class="sxs-lookup"><span data-stu-id="7699b-142">Tenant-to-tenant migrations</span></span>

<span data-ttu-id="7699b-143">Er zijn verschillende architectuurbenaderingen voor fusies, overnames, verkoop en andere scenario's die ertoe kunnen leiden dat u een bestaande Microsoft 365-tenant migreert naar een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-143">There are several architectural approaches for mergers, acquisitions, divestitures, and other scenarios that might lead you to migrate an existing Microsoft 365 tenant to a new tenant.</span></span> 

<span data-ttu-id="7699b-144">Zie Microsoft [365-tenant-naar-tenantmigraties voor gedetailleerde instructies.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)</span><span class="sxs-lookup"><span data-stu-id="7699b-144">For detailed guidance, see [Microsoft 365 tenant-to-tenant migrations](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).</span></span>

## <a name="multi-geo-for-a-tenant"></a><span data-ttu-id="7699b-145">Multi-Geo voor een tenant</span><span class="sxs-lookup"><span data-stu-id="7699b-145">Multi-Geo for a tenant</span></span>

<span data-ttu-id="7699b-146">Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan in de geolocaties van het andere datacenter die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag en tegelijkertijd uw globale implementatie van moderne productiviteitservaringen voor uw collega's ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="7699b-146">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the other datacenter geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global rollout of modern productivity experiences to your workers.</span></span>

<span data-ttu-id="7699b-147">In een Multi Geo-omgeving bestaat uw Microsoft 365-tenant uit een standaard- of centrale locatie waar uw Microsoft 365-abonnement oorspronkelijk is gemaakt en een of meer satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="7699b-147">In a Multi-Geo environment, your Microsoft 365 tenant consists of a default or central location where your Microsoft 365 subscription was originally created and one or more satellite locations.</span></span> <span data-ttu-id="7699b-148">In een multige geo-tenant wordt de informatie over geografische locaties, groepen en gebruikersgegevens gemodeld in een globale Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-148">In a multi-geo tenant, the information about geo locations, groups, and user information is mastered in a global Azure AD tenant.</span></span> <span data-ttu-id="7699b-149">Omdat uw tenantgegevens centraal worden gemodelleerd en gesynchroniseerd in elke geografische locatie, worden samenwerkingservaringen met iedereen in uw bedrijf gedeeld over de locaties.</span><span class="sxs-lookup"><span data-stu-id="7699b-149">Because your tenant information is mastered centrally and synchronized into each geo location, collaboration experiences involving anyone from your company are shared across the locations.</span></span>

<span data-ttu-id="7699b-150">Hier is een voorbeeld van een organisatie met een standaardlocatie in Europa en een satellietlocatie in Noord-Amerika.</span><span class="sxs-lookup"><span data-stu-id="7699b-150">Here is an example of an organization that has its default location in Europe and a satellite location in North America.</span></span> <span data-ttu-id="7699b-151">Beide locaties delen dezelfde globale Azure AD-tenant voor één Microsoft 365-tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-151">Both locations share the same global Azure AD tenant for the single Microsoft 365 tenant.</span></span>

![Voorbeeld van een Multi Geo Microsoft 365-tenant](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

<span data-ttu-id="7699b-153">Zie [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="7699b-153">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

## <a name="moving-core-data-to-a-new-datacenter-geo"></a><span data-ttu-id="7699b-154">Belangrijke gegevens verplaatsen naar een nieuw geografisch datacenter</span><span class="sxs-lookup"><span data-stu-id="7699b-154">Moving core data to a new datacenter geo</span></span>

<span data-ttu-id="7699b-155">Microsoft blijft het nieuwe datacenter geos openen voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="7699b-155">Microsoft continues to open new datacenter geos for Microsoft 365 services.</span></span> <span data-ttu-id="7699b-156">Deze nieuwe datacenters voegen capaciteits- en berekeningsbronnen toe om onze continue vraag en gebruiksgroei van klanten te ondersteunen.</span><span class="sxs-lookup"><span data-stu-id="7699b-156">These new datacenter geos add capacity and compute resources to support our ongoing customer demand and usage growth.</span></span> <span data-ttu-id="7699b-157">Bovendien bieden de nieuwe datacenter geo's in-geo-gegevens opgeslagen voor belangrijke klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="7699b-157">Additionally, the new datacenter geos offer in-geo data residency for core customer data.</span></span>

<span data-ttu-id="7699b-158">Hoewel het openen van een nieuw datacenter geo geen invloed heeft op u en uw kerngegevens die zijn opgeslagen in een bestaande geografische datacenter, kunt u met Microsoft een vroege migratie aanvragen van de kernklantgegevens van uw organisatie in rust naar een nieuw geografisch datacenter.</span><span class="sxs-lookup"><span data-stu-id="7699b-158">Although opening a new datacenter geo does not impact you and your core data stored in an already existing datacenter geo, Microsoft allows you to request an early migration of your organization's core customer data at rest to a new datacenter geo.</span></span>

<span data-ttu-id="7699b-159">Hier is een voorbeeld waarin een Microsoft 365-tenant is verplaatst van het geografische datacenter van de Europese Unie (EU) naar het datacenter in het Verenigd Koninkrijk (VK).</span><span class="sxs-lookup"><span data-stu-id="7699b-159">Here is an example in which a Microsoft 365 tenant was moved from the European Union (EU) datacenter geo to the one located in the United Kingdom (UK).</span></span>

![Voorbeeld van het verplaatsen van een Microsoft 365-tenant tussen datacenters](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

<span data-ttu-id="7699b-161">Zie Kerngegevens verplaatsen naar nieuwe geografische datacenters in [Microsoft 365 voor meer informatie.](../enterprise/moving-data-to-new-datacenter-geos.md)</span><span class="sxs-lookup"><span data-stu-id="7699b-161">For more information, see [Moving core data to new Microsoft 365 datacenter geos](../enterprise/moving-data-to-new-datacenter-geos.md).</span></span>

## <a name="products-and-licenses-for-a-tenant"></a><span data-ttu-id="7699b-162">Producten en licenties voor een tenant</span><span class="sxs-lookup"><span data-stu-id="7699b-162">Products and licenses for a tenant</span></span>

<span data-ttu-id="7699b-163">Uw Microsoft 365-tenant wordt gemaakt wanneer u uw eerste product koopt, zoals Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="7699b-163">Your Microsoft 365 tenant gets created when you purchase your first product, such as Microsoft 365 E3.</span></span> <span data-ttu-id="7699b-164">Naast het product zijn licenties, waarvoor een maandelijks of jaarlijks bedrag in rekening wordt gebracht.</span><span class="sxs-lookup"><span data-stu-id="7699b-164">Along with the product are licenses, which are charged a monthly or annual fee.</span></span> <span data-ttu-id="7699b-165">Een beheerder wijst vervolgens een beschikbare licentie van een van uw producten toe aan een gebruikersaccount, rechtstreeks of via groepslidmaatschap.</span><span class="sxs-lookup"><span data-stu-id="7699b-165">An administrator then assigns an available license from one of your products to a user account, either directly or through group membership.</span></span> <span data-ttu-id="7699b-166">Afhankelijk van de zakelijke behoeften van uw organisatie, hebt u mogelijk een set producten met elk een eigen groep licenties.</span><span class="sxs-lookup"><span data-stu-id="7699b-166">Depending on your organization's business needs, you might have a set of products, each with their own pool of licenses.</span></span> 

<span data-ttu-id="7699b-167">Voor het bepalen van de set producten en het aantal licenties voor elke set moet u enkele planningen maken:</span><span class="sxs-lookup"><span data-stu-id="7699b-167">Determining the set of products and the number of licenses for each requires some planning to:</span></span>

- <span data-ttu-id="7699b-168">Zorg ervoor dat u voldoende licenties hebt voor de gebruikersaccounts die geavanceerde functies nodig hebben.</span><span class="sxs-lookup"><span data-stu-id="7699b-168">Ensure you have enough licenses for the user accounts that need advanced features.</span></span>
- <span data-ttu-id="7699b-169">Voorkomen dat uw licenties op lopen of te veel niet-toegewezen licenties hebben, op basis van wijzigingen in de personeelsbeplaatsing in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="7699b-169">Prevent you from running out of licenses or having too many unassigned licenses, based on changes in staffing at your organization.</span></span>


## <a name="results-of-step-1"></a><span data-ttu-id="7699b-170">Resultaten van stap 1</span><span class="sxs-lookup"><span data-stu-id="7699b-170">Results of Step 1</span></span>

<span data-ttu-id="7699b-171">Voor uw Microsoft 365 voor enterprise-tenants hebt u het volgende bepaald:</span><span class="sxs-lookup"><span data-stu-id="7699b-171">For your Microsoft 365 for enterprise tenants, you have determined:</span></span>

- <span data-ttu-id="7699b-172">Hoeveel tenants u hebt of nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="7699b-172">How many tenants you have or need.</span></span>
- <span data-ttu-id="7699b-173">Voor elke tenant moeten de producten en licenties worden gekocht.</span><span class="sxs-lookup"><span data-stu-id="7699b-173">For each tenant, which products and licenses must be purchased.</span></span>
- <span data-ttu-id="7699b-174">Of een tenant multige geo moet zijn om te voldoen aan de vereisten voor gegevenslocatie.</span><span class="sxs-lookup"><span data-stu-id="7699b-174">Whether a tenant needs to be Multi-Geo to comply with data residency requirements.</span></span>
- <span data-ttu-id="7699b-175">Of u samenwerking tussen tenants moet instellen.</span><span class="sxs-lookup"><span data-stu-id="7699b-175">Whether you need to set up inter-tenant collaboration.</span></span>
- <span data-ttu-id="7699b-176">Of u de ene tenant naar de andere wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="7699b-176">Whether you need to migrate one tenant to another.</span></span>
- <span data-ttu-id="7699b-177">Of u kerngegevens moet verplaatsen van een geo datacenter naar een nieuwe datacenter.</span><span class="sxs-lookup"><span data-stu-id="7699b-177">Whether you need to move core data from one datacenter geo to new one.</span></span>

<span data-ttu-id="7699b-178">Hier is een voorbeeld van een nieuwe tenant.</span><span class="sxs-lookup"><span data-stu-id="7699b-178">Here is an example of a new tenant.</span></span>

![Voorbeeld van een nieuwe tenant](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

<span data-ttu-id="7699b-180">In deze afbeelding heeft de tenant:</span><span class="sxs-lookup"><span data-stu-id="7699b-180">In this illustration, the tenant has:</span></span>

- <span data-ttu-id="7699b-181">Een standaardlocatie die overeenkomt met een geografische locatie in het Microsoft 365-datacenter.</span><span class="sxs-lookup"><span data-stu-id="7699b-181">A default location corresponding to a Microsoft 365 datacenter geo.</span></span>
- <span data-ttu-id="7699b-182">Een set producten en licenties.</span><span class="sxs-lookup"><span data-stu-id="7699b-182">A set of products and licenses.</span></span>
- <span data-ttu-id="7699b-183">De set cloudproductiviteitsapps, waarvan sommige specifiek zijn voor producten.</span><span class="sxs-lookup"><span data-stu-id="7699b-183">The set of cloud productivity apps, some of which are specific to products.</span></span>
- <span data-ttu-id="7699b-184">Een Azure AD-tenant met globale beheerdersaccounts en een initiële DNS-domeinnaam.</span><span class="sxs-lookup"><span data-stu-id="7699b-184">An Azure AD tenant that contains global administrator accounts and an initial DNS domain name.</span></span>

<span data-ttu-id="7699b-185">Terwijl we verder gaan met de extra stappen van deze oplossing, bouwen we deze afbeelding uit.</span><span class="sxs-lookup"><span data-stu-id="7699b-185">As we move through the additional steps of this solution, we will build out this figure.</span></span>

## <a name="ongoing-maintenance-for-tenants"></a><span data-ttu-id="7699b-186">Doorlopend onderhoud voor tenants</span><span class="sxs-lookup"><span data-stu-id="7699b-186">Ongoing maintenance for tenants</span></span>

<span data-ttu-id="7699b-187">Oplopende basis moet u mogelijk het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="7699b-187">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="7699b-188">Voeg een nieuwe tenant toe.</span><span class="sxs-lookup"><span data-stu-id="7699b-188">Add a new tenant.</span></span>
- <span data-ttu-id="7699b-189">Nieuwe producten toevoegen aan een tenant met een eerste aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="7699b-189">Add new products to a tenant with an initial number of licenses.</span></span>
- <span data-ttu-id="7699b-190">Wijzig de set licenties voor een product in een tenant om de personeelsvereisten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="7699b-190">Change the set of licenses for a product in a tenant to adjust for changing staff requirements.</span></span>
- <span data-ttu-id="7699b-191">Verplaats de kerngegevens van een tenant naar een nieuwe geografische locatie in het datacenter.</span><span class="sxs-lookup"><span data-stu-id="7699b-191">Move your core data from a tenant to a new datacenter geo location.</span></span>
- <span data-ttu-id="7699b-192">Voeg Multi-Geo toe voor vereisten voor het opslaan van gegevens.</span><span class="sxs-lookup"><span data-stu-id="7699b-192">Add Multi-Geo for data residency requirements.</span></span>
- <span data-ttu-id="7699b-193">Samenwerking tussen tenants instellen.</span><span class="sxs-lookup"><span data-stu-id="7699b-193">Set up inter-tenant collaboration.</span></span>

## <a name="next-step"></a><span data-ttu-id="7699b-194">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="7699b-194">Next step</span></span>

<span data-ttu-id="7699b-195">[![Stap 2. Uw tenant optimaliseren voor netwerk voor toegang](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span><span class="sxs-lookup"><span data-stu-id="7699b-195">[![Step 2. Optimize your tenant for network for access](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)</span></span>

<span data-ttu-id="7699b-196">Ga door [met netwerken](tenant-management-networking.md) om optimale netwerken van uw collega's en Microsoft 365-cloudservices te bieden.</span><span class="sxs-lookup"><span data-stu-id="7699b-196">Continue with [networking](tenant-management-networking.md) to provide optimal networking from your workers to Microsoft 365 cloud services.</span></span>
