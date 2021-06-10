---
title: Stap 4. Migratie voor uw Microsoft 365 voor enterprise tenants
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
description: Migreert Windows apparaten, Office client-apps en Office servers voor uw Microsoft 365 tenants.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929142"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a><span data-ttu-id="d6aec-104">Stap 4.</span><span class="sxs-lookup"><span data-stu-id="d6aec-104">Step 4.</span></span> <span data-ttu-id="d6aec-105">Migratie voor uw Microsoft 365 voor enterprise tenants</span><span class="sxs-lookup"><span data-stu-id="d6aec-105">Migration for your Microsoft 365 for enterprise tenants</span></span>

<span data-ttu-id="d6aec-106">De meeste ondernemingsorganisaties hebben een heterogene omgeving met meerdere versies van besturingssystemen, clientsoftware en serversoftware.</span><span class="sxs-lookup"><span data-stu-id="d6aec-106">Most enterprise organizations have a heterogeneous environment that includes multiple releases of operating systems, client software, and server software.</span></span> <span data-ttu-id="d6aec-107">Microsoft 365 voor bedrijven bevat de veiligste versies van de belangrijkste onderdelen van uw IT-infrastructuur.</span><span class="sxs-lookup"><span data-stu-id="d6aec-107">Microsoft 365 for enterprise includes the most secure versions of the key components of your IT infrastructure.</span></span> <span data-ttu-id="d6aec-108">Het bevat ook productiviteitsfuncties die zijn ontworpen om te profiteren van cloudtechnologieën.</span><span class="sxs-lookup"><span data-stu-id="d6aec-108">It also includes productivity features that are designed to take advantage of cloud technologies.</span></span>

<span data-ttu-id="d6aec-109">Als u de zakelijke waarde van de Microsoft 365 geïntegreerde suite met producten voor ondernemingen wilt maximaliseren, begint u met het plannen en implementeren van een strategie om deze releases te migreren:</span><span class="sxs-lookup"><span data-stu-id="d6aec-109">To maximize the business value of the Microsoft 365 for enterprise integrated suite of products, begin planning and implementing a strategy to migrate these releases:</span></span>

| <span data-ttu-id="d6aec-110">Van</span><span class="sxs-lookup"><span data-stu-id="d6aec-110">From</span></span> | <span data-ttu-id="d6aec-111">Naar</span><span class="sxs-lookup"><span data-stu-id="d6aec-111">To</span></span> |
|:-------|:-----|
| <span data-ttu-id="d6aec-112">Windows 7 en Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d6aec-112">Windows 7 and Windows 8.1</span></span> | <span data-ttu-id="d6aec-113">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="d6aec-113">Windows 10 Enterprise</span></span> |
| <span data-ttu-id="d6aec-114">Office clientproducten geïnstalleerd op de apparaten van uw werknemer</span><span class="sxs-lookup"><span data-stu-id="d6aec-114">Office client products installed on your worker's devices</span></span> | <span data-ttu-id="d6aec-115">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d6aec-115">Microsoft 365 Apps for enterprise</span></span> |
| <span data-ttu-id="d6aec-116">Office serverproducten geïnstalleerd op on-premises servers</span><span class="sxs-lookup"><span data-stu-id="d6aec-116">Office server products installed on on-premises servers</span></span> | <span data-ttu-id="d6aec-117">Hun equivalente cloudservices in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6aec-117">Their equivalent cloud-based services in Microsoft 365</span></span> |
|  |  |

## <a name="migrating-to-windows-10"></a><span data-ttu-id="d6aec-118">Migreren naar Windows 10</span><span class="sxs-lookup"><span data-stu-id="d6aec-118">Migrating to Windows 10</span></span>

<span data-ttu-id="d6aec-119">Elke Microsoft 365 voor ondernemingslicentie bevat een licentie voor Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d6aec-119">Each Microsoft 365 for enterprise license includes a license for Windows 10 Enterprise.</span></span> <span data-ttu-id="d6aec-120">Als u uw apparaten wilt migreren die Windows 7 of Windows 8.1 uitvoeren, kunt u een in-place upgrade uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="d6aec-120">To migrate your devices that run Windows 7 or Windows 8.1, you can do an in-place upgrade.</span></span> <span data-ttu-id="d6aec-121">De ondersteuning is beëindigd Windows 7 *januari 2020*.</span><span class="sxs-lookup"><span data-stu-id="d6aec-121">Support ended for Windows 7 on *January 14, 2020*.</span></span> 

