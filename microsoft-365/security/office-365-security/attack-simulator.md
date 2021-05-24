---
title: Attack Simulator in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze Attack Simulator kunnen gebruiken om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2-organisaties.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 73ad3501ed9818261c9fbec6ba12b4dc884da84f
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624823"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="c4177-103">Attack Simulator in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c4177-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c4177-104">**Van toepassing op** [Microsoft Defender voor Office 365 abonnement 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c4177-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="c4177-105">Als uw organisatie Beschikt over Microsoft Defender voor Office 365 Plan 2, dat mogelijkheden voor bedreigingsonderzoek en antwoord [bevat,](office-365-ti.md)kunt u Attack Simulator gebruiken in het Beveiligings- & Compliancecentrum om realistische aanvalsscenario's in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="c4177-106">Deze gesimuleerde aanvallen kunnen u helpen bij het identificeren en vinden van kwetsbare gebruikers voordat een echte aanval van invloed is op uw bottom line.</span><span class="sxs-lookup"><span data-stu-id="c4177-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="c4177-107">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c4177-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="c4177-108">Attack Simulator zoals beschreven in dit artikel is nu alleen-lezen en is vervangen door **attack-simulatietraining** in het e-mail- **&-samenwerkings** knooppunt in het Microsoft 365 [beveiligingscentrum.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c4177-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="c4177-109">Zie Aan de slag [met de trainingstraining Aanvalssimulatie voor meer informatie.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="c4177-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="c4177-110">De mogelijkheid om nieuwe simulaties te starten vanuit deze versie van Attack Simulator is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="c4177-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="c4177-111">Vanaf 24 januari 2021 hebt u echter nog steeds toegang tot rapporten voor maximaal 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="c4177-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c4177-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="c4177-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c4177-113">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="c4177-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="c4177-114">Attack simulator is beschikbaar op **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="c4177-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="c4177-115">Als u direct naar de aanvalssimulator wilt gaan, opent <https://protection.office.com/attacksimulator> u .</span><span class="sxs-lookup"><span data-stu-id="c4177-115">To go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="c4177-116">Zie Microsoft Defender voor Office 365 servicebeschrijving voor meer informatie over de beschikbaarheid van Attack Simulator Microsoft 365 [verschillende abonnementen.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="c4177-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="c4177-117">U moet lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="c4177-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="c4177-118">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="c4177-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="c4177-119">Uw account moet zijn geconfigureerd voor meervoudige verificatie (MFA) om campagnes te maken en te beheren in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="c4177-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="c4177-120">Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="c4177-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="c4177-121">Attack Simulator werkt alleen in postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="c4177-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="c4177-122">Phishingcampagnes verzamelen en verwerken gebeurtenissen voor 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="c4177-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="c4177-123">Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="c4177-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="c4177-124">Aanvalssimulatie en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365 services.</span><span class="sxs-lookup"><span data-stu-id="c4177-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="c4177-125">Zie voor meer informatie [Microsoft 365 gegevenslocaties.](../../enterprise/o365-data-locations.md)</span><span class="sxs-lookup"><span data-stu-id="c4177-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="c4177-126">Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="c4177-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="c4177-127">Phishingcampagnes voor speer</span><span class="sxs-lookup"><span data-stu-id="c4177-127">Spear phishing campaigns</span></span>

<span data-ttu-id="c4177-128">*Phishing* is een algemene term voor e-mailaanvallen die gevoelige informatie proberen te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="c4177-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="c4177-129">*Phishing via phishing* is een gerichte phishing-aanval die gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de geadresseerden (meestal na verkenning van de geadresseerden door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="c4177-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="c4177-130">In Attack Simulator zijn twee verschillende typen phishingcampagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="c4177-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="c4177-131">**Phishing van de speer (referenties oogst)**: De aanval probeert de geadresseerden te overtuigen om op een URL in het bericht te klikken.</span><span class="sxs-lookup"><span data-stu-id="c4177-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="c4177-132">Als ze op de koppeling klikken, wordt hen gevraagd hun referenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="c4177-133">Als ze dat doen, worden ze naar een van de volgende locaties overgebracht:</span><span class="sxs-lookup"><span data-stu-id="c4177-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="c4177-134">Een standaardpagina waarin wordt uitgelegd dat dit slechts een test was en tips geeft voor het herkennen van phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="c4177-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishingkoppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="c4177-136">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="c4177-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="c4177-137">**Phishing via e-mail (bijlage)**: De aanval probeert de geadresseerden ervan te overtuigen om een bijlage .docx of .pdf in het bericht te openen.</span><span class="sxs-lookup"><span data-stu-id="c4177-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="c4177-138">De bijlage bevat dezelfde inhoud van de standaardkoppeling phishing, maar de eerste zin begint met " , u ziet dit bericht als een recent e-mailbericht \<Display Name\> dat u hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="c4177-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="c4177-139">Momenteel verlopen phishingcampagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="c4177-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="c4177-140">Een phishingcampagne voor een speer maken</span><span class="sxs-lookup"><span data-stu-id="c4177-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="c4177-141">Een belangrijk onderdeel van een phishingcampagne is het uiterlijk van het e-mailbericht dat naar de geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="c4177-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="c4177-142">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="c4177-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="c4177-143">**Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Prijs giveaway** en **Salarisupdate.**</span><span class="sxs-lookup"><span data-stu-id="c4177-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="c4177-144">U kunt sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="c4177-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="c4177-145">**Een herbruikbare e-mailsjabloon** maken: nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="c4177-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="c4177-146">U kunt sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="c4177-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="c4177-147">**Maak het e-mailbericht in de wizard:** U kunt het e-mailbericht rechtstreeks in de wizard maken terwijl u de phishingcampagne voor de speer maakt en start.</span><span class="sxs-lookup"><span data-stu-id="c4177-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="c4177-148">Stap 1 (optioneel): een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="c4177-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="c4177-149">Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="c4177-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="c4177-150">Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="c4177-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c4177-151">Klik op **de pagina** Aanvallen simuleren in de secties Phishing van **de speer (Referenties oogst)** of **In** bijlage op Details van aanvallen **.**</span><span class="sxs-lookup"><span data-stu-id="c4177-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="c4177-152">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="c4177-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="c4177-153">De beschikbare opties in de sjabloon zijn hetzelfde voor beide typen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="c4177-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="c4177-154">Klik op de pagina Aanvalsdetails die wordt geopend in de sectie **Phishingsjablonen** in het gebied **Sjablonen** maken op **Nieuwe sjabloon.** </span><span class="sxs-lookup"><span data-stu-id="c4177-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="c4177-155">De **wizard Phishingsjabloon** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="c4177-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="c4177-156">Voer in **de stap** Start een unieke weergavenaam voor de sjabloon in en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="c4177-157">Configureer **in de stap E-maildetails** configureren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c4177-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="c4177-158">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="c4177-159">**Van (e-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="c4177-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="c4177-160">**URL van de phishing-aanmeldingsserver:** Klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="c4177-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="c4177-161">Dit is de URL waar gebruikers op zullen klikken.</span><span class="sxs-lookup"><span data-stu-id="c4177-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="c4177-162">De keuzen zijn:</span><span class="sxs-lookup"><span data-stu-id="c4177-162">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > <span data-ttu-id="c4177-163">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="c4177-164">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="c4177-165">**Aangepaste landingspagina-URL:** Voer een optionele landingspagina in waarin gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="c4177-166">Deze koppeling vervangt de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="c4177-166">This link replaces the default landing page.</span></span> <span data-ttu-id="c4177-167">Als u bijvoorbeeld training voor interne bewustmaking hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="c4177-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="c4177-168">**Categorie:** Deze instelling wordt momenteel niet gebruikt (alles wat u in typt, wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="c4177-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="c4177-169">**Onderwerp:** Het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="c4177-170">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c4177-171">Maak in **de stap E-mail** opstellen de berichtin body van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="c4177-172">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad Bron** (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c4177-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="c4177-173">De HTML-opmaak kan zo eenvoudig of complex zijn als u dat nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="c4177-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="c4177-174">U kunt afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de geadresseerde te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="c4177-175">`${username}` hiermee voegt u de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="c4177-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="c4177-176">`${loginserverurl}` hiermee voegt u de **URL-waarde phishing-aanmeldingsserver** in van de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="c4177-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="c4177-177">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="c4177-178">Klik in **de stap** Bevestigen op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="c4177-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="c4177-179">Stap 2: De phishingcampagne voor de speer maken en starten</span><span class="sxs-lookup"><span data-stu-id="c4177-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="c4177-180">Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="c4177-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c4177-181">Maak op **de** pagina Aanvallen simuleren een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="c4177-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="c4177-182">Klik in de sectie Speer phishing **(referenties oogst)** op **Aanval starten** of klik **op Aanvalsdetails** \> **starten aanval.**</span><span class="sxs-lookup"><span data-stu-id="c4177-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="c4177-183">Klik in de sectie Phishing van de speer **(bijlage)** op **Aanval starten of** klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="c4177-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="c4177-184">De **wizard Phishing-aanval** configureren begint in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="c4177-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="c4177-185">Ga in **de stap** Start op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="c4177-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c4177-186">Voer in **het** vak Naam een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="c4177-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="c4177-187">Klik niet op Sjabloon **gebruiken,** omdat u het e-mailbericht later in de wizard maakt.</span><span class="sxs-lookup"><span data-stu-id="c4177-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="c4177-188">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="c4177-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="c4177-189">Nadat u de sjabloon hebt geselecteerd, wordt het vak **Naam** automatisch opgevuld op basis van de sjabloon, maar u kunt de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c4177-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4177-190">![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="c4177-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="c4177-191">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="c4177-192">Ga in **de stap Doel geadresseerden** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="c4177-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c4177-193">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="c4177-194">Elke geadresseerde moet een postvak Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="c4177-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="c4177-195">Als u op **Filteren en** **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="c4177-196">Klik **op Importeren** en vervolgens **bestand** importeren om een door komma's gescheiden waarde (CSV) of een door regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="c4177-197">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="c4177-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="c4177-198">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c4177-199">Configureer **in de stap E-maildetails** configureren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="c4177-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="c4177-200">Als u een sjabloon hebt geselecteerd in de **stap Start,** zijn de meeste van deze waarden al geconfigureerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="c4177-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="c4177-201">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="c4177-202">**Van (e-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="c4177-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="c4177-203">U kunt een echt of nep-e-mailadres invoeren vanuit het e-maildomein van uw organisatie, of u kunt een echt of nep extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="c4177-204">Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="c4177-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="c4177-205">**URL van de phishing-aanmeldingsserver:** Klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="c4177-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="c4177-206">Dit is de URL waar gebruikers op zullen klikken.</span><span class="sxs-lookup"><span data-stu-id="c4177-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="c4177-207">De keuzen zijn:</span><span class="sxs-lookup"><span data-stu-id="c4177-207">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="c4177-208">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="c4177-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="c4177-209">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="c4177-210">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="c4177-211">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-211">You are required to select a URL.</span></span> <span data-ttu-id="c4177-212">Voor **phishingcampagnes (bijlage)** kunt u de koppeling in de volgende stap uit de hoofdbeslag van het bericht verwijderen (anders bevat het bericht zowel een **koppeling** als een bijlage).</span><span class="sxs-lookup"><span data-stu-id="c4177-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="c4177-213">**Type bijlage:** deze instelling is alleen beschikbaar in **campagnes met Phishing-e-mail (Bijlage).**</span><span class="sxs-lookup"><span data-stu-id="c4177-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="c4177-214">Klik op de vervolgkeuzelijst en selecteer **.DOCX** of **.PDF** in de lijst.</span><span class="sxs-lookup"><span data-stu-id="c4177-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="c4177-215">**Naam van bijlage:** deze instelling is alleen beschikbaar in **Campagnes voor Phishing van de e-mail (Bijlage).**</span><span class="sxs-lookup"><span data-stu-id="c4177-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="c4177-216">Voer een bestandsnaam in voor de .docx of .pdf bijlage.</span><span class="sxs-lookup"><span data-stu-id="c4177-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="c4177-217">**Aangepaste landingspagina-URL:** Voer een optionele landingspagina in waarin gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="c4177-218">Deze koppeling vervangt de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="c4177-218">This link replaces the default landing page.</span></span> <span data-ttu-id="c4177-219">Als u bijvoorbeeld training voor interne bewustmaking hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="c4177-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="c4177-220">**Onderwerp:** Het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="c4177-221">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c4177-222">Maak in **de stap E-mail** opstellen de berichtin body van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="c4177-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="c4177-223">Als u een sjabloon hebt geselecteerd in de **stap Start,** is de berichtinstelling al geconfigureerd, maar u kunt deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="c4177-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="c4177-224">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad Bron** (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="c4177-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="c4177-225">De HTML-opmaak kan zo eenvoudig of complex zijn als u dat nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="c4177-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="c4177-226">U kunt afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de geadresseerde te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="c4177-227">`${username}` hiermee voegt u de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="c4177-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="c4177-228">`${loginserverurl}` hiermee voegt u de **URL-waarde phishing-aanmeldingsserver** in.</span><span class="sxs-lookup"><span data-stu-id="c4177-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="c4177-229">Voor **Phishing-campagnes (Bijlage)** moet u de koppeling verwijderen uit de hoofdbeslag van het bericht (anders bevat het bericht zowel een **koppeling** als een bijlage, en worden klikken op koppeling niet bijgeplagd in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="c4177-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c4177-230">![E-mail op te stellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="c4177-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="c4177-231">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="c4177-232">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="c4177-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="c4177-233">Het phishingbericht wordt bezorgd bij de beoogde geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="c4177-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="c4177-234">Wachtwoord aanvalscampagnes</span><span class="sxs-lookup"><span data-stu-id="c4177-234">Password attack campaigns</span></span>

<span data-ttu-id="c4177-235">Met *een wachtwoordaanval* wordt geprobeerd wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="c4177-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="c4177-236">In Attack Simulator zijn er twee verschillende typen wachtwoord aanvalscampagnes beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:</span><span class="sxs-lookup"><span data-stu-id="c4177-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="c4177-237">**Brute force password (dictionary attack)**  : Bij een aanval met een brute kracht of woordenlijst wordt een groot woordenlijstbestand met wachtwoorden op een gebruikersaccount gebruikt in de hoop dat een van deze wachtwoorden werkt (veel wachtwoorden voor één account). </span><span class="sxs-lookup"><span data-stu-id="c4177-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="c4177-238">Onjuiste wachtwoordvergrendelingen helpen bij het voorkomen van brute force wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="c4177-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="c4177-239">Voor de woordenlijst-aanval kunt u een of meer wachtwoorden opgeven om te proberen (handmatig ingevoerd of in een geüpload bestand) en kunt u een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="c4177-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="c4177-240">**Wachtwoordinfarct**: Bij een *wachtwoordinfarct* wordt hetzelfde zorgvuldig overwogen wachtwoord gebruikt voor een lijst met gebruikersaccounts (één wachtwoord voor veel accounts).</span><span class="sxs-lookup"><span data-stu-id="c4177-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="c4177-241">Wachtwoordsproeiaanvallen zijn moeilijker te detecteren dan brute force wachtwoordaanvallen (de kans op succes neemt toe wanneer een aanvaller één wachtwoord probeert op tientallen of honderden accounts zonder dat het risico bestaat dat de gebruiker het onjuiste wachtwoord wordt vergrendeld).</span><span class="sxs-lookup"><span data-stu-id="c4177-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="c4177-242">Voor de wachtwoordinfarct kunt u slechts één wachtwoord opgeven om te proberen en kunt u een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="c4177-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="c4177-243">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord eenvoudige auth-aanvragen door aan een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, pass-through, PingFederate, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="c4177-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="c4177-244">Voor gebruikers die MFA hebben ingeschakeld, zelfs als met de wachtwoordaanval het werkelijke wachtwoord wordt geprobeerd, wordt de  poging altijd geregistreerd als een fout (met andere woorden: MFA-gebruikers worden nooit weergegeven in het aantal geslaagde pogingen van de campagne).</span><span class="sxs-lookup"><span data-stu-id="c4177-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="c4177-245">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="c4177-245">This is the expected result.</span></span> <span data-ttu-id="c4177-246">MFA is een primaire methode om u te beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="c4177-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="c4177-247">Een wachtwoord aanvalscampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="c4177-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="c4177-248">Ga in het & Compliance center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="c4177-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="c4177-249">Maak op **de** pagina Aanvallen simuleren een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="c4177-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="c4177-250">Klik in **de sectie Brute Force Password (Dictionary Attack)** op Aanval **starten** of klik op **Aanvalsdetails** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="c4177-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="c4177-251">klik in **de sectie Password spray attack** op Aanval starten **of** klik **op Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="c4177-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="c4177-252">De **wizard Wachtwoordinfarct** configureren wordt gestart in een nieuw flyout.</span><span class="sxs-lookup"><span data-stu-id="c4177-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="c4177-253">Voer in **de stap** Start een unieke weergavenaam voor de campagne in en klik vervolgens op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="c4177-254">Ga in **de stap Doelgebruikers** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="c4177-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="c4177-255">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="c4177-256">Elke geadresseerde moet een postvak Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="c4177-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="c4177-257">Als u op **Filteren en** **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="c4177-258">Klik **op Importeren** en vervolgens **bestand** importeren om een door komma's gescheiden waarde (CSV) of een door regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="c4177-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="c4177-259">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="c4177-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="c4177-260">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="c4177-261">Kies in **de stap Aanvalsinstellingen** kiezen wat u moet doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="c4177-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="c4177-262">**Brute Force Password (Dictionary Attack)**: Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="c4177-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="c4177-263">**Wachtwoorden handmatig invoeren:** Typ in het vak Druk op **Enter** om een wachtwoord toe te voegen een wachtwoord en druk vervolgens op Enter.</span><span class="sxs-lookup"><span data-stu-id="c4177-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="c4177-264">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="c4177-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="c4177-265">**Upload wachtwoorden uit** een woordenlijstbestand: Klik **op** Upload om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat.</span><span class="sxs-lookup"><span data-stu-id="c4177-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="c4177-266">Het tekstbestand moet 10 MB of kleiner zijn en mag niet meer dan 30000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="c4177-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="c4177-267">**Wachtwoordinfarct**: Voer in **Het wachtwoord(en)** dat u wilt gebruiken in het aanvalsvak één wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="c4177-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="c4177-268">Wanneer u klaar bent, klikt u op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="c4177-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="c4177-269">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="c4177-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="c4177-270">De wachtwoorden die u hebt opgegeven, worden beproefd voor gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="c4177-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="c4177-271">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="c4177-271">View campaign results</span></span>

<span data-ttu-id="c4177-272">Nadat u een campagne hebt gestart, kunt u de voortgang en resultaten controleren op de **hoofdpagina Aanvallen simuleren.**</span><span class="sxs-lookup"><span data-stu-id="c4177-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="c4177-273">In actieve campagnes worden een statusbalk, een voltooid percentage en '(voltooide gebruikers) van (totaal aantal gebruikers)' geteld.</span><span class="sxs-lookup"><span data-stu-id="c4177-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="c4177-274">Als u op **de knop** Vernieuwen klikt, wordt de voortgang van actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="c4177-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="c4177-275">U kunt ook op **Beëindigen klikken om** een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="c4177-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="c4177-276">Wanneer de campagne is voltooid, wordt de status gewijzigd in **Aanval voltooid.**</span><span class="sxs-lookup"><span data-stu-id="c4177-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="c4177-277">U kunt de resultaten van de campagne bekijken door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="c4177-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="c4177-278">Klik op de **hoofdpagina Aanvallen simuleren** op **Rapport weergeven** onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="c4177-279">Klik op de **hoofdpagina Aanvallen simuleren** op **Details van** aanvallen in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="c4177-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="c4177-280">Selecteer op de pagina Aanvalsdetails die wordt geopend de campagne in **de sectie Aanvalsgeschiedenis.** </span><span class="sxs-lookup"><span data-stu-id="c4177-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="c4177-281">Met een van de vorige acties gaat u naar een pagina met de naam **Details van de aanval.**</span><span class="sxs-lookup"><span data-stu-id="c4177-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="c4177-282">De informatie die beschikbaar is op deze pagina voor elk type campagne, wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="c4177-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="c4177-283">Campagneresultaten van De phishing van de speer (Referenties oogst)</span><span class="sxs-lookup"><span data-stu-id="c4177-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="c4177-284">De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="c4177-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c4177-285">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c4177-286">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="c4177-286">**Total users targeted**</span></span>

- <span data-ttu-id="c4177-287">**Geslaagde pogingen:** het aantal gebruikers dat op de koppeling heeft geklikt **en** hun referenties heeft ingevoerd *(elke* gebruikersnaam en wachtwoordwaarde).</span><span class="sxs-lookup"><span data-stu-id="c4177-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="c4177-288">**Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="c4177-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c4177-289">**Snelste klik:** hoe lang het duurde voordat de eerste gebruiker op de koppeling klikt nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="c4177-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="c4177-290">**Gemiddelde klik:** de som van hoe lang het duurde voordat iedereen op de koppeling klikt, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="c4177-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="c4177-291">**Klik op Slagingspercentage:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat op de koppeling heeft geklikt) / **Totaal aantal gebruikers dat is getarget.**</span><span class="sxs-lookup"><span data-stu-id="c4177-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="c4177-292">**Snelste referenties:** Hoe lang het duurde voordat de eerste gebruiker zijn of haar referenties invoerde nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="c4177-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="c4177-293">**Gemiddelde referenties:** de som van de tijd die iedereen nodig heeft om zijn of haar referenties in te voeren, gedeeld door het aantal gebruikers dat zijn of haar referenties heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="c4177-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="c4177-294">**Succespercentage referenties:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat hun referenties heeft ingevoerd) / **Totaal aantal gebruikers dat is getarget.**</span><span class="sxs-lookup"><span data-stu-id="c4177-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="c4177-295">Een staafdiagram met de **door koppeling geklikte** en **opgegeven** referenties per dag.</span><span class="sxs-lookup"><span data-stu-id="c4177-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="c4177-296">Een cirkeldiagram met de **gekoppelde** klik , **opgegeven** referenties en **Geen** percentages voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="c4177-297">De **sectie Gecompromitteerde** gebruikers bevat de details van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="c4177-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="c4177-298">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="c4177-298">The user's email address</span></span>

  - <span data-ttu-id="c4177-299">De datum/tijd waarop ze op de koppeling hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="c4177-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="c4177-300">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="c4177-300">The client IP address.</span></span>

  - <span data-ttu-id="c4177-301">Details over de versie van de gebruiker van Windows en webbrowser.</span><span class="sxs-lookup"><span data-stu-id="c4177-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="c4177-302">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="c4177-303">Campagneresultaten van De phishing-campagne (Bijlage) van De speer</span><span class="sxs-lookup"><span data-stu-id="c4177-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="c4177-304">De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="c4177-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c4177-305">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c4177-306">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="c4177-306">**Total users targeted**</span></span>

- <span data-ttu-id="c4177-307">**Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (voorbeeld telt niet).</span><span class="sxs-lookup"><span data-stu-id="c4177-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="c4177-308">**Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="c4177-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c4177-309">**Snelste geopende bijlage:** Hoe lang het duurde voordat de eerste gebruiker de bijlage heeft geopend nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="c4177-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="c4177-310">**Gemiddelde opentijd van bijlage:** de som van de tijd die iedereen nodig had om de bijlage te openen, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="c4177-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="c4177-311">**Aantal geopende bijlagen:** een percentage dat wordt berekend op basis van (het aantal gebruikers dat de bijlage heeft geopend) / **Het totale aantal gebruikers dat is getarget.**</span><span class="sxs-lookup"><span data-stu-id="c4177-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="c4177-312">Campagneresultaten van Brute Force Password (Dictionary Attack)</span><span class="sxs-lookup"><span data-stu-id="c4177-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="c4177-313">De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="c4177-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c4177-314">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c4177-315">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="c4177-315">**Total users targeted**</span></span>

- <span data-ttu-id="c4177-316">**Geslaagde pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c4177-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="c4177-317">**Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="c4177-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="c4177-318">De **sectie Gecompromitteerde** gebruikers bevat de e-mailadressen van de getroffen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c4177-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="c4177-319">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="c4177-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="c4177-320">Campagneresultaten met wachtwoordsproeiactie</span><span class="sxs-lookup"><span data-stu-id="c4177-320">Password spray attack campaign results</span></span>

<span data-ttu-id="c4177-321">De volgende informatie is beschikbaar op de **pagina Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="c4177-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="c4177-322">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="c4177-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="c4177-323">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="c4177-323">**Total users targeted**</span></span>

- <span data-ttu-id="c4177-324">**Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="c4177-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="c4177-325">**Algehele slagingspercentage:** een percentage dat wordt berekend door **Succesvolle pogingen** Totaal aantal  /  **beoogde gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="c4177-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
