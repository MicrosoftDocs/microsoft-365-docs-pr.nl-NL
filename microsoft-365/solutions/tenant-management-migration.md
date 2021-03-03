---
title: Stap 4. Migratie voor uw Microsoft 365-tenants voor ondernemingen
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
description: Migreert uw Windows-apparaten, Office-client-apps en Office-servers voor uw Microsoft 365-tenants.
ms.openlocfilehash: 85f1c0d927b881c4d1526ce538ae54f5954a0664
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406358"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="617fb-104">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="617fb-104">Step 4.</span></span> <span data-ttu-id="617fb-105">Migratie voor uw Microsoft 365-tenants voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="617fb-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="617fb-106">De meeste ondernemingen hebben een heterogene omgeving met meerdere versies van besturingssystemen, clientsoftware en serversoftware.</span><span class="sxs-lookup"><span data-stu-id="617fb-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="617fb-107">Microsoft 365 voor Ondernemingen bevat de veiligste versies van de belangrijkste onderdelen van uw IT-infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="617fb-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="617fb-108">Het bevat ook productiviteitsfuncties die zijn ontworpen om te profiteren van cloudtechnologieën.</span><span class="sxs-lookup"><span data-stu-id="617fb-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="617fb-109">Als u de zakelijke waarde van de geïntegreerde suite met Microsoft 365 enterprise-producten wilt maximaliseren, begint u met het plannen en implementeren van een strategie voor het migreren van deze releases:</span><span class="sxs-lookup"><span data-stu-id="617fb-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="617fb-110">Van</span><span class="sxs-lookup"><span data-stu-id="617fb-110">From</span></span> | <span data-ttu-id="617fb-111">Naar</span><span class="sxs-lookup"><span data-stu-id="617fb-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="617fb-112">Windows 7 en Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="617fb-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="617fb-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="617fb-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="617fb-114">Office-clientproducten geïnstalleerd op de apparaten van de werknemer</span><span class="sxs-lookup"><span data-stu-id="617fb-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="617fb-115">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="617fb-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="617fb-116">Office Server-producten geïnstalleerd op on-premises servers</span><span class="sxs-lookup"><span data-stu-id="617fb-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="617fb-117">De overeenkomstige cloudservices in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="617fb-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="617fb-118">Migreren naar Windows 10</span><span class="sxs-lookup"><span data-stu-id="617fb-118">Migrating to Windows 10</span></span>

