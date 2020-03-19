---
title: Tickets maken en volgen via ServiceNow
description: Microsoft 365 security center wordt verbeterd met de mogelijkheid om native te maken en te volgen tickets in ServiceNow. Beveiligingsbeheerders kunnen een aanbeveling voor een beveiligde score rechtstreeks naar ServiceNow verzenden en een ticket maken.
keywords: beveiliging, Microsoft 365, M365, beveiligde score, beveiligingscentrum, ServiceNow, tickets, taken
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 904c1a019c55cabce6856a7caaca73d08d6db3f7
ms.sourcegitcommit: 841c06a5d566d404c35d5e9c0c7de5088daab976
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42836878"
---
# <a name="manage-tickets-through-servicenow"></a><span data-ttu-id="55905-105">Tickets beheren via ServiceNow</span><span class="sxs-lookup"><span data-stu-id="55905-105">Manage tickets through ServiceNow</span></span>

<span data-ttu-id="55905-106">Microsoft 365 security center wordt verbeterd met de mogelijkheid om native te maken en te volgen tickets in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-106">Microsoft 365 security center is being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span> <span data-ttu-id="55905-107">Beveiligingsbeheerders kunnen een [verbeteringsactie voor Microsoft Secure Score](microsoft-secure-score.md) rechtstreeks naar ServiceNow verzenden en een ticket maken.</span><span class="sxs-lookup"><span data-stu-id="55905-107">Security administrators can send a [Microsoft Secure Score](microsoft-secure-score.md) improvement action directly to ServiceNow and create a ticket.</span></span> <span data-ttu-id="55905-108">Zowel incident management en change management tickets kunnen worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="55905-108">Both incident management and change management tickets can be created.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55905-109">Vereisten</span><span class="sxs-lookup"><span data-stu-id="55905-109">Prerequisites</span></span>

<span data-ttu-id="55905-110">Toegang hebben tot het Microsoft 365-beveiligingscentrum en een Instantie ServiceNow met:</span><span class="sxs-lookup"><span data-stu-id="55905-110">Have access to the Microsoft 365 security center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="55905-111">Kingston of hogere versie</span><span class="sxs-lookup"><span data-stu-id="55905-111">Kingston or higher version</span></span>
* <span data-ttu-id="55905-112">Hi-referenties voor beheerders hebben</span><span class="sxs-lookup"><span data-stu-id="55905-112">Have admin HI credentials</span></span>
* <span data-ttu-id="55905-113">Beheerdersrechten hebben voor uw doelleverancier</span><span class="sxs-lookup"><span data-stu-id="55905-113">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="55905-114">ServiceNow raadt gebruikers aan de standaardinstellingen in uw ServiceNow-exemplaar te behouden.</span><span class="sxs-lookup"><span data-stu-id="55905-114">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="55905-115">Het hebben van aanpassingen kan fouten veroorzaken bij het invullen van de installatiechecklist en integratie met het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="55905-115">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="55905-116">Gegevensuitwisseling</span><span class="sxs-lookup"><span data-stu-id="55905-116">Data exchange</span></span>

<span data-ttu-id="55905-117">Wanneer u het Microsoft 365-beveiligingscentrum aansluit op ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:</span><span class="sxs-lookup"><span data-stu-id="55905-117">When you connect the Microsoft 365 security center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="55905-118">Naam van instantie ServiceNow</span><span class="sxs-lookup"><span data-stu-id="55905-118">ServiceNow instance name</span></span>
* <span data-ttu-id="55905-119">ServiceNow-client-id</span><span class="sxs-lookup"><span data-stu-id="55905-119">ServiceNow client ID</span></span>
* <span data-ttu-id="55905-120">ServiceNow klant geheim</span><span class="sxs-lookup"><span data-stu-id="55905-120">ServiceNow client secret</span></span>
* <span data-ttu-id="55905-121">ServiceNow toegang tot & tokens vernieuwen</span><span class="sxs-lookup"><span data-stu-id="55905-121">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="55905-122">Wanneer u een ServiceNow-ticket maakt vanuit het Microsoft 365-beveiligingscentrum, worden de volgende gegevens naar ServiceNow verzonden:</span><span class="sxs-lookup"><span data-stu-id="55905-122">When you create a ServiceNow ticket from the Microsoft 365 security center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="55905-123">Gebruikersnaam waarmee de het maken van het ticket wordt geïnitieerd</span><span class="sxs-lookup"><span data-stu-id="55905-123">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="55905-124">Taaknaam</span><span class="sxs-lookup"><span data-stu-id="55905-124">Task name</span></span>
* <span data-ttu-id="55905-125">Taakbeschrijving</span><span class="sxs-lookup"><span data-stu-id="55905-125">Task description</span></span>
* <span data-ttu-id="55905-126">Priority</span><span class="sxs-lookup"><span data-stu-id="55905-126">Priority</span></span>
* <span data-ttu-id="55905-127">Vervaldatum</span><span class="sxs-lookup"><span data-stu-id="55905-127">Due date</span></span>
* <span data-ttu-id="55905-128">Aanbevelingsbron (aanbeveling van de gebruiker of aanbeveling van Microsoft)</span><span class="sxs-lookup"><span data-stu-id="55905-128">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="55905-129">Aanbevelingscategorie (apparaten, gegevens, apps, identiteit, infrastructuur)</span><span class="sxs-lookup"><span data-stu-id="55905-129">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-microsoft-365-security-center-to-servicenow"></a><span data-ttu-id="55905-130">Microsoft 365-beveiligingscentrum verbinden met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="55905-130">Connect Microsoft 365 security center to ServiceNow</span></span>

