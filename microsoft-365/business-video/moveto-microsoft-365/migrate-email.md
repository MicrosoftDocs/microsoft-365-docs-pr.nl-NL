---
title: Zakelijke e-mail en agenda migreren van Google Workspace
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
description: Leer hoe u e-mail, contactpersonen en agenda van Google Workspace migreert naar Microsoft 365 voor bedrijven.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794603"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="a9ba3-103">Zakelijke e-mail en agenda migreren van Google Workspace</span><span class="sxs-lookup"><span data-stu-id="a9ba3-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="a9ba3-104">U kunt een door de beheerder uitgevoerde migratie gebruiken voor Exchange Online vanuit Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="a9ba3-105">U kunt de e-mail allemaal tegelijk migreren of in fasen.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="a9ba3-106">In de volgende stappen wordt uitgelegd hoe u de e-mail gegevens in één keer migreert.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="a9ba3-107">Zie voor meer informatie [een G suite-migratie uitvoeren](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span><span class="sxs-lookup"><span data-stu-id="a9ba3-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="a9ba3-108">Het migratieproces gaat meerdere stappen uit en kan een paar dagen duren, afhankelijk van de hoeveelheid gegevens die u wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="a9ba3-109">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="a9ba3-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="a9ba3-110">Een Google-service account maken</span><span class="sxs-lookup"><span data-stu-id="a9ba3-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="a9ba3-111">Meld u met een Chrome-browser aan bij uw Google Workspace-beheerconsole op [admin.Google.com](https://admin.google.com).</span><span class="sxs-lookup"><span data-stu-id="a9ba3-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="a9ba3-112">Ga in een nieuw tabblad of venster naar de pagina [service accounts](https://console.developers.google.com/iam-admin/serviceaccounts) .</span><span class="sxs-lookup"><span data-stu-id="a9ba3-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="a9ba3-113">Selecteer **project maken**, geef een naam op voor het project en kies **maken**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="a9ba3-114">Selecteer **serviceaccount maken**, voer een naam in, kies **maken** en klik vervolgens op **gereed**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="a9ba3-115">Open het menu **acties** , selecteer **bewerken** en noteer de unieke id.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="a9ba3-116">U hebt deze ID later in het proces nodig.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="a9ba3-117">Open de sectie **delegeren op domeinniveau weergeven** .</span><span class="sxs-lookup"><span data-stu-id="a9ba3-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="a9ba3-118">Selecteer **Schakel G suite Domain-Wide delegering in**, voer een productnaam in voor het scherm voor toestemming en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="a9ba3-119">De productnaam wordt niet door het migratieproces gebruikt, maar is nodig om in het dialoogvenster op te slaan.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="a9ba3-120">Open het menu **acties** opnieuw en klik op **sleutel maken**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="a9ba3-121">Kies **JSON** en vervolgens **Create**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="a9ba3-122">De persoonlijke sleutel wordt opgeslagen in de downloadmap van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="a9ba3-123">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="a9ba3-124">API-gebruik voor het project inschakelen</span><span class="sxs-lookup"><span data-stu-id="a9ba3-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="a9ba3-125">Ga naar de [pagina api's](https://console.developers.google.com/apis/library).</span><span class="sxs-lookup"><span data-stu-id="a9ba3-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="a9ba3-126">Voer **Gmail-API** in de zoekbalk in.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="a9ba3-127">Selecteer het en kies **inschakelen**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="a9ba3-128">Herhaal dit proces voor de API van Google agenda en contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="a9ba3-129">Toegang verlenen aan het serviceaccount</span><span class="sxs-lookup"><span data-stu-id="a9ba3-129">Grant access to the service account</span></span>

1. <span data-ttu-id="a9ba3-130">Ga terug naar de beheerconsole van Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="a9ba3-131">Selecteer **beveiliging**, Blader omlaag en open **besturingselementen** voor de API.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="a9ba3-132">Schuif omlaag en selecteer **delegeren op domeinniveau beheren**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="a9ba3-133">Selecteer **nieuwe toevoegen** en voer de client-id in die u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="a9ba3-134">Voer vervolgens de OAuth-bereiken voor Google-Api's in.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="a9ba3-135">Deze bevindt zich in [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in stap 5 en zijn:</span><span class="sxs-lookup"><span data-stu-id="a9ba3-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="a9ba3-136">Kies **machtigen**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="a9ba3-137">Een subdomein maken voor e-mail die naar Microsoft 365 wordt verzonden</span><span class="sxs-lookup"><span data-stu-id="a9ba3-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="a9ba3-138">Ga terug naar de beheerconsole van **Google Workspace** .</span><span class="sxs-lookup"><span data-stu-id="a9ba3-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="a9ba3-139">Selecteer **domeinen**, **domeinen beheren** en voeg vervolgens **een domeinalias toe**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="a9ba3-140">Voer een domeinalias like in `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="a9ba3-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="a9ba3-141">Selecteer vervolgens **Doorgaan en domein eigendom verifiëren**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="a9ba3-142">De domeinverificatie duurt meestal enkele minuten, maar het kan tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="a9ba3-143">Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="a9ba3-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="a9ba3-144">In het **Microsoft 365-Beheercentrum**, in het linkernavigatievenster, selecteert u **AllesWeergeven**, **instellingen**, **domeinen** en vervolgens **domein toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="a9ba3-145">Voer het subdomein in dat u eerder hebt gemaakt en selecteer vervolgens **dit domein gebruiken**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="a9ba3-146">Als u verbinding wilt maken met het domein, selecteert u **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="a9ba3-147">Schuif omlaag en noteer de MX-records, CNAME-records en TXT-records.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="a9ba3-148">Ga terug naar de **Google-beheerconsole**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="a9ba3-149">Selecteer **domeinen**, selecteer **domeinen beheren**, **Controleer de gegevens** en klik vervolgens op **domein beheren**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="a9ba3-150">Kies in het linkernavigatievenster de optie **DNS** en schuif omlaag naar **Custom resource records**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="a9ba3-151">Open de vervolgkeuzelijst recordtype en selecteer **MX**, typ of kopieer en plak de gegevens van de MX-record die u eerder hebt vermeld, en kies vervolgens **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="a9ba3-152">Herhaal het proces voor de CNAME-record en de TXT-record.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="a9ba3-153">Het kan enige tijd duren voordat deze wijzigingen worden doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="a9ba3-154">Ga terug naar de plaats waar u was gebleven in **Microsoft 365-Beheercentrum** en selecteer **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="a9ba3-155">Uw domein is nu ingesteld.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="a9ba3-156">E-mail aliassen maken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9ba3-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="a9ba3-157">Voordat de migratie kan beginnen, moet u e-mail aliassen voor uw gebruikers maken met het nieuwe subdomein.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="a9ba3-158">Als u wilt beginnen met de volgende stap, selecteert u in de wizard **domeinen toevoegen** in het microsoft 365-Beheercentrum de optie **Ga naar actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="a9ba3-159">Selecteer een gebruiker en vervolgens **gebruikersnaam en E-mail beheren**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="a9ba3-160">Selecteer in de vervolgkeuzelijst **Domains** het subdomein dat u eerder hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="a9ba3-161">Voer een gebruikersnaam in, selecteer **toevoegen**, **wijzigingen opslaan** en sluit het venster.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="a9ba3-162">Herhaal dit proces voor elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="a9ba3-163">Het migratieproces starten</span><span class="sxs-lookup"><span data-stu-id="a9ba3-163">Start the migration process</span></span>

<span data-ttu-id="a9ba3-164">Wanneer u klaar bent met migreren, kunt u de migratie voltooien.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="a9ba3-165">Ga in het linkernavigatievenster van het **Microsoft 365-Beheercentrum** naar **beheer centra** en selecteer **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="a9ba3-166">Kies in het vak **geadresseerden** de optie **Migration**, selecteer **Nieuw**, **migreren naar Exchange Online**, kies de optie **G suite-migratie** en vervolgens **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="a9ba3-167">Maak een CSV-bestand met een lijst met de postvakken die u wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="a9ba3-168">Zorg ervoor dat het bestand de volgende indeling heeft:</span><span class="sxs-lookup"><span data-stu-id="a9ba3-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="a9ba3-169">Zie [aka.MS/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="a9ba3-170">Selecteer **bestand kiezen**, ga naar het CSV-bestand, kies het bestand, selecteer **openen** en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="a9ba3-171">Controleer het e-mailadres van de beheerder dat u wilt gebruiken om te testen.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="a9ba3-172">Selecteer **bestand kiezen**, ga naar het JSON-bestand dat u eerder hebt gemaakt (meestal in de map downloads op uw computer), kies dit, selecteer **openen** en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="a9ba3-173">Voer een naam in het **veld nieuwe migratie batchnaam** in.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="a9ba3-174">Typ het subdomein dat u hebt gemaakt in het veld **doel leverings domein** , selecteer **volgende** en klik vervolgens op **Nieuw**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="a9ba3-175">Wanneer de gegevens zijn opgeslagen, selecteert u **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="a9ba3-176">U kunt nu de status van uw migratie bekijken.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="a9ba3-177">Selecteer **vernieuwen**, afhankelijk van het aantal gebruikers dat u migreert, op het moment dat u de migratie hebt voltooid.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="a9ba3-178">Wanneer de status is gewijzigd in **gesynchroniseerd**, selecteert u **deze migratie batch voltooien** en vervolgens **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="a9ba3-179">Wanneer het proces is voltooid, wordt uw status gewijzigd in **voltooid**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="a9ba3-180">Als u wilt, kunt u **Details weergeven** selecteren voor meer informatie over de migratie.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="a9ba3-181">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-181">Select **Close**.</span></span> 
1. <span data-ttu-id="a9ba3-182">Open Outlook om te controleren of alle e-mailberichten van Google Workspace zijn gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="a9ba3-183">U kunt dit voor agenda-items en contactpersonen ook herhalen.</span><span class="sxs-lookup"><span data-stu-id="a9ba3-183">You can repeat this for calendar items and contacts as well.</span></span>