---
title: Gebruik Microsoft Teams met Blackboard Learn Ultra
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
description: Gebruik Microsoft Teams met Blackboard Learn Ultra
ms.openlocfilehash: a97d5bf56e1e045ccb0ef7cc66ecef7dfba4041a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454627"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="36a03-103">Gebruik Microsoft Teams met Blackboard Learn Ultra</span><span class="sxs-lookup"><span data-stu-id="36a03-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="36a03-104">Teamwerk staat centraal in elke moderne organisatie.</span><span class="sxs-lookup"><span data-stu-id="36a03-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="36a03-105">Door samenwerking te bevorderen, is het een bepalend kenmerk van elke succesvolle instelling.</span><span class="sxs-lookup"><span data-stu-id="36a03-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="36a03-106">U kunt alle mogelijkheden en functies van Blackboard Learn Ultra verbeteren door ze te koppelen aan Microsoft Teams klassen.</span><span class="sxs-lookup"><span data-stu-id="36a03-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="36a03-107">Uw lessen kunnen realtime gesprekken, videovergaderingen of asynchrone interacties bevatten.</span><span class="sxs-lookup"><span data-stu-id="36a03-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="36a03-108">U kunt bestanden delen en cocreatie-ervaringen toevoegen voor uw leerlingen/studenten, allemaal op één plek.</span><span class="sxs-lookup"><span data-stu-id="36a03-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="36a03-109">Microsoft Teams met Learn Ultra de dynamiek van het onderwijs opnieuw definiëren en wat effectief leren betekent.</span><span class="sxs-lookup"><span data-stu-id="36a03-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="36a03-110">Zorg ervoor dat u het veld Instellingse-e-mail hebt ingesteld in uw [SIS (Student Information System)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span><span class="sxs-lookup"><span data-stu-id="36a03-110">Ensure that you have successfully set up the Institution Email field in your [Student Information System (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span></span>
>
><span data-ttu-id="36a03-111">De Microsoft Teams klassenintegratie is afhankelijk van het e-mailveld van de instelling in uw SIS om de juiste Microsoft Azure Active Directory's (AAD) [User Principle Name (UPN) toe te vertrouwen.](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)</span><span class="sxs-lookup"><span data-stu-id="36a03-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) [User Principle Name (UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span></span> <span data-ttu-id="36a03-112">Als er geen e-mail van een instelling is ingericht, wordt dit standaard ingesteld op de bestaande e-mail.</span><span class="sxs-lookup"><span data-stu-id="36a03-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="36a03-113">Het wordt aanbevolen om dit veld in te stellen voor elke gebruiker om ervoor te zorgen dat hun gegevens correct worden gesynchroniseerd en dat er geen conflict is tussen e-mailgegevens tussen AAD en Blackboard Learn Ultra.</span><span class="sxs-lookup"><span data-stu-id="36a03-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="36a03-114">Als u dit veld niet op de juiste manier hebt ingesteld in de SIS-toewijzing, blijft de integratie werken, maar worden gebruikers mogelijk niet weergegeven in de Teams-klassen die zijn gemaakt en kunnen er fouten optreden.</span><span class="sxs-lookup"><span data-stu-id="36a03-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="36a03-115">Ondersteuning voor het toewijzen van institutionele gegevens – SIS-veld instellings-e-mail</span><span class="sxs-lookup"><span data-stu-id="36a03-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="36a03-116">Als onderdeel van de ontwikkeling met integraties van cloudproviders heeft Blackboard Learn Ultra een nieuw veld Voor e-mail van instellingen gemaakt, zowel in de integratie van studentinformatiesysteemkader als openbare REST-API's, zodat instellingen het proces voor gegevenssynchronisatie effectief kunnen beheren tussen Blackboard Learn Ultra en AAD. </span><span class="sxs-lookup"><span data-stu-id="36a03-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="36a03-117">Wat betekent de e-mail van de instelling en wat wordt er ondersteund?</span><span class="sxs-lookup"><span data-stu-id="36a03-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="36a03-118">In het veld Instellings-e-mail kunnen aangepaste veldtoewijzingen worden gemaakt tussen de extern ondersteunde gegevensbronnen van een client en Blackboard Learn Ultra. </span><span class="sxs-lookup"><span data-stu-id="36a03-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="36a03-119">Als gegevensbronnen cloudproviders zijn, zoals Microsoft, is de UPN (User Principle Name) een primaire unieke id voor elke gebruiker die bestaat uit een UPN-voorvoegsel (de accountnaam van de gebruiker) en een UPN-achtervoegsel (een DNS-domeinnaam) die is samengevoegd met een @-symbool.</span><span class="sxs-lookup"><span data-stu-id="36a03-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="36a03-120">Hiermee wordt een uniek e-mailadres gemaakt voor elke specifieke gebruiker binnen de Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="36a03-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="36a03-121">Om ervoor te zorgen dat gegevens nauwkeurig zijn en registraties of lidmaatschappen tussen Blackboard Learn Ultra en Microsoft Teams-klassen correct worden bereikt, moet het e-mailadres van een gebruiker overeenkomen tussen beide systemen.</span><span class="sxs-lookup"><span data-stu-id="36a03-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="36a03-122">In Blackboard Learn Ultra kunnen gebruikers hun bestaande e-mailadres wijzigen of overschrijven in de gebruikersinterface, wat kan leiden tot synchronisatiefouten en dat de gebruiker niet correct wordt toegevoegd aan een klasteam.</span><span class="sxs-lookup"><span data-stu-id="36a03-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="36a03-123">Met **de toewijzing** van het veld Institution Email zorgt u ervoor dat dit beveiligings- en validatiecontroleniveau correct kan worden beheerd, ongeacht of gebruikers hun e-mail hebben gewijzigd in Blackboard Learn Ultra of niet.</span><span class="sxs-lookup"><span data-stu-id="36a03-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="36a03-124">Als er twee e-mailadressen verschillen, is dit het volgende:</span><span class="sxs-lookup"><span data-stu-id="36a03-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="36a03-125">Er moet een beslissing worden genomen over welke bron voorrang heeft en wordt zowel als de e-mails van de persoon als de e-mail van de instelling genomen.</span><span class="sxs-lookup"><span data-stu-id="36a03-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="36a03-126">Of</span><span class="sxs-lookup"><span data-stu-id="36a03-126">Or</span></span>
- <span data-ttu-id="36a03-127">Een instelling kan een aangepaste veldtoewijzing instellen in de instellings-e-mail, waarmee een mogelijk conflict kan worden opgelost.</span><span class="sxs-lookup"><span data-stu-id="36a03-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="36a03-128">De **toewijzing van** het veld Institution Email is nu beschikbaar voor alle bestaande SIS-integratietypen op Advanced Configuration **Instellingen** Users Learn Object  >  **Type** Field  >  **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="36a03-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="36a03-129">Het is belangrijk om te weten dat instellings-e-mail standaard **is** ingesteld op e-mail van persoon voor alle SIS-indelingen en uniek moet zijn voor elke persoon. </span><span class="sxs-lookup"><span data-stu-id="36a03-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="36a03-130">Voor alle bestaande integraties die zijn ingesteld en uitgevoerd, is deze gegevenstoewijzing ingesteld, omdat sis gebruikers niet kan importeren als hun e-mail is gedupliceerd.</span><span class="sxs-lookup"><span data-stu-id="36a03-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="36a03-131">Als een instelling de mogelijkheid vereist om de instellings-e-mail te wijzigen **in** **aangepast,** moet de instelling dit beheren via de Instellingen geavanceerde configuratie in het SIS.</span><span class="sxs-lookup"><span data-stu-id="36a03-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="36a03-132">Vereisten</span><span class="sxs-lookup"><span data-stu-id="36a03-132">Requirements</span></span>

<span data-ttu-id="36a03-133">De Microsoft Teams klassenintegratie is alleen beschikbaar voor **cursussen voor Ultra Course View.**</span><span class="sxs-lookup"><span data-stu-id="36a03-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="36a03-134">Uw instelling moet aan deze vereisten voldoen om deze te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="36a03-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="36a03-135">Laat Blackboard Learn Ultra Learn SaaS met Ultra Base Navigation ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="36a03-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

  ![een voorbeeld van de functie is ingeschakeld in cursussen](media/feature-availability.png)

- <span data-ttu-id="36a03-137">LTI inschakelen voor gebruik in cursussen.</span><span class="sxs-lookup"><span data-stu-id="36a03-137">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="36a03-138">a.</span><span class="sxs-lookup"><span data-stu-id="36a03-138">a.</span></span> <span data-ttu-id="36a03-139">Ga naar de **LTI-hulpprogramma's** van  >  **het beheerderspaneel**  >  **Globale eigenschappen beheren.**</span><span class="sxs-lookup"><span data-stu-id="36a03-139">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="36a03-140">b.</span><span class="sxs-lookup"><span data-stu-id="36a03-140">b.</span></span> <span data-ttu-id="36a03-141">Selecteer **LTI ingeschakeld in cursussen** en selecteer desgewenst Ingeschakeld in **organisaties.**</span><span class="sxs-lookup"><span data-stu-id="36a03-141">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="36a03-142">c.</span><span class="sxs-lookup"><span data-stu-id="36a03-142">c.</span></span> <span data-ttu-id="36a03-143">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="36a03-143">Select **Submit**.</span></span>

- <span data-ttu-id="36a03-144">LTI moet zijn geconfigureerd</span><span class="sxs-lookup"><span data-stu-id="36a03-144">Must have LTI configured</span></span>

- <span data-ttu-id="36a03-145">Blackboard Learn Ultra-Teams LTI-integratie toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-145">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="36a03-146">Hulpprogramma Microsoft Teams klassen LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-146">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="36a03-147">Het REST API-hulpprogramma en het delen van resources over verschillende origins toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-147">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="36a03-148">Integratie van klassen configureren Microsoft Teams goedkeuren</span><span class="sxs-lookup"><span data-stu-id="36a03-148">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="36a03-149">Het hulpmiddel Blackboard Learn Ultra Teams Classes LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-149">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="36a03-150">Selecteer in **het beheerderspaneel** de optie **LTI Tool Providers**.</span><span class="sxs-lookup"><span data-stu-id="36a03-150">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="36a03-151">Selecteer **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="36a03-151">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="36a03-152">Typ of **kopieer en** plak deze id in het veld Client-id:</span><span class="sxs-lookup"><span data-stu-id="36a03-152">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="36a03-153">Bekijk alle instellingen die vooraf zijn ingevuld en in **De status** van het hulpprogramma en selecteer **vervolgens Ingeschakeld.**</span><span class="sxs-lookup"><span data-stu-id="36a03-153">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="36a03-154">Selecteer **in Instellingsbeleid** de optie **Rol in Cursus, Naam** en **E-mailadres** en selecteer **vervolgens Ja** voor beide.</span><span class="sxs-lookup"><span data-stu-id="36a03-154">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="36a03-155">Selecteer **Cijferservicetoegang toestaan en** **Lidmaatschapsservicetoegang toestaan.**</span><span class="sxs-lookup"><span data-stu-id="36a03-155">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="36a03-156">Het hulpmiddel Microsoft Teams klassen LTI 1.3 toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-156">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="36a03-157">Selecteer in **het beheerderspaneel** de optie **LTI Tool Providers**.</span><span class="sxs-lookup"><span data-stu-id="36a03-157">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="36a03-158">Selecteer **register LTI 1.3 Tool**.</span><span class="sxs-lookup"><span data-stu-id="36a03-158">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="36a03-159">Typ of **kopieer en** plak deze id in het veld Client-id:</span><span class="sxs-lookup"><span data-stu-id="36a03-159">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="36a03-160">Controleer alle instellingen die vooraf zijn ingevuld en in *De status van* het hulpprogramma en selecteer *Ingeschakeld.*</span><span class="sxs-lookup"><span data-stu-id="36a03-160">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="36a03-161">Selecteer **in Instellingsbeleid** de optie **Rol in cursus, naam** en **e-mailadres.**</span><span class="sxs-lookup"><span data-stu-id="36a03-161">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="36a03-162">Selecteer **Ja** voor beide.</span><span class="sxs-lookup"><span data-stu-id="36a03-162">Select **Yes** for both.</span></span>

6. <span data-ttu-id="36a03-163">Selecteer **Cijferservicetoegang toestaan en** **Lidmaatschapsservicetoegang toestaan.**</span><span class="sxs-lookup"><span data-stu-id="36a03-163">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="36a03-164">Het HULPPROGRAMMA REST-API toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-164">Add the REST API tool</span></span>

1. <span data-ttu-id="36a03-165">Ga in **het beheerderspaneel** naar **Integraties** en selecteer **Rest API-integraties.**</span><span class="sxs-lookup"><span data-stu-id="36a03-165">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="36a03-166">Selecteer **Integratie maken.**</span><span class="sxs-lookup"><span data-stu-id="36a03-166">Select **Create Integration**.</span></span>

3. <span data-ttu-id="36a03-167">Typ of kopieer **en** plak deze id in het veld Toepassing-id:</span><span class="sxs-lookup"><span data-stu-id="36a03-167">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="36a03-168">Typ een gebruiker voor deze integratie.</span><span class="sxs-lookup"><span data-stu-id="36a03-168">Type a user for this integration.</span></span>

   <span data-ttu-id="36a03-169">Deze gebruiker is degene met api-toegang voor thuisgebruik waaruit de toepassing is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="36a03-169">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="36a03-170">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="36a03-170">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="36a03-171">Het delen van resources over verschillende origins toevoegen</span><span class="sxs-lookup"><span data-stu-id="36a03-171">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="36a03-172">Ga in **het deelvenster Beheerder** naar **Integraties** en selecteer \**Resource delen met meerdere origins.*</span><span class="sxs-lookup"><span data-stu-id="36a03-172">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="36a03-173">Selecteer **Configuratie maken.**</span><span class="sxs-lookup"><span data-stu-id="36a03-173">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="36a03-174">In het **veld Origin** kopieert en plakt u deze URL:</span><span class="sxs-lookup"><span data-stu-id="36a03-174">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="36a03-175">Typ **autorisatie** in het veld Toegestane **kopteksten.**</span><span class="sxs-lookup"><span data-stu-id="36a03-175">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="36a03-176">Beschikbaar **instellen** op **Ja**.</span><span class="sxs-lookup"><span data-stu-id="36a03-176">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="36a03-177">Selecteer **Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="36a03-177">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="36a03-178">Integratie van klassen configureren Microsoft Teams goedkeuren</span><span class="sxs-lookup"><span data-stu-id="36a03-178">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="36a03-179">Als u uw Blackboard Learn Ultra-exemplaar wilt integreren met Microsoft Teams klassen, moet u ervoor zorgen dat de Blackboard Learn Ultra-toepassing is goedgekeurd voor toegang binnen uw Microsoft Azure tenant.</span><span class="sxs-lookup"><span data-stu-id="36a03-179">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="36a03-180">Dit is een proces dat moet worden voltooid door de globale beheerder van Microsoft 365 instelling.</span><span class="sxs-lookup"><span data-stu-id="36a03-180">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="36a03-181">Dit proces kan worden uitgevoerd vóór of nadat u de LTI-toepassingen in uw Blackboard Learn Ultra Instance hebt geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="36a03-181">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="36a03-182">Voordat u de LTI-toepassingen configureert</span><span class="sxs-lookup"><span data-stu-id="36a03-182">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="36a03-183">Als u ervoor kiest om de app Blackboard Learn Ultra Teams Classes Azure goed te keuren voordat u de LTI-integraties configureert, moet u omleiden naar het **Microsoft Identity Platform Admin Consent Endpoint**.</span><span class="sxs-lookup"><span data-stu-id="36a03-183">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="36a03-184">De URL wordt weergegeven:</span><span class="sxs-lookup"><span data-stu-id="36a03-184">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="36a03-185">U vervangt **{Tenant} door** uw specifieke Microsoft Azure tenant-id.</span><span class="sxs-lookup"><span data-stu-id="36a03-185">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

<span data-ttu-id="36a03-186">U ziet een machtigingenvenster waarin wordt uitgelegd dat u toestemming geeft voor Blackboard Learn Ultra om toegang te krijgen tot Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36a03-186">You'll see a permissions window that explains you're giving permission to Blackboard Learn Ultra to access Microsoft Teams.</span></span>

![het machtigingsvenster voor Microsoft en Blackboard](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="36a03-188">Na het configureren van de LTI-toepassingen</span><span class="sxs-lookup"><span data-stu-id="36a03-188">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="36a03-189">Ga in **het beheerderspaneel** naar **Hulpprogramma's** en selecteer **Microsoft Teams Integratiebeheerder.**</span><span class="sxs-lookup"><span data-stu-id="36a03-189">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="36a03-190">Selecteer **Inschakelen Microsoft Teams.**</span><span class="sxs-lookup"><span data-stu-id="36a03-190">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="36a03-191">Voeg uw **Microsoft Tenant-id toe** aan het beschikbare tekstveld.</span><span class="sxs-lookup"><span data-stu-id="36a03-191">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="36a03-192">Kies een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="36a03-192">Choose one of the following options:</span></span>

   - <span data-ttu-id="36a03-193">Als de app vooraf toestemming heeft gegeven, wordt er een klein vinkje gegeven.</span><span class="sxs-lookup"><span data-stu-id="36a03-193">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="36a03-194">Als het vinkje wordt weergegeven, selecteert u **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="36a03-194">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="36a03-195">Als toestemming nog niet is goedgekeurd, volgt u de stappen die worden beschreven om de URL voor toestemming te genereren en deze ter goedkeuring naar de Microsoft 365 globale beheerder te verzenden.</span><span class="sxs-lookup"><span data-stu-id="36a03-195">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="36a03-196">Nadat u de goedkeuring hebt bevestigd, **selecteert** u Opnieuw proberen om te bevestigen en selecteert u **Vervolgens Verzenden**.</span><span class="sxs-lookup"><span data-stu-id="36a03-196">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>

   ![Een dialoogvenster dat aangeeft dat uw toegang is geblokkeerd](media/blocked-access.png)