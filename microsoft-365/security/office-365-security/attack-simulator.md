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
ms.openlocfilehash: 7c88a5df6fae61e1ffe70214ad4a73deef4b380e
ms.sourcegitcommit: 6e4ddf35aaf747599f476f9988bcef02cacce1b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/11/2021
ms.locfileid: "50717613"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="6905c-103">Attack Simulator in Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="6905c-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="6905c-104">**Van toepassing op** [Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="6905c-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="6905c-105">Als uw organisatie beschikt over Microsoft Defender voor Office 365 Plan 2, dat functies voor bedreigingsonderzoek en antwoord [bevat,](office-365-ti.md)kunt u de Attack Simulator in het beveiligings- &-compliancecentrum gebruiken om realistische scenario's voor aanvallen in uw organisatie uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6905c-106">Deze gesimuleerde aanvallen kunnen u helpen om kwetsbaar gebruikers te identificeren en te vinden voordat een echte aanval uw bottom line beïnvloedt.</span><span class="sxs-lookup"><span data-stu-id="6905c-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6905c-107">Lees dit artikel voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6905c-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="6905c-108">Attack Simulator, zoals beschreven in dit artikel, is nu alleen-lezen en is vervangen door de training voor de aanvalstraining **in** het samenwerkings knooppunt e-mail **&** samenwerking in het [Microsoft 365-beveiligingscentrum.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="6905c-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="6905c-109">Zie Aan de slag met de trainingstraining [voor de aanvalstraining](attack-simulation-training-get-started.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6905c-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="6905c-110">De mogelijkheid om nieuwe versies van deze versie van Attack Simulator te starten is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="6905c-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="6905c-111">Vanaf 24 januari 2021 hebt u echter nog steeds toegang tot rapporten die nog maximaal 90 dagen duren.</span><span class="sxs-lookup"><span data-stu-id="6905c-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6905c-112">Wat moet u weten voordat u begint?</span><span class="sxs-lookup"><span data-stu-id="6905c-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6905c-113">Ga naar <https://protection.office.com/> om het Beveiligings- en compliancecentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="6905c-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="6905c-114">De attack simulator is beschikbaar op **Threat Management** \> **Attack simulator.**</span><span class="sxs-lookup"><span data-stu-id="6905c-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="6905c-115">Ga rechtstreeks naar de attack simulator, open <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="6905c-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="6905c-116">Zie de servicebeschrijving van Microsoft Defender voor Office 365 voor meer informatie over de beschikbaarheid van Attack Simulator in verschillende Microsoft [365-abonnementen.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="6905c-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6905c-117">U moet lid zijn van de rollengroepen **Organisatiebeheer** of **Beveiligingsbeheerder.**</span><span class="sxs-lookup"><span data-stu-id="6905c-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6905c-118">Zie [Machtigingen in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie over groepen in het Beveiligings- en compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="6905c-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6905c-119">Uw account moet worden geconfigureerd voor meervoudige verificatie (MFA) voor het maken en beheren van campagnes in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="6905c-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="6905c-120">Zie Meervoudige verificatie instellen voor [instructies.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="6905c-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="6905c-121">Attack Simulator werkt alleen voor postvakken in de cloud.</span><span class="sxs-lookup"><span data-stu-id="6905c-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="6905c-122">Phishing-campagnes verzamelen en verwerken gebeurtenissen voor 30 dagen.</span><span class="sxs-lookup"><span data-stu-id="6905c-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="6905c-123">Historische campagnegegevens zijn beschikbaar tot 90 dagen nadat u de campagne hebt gestart.</span><span class="sxs-lookup"><span data-stu-id="6905c-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="6905c-124">Het analyseren van aanvallen en trainingsgerelateerde gegevens worden opgeslagen met andere klantgegevens voor Microsoft 365-services.</span><span class="sxs-lookup"><span data-stu-id="6905c-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="6905c-125">Zie Microsoft [365-gegevenslocaties voor meer informatie.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="6905c-125">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="6905c-126">Er zijn geen bijbehorende PowerShell-cmdlets voor Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="6905c-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="6905c-127">Phishingcampagnes</span><span class="sxs-lookup"><span data-stu-id="6905c-127">Spear phishing campaigns</span></span>

