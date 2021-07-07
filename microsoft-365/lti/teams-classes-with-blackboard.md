---
title: Integratie Microsoft Teams klassen met Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integratie Microsoft Teams klassen met Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314489"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="e393e-103">Gebruik Microsoft Teams met Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="e393e-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="e393e-104">Teamwerk staat centraal in elke moderne organisatie.</span><span class="sxs-lookup"><span data-stu-id="e393e-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="e393e-105">Door samenwerking te bevorderen, is het een bepalend kenmerk van elke succesvolle instelling.</span><span class="sxs-lookup"><span data-stu-id="e393e-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="e393e-106">U kunt alle mogelijkheden en functies van Blackboard Learn Ultra verbeteren door ze te koppelen aan Microsoft Teams klassen.</span><span class="sxs-lookup"><span data-stu-id="e393e-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="e393e-107">Uw lessen kunnen realtime gesprekken, videovergaderingen of asynchrone interacties bevatten.</span><span class="sxs-lookup"><span data-stu-id="e393e-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="e393e-108">U kunt bestanden delen en cocreatie-ervaringen toevoegen voor uw leerlingen/studenten, allemaal op één plek.</span><span class="sxs-lookup"><span data-stu-id="e393e-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="e393e-109">Microsoft Teams met Learn Ultra de dynamiek van het onderwijs opnieuw definiëren en wat effectief leren betekent.</span><span class="sxs-lookup"><span data-stu-id="e393e-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e393e-110">Zorg ervoor dat u het veld Instellingse-e-mail hebt ingesteld in uw SIS (Student Information System) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="e393e-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="e393e-111">De Microsoft Teams klassenintegratie is afhankelijk van het e-mailveld van de instelling in uw SIS om de juiste Microsoft Azure Active Directory's (AAD) User Principal Name (UPN) toe te vertrouwen.</span><span class="sxs-lookup"><span data-stu-id="e393e-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="e393e-112">Als er geen e-mail van een instelling is ingericht, wordt dit standaard ingesteld op de bestaande e-mail.</span><span class="sxs-lookup"><span data-stu-id="e393e-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="e393e-113">U wordt aangeraden dit veld in te stellen voor elke gebruiker om ervoor te zorgen dat hun gegevens correct worden gesynchroniseerd en dat er geen conflict is tussen e-mailgegevens tussen Microsoft AAD en Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="e393e-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="e393e-114">Als u dit veld niet op de juiste manier hebt ingesteld in de SIS-toewijzing, blijft de integratie werken, maar worden gebruikers mogelijk niet weergegeven in de Teams-klassen die zijn gemaakt en kunnen er fouten optreden.</span><span class="sxs-lookup"><span data-stu-id="e393e-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="e393e-115">Ondersteuning voor het toewijzen van institutionele gegevens – SIS-veld instellings-e-mail</span><span class="sxs-lookup"><span data-stu-id="e393e-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="e393e-116">Als onderdeel van de ontwikkeling met cloudproviderintegraties heeft  Blackboard Learn Ultra een nieuw veld Voor e-mail van instellingen gemaakt, zowel in de integratie van het Student Information System Framework als openbare REST-API's, zodat instellingen het proces voor gegevenssynchronisatie effectief kunnen beheren tussen Blackboard Learn Ultra en Microsoft AAD.</span><span class="sxs-lookup"><span data-stu-id="e393e-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="e393e-117">Wat betekent de e-mail van de instelling en wat wordt er ondersteund?</span><span class="sxs-lookup"><span data-stu-id="e393e-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="e393e-118">In het veld Instellings-e-mail kunnen aangepaste veldtoewijzingen worden gemaakt tussen de extern ondersteunde gegevensbronnen van een client en Blackboard Learn Ultra. </span><span class="sxs-lookup"><span data-stu-id="e393e-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="e393e-119">Als gegevensbronnen cloudproviders zijn, zoals Microsoft, is de UPN (User Principle Name) een primaire unieke id voor elke gebruiker die bestaat uit een UPN-voorvoegsel (de accountnaam van de gebruiker) en een UPN-achtervoegsel (een DNS-domeinnaam) die is samengevoegd met een @-symbool.</span><span class="sxs-lookup"><span data-stu-id="e393e-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="e393e-120">Hiermee wordt een uniek e-mailadres gemaakt voor elke specifieke gebruiker binnen de Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e393e-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="e393e-121">Om ervoor te zorgen dat gegevens nauwkeurig zijn en registraties of lidmaatschappen tussen Blackboard Learn Ultra en Microsoft Teams-klassen correct worden bereikt, moet het e-mailadres van een gebruiker overeenkomen tussen beide systemen.</span><span class="sxs-lookup"><span data-stu-id="e393e-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="e393e-122">In Blackboard Learn Ultra kunnen gebruikers hun bestaande e-mailadres wijzigen of overschrijven in de gebruikersinterface, wat kan leiden tot synchronisatiefouten en dat de gebruiker niet correct wordt toegevoegd aan een klasteam.</span><span class="sxs-lookup"><span data-stu-id="e393e-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="e393e-123">Met **de toewijzing** van het veld Institution Email zorgt u ervoor dat dit beveiligings- en validatiecontroleniveau correct kan worden beheerd, ongeacht of gebruikers hun e-mail hebben gewijzigd in Blackboard Learn Ultra of niet.</span><span class="sxs-lookup"><span data-stu-id="e393e-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="e393e-124">Als er twee e-mailadressen verschillen, is dit het volgende:</span><span class="sxs-lookup"><span data-stu-id="e393e-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="e393e-125">Er moet een beslissing worden genomen over welke bron voorrang heeft en wordt zowel als de e-mails van de persoon als de e-mail van de instelling genomen.</span><span class="sxs-lookup"><span data-stu-id="e393e-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="e393e-126">Of</span><span class="sxs-lookup"><span data-stu-id="e393e-126">Or</span></span>
- <span data-ttu-id="e393e-127">Een instelling kan een aangepaste veldtoewijzing instellen in de instellings-e-mail, waarmee een mogelijk conflict kan worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="e393e-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="e393e-128">De **toewijzing van** het veld Institution Email is nu beschikbaar voor alle bestaande SIS-integratietypen op Advanced Configuration **Instellingen** Users Learn Object  >  **Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="e393e-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="e393e-129">Het is belangrijk om te weten dat instellings-e-mail standaard **is** ingesteld op e-mail van persoon voor alle SIS-indelingen en uniek moet zijn voor elke persoon. </span><span class="sxs-lookup"><span data-stu-id="e393e-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="e393e-130">Voor alle bestaande integraties die zijn ingesteld en uitgevoerd, is deze gegevenstoewijzing ingesteld, omdat sis gebruikers niet kan importeren als hun e-mail is gedupliceerd.</span><span class="sxs-lookup"><span data-stu-id="e393e-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="e393e-131">Als een instelling de mogelijkheid vereist om de instellings-e-mail te wijzigen **in** **aangepast,** moet de instelling dit beheren via de Instellingen geavanceerde configuratie in het SIS.</span><span class="sxs-lookup"><span data-stu-id="e393e-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="e393e-132">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e393e-132">Requirements</span></span>

