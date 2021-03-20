---
title: 'Google-bestanden migreren naar Microsoft 365 voor Bedrijven '
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het migreren van Google-bestanden naar Microsoft 365 voor Bedrijven met behulp van Mover.
ms.openlocfilehash: 6feabff7e36e84f7dba56e74333648325cf43920
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913572"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="aceb4-103">Google-bestanden migreren naar Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="aceb4-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="aceb4-104">Wanneer u naar Microsoft 365 voor Bedrijven gaat, wilt u uw bestanden migreren vanuit Google Drive.</span><span class="sxs-lookup"><span data-stu-id="aceb4-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="aceb4-105">U kunt de Mover-app gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations.</span><span class="sxs-lookup"><span data-stu-id="aceb4-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="aceb4-106">Zie [Mover Cloud Migration](/sharepointmigration/mover-plan-migration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aceb4-106">For more information, see [Mover Cloud Migration](/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="aceb4-107">Mover maakt een kopie van de bestanden en verplaatst de kopieën naar Microsoft 365 voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="aceb4-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="aceb4-108">De oorspronkelijke bestanden blijven ook in Google Drives.</span><span class="sxs-lookup"><span data-stu-id="aceb4-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="aceb4-109">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="aceb4-109">Before you start</span></span>

<span data-ttu-id="aceb4-110">Alle gebruikers moeten zich hebben aangemeld bij Microsoft 365 voor Bedrijven en hun OneDrive voor Bedrijven hebben ingesteld.</span><span class="sxs-lookup"><span data-stu-id="aceb4-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="aceb4-111">Hiervoor gaat u naar [office.com,](https://office.com)meld u aan met uw microsoft 365 voor bedrijven-referenties en kiest u Vervolgens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="aceb4-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="aceb4-112">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="aceb4-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="aceb4-113">Mover installeren</span><span class="sxs-lookup"><span data-stu-id="aceb4-113">Install Mover</span></span>

1. <span data-ttu-id="aceb4-114">Meld u aan bij uw Google Workspace-beheerconsole [op admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="aceb4-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="aceb4-115">Kies **Apps**  >  **Google Workspace Marketplace-apps** App toevoegen aan lijst domein  >  **installeren**.</span><span class="sxs-lookup"><span data-stu-id="aceb4-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="aceb4-116">Zoek naar Mover en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="aceb4-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="aceb4-117">Kies **Domein installeren** en ga vervolgens **door.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="aceb4-118">Controleer de machtigingen, schakel het selectievakje in om akkoord te gaan met de voorwaarden en selecteer vervolgens Toestaan **,** kies **Volgende** en vervolgens **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="aceb4-119">Verbindingslijnen maken en de migratie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="aceb4-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="aceb4-120">Ga terug **naar Google Workspace Marketplace-apps.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="aceb4-121">Vernieuw uw browser en selecteer de **Mover-app.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="aceb4-122">Schuif omlaag en kies de universele navigatiekoppeling.</span><span class="sxs-lookup"><span data-stu-id="aceb4-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="aceb4-123">Selecteer **Nieuwe verbindingslijn machtigen,** **zoek G Suite (beheerder)** en kies **Machtigen.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="aceb4-124">Wijzig de **weergavenaam**, als u wilt, en selecteer vervolgens **Autor.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="aceb4-125">Kies een Google-beheerdersaccount, controleer de machtigingen en selecteer **Vervolgens Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="aceb4-126">Mover geeft het aantal teamstations en gebruikersstations weer dat is gevonden.</span><span class="sxs-lookup"><span data-stu-id="aceb4-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="aceb4-127">Kies **onder Doel selecteren** de optie Nieuwe **verbindingslijn machtigen**, zoek **Office 365** en selecteer **Autor.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="aceb4-128">Als u machtigingen wilt verlenen voor de Mover-app in uw Azure Active Directory, gaat u naar [aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="aceb4-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="aceb4-129">Selecteer **Office 365 Mover**, **Machtigingen**, **Beheerders toestemming geven voor uw bedrijf**.</span><span class="sxs-lookup"><span data-stu-id="aceb4-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="aceb4-130">Kies uw account, controleer de machtigingen en selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="aceb4-131">Kies **Eigenschappen** en controleer of **gebruikerstoewijzing** vereist is? is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="aceb4-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="aceb4-132">Ga terug naar de Mover-app, wijzig de **weergavenaam**, kies indien u wilt Autor toestemming **en** selecteer vervolgens een Microsoft-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="aceb4-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="aceb4-133">Mover informeert u over het aantal SharePoint Online-sites (of SPO)-sites en gebruikers dat is gevonden.</span><span class="sxs-lookup"><span data-stu-id="aceb4-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="aceb4-134">Kies **Doorgaan met migratie-instelling,** **selecteer Gebruikers toevoegen** en vervolgens Gebruikers automatisch ontdekken en **toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="aceb4-135">De Mover-app probeert stations van het bronpad in Google toe te wijden aan het doelpad in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="aceb4-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="aceb4-136">Als een station niet automatisch wordt uitgedeeld, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="aceb4-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="aceb4-137">In dit geval hebben we een SharePoint-site met de naam Gemigreerde bestanden toegevoegd en hebben we kennis genomen van de URL voor de pagina documenten.</span><span class="sxs-lookup"><span data-stu-id="aceb4-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="aceb4-138">Vervolgens hebben we een CSV-bestand gemaakt met de indeling Bronpad, Doelpad en Tags.</span><span class="sxs-lookup"><span data-stu-id="aceb4-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="aceb4-139">Zie voor meer [informatie aka.ms/movercsv.](/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="aceb4-139">For details see [aka.ms/movercsv](/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="aceb4-140">Wanneer u de URL van het doelpad toevoegt, verwijdert u alles na Gedeelde documenten.</span><span class="sxs-lookup"><span data-stu-id="aceb4-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="aceb4-141">Deze volledige URL werkt bijvoorbeeld niet: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="aceb4-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="aceb4-142">Wijzig het in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="aceb4-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="aceb4-143">Zodra uw CSV-bestand gereed is, selecteert u **Migratieacties**, **Toevoegen aan migratie**, Kies een bestand dat u wilt **uploaden**.</span><span class="sxs-lookup"><span data-stu-id="aceb4-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="aceb4-144">Ga naar het CSV-bestand, selecteer het bestand en kies **Openen.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="aceb4-145">Selecteer de gebruikersstations waarvan u de bestanden wilt migreren en kies **Vervolgens Migrerende gebruikers starten.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="aceb4-146">Controleer de migratiegegevens, kies wanneer u de migratie wilt starten, ga akkoord met de Voorwaarden **en** selecteer **doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="aceb4-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="aceb4-147">De Mover-app informeert u wanneer het migratieproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="aceb4-147">The Mover app will inform you when the migration process is complete.</span></span>