<span data-ttu-id="d6aec-122">Zie voor aanvullende methoden voor het installeren Windows 10 Enterprise meer dan een in-place upgrade, [Windows 10 implementatiescenario's.](/windows/deployment/windows-10-deployment-scenarios)</span><span class="sxs-lookup"><span data-stu-id="d6aec-122">For additional methods of installing Windows 10 Enterprise beyond an in-place upgrade, see [Windows 10 deployment scenarios](/windows/deployment/windows-10-deployment-scenarios).</span></span> <span data-ttu-id="d6aec-123">U kunt ook zelf [de implementatie van Windows 10 plannen](/windows/deployment/planning/).</span><span class="sxs-lookup"><span data-stu-id="d6aec-123">You can also [plan for Windows 10 deployment](/windows/deployment/planning/) on your own.</span></span>

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="d6aec-124">Migreren naar Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="d6aec-124">Migrating to Microsoft 365 Apps for enterprise</span></span>

<span data-ttu-id="d6aec-125">Microsoft 365 voor bedrijven bevat Microsoft 365-apps voor ondernemingen, een versie van de Office-clientproducten (Word, PowerPoint, Excel en Outlook) die is geïnstalleerd en bijgewerkt vanuit de Microsoft-cloud.</span><span class="sxs-lookup"><span data-stu-id="d6aec-125">Microsoft 365 for enterprise includes Microsoft 365 Apps for enterprise, a version of the Office client products (Word, PowerPoint, Excel, and Outlook) that is installed and updated from the Microsoft cloud.</span></span> <span data-ttu-id="d6aec-126">Zie Info over [Microsoft 365-apps voor ondernemingen.](/deployoffice/about-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="d6aec-126">For more information, see [About Microsoft 365 Apps for enterprise](/deployoffice/about-microsoft-365-apps).</span></span>

<span data-ttu-id="d6aec-127">In plaats van uw computers actueel te houden voor Office 2019 of oudere versies, moet u de volgende stappen ondernemen:</span><span class="sxs-lookup"><span data-stu-id="d6aec-127">Rather than keeping your computers current for Office 2019 or older versions, take the following steps:</span></span>

1. <span data-ttu-id="d6aec-128">Een licentie voor Microsoft 365 gebruikers krijgen en toewijzen.</span><span class="sxs-lookup"><span data-stu-id="d6aec-128">Get and assign a Microsoft 365 license for your users.</span></span>
2. <span data-ttu-id="d6aec-129">Verwijder Office 2013 of Office 2016 op hun computers.</span><span class="sxs-lookup"><span data-stu-id="d6aec-129">Uninstall Office 2013 or Office 2016 on their computers.</span></span>
3. <span data-ttu-id="d6aec-130">Installeer Microsoft 365-apps voor ondernemingen, afzonderlijk of tijdens een IT-implementatie.</span><span class="sxs-lookup"><span data-stu-id="d6aec-130">Install Microsoft 365 Apps for enterprise, either individually or during an IT rollout.</span></span> <span data-ttu-id="d6aec-131">Zie Implementatiehandleiding [voor Microsoft 365-apps.](/deployoffice/deployment-guide-microsoft-365-apps)</span><span class="sxs-lookup"><span data-stu-id="d6aec-131">For more information, see [Deployment guide for Microsoft 365 Apps](/deployoffice/deployment-guide-microsoft-365-apps).</span></span>

<span data-ttu-id="d6aec-132">Microsoft 365-apps voor ondernemingen installeert zowel beveiligingsupdates als nieuwe functie-updates automatisch en kan profiteren van cloudservices in Microsoft 365 voor verbeterde beveiliging en productiviteit.</span><span class="sxs-lookup"><span data-stu-id="d6aec-132">Microsoft 365 Apps for enterprise installs both security updates and new feature updates automatically and can take advantage of cloud-based services in Microsoft 365 for enhanced security and productivity.</span></span>

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a><span data-ttu-id="d6aec-133">On-premises servers en gegevens migreren naar Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d6aec-133">Migrating on-premises servers and data to Microsoft 365</span></span>

<span data-ttu-id="d6aec-134">Microsoft 365 voor bedrijven bevat cloudversies van Office-serverservices die gebruikmaken van enkele van dezelfde hulpprogramma's als on-premises versies van Office-serversoftware, zoals webbrowsers en de Outlook client.</span><span class="sxs-lookup"><span data-stu-id="d6aec-134">Microsoft 365 for enterprise includes cloud-based versions of Office server services that use some of the same tools as on-premises versions of Office server software, such as web browsers and the Outlook client.</span></span> <span data-ttu-id="d6aec-135">Deze cloudservices worden automatisch bijgewerkt voor beveiliging en nieuwe functies.</span><span class="sxs-lookup"><span data-stu-id="d6aec-135">These cloud-based services are automatically updated for security and new features.</span></span> <span data-ttu-id="d6aec-136">Na de migratie kan uw IT-afdeling de tijd besparen die nodig is om on-premises servers te onderhouden en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="d6aec-136">After migration, your IT department can save the time it takes to maintain and update on-premises servers.</span></span>

<span data-ttu-id="d6aec-137">Gebruik de volgende bronnen voor informatie over het migreren van gebruikers en gegevens voor specifieke Microsoft 365 werkbelastingen:</span><span class="sxs-lookup"><span data-stu-id="d6aec-137">Use the following resources for information about migrating users and data for specific Microsoft 365 workloads:</span></span>

- [<span data-ttu-id="d6aec-138">Postvakken verplaatsen van on-premises Exchange Server naar Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d6aec-138">Move mailboxes from on-premises Exchange Server to Exchange Online</span></span>](/exchange/hybrid-deployment/move-mailboxes)
- [<span data-ttu-id="d6aec-139">Gegevens SharePoint van SharePoint Server migreren naar SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d6aec-139">Migrate SharePoint data from SharePoint Server to SharePoint Online</span></span>](/sharepointmigration/migrate-to-sharepoint-online)
- [<span data-ttu-id="d6aec-140">Online Skype voor Bedrijven migreren naar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6aec-140">Migrate Skype for Business Online to Microsoft Teams</span></span>](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a><span data-ttu-id="d6aec-141">Uw hele organisatie overzetten</span><span class="sxs-lookup"><span data-stu-id="d6aec-141">Transition your entire organization</span></span>

<span data-ttu-id="d6aec-142">Als u een beter beeld wilt krijgen van hoe u uw hele organisatie kunt verplaatsen naar de producten en services in Microsoft 365 voor bedrijven, downloadt u deze overgangsposter:</span><span class="sxs-lookup"><span data-stu-id="d6aec-142">To get a better picture of how to move your entire organization to the products and services in Microsoft 365 for enterprise, download this transition poster:</span></span>

<span data-ttu-id="d6aec-143">[![Afbeelding met de poster Overgang naar Microsoft 365 afbeelding.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span><span class="sxs-lookup"><span data-stu-id="d6aec-143">[![Image showing the Transition to Microsoft 365 poster.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)</span></span>

<span data-ttu-id="d6aec-144">Deze poster van twee pagina‘s is een snelle manier om de bestaande infrastructuur te inventariseren.</span><span class="sxs-lookup"><span data-stu-id="d6aec-144">This two-page poster is a quick way to inventory your existing infrastructure.</span></span> <span data-ttu-id="d6aec-145">Gebruik deze informatie om richtlijnen te krijgen voor het verplaatsen naar een product of service in Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="d6aec-145">Use it to get guidance for moving to a product or service in Microsoft 365 for enterprise.</span></span> <span data-ttu-id="d6aec-146">Het toont Windows en Office en andere infrastructuur- en beveiligingselementen, zoals apparaatbeheer, identiteits- en bedreigingsbeveiliging en informatiebeveiliging en compliance.</span><span class="sxs-lookup"><span data-stu-id="d6aec-146">It shows Windows and Office products and other infrastructure and security elements such as device management, identity and threat protection, and information protection and compliance.</span></span>

## <a name="results-of-step-4"></a><span data-ttu-id="d6aec-147">Resultaten van stap 4</span><span class="sxs-lookup"><span data-stu-id="d6aec-147">Results of Step 4</span></span>

<span data-ttu-id="d6aec-148">Voor migratie voor uw Microsoft 365 tenant hebt u het volgende bepaald:</span><span class="sxs-lookup"><span data-stu-id="d6aec-148">For migration for your Microsoft 365 tenant, you have determined:</span></span>

- <span data-ttu-id="d6aec-149">Welke apparaten worden uitgevoerd Windows 7 of Windows 8.1 en het plan om ze bij te werken naar Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d6aec-149">Which devices are running Windows 7 or Windows 8.1 and the plan to update them to Windows 10 Enterprise.</span></span>
- <span data-ttu-id="d6aec-150">Op welke apparaten worden de Office client-apps uitgevoerd en het plan om ze bij te werken Microsoft 365 apps voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="d6aec-150">Which devices are running the Office client apps and the plan to update them to Microsoft 365 apps for enterprise.</span></span>
- <span data-ttu-id="d6aec-151">Welke on-premises Office serverservices moeten worden gemigreerd naar hun Microsoft 365 equivalent en het plan om deze en hun gegevens te migreren.</span><span class="sxs-lookup"><span data-stu-id="d6aec-151">Which on-premises Office server services should be migrated to their Microsoft 365 equivalent and the plan to migrate them and their data.</span></span>

<span data-ttu-id="d6aec-152">Hier is een voorbeeld van een tenant met een voltooide migratie van on-premises servers.</span><span class="sxs-lookup"><span data-stu-id="d6aec-152">Here is an example of a tenant with a completed migration of on-premises servers.</span></span>

![Voorbeeld van een tenant met een voltooide migratie van on-premises servers](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

<span data-ttu-id="d6aec-154">In deze afbeelding heeft de organisatie:</span><span class="sxs-lookup"><span data-stu-id="d6aec-154">In this illustration, the organization has:</span></span>

- <span data-ttu-id="d6aec-155">De on-premises postvakken Exchange Server gemigreerd naar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d6aec-155">Migrated its on-premises Exchange Server mailboxes to Exchange Online.</span></span>
- <span data-ttu-id="d6aec-156">De on-premises SharePoint serversites en -gegevens gemigreerd naar SharePoint in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d6aec-156">Migrated its on-premises SharePoint Server sites and data to SharePoint in Microsoft 365.</span></span>

## <a name="ongoing-maintenance-for-migration"></a><span data-ttu-id="d6aec-157">Doorlopend onderhoud voor migratie</span><span class="sxs-lookup"><span data-stu-id="d6aec-157">Ongoing maintenance for migration</span></span>

<span data-ttu-id="d6aec-158">Op permanente basis moet u mogelijk het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="d6aec-158">On an ongoing basis, you might need to:</span></span>

- <span data-ttu-id="d6aec-159">Afhankelijk van de status van uw postvakmigratie Exchange de overgang naar Exchange Online naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d6aec-159">Depending on the state of your Exchange mailbox migration, continue rolling the transition to Exchange Online out to your organization.</span></span>
- <span data-ttu-id="d6aec-160">Afhankelijk van de status van uw on-premises SharePoint sitemigratie, blijft u de overgang naar SharePoint in Microsoft 365 naar uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d6aec-160">Depending on the state of your on-premises SharePoint site migration, continue rolling the transition to SharePoint in Microsoft 365 out to your organization.</span></span>

## <a name="next-step"></a><span data-ttu-id="d6aec-161">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="d6aec-161">Next step</span></span>

<span data-ttu-id="d6aec-162">[![Stap 5. Apparaat- en app-beheer implementeren](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span><span class="sxs-lookup"><span data-stu-id="d6aec-162">[![Step 5. Deploy device and app management](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)</span></span>

<span data-ttu-id="d6aec-163">Ga verder [met apparaat- en app-beheer](tenant-management-device-management.md) om apparaat- en app-beheer te implementeren.</span><span class="sxs-lookup"><span data-stu-id="d6aec-163">Continue with [device and app management](tenant-management-device-management.md) to deploy device and app management.</span></span>