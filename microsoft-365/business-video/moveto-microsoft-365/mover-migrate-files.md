---
title: 'Google-bestanden migreren naar Microsoft 365 voor bedrijven '
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
description: Informatie over het migreren van Google-bestanden naar Microsoft 365 voor bedrijven met behulp van de overzetten.
ms.openlocfilehash: a6f9dbf7803cb552c23b6c6abb13d13d6f3eda5d
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794599"
---
# <a name="migrate-google-files-to-microsoft-365-for-business"></a><span data-ttu-id="2cd79-103">Google-bestanden migreren naar Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="2cd79-103">Migrate Google files to Microsoft 365 for business</span></span> 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4MhaD?autoplay=false]

<span data-ttu-id="2cd79-104">Wanneer u overstapt op Microsoft 365 voor bedrijven, wilt u uw bestanden migreren van Google Drive.</span><span class="sxs-lookup"><span data-stu-id="2cd79-104">When you move to Microsoft 365 for business, you’ll want to migrate your files from Google Drive.</span></span> <span data-ttu-id="2cd79-105">U kunt de app voor de verhuizer gebruiken om bestanden te verplaatsen van persoonlijke en gedeelde stations.</span><span class="sxs-lookup"><span data-stu-id="2cd79-105">You can use the Mover app to move files from personal and shared Drives.</span></span> <span data-ttu-id="2cd79-106">Zie [migratie van cloud clouds](https://docs.microsoft.com/sharepointmigration/mover-plan-migration) voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="2cd79-106">For more information, see [Mover Cloud Migration](https://docs.microsoft.com/sharepointmigration/mover-plan-migration)</span></span>

> [!NOTE]
> <span data-ttu-id="2cd79-107">Met de overzetten maakt u een kopie van de bestanden en verplaatst u de kopieën naar Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="2cd79-107">Mover will make a copy of the files and move the copies to Microsoft 365 for business.</span></span> <span data-ttu-id="2cd79-108">De oorspronkelijke bestanden blijven ook in Google Drive.</span><span class="sxs-lookup"><span data-stu-id="2cd79-108">The original files will stay in Google Drives also.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="2cd79-109">Voordat u van start gaat</span><span class="sxs-lookup"><span data-stu-id="2cd79-109">Before you start</span></span>

<span data-ttu-id="2cd79-110">Alle gebruikers moeten zijn aangemeld bij Microsoft 365 voor bedrijven en hun OneDrive voor bedrijven instellen.</span><span class="sxs-lookup"><span data-stu-id="2cd79-110">All the users should have signed in to Microsoft 365 for business and set up their OneDrive for Business.</span></span> <span data-ttu-id="2cd79-111">Hiervoor gaat u naar [Office.com](https://office.com), meldt u zich aan met Microsft 365 for Business credentials en kies vervolgens OneDrive.</span><span class="sxs-lookup"><span data-stu-id="2cd79-111">To do this, go to [office.com](https://office.com), sign in with you Microsft 365 for business credentials, and then choose OneDrive.</span></span>

## <a name="try-it"></a><span data-ttu-id="2cd79-112">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="2cd79-112">Try it!</span></span>

### <a name="install-mover"></a><span data-ttu-id="2cd79-113">Installatie overdrijf</span><span class="sxs-lookup"><span data-stu-id="2cd79-113">Install Mover</span></span>

1. <span data-ttu-id="2cd79-114">Meld u aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="2cd79-114">Sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span>

1. <span data-ttu-id="2cd79-115">Kies **apps**, **apps voor Google Workspace** en vervolgens **app toevoegen aan de lijst voor installeren** van de domein.</span><span class="sxs-lookup"><span data-stu-id="2cd79-115">Choose **Apps**, **Google Workspace Marketplace apps**, Then **Add app to Domain Install list**.</span></span>

1. <span data-ttu-id="2cd79-116">Zoek de Verhuizer en selecteer deze.</span><span class="sxs-lookup"><span data-stu-id="2cd79-116">Search for Mover and select it.</span></span>

1. <span data-ttu-id="2cd79-117">Kies **domein installeren** en vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-117">Choose **Domain Install**, then **Continue**.</span></span>

1. <span data-ttu-id="2cd79-118">Controleer de machtigingen, schakel het selectievakje in om de voorwaarden te accepteren en selecteer vervolgens **toestaan**, kies **volgende** en vervolgens **gereed**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-118">Review the permissions, select the checkbox to agree to the terms,then select **Allow**, choose **Next**, then **Done**.</span></span>

### <a name="create-connectors-and-run-the-migration"></a><span data-ttu-id="2cd79-119">Connectors maken en de migratie uitvoeren</span><span class="sxs-lookup"><span data-stu-id="2cd79-119">Create Connectors and run the migration</span></span>

1. <span data-ttu-id="2cd79-120">Ga terug naar **apps voor Google Workspace Marketplace**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-120">Return to **Google Workspace Marketplace apps**.</span></span>
1. <span data-ttu-id="2cd79-121">Vernieuw de browser en selecteer de app over de **verhuizer** .</span><span class="sxs-lookup"><span data-stu-id="2cd79-121">Refresh your browser, and select the **Mover** app.</span></span>
1. <span data-ttu-id="2cd79-122">Schuif omlaag en klik op de koppeling voor universeel navigatie.</span><span class="sxs-lookup"><span data-stu-id="2cd79-122">Scroll down and choose the universal navigation link.</span></span>
1. <span data-ttu-id="2cd79-123">Selecteer **nieuwe connector machtigen**, ga naar **G suite (beheerder)** en kies **autoriseren**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-123">Select **Authorize New Connector**, locate **G Suite (Admin)**, and choose **Authorize**.</span></span>
1. <span data-ttu-id="2cd79-124">Wijzig desgewenst de **weergavenaam** en selecteer vervolgens **machtigen**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-124">Change the **Display Name**, if you want, then select **Authorize**.</span></span>
1. <span data-ttu-id="2cd79-125">Kies een Google-beheerdersaccount, Controleer de machtigingen en selecteer **toestaan**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-125">Choose a Google admin account, review the permissions,then select **Allow**.</span></span>

    <span data-ttu-id="2cd79-126">Met de functie aandrijfman wordt het aantal team stations en gebruikersstations weergegeven dat is gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="2cd79-126">Mover displays the number of team drives and user drives it discovered.</span></span> 

1. <span data-ttu-id="2cd79-127">Kies onder **bestemming selecteren** de optie **nieuwe connector machtigen**, zoek **Office 365** en selecteer **autoriseren**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-127">Under **Select destination**, choose **Authorize New Connector**, locate **Office 365**, and select **Authorize**.</span></span>
1. <span data-ttu-id="2cd79-128">Als u machtigingen wilt verlenen aan de app-app in uw Azure Active Directory, gaat u naar [aka.MS/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span><span class="sxs-lookup"><span data-stu-id="2cd79-128">To grant permissions to the Mover app in your Azure Active Directory, navigate to [aka.ms/Office365MoverAuth](https://aka.ms/Office365MoverAuth).</span></span>
1. <span data-ttu-id="2cd79-129">Selecteer **Office 365-Aandrijfing**, **machtigingen**, **verlenen beheerder akkoord voor uw bedrijf**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-129">Select **Office 365 Mover**, **Permissions**, **Grant admin consent for your company**.</span></span>
1. <span data-ttu-id="2cd79-130">Kies uw account, Controleer de machtigingen en selecteer **accepteren**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-130">Choose your account, review the permissions, and select **Accept**.</span></span>
1. <span data-ttu-id="2cd79-131">Kies **Eigenschappen** en controleer of **gebruikerstoewijzing vereist is?** is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="2cd79-131">Choose **Properties** and verify that **User assignment required?** is turned on.</span></span>
1. <span data-ttu-id="2cd79-132">Ga terug naar de verplaatsings-app, Wijzig desgewenst de **weergavenaam**, kies **machtigen** en selecteer vervolgens een Microsoft-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="2cd79-132">Return to the Mover app, change the **Display Name**, if you want, choose **Authorize**,then select a Microsoft admin account.</span></span>

    <span data-ttu-id="2cd79-133">Met de aandrijf functie wordt u geïnformeerd over het aantal sites en gebruikers van SharePoint Online (of SPO).</span><span class="sxs-lookup"><span data-stu-id="2cd79-133">Mover will inform you about the number of SharePoint Online (or SPO) sites and users it discovered.</span></span>
1. <span data-ttu-id="2cd79-134">Kies **Doorgaan met migratie instellen**, selecteer **gebruikers toevoegen** en vervolgens **automatisch gebruikers ontdekken en toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-134">Choose **Continue Migration Setup**, select **Add Users**, then **Automatically Discover and Add Users**.</span></span>

    <span data-ttu-id="2cd79-135">Met de app voor het verplaatsen van een map wordt geprobeerd om stations van het bronpad in Google toe te wijzen aan het doelpad in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2cd79-135">The Mover app will attempt to map drives from the Source Path in Google, to the Destination Path in Microsoft 365.</span></span> 

    <span data-ttu-id="2cd79-136">Als een station niet automatisch wordt toegewezen, voegt u het doelpad toe aan een CSV-bestand, dat we later gebruiken om het gedeelde station te migreren naar een SharePoint-documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="2cd79-136">If a drive doesn’t map automatically, add its destination path to a CSV file, which we’ll use later to migrate the shared drive to a SharePoint document library.</span></span> 

1. <span data-ttu-id="2cd79-137">In dit geval hebben we een SharePoint-site met de naam gemigreerde bestanden toegevoegd en noteert u de URL voor de pagina documenten.</span><span class="sxs-lookup"><span data-stu-id="2cd79-137">In this case, we have added a SharePoint site called Migrated files, and taken note of the URL for the documents page.</span></span> 
1. <span data-ttu-id="2cd79-138">Vervolgens maakt u een CSV-bestand met de indeling van bronpad, doelpad en labels.</span><span class="sxs-lookup"><span data-stu-id="2cd79-138">We then created a CSV file using the format of Source Path, Destination Path, and Tags.</span></span> 

    <span data-ttu-id="2cd79-139">Zie [aka.MS/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2cd79-139">For details see [aka.ms/movercsv](https://docs.microsoft.com/sharepointmigration/mover-create-migration-csv).</span></span>

    <span data-ttu-id="2cd79-140">Wanneer u de URL van het doelpad toevoegt, moet u alles verwijderen na gedeelde documenten, bijvoorbeeld omdat deze volledige URL niet werkt: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span><span class="sxs-lookup"><span data-stu-id="2cd79-140">When adding the Destination Path URL, remove everything after Shared Documents for example For example, this full URL won't work: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents/Forms/AllItems.aspx`</span></span>

    <span data-ttu-id="2cd79-141">Wijzigen in: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span><span class="sxs-lookup"><span data-stu-id="2cd79-141">Change it to: `https://TENANT01.sharepoint.com/sites/SiteName/Shared Documents`</span></span>

1. <span data-ttu-id="2cd79-142">Als het CSV-bestand klaar is, selecteert u **migratie acties**, **toevoegen aan migratie**, en **kiest u een bestand om te uploaden**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-142">Once your CSV file is ready, select **Migration Actions**, **Add to Migration**, **Choose a file to upload**.</span></span>
1. <span data-ttu-id="2cd79-143">Ga naar het CSV-bestand, selecteer het en kies vervolgens **openen**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-143">Navigate to your CSV file, select it,then choose **Open**.</span></span>
1. <span data-ttu-id="2cd79-144">Selecteer de stations van de gebruiker van wie u de bestanden wilt migreren en kies vervolgens **migratie gebruikers starten**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-144">Select the user drives whose files you want to migrate, then choose **Start Migrating Users**.</span></span>
1. <span data-ttu-id="2cd79-145">Controleer de migratiegegevens, Kies wanneer u de migratie wilt starten, ga akkoord met de **voorwaarden en** Selecteer vervolgens **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="2cd79-145">Review the migration information, choose when to start the migration, agree to the **Terms and Conditions**, then select **Continue**.</span></span>

<span data-ttu-id="2cd79-146">Met de app over de Verhuizer wordt u gewaarschuwd wanneer het migratieproces is voltooid.</span><span class="sxs-lookup"><span data-stu-id="2cd79-146">The Mover app will inform you when the migration process is complete.</span></span>