<span data-ttu-id="e393e-133">De Microsoft Teams klassenintegratie is alleen beschikbaar voor **cursussen voor Ultra Course View.**</span><span class="sxs-lookup"><span data-stu-id="e393e-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="e393e-134">Uw instelling moet aan deze vereisten voldoen om deze te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="e393e-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="e393e-135">Laat Blackboard Learn Ultra Learn SaaS met Ultra Base Navigation ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e393e-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="e393e-136">LTI inschakelen voor gebruik in cursussen.</span><span class="sxs-lookup"><span data-stu-id="e393e-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="e393e-137">a.</span><span class="sxs-lookup"><span data-stu-id="e393e-137">a.</span></span> <span data-ttu-id="e393e-138">Ga naar de **LTI-hulpprogramma's** van  >  **het beheerderspaneel**  >  **Globale eigenschappen beheren.**</span><span class="sxs-lookup"><span data-stu-id="e393e-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="e393e-139">b.</span><span class="sxs-lookup"><span data-stu-id="e393e-139">b.</span></span> <span data-ttu-id="e393e-140">Selecteer **LTI ingeschakeld in cursussen** en selecteer desgewenst Ingeschakeld in **organisaties.**</span><span class="sxs-lookup"><span data-stu-id="e393e-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="e393e-141">c.</span><span class="sxs-lookup"><span data-stu-id="e393e-141">c.</span></span> <span data-ttu-id="e393e-142">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="e393e-142">Select **Submit**.</span></span>