<span data-ttu-id="55905-131">Navigeer naar de startpagina van het Microsoft 365-beveiligingscentrum om de ServiceNow-verbindingskaart te bekijken.</span><span class="sxs-lookup"><span data-stu-id="55905-131">Navigate to the Microsoft 365 security center home page to see the ServiceNow connection card.</span></span>

![Gebruikt u ServiceNow](../../media/do-you-use-servicenow-250.png)

<span data-ttu-id="55905-133">Selecteer 'Verbinding maken met ServiceNow' om naar de installatiepagina servicenow te gaan.</span><span class="sxs-lookup"><span data-stu-id="55905-133">Select "Connect to ServiceNow" to go to the ServiceNow setup page.</span></span> <span data-ttu-id="55905-134">Volg de instructies om de Microsoft 365 Connector-app te autoriseren.</span><span class="sxs-lookup"><span data-stu-id="55905-134">Follow the instructions to authorize the Microsoft 365 Connector app.</span></span>

> [!NOTE]
> <span data-ttu-id="55905-135">Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u ervoor zorgen dat u de inlog- en wachtwoord van de integratiegebruiker gebruikt die u in de installatiestappen hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="55905-135">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="55905-136">Gebruik uw persoonlijke referenties niet.</span><span class="sxs-lookup"><span data-stu-id="55905-136">Do not use your personal credentials.</span></span>

<span data-ttu-id="55905-137">Nadat u de aanwijzingen hebt gevolgd en de verbinding hebt autoriseren, bekijkt u de verbindingsstatus op zowel de verbindingspagina van het Microsoft 365-beveiligingscentrum als op de ervaring van de ServiceNow Microsoft 365 Ticketing Connector-app.</span><span class="sxs-lookup"><span data-stu-id="55905-137">After you have followed the directions and authorizing the connection, view the connection status on both the Microsoft 365 security center connection page and in the ServiceNow Microsoft 365 Ticketing Connector App experience.</span></span> <span data-ttu-id="55905-138">Nu bent u helemaal klaar om te beginnen met het maken van taken!</span><span class="sxs-lookup"><span data-stu-id="55905-138">Now you are all set to start creating tasks!</span></span>

## <a name="create-a-task-and-share-it-to-servicenow"></a><span data-ttu-id="55905-139">Een taak maken en delen met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="55905-139">Create a task and share it to ServiceNow</span></span>

<span data-ttu-id="55905-140">Zodra de integratie is ingesteld, maakt u ServiceNow-taken op basis van specifieke verbeteringen van Microsoft Secure Score.</span><span class="sxs-lookup"><span data-stu-id="55905-140">Once the integration is set up, create ServiceNow tasks based on specific Microsoft Secure Score improvement actions.</span></span> <span data-ttu-id="55905-141">Ga naar een verbeteringsactie in Secure Score in de Microsoft 365 security center portal en selecteer het pictogram 'Delen'.</span><span class="sxs-lookup"><span data-stu-id="55905-141">Go to any improvement action in Secure Score in the Microsoft 365 security center portal, and select the "share" icon.</span></span> <span data-ttu-id="55905-142">Een van de vervolgkeuzeopties is ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-142">One of the dropdown options is ServiceNow.</span></span>

![ServiceNow delen in Secure Score](../../media/servicenow-share.png)

<span data-ttu-id="55905-144">Er wordt een taak gegenereerd waar u de prioriteit instellen en de naam, beschrijving of vervaldatum bewerken.</span><span class="sxs-lookup"><span data-stu-id="55905-144">A task is generated where you can set the priority and edit the name, description, or due date.</span></span> <span data-ttu-id="55905-145">Zodra alle vereiste velden zijn ingevuld, stuurt u de taak naar ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-145">Once all the required fields are filled in, send the task to ServiceNow.</span></span>

