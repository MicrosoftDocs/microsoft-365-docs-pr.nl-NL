---
title: De phish-invoeging rapport inschakelen
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
description: Meer informatie over het inschakelen van de invoegversie Van Phishing melden voor de webversie van Outlook en Outlook, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059621"
---
# <a name="enable-the-report-phishing-add-in"></a><span data-ttu-id="f27cc-103">De invoegtoepassing Phishing rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="f27cc-103">Enable the Report Phishing add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="f27cc-104">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="f27cc-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f27cc-105">Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f27cc-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f27cc-106">Met de invoegvoegingen Rapportbericht en Rapport phishing voor de webversie van Outlook en Outlook (voorheen Bekend als Outlook Web App) kunnen personen eenvoudig onwaar-positieven (goede e-mail die als slecht is gemarkeerd) of onwaar negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar gelieerde bedrijven voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f27cc-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enable people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="f27cc-107">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="f27cc-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f27cc-108">Stel dat mensen veel berichten rapporteren met de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="f27cc-108">For example, suppose that people are reporting many messages using the Report Phishing add-in.</span></span> <span data-ttu-id="f27cc-109">Deze informatie wordt in het [beveiligingsdashboard en](security-dashboard.md) andere rapporten opgedoken.</span><span class="sxs-lookup"><span data-stu-id="f27cc-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f27cc-110">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat anti-phishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f27cc-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span>