- <span data-ttu-id="e393e-143">LTI moet zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="e393e-143">Must have LTI configured</span></span>

- <span data-ttu-id="e393e-144">Blackboard Learn Ultra-Teams LTI-integratie toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="e393e-145">Hulpprogramma Microsoft Teams klassen LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="e393e-146">Het REST API-hulpprogramma en het delen van resources over verschillende origins toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="e393e-147">Integratie van klassen configureren Microsoft Teams goedkeuren</span><span class="sxs-lookup"><span data-stu-id="e393e-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="e393e-148">Het hulpmiddel Blackboard Learn Ultra Teams Classes LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="e393e-149">Selecteer in **het beheerderspaneel** de optie **LTI Tool Providers**.</span><span class="sxs-lookup"><span data-stu-id="e393e-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="e393e-150">Selecteer **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="e393e-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="e393e-151">Typ of **kopieer en** plak deze id in het veld Client-id:</span><span class="sxs-lookup"><span data-stu-id="e393e-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="e393e-152">Bekijk alle instellingen die vooraf zijn ingevuld en in **De status** van het hulpprogramma en selecteer **vervolgens Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="e393e-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="e393e-153">Selecteer **in Instellingsbeleid** de optie **Rol in Cursus, Naam** en **E-mailadres** en selecteer **vervolgens Ja** voor beide.</span><span class="sxs-lookup"><span data-stu-id="e393e-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="e393e-154">Selecteer **Cijferservicetoegang toestaan en** **Lidmaatschapsservicetoegang toestaan.**</span><span class="sxs-lookup"><span data-stu-id="e393e-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="e393e-155">Het hulpmiddel Microsoft Teams klassen LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="e393e-156">Selecteer in **het beheerderspaneel** de optie **LTI Tool Providers**.</span><span class="sxs-lookup"><span data-stu-id="e393e-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="e393e-157">Selecteer **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="e393e-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="e393e-158">Typ of **kopieer en** plak deze id in het veld Client-id:</span><span class="sxs-lookup"><span data-stu-id="e393e-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="e393e-159">Controleer alle instellingen die vooraf zijn ingevuld en in *De status van* het hulpprogramma en selecteer *Ingeschakeld.*</span><span class="sxs-lookup"><span data-stu-id="e393e-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="e393e-160">Selecteer **in Instellingsbeleid** de optie **Rol in cursus, naam** en **e-mailadres.**</span><span class="sxs-lookup"><span data-stu-id="e393e-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="e393e-161">Selecteer **Ja** voor beide.</span><span class="sxs-lookup"><span data-stu-id="e393e-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="e393e-162">Selecteer **Cijferservicetoegang toestaan en** **Lidmaatschapsservicetoegang toestaan.**</span><span class="sxs-lookup"><span data-stu-id="e393e-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="e393e-163">Het HULPPROGRAMMA REST-API toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-163">Add the REST API tool</span></span>