<span data-ttu-id="55905-146">De taak is zichtbaar in ServiceNow als een Microsoft 365-aanvraag voor beveiligings- en configuratiewijziging.</span><span class="sxs-lookup"><span data-stu-id="55905-146">The task is visible in ServiceNow as a Microsoft 365 Security and Configuration Change Request.</span></span>

## <a name="track-tickets"></a><span data-ttu-id="55905-147">Tickets volgen</span><span class="sxs-lookup"><span data-stu-id="55905-147">Track tickets</span></span>

<span data-ttu-id="55905-148">Zodra servicenow-tickets voor wijzigingsbeheer en incidentbeheer zijn gemaakt, worden ze weergegeven op kaarten op de startpagina van het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="55905-148">Once ServiceNow change management and incident management tickets have been created, they are displayed on cards in the Microsoft 365 security center home page.</span></span> <span data-ttu-id="55905-149">Vanaf deze kaarten u een ticket maken, alle tickets bekijken of de ServiceNow-configuratie beheren.</span><span class="sxs-lookup"><span data-stu-id="55905-149">From these cards, you can create a ticket, view all tickets, or manage the ServiceNow configuration.</span></span>

![ServiceNow verander managementtickets](../../media/change-management-375.png)  ![ServiceNow incident management tickets](../../media/incident-management-375.png)

<span data-ttu-id="55905-152">Als u uw ServiceNow-integratie opnieuw wilt inrichten of beheren in het Microsoft 365-beveiligingscentrum, selecteert u **ServiceNow-configuratie beheren** op een van de kaarten.</span><span class="sxs-lookup"><span data-stu-id="55905-152">To re-provision or manage your ServiceNow integration in the Microsoft 365 security center, select **Manage ServiceNow configuration** on either of the cards.</span></span> <span data-ttu-id="55905-153">Verwijder van daaruit de huidige ServiceNow-verbinding en pas de namen van de ticketstatus aan.</span><span class="sxs-lookup"><span data-stu-id="55905-153">From there, remove the current ServiceNow connection and customize ticket state names.</span></span>

<span data-ttu-id="55905-154">Met ServiceNow-tickets zichtbaar in het Microsoft 365-beveiligingscentrum, leven uw taken op een plaats waar ze kunnen worden gevolgd en uitgevoerd naast uw andere beveiligingsdashboarditems.</span><span class="sxs-lookup"><span data-stu-id="55905-154">With ServiceNow tickets visible in the Microsoft 365 security center, your tasks live in a place where they can be tracked and acted upon alongside your other security dashboard items.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="55905-155">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="55905-155">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="55905-156">U ontvangt een foutmelding in de eerste stap van de installatiechecklist (OAuth-creatie)</span><span class="sxs-lookup"><span data-stu-id="55905-156">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="55905-157">**Foutbericht**: Bewerking tegen 'oauth_entity' van scope 'x_mioms_m365ticket' is geweigerd vanwege het toegangsbeleid voor de randvan de lijst</span><span class="sxs-lookup"><span data-stu-id="55905-157">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="55905-158">De app gaat ervan uit dat elke beheerder op het Instantie ServiceNow OAuth-entiteiten kan maken en lezen.</span><span class="sxs-lookup"><span data-stu-id="55905-158">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="55905-159">Deze fout kan worden veroorzaakt door een aanpassing op uw exemplaar van ServiceNow, die beperkt wie OAuth-entiteiten kan maken/lezen.</span><span class="sxs-lookup"><span data-stu-id="55905-159">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="55905-160">**ServiceNow raadt gebruikers aan de standaardfunctionaliteit te behouden.**</span><span class="sxs-lookup"><span data-stu-id="55905-160">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="55905-161">Stel de tabelconfiguraties van de tabel 'toepassingsregisters' in op standaard:</span><span class="sxs-lookup"><span data-stu-id="55905-161">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="55905-162">Label = Aanvraagregistereren</span><span class="sxs-lookup"><span data-stu-id="55905-162">Label = Application Registeries</span></span>
* <span data-ttu-id="55905-163">Naam = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="55905-163">Name = oauth_entity</span></span>
* <span data-ttu-id="55905-164">Toegankelijk vanaf = Alle toepassingsscopes</span><span class="sxs-lookup"><span data-stu-id="55905-164">Accessible from = All application scopes</span></span>
* <span data-ttu-id="55905-165">Kan lezen = selectievakje ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="55905-165">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="55905-166">De OAuth-entiteit valideren die is gemaakt voor Microsoft 365 Security & Compliance-connector</span><span class="sxs-lookup"><span data-stu-id="55905-166">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="55905-167">Ga naar de tabel met toepassingsregisters **(Menu > System OAuth > Application Registry)** in ServiceNow en zoek de OAuth-entiteit die door u is gemaakt, met de naam die u hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="55905-167">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="55905-168">Inloggen als integratiegebruiker</span><span class="sxs-lookup"><span data-stu-id="55905-168">Logging in as the integration user</span></span>

