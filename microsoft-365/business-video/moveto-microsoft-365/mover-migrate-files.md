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
description: Lees hoe u Google-bestanden migreert naar Microsoft 365 voor Bedrijven met behulp van Mover.
ms.openlocfilehash: 72ea81ad86a20e01b4650915fef96a713b207c3b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166157"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="119db-103">Google-bestanden migreren naar Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="119db-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="119db-104">Wanneer u overstapt op Microsoft 365 voor Bedrijven, wilt u uw bestanden migreren vanuit Google Drive.</span><span class="sxs-lookup"><span data-stu-id="119db-104">When you move to Microsoft 365 for business, you'll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="119db-105">U kunt de app Mover gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations.</span><span class="sxs-lookup"><span data-stu-id="119db-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="119db-106">Zie [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="119db-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="119db-107">Mover maakt een kopie van de bestanden en verplaatst de kopieën naar Microsoft 365 voor Bedrijven.</span><span class="sxs-lookup"><span data-stu-id="119db-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="119db-108">De oorspronkelijke bestanden blijven ook in Google Drives behouden.</span><span class="sxs-lookup"><span data-stu-id="119db-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="119db-109">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="119db-109">Before you start</span></span>

<span data-ttu-id="119db-110">Alle gebruikers moeten zich hebben aangemeld bij Microsoft 365 voor Bedrijven en hun OneDrive voor Bedrijven hebben ingesteld.</span><span class="sxs-lookup"><span data-stu-id="119db-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="119db-111">U doet dit door naar de [office.com,](https://office.com)u aan te melden met uw referenties voor Microsoft 365 voor Bedrijven en vervolgens OneDrive te kiezen.</span><span class="sxs-lookup"><span data-stu-id="119db-111">To do this, go to [office.com](https://office.com), sign in with your Microsoft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="119db-112">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="119db-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="119db-113">Mover installeren</span><span class="sxs-lookup"><span data-stu-id="119db-113">Install Mover</span></span>

1. <span data-ttu-id="119db-114">Meld u aan bij de beheerconsole van Google Workspace [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="119db-114">Sign in to your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="119db-115">Kies **Apps**  >  **Google Workspace Marketplace-apps** App toevoegen aan de lijst voor het installeren van  >  **domeinen.**</span><span class="sxs-lookup"><span data-stu-id="119db-115">Choose **Apps** > **Google Workspace Marketplace apps** > **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="119db-116">Zoek naar Mover en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="119db-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="119db-117">Kies **Domein installeren** en vervolgens **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="119db-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="119db-118">Controleer de machtigingen, schakel het selectievakje in om akkoord te gaan met de voorwaarden, selecteer Vervolgens **Toestaan,** **kies Volgende** en vervolgens **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="119db-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="119db-119">Connectors maken en de migratie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="119db-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="119db-120">Ga terug **naar De Marketplace-apps van Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="119db-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="119db-121">Vernieuw uw browser en selecteer de **Mover-app.**</span><span class="sxs-lookup"><span data-stu-id="119db-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="119db-122">Schuif omlaag en kies de universele navigatiekoppeling.</span><span class="sxs-lookup"><span data-stu-id="119db-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="119db-123">Selecteer **Nieuwe connector autor toestemming geven,** zoek **G Suite (beheer)** en kies **Autorbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="119db-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="119db-124">Wijzig indien **nodig de weergavenaam** en selecteer **Autor.**</span><span class="sxs-lookup"><span data-stu-id="119db-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="119db-125">Kies een Google-beheerdersaccount, controleer de machtigingen en selecteer **Toestaan.**</span><span class="sxs-lookup"><span data-stu-id="119db-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="119db-126">Mover geeft het aantal teamstations en gebruikersstations weer dat is gevonden.</span><span class="sxs-lookup"><span data-stu-id="119db-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="119db-127">Kies **onder Bestemming selecteren** Nieuwe connector **autor elke** keer, zoek Office **365** en selecteer **Autor.**</span><span class="sxs-lookup"><span data-stu-id="119db-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="119db-128">Als u machtigingen wilt verlenen aan de Mover-app in uw Azure Active Directory, gaat u [naar aka.ms/Office365MoverAuth.](https://aka.ms/Office365MoverAuth)</span><span class="sxs-lookup"><span data-stu-id="119db-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="119db-129">Selecteer **Office 365 Mover,** **Machtigingen,** **beheermachtiging verlenen voor uw bedrijf.**</span><span class="sxs-lookup"><span data-stu-id="119db-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="119db-130">Kies uw account, controleer de machtigingen en selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="119db-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="119db-131">Kies **Eigenschappen en** controleer of **gebruikerstoewijzing** vereist is? is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="119db-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="119db-132">Ga terug naar de Mover-app, wijzig indien nodig de weergavenaam en selecteer een Microsoft-beheerdersaccount. </span><span class="sxs-lookup"><span data-stu-id="119db-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="119db-133">Mover informeert u over het aantal SharePoint Online-sites (of SPO-sites) en gebruikers dat is gevonden.</span><span class="sxs-lookup"><span data-stu-id="119db-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="119db-134">Kies **Doorgaan met migratie instellen,** selecteer Gebruikers **toevoegen** en vervolgens Gebruikers automatisch ontdekken **en toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="119db-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="119db-135">De Mover-app probeert stations uit het bronpad in Google toe te staan aan het doelpad in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="119db-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="119db-136">Als een station niet automatisch wordt weergegeven, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="119db-136">If a drive doesn't map automatically, add its destination path to a CSV file, which we'll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="119db-137">In dit geval hebben we een SharePoint-site met de naam Gemigreerde bestanden toegevoegd en een notitie gemaakt van de URL voor de pagina documenten.</span><span class="sxs-lookup"><span data-stu-id="119db-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="119db-138">Vervolgens hebben we een CSV-bestand gemaakt met de indeling bronpad, doelpad en tags.</span><span class="sxs-lookup"><span data-stu-id="119db-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="119db-139">Zie de aka.ms/movercsv voor [meer informatie.](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)</span><span class="sxs-lookup"><span data-stu-id="119db-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="119db-140">Wanneer u de URL van het doelpad toevoegt, verwijdert u alles na Gedeelde documenten.</span><span class="sxs-lookup"><span data-stu-id="119db-140">When adding the Destination Path URL, remove everything after Shared Documents.</span></span> <span data-ttu-id="119db-141">Deze volledige URL werkt bijvoorbeeld niet: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="119db-141">For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="119db-142">Wijzig deze in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="119db-142">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="119db-143">Wanneer het CSV-bestand klaar is, selecteert u **Migratieacties,** Toevoegen **aan migratie,** **Kies een bestand om te uploaden.**</span><span class="sxs-lookup"><span data-stu-id="119db-143">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="119db-144">Ga naar het CSV-bestand, selecteer dit en kies **Openen.**</span><span class="sxs-lookup"><span data-stu-id="119db-144">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="119db-145">Selecteer de stations van de gebruiker van wie u de bestanden wilt migreren en **kies Migratie van gebruikers starten.**</span><span class="sxs-lookup"><span data-stu-id="119db-145">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="119db-146">Controleer de migratiegegevens, kies wanneer u de migratie wilt starten, ga akkoord met de **algemene** voorwaarden en selecteer **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="119db-146">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="119db-147">De Mover-app laat u weten wanneer het migratieproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="119db-147">The Mover app will inform you when the migration process is complete.</span></span>
