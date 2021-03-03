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
description: Beheerders kunnen informatie krijgen over het gebruik van de Attack Simulator om gesimuleerde phishing- en wachtwoordaanvallen uit te voeren in hun organisaties met Microsoft 365 E5 of Microsoft Defender voor Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85b376701ffa0c567fd66aa629371e9f69b354e9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407468"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="aed9b-103">Attack Simulator in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="aed9b-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="aed9b-104">**Van toepassing op** [Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="aed9b-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="aed9b-105">Als uw organisatie beschikt over Microsoft Defender voor Office 365 Plan 2, dat functies voor bedreigingsonderzoek en antwoord [bevat,](office-365-ti.md)kunt u de Attack Simulator in het beveiligings- &-compliancecentrum gebruiken om realistische scenario's voor aanvallen in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="aed9b-106">Deze gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren en te vinden voordat een echte aanval uw onderlijn beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="aed9b-107">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aed9b-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="aed9b-108">De ervaring met Attack Simulator v1 is overgeschakeld naar de alleen-lezen modus en vervangen door training voor de Attack simulator die wordt beschreven in Aan de slag met de training voor de [aanvalstraining.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="aed9b-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="aed9b-109">De mogelijkheid om nieuwe validen vanaf deze site te starten is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="aed9b-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="aed9b-110">Vanaf 24 januari 2021 kunt u echter nog steeds rapporten voor worden uitgevoerd met een periode van 90 dagen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aed9b-111">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="aed9b-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aed9b-112">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="aed9b-113">De attack simulator is beschikbaar op **Threat Management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="aed9b-114">Ga rechtstreeks naar de attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="aed9b-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="aed9b-115">Zie de servicebeschrijving van Microsoft Defender voor Office 365 voor meer informatie over de beschikbaarheid van Attack Simulator in verschillende Microsoft [365-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="aed9b-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="aed9b-116">U moet lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="aed9b-117">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="aed9b-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="aed9b-118">Uw account moet worden geconfigureerd voor meervoudige verificatie (MFA) voor het maken en beheren van campagnes in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="aed9b-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="aed9b-119">Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="aed9b-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="aed9b-120">Attack Simulator werkt alleen voor postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="aed9b-120">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="aed9b-121">Phishing-campagnes verzamelen en verwerken gebeurtenissen voor 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-121">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="aed9b-122">Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="aed9b-122">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="aed9b-123">Het analyseren van aanvallen en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="aed9b-123">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="aed9b-124">Zie Microsoft [365-gegevenslocaties voor meer informatie.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="aed9b-124">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="aed9b-125">Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="aed9b-125">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="aed9b-126">Phishingcampagnes</span><span class="sxs-lookup"><span data-stu-id="aed9b-126">Spear phishing campaigns</span></span>

<span data-ttu-id="aed9b-127">*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="aed9b-127">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="aed9b-128">*Phishing is* een gerichte phishing-aanval die gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de specifieke ontvangers (meestal na een aanval op de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="aed9b-128">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="aed9b-129">In Attack Simulator zijn twee verschillende typen phishingcampagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="aed9b-129">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="aed9b-130">**Phishing onder de aandacht brengen (referentiegegevens)**: de aanval probeert de ontvangers ervan te overtuigen op een URL in het bericht te klikken.</span><span class="sxs-lookup"><span data-stu-id="aed9b-130">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="aed9b-131">Als de gebruiker op de koppeling klikt, wordt hem of haar gevraagd zijn of haar referenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-131">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="aed9b-132">Als ze dit doen, gaan ze naar een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="aed9b-132">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="aed9b-133">Een standaardpagina waarin wordt uitgelegd dat dit slechts een test was, en tips voor het herkennen van phishing-berichten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-133">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishing-koppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="aed9b-135">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="aed9b-135">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="aed9b-136">**Phishing (bijlage)**- Bij de aanval wordt geprobeerd de ontvangers ervan te overtuigen een DOCX- of PDF-bijlage in het bericht te openen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-136">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="aed9b-137">De bijlage bevat dezelfde inhoud van de standaard phishing-koppeling, maar de eerste zin begint met " , u ziet dit bericht als een recent e-mailbericht dat u \<Display Name\> hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="aed9b-137">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="aed9b-138">Momenteel verlopen phishingcampagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="aed9b-138">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="aed9b-139">Een phishingcampagne maken</span><span class="sxs-lookup"><span data-stu-id="aed9b-139">Create a spear phishing campaign</span></span>

<span data-ttu-id="aed9b-140">Een belangrijk onderdeel van een phishingcampagne is het uiterlijk van het e-mailbericht dat naar de geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="aed9b-140">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="aed9b-141">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="aed9b-141">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="aed9b-142">**Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen **beschikbaar:** Giveaway voor prijzen en **Salarisadministratie bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-142">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="aed9b-143">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="aed9b-143">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="aed9b-144">**Maak een herbruikbare e-mailsjabloon:** nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="aed9b-144">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="aed9b-145">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="aed9b-145">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="aed9b-146">**Maak het e-mailbericht in de wizard:** u kunt het e-mailbericht rechtstreeks in de wizard maken tijdens het maken en starten van de phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-146">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="aed9b-147">Stap 1 (optioneel): Een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="aed9b-147">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="aed9b-148">Als u een van de ingebouwde sjablonen gebruikt of het e-mailbericht rechtstreeks in de wizard maakt, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="aed9b-148">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="aed9b-149">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-149">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="aed9b-150">Klik op **de pagina** Aanvallen nabootsen in de **secties Phishing (Referenties ontvangen)** of **Phishing (bijlage)** op **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-150">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="aed9b-151">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-151">It doesn't matter where you create the template.</span></span> <span data-ttu-id="aed9b-152">De beschikbare opties in de sjabloon zijn hetzelfde voor beide soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-152">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="aed9b-153">Klik op **de pagina Details** van aanval die wordt geopend in de sectie **Phishing-sjablonen** in het gebied **Sjablonen** maken op Nieuwe **sjabloon.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-153">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="aed9b-154">De **wizard Phishingsjabloon** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="aed9b-154">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="aed9b-155">Voer in **de stap** Start een unieke weergavenaam voor de sjabloon in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-155">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="aed9b-156">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="aed9b-156">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="aed9b-157">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-157">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="aed9b-158">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="aed9b-158">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="aed9b-159">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="aed9b-159">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="aed9b-160">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="aed9b-160">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="aed9b-161">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="aed9b-161">The choices are:</span></span>

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
     > <span data-ttu-id="aed9b-162">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-162">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="aed9b-163">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-163">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="aed9b-164">**Aangepaste URL van** landingspagina: voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-164">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="aed9b-165">Deze koppeling vervangt de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="aed9b-165">This link replaces the default landing page.</span></span> <span data-ttu-id="aed9b-166">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="aed9b-166">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="aed9b-167">**Categorie:** deze instelling wordt momenteel niet gebruikt (alles wat u optreedt, wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="aed9b-167">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="aed9b-168">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-168">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="aed9b-169">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-169">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="aed9b-170">Maak in **de stap E-mailbericht** opstellen de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-170">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="aed9b-171">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aed9b-171">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="aed9b-172">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="aed9b-172">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="aed9b-173">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="aed9b-173">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="aed9b-174">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="aed9b-174">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="aed9b-175">`${loginserverurl}` voegt de **URL-waarde voor Phishing Login Server** uit de vorige stap in.</span><span class="sxs-lookup"><span data-stu-id="aed9b-175">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="aed9b-176">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-176">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="aed9b-177">Klik in **de stap** Bevestigen op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-177">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="aed9b-178">Stap 2: De phishingcampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="aed9b-178">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="aed9b-179">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-179">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="aed9b-180">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="aed9b-180">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="aed9b-181">Klik in **de sectie Phishing phishing (referenties wordt te keer gaan)** op Aanval **starten** of klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="aed9b-181">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="aed9b-182">Klik in **de sectie Phishing (bijlage) op** Aanval starten **of** klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="aed9b-182">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="aed9b-183">De **wizard Phishing-aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="aed9b-183">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="aed9b-184">Ga in **de stap** Start op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="aed9b-184">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="aed9b-185">Voer in **het** vak Naam een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="aed9b-185">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="aed9b-186">Klik niet op **Sjabloon gebruiken,** want u maakt het e-mailbericht later in de wizard.</span><span class="sxs-lookup"><span data-stu-id="aed9b-186">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="aed9b-187">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="aed9b-187">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="aed9b-188">Nadat u de sjabloon hebt geselecteerd, wordt **het** vak Naam automatisch ingevuld op basis van de sjabloon, maar u kunt de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-188">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aed9b-189">![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="aed9b-189">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="aed9b-190">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="aed9b-191">Ga in **de stap Geadresseerden van** het doel op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="aed9b-191">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="aed9b-192">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-192">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="aed9b-193">Elke beoogde geadresseerde moet een Postvak IN van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="aed9b-193">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="aed9b-194">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-194">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="aed9b-195">Klik **op Importeren** en vervolgens op **Bestand** importeren om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-195">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="aed9b-196">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-196">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="aed9b-197">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-197">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="aed9b-198">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="aed9b-198">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="aed9b-199">Als u in de stap Begin een sjabloon **hebt** geselecteerd, zijn de meeste van deze waarden al geconfigureerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-199">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="aed9b-200">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-200">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="aed9b-201">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="aed9b-201">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="aed9b-202">U kunt een echt of vervalst e-mailadres invoeren vanuit het e-maildomein van uw organisatie of u kunt een echt of vervalst extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-202">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="aed9b-203">Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="aed9b-203">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="aed9b-204">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="aed9b-204">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="aed9b-205">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="aed9b-205">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="aed9b-206">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="aed9b-206">The choices are:</span></span>

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
     > - <span data-ttu-id="aed9b-207">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="aed9b-207">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="aed9b-208">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-208">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="aed9b-209">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-209">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="aed9b-210">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-210">You are required to select a URL.</span></span> <span data-ttu-id="aed9b-211">Voor **Phishing-campagnes (bijlage)** kunt u in de volgende stap de koppeling verwijderen uit de hoofd tekst van het bericht (anders bevat het bericht zowel een koppeling als **een** bijlage).</span><span class="sxs-lookup"><span data-stu-id="aed9b-211">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="aed9b-212">**Type bijlage:** deze instelling is alleen beschikbaar in **Phishing-campagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="aed9b-212">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="aed9b-213">Klik op de vervolgkeuzepagina en selecteer **. DOCX** of **. PDF** uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="aed9b-213">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="aed9b-214">**Bijlagenaam:** deze instelling is alleen beschikbaar in **Phishing-campagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="aed9b-214">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="aed9b-215">Voer een bestandsnaam in voor de .docx- of .pdf-bijlage.</span><span class="sxs-lookup"><span data-stu-id="aed9b-215">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="aed9b-216">**Aangepaste URL van** landingspagina: voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-216">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="aed9b-217">Deze koppeling vervangt de standaard landingspagina.</span><span class="sxs-lookup"><span data-stu-id="aed9b-217">This link replaces the default landing page.</span></span> <span data-ttu-id="aed9b-218">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="aed9b-218">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="aed9b-219">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-219">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="aed9b-220">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-220">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="aed9b-221">Maak in **de stap E-mailbericht** opstellen de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="aed9b-221">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="aed9b-222">Als u in de beginstap een sjabloon **hebt** geselecteerd, is de bericht zelf al geconfigureerd, maar u kunt deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-222">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="aed9b-223">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="aed9b-223">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="aed9b-224">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="aed9b-224">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="aed9b-225">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="aed9b-225">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="aed9b-226">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="aed9b-226">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="aed9b-227">`${loginserverurl}`de **URL-waarde voor phishing-aanmeldingsserver.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-227">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="aed9b-228">Voor **Phishing-campagnes (bijlage)** moet u de koppeling verwijderen uit de hoofd tekst van  het bericht (anders bevat het bericht zowel een koppeling als een bijlage, en worden klikken op een koppeling niet bij te houden in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="aed9b-228">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aed9b-229">![Bericht zelf opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="aed9b-229">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="aed9b-230">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-230">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="aed9b-231">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-231">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="aed9b-232">Het phishingbericht wordt bezorgd bij de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="aed9b-232">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="aed9b-233">Campagnes voor wachtwoord-aanvallen</span><span class="sxs-lookup"><span data-stu-id="aed9b-233">Password attack campaigns</span></span>

<span data-ttu-id="aed9b-234">Bij *een wachtwoord-aanval* wordt geprobeerd wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="aed9b-234">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="aed9b-235">In de Attack Simulator zijn twee verschillende typen wachtwoord-aanvalscampagnes beschikbaar waarmee u de complexiteit van de wachtwoorden van uw gebruikers kunt testen:</span><span class="sxs-lookup"><span data-stu-id="aed9b-235">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="aed9b-236">**Wachtwoord voor een** 1000-wachtwoord  (aanval van woordenlijsten) - Een force of een aanval van een *woordenlijst* maakt gebruik van een groot woordenlijstbestand met wachtwoorden op een gebruikersaccount, in de hoop dat een van deze wachtwoorden zal werken (veel wachtwoorden voor één account).</span><span class="sxs-lookup"><span data-stu-id="aed9b-236">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="aed9b-237">Onjuiste wachtwoordvergrendeling helpt forceer wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-237">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="aed9b-238">Voor de aanval van de woordenlijst kunt u een of meer wachtwoorden opgeven (handmatig ingevoerd of in een geüpload bestand) en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="aed9b-238">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="aed9b-239">**Wachtwoord-aanval:** bij een *wachtwoord-aanval* wordt hetzelfde wachtwoord gebruikt dat zorgvuldig wordt overwogen voor een lijst met gebruikersaccounts (één wachtwoord voor veel accounts).</span><span class="sxs-lookup"><span data-stu-id="aed9b-239">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="aed9b-240">Wachtwoordaanvallen zijn moeilijker te detecteren dan forceer wachtwoordaanvallen (de kans op succes neemt toe wanneer een aanvaller een wachtwoord probeert te doen via tientallen of honderden accounts zonder het risico dat de verkeerde wachtwoordvergrendeling van de gebruiker struikelen).</span><span class="sxs-lookup"><span data-stu-id="aed9b-240">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="aed9b-241">Voor de wachtwoord-aanval kunt u slechts één wachtwoord opgeven en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="aed9b-241">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="aed9b-242">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord basic-verificatie door aan een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, pass-through, PingFederate, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="aed9b-242">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="aed9b-243">Voor gebruikers die MFA hebben ingeschakeld, wordt de poging altijd als een fout geregistreerd, zelfs als de wachtwoord-aanval  het werkelijke wachtwoord probeert uit te voeren (met andere woorden: MFA-gebruikers worden nooit weergegeven in het aantal geslaagde pogingen van de campagne).</span><span class="sxs-lookup"><span data-stu-id="aed9b-243">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="aed9b-244">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="aed9b-244">This is the expected result.</span></span> <span data-ttu-id="aed9b-245">MFA is een primaire methode om u te beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-245">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="aed9b-246">Een wachtwoord-aanvalscampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="aed9b-246">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="aed9b-247">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-247">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="aed9b-248">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="aed9b-248">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="aed9b-249">Klik in **de sectie Force Password (Dictionary Attack)** op Aanval **starten** of klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-249">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="aed9b-250">klik in **de sectie Wachtwoord voor een** aanval op Aanval starten **of** klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-250">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="aed9b-251">De **wizard Wachtwoord aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="aed9b-251">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="aed9b-252">Voer in **de stap** Start een unieke weergavenaam voor de campagne in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-252">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="aed9b-253">Ga in de stap **Doelgebruikers** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="aed9b-253">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="aed9b-254">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-254">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="aed9b-255">Elke beoogde geadresseerde moet een Postvak IN van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="aed9b-255">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="aed9b-256">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-256">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="aed9b-257">Klik **op Importeren** en vervolgens op **Bestand** importeren om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-257">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="aed9b-258">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-258">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="aed9b-259">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-259">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="aed9b-260">Kies in **de stap Aanvalsinstellingen** kiezen wat u wilt doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="aed9b-260">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="aed9b-261">**ForceEr wachtwoord (aanval van woordenlijst)**: Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="aed9b-261">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="aed9b-262">**Wachtwoorden handmatig invoeren:** typ een wachtwoord in het vak Druk op **Enter** om een wachtwoord toe te voegen en druk op Enter.</span><span class="sxs-lookup"><span data-stu-id="aed9b-262">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="aed9b-263">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="aed9b-263">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="aed9b-264">**Upload wachtwoorden uit een woordenlijstbestand:** klik op Uploaden om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat. </span><span class="sxs-lookup"><span data-stu-id="aed9b-264">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="aed9b-265">Het tekstbestand mag niet groter zijn dan 10 MB en mag niet meer dan 30.000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-265">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="aed9b-266">**Wachtwoord-aanval:** voer één wachtwoord **in het wachtwoord(en) in het aanvalsvak** dat moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-266">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="aed9b-267">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-267">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="aed9b-268">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="aed9b-268">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="aed9b-269">De wachtwoorden die u hebt opgegeven, worden beschreven bij gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="aed9b-269">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="aed9b-270">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="aed9b-270">View campaign results</span></span>

<span data-ttu-id="aed9b-271">Nadat u een campagne hebt gestart, kunt u de voortgang en resultaten controleren op de hoofdpagina **voor het simuleren van** aanvallen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-271">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="aed9b-272">Actieve campagnes tonen een statusbalk, een voltooid percentage en het aantal (voltooide gebruikers) van (totaal aantal gebruikers).</span><span class="sxs-lookup"><span data-stu-id="aed9b-272">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="aed9b-273">Als u op **de knop** Vernieuwen klikt, wordt de voortgang van alle actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-273">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="aed9b-274">U kunt ook op **Beëindigen klikken om** een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="aed9b-274">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="aed9b-275">Wanneer de campagne is voltooid, wordt de status gewijzigd in **Aanval voltooid.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-275">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="aed9b-276">U kunt de resultaten van de campagne weergeven door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="aed9b-276">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="aed9b-277">Klik op de **hoofdpagina voor** het simuleren van aanvallen op **Rapport** weergeven onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-277">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="aed9b-278">Klik op de **hoofdpagina voor het** simuleren van aanvallen op **Details** van aanvallen in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="aed9b-278">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="aed9b-279">Op de **pagina Details van aanval** die wordt geopend, selecteert u de campagne in de sectie **Aanvalsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-279">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="aed9b-280">Met een van de vorige acties gaat u naar een pagina met de naam **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-280">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="aed9b-281">De informatie die beschikbaar is op deze pagina voor elk type campagne, wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="aed9b-281">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="aed9b-282">Phishing-campagneresultaten (referenties, campagneresultaten)</span><span class="sxs-lookup"><span data-stu-id="aed9b-282">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="aed9b-283">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="aed9b-283">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="aed9b-284">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-284">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="aed9b-285">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="aed9b-285">**Total users targeted**</span></span>

- <span data-ttu-id="aed9b-286">**Geslaagde pogingen:** het aantal gebruikers dat  op de koppeling heeft geklikt en hun referenties (elke gebruikersnaam en wachtwoordwaarde) heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="aed9b-286">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="aed9b-287">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-287">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="aed9b-288">**Snelste klik:** de eerste gebruiker heeft na het starten van de campagne op de koppeling geklikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-288">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="aed9b-289">**Gemiddelde klikken:** de som van de tijd die iedereen heeft genomen om op de koppeling te klikken, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-289">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="aed9b-290">**Klik op Succespercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat op de koppeling heeft geklikt) / het totale aantal gebruikers dat op de koppeling **heeft geklikt.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-290">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="aed9b-291">**Snelste referenties:** hoe lang het de eerste gebruiker heeft nodig om zijn of haar referenties in te voeren na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-291">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="aed9b-292">**Gemiddelde referenties:** de som van de tijd die iedereen nodig had om zijn of haar referenties in te voeren, gedeeld door het aantal gebruikers dat de referenties heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="aed9b-292">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="aed9b-293">**Referentiepercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat hun referenties heeft ingevoerd) / **Totaal aantal gebruikers dat is gericht.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-293">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="aed9b-294">A bar graph that shows the **Link clicked** and **Credential supplie numbers** per day.</span><span class="sxs-lookup"><span data-stu-id="aed9b-294">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="aed9b-295">Een cirkeldiagram met de koppeling **klik** **op** de opgegeven referenties en geen **percentages** voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-295">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="aed9b-296">In **de sectie Gekromde** gebruikers worden de details vermeld van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="aed9b-296">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="aed9b-297">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="aed9b-297">The user's email address</span></span>

  - <span data-ttu-id="aed9b-298">De datum/tijd waarop ze op de koppeling hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-298">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="aed9b-299">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="aed9b-299">The client IP address.</span></span>

  - <span data-ttu-id="aed9b-300">Meer informatie over de versie van de gebruiker van Windows en de webbrowser.</span><span class="sxs-lookup"><span data-stu-id="aed9b-300">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="aed9b-301">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-301">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="aed9b-302">Phishing-campagneresultaten (bijlage)</span><span class="sxs-lookup"><span data-stu-id="aed9b-302">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="aed9b-303">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="aed9b-303">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="aed9b-304">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-304">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="aed9b-305">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="aed9b-305">**Total users targeted**</span></span>

- <span data-ttu-id="aed9b-306">**Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (voorbeeld telt niet).</span><span class="sxs-lookup"><span data-stu-id="aed9b-306">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="aed9b-307">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-307">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="aed9b-308">**Snelste tijd bij het openen van** bijlagen: hoe lang het de eerste gebruiker duurde om de bijlage te openen na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-308">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="aed9b-309">**Gemiddelde openstaande tijd voor bijlagen:** de som van de tijd die iedereen nodig had om de bijlage te openen, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="aed9b-309">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="aed9b-310">**Aantal geopende bijlagen:** een percentage dat wordt berekend door (het aantal gebruikers dat de bijlage heeft geopend) / Het totale aantal gebruikers dat de bijlage **heeft geopend.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-310">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="aed9b-311">Campagneresultaten voor Het wachtwoord voor een forceer woordenlijst</span><span class="sxs-lookup"><span data-stu-id="aed9b-311">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="aed9b-312">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="aed9b-312">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="aed9b-313">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-313">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="aed9b-314">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="aed9b-314">**Total users targeted**</span></span>

- <span data-ttu-id="aed9b-315">**Geslaagde pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-315">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="aed9b-316">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-316">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="aed9b-317">In **de sectie Gekromde** gebruikers worden de e-mailadressen van de betrokken gebruikers vermeld.</span><span class="sxs-lookup"><span data-stu-id="aed9b-317">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="aed9b-318">U kunt op **Exporteren klikken** om de resultaten naar een CSV-bestand te exporteren.</span><span class="sxs-lookup"><span data-stu-id="aed9b-318">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="aed9b-319">Resultaten van wachtwoord-aanvalscampagne</span><span class="sxs-lookup"><span data-stu-id="aed9b-319">Password spray attack campaign results</span></span>

<span data-ttu-id="aed9b-320">De volgende informatie is beschikbaar op de **pagina Details van aanval** voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="aed9b-320">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="aed9b-321">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="aed9b-321">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="aed9b-322">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="aed9b-322">**Total users targeted**</span></span>

- <span data-ttu-id="aed9b-323">**Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="aed9b-323">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="aed9b-324">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="aed9b-324">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
