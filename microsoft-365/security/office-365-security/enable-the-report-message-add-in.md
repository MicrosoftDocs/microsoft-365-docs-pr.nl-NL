---
title: De invoegtoepassing Bericht rapporteren inschakelen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Meer informatie over het inschakelen van de invoegtoepassing Bericht rapport voor de webversie van Outlook en Outlook, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 101a37f48e31f762171b2269055d0e69c889d0dc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633297"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f953a-103">De invoegtoepassing Bericht rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="f953a-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="f953a-104">Als u een beheerder bent in een organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Beveiligings- & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="f953a-104">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="f953a-105">Zie [Het indienen van beheerders gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="f953a-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="f953a-106">Met de invoegtoepassing Rapportbericht voor Outlook en Outlook op het web (voorheen Outlook Web App) kunnen mensen eenvoudig valse positieven (goede e-mail gemarkeerd als slecht) of valse negatieven (slechte e-mail toegestaan) melden aan Microsoft en haar gelieerde ondernemingen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f953a-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="f953a-107">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="f953a-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="f953a-108">Stel dat mensen veel berichten melden als phishing.</span><span class="sxs-lookup"><span data-stu-id="f953a-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="f953a-109">Deze informatie wordt weergegeven in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="f953a-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f953a-110">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat het antiphishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f953a-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="f953a-111">Als mensen veel berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als Niet-ongewenstee e-mail met behulp van de invoegtoepassing Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk [het antispambeleid](configure-your-spam-filter-policies.md)aanpassen.</span><span class="sxs-lookup"><span data-stu-id="f953a-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f953a-112">Als uw organisatie bovendien [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) of Plan [2](office-365-ti.md)gebruikt, biedt de invoegtoepassing Rapportbericht het beveiligingsteam van uw organisatie nuttige informatie die ze kunnen gebruiken om het beveiligingsbeleid te bekijken en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="f953a-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="f953a-113">Beheerders kunnen de invoegtoepassing Rapportbericht voor de organisatie inschakelen en individuele gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="f953a-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="f953a-114">Als u een individuele gebruiker bent, u [de invoegtoepassing Bericht melden voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f953a-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="f953a-115">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd om OAuth-verificatie te gebruiken, u [de invoegtoepassing Bericht rapport voor uw organisatie inschakelen.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f953a-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="f953a-116">De invoegtoepassing Rapportbericht is nu beschikbaar via [gecentraliseerde implementatie.](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f953a-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f953a-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="f953a-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f953a-118">De invoegtoepassing Rapportbericht werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="f953a-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="f953a-119">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f953a-119">Outlook on the web</span></span>
  - <span data-ttu-id="f953a-120">Outlook 2013 SP1 of hoger</span><span class="sxs-lookup"><span data-stu-id="f953a-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="f953a-121">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="f953a-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="f953a-122">Outlook opgenomen in Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="f953a-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="f953a-123">De invoegtoepassing Rapportbericht is momenteel niet beschikbaar voor:</span><span class="sxs-lookup"><span data-stu-id="f953a-123">The Report Message add-in is currently not available for:</span></span>

  - <span data-ttu-id="f953a-124">Postvakken in on-premises Exchange-organisaties</span><span class="sxs-lookup"><span data-stu-id="f953a-124">Mailboxes in on-premises Exchange organizations</span></span>
  - <span data-ttu-id="f953a-125">GCC-, GCC HIGH- of DoD-abonnementen</span><span class="sxs-lookup"><span data-stu-id="f953a-125">GCC, GCC HIGH, or DoD subscriptions</span></span>

- <span data-ttu-id="f953a-126">Uw bestaande webbrowser moet werken met de invoegtoepassing Bericht rapporteren.</span><span class="sxs-lookup"><span data-stu-id="f953a-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="f953a-127">Maar als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="f953a-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="f953a-128">Voor organisatorische installaties moet de organisatie worden geconfigureerd om OAuth-verificatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="f953a-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="f953a-129">Zie [Bepalen of gecentraliseerde implementatie van invoegingen voor uw organisatie werkt](../../admin/manage/centralized-deployment-of-add-ins.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f953a-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="f953a-130">Beheerders moeten lid zijn van de rolgroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="f953a-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="f953a-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="f953a-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f953a-132">De invoegtoepassing Rapportbericht zelf opvragen</span><span class="sxs-lookup"><span data-stu-id="f953a-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f953a-133">Ga naar de Microsoft <https://appsource.microsoft.com/marketplace/apps> AppSource bij en zoek naar de invoegtoepassing Bericht rapport.</span><span class="sxs-lookup"><span data-stu-id="f953a-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="f953a-134">Ga naar <https://appsource.microsoft.com/product/office/wa104381180>.</span><span class="sxs-lookup"><span data-stu-id="f953a-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="f953a-135">Klik **op NU KRIJGEN.**</span><span class="sxs-lookup"><span data-stu-id="f953a-135">Click **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu verzenden](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="f953a-137">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f953a-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="f953a-138">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="f953a-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f953a-139">Nadat de invoegtoepassing is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f953a-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f953a-140">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f953a-140">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing Bericht rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f953a-142">In de webversie van Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f953a-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing Van het webrapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f953a-144">Zie [De invoegtoepassing Rapportbericht gebruiken](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)voor meer informatie over het gebruik van de invoegtoepassing Rapport.</span><span class="sxs-lookup"><span data-stu-id="f953a-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f953a-145">De invoegtoepassing Rapportbericht voor uw organisatie opvragen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="f953a-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="f953a-146">Het kan tot 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f953a-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="f953a-147">Ga in het Microsoft 365-beheercentrum naar de pagina <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **Services &-invoegtoepassing** op , en klik vervolgens op **Invoegtoepassing implementeren**.</span><span class="sxs-lookup"><span data-stu-id="f953a-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Pagina Services en invoegtoepassing in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f953a-149">Bekijk de informatie in de flyout Implementeren die wordt weergegeven door een nieuwe flyout voor **invoeging** en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f953a-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="f953a-150">Klik op de volgende pagina op **Kiezen uit de Store**.</span><span class="sxs-lookup"><span data-stu-id="f953a-150">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="f953a-152">Klik op de **invoegpagina Selecteren** die wordt weergegeven in het vak **Zoeken,** voer **Bericht melden**in en klik vervolgens op Zoekpictogram](../../media/search-icon.png) **zoeken** ![.</span><span class="sxs-lookup"><span data-stu-id="f953a-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="f953a-153">Zoek in de lijst met resultaten **rapportbericht** en klik op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f953a-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Invoegzoekresultaten selecteren](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="f953a-155">Bekijk in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="f953a-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="f953a-156">Configureer de volgende instellingen op de pagina **Invoegpagina configureren** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="f953a-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="f953a-157">**Toegewezen gebruikers**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f953a-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="f953a-158">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="f953a-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="f953a-159">**Specifieke gebruikers /groepen**</span><span class="sxs-lookup"><span data-stu-id="f953a-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="f953a-160">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="f953a-160">**Just me**</span></span>

   - <span data-ttu-id="f953a-161">**Implementatiemethode:** Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="f953a-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="f953a-162">**Fixed (Default)**: De invoegtoepassing wordt automatisch geïmplementeerd bij de opgegeven gebruikers en deze kunnen niet worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="f953a-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="f953a-163">**Beschikbaar:** Gebruikers kunnen de add-in installeren bij **Home** \> **Get-ins** \> **Admin-managed**.</span><span class="sxs-lookup"><span data-stu-id="f953a-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="f953a-164">**Optioneel**: de invoegtoepassing wordt automatisch geïmplementeerd bij de opgegeven gebruikers, maar ze kunnen ervoor kiezen om de invoeging te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f953a-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="f953a-166">Klik op **Implementeren**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="f953a-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="f953a-167">Op de pagina **Bericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="f953a-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="f953a-168">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f953a-168">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="f953a-170">Bekijk de informatie op de **invoegpagina aankondigen** die wordt weergegeven en klik op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="f953a-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

### <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f953a-172">Meer informatie over het gebruik van de invoegtoepassing Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="f953a-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f953a-173">Mensen die de invoegtoepassing aan hen hebben toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f953a-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="f953a-174">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f953a-174">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing rapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f953a-176">In de webversie van Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f953a-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing van het Web-rapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="f953a-178">Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing Bericht melden, voegt u een koppeling toe naar [De invoegtoepassing Rapportbericht gebruiken.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f953a-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

### <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f953a-179">Instellingen voor de invoegtoepassing Rapportbericht controleren of bewerken</span><span class="sxs-lookup"><span data-stu-id="f953a-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="f953a-180">Ga in het Microsoft 365-beheercentrum naar de pagina <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> **Services &-invoegtoepassing** op .</span><span class="sxs-lookup"><span data-stu-id="f953a-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Pagina Services en invoegtoepassing in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f953a-182">Zoek en selecteer de **invoegtoepassing Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="f953a-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="f953a-183">Bekijk en bewerk de instellingen waar nodig voor uw organisatie in de flyout **Van rapportbericht bewerken** die wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="f953a-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="f953a-184">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="f953a-184">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoegtoepassing Rapportbericht](../../media/EditReportMessageAddIn.png)
