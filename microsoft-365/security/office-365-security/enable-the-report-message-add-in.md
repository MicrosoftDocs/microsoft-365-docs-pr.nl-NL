---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informatie over het inschakelen van de invoegversie bericht rapporteren voor Outlook en de webversie van Outlook, voor individuele gebruikers of voor de hele organisatie.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9b21472736cff2fd0eed7da5495ab6aae597032f
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094853"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="95dcc-103">De invoegtoepassing Bericht rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="95dcc-103">Enable the Report Message add-in</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> <span data-ttu-id="95dcc-104">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Voorzendingen te gebruiken in het beveiligings- & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="95dcc-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="95dcc-105">Zie Inzending door beheerders gebruiken om [verdachte spam, phish, URL's](admin-submission.md)en bestanden bij Microsoft in te dienen.</span><span class="sxs-lookup"><span data-stu-id="95dcc-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="95dcc-106">Met de invoegversies Bericht rapporteren en Phishing rapporteren voor Outlook en de webversie van Outlook (voorheen Outlook Web App) kunnen personen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of fout-negatieven (slechte e-mail toegestaan) rapporteren aan Microsoft en haar partners voor analyse.</span><span class="sxs-lookup"><span data-stu-id="95dcc-106">The Report Message and Report Phishing add-ins for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span>

<span data-ttu-id="95dcc-107">Microsoft gebruikt deze inzendingen om de effectiviteit van technologieën voor e-mailbeveiliging te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="95dcc-108">Als personen bijvoorbeeld een groot aantal berichten melden die zijn gemarkeerd als ongewenste [e-mail](configure-your-spam-filter-policies.md)door de invoeging Bericht rapporteren, moet het beveiligingsteam van uw organisatie mogelijk het antispambeleid aanpassen.</span><span class="sxs-lookup"><span data-stu-id="95dcc-108">For example, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="95dcc-109">U kunt de invoegapp Bericht rapporteren of Phishing melden installeren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-109">You can install either the Report Message or Report Phishing add-in.</span></span> <span data-ttu-id="95dcc-110">Als u wilt dat uw gebruikers alleen phishing-berichten melden, implementeert u de invoeg procenten voor phishing in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="95dcc-110">If you want your users to report only phishing messages, deploy the Report Phishing add-in in your organization.</span></span> <span data-ttu-id="95dcc-111">Zie [Phishing-invoegvoeging melden inschakelen voor meer informatie.](enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="95dcc-111">For more information, see [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).</span></span>

<span data-ttu-id="95dcc-112">De invoegapp Bericht rapporteren biedt de optie om zowel spam- als phishingberichten te melden.</span><span class="sxs-lookup"><span data-stu-id="95dcc-112">The Report Message add-in provides the option to report both spam and phishing messages.</span></span> <span data-ttu-id="95dcc-113">Beheerders kunnen de invoegapp Bericht rapporteren voor de organisatie inschakelen en afzonderlijke gebruikers kunnen deze voor zichzelf installeren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="95dcc-114">Als u een individuele gebruiker bent, kunt u de [invoegapp Bericht rapporteren voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="95dcc-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="95dcc-115">Als u een globale beheerder of een beheerder van Exchange Online bent en Exchange is geconfigureerd voor het gebruik van OAuth-verificatie, kunt u de invoeginstelling Bericht rapporteren [inschakelen voor uw organisatie.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="95dcc-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="95dcc-116">De rapportmel Add-In dingsmelding is nu beschikbaar via [Gecentraliseerde implementatie.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="95dcc-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95dcc-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="95dcc-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95dcc-118">De invoegapp Bericht rapporteren werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="95dcc-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="95dcc-119">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="95dcc-119">Outlook on the web</span></span>
  - <span data-ttu-id="95dcc-120">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="95dcc-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="95dcc-121">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="95dcc-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="95dcc-122">Outlook inbegrepen in Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="95dcc-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>
  - <span data-ttu-id="95dcc-123">Outlook-app voor iOS en Android</span><span class="sxs-lookup"><span data-stu-id="95dcc-123">Outlook app for iOS and Android</span></span>

- <span data-ttu-id="95dcc-124">De invoegapp Bericht rapporteren is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="95dcc-124">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="95dcc-125">U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="95dcc-125">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="95dcc-126">Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="95dcc-126">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="95dcc-127">Uw bestaande webbrowser moet werken met de invoegapp Bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-127">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="95dcc-128">Maar als u merkt dat de invoeg mail niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.</span><span class="sxs-lookup"><span data-stu-id="95dcc-128">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="95dcc-129">Voor installaties van de organisatie moet de organisatie worden geconfigureerd voor het gebruik van OAuth-verificatie.</span><span class="sxs-lookup"><span data-stu-id="95dcc-129">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="95dcc-130">Zie Bepalen of [Gecentraliseerde implementatie van invoegingen voor uw organisatie](../../admin/manage/centralized-deployment-of-add-ins.md)werkt voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="95dcc-130">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="95dcc-131">Beheerders moeten lid zijn van de rollengroep voor globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="95dcc-131">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="95dcc-132">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="95dcc-132">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="95dcc-133">De invoegapp Bericht rapporteren voor uzelf op halen</span><span class="sxs-lookup"><span data-stu-id="95dcc-133">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="95dcc-134">Ga naar Microsoft AppSource en zoek naar de <https://appsource.microsoft.com/marketplace/apps> invoegapp Bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-134">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="95dcc-135">Als u rechtstreeks naar de invoegvoegapp Bericht rapporteren wilt gaan, gaat u naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="95dcc-135">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="95dcc-136">Klik **OP NU KRIJGEN.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-136">Click **GET IT NOW**.</span></span>

   ![Bericht rapporteren - Nu ontvangen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="95dcc-138">Controleer in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-138">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="95dcc-139">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="95dcc-139">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="95dcc-140">Nadat de invoeg toevoegen is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="95dcc-140">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="95dcc-141">In Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="95dcc-141">In Outlook, the icon looks like this:</span></span>

  ![Pictogram berichtrapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="95dcc-143">In de webversie van Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="95dcc-143">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the web Report Message add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="95dcc-145">Zie De invoegapp Rapportbericht gebruiken voor meer informatie over het gebruik [van de invoegapp.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="95dcc-145">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="95dcc-146">De invoegapp Bericht rapporteren voor uw organisatie in- en uitschakelen</span><span class="sxs-lookup"><span data-stu-id="95dcc-146">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="95dcc-147">Het kan tot 12 uur duren voordat de invoeg toevoegen in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="95dcc-147">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="95dcc-148">Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="95dcc-148">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

2. <span data-ttu-id="95dcc-149">Selecteer **Invoeg toevoegen implementeren** boven aan de pagina en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-149">Select **Deploy Add-in** at the top of the page, and then select **Next**.</span></span>

   ![Pagina Services en invoegingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. <span data-ttu-id="95dcc-151">Bekijk **de informatie in de** flyout Een nieuwe invoeg toevoeg toevoegen implementeren die wordt weergegeven en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-151">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

4. <span data-ttu-id="95dcc-152">Klik op de volgende pagina op **Kiezen uit de Store.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-152">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="95dcc-154">Klik op de **pagina Invoeg** toevoegen selecteren  die wordt weergegeven in het  zoekvak, voer **Rapportbericht** in en klik vervolgens op het ![ pictogram ](../../media/search-icon.png) Zoeken.</span><span class="sxs-lookup"><span data-stu-id="95dcc-154">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="95dcc-155">Zoek in de lijst met resultaten **Rapportbericht en** klik op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-155">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Zoekresultaten voor invoegingen selecteren](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="95dcc-157">Controleer in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-157">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

7. <span data-ttu-id="95dcc-158">Configureer de volgende instellingen op de pagina **Invoeg** toevoegen configureren die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="95dcc-158">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="95dcc-159">**Toegewezen gebruikers:** selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="95dcc-159">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="95dcc-160">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="95dcc-160">**Everyone** (default)</span></span>
     - <span data-ttu-id="95dcc-161">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="95dcc-161">**Specific users / groups**</span></span>
     - <span data-ttu-id="95dcc-162">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="95dcc-162">**Just me**</span></span>

   - <span data-ttu-id="95dcc-163">**Implementatiemethode:** selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="95dcc-163">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="95dcc-164">**Opgelost (standaard)**: De invoeg toevoegen wordt automatisch geïmplementeerd voor de opgegeven gebruikers en ze kunnen deze niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="95dcc-164">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="95dcc-165">**Beschikbaar:** gebruikers kunnen de invoeg invoeg mag installeren in **de Home** \> **Get-invoegvoegingen,** \> **beheerd door de beheerder.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-165">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="95dcc-166">**Optioneel:** De invoegvoeginstelling wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen om deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="95dcc-166">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Pagina voor het configureren van invoeginstellingen](../../media/configure-add-in.png)

   <span data-ttu-id="95dcc-168">Klik op Implementeren wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-168">When you're finished, click **Deploy**.</span></span>

8. <span data-ttu-id="95dcc-169">Op de **pagina Rapportbericht** implementeren dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegapp is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="95dcc-169">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="95dcc-170">Nadat u de informatie hebt gelezen, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-170">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

9. <span data-ttu-id="95dcc-172">Controleer de gegevens op de pagina Aankondiging van **de invoeging** die wordt weergegeven en klik op **Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="95dcc-172">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Pagina voor aankondigen van invoegvoeging](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="95dcc-174">Informatie over het gebruik van de invoegapp Bericht rapporteren</span><span class="sxs-lookup"><span data-stu-id="95dcc-174">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="95dcc-175">Personen aan wie de invoeg toevoeg is toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="95dcc-175">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="95dcc-176">In Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="95dcc-176">In Outlook, the icon looks like this:</span></span>

  ![Pictogram berichtmelding rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="95dcc-178">In de webversie van Outlook ziet het pictogram er zo uit:</span><span class="sxs-lookup"><span data-stu-id="95dcc-178">In Outlook on the web, the icon looks like this:</span></span>

  ![Outlook on the Web Report Message Add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="95dcc-180">Wanneer u gebruikers op de hoogte stelt van de invoegapp Bericht rapporteren, voegt u een koppeling toe voor het gebruik van de [invoegapp Bericht rapporteren.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="95dcc-180">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="95dcc-181">Instellingen voor de invoegapp Bericht rapporteren bekijken of bewerken</span><span class="sxs-lookup"><span data-stu-id="95dcc-181">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="95dcc-182">Ga in het Microsoft 365-beheercentrum  naar de pagina \> **Instellingen-invoegvoegingen** op . Als u de pagina Invoeg toevoegen niet ziet, gaat u naar de koppeling Geïntegreerde <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>   \>  \> **apps-invoeginstellingen**  instellingen boven aan de pagina Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="95dcc-182">In the Microsoft 365 admin center, go to the go to the **Settings** \> **Add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns>, If you don't see the **Add-in** Page, go to the **Settings** \> **Integrated apps** \> **Add-ins** link on the top of the **Integrated apps** page.</span></span>

   ![Services en Add-Ins in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="95dcc-184">Zoek en selecteer de **invoegapp Bericht** rapporteren.</span><span class="sxs-lookup"><span data-stu-id="95dcc-184">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="95dcc-185">Bekijk en **bewerk** de instellingen in de flyout Rapportbericht bewerken die wordt weergegeven voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="95dcc-185">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="95dcc-186">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="95dcc-186">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoegapp Bericht rapporteren](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="95dcc-188">Gerapporteerde berichten weergeven en controleren</span><span class="sxs-lookup"><span data-stu-id="95dcc-188">View and review reported messages</span></span>

<span data-ttu-id="95dcc-189">Als u berichten wilt controleren die gebruikers rapporteren bij Microsoft, hebt u deze opties:</span><span class="sxs-lookup"><span data-stu-id="95dcc-189">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="95dcc-190">Gebruik de portal Voor het indienen van beheerders.</span><span class="sxs-lookup"><span data-stu-id="95dcc-190">Use the Admin Submissions portal.</span></span> <span data-ttu-id="95dcc-191">Zie Gebruikersinzendingen voor [Microsoft weergeven voor meer informatie.](admin-submission.md#view-user-submissions-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="95dcc-191">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="95dcc-192">Maak een e-mailstroomregel (ook wel transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="95dcc-192">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="95dcc-193">Zie Regels voor de [e-mailstroom gebruiken om te zien](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)wat uw gebruikers melden bij Microsoft.</span><span class="sxs-lookup"><span data-stu-id="95dcc-193">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
