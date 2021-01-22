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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Lees hoe u e-mail, contactpersonen en agenda migreert van Google Workspace naar Microsoft 365 voor Bedrijven.
ms.openlocfilehash: cb751b1d2f18b226021bb6f218b62f3ae426f6a4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928244"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a><span data-ttu-id="cc0ef-103">Zakelijke e-mail en agenda migreren van Google Workspace</span><span class="sxs-lookup"><span data-stu-id="cc0ef-103">Migrate business email and calendar from Google Workspace</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

<span data-ttu-id="cc0ef-104">U kunt vanuit Google Workspace een migratie door beheerders naar Exchange Online gebruiken.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-104">You can use an admin-ran migration to Exchange Online from Google Workspace.</span></span> <span data-ttu-id="cc0ef-105">U kunt de e-mail in één keer of in fasen migreren.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-105">You can migrate the mail either all at once, or in stages.</span></span> <span data-ttu-id="cc0ef-106">De volgende stappen laten zien hoe u de e-mailgegevens in één keer migreert.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-106">The following steps show how to migrate the email data at once.</span></span> <span data-ttu-id="cc0ef-107">Zie Een G Suite-migratie uitvoeren voor [meer informatie.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-107">For more information, see [Perform a G Suite migration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).</span></span>

<span data-ttu-id="cc0ef-108">Het migratieproces is in enkele stappen en kan enkele uren tot een paar dagen duren, afhankelijk van de hoeveelheid gegevens die u migreert.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-108">The migration process takes several steps and can take from several hours to a couple of days depending on the amount of data you are migrating.</span></span>

## <a name="try-it"></a><span data-ttu-id="cc0ef-109">Probeer het zelf!</span><span class="sxs-lookup"><span data-stu-id="cc0ef-109">Try it!</span></span>

### <a name="create-a-google-service-account"></a><span data-ttu-id="cc0ef-110">Een Google Service-account maken</span><span class="sxs-lookup"><span data-stu-id="cc0ef-110">Create a Google Service Account</span></span>

