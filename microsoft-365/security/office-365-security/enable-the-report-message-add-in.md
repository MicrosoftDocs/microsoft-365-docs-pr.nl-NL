---
title: De invoegtoepassing Rapportbericht inschakelen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
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
ms.openlocfilehash: 32b4ab318237ca220b63c87bd4a664cfb69d0b45
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893752"
---
# <a name="enable-the-report-message-add-in"></a><span data-ttu-id="f688a-103">De invoegtoepassing Rapportbericht inschakelen</span><span class="sxs-lookup"><span data-stu-id="f688a-103">Enable the Report Message add-in</span></span>

> [!NOTE]
> <span data-ttu-id="f688a-104">De invoegtoepassing Rapportbericht voor Outlook en Outlook op de web is niet precies hetzelfde als het [Outlook Junk Email-filter,](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)hoewel beide kunnen worden gebruikt om e-mail te markeren als ongewenste e-mail, geen ongewenste e-mail of een phishing-poging.</span><span class="sxs-lookup"><span data-stu-id="f688a-104">The Report Message add-in for Outlook and Outlook on the web is not exactly the same thing as the [Outlook Junk Email Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), although both can be used to mark email as junk, not junk, or a phishing attempt.</span></span> <span data-ttu-id="f688a-105">Het verschil is dat de invoegtoepassing Bericht rapport voor Outlook en Outlook op het web Microsoft informeert over verkeerd geclassificeerde e-mail, terwijl het Outlook Junk Email Filter wordt gebruikt om e-mailberichten in het postvak van een gebruiker te ordenen.</span><span class="sxs-lookup"><span data-stu-id="f688a-105">The difference is, the Report Message add-in for Outlook and Outlook on the web notifies Microsoft about misclassified email, whereas the Outlook Junk Email Filter is used to organize email messages in a user's mailbox.</span></span>

## <a name="overview"></a><span data-ttu-id="f688a-106">Overzicht</span><span class="sxs-lookup"><span data-stu-id="f688a-106">Overview</span></span>

<span data-ttu-id="f688a-107">Met de invoegtoepassing Rapportbericht voor Outlook en Outlook op de web (voorheen Outlook Web App) kunnen mensen eenvoudig verkeerd geclassificeerde e-mail, veilig of kwaadaardig, melden aan Microsoft en haar gelieerde ondernemingen voor analyse.</span><span class="sxs-lookup"><span data-stu-id="f688a-107">The Report Message add-in for Outlook and Outlook on the web (formerly known as Outlook Web App) enables people to easily report misclassified email, whether safe or malicious, to Microsoft and its affiliates for analysis.</span></span> <span data-ttu-id="f688a-108">Microsoft gebruikt deze inzendingen om de effectiviteit van e-mailbeveiligingstechnologieën te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="f688a-108">Microsoft uses these submissions to improve the effectiveness of email protection technologies.</span></span> <span data-ttu-id="f688a-109">Als uw organisatie bovendien [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) of Plan [2](office-365-ti.md)gebruikt, biedt de invoegtoepassing Rapportbericht het beveiligingsteam van uw organisatie nuttige informatie die ze kunnen gebruiken om het beveiligingsbeleid te bekijken en bij te werken.</span><span class="sxs-lookup"><span data-stu-id="f688a-109">In addition, if your organization is using [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) or [Plan 2](office-365-ti.md), the Report Message add-in provides your organization's security team with useful information they can use to review and update security policies.</span></span>

