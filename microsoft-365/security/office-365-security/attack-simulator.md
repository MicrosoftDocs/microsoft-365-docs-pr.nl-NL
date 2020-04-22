---
title: Aanvalsimulator in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Als globale beheerder u Attack Simulator gebruiken om realistische aanvalsscenario's in uw organisatie uit te voeren. Dit kan u helpen kwetsbare gebruikers te identificeren en te vinden voordat een echte aanval uw bedrijf raakt.
ms.openlocfilehash: cac09ed48a46531ea2246f9c3ef798649dc73196
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638570"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="17c9f-104">Aanvalsimulator in ATP</span><span class="sxs-lookup"><span data-stu-id="17c9f-104">Attack Simulator in ATP</span></span>

<span data-ttu-id="17c9f-105">**Overzicht** Als u een globale beheerder of een beveiligingsbeheerder bent en uw organisatie office 365 Advanced Threat Protection Plan 2 heeft, waaronder [mogelijkheden voor bedreigingsonderzoek en -respons,](office-365-ti.md)u Attack Simulator gebruiken om realistische aanvalsscenario's in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-105">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="17c9f-106">Dit kan u helpen kwetsbare gebruikers te identificeren en te vinden voordat een echte aanval van invloed is op uw bedrijfsresultaat.</span><span class="sxs-lookup"><span data-stu-id="17c9f-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="17c9f-107">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="17c9f-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="17c9f-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="17c9f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="17c9f-109">Als u het Security & <https://protection.office.com/>Compliance Center wilt openen, gaat u naar .</span><span class="sxs-lookup"><span data-stu-id="17c9f-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="17c9f-110">Attack simulator is beschikbaar op **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Threat management - Attack Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="17c9f-112">Zie de beschrijving van de Service Office [365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van Attack Simulator voor verschillende Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="17c9f-113">U moet lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="17c9f-114">Zie Machtigingen in het Security & Compliance [Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rolgroepen in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="17c9f-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="17c9f-115">Uw account moet zijn geconfigureerd voor multi-factor authenticatie (MFA) om campagnes te maken en te beheren in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="17c9f-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="17c9f-116">Zie Meervoudige [verificatie instellen](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies .</span><span class="sxs-lookup"><span data-stu-id="17c9f-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="17c9f-117">Als u een aanval met succes wilt starten, moet u ervoor zorgen dat het account dat u gebruikt om gesimuleerde aanvallen uit te voeren, multi-factor authenticatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-117">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="17c9f-118">Bovendien moet u een globale beheerder of een beveiligingsbeheerder zijn.</span><span class="sxs-lookup"><span data-stu-id="17c9f-118">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="17c9f-119">(Zie Machtigingen in het Security [& Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen.)</span><span class="sxs-lookup"><span data-stu-id="17c9f-119">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="17c9f-120">Phishingcampagnes verzamelen en verwerken gebeurtenissen gedurende 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="17c9f-121">Historische campagnegegevens zijn tot 90 dagen na de lancering van de campagne beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="17c9f-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="17c9f-122">Er zijn geen overeenkomstige PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="17c9f-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="17c9f-123">Spear phishing-campagnes</span><span class="sxs-lookup"><span data-stu-id="17c9f-123">Spear phishing campaigns</span></span>

<span data-ttu-id="17c9f-124">*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="17c9f-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="17c9f-125">*Spear phishing* is een gerichte phishing-aanval die gebruik maakt van zeer gerichte en aangepaste inhoud die specifiek is afgestemd op de beoogde ontvangers (meestal, na verkenning op de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="17c9f-125">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="17c9f-126">U bent een globale beheerder of beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="17c9f-126">You are a global administrator or security administrator</span></span>

