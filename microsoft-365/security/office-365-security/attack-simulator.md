---
title: Attack Simulator in ATP
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
ms.custom:
- seo-marvel-apr2020
description: Meer informatie over het gebruik van Attack Simulator voor het uitvoeren van gesimuleerde phishing- en wachtwoordaanvallen in uw Microsoft 365 E5- of ATP Plan 2-organisatie.
ms.openlocfilehash: 166a8ab9f6ef08ca089bc8924b686e392e870526
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587566"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="79135-103">Attack Simulator in ATP</span><span class="sxs-lookup"><span data-stu-id="79135-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="79135-104">**Samenvatting** Als u een globale beheerder of een beveiligingsbeheerder bent en uw organisatie Office 365 Advanced Threat Protection Plan 2 heeft, dat mogelijkheden voor [bedreigingsonderzoek en -reactie](office-365-ti.md)omvat, u Attack Simulator gebruiken om realistische aanvalsscenario's in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="79135-104">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="79135-105">Dit kan u helpen kwetsbare gebruikers te identificeren en te vinden voordat een echte aanval uw bedrijfsresultaat beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="79135-105">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="79135-106">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="79135-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="79135-107">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="79135-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="79135-108">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="79135-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="79135-109">Attack simulator is beschikbaar bij **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="79135-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Dreigingsbeheer - Attack Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="79135-111">Zie de servicebeschrijving van [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)voor meer informatie over de beschikbaarheid van Attack Simulator voor verschillende Microsoft 365-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="79135-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="79135-112">U moet lid zijn van de rolgroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="79135-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="79135-113">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="79135-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="79135-114">Uw account moet zijn geconfigureerd voor multi-factor authenticatie (MFA) om campagnes te maken en te beheren in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="79135-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="79135-115">Zie [Meerstapverificatie instellen](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)voor instructies.</span><span class="sxs-lookup"><span data-stu-id="79135-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="79135-116">Zorg ervoor dat het account dat u gebruikt om gesimuleerde aanvallen uit te voeren, gebruik maakt van multi-factor authenticatie om een aanval met succes te starten.</span><span class="sxs-lookup"><span data-stu-id="79135-116">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="79135-117">Daarnaast moet u een globale beheerder of een beveiligingsbeheerder zijn.</span><span class="sxs-lookup"><span data-stu-id="79135-117">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="79135-118">(Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie over rollen en machtigingen .)</span><span class="sxs-lookup"><span data-stu-id="79135-118">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="79135-119">Phishingcampagnes verzamelen en verwerken gebeurtenissen gedurende 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="79135-119">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="79135-120">Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="79135-120">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="79135-121">Er zijn geen overeenkomstige PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="79135-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="79135-122">Spear phishing campagnes</span><span class="sxs-lookup"><span data-stu-id="79135-122">Spear phishing campaigns</span></span>

<span data-ttu-id="79135-123">*Phishing* is een algemene term voor e-mailaanvallen die proberen om gevoelige informatie te stelen in berichten die lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="79135-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="79135-124">*Spear phishing* is een gerichte phishing-aanval die zeer gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de beoogde ontvangers (meestal na verkenning van de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="79135-124">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="79135-125">U bent een globale beheerder of beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="79135-125">You are a global administrator or security administrator</span></span>

