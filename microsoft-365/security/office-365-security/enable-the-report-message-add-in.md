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
description: Meer informatie over het inschakelen van de invoegtoepassing Report Message voor Outlook en Outlook op de web, voor individuele gebruikers of uw hele organisatie.
ms.openlocfilehash: 2b074d1bd260f5c95d138577e259aee14ec9e8d7
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430505"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="a7c8f-103">De invoegtoepassing Bericht rapporteren inschakelen</span><span class="sxs-lookup"><span data-stu-id="a7c8f-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="a7c8f-104">Als u een beheerder bent in een Microsoft 365-organisatie met Exchange Online-postvakken, raden we u aan de portal Inzendingen te gebruiken in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-104">If you're an admin in a Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a7c8f-105">Zie [Beheerdersinzending gebruiken om vermoedelijke spam, phish, URL's en bestanden in te dienen bij Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a7c8f-106">Met de invoegtoepassing Report Message voor Outlook en Outlook op het web (voorheen Bekend als Outlook Web App) kunnen mensen eenvoudig fout-positieven (goede e-mail gemarkeerd als slecht) of valse negatieven (slechte e-mail toegestaan) melden aan Microsoft en haar gelieerde ondernemingen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-106">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report false positives (good email marked as bad) or false negatives (bad email allowed) to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="a7c8f-107">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-107">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span>

<span data-ttu-id="a7c8f-108">Stel dat mensen veel berichten melden als phishing.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-108">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="a7c8f-109">Deze informatie duikt op in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-109">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="a7c8f-110">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat het beleid voor antiphishing mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-110">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="a7c8f-111">Of als mensen veel berichten rapporteren die zijn gemarkeerd als ongewenste e-mail als Niet ongewenste e-mail met behulp van de invoegtoepassing Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk [het antispambeleid](configure-your-spam-filter-policies.md)aanpassen.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-111">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="a7c8f-112">Als uw organisatie bovendien [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) of [Plan 2](office-365-ti.md)gebruikt, biedt de invoegtoepassing Rapportbericht het beveiligingsteam van uw organisatie nuttige informatie die ze kunnen gebruiken om beveiligingsbeleid te controleren en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-112">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="a7c8f-113">Beheerders kunnen de invoegtoepassing Report Message voor de organisatie inschakelen en individuele gebruikers kunnen het zelf installeren.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-113">Admins can enable the Report Message add-in for the organization, and individual users can install it for themselves.</span></span>

<span data-ttu-id="a7c8f-114">Als u een individuele gebruiker bent, u [de invoegtoepassing Report Message zelf inschakelen.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-114">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="a7c8f-115">Als u een globale beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd om OAuth-verificatie te gebruiken, u [de invoegtoepassing Rapportbericht voor uw organisatie inschakelen.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-115">If you're a global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="a7c8f-116">De invoegtoepassing Rapportberichten is nu beschikbaar via [gecentraliseerde implementatie.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-116">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a7c8f-117">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="a7c8f-117">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a7c8f-118">De invoegtoepassing Report Message werkt met de meeste Microsoft 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-118">The Report Message add-in works with most Microsoft 365 subscriptions and the following products:</span></span>

  - <span data-ttu-id="a7c8f-119">Webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="a7c8f-119">Outlook on the web</span></span>
  - <span data-ttu-id="a7c8f-120">SP1 2013 of hoger</span><span class="sxs-lookup"><span data-stu-id="a7c8f-120">Outlook 2013 SP1 or later</span></span>
  - <span data-ttu-id="a7c8f-121">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="a7c8f-121">Outlook 2016 for Mac</span></span>
  - <span data-ttu-id="a7c8f-122">Outlook inbegrepen bij Microsoft 365-apps voor Enterprise</span><span class="sxs-lookup"><span data-stu-id="a7c8f-122">Outlook included with Microsoft 365 apps for Enterprise</span></span>

- <span data-ttu-id="a7c8f-123">De invoegtoepassing Rapportbericht is niet beschikbaar voor postvakken in on-premises Exchange-organisaties.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-123">The Report Message add-in is not available for mailboxes in on-premises Exchange organizations.</span></span>

- <span data-ttu-id="a7c8f-124">U gerapporteerde berichten configureren die moeten worden gekopieerd of doorgestuurd naar een postvak dat u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-124">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="a7c8f-125">Zie [Een postvak opgeven voor gebruikersinzendingen van spam- en phishingberichten in Exchange Online](user-submission.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-125">For more information, see [Specify a mailbox for user submissions of spam and phishing messages in Exchange Online](user-submission.md).</span></span>

- <span data-ttu-id="a7c8f-126">Uw bestaande webbrowser moet werken met de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-126">Your existing web browser should work with the Report Message add-in.</span></span> <span data-ttu-id="a7c8f-127">Maar als u merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, probeer dan een andere browser.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-127">But, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

- <span data-ttu-id="a7c8f-128">Voor organisatorische installaties moet de organisatie worden geconfigureerd om OAuth-verificatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-128">For organizational installs, the organization needs to be configured to use OAuth authentication.</span></span> <span data-ttu-id="a7c8f-129">Zie [Bepalen of Gecentraliseerde implementatie van invoegtoepassingen werkt voor uw organisatie voor](../../admin/manage/centralized-deployment-of-add-ins.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-129">For more information, see [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).</span></span>

- <span data-ttu-id="a7c8f-130">Beheerders moeten lid zijn van de rolgroep Globale beheerders.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-130">Admins need to be a member of the Global admins role group.</span></span> <span data-ttu-id="a7c8f-131">Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-131">For more information, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="a7c8f-132">De invoegtoepassing Rapportbericht voor uzelf ophalen</span><span class="sxs-lookup"><span data-stu-id="a7c8f-132">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="a7c8f-133">Ga naar de Microsoft AppSource bij <https://appsource.microsoft.com/marketplace/apps> en zoek naar de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-133">Go to the Microsoft AppSource at <https://appsource.microsoft.com/marketplace/apps> and search for the Report Message add-in.</span></span> <span data-ttu-id="a7c8f-134">Ga naar <https://appsource.microsoft.com/product/office/wa104381180> .</span><span class="sxs-lookup"><span data-stu-id="a7c8f-134">To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180>.</span></span>

2. <span data-ttu-id="a7c8f-135">Klik **op NU ophalen.**</span><span class="sxs-lookup"><span data-stu-id="a7c8f-135">Click **GET IT NOW**.</span></span>

   ![Bericht melden - Nu ophalen](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="a7c8f-137">Bekijk in het dialoogvenster dat wordt weergegeven de gebruiksvoorwaarden en het privacybeleid en klik op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-137">In the dialog that appears, review the terms of use and privacy policy, and then click **Continue**.</span></span>

4. <span data-ttu-id="a7c8f-138">Meld u aan met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="a7c8f-138">Sign in using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="a7c8f-139">Nadat de invoegtoepassing is geïnstalleerd en is ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-139">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="a7c8f-140">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-140">In Outlook, the icon looks like this:</span></span>

  ![Invoegpictogram Bericht rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a7c8f-142">In de webversie van Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-142">In Outlook on the web, the icon looks like this:</span></span>

  ![Invoegpictogram webbericht rapporteren](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a7c8f-144">Zie De invoegtoepassing Rapportbericht gebruiken voor meer informatie over het gebruik van [de invoegtoepassing](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="a7c8f-144">To learn how to use the add-in, see [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="a7c8f-145">De invoegtoepassing Rapportbericht voor uw organisatie ophalen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="a7c8f-145">Get and enable the Report Message add-in for your organization</span></span>

> [!NOTE]
> <span data-ttu-id="a7c8f-146">Het kan tot 12 uur duren voordat de invoegtoepassing in uw organisatie wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-146">It could take up to 12 hours for the add-in to appear in your organization.</span></span>

1. <span data-ttu-id="a7c8f-147">Ga in het Microsoft 365-beheercentrum naar de pagina **Services & invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> en klik vervolgens op **Invoegtoepassing implementeren**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-147">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>, and then click **Deploy Add-In**.</span></span>

   ![Pagina Services en invoegtoepassingen in het Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="a7c8f-149">Bekijk de informatie in de **flyout Voor de invoegtoepassing implementeren** die wordt weergegeven en controleer de informatie en klik vervolgens op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-149">In the **Deploy a new add-in** flyout that appears, review the information, and then click **Next**.</span></span>

3. <span data-ttu-id="a7c8f-150">Klik op de volgende pagina op **Kiezen uit de Winkel**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-150">On the next page, click **Choose from the Store**.</span></span>

   ![Een nieuwe invoegpagina implementeren](../../media/NewAddInScreen2.png)

4. <span data-ttu-id="a7c8f-152">Klik op de **invoegtoepassingspagina selecteren** die wordt weergegeven in het vak **Zoeken,** voer **Rapportbericht**in en **klik** vervolgens op ![ Zoekzoeken. ](../../media/search-icon.png)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-152">In the **Select add-in** page that appears, click in the **Search** box, enter **Report Message**, and then click **Search** ![Search icon](../../media/search-icon.png).</span></span> <span data-ttu-id="a7c8f-153">Zoek **rapportbericht** in de lijst met resultaten en klik vervolgens op **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-153">In the list of results, find **Report Message** and then click **Add**.</span></span>

   ![Invoegtoepassingszoeken selecteren](../../media/NewAddInScreen3.png)

5. <span data-ttu-id="a7c8f-155">Bekijk in het dialoogvenster dat wordt weergegeven de licentie- en privacygegevens en klik op **Doorgaan**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-155">In the dialog that appears, review the licensing and privacy information, and then click **Continue**.</span></span>

6. <span data-ttu-id="a7c8f-156">Configureer de volgende instellingen op de **invoegpagina configureren** die wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-156">In the **Configure add-in** page that appears, configure the following settings:</span></span>

   - <span data-ttu-id="a7c8f-157">**Toegewezen gebruikers**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-157">**Assigned users**: Select one of the following values:</span></span>

     - <span data-ttu-id="a7c8f-158">**Iedereen** (standaard)</span><span class="sxs-lookup"><span data-stu-id="a7c8f-158">**Everyone** (default)</span></span>
     - <span data-ttu-id="a7c8f-159">**Specifieke gebruikers/groepen**</span><span class="sxs-lookup"><span data-stu-id="a7c8f-159">**Specific users / groups**</span></span>
     - <span data-ttu-id="a7c8f-160">**Alleen ik**</span><span class="sxs-lookup"><span data-stu-id="a7c8f-160">**Just me**</span></span>

   - <span data-ttu-id="a7c8f-161">**Implementatiemethode**: Selecteer een van de volgende waarden:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-161">**Deployment method**: Select one of the following values:</span></span>

     - <span data-ttu-id="a7c8f-162">**Opgelost (Standaard)**: De invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers en deze kan deze niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-162">**Fixed (Default)**: The add-in is automatically deployed to the specified users and they can't remove it.</span></span>
     - <span data-ttu-id="a7c8f-163">**Beschikbaar**: Gebruikers kunnen de invoegtoepassing **thuis** \> **installeren Door invoegtoepassingen** \> **beheerde beheerder.**</span><span class="sxs-lookup"><span data-stu-id="a7c8f-163">**Available**: Users can install the add-in at **Home** \> **Get add-ins** \> **Admin-managed**.</span></span>
     - <span data-ttu-id="a7c8f-164">**Optioneel**: De invoegtoepassing wordt automatisch geïmplementeerd voor de opgegeven gebruikers, maar ze kunnen ervoor kiezen deze te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-164">**Optional**: The add-in is automatically deployed to the specified users, but they can choose to remove it.</span></span>

   ![Invoegpagina configureren](../../media/configure-add-in.png)

   <span data-ttu-id="a7c8f-166">Klik op **Implementeren**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-166">When you're finished, click **Deploy**.</span></span>

7. <span data-ttu-id="a7c8f-167">Op de pagina **Rapportbericht implementeren** dat wordt weergegeven, ziet u een voortgangsrapport, gevolgd door een bevestiging dat de invoegtoepassing is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-167">In the **Deploy Report Message** page that appears, you'll see a progress report followed by a confirmation that the add-in was deployed.</span></span> <span data-ttu-id="a7c8f-168">Nadat u de informatie hebt gelezen, klikt u op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-168">After you read the information, click **Next**.</span></span>

   ![Pagina Rapportbericht implementeren](../../media/deploy-report-message-page.png)

8. <span data-ttu-id="a7c8f-170">Bekijk de informatie op de **invoegtoepassingspagina aankondigen** en klik vervolgens op **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-170">On the **Announce add-in** page that appears, review the information, and then click **Close**.</span></span>

   ![Invoegpagina aankondigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="a7c8f-172">Meer informatie over het gebruik van de invoegtoepassing Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="a7c8f-172">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="a7c8f-173">Mensen die de invoegtoepassing aan hen hebben toegewezen, zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-173">People who have the add-in assigned to them will see the following icons:</span></span>

- <span data-ttu-id="a7c8f-174">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-174">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing rapportbericht voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="a7c8f-176">In de webversie van Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-176">In Outlook on the web, the icon looks like this:</span></span>

  ![Invoegtoepassingspictogram Webrapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

<span data-ttu-id="a7c8f-178">Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing Rapportbericht, voegt u een koppeling toe naar [De invoegtoepassing Rapportbericht](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)gebruiken .</span><span class="sxs-lookup"><span data-stu-id="a7c8f-178">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="a7c8f-179">Instellingen voor de invoegtoepassing Rapportbericht controleren of bewerken</span><span class="sxs-lookup"><span data-stu-id="a7c8f-179">Review or edit settings for the Report Message add-in</span></span>

1. <span data-ttu-id="a7c8f-180">Ga in het Microsoft 365-beheercentrum naar de pagina **Services &-invoegtoepassingen** op <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .</span><span class="sxs-lookup"><span data-stu-id="a7c8f-180">In the Microsoft 365 admin center, go to the **Services & add-ins** page at <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns>.</span></span>

   ![Pagina Services en invoegtoepassingen in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="a7c8f-182">Zoek en selecteer de invoegtoepassing **Rapportbericht.**</span><span class="sxs-lookup"><span data-stu-id="a7c8f-182">Find and select the **Report Message** add-in.</span></span>

3. <span data-ttu-id="a7c8f-183">Controleer en bewerk instellingen in de flyout **Rapportbericht bewerken** die wordt weergegeven, en bewerk deze zo geschikt voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-183">In the **Edit Report Message** flyout that appears, review and edit settings as appropriate for your organization.</span></span> <span data-ttu-id="a7c8f-184">Klik op **Opslaan** wanneer u gereed bent.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-184">When you're finished, click **Save**.</span></span>

   ![Instellingen voor de invoegtoepassing Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a><span data-ttu-id="a7c8f-186">Gerapporteerde berichten bekijken en bekijken</span><span class="sxs-lookup"><span data-stu-id="a7c8f-186">View and review reported messages</span></span>

<span data-ttu-id="a7c8f-187">Als u berichten wilt bekijken die gebruikers aan Microsoft rapporteren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="a7c8f-187">To review messages that users report to Microsoft, you have these options:</span></span>

- <span data-ttu-id="a7c8f-188">Gebruik de portal Beheerdersinzendingen.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-188">Use the Admin Submissions portal.</span></span> <span data-ttu-id="a7c8f-189">[Zie Gebruikersinzendingen weergeven bij Microsoft](admin-submission.md#view-user-submissions-to-microsoft)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-189">For more information, see [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).</span></span>

- <span data-ttu-id="a7c8f-190">Maak een e-mailstroomregel (ook wel een transportregel genoemd) om kopieën van gerapporteerde berichten te verzenden.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-190">Create a mail flow rule (also known as a transport rule) to send copies of reported messages.</span></span> <span data-ttu-id="a7c8f-191">Zie Regels [voor e-mailstromen gebruiken om te zien wat uw gebruikers aan Microsoft rapporteren](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="a7c8f-191">For instructions, see [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).</span></span>
