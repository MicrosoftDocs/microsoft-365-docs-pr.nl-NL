---
title: Aanvals Simulator in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp van Hack Simulator een aanval en wachtwoord aanval uitvoert in hun Microsoft 365 E5 of Microsoft Defender for Office 365-abonnement 2-organisaties.
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615202"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="2936a-103">Aanvals Simulator in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2936a-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2936a-104">Als uw organisatie Microsoft Defender voor Office 365, abonnement 2 bevat, inclusief het [onderzoek en de antwoord mogelijkheden](office-365-ti.md)van de organisatie, kunt u met behulp van aanvals functie in het beveiligings & nalevings centrum realistische aanvalsscenario's in uw organisatie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="2936a-105">Met de gesimuleerde aanvallen kunt u gebruikers kwetsbaar maken en kwetsbaar maken voor een echte aanval met uw onderste regel.</span><span class="sxs-lookup"><span data-stu-id="2936a-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="2936a-106">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2936a-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="2936a-107">Simulatie van aanval en opleidingen met betrekking tot de training voor Microsoft 365-Services met andere klantgegevens.</span><span class="sxs-lookup"><span data-stu-id="2936a-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="2936a-108">Zie [Microsoft 365-gegevenslocaties](/microsoft-365/enterprise/o365-data-locations)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2936a-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="2936a-109">Simulatie van aanval is beschikbaar in de openbare preview-versie van het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="2936a-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="2936a-110">Zie [een phishing-aanval simuleren met Microsoft Defender voor Office 365](attack-simulation-training.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2936a-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2936a-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="2936a-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2936a-112">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="2936a-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="2936a-113">Er is een aanvals Simulator beschikbaar op de **bedreigings beheer** \> **aanval Simulator**.</span><span class="sxs-lookup"><span data-stu-id="2936a-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="2936a-114">Ga rechtstreeks naar aanval Simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="2936a-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="2936a-115">Zie voor meer informatie over de beschikbaarheid van Hack Simulator in diverse Microsoft 365-abonnementen de [servicebeschrijving van Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2936a-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="2936a-116">U moet lid zijn van de rollen groepen **Organisatiebeheer** of **beveiligingsbeheerder** .</span><span class="sxs-lookup"><span data-stu-id="2936a-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2936a-117">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="2936a-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2936a-118">Uw account moet worden geconfigureerd voor multi-factor Authentication (MFA) voor het maken en beheren van campagnes in aanvals Simulator.</span><span class="sxs-lookup"><span data-stu-id="2936a-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="2936a-119">Zie [multi-factor Authentication instellen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="2936a-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="2936a-120">Phishingberichten verzamelen en verwerken activiteiten gedurende 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="2936a-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="2936a-121">Actuele campagnegegevens zijn beschikbaar voor 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="2936a-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="2936a-122">Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="2936a-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="2936a-123">Met Spear verphishings campagnes</span><span class="sxs-lookup"><span data-stu-id="2936a-123">Spear phishing campaigns</span></span>