1. <span data-ttu-id="cc0ef-111">Meld u met een Chrome-browser aan bij uw Google Workspace-beheerconsole op [admin.google.com.](https://admin.google.com)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-111">Using a Chrome browser, sign into your Google Workspace admin console at [admin.google.com](https://admin.google.com).</span></span> 
1. <span data-ttu-id="cc0ef-112">Navigeer in een nieuw tabblad of venster naar de [pagina Serviceaccounts.](https://console.developers.google.com/iam-admin/serviceaccounts)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-112">In a new tab or window, navigate to the [Service Accounts](https://console.developers.google.com/iam-admin/serviceaccounts) page.</span></span> 
1. <span data-ttu-id="cc0ef-113">Selecteer **Project maken,** noem het project en kies **Maken.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-113">Select **Create project**, name the project and choose **Create**.</span></span> 
1. <span data-ttu-id="cc0ef-114">Selecteer **Serviceaccount maken,** voer een naam in, kies **Maken** en vervolgens **Klaar.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-114">Select **Create service account**, enter a name, choose **Create** and then **Done**.</span></span> 
1. <span data-ttu-id="cc0ef-115">Open **het** menu Acties, **selecteer** Bewerken en noteer de unieke id.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-115">Open the **Actions** menu, select **Edit**, and take note of the Unique ID.</span></span> <span data-ttu-id="cc0ef-116">U hebt deze id later in het proces nodig.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-116">You’ll need this ID later in the process.</span></span> 
1. <span data-ttu-id="cc0ef-117">Open de **sectie Delegatie voor het hele domein** tonen.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-117">Open the **Show domain-wide delegation** section.</span></span> 
1. <span data-ttu-id="cc0ef-118">Selecteer **Delegatie voor het hele G Suite-domein** inschakelen, voer een productnaam in voor het toestemmingsscherm en kies **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-118">Select **Enable G Suite Domain-wide Delegation**, enter a product name for the consent screen, and choose **Save**.</span></span> 

    > [!NOTE]
> <span data-ttu-id="cc0ef-119">De productnaam wordt niet gebruikt tijdens het migratieproces, maar moet worden op te slaan in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-119">The product name is not used by the migration process, but is needed to save in the dialog.</span></span>     

1. <span data-ttu-id="cc0ef-120">Open **het** menu Acties opnieuw en selecteer **Sleutel maken.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-120">Open the **Actions** menu again and select **Create key**.</span></span> 
1. <span data-ttu-id="cc0ef-121">Kies **JSON** en vervolgens **Maken.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-121">Choose **JSON**, then **Create**.</span></span> 

     <span data-ttu-id="cc0ef-122">De persoonlijke sleutel wordt opgeslagen in de downloadmap op uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-122">The private key is saved to the download folder on your device.</span></span>
 
1. <span data-ttu-id="cc0ef-123">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-123">Select **Close**.</span></span> 

### <a name="enable-api-usage-for-the-project"></a><span data-ttu-id="cc0ef-124">API-gebruik voor het project inschakelen</span><span class="sxs-lookup"><span data-stu-id="cc0ef-124">Enable API usage for the project</span></span>

1. <span data-ttu-id="cc0ef-125">Ga naar de [pagina API's.](https://console.developers.google.com/apis/library)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-125">Navigate to the [APIs page](https://console.developers.google.com/apis/library).</span></span> 
1. <span data-ttu-id="cc0ef-126">Voer in de zoekbalk de **Gmail-API in.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-126">In the search bar, enter **Gmail API**.</span></span>
1. <span data-ttu-id="cc0ef-127">Selecteer deze en kies **Inschakelen.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-127">Select it and then choose **Enable**.</span></span>
1. <span data-ttu-id="cc0ef-128">Herhaal deze procedure voor google Agenda-API en Contactpersonen-API.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-128">Repeat this process for Google Calendar API and Contacts API.</span></span> 

### <a name="grant-access-to-the-service-account"></a><span data-ttu-id="cc0ef-129">Toegang verlenen tot het serviceaccount</span><span class="sxs-lookup"><span data-stu-id="cc0ef-129">Grant access to the service account</span></span>

1. <span data-ttu-id="cc0ef-130">Ga terug naar de beheerconsole van Google Workspace.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-130">Return to the Google Workspace admin console.</span></span> 
1. <span data-ttu-id="cc0ef-131">Selecteer **Beveiliging,** schuif omlaag en open **API-besturingselementen.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-131">Select **Security**, scroll down and open **API controls**.</span></span> 
1. <span data-ttu-id="cc0ef-132">Schuif omlaag en selecteer **Delegatie voor het hele domein beheren.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-132">Scroll down and select **Manage Domain-wide Delegation**.</span></span>
1. <span data-ttu-id="cc0ef-133">Selecteer **Nieuwe toevoegen** en voer de klant-id in die u eerder hebt noteren.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-133">Select **Add new** and enter the Client ID you made note of earlier.</span></span>
1. <span data-ttu-id="cc0ef-134">Voer vervolgens de OAuth-scopes voor Google API's in.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-134">Then enter the OAuth scopes for Google APIs.</span></span> <span data-ttu-id="cc0ef-135">Deze zijn beschikbaar op [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in stap 5 en zijn:</span><span class="sxs-lookup"><span data-stu-id="cc0ef-135">These are available at [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) in step 5 and are:</span></span>

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. <span data-ttu-id="cc0ef-136">Kies **Autor.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-136">Choose **Authorize**.</span></span> 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a><span data-ttu-id="cc0ef-137">Een subdomein maken voor e-mail die naar Microsoft 365 gaat</span><span class="sxs-lookup"><span data-stu-id="cc0ef-137">Create a sub-domain for mail going to Microsoft 365</span></span>

1. <span data-ttu-id="cc0ef-138">Ga terug naar de **beheerconsole van Google Workspace.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-138">Return to the **Google Workspace admin** console.</span></span>
1. <span data-ttu-id="cc0ef-139">Selecteer Domeinen, **Domeinen beheren** en vervolgens Een **domeinalias toevoegen.** </span><span class="sxs-lookup"><span data-stu-id="cc0ef-139">Select **Domains**, **Manage domains**, then, **Add a domain alias**.</span></span> 
1. <span data-ttu-id="cc0ef-140">Voer een domeinalias in, zoals `m365.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="cc0ef-140">Enter a domain alias like `m365.contoso.com`.</span></span>
1. <span data-ttu-id="cc0ef-141">Selecteer vervolgens **Doorgaan en controleer het eigendom van het domein.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-141">Then select **Continue and verify domain ownership**.</span></span> 

    <span data-ttu-id="cc0ef-142">Domeinverificatie duurt meestal slechts een paar minuten, maar dit kan tot 48 uur duren.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-142">Domain verification usually takes just a few minutes, but it can take up to 48 hours.</span></span>

1. <span data-ttu-id="cc0ef-143">Ga naar het [Microsoft 365-beheercentrum.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-143">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="cc0ef-144">Selecteer in **het Microsoft 365-beheercentrum** in **het** linkernavigatiemenu Alles **tonen,** **Instellingen,** Domeinen en vervolgens **Domein toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-144">In the **Microsoft 365 admin center**, in the left nav, select **Show all**, **Settings**, **Domains**, and then **Add domain**.</span></span> 
1. <span data-ttu-id="cc0ef-145">Voer het subdomein in dat u eerder hebt gemaakt en selecteer **Dit domein gebruiken.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-145">Enter the subdomain you previously created, then select **Use this domain**.</span></span> 
1. <span data-ttu-id="cc0ef-146">Als u het domein wilt verbinden, selecteert u **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-146">To connect the domain, select **Continue**.</span></span> 
1. <span data-ttu-id="cc0ef-147">Schuif omlaag en noteer de MX-records, CNAME-records en TXT-records.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-147">Scroll down and take note of the MX records, CNAME records, and TXT records.</span></span> 
1. <span data-ttu-id="cc0ef-148">Ga terug naar de **Google-beheerconsole.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-148">Return to the **Google admin console**.</span></span>
1. <span data-ttu-id="cc0ef-149">Selecteer **Domeinen,** selecteer **Domeinen beheren,** **Controleer details** en vervolgens **Domein beheren.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-149">Select **Domains**, select **Manage domains**, **Verify Details** and then, **Manage domain**.</span></span> 
1. <span data-ttu-id="cc0ef-150">Kies DNS in het linkernavigatie **navigatiecentrum** en schuif omlaag **naar Aangepaste resourcerecords.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-150">In the left nav, choose **DNS** and scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="cc0ef-151">Open de vervolgkeuze met recordtype en selecteer **MX,** typ of kopieer en plak de mx-recordgegevens die u eerder hebt genoteerd, en kies vervolgens **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-151">Open the record type dropdown and select **MX**, enter or copy and paste the MX record information you previously noted,then choose **Add**.</span></span> 
1. <span data-ttu-id="cc0ef-152">Herhaal dit proces voor de CNAME-record en de TXT-record.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-152">Repeat the process for the CNAME record and the TXT record.</span></span> 

    <span data-ttu-id="cc0ef-153">Het kan even duren voor deze wijzigingen zijn doorgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-153">It may take some time for these changes to take effect.</span></span>  

1. <span data-ttu-id="cc0ef-154">Ga terug naar waar u was gebleven in het **Microsoft 365-beheercentrum** en selecteer **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-154">Return to where you left off in **Microsoft 365 admin center**, and select **Continue**.</span></span> 

<span data-ttu-id="cc0ef-155">Uw domein is nu ingesteld.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-155">Your domain is now set up.</span></span>  

### <a name="create-email-aliases-in-microsoft-365"></a><span data-ttu-id="cc0ef-156">E-mailaliassen maken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cc0ef-156">Create email aliases in Microsoft 365</span></span>

<span data-ttu-id="cc0ef-157">Voordat de migratie kan beginnen, moet u e-mailaliassen maken voor uw gebruikers met het nieuwe subdomein.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-157">Before migration can begin, you need to create email aliases for your users with the new subdomain.</span></span> 

1. <span data-ttu-id="cc0ef-158">Als u de volgende stap wilt starten, selecteert u in de **wizard** Domeinen toevoegen in het Microsoft 365-beheercentrum de optie Ga naar **Actieve gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-158">To start the next step, in the **Add Domains** wizard in the Microsoft 365 admin center, select **Go to Active users**.</span></span> 
1. <span data-ttu-id="cc0ef-159">Selecteer een gebruiker en vervolgens **Gebruikersnaam en e-mailadres beheren.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-159">Select a user, then, **Manage username and email**.</span></span> 
1. <span data-ttu-id="cc0ef-160">Selecteer het subdomein **dat** u eerder hebt gemaakt in de vervolgkeuze voor domeinen.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-160">From the **Domains** dropdown, select the subdomain you previously created.</span></span> 
1. <span data-ttu-id="cc0ef-161">Voer een gebruikersnaam in, selecteer **Toevoegen,** **Wijzigingen opslaan** en sluit het venster.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-161">Enter a username, select **Add**, **Save changes**, and close the window.</span></span> 

    <span data-ttu-id="cc0ef-162">Herhaal deze procedure voor elke gebruiker.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-162">Repeat this process for each user.</span></span> 

### <a name="start-the-migration-process"></a><span data-ttu-id="cc0ef-163">Het migratieproces starten</span><span class="sxs-lookup"><span data-stu-id="cc0ef-163">Start the migration process</span></span>

<span data-ttu-id="cc0ef-164">Wanneer u klaar bent, kunt u gaan migreren.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-164">Once you’ve finished, you’re ready to migrate.</span></span> 

1. <span data-ttu-id="cc0ef-165">Schuif in het linkernavigatienavigatiecentrum van **het Microsoft 365-beheercentrum** omlaag naar **beheercentra** en selecteer **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-165">In the left nav of the **Microsoft 365 admin center**, scroll down to **Admin centers**,and select **Exchange**.</span></span> 
1. <span data-ttu-id="cc0ef-166">Kies **migratie onder** geadresseerden, **selecteer** **Nieuw,** Migreren naar **Exchange Online,** **kies G Suite-migratie** en vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-166">Under **recipients**, choose **migration**, select **New**, **Migrate to Exchange Online**, choose **G Suite migration**, and then **Next**.</span></span> 
1. <span data-ttu-id="cc0ef-167">Maak een CSV-bestand met een lijst met de postvakken die u wilt migreren.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-167">Create a CSV file with a list of the mailboxes you want to migrate.</span></span> <span data-ttu-id="cc0ef-168">Zorg ervoor dat het bestand de volgende indeling heeft:</span><span class="sxs-lookup"><span data-stu-id="cc0ef-168">Make sure the file follows this format:</span></span> 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      <span data-ttu-id="cc0ef-169">Zie voor meer [informatie aka.ms/GoogleWorkspaceMigration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac)</span><span class="sxs-lookup"><span data-stu-id="cc0ef-169">For details see [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac).</span></span> 

1. <span data-ttu-id="cc0ef-170">Selecteer **Bestand kiezen,** ga naar het CSV-bestand, kies het, **selecteer Openen** en vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-170">Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="cc0ef-171">Controleer het e-mailadres van de beheerder dat u wilt gebruiken voor het testen.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-171">Verify the admin email address you want to use for testing.</span></span> 
1. <span data-ttu-id="cc0ef-172">Selecteer **Bestand kiezen,** ga naar het JSON-bestand dat u eerder hebt gemaakt (meestal in de map Downloads op uw computer), kies het, selecteer Openen **en** vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-172">Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**.</span></span> 
1. <span data-ttu-id="cc0ef-173">Voer een naam in het **veld Nieuwe migratiebatchnaam in.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-173">Enter a name in the **New migration batch name field**.</span></span>
1. <span data-ttu-id="cc0ef-174">Voer het subdomein in dat u hebt gemaakt in het veld Doelbezorgingsdomein, selecteer **Volgende** en vervolgens **Nieuw.** </span><span class="sxs-lookup"><span data-stu-id="cc0ef-174">Enter the subdomain you created in the **Target delivery domain** field, select **Next**, and then **New**.</span></span> 
1. <span data-ttu-id="cc0ef-175">Nadat de gegevens zijn opgeslagen, selecteert u **OK.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-175">Once the information is saved, select **OK**.</span></span> 

    <span data-ttu-id="cc0ef-176">U kunt nu de status van de migratie bekijken.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-176">You can now view the status of your migration.</span></span> 

1. <span data-ttu-id="cc0ef-177">Nadat enige tijd is verstreken, selecteert u Vernieuwen, afhankelijk van het aantal gebruikers dat u **wilt migreren.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-177">After some time has passed, depending on how many users you are migrating, select **Refresh**.</span></span> 
1. <span data-ttu-id="cc0ef-178">Nadat de status is gewijzigd in **Gesynchroniseerd,** selecteert u **Deze migratiebatch voltooien** en vervolgens **Ja.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-178">Once the status has changed to **Synced**, select **Complete this migration batch**,then **Yes**.</span></span> 
1. <span data-ttu-id="cc0ef-179">Wanneer het proces is voltooid, wordt uw status gewijzigd in **Voltooid.**</span><span class="sxs-lookup"><span data-stu-id="cc0ef-179">Once the process is complete, your status will change to **Completed**.</span></span> 
1. <span data-ttu-id="cc0ef-180">Als u wilt, kunt u **Details weergeven selecteren** voor meer informatie over de migratie.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-180">If you want, you can select **View details** for more information about the migration.</span></span> 
1. <span data-ttu-id="cc0ef-181">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-181">Select **Close**.</span></span> 
1. <span data-ttu-id="cc0ef-182">Open Outlook om te controleren of alle e-mailberichten van Google Workspace zijn gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-182">Open Outlook to verify that all the emails from Google Workspace were successfully migrated.</span></span>
<span data-ttu-id="cc0ef-183">U kunt dit ook herhalen voor agenda-items en contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="cc0ef-183">You can repeat this for calendar items and contacts as well.</span></span>