<span data-ttu-id="6905c-128">*Phishing* is een algemene term voor e-mailaanvallen die proberen gevoelige informatie te stelen in berichten die afkomstig lijken te zijn van legitieme of vertrouwde afzenders.</span><span class="sxs-lookup"><span data-stu-id="6905c-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6905c-129">*Phishing is* een gerichte phishing-aanval die gerichte en aangepaste inhoud gebruikt die specifiek is afgestemd op de specifieke ontvangers (meestal na een aanval op de ontvangers door de aanvaller).</span><span class="sxs-lookup"><span data-stu-id="6905c-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="6905c-130">In Attack Simulator zijn twee verschillende typen phishingcampagnes beschikbaar:</span><span class="sxs-lookup"><span data-stu-id="6905c-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="6905c-131">**Phishing onder de aandacht brengen (referentiegegevens)**: de aanval probeert de ontvangers ervan te overtuigen op een URL in het bericht te klikken.</span><span class="sxs-lookup"><span data-stu-id="6905c-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="6905c-132">Als de gebruiker op de koppeling klikt, wordt hem of haar gevraagd zijn of haar referenties in te voeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="6905c-133">Als ze dit doen, gaan ze naar een van de volgende locaties:</span><span class="sxs-lookup"><span data-stu-id="6905c-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="6905c-134">Een standaardpagina waarin wordt uitgelegd dat dit slechts een test was, en tips voor het herkennen van phishing-berichten.</span><span class="sxs-lookup"><span data-stu-id="6905c-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Wat gebruikers zien als ze op de phishing-koppeling klikken en hun referenties invoeren](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="6905c-136">Een aangepaste pagina (URL) die u opgeeft.</span><span class="sxs-lookup"><span data-stu-id="6905c-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="6905c-137">**Phishing (bijlage)**- De aanval probeert de ontvangers ervan te overtuigen dat ze een DOCX- of PDF-bijlage in het bericht moeten openen.</span><span class="sxs-lookup"><span data-stu-id="6905c-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="6905c-138">De bijlage bevat dezelfde inhoud van de standaard phishing-koppeling, maar de eerste zin begint met " , u ziet dit bericht als een recent e-mailbericht dat u \<Display Name\> hebt geopend...".</span><span class="sxs-lookup"><span data-stu-id="6905c-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="6905c-139">Momenteel verlopen phishingcampagnes in Attack Simulator niet.</span><span class="sxs-lookup"><span data-stu-id="6905c-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="6905c-140">Een phishingcampagne maken</span><span class="sxs-lookup"><span data-stu-id="6905c-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="6905c-141">Een belangrijk onderdeel van een phishingcampagne is het uiterlijk van het e-mailbericht dat naar de geadresseerden wordt verzonden.</span><span class="sxs-lookup"><span data-stu-id="6905c-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="6905c-142">Als u het e-mailbericht wilt maken en configureren, hebt u de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="6905c-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="6905c-143">**Gebruik een ingebouwde e-mailsjabloon:** Er zijn twee ingebouwde sjablonen beschikbaar: **Giveaway** voor prijzen en **Salarisadministratie Update.**</span><span class="sxs-lookup"><span data-stu-id="6905c-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="6905c-144">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="6905c-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6905c-145">**Maak een herbruikbare e-mailsjabloon:** nadat u de e-mailsjabloon hebt gemaakt en opgeslagen, kunt u deze opnieuw gebruiken in toekomstige phishingcampagnes.</span><span class="sxs-lookup"><span data-stu-id="6905c-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="6905c-146">U kunt nog enkele, alle of geen e-maileigenschappen van de sjabloon aanpassen wanneer u de campagne maakt en start.</span><span class="sxs-lookup"><span data-stu-id="6905c-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6905c-147">**Maak het e-mailbericht in de wizard:** u kunt het e-mailbericht rechtstreeks in de wizard maken tijdens het maken en starten van de phishingcampagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="6905c-148">Stap 1 (optioneel): Een aangepaste e-mailsjabloon maken</span><span class="sxs-lookup"><span data-stu-id="6905c-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="6905c-149">Als u een van de ingebouwde sjablonen wilt gebruiken of het e-mailbericht rechtstreeks in de wizard wilt maken, kunt u deze stap overslaan.</span><span class="sxs-lookup"><span data-stu-id="6905c-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="6905c-150">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="6905c-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6905c-151">Klik op **de pagina** Aanvallen nabootsen in de **secties Phishing (Referenties** worden ontvangen) of Phishing via phishing **(bijlage)** op **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="6905c-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="6905c-152">Het maakt niet uit waar u de sjabloon maakt.</span><span class="sxs-lookup"><span data-stu-id="6905c-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="6905c-153">De beschikbare opties in de sjabloon zijn hetzelfde voor beide soorten phishing-aanvallen.</span><span class="sxs-lookup"><span data-stu-id="6905c-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="6905c-154">Klik op **de pagina Details** van aanval die wordt geopend in de sectie **Phishing-sjablonen** in het gebied **Sjablonen** maken op Nieuwe **sjabloon.**</span><span class="sxs-lookup"><span data-stu-id="6905c-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="6905c-155">De **wizard Phishingsjabloon** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="6905c-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="6905c-156">Voer in **de stap** Start een unieke weergavenaam voor de sjabloon in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6905c-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="6905c-157">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="6905c-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="6905c-158">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6905c-159">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="6905c-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="6905c-160">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="6905c-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6905c-161">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="6905c-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6905c-162">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="6905c-162">The choices are:</span></span>

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
     > <span data-ttu-id="6905c-163">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6905c-164">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="6905c-165">**Aangepaste landingspagina-URL:** voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6905c-166">Deze koppeling vervangt de standaardlandingspagina.</span><span class="sxs-lookup"><span data-stu-id="6905c-166">This link replaces the default landing page.</span></span> <span data-ttu-id="6905c-167">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="6905c-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6905c-168">**Categorie:** deze instelling wordt momenteel niet gebruikt (alles wat u optreedt, wordt genegeerd).</span><span class="sxs-lookup"><span data-stu-id="6905c-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="6905c-169">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6905c-170">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6905c-171">Maak in **de stap E-mailbericht opstellen** de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6905c-172">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6905c-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6905c-173">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="6905c-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6905c-174">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="6905c-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6905c-175">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="6905c-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6905c-176">`${loginserverurl}` voegt de **URL-waarde voor Phishing Login Server** uit de vorige stap in.</span><span class="sxs-lookup"><span data-stu-id="6905c-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="6905c-177">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6905c-178">Klik in **de stap** Bevestigen op **Voltooien.**</span><span class="sxs-lookup"><span data-stu-id="6905c-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="6905c-179">Stap 2: De phishingcampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="6905c-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="6905c-180">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="6905c-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6905c-181">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="6905c-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6905c-182">Klik in **de sectie Phishing phishing (credentials er wordt gestolen)** op Aanval **starten** of klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="6905c-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6905c-183">Klik in **de sectie Phishing (bijlage) op** Aanval starten **of** klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="6905c-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6905c-184">De **wizard Phishing-aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="6905c-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6905c-185">Ga in **de stap** Start op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="6905c-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6905c-186">Voer in **het** vak Naam een unieke weergavenaam voor de campagne in.</span><span class="sxs-lookup"><span data-stu-id="6905c-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="6905c-187">Klik niet op **Sjabloon gebruiken,** want u maakt het e-mailbericht later in de wizard.</span><span class="sxs-lookup"><span data-stu-id="6905c-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="6905c-188">Klik **op Sjabloon gebruiken** en selecteer een ingebouwde of aangepaste e-mailsjabloon.</span><span class="sxs-lookup"><span data-stu-id="6905c-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="6905c-189">Nadat u de sjabloon hebt geselecteerd, wordt **het** vak Naam automatisch ingevuld op basis van de sjabloon, maar u kunt de naam wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6905c-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6905c-190">![Startpagina phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="6905c-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="6905c-191">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6905c-192">Ga in **de stap Geadresseerden van** het doel op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="6905c-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6905c-193">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6905c-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6905c-194">Elke beoogde geadresseerde moet een Postvak IN van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="6905c-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6905c-195">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6905c-196">Klik **op Importeren** en Vervolgens Bestand **importeren** om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6905c-197">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="6905c-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6905c-198">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6905c-199">Configureer **de volgende instellingen** in de stap E-maildetails configureren:</span><span class="sxs-lookup"><span data-stu-id="6905c-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="6905c-200">Als u in de stap Begin een sjabloon **hebt** geselecteerd, zijn de meeste van deze waarden al geconfigureerd, maar u kunt deze wijzigen.</span><span class="sxs-lookup"><span data-stu-id="6905c-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="6905c-201">**Van (Naam)**: De weergavenaam die wordt gebruikt voor de afzender van het bericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6905c-202">**Van (E-mail)**: Het e-mailadres van de afzender.</span><span class="sxs-lookup"><span data-stu-id="6905c-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="6905c-203">U kunt een echt of vervalst e-mailadres invoeren vanuit het e-maildomein van uw organisatie of u kunt een echt of vervalst extern e-mailadres invoeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="6905c-204">Een geldig e-mailadres van de afzender van uw organisatie wordt daadwerkelijk opgelost in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="6905c-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="6905c-205">**URL van phishing-aanmeldingsserver:** klik op de vervolgkeuzelijst en selecteer een van de beschikbare URL's in de lijst.</span><span class="sxs-lookup"><span data-stu-id="6905c-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6905c-206">Dit is de URL waar gebruikers op kunnen klikken.</span><span class="sxs-lookup"><span data-stu-id="6905c-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6905c-207">U hebt de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="6905c-207">The choices are:</span></span>

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
     > - <span data-ttu-id="6905c-208">Alle URL's zijn opzettelijk http, niet https.</span><span class="sxs-lookup"><span data-stu-id="6905c-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="6905c-209">Een URL-reputatieservice kan een of meer van deze URL's als onveilig identificeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6905c-210">Controleer de beschikbaarheid van de URL in de ondersteunde webbrowsers voordat u de URL gebruikt in een phishing-campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="6905c-211">U moet een URL selecteren.</span><span class="sxs-lookup"><span data-stu-id="6905c-211">You are required to select a URL.</span></span> <span data-ttu-id="6905c-212">Voor **Phishing-campagnes (bijlage)** kunt u in de volgende stap de koppeling verwijderen uit de hoofd tekst van het bericht (anders bevat het bericht zowel een koppeling als **een** bijlage).</span><span class="sxs-lookup"><span data-stu-id="6905c-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="6905c-213">**Type bijlage:** deze instelling is alleen beschikbaar in **Phishing-campagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="6905c-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6905c-214">Klik op de vervolgkeuzepagina en selecteer **. DOCX** of **. PDF** uit de lijst.</span><span class="sxs-lookup"><span data-stu-id="6905c-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="6905c-215">**Bijlagenaam:** deze instelling is alleen beschikbaar in **Phishing-campagnes (bijlage).**</span><span class="sxs-lookup"><span data-stu-id="6905c-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6905c-216">Voer een bestandsnaam in voor de .docx- of .pdf-bijlage.</span><span class="sxs-lookup"><span data-stu-id="6905c-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="6905c-217">**Aangepaste landingspagina-URL:** voer een optionele landingspagina in waar gebruikers worden geplaatst als ze op de phishing-koppeling klikken en hun referenties invoeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6905c-218">Deze koppeling vervangt de standaardlandingspagina.</span><span class="sxs-lookup"><span data-stu-id="6905c-218">This link replaces the default landing page.</span></span> <span data-ttu-id="6905c-219">Als u bijvoorbeeld een interne informatietraining hebt, kunt u deze URL hier opgeven.</span><span class="sxs-lookup"><span data-stu-id="6905c-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6905c-220">**Onderwerp:** het **veld Onderwerp** van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6905c-221">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6905c-222">Maak in **de stap E-mailbericht opstellen** de bericht zelf van het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="6905c-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6905c-223">Als u in de beginstap een sjabloon **hebt** geselecteerd, is de bericht zelf al geconfigureerd, maar u kunt deze aanpassen.</span><span class="sxs-lookup"><span data-stu-id="6905c-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="6905c-224">U kunt het tabblad **E-mail** (een uitgebreide HTML-editor) of het **tabblad** Bron (onbewerkte HTML-code) gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6905c-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6905c-225">De HTML-opmaak kan zo eenvoudig of complex zijn als nodig is.</span><span class="sxs-lookup"><span data-stu-id="6905c-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6905c-226">U kunt afbeeldingen en tekst invoegen om de betrouwbaarheid van het bericht te vergroten in de e-mailclient van de geadresseerde.</span><span class="sxs-lookup"><span data-stu-id="6905c-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6905c-227">`${username}` voegt de naam van de geadresseerde in.</span><span class="sxs-lookup"><span data-stu-id="6905c-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6905c-228">`${loginserverurl}`de **URL-waarde voor phishing-aanmeldingsserver.**</span><span class="sxs-lookup"><span data-stu-id="6905c-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="6905c-229">Voor **Phishing-campagnes (bijlage)** moet u de koppeling verwijderen uit de hoofd tekst van  het bericht (anders bevat het bericht zowel een koppeling als een bijlage, en worden klikken op een koppeling niet bij te houden in een bijlagecampagne).</span><span class="sxs-lookup"><span data-stu-id="6905c-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6905c-230">![Bericht zelf opstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="6905c-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="6905c-231">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6905c-232">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="6905c-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6905c-233">Het phishingbericht wordt bezorgd bij de geadresseerden.</span><span class="sxs-lookup"><span data-stu-id="6905c-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="6905c-234">Wachtwoord-aanvalcampagnes</span><span class="sxs-lookup"><span data-stu-id="6905c-234">Password attack campaigns</span></span>

<span data-ttu-id="6905c-235">Bij *een wachtwoord-aanval* wordt geprobeerd wachtwoorden te raden voor gebruikersaccounts in een organisatie, meestal nadat de aanvaller een of meer geldige gebruikersaccounts heeft geïdentificeerd.</span><span class="sxs-lookup"><span data-stu-id="6905c-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="6905c-236">In de Attack Simulator zijn twee verschillende typen campagnes voor wachtwoord-aanvallen beschikbaar om de complexiteit van de wachtwoorden van uw gebruikers te testen:</span><span class="sxs-lookup"><span data-stu-id="6905c-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="6905c-237">**Wachtwoord voor een** 1000-wachtwoord  (aanval van woordenlijsten) - Een force of een aanval van een *woordenlijst* maakt gebruik van een groot woordenlijstbestand met wachtwoorden op een gebruikersaccount, in de hoop dat een van deze wachtwoorden zal werken (veel wachtwoorden voor één account).</span><span class="sxs-lookup"><span data-stu-id="6905c-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="6905c-238">Onjuiste wachtwoordvergrendeling helpt forceer wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="6905c-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="6905c-239">Voor de aanval van de woordenlijst kunt u een of meer wachtwoorden opgeven (handmatig ingevoerd of in een geüpload bestand) en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="6905c-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="6905c-240">**Wachtwoord-aanval:** bij een *wachtwoord-aanval* wordt hetzelfde wachtwoord gebruikt dat zorgvuldig wordt overwogen voor een lijst met gebruikersaccounts (één wachtwoord voor veel accounts).</span><span class="sxs-lookup"><span data-stu-id="6905c-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="6905c-241">Wachtwoordaanvallen zijn moeilijker te detecteren dan forceer wachtwoordaanvallen (de kans op succes neemt toe wanneer een aanvaller een wachtwoord probeert te doen via tientallen of honderden accounts zonder het risico dat de verkeerde wachtwoordvergrendeling van de gebruiker struikelen).</span><span class="sxs-lookup"><span data-stu-id="6905c-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="6905c-242">Voor de wachtwoord-aanval kunt u slechts één wachtwoord opgeven en u kunt een of meer gebruikers opgeven.</span><span class="sxs-lookup"><span data-stu-id="6905c-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="6905c-243">De wachtwoordaanvallen in Attack Simulator geven gebruikersnaam en wachtwoord basic-verificatie door aan een eindpunt, zodat ze ook werken met andere verificatiemethoden (AD FS, wachtwoordhashsynchronisatie, pass-through, PingFederate, enzovoort).</span><span class="sxs-lookup"><span data-stu-id="6905c-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="6905c-244">Voor gebruikers die MFA hebben ingeschakeld, wordt de poging altijd als een fout geregistreerd, zelfs als de wachtwoord-aanval  het werkelijke wachtwoord probeert uit te voeren (met andere woorden: MFA-gebruikers worden nooit weergegeven in het aantal succesvolle pogingen van de campagne).</span><span class="sxs-lookup"><span data-stu-id="6905c-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="6905c-245">Dit is het verwachte resultaat.</span><span class="sxs-lookup"><span data-stu-id="6905c-245">This is the expected result.</span></span> <span data-ttu-id="6905c-246">MFA is een primaire methode om u te beschermen tegen wachtwoordaanvallen.</span><span class="sxs-lookup"><span data-stu-id="6905c-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="6905c-247">Een wachtwoord-aanvalscampagne maken en starten</span><span class="sxs-lookup"><span data-stu-id="6905c-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="6905c-248">Ga in het & Compliancecentrum naar **de threat management** Attack \> **simulator.**</span><span class="sxs-lookup"><span data-stu-id="6905c-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6905c-249">Maak op **de pagina** Simuleren aanvallen een van de volgende selecties op basis van het type campagne dat u wilt maken:</span><span class="sxs-lookup"><span data-stu-id="6905c-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6905c-250">Klik in **de sectie Force Password (Dictionary Attack)** op Aanval **starten** of klik op **Aanvalsdetails starten.** \> </span><span class="sxs-lookup"><span data-stu-id="6905c-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6905c-251">klik in **de sectie Wachtwoord voor een** aanval op Aanval starten **of** klik op **Aanvalsdetails** \> **starten.**</span><span class="sxs-lookup"><span data-stu-id="6905c-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6905c-252">De **wizard Wachtwoord aanval** configureren wordt gestart in een nieuwe flyout.</span><span class="sxs-lookup"><span data-stu-id="6905c-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6905c-253">Voer in **de stap** Start een unieke weergavenaam voor de campagne in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6905c-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="6905c-254">Ga in de stap **Doelgebruikers** op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="6905c-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6905c-255">Klik **op Adresboek** om de geadresseerden (gebruikers of groepen) voor de campagne te selecteren.</span><span class="sxs-lookup"><span data-stu-id="6905c-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6905c-256">Elke beoogde geadresseerde moet een Postvak IN van Exchange Online hebben.</span><span class="sxs-lookup"><span data-stu-id="6905c-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6905c-257">Als u op **Filteren en** **Toepassen** klikt zonder zoekcriteria in te voeren, worden alle geadresseerden geretourneerd en toegevoegd aan de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6905c-258">Klik **op Importeren** en Vervolgens Bestand **importeren** om een bestand met door komma's gescheiden waarden (CSV) of een bestand met e-mailadressen met door komma's gescheiden waarden te importeren.</span><span class="sxs-lookup"><span data-stu-id="6905c-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6905c-259">Elke regel moet het e-mailadres van de geadresseerde bevatten.</span><span class="sxs-lookup"><span data-stu-id="6905c-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6905c-260">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6905c-261">Kies in **de stap Aanvalsinstellingen** kiezen wat u wilt doen op basis van het campagnetype:</span><span class="sxs-lookup"><span data-stu-id="6905c-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="6905c-262">**ForceEr wachtwoord (aanval van woordenlijst)**: Ga op een van de volgende stappen te werk:</span><span class="sxs-lookup"><span data-stu-id="6905c-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="6905c-263">**Wachtwoorden handmatig invoeren:** typ een wachtwoord in het vak Druk op **Enter** om een wachtwoord toe te voegen en druk op Enter.</span><span class="sxs-lookup"><span data-stu-id="6905c-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="6905c-264">Herhaal deze stap zo vaak als nodig is.</span><span class="sxs-lookup"><span data-stu-id="6905c-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="6905c-265">**Upload wachtwoorden uit een woordenlijstbestand:** klik op Uploaden om een bestaand tekstbestand te importeren dat één wachtwoord op elke regel en een lege laatste regel bevat. </span><span class="sxs-lookup"><span data-stu-id="6905c-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="6905c-266">Het tekstbestand mag niet groter zijn dan 10 MB en mag niet meer dan 30.000 wachtwoorden bevatten.</span><span class="sxs-lookup"><span data-stu-id="6905c-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="6905c-267">**Wachtwoord-aanval:** voer één wachtwoord **in het wachtwoord(en) in het aanvalsvak** dat moet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="6905c-268">Klik op Volgende wanneer u klaar **bent.**</span><span class="sxs-lookup"><span data-stu-id="6905c-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6905c-269">Klik in **de stap** Bevestigen op **Voltooien om** de campagne te starten.</span><span class="sxs-lookup"><span data-stu-id="6905c-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6905c-270">De wachtwoorden die u hebt opgegeven, worden beschreven bij gebruikers die u hebt opgegeven.</span><span class="sxs-lookup"><span data-stu-id="6905c-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="6905c-271">Campagneresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="6905c-271">View campaign results</span></span>

<span data-ttu-id="6905c-272">Nadat u een campagne hebt gestart, kunt u de voortgang en resultaten controleren op de hoofdpagina **voor het simuleren van** aanvallen.</span><span class="sxs-lookup"><span data-stu-id="6905c-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="6905c-273">Actieve campagnes tonen een statusbalk, een voltooid percentage en het aantal (voltooide gebruikers) van (totaal aantal gebruikers).</span><span class="sxs-lookup"><span data-stu-id="6905c-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="6905c-274">Als u op **de knop** Vernieuwen klikt, wordt de voortgang van alle actieve campagnes bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="6905c-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="6905c-275">U kunt ook op **Beëindigen klikken om** een actieve campagne te stoppen.</span><span class="sxs-lookup"><span data-stu-id="6905c-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="6905c-276">Wanneer de campagne is voltooid, wordt de status gewijzigd in **Aanval voltooid.**</span><span class="sxs-lookup"><span data-stu-id="6905c-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="6905c-277">U kunt de resultaten van de campagne weergeven door een van de volgende acties uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="6905c-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="6905c-278">Klik op de **hoofdpagina voor** het simuleren van aanvallen op **Rapport** weergeven onder de naam van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="6905c-279">Klik op de **hoofdpagina voor het** simuleren van aanvallen op **Details** van aanvallen in de sectie voor het type aanval.</span><span class="sxs-lookup"><span data-stu-id="6905c-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="6905c-280">Op de **pagina Details van aanval** die wordt geopend, selecteert u de campagne in de sectie **Aanvalsgeschiedenis.**</span><span class="sxs-lookup"><span data-stu-id="6905c-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="6905c-281">Met een van de vorige acties gaat u naar een pagina met de naam **Details van aanval.**</span><span class="sxs-lookup"><span data-stu-id="6905c-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="6905c-282">De informatie die beschikbaar is op deze pagina voor elk type campagne, wordt beschreven in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="6905c-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="6905c-283">Phishing-campagneresultaten (referenties, campagneresultaten)</span><span class="sxs-lookup"><span data-stu-id="6905c-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="6905c-284">De volgende informatie is beschikbaar op de **pagina met details over** aanvallen voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="6905c-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6905c-285">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6905c-286">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="6905c-286">**Total users targeted**</span></span>

- <span data-ttu-id="6905c-287">**Geslaagde pogingen:** het aantal gebruikers dat  op de koppeling heeft geklikt en hun referenties *(elke* gebruikersnaam en wachtwoordwaarde) heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="6905c-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="6905c-288">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="6905c-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6905c-289">**Snelste klik:** de eerste gebruiker heeft na het starten van de campagne op de koppeling geklikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="6905c-290">**Gemiddelde klikken:** de som van de tijd die iedereen heeft genomen om op de koppeling te klikken, gedeeld door het aantal gebruikers dat op de koppeling heeft geklikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="6905c-291">**Klik op Succespercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat op de koppeling heeft geklikt) / het totale aantal gebruikers dat op de koppeling **heeft geklikt.**</span><span class="sxs-lookup"><span data-stu-id="6905c-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="6905c-292">**Snelste referenties:** hoe lang het de eerste gebruiker heeft nodig om zijn of haar referenties in te voeren na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="6905c-293">**Gemiddelde referenties:** de som van de tijd die iedereen nodig had om zijn of haar referenties in te voeren, gedeeld door het aantal gebruikers dat de referenties heeft ingevoerd.</span><span class="sxs-lookup"><span data-stu-id="6905c-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="6905c-294">**Referentiepercentage:** een percentage dat wordt berekend door (het aantal gebruikers dat hun referenties heeft ingevoerd) / **Totaal aantal gebruikers dat is gericht.**</span><span class="sxs-lookup"><span data-stu-id="6905c-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="6905c-295">A bar graph that shows the **Link clicked** and **Credential supplie numbers** per day.</span><span class="sxs-lookup"><span data-stu-id="6905c-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="6905c-296">Een cirkeldiagram met de koppeling **klik** **op** de opgegeven referenties en geen **percentages** voor de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="6905c-297">In **de sectie Gekromde** gebruikers worden de details vermeld van de gebruikers die op de koppeling hebben geklikt:</span><span class="sxs-lookup"><span data-stu-id="6905c-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="6905c-298">Het e-mailadres van de gebruiker</span><span class="sxs-lookup"><span data-stu-id="6905c-298">The user's email address</span></span>

  - <span data-ttu-id="6905c-299">De datum/tijd waarop ze op de koppeling hebben geklikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="6905c-300">Het IP-adres van de client.</span><span class="sxs-lookup"><span data-stu-id="6905c-300">The client IP address.</span></span>

  - <span data-ttu-id="6905c-301">Meer informatie over de versie van de gebruiker van Windows en de webbrowser.</span><span class="sxs-lookup"><span data-stu-id="6905c-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="6905c-302">U kunt op **Exporteren klikken** om de resultaten te exporteren naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="6905c-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="6905c-303">Phishing-campagneresultaten (bijlage)</span><span class="sxs-lookup"><span data-stu-id="6905c-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="6905c-304">De volgende informatie is beschikbaar op de **pagina met details over** aanvallen voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="6905c-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6905c-305">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6905c-306">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="6905c-306">**Total users targeted**</span></span>

- <span data-ttu-id="6905c-307">**Geslaagde pogingen:** het aantal gebruikers dat de bijlage heeft geopend of gedownload en geopend (preview telt niet).</span><span class="sxs-lookup"><span data-stu-id="6905c-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="6905c-308">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="6905c-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6905c-309">**Snelste tijd bij het openen van** bijlagen: hoe lang het de eerste gebruiker duurde om de bijlage te openen na het starten van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="6905c-310">**Gemiddelde open tijd voor bijlagen:** de som van de tijd die iedereen nodig had om de bijlage te openen, gedeeld door het aantal gebruikers dat de bijlage heeft geopend.</span><span class="sxs-lookup"><span data-stu-id="6905c-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="6905c-311">**Succespercentage van geopende bijlage:** een percentage dat wordt berekend door (het aantal gebruikers dat de bijlage heeft geopend) / Het totale aantal gebruikers dat de bijlage **heeft geopend.**</span><span class="sxs-lookup"><span data-stu-id="6905c-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="6905c-312">Campagneresultaten voor Het wachtwoord voor een forceer woordenlijst</span><span class="sxs-lookup"><span data-stu-id="6905c-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="6905c-313">De volgende informatie is beschikbaar op de **pagina met details over** aanvallen voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="6905c-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6905c-314">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6905c-315">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="6905c-315">**Total users targeted**</span></span>

- <span data-ttu-id="6905c-316">**Geslaagde pogingen:** het aantal gebruikers dat een van de opgegeven wachtwoorden heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="6905c-317">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="6905c-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6905c-318">In **de sectie Gekromde** gebruikers worden de e-mailadressen van de betrokken gebruikers vermeld.</span><span class="sxs-lookup"><span data-stu-id="6905c-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="6905c-319">U kunt op **Exporteren klikken** om de resultaten te exporteren naar een CSV-bestand.</span><span class="sxs-lookup"><span data-stu-id="6905c-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="6905c-320">Resultaten van wachtwoord-aanvalscampagne</span><span class="sxs-lookup"><span data-stu-id="6905c-320">Password spray attack campaign results</span></span>

<span data-ttu-id="6905c-321">De volgende informatie is beschikbaar op de **pagina met details over** aanvallen voor elke campagne:</span><span class="sxs-lookup"><span data-stu-id="6905c-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6905c-322">De duur (begindatum/-tijd en einddatum/-tijd) van de campagne.</span><span class="sxs-lookup"><span data-stu-id="6905c-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6905c-323">**Totaal aantal gerichte gebruikers**</span><span class="sxs-lookup"><span data-stu-id="6905c-323">**Total users targeted**</span></span>

- <span data-ttu-id="6905c-324">**Geslaagde pogingen:** het aantal gebruikers dat het opgegeven wachtwoord heeft gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6905c-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="6905c-325">**Overall Success Rate:** A percentage that's calculated by **Successful attempts** Total  /  **users targeted.**</span><span class="sxs-lookup"><span data-stu-id="6905c-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