<span data-ttu-id="f688a-110">Stel dat mensen veel berichten melden als phishing.</span><span class="sxs-lookup"><span data-stu-id="f688a-110">For example, suppose that people are reporting a lot of messages as phishing.</span></span> <span data-ttu-id="f688a-111">Deze informatie wordt weergegeven in het [beveiligingsdashboard](security-dashboard.md) en andere rapporten.</span><span class="sxs-lookup"><span data-stu-id="f688a-111">This information surfaces in the [Security Dashboard](security-dashboard.md) and other reports.</span></span> <span data-ttu-id="f688a-112">Het beveiligingsteam van uw organisatie kan deze informatie gebruiken als een indicatie dat het antiphishingbeleid mogelijk moet worden bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="f688a-112">Your organization's security team can use this information as an indication that anti-phishing policies might need to be updated.</span></span> <span data-ttu-id="f688a-113">Als mensen veel berichten rapporteren die als ongewenste e-mail zijn gemarkeerd als Niet-ongewenstee e-mail met behulp van de invoegtoepassing Rapportbericht, moet het beveiligingsteam van uw organisatie mogelijk [het antispambeleid](configure-your-spam-filter-policies.md)aanpassen.</span><span class="sxs-lookup"><span data-stu-id="f688a-113">Or, if people are reporting a lot of messages that were flagged as junk mail as Not Junk by using the Report Message add-in, your organization's security team might need to adjust [anti-spam policies](configure-your-spam-filter-policies.md).</span></span>

<span data-ttu-id="f688a-114">De invoegtoepassing Rapportbericht werkt met de meeste Office 365-abonnementen en de volgende producten:</span><span class="sxs-lookup"><span data-stu-id="f688a-114">The Report Message add-in works with most Office 365 subscriptions and the following products:</span></span>

- <span data-ttu-id="f688a-115">De webversie van Outlook</span><span class="sxs-lookup"><span data-stu-id="f688a-115">Outlook on the web</span></span>
- <span data-ttu-id="f688a-116">Outlook 2013 SP1</span><span class="sxs-lookup"><span data-stu-id="f688a-116">Outlook 2013 SP1</span></span>
- <span data-ttu-id="f688a-117">Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f688a-117">Outlook 2016</span></span>
- <span data-ttu-id="f688a-118">Outlook 2016 voor Mac</span><span class="sxs-lookup"><span data-stu-id="f688a-118">Outlook 2016 for Mac</span></span>
- <span data-ttu-id="f688a-119">Outlook inbegrepen bij Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="f688a-119">Outlook included with Office 365 ProPlus</span></span>

<span data-ttu-id="f688a-120">De invoegtoepassing Rapportbericht is momenteel niet beschikbaar voor:</span><span class="sxs-lookup"><span data-stu-id="f688a-120">The Report Message add-in is currently not available for:</span></span>

- <span data-ttu-id="f688a-121">Postvakken in on-premises Exchange-organisaties</span><span class="sxs-lookup"><span data-stu-id="f688a-121">Mailboxes in on-premises Exchange organizations</span></span>
- <span data-ttu-id="f688a-122">GCC-, GCC HIGH- of DoD-abonnementen</span><span class="sxs-lookup"><span data-stu-id="f688a-122">GCC, GCC HIGH, or DoD subscriptions</span></span>

<span data-ttu-id="f688a-123">Uw bestaande webbrowser moet volstaan om de invoegtoepassing Rapportbericht te laten werken. Als u echter merkt dat de invoegtoepassing niet beschikbaar is of niet werkt zoals verwacht, probeert u een andere browser.</span><span class="sxs-lookup"><span data-stu-id="f688a-123">Your existing web browser should suffice for the Report Message add-in to work; however, if you notice the add-in is not available or not working as expected, try a different browser.</span></span>