<span data-ttu-id="617fb-119">Elke Microsoft 365 Enterprise-licentie bevat een licentie voor Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="617fb-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="617fb-120">Als u uw apparaten met Windows 7 of Windows 8.1 wilt migreren, kunt u een in-place upgrade uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="617fb-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="617fb-121">Ondersteuning voor Windows 7 is beëindigd op *14 januari 2020.*</span><span class="sxs-lookup"><span data-stu-id="617fb-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="617fb-122">Zie windows 10-implementatiescenario's voor aanvullende methoden voor het installeren van Windows [10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios)Enterprise voorbij een in-place upgrade.</span><span class="sxs-lookup"><span data-stu-id="617fb-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="617fb-123">U kunt ook zelf [de implementatie van Windows 10 plannen](https://aka.ms/planforwin10deployment).</span><span class="sxs-lookup"><span data-stu-id="617fb-123">You can also [plan for Windows 10 deployment](https://aka.ms/planforwin10deployment) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="617fb-124">Migreren naar Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="617fb-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="617fb-125">Microsoft 365 voor ondernemingen omvat Microsoft 365-apps voor ondernemingen, een versie van de Office-clientproducten (Word, PowerPoint, Excel en Outlook) die wordt geïnstalleerd en bijgewerkt vanuit de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="617fb-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="617fb-126">Zie Voor meer informatie over [Microsoft 365-apps voor ondernemingen.](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="617fb-126">For more information, see [About Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="617fb-127">In plaats van de computers actueel te houden voor Office 2019 of oudere versies, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="617fb-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="617fb-128">Haal een Microsoft 365-licentie op en wijs deze toe voor uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="617fb-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="617fb-129">Verwijder Office 2013 of Office 2016 van hun computers.</span><span class="sxs-lookup"><span data-stu-id="617fb-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="617fb-130">Installeer Microsoft 365 Apps voor ondernemingen afzonderlijk of tijdens een IT-implementatie.</span><span class="sxs-lookup"><span data-stu-id="617fb-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="617fb-131">Zie de implementatiehandleiding [voor Microsoft 365-apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="617fb-131">For more information, see [Deployment guide for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="617fb-132">Microsoft 365 Apps voor ondernemingen installeert beveiligingsupdates en nieuwe functie-updates automatisch en kan profiteren van cloudservices in Microsoft 365 voor betere beveiliging en productiviteit.</span><span class="sxs-lookup"><span data-stu-id="617fb-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="617fb-133">On-premises servers en gegevens migreren naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="617fb-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="617fb-134">Microsoft 365 voor Ondernemingen bevat cloudversies van Office-serverservices die gebruikmaken van een aantal dezelfde hulpprogramma's als on-premises versies van Office Server-software, zoals webbrowsers en de Outlook-client.</span><span class="sxs-lookup"><span data-stu-id="617fb-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="617fb-135">Deze cloudservices worden automatisch bijgewerkt voor beveiliging en nieuwe functies.</span><span class="sxs-lookup"><span data-stu-id="617fb-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="617fb-136">Na de migratie kan uw IT-afdeling de tijd besparen die nodig is om on-premises servers te onderhouden en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="617fb-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="617fb-137">Gebruik de volgende bronnen voor informatie over het migreren van gebruikers en gegevens voor specifieke Microsoft 365-werkbelastingen:</span><span class="sxs-lookup"><span data-stu-id="617fb-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="617fb-138">Postvakken verplaatsen van on-premises Exchange Server naar Exchange Online</span><span class="sxs-lookup"><span data-stu-id="617fb-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](https://docs.microsoft.com/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="617fb-139">SharePoint-gegevens migreren van SharePoint Server naar SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="617fb-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="617fb-140">Skype voor Bedrijven Online migreren naar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="617fb-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="617fb-141">Uw hele organisatie overzetten</span><span class="sxs-lookup"><span data-stu-id="617fb-141">Transition your entire organization</span></span>

<span data-ttu-id="617fb-142">Download deze overgangsposter voor een beter beeld van hoe u uw hele organisatie kunt verplaatsen naar de producten en services in Microsoft 365 enterprise:</span><span class="sxs-lookup"><span data-stu-id="617fb-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="617fb-143">[![Afbeelding met de poster Overgang naar Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="617fb-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="617fb-144">Deze poster van twee pagina‘s is een snelle manier om de bestaande infrastructuur te inventariseren.</span><span class="sxs-lookup"><span data-stu-id="617fb-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="617fb-145">Gebruik deze voor hulp bij het over overstapen naar een product of service in Microsoft 365 voor Ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="617fb-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="617fb-146">Het toont Windows- en Office-producten en andere infrastructuur- en beveiligingselementen, zoals apparaatbeheer, identiteits- en bedreigingsbescherming, en informatiebescherming en naleving.</span><span class="sxs-lookup"><span data-stu-id="617fb-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="617fb-147">Resultaten van stap 4</span><span class="sxs-lookup"><span data-stu-id="617fb-147">Results of Step 4</span></span>

<span data-ttu-id="617fb-148">Voor de migratie van uw Microsoft 365-tenant hebt u het volgende bepaald:</span><span class="sxs-lookup"><span data-stu-id="617fb-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="617fb-149">Op welke apparaten Windows 7 of Windows 8.1 wordt uitgevoerd en van plan zijn deze bij te werken naar Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="617fb-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="617fb-150">Op welke apparaten de Office-client-apps worden uitgevoerd en welke van plan zijn ze bij te werken naar Microsoft 365-apps voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="617fb-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="617fb-151">Welke on-premises Office-serverservices moeten worden gemigreerd naar het equivalent van Microsoft 365 en welke services en hun gegevens moeten worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="617fb-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="617fb-152">Hier is een voorbeeld van een tenant met een voltooide migratie van on-premises servers.</span><span class="sxs-lookup"><span data-stu-id="617fb-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Voorbeeld van een tenant met een voltooide migratie van on-premises servers](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="617fb-154">In deze afbeelding heeft de organisatie het volgende:</span><span class="sxs-lookup"><span data-stu-id="617fb-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="617fb-155">De on-premises Exchange Server-postvakken zijn gemigreerd naar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="617fb-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="617fb-156">De on-premises SharePoint Server-sites en -gegevens zijn gemigreerd naar SharePoint in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="617fb-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="617fb-157">Doorlopend onderhoud voor migratie</span><span class="sxs-lookup"><span data-stu-id="617fb-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="617fb-158">Oplopende basis moet u mogelijk het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="617fb-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="617fb-159">Afhankelijk van de status van de migratie van uw Exchange-postvak, blijft u de overgang naar Exchange Online naar uw organisatie rollen.</span><span class="sxs-lookup"><span data-stu-id="617fb-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="617fb-160">Afhankelijk van de status van de migratie van uw on-premises SharePoint-site, blijft u de overgang naar SharePoint in Microsoft 365 naar uw organisatie rollen.</span><span class="sxs-lookup"><span data-stu-id="617fb-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="617fb-161">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="617fb-161">Next step</span></span>

<span data-ttu-id="617fb-162">[![Stap 5. Apparaat- en app-beheer implementeren](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="617fb-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="617fb-163">Ga verder [met apparaat- en app-beheer](tenant-management-device-management.md) om apparaat- en app-beheer te implementeren.</span><span class="sxs-lookup"><span data-stu-id="617fb-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>
