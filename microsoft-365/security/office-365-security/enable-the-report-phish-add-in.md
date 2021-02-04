---
title: De invoegsel Phish-rapport inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informatie over het inschakelen van de invoegversie Phishing melden voor Outlook en de webversie van Outlook, voor individuele gebruikers of voor de hele organisatie.
ms.openlocfilehash: abac24e447d0afe9bc725dd8f9a976dce900b278
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094675"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="90aad-103">De invoegtoepassing Phishing rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="90aad-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="90aad-104">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="90aad-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="90aad-105">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="90aad-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="90aad-106">Met de invoegversies Bericht rapporteren en Phishing rapporteren voor Outlook en de webversie van Outlook (voorheen Outlook Web App) kunnen personen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of fout-negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar partners voor analyse.</span><span class="sxs-lookup"><span data-stu-id="90aad-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="90aad-107">Microsoft gebruikt deze inzendingen om de effectiviteit van technologieën voor e-mailbeveiliging te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="90aad-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="90aad-108">Stel dat veel berichten worden verzonden via de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="90aad-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="90aad-109">Deze informatie wordt beschikbaar in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="90aad-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="90aad-110">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken om aan te geven dat het anti-phishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="90aad-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="90aad-111">U kunt de invoegapp Bericht rapporteren of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="90aad-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="90aad-112">Als u wilt dat uw gebruikers zowel spam- als phishingberichten melden, implementeert u de invoegapp Bericht rapporteren in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90aad-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="90aad-113">Zie De [invoegapp Bericht rapporteren inschakelen voor meer informatie.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="90aad-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="90aad-114">De invoegvoegvoeging Phishing melden biedt de optie om alleen phishing-berichten te melden.</span><span class="sxs-lookup"><span data-stu-id="90aad-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="90aad-115">Beheerders kunnen de invoeg versie phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze voor zichzelf installeren.</span><span class="sxs-lookup"><span data-stu-id="90aad-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="90aad-116">Als u een individuele gebruiker bent, kunt u de invoeggebruiker [Phishing melden voor uzelf inschakelen.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="90aad-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="90aad-117">Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeginstelling Phishing melden voor uw [organisatie inschakelen.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="90aad-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="90aad-118">De melding Phishing-Add-In is nu beschikbaar via [Gecentraliseerde implementatie.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="90aad-118">The Report Phishing Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="90aad-119">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="90aad-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="90aad-120">De invoegvoeging Report Phishing werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="90aad-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="90aad-121">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="90aad-121">Outlook on the web</span></span>
  - <span data-ttu-id="90aad-122">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="90aad-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="90aad-123">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="90aad-123">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="90aad-124">Outlook inbegrepen in Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="90aad-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="90aad-125">Outlook-app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="90aad-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="90aad-126">De invoegbox Report Phishing is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="90aad-126">The Report Phishing add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="90aad-127">U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="90aad-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="90aad-128">Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="90aad-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="90aad-129">Uw bestaande webbrowser moet werken met de invoegonderdeel Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="90aad-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="90aad-130">Maar als u merkt dat de invoeg mail niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.</span><span class="sxs-lookup"><span data-stu-id="90aad-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="90aad-131">Voor installaties van de organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="90aad-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="90aad-132">Zie Bepalen of [Gecentraliseerde implementatie van invoegingen voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)werkt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90aad-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="90aad-133">Beheerders moeten lid zijn van de rollengroep voor globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="90aad-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="90aad-134">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90aad-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="90aad-135">De invoegvoeg voor Phishing melden voor uzelf</span><span class="sxs-lookup"><span data-stu-id="90aad-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="90aad-136">Ga naar Microsoft AppSource en zoek naar de invoegapp <https://appsource.microsoft.com/marketplace/apps> Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="90aad-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="90aad-137">Klik **OP NU KRIJGEN.**</span><span class="sxs-lookup"><span data-stu-id="90aad-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="90aad-138">Controleer in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="90aad-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="90aad-139">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="90aad-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="90aad-140">Nadat de invoeg toevoegen is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="90aad-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="90aad-141">In Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="90aad-141">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegvoeg voor Outlook melden](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="90aad-143">In de webversie van Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="90aad-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="90aad-145">De invoegvoeging Phishing melden voor uw organisatie in- en inschakelen</span><span class="sxs-lookup"><span data-stu-id="90aad-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="90aad-146">Het kan tot 12 uur duren voordat de invoeg toevoegen in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="90aad-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="90aad-147">Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="90aad-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="90aad-148">Selecteer **Invoeg toevoegen implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="90aad-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="90aad-150">Bekijk **de informatie in de** flyout Een nieuwe invoeg toevoeg toevoegen implementeren die wordt weergegeven en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="90aad-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="90aad-151">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="90aad-151">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="90aad-153">Klik op de **pagina Invoeg mail** selecteren  die wordt weergegeven in het  zoekvak, voer **Phishing** melden in en klik vervolgens op ![ het pictogram ](../../media/search-icon.png) Zoeken.</span><span class="sxs-lookup"><span data-stu-id="90aad-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="90aad-154">Zoek Phishing melden in de lijst **met** resultaten en klik op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="90aad-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="90aad-155">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="90aad-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="90aad-156">Configureer de volgende instellingen op de pagina **Invoeg** toevoegen configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="90aad-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="90aad-157">**Toegewezen gebruikers:** selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="90aad-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="90aad-158">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="90aad-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="90aad-159">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="90aad-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="90aad-160">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="90aad-160">**Just me**</span></span>

   - <span data-ttu-id="90aad-161">**Implementatiemethode:** selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="90aad-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="90aad-162">**Opgelost (standaard)**: De invoeg toevoegen wordt automatisch geïmplementeerd voor de opgegeven gebruikers en ze kunnen deze niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="90aad-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="90aad-163">**Beschikbaar:** gebruikers kunnen de invoeg invoeg mag installeren in **de Home** \> **Get-invoegvoegingen,** \> **beheerd door de beheerder.**</span><span class="sxs-lookup"><span data-stu-id="90aad-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="90aad-164">**Optioneel:** De invoegvoeginstelling wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen om deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="90aad-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="90aad-165">Klik op Implementeren wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="90aad-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="90aad-166">Op de **phishing-pagina Rapport** implementeren die wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegcode is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="90aad-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="90aad-167">Nadat u de informatie hebt gelezen, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="90aad-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="90aad-168">Controleer de gegevens op de pagina Aankondiging van **de invoeging** die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="90aad-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="90aad-169">Informatie over het gebruik van de invoeg toepassing Phishing melden</span><span class="sxs-lookup"><span data-stu-id="90aad-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="90aad-170">Personen aan wie de invoeg toevoeg is toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="90aad-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="90aad-171">In Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="90aad-171">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegvoeg voor Outlook melden](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="90aad-173">In de webversie van Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="90aad-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web Report Phishing Add-in icon](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="90aad-175">Instellingen voor de phishing-invoeging rapporteren controleren of bewerken</span><span class="sxs-lookup"><span data-stu-id="90aad-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="90aad-176">Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="90aad-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="90aad-177">Zoek en selecteer de **invoegvoeg voor Phishing** melden.</span><span class="sxs-lookup"><span data-stu-id="90aad-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="90aad-178">In de **Phishing-flyout Rapport** bewerken die wordt weergegeven, controleert en bewerkt, waar nodig voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="90aad-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="90aad-179">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="90aad-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="90aad-180">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="90aad-180">View and review reported messages</span></span>

<span data-ttu-id="90aad-181">Als u berichten wilt controleren die gebruikers rapporteren bij Microsoft, hebt u deze opties:</span><span class="sxs-lookup"><span data-stu-id="90aad-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="90aad-182">Gebruik de portal Voor het indienen van beheerders.</span><span class="sxs-lookup"><span data-stu-id="90aad-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="90aad-183">Zie Gebruikersinzendingen voor [Microsoft weergeven voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="90aad-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="90aad-184">Maak een e-mailstroomregel (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="90aad-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="90aad-185">Zie Regels voor de [e-mailstroom gebruiken om te zien](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)wat uw gebruikers melden bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="90aad-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