<span data-ttu-id="f688a-124">Als u een individuele gebruiker bent, u [de invoegtoepassing Bericht melden voor uzelf inschakelen.](#get-the-report-message-add-in-for-yourself)</span><span class="sxs-lookup"><span data-stu-id="f688a-124">If you're an individual user, you can [enable the Report Message add-in for yourself](#get-the-report-message-add-in-for-yourself).</span></span>

<span data-ttu-id="f688a-125">Als u een globale office 365-beheerder of een Exchange Online-beheerder bent en Exchange is geconfigureerd om OAuth-verificatie te gebruiken, u [de invoegtoepassing Bericht melden voor uw organisatie inschakelen.](#get-and-enable-the-report-message-add-in-for-your-organization)</span><span class="sxs-lookup"><span data-stu-id="f688a-125">If you're an Office 365 global administrator or an Exchange Online administrator, and Exchange is configured to use OAuth authentication, you can [enable the Report Message add-in for your organization](#get-and-enable-the-report-message-add-in-for-your-organization).</span></span> <span data-ttu-id="f688a-126">De invoegtoepassing Rapportbericht is nu beschikbaar via [gecentraliseerde implementatie.](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="f688a-126">The Report Message Add-In is now available through [Centralized Deployment](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

## <a name="get-the-report-message-add-in-for-yourself"></a><span data-ttu-id="f688a-127">De invoegtoepassing Rapportbericht zelf opvragen</span><span class="sxs-lookup"><span data-stu-id="f688a-127">Get the Report Message add-in for yourself</span></span>

1. <span data-ttu-id="f688a-128">Zoek in [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)naar de [invoegtoepassing Bericht](https://appsource.microsoft.com/product/office/wa104381180)rapport .</span><span class="sxs-lookup"><span data-stu-id="f688a-128">In [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps), search for the [Report Message add-in](https://appsource.microsoft.com/product/office/wa104381180).</span></span>

2. <span data-ttu-id="f688a-129">Kies **GET IT NOW**.</span><span class="sxs-lookup"><span data-stu-id="f688a-129">Choose **GET IT NOW**.</span></span>

   ![Rapportbericht - Nu verzenden](../../media/ReportMessageGETITNOW.png)

3. <span data-ttu-id="f688a-131">Bekijk de gebruiksvoorwaarden en het privacybeleid.</span><span class="sxs-lookup"><span data-stu-id="f688a-131">Review the terms of use and privacy policy.</span></span> <span data-ttu-id="f688a-132">Kies **Continue**.</span><span class="sxs-lookup"><span data-stu-id="f688a-132">Then choose **Continue**.</span></span>

4. <span data-ttu-id="f688a-133">Meld u aan bij Office 365 met uw werk- of schoolaccount (voor zakelijk gebruik) of uw Microsoft-account (voor persoonlijk gebruik).</span><span class="sxs-lookup"><span data-stu-id="f688a-133">Sign in to Office 365 using your work or school account (for business use) or your Microsoft account (for personal use).</span></span>

<span data-ttu-id="f688a-134">Nadat de invoegtoepassing is geïnstalleerd en ingeschakeld, ziet u de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f688a-134">After the add-in is installed and enabled, you'll see the following icons:</span></span>

- <span data-ttu-id="f688a-135">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f688a-135">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing Bericht rapporteren voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f688a-137">In de webversie van Outlook (voorheen Outlook Web App) ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f688a-137">In Outlook on the web (formerly known as Outlook Web App), the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing Van het webrapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="f688a-139">Lees als volgende stap hoe [u de invoegtoepassing Rapportbericht](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)gebruikt .</span><span class="sxs-lookup"><span data-stu-id="f688a-139">As a next step, learn how to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a><span data-ttu-id="f688a-140">De invoegtoepassing Rapportbericht voor uw organisatie opvragen en inschakelen</span><span class="sxs-lookup"><span data-stu-id="f688a-140">Get and enable the Report Message add-in for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f688a-141">U moet een globale office 365-beheerder of een Exchange Online-beheerder zijn om deze taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f688a-141">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span> <span data-ttu-id="f688a-142">Bovendien moet Exchange zijn geconfigureerd om OAuth-verificatie te gebruiken Voor meer informatie, zie [Exchange-vereisten (Gecentraliseerde implementatie van invoegingen)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span><span class="sxs-lookup"><span data-stu-id="f688a-142">In addition, Exchange must be configured to use OAuth authentication To learn more, see [Exchange requirements (Centralized Deployment of add-ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).</span></span>

1. <span data-ttu-id="f688a-143">Ga naar de [pagina Services &-invoegtoepassing](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f688a-143">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Pagina Services en invoegtoepassing in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f688a-145">Kies **+ Invoegtoepassing implementeren**.</span><span class="sxs-lookup"><span data-stu-id="f688a-145">Choose **+ Deploy Add-in**.</span></span>

   ![Invoegtoepassing implementeren kiezen](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. <span data-ttu-id="f688a-147">Bekijk de informatie in het scherm **Nieuwe invoegtoepassing** en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f688a-147">In the **New Add-In** screen, review the information, and then choose **Next**.</span></span>

   ![Nieuwe invoeggegevens](../../media/NewAddInScreen1.png)

4. <span data-ttu-id="f688a-149">Selecteer **Ik wil een invoegtoepassing toevoegen in de Office Store**en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f688a-149">Select **I want to add an Add-In from the Office Store**, and then choose **Next**.</span></span>

   ![Ik wil een nieuwe invoegtoepassing toevoegen](../../media/NewAddInScreen2.png)

5. <span data-ttu-id="f688a-151">Zoek naar **Rapportbericht**en kies in de lijst met resultaten naast de **invoegtoepassing Rapportbericht**de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="f688a-151">Search for **Report Message**, and in the list of results, next to the **Report Message Add-In**, choose **Add**.</span></span>

   ![Zoeken naar Rapportbericht en vervolgens Toevoegen kiezen](../../media/NewAddInScreen3.png)

6. <span data-ttu-id="f688a-153">Bekijk in het scherm **Bericht melden** de informatie en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f688a-153">On the **Report Message** screen, review the information, and then choose **Next**.</span></span>

   ![Details van berichtberichten](../../media/ReportMessageAdd-InNewScreen4.png)

7. <span data-ttu-id="f688a-155">Geef de standaardinstellingen van de gebruiker voor Outlook op en kies **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="f688a-155">Specify the user default settings for Outlook, and  then choose **Next**.</span></span>

   ![Standaardinstellingen voor berichten rapporteren voor Outlook](../../media/ReportMessageOptionsScreen5.png)

8. <span data-ttu-id="f688a-157">Geef op wie de invoegtoepassing Rapportbericht krijgt en kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f688a-157">Specify who gets the Report Message Add-in, and then choose **Save**.</span></span>

   ![Wie krijgt de invoegtoepassing Rapportbericht](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> <span data-ttu-id="f688a-159">We raden u aan [een regel in te stellen om een kopie van e-mailberichten te laten melden door uw gebruikers.](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users)</span><span class="sxs-lookup"><span data-stu-id="f688a-159">We recommend [setting up a rule to get a copy of email messages reported by your users](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).</span></span>

<span data-ttu-id="f688a-160">Afhankelijk van wat u hebt geselecteerd wanneer u de invoegtoepassing (stap 7-8 hierboven) instelt, hebben mensen in uw organisatie de [invoegtoepassing Rapportbericht](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="f688a-160">Depending on what you selected when you set up the add-in (steps 7-8 above), people in your organization will have the [Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) available.</span></span> <span data-ttu-id="f688a-161">Mensen in uw organisatie zien de volgende pictogrammen:</span><span class="sxs-lookup"><span data-stu-id="f688a-161">People in your organization will see the following icons:</span></span>

- <span data-ttu-id="f688a-162">In Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f688a-162">In Outlook, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing rapport voor Outlook](../../media/OutlookReportMessageIcon.png)

- <span data-ttu-id="f688a-164">In de webversie van Outlook ziet het pictogram er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="f688a-164">In Outlook on the web, the icon looks like this:</span></span>

  ![Pictogram Invoegtoepassing van het Web-rapportbericht](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> <span data-ttu-id="f688a-166">Wanneer u gebruikers op de hoogte stelt van de invoegtoepassing Bericht melden, voegt u een koppeling toe naar [De invoegtoepassing Rapportbericht gebruiken.](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span><span class="sxs-lookup"><span data-stu-id="f688a-166">When you notify users about the Report Message add-in, include a link to [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a><span data-ttu-id="f688a-167">Een regel instellen om een kopie van e-mailberichten te laten melden door uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="f688a-167">Set up a rule to get a copy of email messages reported by your users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f688a-168">U moet een Exchange Online-beheerder zijn om deze taak uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="f688a-168">You must be an Exchange Online Administrator to perform this task.</span></span>

<span data-ttu-id="f688a-169">U een regel instellen om een kopie van e-mailberichten te laten melden door gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f688a-169">You can set up a rule to get a copy of email messages reported by users in your organization.</span></span> <span data-ttu-id="f688a-170">U doet dit nadat u de invoegtoepassing Rapportbericht voor uw organisatie hebt gedownload en ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="f688a-170">You do this after you have downloaded and enabled the Report Message add-in for your organization.</span></span>

1. <span data-ttu-id="f688a-171">Kies in het Exchange-beheercentrum **de regels voor e-mailstroom** \> **rules**.</span><span class="sxs-lookup"><span data-stu-id="f688a-171">In the Exchange admin center, choose **mail flow** \> **rules**.</span></span>

2. <span data-ttu-id="f688a-172">Kies **+** \> **Een nieuwe regel maken**.</span><span class="sxs-lookup"><span data-stu-id="f688a-172">Choose **+** \> **Create a new rule**.</span></span>

3. <span data-ttu-id="f688a-173">Typ **in** het vak Naam een naam, zoals Inzendingen.</span><span class="sxs-lookup"><span data-stu-id="f688a-173">In the **Name** box, type a name, such as Submissions.</span></span>

4. <span data-ttu-id="f688a-174">Kies De **geadresseerdeadres bevat in**de lijst **Deze regel toepassen als** deze lijst bevat... .</span><span class="sxs-lookup"><span data-stu-id="f688a-174">In the **Apply this rule if** list, choose **The recipient address includes...**.</span></span>

5. <span data-ttu-id="f688a-175">Voeg in het scherm Woorden `junk@office365.microsoft.com` of `phish@office365.microsoft.com` **woordgroepen opgeven** toe en kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="f688a-175">In the **specify words or phrases** screen, add `junk@office365.microsoft.com` and `phish@office365.microsoft.com`, and then choose **OK**.</span></span>

   ![De ongewenste e-mailadressen en phish-adressen voor de regel opgeven](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. <span data-ttu-id="f688a-177">Kies **Do the following...** **bcc het bericht naar...**.</span><span class="sxs-lookup"><span data-stu-id="f688a-177">In the **Do the following...** list, choose **Bcc the message to...**.</span></span>

7. <span data-ttu-id="f688a-178">Voeg een globale beheerder, beveiligingsbeheerder en/of beveiligingslezer toe die een kopie van elk e-mailbericht moet ontvangen dat mensen aan Microsoft rapporteren en kies **OK.**</span><span class="sxs-lookup"><span data-stu-id="f688a-178">Add a global administrator, security administrator, and/or security reader who should receive a copy of each email message that people report to Microsoft, and then choose **OK**.</span></span>

   ![Een globale of beveiligingsbeheerder toevoegen om een kopie van elk gerapporteerd bericht te ontvangen](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. <span data-ttu-id="f688a-180">Selecteer **Deze regel controleren met ernstniveau**en kies **Gemiddeld**.</span><span class="sxs-lookup"><span data-stu-id="f688a-180">Select **Audit this rule with severity level**, and choose **Medium**.</span></span>

9. <span data-ttu-id="f688a-181">Kies **onder Een modus kiezen voor deze regel**de optie **Afdwingen**.</span><span class="sxs-lookup"><span data-stu-id="f688a-181">Under **Choose a mode for this rule**, choose **Enforce**.</span></span>

   ![Een regel instellen om een kopie van elk gerapporteerd bericht te krijgen](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. <span data-ttu-id="f688a-183">Selecteer **Save**.</span><span class="sxs-lookup"><span data-stu-id="f688a-183">Choose **Save**.</span></span>

<span data-ttu-id="f688a-184">Wanneer iemand in uw organisatie een e-mailbericht meldt met de invoegtoepassing Rapportbericht, ontvangt uw globale beheerder, beveiligingsbeheerder en/of beveiligingslezer een kopie van dat bericht wanneer iemand in uw organisatie een e-mailbericht meldt met de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="f688a-184">With this rule in place, whenever someone in your organization reports an email message using the Report Message add-in, your global administrator, security administrator, and/or security reader will receive a copy of that message.</span></span> <span data-ttu-id="f688a-185">Met deze informatie u beleid instellen of aanpassen, zoals het beleid voor [veilige koppelingen van Office 365](atp-safe-links.md) OF uw [antispaminstellingen.](anti-spam-protection.md)</span><span class="sxs-lookup"><span data-stu-id="f688a-185">This information can enable you to set up or adjust policies, such as [Office 365 ATP Safe Links](atp-safe-links.md) policies, or your [anti-spam](anti-spam-protection.md) settings.</span></span>

## <a name="learn-how-to-use-the-report-message-add-in"></a><span data-ttu-id="f688a-186">Meer informatie over het gebruik van de invoegtoepassing Rapportbericht</span><span class="sxs-lookup"><span data-stu-id="f688a-186">Learn how to use the Report Message add-in</span></span>

<span data-ttu-id="f688a-187">Zie [De invoegtoepassing Rapportbericht gebruiken](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="f688a-187">See [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span></span>

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a><span data-ttu-id="f688a-188">Instellingen voor de invoegtoepassing Rapportbericht controleren of bewerken</span><span class="sxs-lookup"><span data-stu-id="f688a-188">Review or edit settings for the Report Message add-in</span></span>

<span data-ttu-id="f688a-189">U de standaardinstellingen voor de invoegtoepassing Rapportbericht op de [pagina Services & invoegtoepassing](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)bekijken en bewerken.</span><span class="sxs-lookup"><span data-stu-id="f688a-189">You can review and edit the default settings for the Report Message add-in on the [Services & Add-Ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f688a-190">U moet een globale office 365-beheerder of een Exchange Online-beheerder zijn om deze taak te voltooien.</span><span class="sxs-lookup"><span data-stu-id="f688a-190">You must be an Office 365 global administrator or an Exchange Online Administrator to complete this task.</span></span>

1. <span data-ttu-id="f688a-191">Ga naar de [pagina Services &-invoegtoepassing](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="f688a-191">Go to the [Services & add-ins page](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) in the Microsoft 365 admin center.</span></span>

   ![Pagina Services en invoegtoepassing in het nieuwe Microsoft 365-beheercentrum](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. <span data-ttu-id="f688a-193">Zoek en selecteer de invoegtoepassing Rapportbericht.</span><span class="sxs-lookup"><span data-stu-id="f688a-193">Find and select the Report Message add-in.</span></span>

   ![De invoegtoepassing Rapportbericht zoeken en selecteren](../../media/FindReportMessageAddIn.png)

3. <span data-ttu-id="f688a-195">Bekijk en bewerk de instellingen in het scherm Bericht melden, indien van toepassing voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f688a-195">On the Report Message screen, review and edit settings as appropriate for your organization.</span></span>

   ![Instellingen voor de invoegtoepassing Rapportbericht](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a><span data-ttu-id="f688a-197">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f688a-197">Related topics</span></span>

[<span data-ttu-id="f688a-198">De invoegtoepassing Rapportbericht gebruiken</span><span class="sxs-lookup"><span data-stu-id="f688a-198">Use the Report Message add-in</span></span>](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[<span data-ttu-id="f688a-199">E-mailbeveiligingsrapporten weergeven in het Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f688a-199">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)

[<span data-ttu-id="f688a-200">Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365</span><span class="sxs-lookup"><span data-stu-id="f688a-200">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="f688a-201">Explorer gebruiken in &amp; het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f688a-201">Use Explorer in the Security &amp; Compliance Center</span></span>](threat-explorer.md)