<span data-ttu-id="79135-126">In Attack Simulator zijn twee verschillende soorten spear phishing-campagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="79135-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="79135-127">[Multi-factor authenticatie/Voorwaardelijke toegang](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) is ingeschakeld, voor ten minste het globale beheerdersaccount en beveiligingsbeheerders die Attack Simulator zullen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79135-127">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="79135-128">(Idealiter is meervoudige verificatie/voorwaardelijke toegang ingeschakeld voor alle gebruikers in uw organisatie.)</span><span class="sxs-lookup"><span data-stu-id="79135-128">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="79135-129">Een standaardpagina die uitlegt dat dit slechts een test was en geeft tips voor het herkennen van phishingberichten.</span><span class="sxs-lookup"><span data-stu-id="79135-129">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishing-link klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="79135-131">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="79135-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="79135-132">**Spear phishing (bijlage)**: De aanval probeert de ontvangers te overtuigen om een .docx of .pdf-bijlage in het bericht te openen.</span><span class="sxs-lookup"><span data-stu-id="79135-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="79135-133">De bijlage bevat dezelfde inhoud van de standaard phishing-link, maar de eerste zin begint met " \<Display Name\> , je ziet dit bericht als een recent e-mailbericht dat je hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="79135-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="79135-134">Op dit moment verlopen spear phishing-campagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="79135-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="79135-135">Maak een spear phishing campagne</span><span class="sxs-lookup"><span data-stu-id="79135-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="79135-136">Een belangrijk onderdeel van elke spear phishing campagne is het uiterlijk van het e-mailbericht dat wordt verzonden naar de beoogde ontvangers.</span><span class="sxs-lookup"><span data-stu-id="79135-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="79135-137">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="79135-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="79135-138">**Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Giveaway en** **Payroll Update**.</span><span class="sxs-lookup"><span data-stu-id="79135-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="79135-139">U sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="79135-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="79135-140">**Een herbruikbare e-mailsjabloon maken:** Nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, u deze opnieuw gebruiken in toekomstige spear phishing-campagnes.</span><span class="sxs-lookup"><span data-stu-id="79135-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="79135-141">U sommige, alle of geen e-maileigenschappen van de sjabloon verder aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="79135-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="79135-142">**Het e-mailbericht maken in de wizard**: U het e-mailbericht rechtstreeks in de wizard maken terwijl u de spear phishing-campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="79135-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="79135-143">Stap 1 (optioneel): een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="79135-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="79135-144">Als u een van de ingebouwde sjablonen gaat gebruiken of het e-mailbericht rechtstreeks in de wizard gaat maken, u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="79135-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="79135-145">Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="79135-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="79135-146">Klik op de pagina **Aanvallen simuleren** in de **secties Spear Phishing (Credentials Harvest)** of **Spear Phishing (Attachment)** op **Aanvalsgegevens.**</span><span class="sxs-lookup"><span data-stu-id="79135-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="79135-147">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="79135-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="79135-148">De beschikbare opties in de sjabloon zijn hetzelfde voor beide soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="79135-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="79135-149">Klik op de pagina **Aanvalsdetails** die wordt geopend in de sectie **Phishingsjablonen** in het gebied **Sjablonen maken** op **Nieuwe sjabloon**.</span><span class="sxs-lookup"><span data-stu-id="79135-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="79135-150">De wizard **Phishingsjabloon configureren** wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="79135-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="79135-151">Voer in de stap **Start** een unieke weergavenaam voor de sjabloon in en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="79135-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="79135-152">Configureer in de stap **E-mailgegevens configureren** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="79135-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="79135-153">**Van (Naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="79135-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="79135-154">**Van (E-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="79135-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="79135-155">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="79135-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="79135-156">Dit is de URL waarop gebruikers geneigd zullen zijn om op te klikken.</span><span class="sxs-lookup"><span data-stu-id="79135-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="79135-157">De keuzes zijn:</span><span class="sxs-lookup"><span data-stu-id="79135-157">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="79135-158">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="79135-158">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="79135-159">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="79135-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="79135-160">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="79135-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="79135-161">**AANGEPASTE BESTEMMINGSPAGINA-URL:** Voer een optionele bestemmingspagina in waar gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="79135-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="79135-162">Deze koppeling vervangt de standaard bestemmingspagina.</span><span class="sxs-lookup"><span data-stu-id="79135-162">This link replaces the default landing page.</span></span> <span data-ttu-id="79135-163">Als u bijvoorbeeld een interne bewustmakingstraining hebt, u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="79135-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="79135-164">**Categorie**: Momenteel wordt deze instelling niet gebruikt (alles wat u invoert wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="79135-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="79135-165">**Onderwerp**: Het veld **Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="79135-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="79135-166">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="79135-167">Maak in de stap **E-mail opstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="79135-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="79135-168">U het tabblad **E-mail** (een rijke HTML-editor) of het tabblad **Bron** (raw HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79135-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="79135-169">De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="79135-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="79135-170">U afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de ontvanger te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="79135-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="79135-171">`${username}`hiermee wordt de naam van de ontvanger ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="79135-172">`${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-aanmeldingsserver** van de vorige stap ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="79135-173">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="79135-174">Klik **in** de stap Bevestigen op **Voltooien**.</span><span class="sxs-lookup"><span data-stu-id="79135-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="79135-175">Stap 2: Maak en start de spear phishing-campagne</span><span class="sxs-lookup"><span data-stu-id="79135-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="79135-176">Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="79135-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="79135-177">Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="79135-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="79135-178">Klik in de sectie **Spear Phishing (Credential Harvest)** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.</span><span class="sxs-lookup"><span data-stu-id="79135-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="79135-179">Klik in de sectie **Spear Phishing (Attachment)** op **Aanval starten** of klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="79135-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="79135-180">De wizard **Phishing-aanval configureren** wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="79135-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="79135-181">Doe in de stap **Start** een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="79135-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="79135-182">Voer in het vak **Naam** een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="79135-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="79135-183">Klik niet op **Sjabloon gebruiken,** omdat u het e-mailbericht later in de wizard maakt.</span><span class="sxs-lookup"><span data-stu-id="79135-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="79135-184">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="79135-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="79135-185">Nadat u de sjabloon hebt geselecteerd, wordt het vak Naam automatisch gevuld op basis **van** de sjabloon, maar u de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="79135-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="79135-187">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="79135-188">Voert in de stap **Doelontvangers** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="79135-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="79135-189">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="79135-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="79135-190">Elke beoogde ontvanger moet een Exchange Online-postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="79135-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="79135-191">Als u op **Filter** en **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden teruggestuurd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="79135-192">Klik **op Bestand importeren** en bestanden **importeren** om een door komma's gescheiden waarde (CSV) of door regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="79135-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="79135-193">Elke regel moet het e-mailadres van de ontvanger bevatten.</span><span class="sxs-lookup"><span data-stu-id="79135-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="79135-194">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="79135-195">Configureer in de stap **E-mailgegevens configureren** de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="79135-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="79135-196">Als u een sjabloon hebt geselecteerd in de stap **Start,** zijn de meeste van deze waarden al geconfigureerd, maar u deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="79135-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="79135-197">**Van (Naam)**: de weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="79135-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="79135-198">**Van (E-mail)**: het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="79135-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="79135-199">U een echt of nep e-mailadres invoeren vanuit het e-maildomein van uw organisatie, of u een echt of nep extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="79135-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="79135-200">Een geldig e-mailadres van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de ontvanger.</span><span class="sxs-lookup"><span data-stu-id="79135-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="79135-201">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="79135-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="79135-202">Dit is de URL waarop gebruikers geneigd zullen zijn om op te klikken.</span><span class="sxs-lookup"><span data-stu-id="79135-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="79135-203">De keuzes zijn:</span><span class="sxs-lookup"><span data-stu-id="79135-203">The choices are:</span></span>

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
     > <ul><li><span data-ttu-id="79135-204">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="79135-204">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="79135-205">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="79135-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="79135-206">Controleer de beschikbaarheid van de URL in uw ondersteunde webbrowsers voordat u de URL gebruikt in een phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="79135-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="79135-207">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="79135-207">You are required to select a URL.</span></span> <span data-ttu-id="79135-208">Voor <b>Spear Phishing (Attachment)</b> campagnes u de koppeling in de volgende stap verwijderen uit de hoofdtekst van het bericht (anders bevat het bericht zowel een <b>link</b> als een bijlage).</span><span class="sxs-lookup"><span data-stu-id="79135-208">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="79135-209">**Bijlagetype:** deze instelling is alleen beschikbaar in **Spear Phishing -campagnes (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="79135-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="79135-210">Klik op de vervolgkeuzelijst en selecteer **. DOCX** **of. PDF** uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="79135-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="79135-211">**Bijlagenaam:** deze instelling is alleen beschikbaar in **Spear Phishing -campagnes (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="79135-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="79135-212">Voer een bestandsnaam in voor de bijlage .docx of .pdf.</span><span class="sxs-lookup"><span data-stu-id="79135-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="79135-213">**AANGEPASTE BESTEMMINGSPAGINA-URL:** Voer een optionele bestemmingspagina in waar gebruikers worden meegenomen als ze op de phishingkoppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="79135-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="79135-214">Deze koppeling vervangt de standaard bestemmingspagina.</span><span class="sxs-lookup"><span data-stu-id="79135-214">This link replaces the default landing page.</span></span> <span data-ttu-id="79135-215">Als u bijvoorbeeld een interne bewustmakingstraining hebt, u die URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="79135-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="79135-216">**Onderwerp**: Het veld **Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="79135-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="79135-217">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="79135-218">Maak in de stap **E-mail opstellen** de berichttekst van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="79135-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="79135-219">Als u een sjabloon hebt geselecteerd in de stap **Start,** is de berichttekst al geconfigureerd, maar u deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="79135-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="79135-220">U het tabblad **E-mail** (een rijke HTML-editor) of het tabblad **Bron** (raw HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79135-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="79135-221">De HTML-opmaak kan zo eenvoudig of complex zijn als u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="79135-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="79135-222">U afbeeldingen en tekst invoegen om de geloofwaardigheid van het bericht in de e-mailclient van de ontvanger te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="79135-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="79135-223">`${username}`hiermee wordt de naam van de ontvanger ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="79135-224">`${loginserverurl}`hiermee wordt de **URL-waarde van de phishing-inlogserver** ingevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="79135-225">Voor **Spear Phishing (Attachment)** campagnes moet u de koppeling verwijderen uit de hoofdtekst van het bericht (anders bevat het bericht zowel een **koppeling** als een bijlage en worden linkklikken niet bijgehouden in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="79135-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![E-mailtekst opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="79135-227">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="79135-228">Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="79135-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="79135-229">Het phishingbericht wordt bezorgd bij de beoogde ontvangers.</span><span class="sxs-lookup"><span data-stu-id="79135-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="79135-230">Campagnes voor wachtwoordaanvallen</span><span class="sxs-lookup"><span data-stu-id="79135-230">Password attack campaigns</span></span>

<span data-ttu-id="79135-231">Een *wachtwoordaanval* probeert wachtwoorden voor gebruikersaccounts in een organisatie te raden, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="79135-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="79135-232">In Attack Simulator zijn twee verschillende soorten wachtwoordaanvalscampagnes beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:</span><span class="sxs-lookup"><span data-stu-id="79135-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="79135-233">**Brute force wachtwoord (woordenboek aanval)**: Een *brute kracht* of *woordenboek* aanval maakt gebruik van een groot woordenboek bestand van wachtwoorden op een gebruikersaccount in de hoop dat een van hen zal werken (veel wachtwoorden tegen een account).</span><span class="sxs-lookup"><span data-stu-id="79135-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="79135-234">Onjuiste wachtwoord lock-outs helpen af te schrikken brute force wachtwoord aanvallen.</span><span class="sxs-lookup"><span data-stu-id="79135-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="79135-235">Voor de woordenboekaanval u een of meerdere wachtwoorden opgeven om te proberen (handmatig ingevoerd of in een geüpload bestand) en u een of meerdere gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="79135-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="79135-236">**Wachtwoord spray aanval**: Een *wachtwoord spray* aanval maakt gebruik van hetzelfde zorgvuldig overwogen wachtwoord tegen een lijst van gebruikersaccounts (een wachtwoord tegen veel accounts).</span><span class="sxs-lookup"><span data-stu-id="79135-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="79135-237">Wachtwoord spray aanvallen zijn moeilijker te detecteren dan brute force wachtwoord aanvallen (de kans op succes toeneemt wanneer een aanvaller probeert een wachtwoord over tientallen of honderden accounts zonder het risico van struikelen van de gebruiker onjuiste wachtwoord lock-out).</span><span class="sxs-lookup"><span data-stu-id="79135-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="79135-238">Voor de wachtwoordsprayaanval u slechts één wachtwoord opgeven om te proberen en u een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="79135-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="79135-239">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord basic auth-verzoeken door naar een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, password hash sync, pass-through, PingFederate, enz.).</span><span class="sxs-lookup"><span data-stu-id="79135-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="79135-240">Voor gebruikers die MFA hebben ingeschakeld, zelfs als de wachtwoordaanval hun werkelijke wachtwoord probeert, wordt de poging altijd geregistreerd als een fout (met andere woorden, MFA-gebruikers zullen nooit worden weergegeven in het aantal **succesvolle pogingen** van de campagne).</span><span class="sxs-lookup"><span data-stu-id="79135-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="79135-241">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="79135-241">This is the expected result.</span></span> <span data-ttu-id="79135-242">MFA is een primaire methode om te helpen beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="79135-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="79135-243">Een campagne voor wachtwoordaanvallen maken en starten</span><span class="sxs-lookup"><span data-stu-id="79135-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="79135-244">Ga in het Security & Compliance Center naar **Threat management** \> **Attack simulator**.</span><span class="sxs-lookup"><span data-stu-id="79135-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="79135-245">Maak op de pagina **Aanvallen simuleren** een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="79135-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="79135-246">Klik in de sectie **Brute Force Password (Dictionary Attack)** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.</span><span class="sxs-lookup"><span data-stu-id="79135-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="79135-247">Klik in de sectie **Wachtwoordspray-aanval** op **Aanval starten** of klik op **Aanvalsdetails** \> **startaanval**.</span><span class="sxs-lookup"><span data-stu-id="79135-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="79135-248">De wizard **Wachtwoordaanval configureren** wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="79135-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="79135-249">Voer in de stap **Start** een unieke weergavenaam voor de campagne in en klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="79135-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="79135-250">Voert in de stap **Doelgebruikers** een van de volgende stappen uit:</span><span class="sxs-lookup"><span data-stu-id="79135-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="79135-251">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="79135-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="79135-252">Elke beoogde ontvanger moet een Exchange Online-postvak hebben.</span><span class="sxs-lookup"><span data-stu-id="79135-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="79135-253">Als u op **Filter** en **Toepassen klikt** zonder een zoekcriteria in te voeren, worden alle geadresseerden teruggestuurd en aan de campagne toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="79135-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="79135-254">Klik **op Bestand importeren** en bestanden **importeren** om een door komma's gescheiden waarde (CSV) of door regel gescheiden bestand met e-mailadressen te importeren.</span><span class="sxs-lookup"><span data-stu-id="79135-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="79135-255">Elke regel moet het e-mailadres van de ontvanger bevatten.</span><span class="sxs-lookup"><span data-stu-id="79135-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="79135-256">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="79135-257">Kies in de stap **Aanvalsinstellingen kiezen** wat u wilt doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="79135-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="79135-258">**Brute Force Password (Dictionary Attack)**: Doe een van de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="79135-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="79135-259">**Wachtwoorden handmatig invoeren**: typ in **het vak Druk op Enter om een wachtwoordvak toe te voegen** een wachtwoord en druk op ENTER.</span><span class="sxs-lookup"><span data-stu-id="79135-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="79135-260">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="79135-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="79135-261">**Wachtwoorden uploaden uit een woordenboekbestand**: klik op **Uploaden** om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat.</span><span class="sxs-lookup"><span data-stu-id="79135-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="79135-262">Het tekstbestand moet 10 MB of minder groot zijn en mag niet meer dan 30000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="79135-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="79135-263">**Wachtwoord spray aanval**: Voer in **het wachtwoord(en) te gebruiken in het** aanvalsvak, voer een wachtwoord in.</span><span class="sxs-lookup"><span data-stu-id="79135-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="79135-264">Klik op **Volgende**als u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="79135-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="79135-265">Klik **in** de stap Bevestigen op **Voltooien** om de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="79135-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="79135-266">De wachtwoorden die u hebt opgegeven, worden beproefd op gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="79135-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="79135-267">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="79135-267">View campaign results</span></span>

<span data-ttu-id="79135-268">Nadat u een campagne hebt gestart, u de voortgang en resultaten controleren op de pagina **Hoofdaanvallen simuleren.**</span><span class="sxs-lookup"><span data-stu-id="79135-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="79135-269">Actieve campagnes tonen een statusbalk, een voltooid percentage waarde en "(voltooide gebruikers) van (totale gebruikers)" tellen.</span><span class="sxs-lookup"><span data-stu-id="79135-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="79135-270">Als u op de knop **Vernieuwen** klikt, wordt de voortgang van actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="79135-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="79135-271">U ook op **Beëindigen** klikken om een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="79135-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="79135-272">Wanneer de campagne is voltooid, wordt de status **gewijzigd in Aanval voltooid**.</span><span class="sxs-lookup"><span data-stu-id="79135-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="79135-273">U de resultaten van de campagne bekijken door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="79135-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="79135-274">Klik op de hoofdpagina **van aanvallen simuleren** op **Rapport weergeven** onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="79135-275">Klik op de hoofdpagina **aanvallen simuleren** op **Aanvalsdetails** in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="79135-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="79135-276">Selecteer op de pagina **Aanvalsdetails** die wordt geopend de campagne in de sectie **Aanvalsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="79135-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="79135-277">Een van de vorige acties brengt u naar een pagina met de naam **Attack details**.</span><span class="sxs-lookup"><span data-stu-id="79135-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="79135-278">De informatie die beschikbaar is op deze pagina voor elk type campagne wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="79135-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="79135-279">Spear Phishing (Credentials Harvest) campagne resultaten</span><span class="sxs-lookup"><span data-stu-id="79135-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="79135-280">De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="79135-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="79135-281">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="79135-282">**Totaal aantal beoogde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="79135-282">**Total users targeted**</span></span>

- <span data-ttu-id="79135-283">**Geslaagde pogingen**: het aantal gebruikers dat op de link heeft geklikt **en** hun referenties heeft ingevoerd *(elke* gebruikersnaam en wachtwoordwaarde).</span><span class="sxs-lookup"><span data-stu-id="79135-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="79135-284">**Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**</span><span class="sxs-lookup"><span data-stu-id="79135-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="79135-285">**Snelste klik:** Hoe lang het duurde voordat de eerste gebruiker op de link klikte nadat u de campagne had gestart.</span><span class="sxs-lookup"><span data-stu-id="79135-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="79135-286">**Gemiddelde klik:** de som van hoe lang het duurde iedereen om te klikken op de link gedeeld door het aantal gebruikers die op de link geklikt.</span><span class="sxs-lookup"><span data-stu-id="79135-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="79135-287">**Klik op Slagingspercentage:** een percentage dat wordt berekend door (aantal gebruikers dat op de link heeft geklikt) / **Totaal gericht gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="79135-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="79135-288">**Snelste referenties:** Hoe lang het duurde voordat de eerste gebruiker zijn referenties invoerde nadat u de campagne had gestart.</span><span class="sxs-lookup"><span data-stu-id="79135-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="79135-289">**Gemiddelde referenties:** de som van hoe lang het duurde iedereen om hun referenties gedeeld door het aantal gebruikers die hun referenties ingevoerd in te voeren.</span><span class="sxs-lookup"><span data-stu-id="79135-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="79135-290">**Succespercentage referenties:** een percentage dat wordt berekend door (aantal gebruikers die hun referenties hebben ingevoerd) / **Totaal gericht gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="79135-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="79135-291">Een staafgrafiek met de **klik op** de koppeling en de opgegeven nummers **per** dag.</span><span class="sxs-lookup"><span data-stu-id="79135-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="79135-292">Een cirkelgrafiek met de **link waarop is geklikt,** **Referenties geleverd**en **Geen** percentages voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="79135-293">In de sectie **Gecompromitteerde gebruikers** worden de gegevens weergegeven van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="79135-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="79135-294">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="79135-294">The user's email address</span></span>

  - <span data-ttu-id="79135-295">De datum/tijd waarop ze op de link hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="79135-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="79135-296">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="79135-296">The client IP address.</span></span>

  - <span data-ttu-id="79135-297">Details over de versie van Windows en de webbrowser van de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="79135-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="79135-298">U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="79135-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="79135-299">Campagneresultaten van Spear Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="79135-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="79135-300">De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="79135-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="79135-301">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="79135-302">**Totaal aantal beoogde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="79135-302">**Total users targeted**</span></span>

- <span data-ttu-id="79135-303">**Geslaagde pogingen**: het aantal gebruikers dat de bijlage heeft geopend of gedownload en heeft geopend (preview telt niet mee).</span><span class="sxs-lookup"><span data-stu-id="79135-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="79135-304">**Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**</span><span class="sxs-lookup"><span data-stu-id="79135-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="79135-305">**Snelste bevestigingsvrije tijd**: Hoe lang het duurde voordat de eerste gebruiker de bijlage opende nadat u de campagne had gestart.</span><span class="sxs-lookup"><span data-stu-id="79135-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="79135-306">**Gemiddelde gehechtheidsopentijd**: De som van hoe lang het duurde voordat iedereen de bijlage opende, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="79135-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="79135-307">**Slagingspercentage voor bijlageopen**: een percentage dat wordt berekend door (aantal gebruikers dat de bijlage heeft geopend) / **Totaal gericht gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="79135-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="79135-308">Brute Force Password (Dictionary Attack) campagne resultaten</span><span class="sxs-lookup"><span data-stu-id="79135-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="79135-309">De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="79135-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="79135-310">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="79135-311">**Totaal aantal beoogde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="79135-311">**Total users targeted**</span></span>

- <span data-ttu-id="79135-312">**Geslaagde pogingen**: het aantal gebruikers dat een van de opgegeven wachtwoorden bleek te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79135-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="79135-313">**Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**</span><span class="sxs-lookup"><span data-stu-id="79135-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="79135-314">De sectie **Gecompromitteerde gebruikers** bevat de e-mailadressen van de getroffen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="79135-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="79135-315">U op **Exporteren** klikken om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="79135-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="79135-316">Resultaten van de campagne met wachtwoordspray-aanvallen</span><span class="sxs-lookup"><span data-stu-id="79135-316">Password spray attack campaign results</span></span>

<span data-ttu-id="79135-317">De volgende informatie is beschikbaar op de pagina **Aanvalsgegevens** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="79135-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="79135-318">De duur (begindatum/tijd en einddatum/tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="79135-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="79135-319">**Totaal aantal beoogde gebruikers**</span><span class="sxs-lookup"><span data-stu-id="79135-319">**Total users targeted**</span></span>

- <span data-ttu-id="79135-320">**Geslaagde pogingen**: het aantal gebruikers dat het opgegeven wachtwoord bleek te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="79135-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="79135-321">**Algemeen slagingspercentage:** een percentage dat wordt berekend door **succesvolle pogingen**die totale  /  **gebruikers targeten.**</span><span class="sxs-lookup"><span data-stu-id="79135-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
