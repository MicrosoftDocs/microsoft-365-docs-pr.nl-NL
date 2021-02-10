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
description: Beheerders kunnen informatie krijgen over het gebruik van de Attack Simulator om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun microsoft 365 E5- of Microsoft Defender voor Office 365-organisaties met abonnement 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 824ee04e2fcf0757a7eb32b48246bf1a1c638926
ms.sourcegitcommit: 3dc795ea862b180484f76b3eb5d046e74041252b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/10/2021
ms.locfileid: "50175881"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="99dc5-103">Attack Simulator in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="99dc5-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="99dc5-104">**Van toepassing op** [Microsoft Defender voor Office 365-abonnement 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span><span class="sxs-lookup"><span data-stu-id="99dc5-104">**Applies to** [Microsoft Defender for Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span></span>

<span data-ttu-id="99dc5-105">Als uw organisatie beschikt over Microsoft Defender voor Office 365 Plan 2, dat functies voor bedreigingsonderzoek en antwoord [bevat,](office-365-ti.md)kunt u de Attack Simulator in het beveiligings- &-compliancecentrum gebruiken om realistische scenario's met aanvallen in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="99dc5-106">Deze gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren en te vinden voordat een echte aanval uw onderlijn beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="99dc5-107">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="99dc5-107">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="99dc5-108">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="99dc5-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="99dc5-109">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-109">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="99dc5-110">De attack simulator is beschikbaar op **Threat Management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-110">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="99dc5-111">Ga rechtstreeks naar de attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="99dc5-111">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="99dc5-112">Zie de servicebeschrijving van Microsoft Defender voor Office 365 voor meer informatie over de beschikbaarheid van Attack Simulator in verschillende Microsoft [365-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="99dc5-112">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="99dc5-113">U moet lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-113">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="99dc5-114">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="99dc5-114">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="99dc5-115">Uw account moet worden geconfigureerd voor meervoudige verificatie (MFA) voor het maken en beheren van campagnes in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="99dc5-115">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="99dc5-116">Zie Meervoudige verificatie instellen voor [instructies.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="99dc5-116">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="99dc5-117">Phishingcampagnes verzamelen en verwerken gebeurtenissen voor 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-117">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="99dc5-118">Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="99dc5-118">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="99dc5-119">Het analyseren van aanvallen en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="99dc5-119">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="99dc5-120">Zie Microsoft [365-gegevenslocaties voor meer informatie.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="99dc5-120">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="99dc5-121">Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="99dc5-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="99dc5-122">Phishingcampagnes</span><span class="sxs-lookup"><span data-stu-id="99dc5-122">Spear phishing campaigns</span></span>