<span data-ttu-id="17c9f-127">In Attack Simulator zijn twee verschillende soorten spear phishing-campagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="17c9f-127">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="17c9f-128">[Multi-factor authenticatie/voorwaardelijke toegang](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is ingeschakeld, voor ten minste het wereldwijde beheerdersaccount en beveiligingsbeheerders die Attack Simulator zullen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-128">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="17c9f-129">(Idealiter is multi-factor authenticatie/voorwaardelijke toegang ingeschakeld voor alle gebruikers in uw organisatie.)</span><span class="sxs-lookup"><span data-stu-id="17c9f-129">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="17c9f-130">Een standaardpagina die uitlegt dat dit slechts een test was en tips geeft voor het herkennen van phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-130">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishing-link klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="17c9f-132">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="17c9f-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="17c9f-133">**Spear phishing (bijlage)**: De aanval probeert de ontvangers te overtuigen om een .docx of .pdf bijlage in het bericht te openen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="17c9f-134">De bijlage bevat dezelfde inhoud van de standaard phishing-link, maar de eerste zin begint met "\<Display Name\>, u ziet dit bericht als een recent e-mailbericht dat u hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="17c9f-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="17c9f-135">Momenteel verlopen spear phishing-campagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="17c9f-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="17c9f-136">Een spear phishing-campagne maken</span><span class="sxs-lookup"><span data-stu-id="17c9f-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="17c9f-137">Een belangrijk onderdeel van een spear phishing-campagne is de look en feel van het e-mailbericht dat wordt verzonden naar de beoogde ontvangers.</span><span class="sxs-lookup"><span data-stu-id="17c9f-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="17c9f-138">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="17c9f-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="17c9f-139">**Gebruik een ingebouwde e-mailsjabloon:** er zijn twee ingebouwde sjablonen beschikbaar: **Prijsweggeefactie** en **salarisupdate.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="17c9f-140">U sommige, alle of geen van de e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="17c9f-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="17c9f-141">**Een herbruikbare e-mailsjabloon maken:** nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, u deze opnieuw gebruiken in toekomstige spearphishingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="17c9f-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="17c9f-142">U sommige, alle of geen van de e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="17c9f-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="17c9f-143">**Maak het e-mailbericht in de wizard:** U het e-mailbericht rechtstreeks in de wizard maken terwijl u de spear phishing-campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="17c9f-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="17c9f-144">Stap 1 (optioneel): Een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="17c9f-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="17c9f-145">Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="17c9f-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="17c9f-146">Ga in het Security & Compliance Center naar **de threat management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="17c9f-147">Klik op de pagina **Aanvallen simuleren** in de secties Spear **Phishing (Credentials Harvest)** of **Spear Phishing (Attachment)** op **Aanvalsgegevens.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="17c9f-148">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="17c9f-149">De beschikbare opties in de sjabloon zijn hetzelfde voor beide soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="17c9f-150">Klik op de pagina **Details van aanvallen** die wordt geopend in de sectie **Phishingsjablonen** in het gebied **Sjablonen maken** op **Nieuwe sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="17c9f-151">De wizard **Phishingsjabloon configureren** begint in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="17c9f-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="17c9f-152">Voer in de stap **Start** een unieke weergavenaam voor de sjabloon in en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="17c9f-153">Configureer in de stap **E-maildetails** configureren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="17c9f-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="17c9f-154">**Van (Naam):** de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="17c9f-155">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="17c9f-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="17c9f-156">**URL van de phishing-aanmeldingsserver**: klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="17c9f-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="17c9f-157">Dit is de URL waar gebruikers op in de verleiding komen om te klikken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="17c9f-158">De keuzes zijn:</span><span class="sxs-lookup"><span data-stu-id="17c9f-158">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="17c9f-159">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="17c9f-159">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="17c9f-160">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="17c9f-161">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL in een phishingcampagne gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="17c9f-162">**Aangepaste URL van bestemmingspagina**: Voer een optionele bestemmingspagina in waar gebruikers worden genomen als ze op de phishing-link klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="17c9f-163">Deze koppeling vervangt de standaardbestemmingspagina.</span><span class="sxs-lookup"><span data-stu-id="17c9f-163">This link replaces the default landing page.</span></span> <span data-ttu-id="17c9f-164">Als u bijvoorbeeld interne bewustzijnstraining hebt, u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="17c9f-165">**Categorie:** Momenteel wordt deze instelling niet gebruikt (alles wat u invoert wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="17c9f-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="17c9f-166">**Onderwerp:** Het veld **Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="17c9f-167">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="17c9f-168">Maak in de **stap E-mail samenstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="17c9f-169">U het tabblad **E-mail** (een uitgebreide HTML-editor) of het tabblad **Bron** (ruwe HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="17c9f-170">De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="17c9f-171">U afbeeldingen en tekst invoegen om de glievability van het bericht in de e-mailclient van de ontvanger te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="17c9f-172">`${username}`hiermee wordt de naam van de ontvanger ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="17c9f-173">`${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-aanmeldingsserver** van de vorige stap ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="17c9f-174">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="17c9f-175">Klik **in** de stap Bevestigen op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="17c9f-176">Stap 2: Maak en start de spear phishing-campagne</span><span class="sxs-lookup"><span data-stu-id="17c9f-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="17c9f-177">Ga in het Security & Compliance Center naar **de threat management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="17c9f-178">Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="17c9f-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="17c9f-179">Klik in de sectie **Spear Phishing (Credentials Harvest)** op **Attack starten** of klik op Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="17c9f-180">Klik in de sectie **Spear Phishing (Attachment)** op **Aanval starten** of klik op **Aanvalsgegevens** \> **Startaanval**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="17c9f-181">De wizard **Phishing-aanval configureren** begint in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="17c9f-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="17c9f-182">Ga in de stap **Start** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="17c9f-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="17c9f-183">Voer in het vak **Naam** een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="17c9f-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="17c9f-184">Klik niet op **Sjabloon gebruiken,** omdat u het e-mailbericht later in de wizard maakt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="17c9f-185">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="17c9f-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="17c9f-186">Nadat u de sjabloon hebt geselecteerd, wordt het vak **Naam** automatisch ingevuld op basis van de sjabloon, maar u de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="17c9f-188">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="17c9f-189">Ga in de stap **Doelontvangers** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="17c9f-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="17c9f-190">Klik **op Adresboek** om de ontvangers (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="17c9f-191">Elke gerichte ontvanger moet een Exchange Online-postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="17c9f-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="17c9f-192">Als u op **Filteren** en **toepassen klikt** zonder zoekcriteria in te voeren, worden alle ontvangers geretourneerd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="17c9f-193">Klik **op Importeren** en vervolgens Bestand **importeren** om een door komma's gescheiden waarde (CSV) of een door de regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="17c9f-194">Elke regel moet het e-mailadres van de ontvanger bevatten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="17c9f-195">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="17c9f-196">Configureer in de stap **E-maildetails** configureren de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="17c9f-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="17c9f-197">Als u een sjabloon hebt geselecteerd in de **stap Start,** zijn de meeste van deze waarden al geconfigureerd, maar u deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="17c9f-198">**Van (Naam):** de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="17c9f-199">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="17c9f-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="17c9f-200">U een echt of nep e-mailadres invoeren vanuit het e-maildomein van uw organisatie, of u een echt of nep extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="17c9f-201">Een geldig e-mailadres van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="17c9f-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="17c9f-202">**URL van de phishing-aanmeldingsserver**: klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="17c9f-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="17c9f-203">Dit is de URL waar gebruikers op in de verleiding komen om te klikken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="17c9f-204">De keuzes zijn:</span><span class="sxs-lookup"><span data-stu-id="17c9f-204">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="17c9f-205">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="17c9f-205">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="17c9f-206">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="17c9f-207">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL in een phishingcampagne gebruikt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="17c9f-208">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-208">You are required to select a URL.</span></span> <span data-ttu-id="17c9f-209">Voor <b>Spear Phishing-campagnes (Attachment)</b> u de koppeling in de volgende stap uit de hoofdtekst van het bericht verwijderen (anders bevat het bericht zowel een <b>koppeling</b> als een bijlage).</span><span class="sxs-lookup"><span data-stu-id="17c9f-209">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="17c9f-210">**Bijlagetype:** deze instelling is alleen beschikbaar in **Spear Phishing-campagnes (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="17c9f-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="17c9f-211">Klik op de vervolgkeuzelijst en selecteer **. DOCX** of **. PDF** uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="17c9f-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="17c9f-212">**Naam van bijlage:** deze instelling is alleen beschikbaar in **Spear Phishing-campagnes (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="17c9f-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="17c9f-213">Voer een bestandsnaam in voor de bijlage .docx of .pdf.</span><span class="sxs-lookup"><span data-stu-id="17c9f-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="17c9f-214">**Aangepaste URL van bestemmingspagina**: Voer een optionele bestemmingspagina in waar gebruikers worden genomen als ze op de phishing-link klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="17c9f-215">Deze koppeling vervangt de standaardbestemmingspagina.</span><span class="sxs-lookup"><span data-stu-id="17c9f-215">This link replaces the default landing page.</span></span> <span data-ttu-id="17c9f-216">Als u bijvoorbeeld interne bewustzijnstraining hebt, u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="17c9f-217">**Onderwerp:** Het veld **Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="17c9f-218">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="17c9f-219">Maak in de **stap E-mail samenstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="17c9f-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="17c9f-220">Als u een sjabloon hebt geselecteerd in de **stap Start,** is de berichttekst al geconfigureerd, maar u deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="17c9f-221">U het tabblad **E-mail** (een uitgebreide HTML-editor) of het tabblad **Bron** (ruwe HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="17c9f-222">De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="17c9f-223">U afbeeldingen en tekst invoegen om de glievability van het bericht in de e-mailclient van de ontvanger te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="17c9f-224">`${username}`hiermee wordt de naam van de ontvanger ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="17c9f-225">`${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-aanmeldingsserver** ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="17c9f-226">Voor **Spear Phishing-campagnes (Attachment)** moet u de koppeling uit de hoofdtekst van het bericht verwijderen (anders bevat het bericht zowel een **koppeling** als een bijlage en worden klikken op koppelingen niet bijgehouden in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="17c9f-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![E-mailinstantie opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="17c9f-228">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="17c9f-229">Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="17c9f-230">Het phishingbericht wordt geleverd aan de beoogde ontvangers.</span><span class="sxs-lookup"><span data-stu-id="17c9f-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="17c9f-231">Campagnes voor wachtwoordaanvallen</span><span class="sxs-lookup"><span data-stu-id="17c9f-231">Password attack campaigns</span></span>

<span data-ttu-id="17c9f-232">Een *wachtwoordaanval* probeert wachtwoorden voor gebruikersaccounts in een organisatie te raden, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="17c9f-233">In Attack Simulator zijn twee verschillende soorten wachtwoordaanvalscampagnes beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:</span><span class="sxs-lookup"><span data-stu-id="17c9f-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="17c9f-234">**Brute force wachtwoord (woordenboek aanval)**: Een *brute force* of *woordenboek* aanval maakt gebruik van een groot woordenboek bestand van wachtwoorden op een gebruikersaccount in de hoop dat een van hen zal werken (veel wachtwoorden tegen een account).</span><span class="sxs-lookup"><span data-stu-id="17c9f-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="17c9f-235">Onjuiste wachtwoordvergrendelingen helpen aanvallen op brute force-wachtwoorden af te schrikken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="17c9f-236">Voor de woordenboekaanval u een of meerdere wachtwoorden opgeven om te proberen (handmatig ingevoerd of in een geüpload bestand) en u een of meerdere gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="17c9f-237">**Password spray attack**: Een *wachtwoord spray* aanval maakt gebruik van hetzelfde zorgvuldig overwogen wachtwoord tegen een lijst van gebruikersaccounts (een wachtwoord tegen veel accounts).</span><span class="sxs-lookup"><span data-stu-id="17c9f-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="17c9f-238">Wachtwoord spray aanvallen zijn moeilijker te detecteren dan brute force wachtwoord aanvallen (de kans op succes toeneemt wanneer een aanvaller probeert een wachtwoord over tientallen of honderden accounts zonder het risico van struikelen van de gebruiker onjuiste wachtwoord lock-out).</span><span class="sxs-lookup"><span data-stu-id="17c9f-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="17c9f-239">Voor de wachtwoordsprayaanval u slechts één wachtwoord opgeven om te proberen en u een of veel gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="17c9f-240">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord door Basisauth-aanvragen naar een eindpunt, dus ze werken ook met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, doorgeef, PingFederate, enz.).</span><span class="sxs-lookup"><span data-stu-id="17c9f-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="17c9f-241">Voor gebruikers die MFA hebben ingeschakeld, zelfs als de wachtwoordaanval hun werkelijke wachtwoord probeert, wordt de poging altijd geregistreerd als een fout (met andere woorden, MFA-gebruikers zullen nooit worden weergegeven in het aantal **geslaagde pogingen** van de campagne).</span><span class="sxs-lookup"><span data-stu-id="17c9f-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="17c9f-242">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="17c9f-242">This is the expected result.</span></span> <span data-ttu-id="17c9f-243">MFA is een primaire methode om te beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="17c9f-244">Een wachtwoordaanvalscampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="17c9f-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="17c9f-245">Ga in het Security & Compliance Center naar **de threat management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="17c9f-246">Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="17c9f-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="17c9f-247">Klik in de sectie **Brute Force Password (Dictionary Attack)** op **Attack starten** of klik op **Aanvalsdetails** \> **Aanvalsaanval**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="17c9f-248">klik in de sectie **Wachtwoordsprayaanval** op **Aanval starten** of klik op **Aanvalsdetails** \> **Startaanval**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="17c9f-249">De wizard **Wachtwoordaanval configureren** begint in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="17c9f-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="17c9f-250">Voer in de stap **Start** een unieke weergavenaam voor de campagne in en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="17c9f-251">Ga in de stap **Doelgebruikers** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="17c9f-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="17c9f-252">Klik **op Adresboek** om de ontvangers (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="17c9f-253">Elke gerichte ontvanger moet een Exchange Online-postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="17c9f-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="17c9f-254">Als u op **Filteren** en **toepassen klikt** zonder zoekcriteria in te voeren, worden alle ontvangers geretourneerd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="17c9f-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="17c9f-255">Klik **op Importeren** en vervolgens Bestand **importeren** om een door komma's gescheiden waarde (CSV) of een door de regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="17c9f-256">Elke regel moet het e-mailadres van de ontvanger bevatten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="17c9f-257">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="17c9f-258">Kies in de stap **Aanvalsinstellingen kiezen** wat u moet doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="17c9f-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="17c9f-259">**Brute Force Password (Dictionary Attack)**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="17c9f-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="17c9f-260">**Wachtwoorden handmatig invoeren**: Typ in het **voer druk om een wachtwoordvak toe te voegen** een wachtwoord en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="17c9f-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="17c9f-261">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="17c9f-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="17c9f-262">**Wachtwoorden uploaden uit een woordenboekbestand:** klik op **Uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat.</span><span class="sxs-lookup"><span data-stu-id="17c9f-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="17c9f-263">Het tekstbestand moet 10 MB of minder groot zijn en mag niet meer dan 30000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="17c9f-264">**Wachtwoordsprayaanval**: Voer in **Het wachtwoord(en) dat u in het aanvalsvak** wilt gebruiken één wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="17c9f-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="17c9f-265">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="17c9f-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="17c9f-266">Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="17c9f-267">De wachtwoorden die u hebt opgegeven, worden geprobeerd op gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="17c9f-268">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="17c9f-268">View campaign results</span></span>

<span data-ttu-id="17c9f-269">Nadat u een campagne hebt gestart, u de voortgang en resultaten op de pagina **Aanvallen simuleren** controleren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="17c9f-270">Actieve campagnes tonen een statusbalk, een voltooid percentage waarde en "(voltooide gebruikers) van (totale gebruikers)" tellen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="17c9f-271">Als u op **Vernieuwen** klikt, wordt de voortgang van actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="17c9f-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="17c9f-272">U ook op **Beëindigen** klikken om een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="17c9f-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="17c9f-273">Wanneer de campagne is voltooid, worden de statuswijzigingen **in Attack voltooid.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="17c9f-274">U de resultaten van de campagne bekijken door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="17c9f-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="17c9f-275">Klik op de pagina **Aanvallen simuleren** op **Rapport weergeven** onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="17c9f-276">Klik op de pagina **Aanvallen simuleren** op **Aanvalsgegevens** in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="17c9f-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="17c9f-277">Selecteer op de pagina **Details van aanvallen** die wordt geopend de campagne in de sectie **Aanvalsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="17c9f-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="17c9f-278">Een van de vorige acties brengt u naar een pagina met de naam **Attack details**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="17c9f-279">De informatie die beschikbaar is op deze pagina voor elk type campagne wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="17c9f-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="17c9f-280">Spear Phishing (Credentials Harvest) campagneresultaten</span><span class="sxs-lookup"><span data-stu-id="17c9f-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="17c9f-281">De volgende informatie is beschikbaar op de pagina **Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="17c9f-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="17c9f-282">De duur (begindatum/-tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="17c9f-283">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="17c9f-283">**Total users targeted**</span></span>

- <span data-ttu-id="17c9f-284">**Geslaagde pogingen:** het aantal gebruikers dat op de koppeling heeft geklikt **en** hun referenties heeft ingevoerd *(elke* gebruikersnaam en wachtwoordwaarde).</span><span class="sxs-lookup"><span data-stu-id="17c9f-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="17c9f-285">**Algemeen slagingspercentage**: Een percentage dat wordt berekend door **Succesvolle pogingen** / **Totaal aantal gebruikers gericht**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="17c9f-286">**Snelste klik:** Hoe lang het duurde voordat de eerste gebruiker op de link klikte nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="17c9f-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="17c9f-287">**Gemiddelde klik:** De som van hoe lang het duurde iedereen om de link gedeeld door het aantal gebruikers die op de link geklikt klikken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="17c9f-288">**Klik op Slagingspercentage:** een percentage dat wordt berekend door (aantal gebruikers dat op de link heeft geklikt) / **Totaal aantal gerichte gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="17c9f-289">**Snelste referenties:** hoe lang het duurde voordat de eerste gebruiker zijn of haar referenties invulde nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="17c9f-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="17c9f-290">**Gemiddelde referenties:** de som van hoe lang het duurde iedereen om hun referenties gedeeld door het aantal gebruikers die hun geloofsbrieven ingevoerd in te voeren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="17c9f-291">**Referentieslagpercentage:** een percentage dat wordt berekend door (aantal gebruikers dat hun referenties heeft ingevoerd) / **Totaal aantal gebruikers dat is getarget**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="17c9f-292">Een staafdiagram met de **klikkoppeling** en **de opgegeven** nummers per dag.</span><span class="sxs-lookup"><span data-stu-id="17c9f-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="17c9f-293">Een cirkelgrafiek met de **klikkoppeling**, **opgegeven referenties**en **geen** percentages voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="17c9f-294">In de sectie **Gecompromitteerde gebruikers** worden de details weergegeven van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="17c9f-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="17c9f-295">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="17c9f-295">The user's email address</span></span>

  - <span data-ttu-id="17c9f-296">De datum/tijd waarop ze op de link klikten.</span><span class="sxs-lookup"><span data-stu-id="17c9f-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="17c9f-297">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="17c9f-297">The client IP address.</span></span>

  - <span data-ttu-id="17c9f-298">Details over de versie van Windows en de webbrowser van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="17c9f-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="17c9f-299">U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="17c9f-300">Campagneresultaten van Spear Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="17c9f-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="17c9f-301">De volgende informatie is beschikbaar op de pagina **Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="17c9f-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="17c9f-302">De duur (begindatum/-tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="17c9f-303">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="17c9f-303">**Total users targeted**</span></span>

- <span data-ttu-id="17c9f-304">**Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (voorbeeld telt niet mee).</span><span class="sxs-lookup"><span data-stu-id="17c9f-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="17c9f-305">**Algemeen slagingspercentage**: Een percentage dat wordt berekend door **Succesvolle pogingen** / **Totaal aantal gebruikers gericht**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="17c9f-306">**Snelste bijlage open tijd:** Hoe lang het duurde de eerste gebruiker om de bijlage te openen nadat u de campagne gestart.</span><span class="sxs-lookup"><span data-stu-id="17c9f-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="17c9f-307">**Gemiddelde bijlage open tijd**: De som van hoe lang het duurde iedereen om de bijlage te openen gedeeld door het aantal gebruikers die de bijlage geopend.</span><span class="sxs-lookup"><span data-stu-id="17c9f-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="17c9f-308">**Attachment open slagingspercentage**: Een percentage dat wordt berekend door (aantal gebruikers die de bijlage hebben geopend) / **Totaal aantal gerichte gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="17c9f-309">Campagneresultaten van Brute Force Password (Dictionary Attack)</span><span class="sxs-lookup"><span data-stu-id="17c9f-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="17c9f-310">De volgende informatie is beschikbaar op de pagina **Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="17c9f-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="17c9f-311">De duur (begindatum/-tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="17c9f-312">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="17c9f-312">**Total users targeted**</span></span>

- <span data-ttu-id="17c9f-313">**Succesvolle pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden bleek te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="17c9f-314">**Algemeen slagingspercentage**: Een percentage dat wordt berekend door **Succesvolle pogingen** / **Totaal aantal gebruikers gericht**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="17c9f-315">In de sectie **Gecompromitteerde gebruikers** worden de e-mailadressen van de getroffen gebruikers weergegeven.</span><span class="sxs-lookup"><span data-stu-id="17c9f-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="17c9f-316">U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="17c9f-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="17c9f-317">Wachtwoord spray aanval campagne resultaten</span><span class="sxs-lookup"><span data-stu-id="17c9f-317">Password spray attack campaign results</span></span>

<span data-ttu-id="17c9f-318">De volgende informatie is beschikbaar op de pagina **Details van de aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="17c9f-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="17c9f-319">De duur (begindatum/-tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="17c9f-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="17c9f-320">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="17c9f-320">**Total users targeted**</span></span>

- <span data-ttu-id="17c9f-321">**Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord bleek te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="17c9f-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="17c9f-322">**Algemeen slagingspercentage**: Een percentage dat wordt berekend door **Succesvolle pogingen** / **Totaal aantal gebruikers gericht**.</span><span class="sxs-lookup"><span data-stu-id="17c9f-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