<span data-ttu-id="55905-169">Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u ervoor zorgen dat u de inlog- en wachtwoord van de integratiegebruiker gebruikt die u in de installatiestappen hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="55905-169">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="55905-170">Gebruik uw persoonlijke referenties niet.</span><span class="sxs-lookup"><span data-stu-id="55905-170">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="55905-171">Ga naar de autorisatiepagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-171">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="55905-172">Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **Niet u** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="55905-172">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="55905-173">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt op basis van de checklist voor installatie.</span><span class="sxs-lookup"><span data-stu-id="55905-173">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="55905-174">Selecteer **Toestaan** op de pagina ServiceNow met de vraag of de Beveiligings - + complianceconnector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="55905-174">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="55905-175">Ga verder met de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="55905-175">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="55905-176">De integratiegebruiker valideren die is gemaakt met de installatiechecklist voor Microsoft 365 Security & Compliance-connector</span><span class="sxs-lookup"><span data-stu-id="55905-176">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="55905-177">Ga naar gebruikerstabel **(Menu > gebruikersbeheer > gebruikers)** in ServiceNow en zoek de integratiegebruiker die door u is gemaakt, met de naam die u hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="55905-177">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="55905-178">Uw bedrijf heeft eenmalige aanmelding ingeschakeld, waardoor u geen verbinding maken met ServiceNow via het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="55905-178">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="55905-179">Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een fout ontvangt of als het inloggen mislukt, volgt u een van de twee oplossingen.</span><span class="sxs-lookup"><span data-stu-id="55905-179">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="55905-180">Log in bij ServiceNow als integratiegebruiker</span><span class="sxs-lookup"><span data-stu-id="55905-180">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="55905-181">Navigeer terug naar de autorisatiepagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-181">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="55905-182">Selecteer de koppeling **Niet-u** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="55905-182">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="55905-183">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt op basis van de checklist voor installatie.</span><span class="sxs-lookup"><span data-stu-id="55905-183">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="55905-184">Selecteer **Toestaan** op de pagina ServiceNow met de vraag of de Beveiligings - + complianceconnector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="55905-184">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="55905-185">Ga verder met de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="55905-185">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="55905-186">Een gebruiker van beveiligingsbeheerders maken</span><span class="sxs-lookup"><span data-stu-id="55905-186">Create a security admin user</span></span>

1. <span data-ttu-id="55905-187">Maak een gebruiker met beheerdersbevoegdheden voor beveiligingsbeheer in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="55905-187">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="55905-188">De gebruiker moet dezelfde naam en e-mailadres hebben als de integratiegebruiker die u hebt gemaakt met de checklist voor installatie.</span><span class="sxs-lookup"><span data-stu-id="55905-188">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="55905-189">U de beveiligingsbeheerrol verwijderen nadat de aanmelding en verbinding is voltooid.</span><span class="sxs-lookup"><span data-stu-id="55905-189">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="55905-190">Meld u als gebruiker aan bij het Microsoft 365-beveiligingscentrum en volg de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="55905-190">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="55905-191">IP-filtering</span><span class="sxs-lookup"><span data-stu-id="55905-191">IP filtering</span></span>

<span data-ttu-id="55905-192">Als u IP-filtering hebt ingeschakeld, moet u mogelijk expliciet IP-adressen toestaan.</span><span class="sxs-lookup"><span data-stu-id="55905-192">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="55905-193">Zie [IP-adrestoegangsbeheer](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="55905-193">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="55905-194">Zie [Azure IP-bereiken en servicetags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) voor een lijst met IP-adressen die u toestaan.</span><span class="sxs-lookup"><span data-stu-id="55905-194">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="55905-195">Installatie is voltooid, maar zie geen tickets en kan niet delen</span><span class="sxs-lookup"><span data-stu-id="55905-195">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="55905-196">Als de installatie- en installatiestappen zijn voltooid, maar u de ServiceNow-kaarten niet op de startpagina ziet en niet delen https://security.microsoft.com/ticketProvisioningmet ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtingspagina op.</span><span class="sxs-lookup"><span data-stu-id="55905-196">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="55905-197">Selecteer **Autoriseren** en terugnaar de startpagina.</span><span class="sxs-lookup"><span data-stu-id="55905-197">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="55905-198">De kaarten moeten verschijnen.</span><span class="sxs-lookup"><span data-stu-id="55905-198">The cards should appear.</span></span>