<span data-ttu-id="99dc5-123">*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="99dc5-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="99dc5-124">*Phishing is* een gerichte phishing-aanval die gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de specifieke ontvangers (meestal na een aanval op de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="99dc5-124">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="99dc5-125">In Attack Simulator zijn twee verschillende typen phishingcampagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="99dc5-125">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="99dc5-126">**Phishing onder de aandacht brengen (referentiegegevens)**: de aanval probeert de ontvangers ervan te overtuigen op een URL in het bericht te klikken.</span><span class="sxs-lookup"><span data-stu-id="99dc5-126">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="99dc5-127">Als de gebruiker op de koppeling klikt, wordt hem of haar gevraagd zijn of haar referenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-127">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="99dc5-128">Als ze dit doen, gaan ze naar een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="99dc5-128">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="99dc5-129">Een standaardpagina waarin wordt uitgelegd dat dit slechts een test was en tips voor het herkennen van phishing-berichten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-129">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishing-koppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="99dc5-131">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="99dc5-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="99dc5-132">**Phishing (bijlage)**- De aanval probeert de ontvangers ervan te overtuigen dat ze een DOCX- of PDF-bijlage in het bericht moeten openen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="99dc5-133">De bijlage bevat dezelfde inhoud van de standaard phishing-koppeling, maar de eerste zin begint met " , u ziet dit bericht als een recent e-mailbericht dat u \<Display Name\> hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="99dc5-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="99dc5-134">Momenteel verlopen phishingcampagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="99dc5-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="99dc5-135">Een phishingcampagne maken</span><span class="sxs-lookup"><span data-stu-id="99dc5-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="99dc5-136">Een belangrijk onderdeel van een phishingcampagne is het uiterlijk van het e-mailbericht dat naar de geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="99dc5-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="99dc5-137">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="99dc5-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="99dc5-138">**Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Giveaway** voor prijzen en **Salarisadministratie Update.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="99dc5-139">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="99dc5-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="99dc5-140">**Maak een herbruikbare e-mailsjabloon:** nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="99dc5-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="99dc5-141">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="99dc5-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="99dc5-142">**Maak het e-mailbericht in de wizard:** u kunt het e-mailbericht rechtstreeks in de wizard maken tijdens het maken en starten van de phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="99dc5-143">Stap 1 (optioneel): Een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="99dc5-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="99dc5-144">Als u een van de ingebouwde sjablonen wilt gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="99dc5-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="99dc5-145">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="99dc5-146">Klik op **de pagina** Aanvallen nabootsen in de **secties Phishing (Referenties** worden ontvangen) of Phishing via phishing **(bijlage)** op **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="99dc5-147">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="99dc5-148">De beschikbare opties in de sjabloon zijn hetzelfde voor beide typen phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="99dc5-149">Klik op **de pagina Details** van aanval die wordt geopend in de sectie **Phishing-sjablonen** in het gebied **Sjablonen** maken op Nieuwe **sjabloon.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="99dc5-150">De **wizard Phishingsjabloon** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="99dc5-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="99dc5-151">Voer in **de stap** Start een unieke weergavenaam voor de sjabloon in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="99dc5-152">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="99dc5-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="99dc5-153">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="99dc5-154">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="99dc5-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="99dc5-155">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="99dc5-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="99dc5-156">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="99dc5-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="99dc5-157">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="99dc5-157">The choices are:</span></span>

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
     > <span data-ttu-id="99dc5-158">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-158">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="99dc5-159">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-159">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="99dc5-160">**Aangepaste URL van** landingspagina: voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-160">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="99dc5-161">Deze koppeling vervangt de standaardlandingspagina.</span><span class="sxs-lookup"><span data-stu-id="99dc5-161">This link replaces the default landing page.</span></span> <span data-ttu-id="99dc5-162">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="99dc5-162">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="99dc5-163">**Categorie:** deze instelling wordt op dit moment niet gebruikt (alles wat u typt, wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="99dc5-163">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="99dc5-164">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-164">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="99dc5-165">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-165">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="99dc5-166">Maak in **de stap E-mailbericht opstellen** de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-166">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="99dc5-167">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="99dc5-167">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="99dc5-168">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="99dc5-168">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="99dc5-169">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="99dc5-169">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="99dc5-170">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="99dc5-170">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="99dc5-171">`${loginserverurl}` voegt de **URL-waarde voor Phishing Login Server** uit de vorige stap in.</span><span class="sxs-lookup"><span data-stu-id="99dc5-171">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="99dc5-172">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-172">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="99dc5-173">Klik in **de stap** Bevestigen op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-173">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="99dc5-174">Stap 2: De phishingcampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="99dc5-174">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="99dc5-175">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-175">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="99dc5-176">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="99dc5-176">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="99dc5-177">Klik in **de sectie Phishing phishing (credentials er wordt gestolen)** op Aanval **starten** of klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="99dc5-177">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="99dc5-178">Klik in **de sectie Phishing (bijlage) op** Aanval starten **of** klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="99dc5-178">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="99dc5-179">De **wizard Phishing-aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="99dc5-179">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="99dc5-180">Ga in **de stap** Start op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="99dc5-180">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="99dc5-181">Voer in **het** vak Naam een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="99dc5-181">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="99dc5-182">Klik niet op **Sjabloon gebruiken,** want u maakt het e-mailbericht later in de wizard.</span><span class="sxs-lookup"><span data-stu-id="99dc5-182">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="99dc5-183">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="99dc5-183">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="99dc5-184">Nadat u de sjabloon hebt geselecteerd, wordt **het** vak Naam automatisch ingevuld op basis van de sjabloon, maar u kunt de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-184">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99dc5-185">![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="99dc5-185">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="99dc5-186">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-186">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="99dc5-187">Ga in **de stap Geadresseerden van** het doel op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="99dc5-187">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="99dc5-188">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-188">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="99dc5-189">Elke beoogde geadresseerde moet een postvak van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="99dc5-189">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="99dc5-190">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-190">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="99dc5-191">Klik **op Importeren** en vervolgens op **Bestand** importeren om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-191">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="99dc5-192">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-192">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="99dc5-193">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-193">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99dc5-194">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="99dc5-194">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="99dc5-195">Als u in de stap Begin een sjabloon **hebt** geselecteerd, zijn de meeste van deze waarden al geconfigureerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-195">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="99dc5-196">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-196">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="99dc5-197">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="99dc5-197">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="99dc5-198">U kunt een echt of vervalst e-mailadres invoeren vanuit het e-maildomein van uw organisatie of u kunt een echt of vervalst extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-198">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="99dc5-199">Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="99dc5-199">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="99dc5-200">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="99dc5-200">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="99dc5-201">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="99dc5-201">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="99dc5-202">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="99dc5-202">The choices are:</span></span>

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
     > - <span data-ttu-id="99dc5-203">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="99dc5-203">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="99dc5-204">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-204">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="99dc5-205">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-205">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="99dc5-206">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-206">You are required to select a URL.</span></span> <span data-ttu-id="99dc5-207">Voor **Phishing-campagnes (bijlage)** kunt u in de volgende stap de koppeling verwijderen uit de hoofd tekst van het bericht (anders bevat het bericht zowel een koppeling als **een** bijlage).</span><span class="sxs-lookup"><span data-stu-id="99dc5-207">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="99dc5-208">**Type bijlage:** deze instelling is alleen beschikbaar in **phishingcampagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="99dc5-208">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="99dc5-209">Klik op de vervolgkeuzekeuze en selecteer **. DOCX** of **. PDF uit** de lijst.</span><span class="sxs-lookup"><span data-stu-id="99dc5-209">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="99dc5-210">**Bijlagenaam:** deze instelling is alleen beschikbaar in **Phishing-campagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="99dc5-210">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="99dc5-211">Voer een bestandsnaam in voor de .docx- of .pdf-bijlage.</span><span class="sxs-lookup"><span data-stu-id="99dc5-211">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="99dc5-212">**Aangepaste URL van** landingspagina: voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-212">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="99dc5-213">Deze koppeling vervangt de standaardlandingspagina.</span><span class="sxs-lookup"><span data-stu-id="99dc5-213">This link replaces the default landing page.</span></span> <span data-ttu-id="99dc5-214">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="99dc5-214">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="99dc5-215">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-215">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="99dc5-216">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-216">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="99dc5-217">Maak in **de stap E-mailbericht opstellen** de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="99dc5-217">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="99dc5-218">Als u in de beginstap een sjabloon **hebt** geselecteerd, is de bericht zelf al geconfigureerd, maar u kunt deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-218">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="99dc5-219">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="99dc5-219">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="99dc5-220">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="99dc5-220">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="99dc5-221">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="99dc5-221">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="99dc5-222">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="99dc5-222">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="99dc5-223">`${loginserverurl}`de **URL-waarde voor phishing-aanmeldingsserver.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-223">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="99dc5-224">Voor **Phishing-campagnes (bijlage)** moet u de koppeling verwijderen uit de hoofd tekst van  het bericht (anders bevat het bericht zowel een koppeling als een bijlage, en worden klikken op een koppeling niet bij te houden in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="99dc5-224">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99dc5-225">![Bericht zelf opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="99dc5-225">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="99dc5-226">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-226">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="99dc5-227">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-227">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="99dc5-228">Het phishingbericht wordt bezorgd bij de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="99dc5-228">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="99dc5-229">Wachtwoord-aanvalcampagnes</span><span class="sxs-lookup"><span data-stu-id="99dc5-229">Password attack campaigns</span></span>

<span data-ttu-id="99dc5-230">Bij *een wachtwoord-aanval* wordt geprobeerd wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="99dc5-230">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="99dc5-231">In de Attack Simulator zijn twee verschillende typen campagnes voor wachtwoord-aanvallen beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:</span><span class="sxs-lookup"><span data-stu-id="99dc5-231">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="99dc5-232">**Wachtwoord voor een** 1000-wachtwoord  (aanval van woordenlijsten) - Een force of een aanval van een *woordenlijst* maakt gebruik van een groot woordenlijstbestand met wachtwoorden op een gebruikersaccount, in de hoop dat een van deze wachtwoorden werkt (veel wachtwoorden voor één account).</span><span class="sxs-lookup"><span data-stu-id="99dc5-232">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="99dc5-233">Onjuiste wachtwoordvergrendeling helpt forceer wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-233">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="99dc5-234">Voor de aanval van de woordenlijst kunt u een of meer wachtwoorden opgeven (handmatig ingevoerd of in een geüpload bestand) en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="99dc5-234">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="99dc5-235">**Wachtwoord-aanval:** bij een *wachtwoord-aanval* wordt hetzelfde wachtwoord gebruikt dat zorgvuldig wordt overwogen voor een lijst met gebruikersaccounts (één wachtwoord voor veel accounts).</span><span class="sxs-lookup"><span data-stu-id="99dc5-235">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="99dc5-236">Wachtwoordaanvallen zijn moeilijker te detecteren dan forceer wachtwoordaanvallen (de kans op succes neemt toe wanneer een aanvaller een wachtwoord probeert te doen via tientallen of honderden accounts zonder het risico dat de verkeerde wachtwoordvergrendeling van de gebruiker struikelen).</span><span class="sxs-lookup"><span data-stu-id="99dc5-236">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="99dc5-237">Voor de wachtwoord-aanval kunt u slechts één wachtwoord opgeven en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="99dc5-237">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="99dc5-238">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord basic-verificatie door aan een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, pass-through, PingFederate, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="99dc5-238">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="99dc5-239">Voor gebruikers die MFA hebben ingeschakeld, wordt de poging altijd als een fout geregistreerd, zelfs als de wachtwoord-aanval  het werkelijke wachtwoord probeert uit te voeren (met andere woorden: MFA-gebruikers worden nooit weergegeven in het aantal geslaagde pogingen van de campagne).</span><span class="sxs-lookup"><span data-stu-id="99dc5-239">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="99dc5-240">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="99dc5-240">This is the expected result.</span></span> <span data-ttu-id="99dc5-241">MFA is een primaire methode om u te helpen beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-241">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="99dc5-242">Een wachtwoord-aanvalscampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="99dc5-242">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="99dc5-243">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-243">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="99dc5-244">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="99dc5-244">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="99dc5-245">Klik in **de sectie Force Password (Dictionary Attack)** op Aanval **starten** of klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-245">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="99dc5-246">klik in **de sectie Wachtwoord-aanval** op **Aanval starten of** klik op Details van aanval  \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-246">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="99dc5-247">De **wizard Wachtwoord aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="99dc5-247">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="99dc5-248">Voer in **de stap** Start een unieke weergavenaam voor de campagne in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-248">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="99dc5-249">Ga in de stap **Doelgebruikers** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="99dc5-249">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="99dc5-250">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-250">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="99dc5-251">Elke beoogde geadresseerde moet een postvak van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="99dc5-251">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="99dc5-252">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-252">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="99dc5-253">Klik **op Importeren** en vervolgens op **Bestand** importeren om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-253">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="99dc5-254">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-254">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="99dc5-255">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-255">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="99dc5-256">Kies in **de stap Aanvalsinstellingen** kiezen wat u wilt doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="99dc5-256">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="99dc5-257">**ForceEr wachtwoord (aanval van woordenlijst)**: Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="99dc5-257">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="99dc5-258">**Wachtwoorden handmatig invoeren:** typ een wachtwoord in het vak Druk op **Enter** om een wachtwoord toe te voegen en druk op Enter.</span><span class="sxs-lookup"><span data-stu-id="99dc5-258">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="99dc5-259">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="99dc5-259">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="99dc5-260">**Upload wachtwoorden uit een woordenlijstbestand:** klik op Uploaden om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat. </span><span class="sxs-lookup"><span data-stu-id="99dc5-260">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="99dc5-261">Het tekstbestand mag niet groter zijn dan 10 MB en mag niet meer dan 30.000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-261">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="99dc5-262">**Wachtwoord-aanval:** voer één wachtwoord **in het wachtwoord(en) in het aanvalsvak** dat moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-262">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="99dc5-263">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-263">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="99dc5-264">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="99dc5-264">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="99dc5-265">De wachtwoorden die u hebt opgegeven, worden beschreven bij gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="99dc5-265">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="99dc5-266">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="99dc5-266">View campaign results</span></span>

<span data-ttu-id="99dc5-267">Nadat u een campagne hebt gestart, kunt u de voortgang en resultaten controleren op de hoofdpagina **voor het simuleren van** aanvallen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-267">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="99dc5-268">Actieve campagnes tonen een statusbalk, een voltooid percentage en het aantal (voltooide gebruikers) van (totaal aantal gebruikers).</span><span class="sxs-lookup"><span data-stu-id="99dc5-268">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="99dc5-269">Als u op **de knop** Vernieuwen klikt, wordt de voortgang van alle actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-269">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="99dc5-270">U kunt ook op **Beëindigen klikken om** een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="99dc5-270">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="99dc5-271">Wanneer de campagne is voltooid, wordt de status gewijzigd in **Aanval voltooid.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-271">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="99dc5-272">U kunt de resultaten van de campagne weergeven door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="99dc5-272">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="99dc5-273">Klik op de **hoofdpagina voor** het simuleren van aanvallen op **Rapport** weergeven onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-273">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="99dc5-274">Klik op de **hoofdpagina voor het** simuleren van aanvallen op **Details** van aanvallen in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="99dc5-274">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="99dc5-275">Op de **pagina Details van aanval** die wordt geopend, selecteert u de campagne in de sectie **Aanvalsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-275">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="99dc5-276">Met een van de vorige acties gaat u naar een pagina met de naam **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-276">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="99dc5-277">De informatie die beschikbaar is op deze pagina voor elk type campagne, wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="99dc5-277">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="99dc5-278">Phishing-campagneresultaten (referenties, campagneresultaten)</span><span class="sxs-lookup"><span data-stu-id="99dc5-278">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="99dc5-279">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="99dc5-279">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="99dc5-280">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-280">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="99dc5-281">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="99dc5-281">**Total users targeted**</span></span>

- <span data-ttu-id="99dc5-282">**Geslaagde pogingen:** het aantal gebruikers dat  op de koppeling heeft geklikt en hun referenties (elke gebruikersnaam en wachtwoordwaarde) heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="99dc5-282">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="99dc5-283">**Overall Success Rate:** a percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-283">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="99dc5-284">**Snelste klik:** de eerste gebruiker heeft na het starten van de campagne op de koppeling geklikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-284">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="99dc5-285">**Gemiddelde klikken:** de som van de tijd die iedereen heeft genomen om op de koppeling te klikken, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-285">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="99dc5-286">**Klik op Succespercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat op de koppeling heeft geklikt) / het totale aantal gebruikers dat op de koppeling **heeft geklikt.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-286">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="99dc5-287">**Snelste referenties:** hoe lang het de eerste gebruiker heeft nodig om zijn of haar referenties in te voeren na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-287">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="99dc5-288">**Gemiddelde referenties:** de som van de tijd die iedereen nodig had om zijn of haar referenties in te voeren, gedeeld door het aantal gebruikers dat de referenties heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="99dc5-288">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="99dc5-289">**Referentiepercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat hun referenties heeft ingevoerd) / **Het totale aantal gebruikers dat is gericht.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-289">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="99dc5-290">A bar graph that shows the **Link clicked** and **Credential supplie numbers** per day.</span><span class="sxs-lookup"><span data-stu-id="99dc5-290">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="99dc5-291">Een cirkeldiagram met de koppeling **klik** **op** de opgegeven referenties en geen **percentages** voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-291">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="99dc5-292">In **de sectie Gecompromitteerde** gebruikers worden de details vermeld van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="99dc5-292">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="99dc5-293">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="99dc5-293">The user's email address</span></span>

  - <span data-ttu-id="99dc5-294">De datum/tijd waarop ze op de koppeling hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-294">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="99dc5-295">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="99dc5-295">The client IP address.</span></span>

  - <span data-ttu-id="99dc5-296">Meer informatie over de versie van de gebruiker van Windows en de webbrowser.</span><span class="sxs-lookup"><span data-stu-id="99dc5-296">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="99dc5-297">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-297">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="99dc5-298">Phishing-campagneresultaten (bijlage)</span><span class="sxs-lookup"><span data-stu-id="99dc5-298">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="99dc5-299">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="99dc5-299">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="99dc5-300">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-300">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="99dc5-301">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="99dc5-301">**Total users targeted**</span></span>

- <span data-ttu-id="99dc5-302">**Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (voorbeeld telt niet).</span><span class="sxs-lookup"><span data-stu-id="99dc5-302">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="99dc5-303">**Overall Success Rate:** a percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-303">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="99dc5-304">**Snelste tijd bij het openen** van bijlagen: hoe lang het de eerste gebruiker duurde om de bijlage te openen na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-304">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="99dc5-305">**Gemiddelde openstaande tijd voor bijlagen:** de som van de tijd die iedereen nodig had om de bijlage te openen, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="99dc5-305">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="99dc5-306">**Succespercentage van geopende bijlage:** een percentage dat wordt berekend door (het aantal gebruikers dat de bijlage heeft geopend) / Het totale aantal gebruikers dat de bijlage **heeft geopend.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-306">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="99dc5-307">Campagneresultaten voor Het wachtwoord voor een forceer woordenlijst</span><span class="sxs-lookup"><span data-stu-id="99dc5-307">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="99dc5-308">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="99dc5-308">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="99dc5-309">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-309">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="99dc5-310">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="99dc5-310">**Total users targeted**</span></span>

- <span data-ttu-id="99dc5-311">**Geslaagde pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-311">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="99dc5-312">**Overall Success Rate:** a percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-312">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="99dc5-313">In **de sectie Gekromde** gebruikers worden de e-mailadressen van de betrokken gebruikers vermeld.</span><span class="sxs-lookup"><span data-stu-id="99dc5-313">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="99dc5-314">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="99dc5-314">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="99dc5-315">Resultaten van wachtwoord-aanvalscampagne</span><span class="sxs-lookup"><span data-stu-id="99dc5-315">Password spray attack campaign results</span></span>

<span data-ttu-id="99dc5-316">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="99dc5-316">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="99dc5-317">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="99dc5-317">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="99dc5-318">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="99dc5-318">**Total users targeted**</span></span>

- <span data-ttu-id="99dc5-319">**Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="99dc5-319">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="99dc5-320">**Overall Success Rate:** a percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="99dc5-320">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