<span data-ttu-id="f27cc-111">U kunt de invoeging Rapportbericht of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="f27cc-111">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="f27cc-112">Als u wilt dat uw gebruikers zowel spam- als phishingberichten rapporteren, implementeert u de invoeging Rapportbericht in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f27cc-112">If you want your users to report both spam and phishing messages, deploy the Report Message add-in in your organization.</span></span> <span data-ttu-id="f27cc-113">Zie De [invoegvoegapp Rapportbericht inschakelen voor meer informatie.](enable-the-report-message-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="f27cc-113">For more information, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="f27cc-114">De invoegvoegvoegoptie Phishing melden biedt de optie om alleen phishingberichten te rapporteren.</span><span class="sxs-lookup"><span data-stu-id="f27cc-114">The Report Phishing add-in provides the option to report only phishing messages.</span></span> <span data-ttu-id="f27cc-115">Beheerders kunnen de invoeging Phishing melden inschakelen voor de organisatie en afzonderlijke gebruikers kunnen deze zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="f27cc-115">Admins can enable the Report Phishing add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f27cc-116">Als u een individuele gebruiker bent, kunt u de invoeging [Phishing melden voor uzelf inschakelen.](#get-the-report-phishing-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f27cc-116">If you're an individual user, you can [enable the Report Phishing add-in for yourself](#get-the-report-phishing-add-in-for-yourself).</span></span>

<span data-ttu-id="f27cc-117">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoegvoeging [Phishing melden inschakelen voor uw organisatie.](#get-and-enable-the-report-phishing-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f27cc-117">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Phishing add-in for your organization](#get-and-enable-the-report-phishing-add-in-for-your-organization).</span></span> <span data-ttu-id="f27cc-118">De phishing-Add-In rapport is nu beschikbaar via [Gecentraliseerde implementatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f27cc-118">The Report Phishing Add-In is now available through [Centralized Deployment](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f27cc-119">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f27cc-119">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f27cc-120">De invoeging Report Phishing werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="f27cc-120">The Report Phishing add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f27cc-121">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f27cc-121">Outlook on the web</span></span>
  - <span data-ttu-id="f27cc-122">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="f27cc-122">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f27cc-123">Outlook 2016 voor Mac of hoger</span><span class="sxs-lookup"><span data-stu-id="f27cc-123">Outlook 2016 for Mac or later</span></span>
  - <span data-ttu-id="f27cc-124">Outlook inbegrepen bij Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="f27cc-124">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="f27cc-125">Outlook-app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="f27cc-125">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="f27cc-126">De invoeging Phishing melden is niet beschikbaar voor gedeelde postvakken of postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="f27cc-126">The Report Phishing add-in is not available for shared mailboxes or mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="f27cc-127">U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="f27cc-127">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="f27cc-128">Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f27cc-128">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="f27cc-129">Uw bestaande webbrowser moet werken met de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="f27cc-129">Your existing web browser should work with the Report Phishing add-in.</span></span> <span data-ttu-id="f27cc-130">Maar als u merkt dat de invoegvoeging niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="f27cc-130">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f27cc-131">Voor organisatie-installaties moet de organisatie zijn geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="f27cc-131">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f27cc-132">Zie Bepalen of gecentraliseerde implementatie van invoegvoegingen werkt [voor uw organisatie voor meer informatie.](../../admin/manage/centralized-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="f27cc-132">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f27cc-133">Beheerders moeten lid zijn van de rollengroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="f27cc-133">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f27cc-134">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f27cc-134">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-phishing-add-in-for-yourself"></a><span data-ttu-id="f27cc-135">De invoeging Report Phishing voor uzelf krijgen</span><span class="sxs-lookup"><span data-stu-id="f27cc-135">Get the Report Phishing add-in for yourself</span></span>

1. <span data-ttu-id="f27cc-136">Ga naar de Microsoft AppSource op <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoeging Phishing melden.</span><span class="sxs-lookup"><span data-stu-id="f27cc-136">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Phishing add-in.</span></span>

2. <span data-ttu-id="f27cc-137">Klik **op NU krijgen.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-137">Click **GET IT NOW**.</span></span>

3. <span data-ttu-id="f27cc-138">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f27cc-139">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="f27cc-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f27cc-140">Nadat de invoegvoegvoeging is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f27cc-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f27cc-141">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="f27cc-141">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f27cc-143">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="f27cc-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook op het web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a><span data-ttu-id="f27cc-145">De invoeging Phishingrapport voor uw organisatie inschakelen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="f27cc-145">Get and enable the Report Phishing add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f27cc-146">Het kan tot 12 uur duren voordat de invoegvoeging wordt weergegeven in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f27cc-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f27cc-147">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="f27cc-147">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f27cc-148">Selecteer **Invoegvoegvoeging implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-148">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegvoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="f27cc-150">Controleer de informatie in het **fly-out Nieuwe invoegsel** implementeren dat wordt weergegeven en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-150">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="f27cc-151">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-151">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="f27cc-153">Klik in het vak Zoeken op de  **pagina** Invoeg toevoegen selecteren die wordt weergegeven, voer **Rapport phishing** in en klik vervolgens op **zoekpictogram** ![ ](../../media/search-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="f27cc-153">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Phishing**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f27cc-154">Zoek in de lijst met resultaten **naar Rapport phishing** en klik vervolgens op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-154">In the list of results, find **Report Phishing** and then click **Add**.</span></span>

6. <span data-ttu-id="f27cc-155">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik vervolgens op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="f27cc-156">Configureer de volgende instellingen op de **pagina Invoeging** configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f27cc-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f27cc-157">**Toegewezen gebruikers:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f27cc-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f27cc-158">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="f27cc-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="f27cc-159">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="f27cc-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="f27cc-160">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="f27cc-160">**Just me**</span></span>

   - <span data-ttu-id="f27cc-161">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f27cc-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f27cc-162">**Opgelost (standaard)**: De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers en kan niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f27cc-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f27cc-163">**Beschikbaar:** Gebruikers kunnen de invoegvoeging installeren bij **Home** \> **Get-invoegvoegingen** beheerd door \> **beheerder.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f27cc-164">**Optioneel:** De invoeging wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f27cc-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   <span data-ttu-id="f27cc-165">Wanneer u klaar bent, klikt u op **Implementeren.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-165">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="f27cc-166">Op de **pagina Rapport phishing implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoeging is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="f27cc-166">In the **Deploy Report Phishing** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f27cc-167">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f27cc-167">After you read the information, click **Next**.</span></span>

9. <span data-ttu-id="f27cc-168">Controleer de gegevens op de **pagina Invoeging** aankondigen die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="f27cc-168">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

## <a name="learn-how-to-use-the-report-phishing-add-in"></a><span data-ttu-id="f27cc-169">Meer informatie over het gebruik van de invoeging Phishing melden</span><span class="sxs-lookup"><span data-stu-id="f27cc-169">Learn how to use the Report Phishing add-in</span></span>

<span data-ttu-id="f27cc-170">Personen aan wie de invoegvoeging is toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f27cc-170">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f27cc-171">In Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="f27cc-171">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook rapporteren](../../media/Outlook-ReportPhishing.png)

- <span data-ttu-id="f27cc-173">In de webversie van Outlook ziet het pictogram er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="f27cc-173">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Phishing-invoegversie van Outlook op het webrapport](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a><span data-ttu-id="f27cc-175">Instellingen controleren of bewerken voor de invoeging Phishingrapport</span><span class="sxs-lookup"><span data-stu-id="f27cc-175">Review or edit settings for the Report Phishing add-in</span></span>

1. <span data-ttu-id="f27cc-176">Ga in het Microsoft 365-beheercentrum  naar de pagina Instellingen invoegvoegingen op , Als u de invoegpagina niet ziet, gaat u naar de koppeling Geïntegreerde \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="f27cc-176">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="f27cc-177">Zoek en selecteer de **invoeging Phishing** melden.</span><span class="sxs-lookup"><span data-stu-id="f27cc-177">Find and select the **Report Phishing** add-in.</span></span>

3. <span data-ttu-id="f27cc-178">In het **flyout Rapport phishing bewerken** dat de instellingen voor uw organisatie wordt weergegeven, controleren en bewerken.</span><span class="sxs-lookup"><span data-stu-id="f27cc-178">In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f27cc-179">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="f27cc-179">When you're finished, click **Save**.</span></span>

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="f27cc-180">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="f27cc-180">View and review reported messages</span></span>

<span data-ttu-id="f27cc-181">Als u berichten wilt bekijken die gebruikers rapporteren aan Microsoft, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="f27cc-181">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="f27cc-182">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="f27cc-182">Use the Admin Submissions portal.</span></span> <span data-ttu-id="f27cc-183">Zie Gebruikersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="f27cc-183">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="f27cc-184">Maak een regel voor de e-mailstroom (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="f27cc-184">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="f27cc-185">Zie Regels voor [e-mailstroom gebruiken voor](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)instructies om te zien wat uw gebruikers rapporteren aan Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f27cc-185">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