<span data-ttu-id="2936a-124">*Phishing* is een algemene term voor e-mail aanvallen waarbij gevoelige informatie wordt gestolen voor berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="2936a-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2936a-125">*Spear phishing* is een gerichte malafide aanval waarbij gerichte en aangepaste inhoud worden gebruikt die specifiek is afgestemd op de gerichte geadresseerden (meestal na Reconnaissance op de geadresseerden van de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="2936a-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="2936a-126">In het geval van een aanvals Simulator zijn er twee verschillende typen vergelijkende phishingberichten beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="2936a-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="2936a-127">**Spear phishing (credentials oogst)**: de aanval probeert de geadresseerden te overtuigen om op een URL in het bericht te klikken.</span><span class="sxs-lookup"><span data-stu-id="2936a-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="2936a-128">Als u op de koppeling klikt, wordt u gevraagd hun referenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="2936a-129">Als dat het geval is, worden deze in een van de volgende locaties gezet:</span><span class="sxs-lookup"><span data-stu-id="2936a-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="2936a-130">Een standaardpagina waarmee wordt uitgelegd dat dit een enkele test is en geeft tips voor het herkennen van phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="2936a-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Welke gebruikers zien of ze op de phishing-koppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="2936a-132">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="2936a-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="2936a-133">**Spear phishing (bijlage)**: de aanval probeert de geadresseerden te overtuigen een. DOCX-of. PDF-bijlage te openen in het bericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="2936a-134">De bijlage bevat dezelfde inhoud van de standaard malafide hyperlink, maar de eerste zin begint met ' \<Display Name\> , dit bericht wordt weergegeven als een onlangs verzonden e-mailbericht dat u hebt geopend... '.</span><span class="sxs-lookup"><span data-stu-id="2936a-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="2936a-135">Op dit moment verloopt het met Spear vermoeden van een aanvals Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="2936a-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="2936a-136">Een Spear malafide campagne maken</span><span class="sxs-lookup"><span data-stu-id="2936a-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="2936a-137">Een belangrijk onderdeel van een spear phishing is het uiterlijk van het e-mailbericht dat naar de specifieke geadresseerden is verzonden.</span><span class="sxs-lookup"><span data-stu-id="2936a-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="2936a-138">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="2936a-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="2936a-139">**Een ingebouwde e-mail sjabloon gebruiken**: er zijn twee ingebouwde sjablonen beschikbaar: **prijs Giveaway** en **salaris update**.</span><span class="sxs-lookup"><span data-stu-id="2936a-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="2936a-140">U kunt enkele, alle of geen van de e-mail eigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="2936a-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2936a-141">**Een herbruikbare e-mail sjabloon maken**: nadat u de e-mail sjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingberichten van een malafide programma.</span><span class="sxs-lookup"><span data-stu-id="2936a-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="2936a-142">U kunt enkele, alle of geen van de e-mail eigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="2936a-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2936a-143">**Het e-mailbericht maken in de wizard**: u kunt het e-mailbericht rechtstreeks in de wizard maken wanneer u de Spear malafide-campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="2936a-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="2936a-144">Stap 1 (optioneel): een aangepaste e-mail sjabloon maken</span><span class="sxs-lookup"><span data-stu-id="2936a-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="2936a-145">Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="2936a-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="2936a-146">Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> .</span><span class="sxs-lookup"><span data-stu-id="2936a-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2936a-147">Op de pagina **aanvallen simuleren** , in de secties **spear phishing (credentials oogst)** of **spear phishing (bijlage)** , klikt u op **Details van aanval**.</span><span class="sxs-lookup"><span data-stu-id="2936a-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="2936a-148">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="2936a-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="2936a-149">De beschikbare opties in de sjabloon zijn hetzelfde voor beide typen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="2936a-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="2936a-150">Klik op de pagina met **aanvals gegevens** die wordt geopend, in de sectie **phishingberichten** , in het gebied **sjablonen maken** op **nieuwe sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="2936a-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="2936a-151">De wizard **phishing configureren** start in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="2936a-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="2936a-152">Voer in de stap **begin** een unieke weergavenaam voor de sjabloon in en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="2936a-153">Configureer de volgende instellingen in de stap **e-mail gegevens configureren** :</span><span class="sxs-lookup"><span data-stu-id="2936a-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="2936a-154">**From (naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2936a-155">**From (e-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="2936a-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="2936a-156">**URL voor phishing-login server**: Klik op de vervolgkeuzelijst en selecteer een van de beschikbare url's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2936a-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2936a-157">Dit is de URL die gebruikers in de neiging krijgen om te klikken.</span><span class="sxs-lookup"><span data-stu-id="2936a-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2936a-158">U kunt kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="2936a-158">The choices are:</span></span>

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
     > - <span data-ttu-id="2936a-159">Alle Url's zijn per ongeluk http, niet HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2936a-159">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2936a-160">Een URL-reputatie service kan een of meer van deze Url's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2936a-161">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2936a-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="2936a-162">**URL voor aangepaste landingspagina**: Voer een optionele openingspagina in, waar gebruikers worden gehouden als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2936a-163">Met deze koppeling vervangt u de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="2936a-163">This link replaces the default landing page.</span></span> <span data-ttu-id="2936a-164">Als u bijvoorbeeld een interne bewustmakings training hebt, kunt u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="2936a-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2936a-165">**Categorie**: deze instelling wordt op dit moment niet gebruikt (alle ingevoerde tekst wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="2936a-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="2936a-166">**Onderwerp**: het veld **onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2936a-167">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2936a-168">Maak in de stap **e-mailbericht opstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2936a-169">U kunt het tabblad **e-mail** (een rijke HTML-editor) of het tabblad **bron** (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2936a-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2936a-170">De HTML-opmaak kan zo eenvoudig of ingewikkeld zijn als u deze nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="2936a-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2936a-171">U kunt afbeeldingen en tekst invoegen om de beknopte van het bericht in de e-mailclient van de ontvanger te bevorderen.</span><span class="sxs-lookup"><span data-stu-id="2936a-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2936a-172">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="2936a-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2936a-173">`${loginserverurl}` Hiermee voegt u de URL-naam van de phishingwebsite voor de **phishingwebsite** in met de vorige stap.</span><span class="sxs-lookup"><span data-stu-id="2936a-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="2936a-174">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2936a-175">Klik in de stap **bevestigen** op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="2936a-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="2936a-176">Stap 2: de spear phishing-campagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="2936a-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="2936a-177">Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> .</span><span class="sxs-lookup"><span data-stu-id="2936a-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2936a-178">Maak op de pagina **aanvallen simuleren** een van de volgende opties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="2936a-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2936a-179">Klik in de sectie **spear phishing (credentials oogst)** op **Attack activeren** of klik op aanvals **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="2936a-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2936a-180">Klik in de sectie **spear phishing (bijlage)** op **aanval starten** of klik op aanvals **informatie** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="2936a-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2936a-181">De wizard **phishing configureren** begint in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="2936a-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2936a-182">Voer in de stap **begin** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="2936a-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2936a-183">Voer in het vak **naam** een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="2936a-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="2936a-184">Klik niet op **sjabloon gebruiken** omdat u het e-mailbericht later in de wizard gaat maken.</span><span class="sxs-lookup"><span data-stu-id="2936a-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="2936a-185">Klik op **sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mail sjabloon.</span><span class="sxs-lookup"><span data-stu-id="2936a-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="2936a-186">Wanneer u de sjabloon hebt geselecteerd, wordt het vak **naam** automatisch ingevuld op basis van de sjabloon, maar u kunt de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2936a-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![De start pagina van phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="2936a-188">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2936a-189">Voer een van de volgende stappen uit in de stap **doel geadresseerden** :</span><span class="sxs-lookup"><span data-stu-id="2936a-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2936a-190">Klik op **Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2936a-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2936a-191">Elke gerichte ontvanger moet een postvak van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="2936a-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2936a-192">Als u op **filter** en **toepassen** klikt zonder de zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2936a-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2936a-193">Klik op **importeren** en vervolgens op **bestand importeren** om een CSV-bestand (door komma's gescheiden waarden) of een bestand met door komma's gescheiden waarden van e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2936a-194">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="2936a-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2936a-195">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2936a-196">Configureer de volgende instellingen in de stap **e-mail gegevens configureren** :</span><span class="sxs-lookup"><span data-stu-id="2936a-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="2936a-197">Als u een sjabloon hebt geselecteerd in de **begin** stap, zijn de meeste van deze waarden al geconfigureerd, maar u kunt ze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="2936a-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="2936a-198">**From (naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2936a-199">**From (e-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="2936a-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="2936a-200">U kunt een echt e-mailadres of e-mailadres invoeren in het e-mail domein van uw organisatie, of u kunt een echt of vervalst extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="2936a-201">Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk omgezet in de e-mailclient van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="2936a-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="2936a-202">**URL voor phishing-login server**: Klik op de vervolgkeuzelijst en selecteer een van de beschikbare url's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="2936a-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2936a-203">Dit is de URL die gebruikers in de neiging krijgen om te klikken.</span><span class="sxs-lookup"><span data-stu-id="2936a-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2936a-204">U kunt kiezen uit de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="2936a-204">The choices are:</span></span>

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
     > - <span data-ttu-id="2936a-205">Alle Url's zijn per ongeluk http, niet HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2936a-205">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2936a-206">Een URL-reputatie service kan een of meer van deze Url's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2936a-207">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL in een malafide campagne gebruikt.</span><span class="sxs-lookup"><span data-stu-id="2936a-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="2936a-208">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="2936a-208">You are required to select a URL.</span></span> <span data-ttu-id="2936a-209">U kunt de koppeling in de hoofdtekst van het bericht in de volgende stap verwijderen (in de volgende stap, anders is het bericht een koppeling **en** een **bijlage).**</span><span class="sxs-lookup"><span data-stu-id="2936a-209">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="2936a-210">**Bijlage type**: deze instelling is alleen beschikbaar in een **Spear malafide-campagne (bijlage)** .</span><span class="sxs-lookup"><span data-stu-id="2936a-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2936a-211">Klik op de vervolgkeuzelijst en selecteer **. DOCX** of **. PDF** uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="2936a-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="2936a-212">**Bijlagenaam**: deze instelling is alleen beschikbaar in een **Spear malafide-campagne (bijlage)** .</span><span class="sxs-lookup"><span data-stu-id="2936a-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2936a-213">Voer een bestandsnaam in voor de. DOCX-of. PDF-bijlage.</span><span class="sxs-lookup"><span data-stu-id="2936a-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="2936a-214">**URL voor aangepaste landingspagina**: Voer een optionele openingspagina in, waar gebruikers worden gehouden als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2936a-215">Met deze koppeling vervangt u de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="2936a-215">This link replaces the default landing page.</span></span> <span data-ttu-id="2936a-216">Als u bijvoorbeeld een interne bewustmakings training hebt, kunt u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="2936a-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2936a-217">**Onderwerp**: het veld **onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2936a-218">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2936a-219">Maak in de stap **e-mailbericht opstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2936a-220">Als u in de stap **begin** een sjabloon hebt geselecteerd, is de berichttekst al geconfigureerd, maar u kunt deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="2936a-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="2936a-221">U kunt het tabblad **e-mail** (een rijke HTML-editor) of het tabblad **bron** (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2936a-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2936a-222">De HTML-opmaak kan zo eenvoudig of ingewikkeld zijn als u deze nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="2936a-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2936a-223">U kunt afbeeldingen en tekst invoegen om de beknopte van het bericht in de e-mailclient van de ontvanger te bevorderen.</span><span class="sxs-lookup"><span data-stu-id="2936a-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2936a-224">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="2936a-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2936a-225">`${loginserverurl}` Hiermee voegt u de URL-naam van de phishingwebsite van de **phishingwebsite** in.</span><span class="sxs-lookup"><span data-stu-id="2936a-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="2936a-226">U moet de koppeling in de hoofdtekst van het bericht verwijderen (in de **meeste** gevallen moet het bericht zowel een koppeling **als** een bijlage bevatten, en koppelings klikken worden niet bijgehouden in een bijlage campagne).</span><span class="sxs-lookup"><span data-stu-id="2936a-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Berichttekst opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="2936a-228">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2936a-229">Klik in de stap **bevestigen** op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="2936a-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2936a-230">Het malafide bericht wordt bezorgd bij de specifieke geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="2936a-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="2936a-231">Wachtwoord aanvals campagnes</span><span class="sxs-lookup"><span data-stu-id="2936a-231">Password attack campaigns</span></span>

<span data-ttu-id="2936a-232">Een *wachtwoord aanval* probeert wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de hacker een of meer geldige gebruikersaccounts heeft vastgesteld.</span><span class="sxs-lookup"><span data-stu-id="2936a-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="2936a-233">In het geval van een aanvals Simulator zijn voor u de complexiteit van de wachtwoorden van de gebruikers mogelijk.</span><span class="sxs-lookup"><span data-stu-id="2936a-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="2936a-234">**Wachtwoord voor brute kracht (woordenboekaanval)**: een *Grove* woord of *woordenboek* aanval gebruikt een groot woordenboek met wachtwoorden voor een gebruikersaccount, zodat een van deze wachtwoorden (veel wachtwoorden voor één account) werkt.</span><span class="sxs-lookup"><span data-stu-id="2936a-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="2936a-235">Onjuiste wachtwoord vergrendelings helpt bij het beschermen van grove aanvals wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="2936a-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="2936a-236">Voor de woordenboekaanval kunt u een of meer wachtwoorden opgeven voor de invoer (handmatig of in een geüpload bestand) en kunt u een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="2936a-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="2936a-237">**Aanval** met een wachtwoord: een aanval met een *wachtwoord* gebruikt hetzelfde zorgvuldig als het wachtwoord voor een lijst met gebruikersaccounts (één wachtwoord voor een groot aantal accounts).</span><span class="sxs-lookup"><span data-stu-id="2936a-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="2936a-238">Aanval met een wachtwoord is moeilijker te detecteren dan aanvallen met een grove kracht (de kans op succes vergroot wanneer een aanvaller één wachtwoord probeert uit te proberen of honderden accounts zonder dat het risico loopt dat de gebruikers onjuiste wachtwoorden voor de gebruiker uitchecken).</span><span class="sxs-lookup"><span data-stu-id="2936a-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="2936a-239">Voor de wachtwoord spray mag u slechts één wachtwoord opgeven om te proberen, en kunt u een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="2936a-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="2936a-240">Met de wachtwoord aanvallen in aanval Simulator worden gebruikersnamen en basisverificatie aanvragen doorgegeven aan een eindpunt, zodat ze ook met andere verificatiemethoden werken (AD FS, hash-synchronisatie, Pass-Through, PingFederate, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="2936a-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="2936a-241">Voor gebruikers waarbij MFA is ingeschakeld, wordt het wachtwoord van de aanvaller automatisch geregistreerd als gevolg van een aanval (met andere woorden, MFA-gebruikers worden nooit weergegeven in het aantal **geslaagde pogingen** van de campagne).</span><span class="sxs-lookup"><span data-stu-id="2936a-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="2936a-242">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="2936a-242">This is the expected result.</span></span> <span data-ttu-id="2936a-243">MFA is een primaire methode voor een betere bescherming tegen wachtwoord aanvallen.</span><span class="sxs-lookup"><span data-stu-id="2936a-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="2936a-244">Een wachtwoord aanvals campagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="2936a-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="2936a-245">Ga in het beveiligings & compliance naar aanvals centrum voor **Threat Management** \> .</span><span class="sxs-lookup"><span data-stu-id="2936a-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2936a-246">Maak op de pagina **aanvallen simuleren** een van de volgende opties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="2936a-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2936a-247">Klik in de sectie **Grove wachtwoord afdwingen (woordenboekaanval)** op **aanval starten** of klik op aanvals **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="2936a-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2936a-248">Klik in de sectie **wachtwoord spuit aanval** op **aanval starten** of klik op aanvals **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="2936a-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2936a-249">De wizard **wachtwoord configureren** wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="2936a-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2936a-250">Voer in de stap **begin** een unieke weergavenaam voor de campagne in en klik op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="2936a-251">Voer een van de volgende stappen uit in de stap **doelgebruikers** :</span><span class="sxs-lookup"><span data-stu-id="2936a-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2936a-252">Klik op **Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="2936a-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2936a-253">Elke gerichte ontvanger moet een postvak van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="2936a-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2936a-254">Als u op **filter** en **toepassen** klikt zonder de zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="2936a-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2936a-255">Klik op **importeren** en vervolgens op **bestand importeren** om een CSV-bestand (door komma's gescheiden waarden) of een bestand met door komma's gescheiden waarden van e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="2936a-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2936a-256">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="2936a-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2936a-257">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2936a-258">Kies in de stap **Choose Attack Settings** wat u wilt doen op basis van het type campagne:</span><span class="sxs-lookup"><span data-stu-id="2936a-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="2936a-259">**Wachtwoord voor brute kracht (woordenboekaanval)**: Voer een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="2936a-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="2936a-260">**Voer uw wachtwoorden handmatig** in: Typ een wachtwoord in het vak **Druk op ENTER om een wachtwoord toe te voegen** en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="2936a-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="2936a-261">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="2936a-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="2936a-262">**Wachtwoorden van een woordenlijstbestand uploaden**: Klik op **uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord bevat op een regel en een lege laatste regel.</span><span class="sxs-lookup"><span data-stu-id="2936a-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="2936a-263">Het tekstbestand mag niet groter zijn dan 10 MB, en mag niet meer dan 30000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="2936a-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="2936a-264">**Aanval** met een wachtwoord: Typ in **het vak voor de aanval** één wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="2936a-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="2936a-265">Wanneer u klaar bent, klikt u op **volgende**.</span><span class="sxs-lookup"><span data-stu-id="2936a-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2936a-266">Klik in de stap **bevestigen** op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="2936a-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2936a-267">De wachtwoorden die u hebt opgegeven, worden geprobeerd op door u opgegeven gebruikers.</span><span class="sxs-lookup"><span data-stu-id="2936a-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="2936a-268">Campagne resultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="2936a-268">View campaign results</span></span>

<span data-ttu-id="2936a-269">Wanneer u een campagne hebt gestart, kunt u de voortgang en de resultaten controleren op de pagina met **aanvals simulatie** .</span><span class="sxs-lookup"><span data-stu-id="2936a-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="2936a-270">Actieve campagnes tonen een statusbalk, een voltooide percentagewaarde en ' (voltooide gebruikers) van (totaal aantal gebruikers) '.</span><span class="sxs-lookup"><span data-stu-id="2936a-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="2936a-271">Als u op de knop **vernieuwen** klikt, wordt de voortgang van actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="2936a-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="2936a-272">U kunt ook op **beëindigen** klikken om een actieve campagne te beëindigen.</span><span class="sxs-lookup"><span data-stu-id="2936a-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="2936a-273">Wanneer de campagne is voltooid, wordt de status gewijzigd in **aanval voltooid**.</span><span class="sxs-lookup"><span data-stu-id="2936a-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="2936a-274">U kunt de resultaten van de campagne weergeven door een van de volgende handelingen uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="2936a-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="2936a-275">Klik op de pagina Hoofdpagina met **simulaties** op **rapport weergeven** onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="2936a-276">Op de pagina Main Attack- **aanvallen** klikt u op **Details van aanval** in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="2936a-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="2936a-277">Selecteer op de pagina **Details van aanval** de optie campagne in de sectie **aanvals geschiedenis** .</span><span class="sxs-lookup"><span data-stu-id="2936a-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="2936a-278">Met een van de vorige acties gaat u naar een pagina met de naam **aanvals gegevens**.</span><span class="sxs-lookup"><span data-stu-id="2936a-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="2936a-279">In de volgende secties wordt beschreven welke informatie op deze pagina beschikbaar is voor elk type campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="2936a-280">Resultaten van een spear phishing-campagne (referenties oogst)</span><span class="sxs-lookup"><span data-stu-id="2936a-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="2936a-281">U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="2936a-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2936a-282">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2936a-283">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="2936a-283">**Total users targeted**</span></span>

- <span data-ttu-id="2936a-284">**Geslaagde pogingen**: het aantal gebruikers dat op de koppeling heeft geklikt **en** hun referenties heeft ingevoerd (*elke* gebruikersnaam en wachtwoord).</span><span class="sxs-lookup"><span data-stu-id="2936a-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="2936a-285">**Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen** voor een  /  **Totaal aantal gebruikers** die zijn gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2936a-286">**Snelste Klik**: hoe lang het duurt voordat de eerste gebruiker op de koppeling klikt, nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="2936a-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="2936a-287">**Gemiddelde Klik**: de som van hoe lang het duurt voordat iedereen op de koppeling klikt, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="2936a-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="2936a-288">**Klik op succes tarief**: een percentage dat wordt berekend door (aantal gebruikers dat op de koppeling hebt geklikt)/ **totale aantal gebruikers** dat is gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="2936a-289">**Snelste referenties**: hoe lang het duurt voordat de eerste gebruiker de referenties heeft ingevoerd nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="2936a-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="2936a-290">**Gemiddelde referenties**: de som van hoe lang het duurt voordat iedereen de referenties heeft ingevoerd, gedeeld door het aantal gebruikers dat hun referenties heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="2936a-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="2936a-291">**Geslaagde referenties**: een percentage dat wordt berekend door (aantal gebruikers dat zijn of haar referenties heeft ingevoerd)/ **totale aantal gebruikers met een targeted**.</span><span class="sxs-lookup"><span data-stu-id="2936a-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="2936a-292">Een staafdiagram met een koppeling waarmee de **koppeling wordt geklikt** en de **ingevoerde** nummers per dag.</span><span class="sxs-lookup"><span data-stu-id="2936a-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="2936a-293">Een cirkeldiagram waarin de koppeling wordt weergegeven waarop de **koppeling** is **gebaseerd**, en **geen** percentages van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="2936a-294">De sectie verdeelde **gebruikers** bevat de details van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="2936a-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="2936a-295">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="2936a-295">The user's email address</span></span>

  - <span data-ttu-id="2936a-296">De datum/tijd waarop ze op de koppeling hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="2936a-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="2936a-297">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="2936a-297">The client IP address.</span></span>

  - <span data-ttu-id="2936a-298">Details van de versie van Windows en de webbrowser van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="2936a-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="2936a-299">U kunt op **exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="2936a-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="2936a-300">Campagne resultaten van Spear malafide (bijlage)</span><span class="sxs-lookup"><span data-stu-id="2936a-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="2936a-301">U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="2936a-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2936a-302">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2936a-303">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="2936a-303">**Total users targeted**</span></span>

- <span data-ttu-id="2936a-304">**Geslaagde pogingen**: het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (geen aantal).</span><span class="sxs-lookup"><span data-stu-id="2936a-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="2936a-305">**Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen** voor een  /  **Totaal aantal gebruikers** die zijn gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2936a-306">**Snelste tijd voor bijlage open**: hoelang de eerste gebruiker de bijlage heeft gemaakt om de bijlage te openen na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="2936a-307">**Gemiddelde openingstijd bijlage**: de som van hoe lang het duurt voordat iedereen de bijlage opent, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="2936a-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="2936a-308">**Bijlage openen geslaagd**: een percentage dat wordt berekend door (aantal gebruikers dat de bijlage heeft geopend)/ **totale aantal gebruikers** dat is gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="2936a-309">De campagne resultaten van brute kracht (woordenboekaanval)</span><span class="sxs-lookup"><span data-stu-id="2936a-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="2936a-310">U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="2936a-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2936a-311">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2936a-312">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="2936a-312">**Total users targeted**</span></span>

- <span data-ttu-id="2936a-313">**Geslaagde pogingen**: het aantal gebruikers dat is gevonden met een van de opgegeven wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="2936a-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="2936a-314">**Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen** voor een  /  **Totaal aantal gebruikers** die zijn gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2936a-315">In de sectie met verdeelde **gebruikers** worden de e-mailadressen van de betrokken gebruikers weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2936a-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="2936a-316">U kunt op **exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="2936a-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="2936a-317">Resultaten van een aanval via een wachtwoord</span><span class="sxs-lookup"><span data-stu-id="2936a-317">Password spray attack campaign results</span></span>

<span data-ttu-id="2936a-318">U vindt de volgende informatie op de pagina met details van een **aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="2936a-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2936a-319">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="2936a-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2936a-320">**Totaal aantal gebruikers dat is gericht**</span><span class="sxs-lookup"><span data-stu-id="2936a-320">**Total users targeted**</span></span>

- <span data-ttu-id="2936a-321">**Geslaagde pogingen**: het aantal gebruikers dat het opgegeven wachtwoord heeft gevonden.</span><span class="sxs-lookup"><span data-stu-id="2936a-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="2936a-322">**Algemeen succes tarief**: een percentage dat wordt berekend door de **succesvolle pogingen** voor een  /  **Totaal aantal gebruikers** die zijn gericht.</span><span class="sxs-lookup"><span data-stu-id="2936a-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