1. <span data-ttu-id="e393e-164">Ga in **het beheerderspaneel** naar **Integraties** en selecteer **Rest API-integraties.**</span><span class="sxs-lookup"><span data-stu-id="e393e-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="e393e-165">Selecteer **Integratie maken.**</span><span class="sxs-lookup"><span data-stu-id="e393e-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="e393e-166">Typ of kopieer **en** plak deze id in het veld Toepassing-id:</span><span class="sxs-lookup"><span data-stu-id="e393e-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="e393e-167">Typ een gebruiker voor deze integratie.</span><span class="sxs-lookup"><span data-stu-id="e393e-167">Type a user for this integration.</span></span>

   <span data-ttu-id="e393e-168">Deze gebruiker is degene met api-toegang voor thuisgebruik waaruit de toepassing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="e393e-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="e393e-169">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="e393e-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="e393e-170">Het delen van resources over verschillende origins toevoegen</span><span class="sxs-lookup"><span data-stu-id="e393e-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="e393e-171">Ga in **het deelvenster Beheerder** naar **Integraties** en selecteer \**Resource delen met meerdere origins.*</span><span class="sxs-lookup"><span data-stu-id="e393e-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="e393e-172">Selecteer **Configuratie maken.**</span><span class="sxs-lookup"><span data-stu-id="e393e-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="e393e-173">In het **veld Origin** kopieert en plakt u deze URL:</span><span class="sxs-lookup"><span data-stu-id="e393e-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="e393e-174">Typ **autorisatie** in het veld Toegestane **kopteksten.**</span><span class="sxs-lookup"><span data-stu-id="e393e-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="e393e-175">Beschikbaar **instellen** op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="e393e-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="e393e-176">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="e393e-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="e393e-177">Integratie van klassen configureren Microsoft Teams goedkeuren</span><span class="sxs-lookup"><span data-stu-id="e393e-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="e393e-178">Als u uw Blackboard Learn Ultra-exemplaar wilt integreren met Microsoft Teams klassen, moet u ervoor zorgen dat de Blackboard Learn Ultra-toepassing is goedgekeurd voor toegang binnen uw Microsoft Azure tenant.</span><span class="sxs-lookup"><span data-stu-id="e393e-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="e393e-179">Dit is een proces dat moet worden voltooid door de globale beheerder van Microsoft 365 instelling.</span><span class="sxs-lookup"><span data-stu-id="e393e-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="e393e-180">Dit proces kan worden uitgevoerd vóór of nadat u de LTI-toepassingen in uw Blackboard Learn Ultra Instance hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="e393e-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="e393e-181">Voordat u de LTI-toepassingen configureert</span><span class="sxs-lookup"><span data-stu-id="e393e-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="e393e-182">Als u ervoor kiest om de app Blackboard Learn Ultra Teams Classes Azure goed te keuren voordat u de LTI-integraties configureert, moet u omleiden naar het **Microsoft Identity Platform Admin Consent Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="e393e-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="e393e-183">De URL wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="e393e-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="e393e-184">U vervangt **{Tenant} door** uw specifieke Microsoft Azure tenant-id.</span><span class="sxs-lookup"><span data-stu-id="e393e-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="e393e-185">Na het configureren van de LTI-toepassingen</span><span class="sxs-lookup"><span data-stu-id="e393e-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="e393e-186">Ga in **het beheerderspaneel** naar **Hulpprogramma's** en selecteer **Microsoft Teams Integratiebeheerder.**</span><span class="sxs-lookup"><span data-stu-id="e393e-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="e393e-187">Selecteer **Inschakelen Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="e393e-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="e393e-188">Voeg uw **Microsoft Tenant-id toe** aan het beschikbare tekstveld.</span><span class="sxs-lookup"><span data-stu-id="e393e-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="e393e-189">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="e393e-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="e393e-190">Als de app vooraf toestemming heeft gegeven, wordt er een klein vinkje gegeven.</span><span class="sxs-lookup"><span data-stu-id="e393e-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="e393e-191">Als het vinkje wordt weergegeven, selecteert u **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="e393e-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="e393e-192">Als toestemming nog niet is goedgekeurd, volgt u de stappen die worden beschreven om de URL voor toestemming te genereren en deze ter goedkeuring naar de Microsoft 365 globale beheerder te verzenden.</span><span class="sxs-lookup"><span data-stu-id="e393e-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="e393e-193">Nadat u de goedkeuring hebt bevestigd, **selecteert** u Opnieuw proberen om te bevestigen en selecteert u **Vervolgens Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="e393e-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
