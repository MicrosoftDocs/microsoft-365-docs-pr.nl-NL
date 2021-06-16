---
title: Uw portal starten met de planning voor het starten van portals
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In dit artikel wordt beschreven hoe u uw portal kunt starten met de planning voor het starten van portals
ms.openlocfilehash: fb092ea2500aaa139a34e511d224ec4419e04cb5
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930257"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a><span data-ttu-id="b0ab3-103">Uw portal starten met de SharePoint portal launch scheduler</span><span class="sxs-lookup"><span data-stu-id="b0ab3-103">Launch your portal using the SharePoint Portal launch scheduler</span></span>

<span data-ttu-id="b0ab3-104">Een portal is een SharePoint communicatiesite op uw intranet die veel verkeer heeft: een site die in de loop van enkele weken tussen de 10.000 en meer dan 100.000 kijkers heeft.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-104">A portal is a SharePoint communication site on your intranet that is high-traffic – a site that has anywhere from 10,000 to over 100,000 viewers over the course of several weeks.</span></span> <span data-ttu-id="b0ab3-105">Gebruik de planning voor het starten van portals om uw portal te starten om ervoor te zorgen dat gebruikers een soepele weergaveervaring hebben bij het openen van uw nieuwe portal SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-105">Use the Portal launch scheduler to launch your portal to ensure users have a smooth viewing experience when accessing your new SharePoint portal.</span></span>
<br>
<br>
<span data-ttu-id="b0ab3-106">De planning voor het starten van portals is ontworpen om u te helpen een gefaseerd implementatieaanpak te volgen door gebruikers in golven te batchen en de URL-omleiding voor de nieuwe portal te beheren.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-106">The Portal launch scheduler is designed to help you follow a phased roll-out approach by batching viewers in waves and managing the URL redirects for the new portal.</span></span> <span data-ttu-id="b0ab3-107">Tijdens de lancering van elke golf kunt u feedback van gebruikers verzamelen, de prestaties van de portal controleren en de start onderbreken om problemen op te lossen voordat u verdergaat met de volgende golf.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-107">During the launch of each wave, you can gather user feedback, monitor portal performance, and pause the launch to resolve issues before proceeding with the next wave.</span></span> <span data-ttu-id="b0ab3-108">Meer informatie over het [plannen van een portallancering in SharePoint.](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="b0ab3-108">Learn more about how to [plan a portal launch in SharePoint](/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span>

<span data-ttu-id="b0ab3-109">**Er zijn twee soorten omleiding:**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-109">**There are two types of redirections:**</span></span>

- <span data-ttu-id="b0ab3-110">**Bidirectioneel:** een nieuwe moderne portal SharePoint om een bestaande SharePoint of moderne portal te vervangen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-110">**Bidirectional**: launch a new modern SharePoint portal to replace an existing SharePoint classic or modern portal</span></span>
- <span data-ttu-id="b0ab3-111">**Omleiden naar een tijdelijke pagina:** start een nieuwe moderne SharePoint portal zonder bestaande SharePoint portal</span><span class="sxs-lookup"><span data-stu-id="b0ab3-111">**Redirect to a temporary page**: launch a new modern SharePoint portal with no existing SharePoint portal</span></span>

<span data-ttu-id="b0ab3-112">Sitemachtigingen moeten afzonderlijk van golven zijn ingesteld als onderdeel van de start.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-112">Site permissions must be set up separately from waves as part of the launch.</span></span> <span data-ttu-id="b0ab3-113">Als u bijvoorbeeld een portal voor de hele organisatie uitwijst, kunt u machtigingen instellen voor 'Iedereen behalve externe gebruikers'. Scheid vervolgens uw gebruikers in golven met behulp van beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-113">For example, if you are releasing an organization-wide portal, you can set permissions to “Everyone except external users,” then separate your users into waves using security groups.</span></span> <span data-ttu-id="b0ab3-114">Als u een beveiligingsgroep toevoegt aan een golf, krijgt die beveiligingsgroep geen toegang tot de site.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-114">Adding a security group to a wave does not give that security group access to the site.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="b0ab3-115">Deze functie is toegankelijk via het **Instellingen-paneel** op de startpagina van SharePoint-communicatiesites voor klanten met gerichte release vanaf mei 2021 en is beschikbaar voor alle klanten in juli 2021</span><span class="sxs-lookup"><span data-stu-id="b0ab3-115">This feature will be accessible from the **Settings** panel on the home page of SharePoint communication sites for Targeted release customers starting in May 2021 and will become available to all customers by July 2021</span></span>
> - <span data-ttu-id="b0ab3-116">De PowerShell-versie van dit hulpprogramma is vandaag beschikbaar</span><span class="sxs-lookup"><span data-stu-id="b0ab3-116">The PowerShell version of this tool is available today</span></span>
> - <span data-ttu-id="b0ab3-117">Deze functie kan alleen worden gebruikt op moderne SharePoint communicatiesites</span><span class="sxs-lookup"><span data-stu-id="b0ab3-117">This feature can only be used on modern SharePoint communication sites</span></span>
> - <span data-ttu-id="b0ab3-118">U moet de machtigingen van de site-eigenaar voor de site hebben om de start van een portal aan te passen en te plannen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-118">You must have site owner permissions for the site to customize and schedule the launch of a portal</span></span>
> - <span data-ttu-id="b0ab3-119">Lanceringen moeten ten minste zeven dagen van tevoren zijn gepland en elke golf kan één tot zeven dagen duren</span><span class="sxs-lookup"><span data-stu-id="b0ab3-119">Launches must be scheduled at least seven days in advance and each wave can last one to seven days</span></span>
> - <span data-ttu-id="b0ab3-120">Het vereiste aantal golven wordt automatisch bepaald door het verwachte aantal gebruikers</span><span class="sxs-lookup"><span data-stu-id="b0ab3-120">The number of waves required is automatically determined by the expected number of users</span></span>
> - <span data-ttu-id="b0ab3-121">Voordat u een portalstart wilt plannen, moet het hulpprogramma [Paginadiagnose voor](https://aka.ms/perftool) SharePoint worden uitgevoerd om te controleren of de startpagina van de site gezond is</span><span class="sxs-lookup"><span data-stu-id="b0ab3-121">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page of the site is healthy</span></span>
> - <span data-ttu-id="b0ab3-122">Aan het einde van de start hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site</span><span class="sxs-lookup"><span data-stu-id="b0ab3-122">At the end of the launch, all users with permissions to the site will be able to access the new site</span></span>
> - <span data-ttu-id="b0ab3-123">Als uw organisatie [Viva Connections](/SharePoint/viva-connections)gebruikt, kunnen gebruikers het pictogram van uw organisatie zien op de app-balk van Microsoft Teams, maar wanneer het pictogram is geselecteerd, kunnen gebruikers pas toegang krijgen tot de portal nadat hun golf is gestart.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-123">If your organization is using [Viva Connections](/SharePoint/viva-connections), users may see your organization's icon in the Microsoft Teams app bar, however when the icon is selected users will not be able to access the portal until their wave has launched</span></span>
> - <span data-ttu-id="b0ab3-124">Deze functie is niet beschikbaar voor Office 365 Duitsland, Office 365 beheerd door 21Vianet (China) of Microsoft 365 amerikaanse overheidsplannen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-124">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans</span></span>

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a><span data-ttu-id="b0ab3-125">De verschillen tussen de opties voor het starten van portals begrijpen:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-125">Understand the differences between Portal launch scheduler options:</span></span>

<span data-ttu-id="b0ab3-126">Voorheen konden portallanceringen alleen worden gepland via SharePoint PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-126">Formerly, portal launches could only be scheduled through SharePoint PowerShell.</span></span> <span data-ttu-id="b0ab3-127">U hebt nu twee opties om u te helpen bij het plannen en beheren van de lancering van uw portal.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-127">Now, you have two options to help you schedule and manage your portal's launch.</span></span> <span data-ttu-id="b0ab3-128">Meer informatie over de belangrijkste verschillen tussen beide hulpprogramma's:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-128">Learn about the key differences between both tools:</span></span>

<span data-ttu-id="b0ab3-129">**SharePoint PowerShell-versie:**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-129">**SharePoint PowerShell version:**</span></span>

- <span data-ttu-id="b0ab3-130">Beheerdersreferenties zijn vereist voor het gebruik [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span><span class="sxs-lookup"><span data-stu-id="b0ab3-130">Admin credentials are required to use [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)</span></span>
- <span data-ttu-id="b0ab3-131">Minimumvereiste van één golf</span><span class="sxs-lookup"><span data-stu-id="b0ab3-131">Minimum requirement of one wave</span></span>
- <span data-ttu-id="b0ab3-132">Start plannen op basis van de tijdzone Coordinated Universal Time (UTC)</span><span class="sxs-lookup"><span data-stu-id="b0ab3-132">Schedule your launch based on Coordinated Universal Time (UTC) time zone</span></span>

<span data-ttu-id="b0ab3-133">**In-productversie:**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-133">**In-product version:**</span></span>

- <span data-ttu-id="b0ab3-134">Referenties van site-eigenaar zijn vereist</span><span class="sxs-lookup"><span data-stu-id="b0ab3-134">Site owner credentials are required</span></span>
- <span data-ttu-id="b0ab3-135">Minimumvereiste van twee golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-135">Minimum requirement of two waves</span></span>
- <span data-ttu-id="b0ab3-136">Start plannen op basis van de lokale tijdzone van de portal, zoals aangegeven in de regionale instellingen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-136">Schedule your launch based on the portal's local time zone as indicated in regional settings</span></span>

## <a name="get-started-using-the-portal-launch-scheduler"></a><span data-ttu-id="b0ab3-137">Aan de slag met de planning voor het starten van portals</span><span class="sxs-lookup"><span data-stu-id="b0ab3-137">Get started using the Portal launch scheduler</span></span>

1. <span data-ttu-id="b0ab3-138">Voordat u het hulpprogramma Voor het starten van portals gebruikt, voegt u alle gebruikers toe die toegang tot deze [site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) nodig hebben via **sitemachtigingen** als site-eigenaar, sitelid of bezoeker.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-138">Before using the Portal launch scheduler tool, [add all users who will need access to this site](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658) through **Site permissions** as a Site owner, Site member, or Visitor.</span></span>

2. <span data-ttu-id="b0ab3-139">Begin vervolgens met het plannen van de lancering van uw portal door op twee manieren toegang te krijgen tot de startschema voor portals:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-139">Then, start scheduling your portal’s launch by accessing the Portal launch scheduler in one of two ways:</span></span>

   <span data-ttu-id="b0ab3-140">**Optie 1:** De eerste paar keer dat u wijzigingen bewerkt en opnieuw uitwerkt op uw startpagina - of tot aan startpagina versie 3.0 - wordt u gevraagd het hulpprogramma Voor het starten van portals te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-140">**Option 1**: The first few times you edit and republish changes to your home page - or up until home page version 3.0 - you will be prompted to use the Portal launch scheduler tool.</span></span> <span data-ttu-id="b0ab3-141">Selecteer **Start plannen om** door te gaan met plannen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-141">Select **Schedule launch** to move forward with scheduling.</span></span> <span data-ttu-id="b0ab3-142">Of selecteer **Opnieuw publiceren om** de paginabewerkingen opnieuw te publiceren zonder de start te plannen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-142">Or select **Republish** to republish your page edits without scheduling the launch.</span></span>

   ![Afbeelding van de prompt om de planning voor het starten van de portal te gebruiken bij het opnieuw publiceren van de startpagina](../media/portal-launch-republish-2.png)

   <span data-ttu-id="b0ab3-144">**Optie 2:** Op elk moment kunt u naar de startpagina  van de communicatiesite SharePoint navigeren, Instellingen selecteren en vervolgens sitelancering plannen om de lancering van uw portal te plannen. </span><span class="sxs-lookup"><span data-stu-id="b0ab3-144">**Option 2**: At any time, you can navigate to the SharePoint communication site home page, select **Settings** and then **Schedule site launch** to schedule your portal’s launch.</span></span>

   ![Afbeelding van het deelvenster Instellingen met Een site starten plannen gemarkeerd](../media/portal-launch-settings-2.png)

3. <span data-ttu-id="b0ab3-146">Bevestig vervolgens de statusscore van de portal en verbeter de portal indien nodig met het hulpprogramma Paginadiagnose voor SharePoint totdat uw portal een gezonde **score** ontvangt. [](https://aka.ms/perftool)</span><span class="sxs-lookup"><span data-stu-id="b0ab3-146">Next, confirm the portal’s health score and make improvements to the portal if needed using the [Page Diagnostics for SharePoint](https://aka.ms/perftool) tool until your portal receives a **Healthy** score.</span></span> <span data-ttu-id="b0ab3-147">Selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-147">Then, select **Next**.</span></span>

   ![Afbeelding van het hulpprogramma Voor het starten van portal](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > <span data-ttu-id="b0ab3-149">De naam en beschrijving van de site kunnen niet worden bewerkt vanuit de planning voor het starten van portals en kunnen **in** plaats daarvan worden gewijzigd door Instellingen en vervolgens **Site-informatie** op de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-149">The site name and description can’t be edited from the Portal launch scheduler and instead can be changed by selecting **Settings** and then **Site information** from the home page.</span></span>

4. <span data-ttu-id="b0ab3-150">Selecteer het **aantal verwachte gebruikers** in de vervolgkeuzekeuze.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-150">Select the **Number of expected users** from the drop-down.</span></span> <span data-ttu-id="b0ab3-151">Deze afbeelding geeft het aantal gebruikers aan dat waarschijnlijk toegang tot de site nodig heeft.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-151">This figure represents the number of users who will most likely need access to the site.</span></span> <span data-ttu-id="b0ab3-152">De planning voor het starten van portals bepaalt automatisch het ideale aantal golven, afhankelijk van de verwachte gebruikers zoals deze:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-152">The Portal launch scheduler will automatically determine the ideal number of waves depending on the expected users like this:</span></span>

   - <span data-ttu-id="b0ab3-153">Minder dan 10.000 gebruikers: twee golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-153">Less than 10k users: Two waves</span></span>
   - <span data-ttu-id="b0ab3-154">10.000 tot 30.000 gebruikers: Drie golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-154">10k to 30k users: Three waves</span></span>
   - <span data-ttu-id="b0ab3-155">30.000 tot 100.000 gebruikers: Vijf golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-155">30k+ to 100k users: Five waves</span></span>
   - <span data-ttu-id="b0ab3-156">Meer dan 100.000 gebruikers: Vijf golven en neem contact op met uw Microsoft via de stappen die worden weergegeven in de sectie Portal starten met meer dan 100.000 gebruikers.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-156">More than 100k users: Five waves and contact your Microsoft via the steps listed in Launch portal with over 100k users section.</span></span>

5. <span data-ttu-id="b0ab3-157">Bepaal vervolgens het **type omleiding dat nodig** is:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-157">Then, determine the **Type of redirect** needed:</span></span>

   <span data-ttu-id="b0ab3-158">Optie 1: Gebruikers verzenden naar een bestaande SharePoint pagina **(bidirectioneel) :** Gebruik deze optie bij het starten van een nieuwe moderne SharePoint-portal om een bestaande SharePoint vervangen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-158">**Option 1: Send users to an existing SharePoint page (bidirectional)** – Use this option when launching a new modern SharePoint portal to replace an existing SharePoint portal.</span></span> <span data-ttu-id="b0ab3-159">Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-159">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="b0ab3-160">Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-160">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b0ab3-161">Wanneer u de optie bidirectioneel gebruikt, moet de persoon die de lancering plant ook machtigingen van de site-eigenaar hebben voor de andere SharePoint portal.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-161">When using the bidirectional option, the person scheduling the launch must also have site owner permissions to the other SharePoint portal.</span></span>

   <span data-ttu-id="b0ab3-162">**Optie 2: Gebruikers** verzenden naar een automatisch gegenereerde tijdelijke pagina (tijdelijke paginaomleiding) - Gebruik een tijdelijke paginaomleiding moet worden gebruikt wanneer er geen bestaande SharePoint portal bestaat.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-162">**Option 2: Send users to an autogenerated temporary page (temporary page redirection)** – Use a temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="b0ab3-163">Gebruikers worden doorgestuurd naar een nieuwe moderne SharePoint portal en als een gebruiker in een golf zit die niet is gestart, worden ze omgeleid naar een tijdelijke pagina.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-163">Users are directed to a new modern SharePoint portal and if a user is in a wave that has not been launched, they will be redirected to a temporary page.</span></span>

   <span data-ttu-id="b0ab3-164">**Optie 3: Gebruikers** naar een externe pagina verzenden: geef een externe URL op voor een tijdelijke landingspagina totdat de golf van de gebruiker wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-164">**Option 3: Send users to an external page** – Provide an external URL to a temporary landing page experience until the user’s wave is launched.</span></span>

6. <span data-ttu-id="b0ab3-165">Verbreed uw publiek in golven.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-165">Break up your audience into waves.</span></span> <span data-ttu-id="b0ab3-166">Voeg maximaal 20 beveiligingsgroepen per golf toe.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-166">Add up to 20 security groups per wave.</span></span> <span data-ttu-id="b0ab3-167">Golfdetails kunnen tot het begin van elke golf worden bewerkt.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-167">Wave details can be edited up until the launch of each wave.</span></span> <span data-ttu-id="b0ab3-168">Elke golf kan minimaal één dag (24 uur) en ten minste zeven dagen duren.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-168">Each wave can last at minimum one day (24 hours) and at most seven days.</span></span> <span data-ttu-id="b0ab3-169">Dit biedt SharePoint en uw technische omgeving de mogelijkheid om te acclimeren en te schalen naar het grote aantal sitegebruikers.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-169">This allows SharePoint and your technical environment an opportunity to acclimate and scale to the large volume of site users.</span></span> <span data-ttu-id="b0ab3-170">Bij het plannen van een start via de gebruikersinterface is de tijdzone gebaseerd op de regionale instellingen van de site.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-170">When scheduling a launch through the UI, the time zone is based on the site’s regional settings.</span></span>

   > [!NOTE]
   >
   > - <span data-ttu-id="b0ab3-171">De planning voor het starten van portals wordt automatisch standaard ingesteld op minimaal 2 golven.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-171">The Portal launch scheduler will automatically default to a minimum of 2 waves.</span></span> <span data-ttu-id="b0ab3-172">De PowerShell-versie van dit hulpprogramma biedt echter 1 golf.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-172">However, the PowerShell version of this tool will allow for 1 wave.</span></span>
   > - <span data-ttu-id="b0ab3-173">Microsoft 365 groepen worden niet ondersteund door deze versie van de planning voor het starten van portals.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-173">Microsoft 365 groups are not supported by this version of the Portal launch scheduler.</span></span>

7. <span data-ttu-id="b0ab3-174">Bepaal wie de site direct moet bekijken en voer de gegevens in in **het veld Gebruikers die zijn vrijgesteld van golven.**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-174">Determine who needs to view the site right away and enter their information into the **Users exempt from waves** field.</span></span> <span data-ttu-id="b0ab3-175">Deze gebruikers worden uitgesloten van golven en worden niet omgeleid vóór, tijdens of na de lancering.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-175">These users are excluded from waves and will not be redirected before, during, or after the launch.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0ab3-176">Maximaal 50 afzonderlijke gebruikers of beveiligingsgroepen kunnen maximaal worden gebruikt voor de hele lancering.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-176">Up to 50 distinct users or security groups max can be used for the entire launch.</span></span> <span data-ttu-id="b0ab3-177">Elke start is onafhankelijk van elkaar, dus als u een lancering in een andere portal plant, kunt u maximaal 50 gebruikers/beveiligingsgroepen gebruiken voor die start.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-177">Each launch is independent of each other, so if you schedule a launch on another portal, then you could use up to 50 users/security groups for that launch.</span></span> <span data-ttu-id="b0ab3-178">Daarnaast kunt u maximaal 20 verschillende gebruikers of beveiligingsgroepen per golf gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-178">Additionally, you can use up to 20 distinct users or security groups per wave.</span></span> 

><span data-ttu-id="b0ab3-179">De planning voor het starten van portals ondersteunt beveiligingsgroepen en beveiligingsgroepen met e-mail.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-179">The portal launch scheduler supports security groups and mail enabled security groups.</span></span> 


8. <span data-ttu-id="b0ab3-180">Bevestig de details van de portallancering en selecteer **Planning.**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-180">Confirm portal launch details and select **Schedule**.</span></span> <span data-ttu-id="b0ab3-181">Nadat de start is gepland, moeten wijzigingen in de startpagina van de portal SharePoint een gezond diagnostisch resultaat ontvangen voordat de portal wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-181">Once the launch has been scheduled, any changes to the SharePoint portal home page will need to receive a healthy diagnostic result before the portal launch will resume.</span></span>

### <a name="launch-a-portal-with-over-100k-users"></a><span data-ttu-id="b0ab3-182">Een portal starten met meer dan 100.000 gebruikers</span><span class="sxs-lookup"><span data-stu-id="b0ab3-182">Launch a portal with over 100k users</span></span>

<span data-ttu-id="b0ab3-183">Als u van plan bent een portal met meer dan 100.000 gebruikers te starten, dient u een ondersteuningsaanvraag in volgens de onderstaande stappen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-183">If you are planning to launch a portal with over 100,000 users, submit a support request following the steps listed below.</span></span> <span data-ttu-id="b0ab3-184">Zorg ervoor dat u alle gevraagde informatie op moet nemen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-184">Make sure to include all the requested information.</span></span>

<span data-ttu-id="b0ab3-185">**Volg deze stappen:**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-185">**Follow these steps:**</span></span>

1. <span data-ttu-id="b0ab3-186">Ga naar <https://admin.microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-186">Go to <https://admin.microsoft.com>.</span></span>
2. <span data-ttu-id="b0ab3-187">Controleer of u de preview van het nieuwe beheercentrum gebruikt</span><span class="sxs-lookup"><span data-stu-id="b0ab3-187">Ensure you are using the new admin center preview</span></span>
3. <span data-ttu-id="b0ab3-188">Selecteer ondersteuning in het linkernavigatiedeelvenster **en** selecteer vervolgens **Nieuwe serviceaanvraag**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-188">On the left navigational pane, select **Support**, and then select **New Service Request**</span></span>

   <span data-ttu-id="b0ab3-189">Hiermee wordt het deelvenster **Hulp nodig?** aan de rechterkant van het scherm geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-189">This will activate the **Need Help?** pane on the right-hand side of your screen.</span></span>

4. <span data-ttu-id="b0ab3-190">Voor **Kort beschrijven van uw probleem,** typt u 'Launch SharePoint Portal with 100k users'</span><span class="sxs-lookup"><span data-stu-id="b0ab3-190">For **Briefly describe your issue**, enter "Launch SharePoint Portal with 100k users"</span></span></br>
5. <span data-ttu-id="b0ab3-191">Selecteer vervolgens **Contact opnemen met ondersteuning**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-191">Then, select **Contact Support**</span></span>
6. <span data-ttu-id="b0ab3-192">Voer **onder Beschrijving**'Start SharePoint Portal met 100.000 gebruikers' in</span><span class="sxs-lookup"><span data-stu-id="b0ab3-192">Under **Description**, enter "Launch SharePoint Portal with 100k users"</span></span>
7. <span data-ttu-id="b0ab3-193">Vul de resterende gegevens in en selecteer contact **met mij opnemen**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-193">Fill out the remaining information, and then select **Contact me**</span></span>
8. <span data-ttu-id="b0ab3-194">Nadat het ticket is gemaakt, moet u de ondersteuningsagent de volgende informatie geven:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-194">After the ticket has been created, ensure you provide the support agent with the following information:</span></span>
   - <span data-ttu-id="b0ab3-195">Portal-URL's</span><span class="sxs-lookup"><span data-stu-id="b0ab3-195">Portal URL's</span></span>
   - <span data-ttu-id="b0ab3-196">Aantal verwachte gebruikers</span><span class="sxs-lookup"><span data-stu-id="b0ab3-196">Number of users expected</span></span>
   - <span data-ttu-id="b0ab3-197">Geschatte beginplanning</span><span class="sxs-lookup"><span data-stu-id="b0ab3-197">Estimated launch schedule</span></span>

## <a name="make-changes-to-a-scheduled-portal-launch"></a><span data-ttu-id="b0ab3-198">Wijzigingen aanbrengen in een geplande portallancering</span><span class="sxs-lookup"><span data-stu-id="b0ab3-198">Make changes to a scheduled portal launch</span></span>

<span data-ttu-id="b0ab3-199">Startdetails kunnen worden bewerkt voor elke golf omhoog tot de datum van de lancering van de golf.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-199">Launch details can be edited for each wave up until the date of the wave’s launch.</span></span>

1. <span data-ttu-id="b0ab3-200">Als u de details van de portallancering wilt bewerken, **gaat u naar Instellingen** en **selecteert u Site starten plannen.**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-200">To edit portal launch details, navigate to **Settings** and select **Schedule site launch**.</span></span>
2. <span data-ttu-id="b0ab3-201">Selecteer vervolgens **Bewerken.**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-201">Then, select **Edit**.</span></span>
3. <span data-ttu-id="b0ab3-202">Wanneer u klaar bent met het bewerken, selecteert u **Bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="b0ab3-202">When you are finished making your edits, select **Update**.</span></span>

## <a name="delete-a-scheduled-portal-launch"></a><span data-ttu-id="b0ab3-203">Een geplande portallancering verwijderen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-203">Delete a scheduled portal launch</span></span>

<span data-ttu-id="b0ab3-204">Lanceringen die zijn gepland met het hulpprogramma Voor het starten van portals, kunnen op elk moment worden geannuleerd of verwijderd, zelfs als sommige golven al zijn gestart.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-204">Launches scheduled using the Portal launch scheduler tool can be canceled, or deleted, at any time even if some waves have already been launched.</span></span>

1. <span data-ttu-id="b0ab3-205">Als u de start van uw portal wilt annuleren, gaat u naar **Instellingen** en **Start van de site plannen**.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-205">To cancel your portal’s launch, navigate to **Settings** and **Schedule site launch**.</span></span>

2. <span data-ttu-id="b0ab3-206">Selecteer vervolgens **Verwijderen en** selecteer nogmaals Verwijderen wanneer u het bericht hieronder ziet. </span><span class="sxs-lookup"><span data-stu-id="b0ab3-206">Then, select **Delete** and then when you see the message below select **Delete** again.</span></span>

   ![Afbeelding van het hulpprogramma Voor het starten van portal](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a><span data-ttu-id="b0ab3-208">De startplanning voor PowerShell Portal gebruiken</span><span class="sxs-lookup"><span data-stu-id="b0ab3-208">Use the PowerShell Portal launch scheduler</span></span>

<span data-ttu-id="b0ab3-209">De SharePoint portal launch scheduler tool was oorspronkelijk alleen beschikbaar via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) en wordt nog steeds ondersteund via PowerShell voor klanten die deze methode willen gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-209">The SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method.</span></span> <span data-ttu-id="b0ab3-210">Dezelfde notities aan het begin van dit artikel zijn van toepassing op beide versies van de planning voor het starten van portals.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-210">The same notes at the beginning of this article apply to both versions of the Portal launch scheduler.</span></span>

> [!NOTE]
> <span data-ttu-id="b0ab3-211">U hebt beheerdersmachtigingen nodig om powershell SharePoint gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-211">You need administrator permissions to use SharePoint PowerShell.</span></span>
> <span data-ttu-id="b0ab3-212">Details voor het starten van portals voor lanceringen die in PowerShell zijn gemaakt, worden weergegeven en kunnen worden beheerd in het nieuwe hulpprogramma voor het starten van portals in SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-212">Portal launch details for launches created in PowerShell will appear and can be managed in the new Portal launch scheduler tool in SharePoint.</span></span>

### <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="b0ab3-213">App-installatie en verbinding maken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0ab3-213">App setup and connecting to SharePoint Online</span></span>

1. <span data-ttu-id="b0ab3-214">[Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="b0ab3-214">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="b0ab3-215">Als u een vorige versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's toevoegen of verwijderen en verwijdert u 'SharePoint Online Management Shell'.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-215">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="b0ab3-216">Selecteer op de pagina Downloadcentrum uw taal en klik vervolgens op de knop Downloaden.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-216">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="b0ab3-217">U wordt gevraagd om te kiezen tussen het downloaden van een x64- en x86-.msi bestand.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-217">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="b0ab3-218">Download het x64-bestand als u de 64-bits versie van Windows of het x86-bestand gebruikt als u de 32-bits versie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-218">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="b0ab3-219">Als u het niet weet, zie [Welke versie van Windows besturingssysteem gebruik ik?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="b0ab3-219">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="b0ab3-220">Voer het bestand na het downloaden uit en volg de stappen in de wizard Instellen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-220">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="b0ab3-221">Verbinding maken als SharePoint globale beheerder of beheerder [SharePoint in](/sharepoint/sharepoint-admin-role) Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-221">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="b0ab3-222">Zie Aan de slag [met SharePoint Online Management Shell voor meer informatie.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)</span><span class="sxs-lookup"><span data-stu-id="b0ab3-222">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>

### <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="b0ab3-223">Bestaande installatie voor het starten van portals weergeven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-223">View any existing portal launch setups</span></span>

<span data-ttu-id="b0ab3-224">Als u wilt zien of er bestaande configuraties voor het starten van portals zijn:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-224">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="b0ab3-225">Een portallancering op de site plannen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-225">Schedule a portal launch on the site</span></span>

<span data-ttu-id="b0ab3-226">Het aantal benodigde golven is afhankelijk van de verwachte startgrootte.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-226">The number of waves required depends on your expected launch size.</span></span>

- <span data-ttu-id="b0ab3-227">Minder dan 10.000 gebruikers: Één golf</span><span class="sxs-lookup"><span data-stu-id="b0ab3-227">Less than 10k users: One wave</span></span>
- <span data-ttu-id="b0ab3-228">10.000 tot 30.000 gebruikers: Drie golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-228">10k to 30k users: Three waves</span></span> 
- <span data-ttu-id="b0ab3-229">30.000 tot 100.000 gebruikers: Vijf golven</span><span class="sxs-lookup"><span data-stu-id="b0ab3-229">30k+ to 100k users: Five waves</span></span>
- <span data-ttu-id="b0ab3-230">Meer dan 100.000 gebruikers: Vijf golven en neem contact op met uw Microsoft-accountteam</span><span class="sxs-lookup"><span data-stu-id="b0ab3-230">More than 100k users: Five waves and contact your Microsoft account team</span></span>

#### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="b0ab3-231">Stappen voor bidirectionele omleiding</span><span class="sxs-lookup"><span data-stu-id="b0ab3-231">Steps for bidirectional redirection</span></span>

<span data-ttu-id="b0ab3-232">Bidirectionele omleiding omvat het starten van een nieuwe moderne SharePoint Online-portal om een bestaande SharePoint of moderne portal te vervangen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-232">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="b0ab3-233">Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-233">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="b0ab3-234">Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-234">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span>

<span data-ttu-id="b0ab3-235">We ondersteunen alleen omleiding tussen de standaard startpagina op de oude site en de standaard startpagina op de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-235">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="b0ab3-236">Als u beheerders of eigenaren hebt die toegang nodig hebben tot de oude en nieuwe sites zonder dat deze worden omgeleid, moet u ervoor zorgen dat deze worden weergegeven met de `WaveOverrideUsers` parameter.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-236">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="b0ab3-237">Als u gebruikers wilt migreren van een bestaande SharePoint site naar een nieuwe SharePoint site op een gefaseerd manier:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-237">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="b0ab3-238">Voer de volgende opdracht uit om portallancerings golven aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-238">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="b0ab3-239">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-239">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="b0ab3-240">Volledige validatie.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-240">Complete validation.</span></span> <span data-ttu-id="b0ab3-241">Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-241">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

#### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="b0ab3-242">Stappen voor omleiding naar tijdelijke pagina</span><span class="sxs-lookup"><span data-stu-id="b0ab3-242">Steps for redirection to temporary page</span></span>

<span data-ttu-id="b0ab3-243">Tijdelijke paginaomleiding moet worden gebruikt wanneer er geen bestaande SharePoint portal bestaat.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-243">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="b0ab3-244">Gebruikers worden op een gefaseerd manier doorgestuurd naar SharePoint nieuwe moderne onlineportal.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-244">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="b0ab3-245">Als een gebruiker in een golf zit die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (elke URL).</span><span class="sxs-lookup"><span data-stu-id="b0ab3-245">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span>

1. <span data-ttu-id="b0ab3-246">Voer de volgende opdracht uit om portallancerings golven aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-246">Run the following command to designate portal launch waves.</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
   ```

   <span data-ttu-id="b0ab3-247">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-247">Example:</span></span>

   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
   [{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
   {Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"},
   {Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="b0ab3-248">Volledige validatie.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-248">Complete validation.</span></span> <span data-ttu-id="b0ab3-249">Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-249">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span>

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="b0ab3-250">Een portal starten op de site onderbreken of opnieuw starten</span><span class="sxs-lookup"><span data-stu-id="b0ab3-250">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="b0ab3-251">Voer de volgende opdracht uit om de voortgang van een portal te onderbreken en tijdelijk te voorkomen dat toekomstige golfprogressie optreedt:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-251">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="b0ab3-252">Valideer dat alle gebruikers worden omgeleid naar de oude site.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-252">Validate that all users are redirected to the old site.</span></span>

3. <span data-ttu-id="b0ab3-253">Voer de volgende opdracht uit als u een portallancering wilt starten die is onderbroken:</span><span class="sxs-lookup"><span data-stu-id="b0ab3-253">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. <span data-ttu-id="b0ab3-254">Controleer of de omleiding nu is hersteld.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-254">Validate that the redirection is now restored.</span></span>

### <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="b0ab3-255">Een portallancering op de site verwijderen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-255">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="b0ab3-256">Voer de volgende opdracht uit om een portalstart gepland of in uitvoering voor een site te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-256">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="b0ab3-257">Valideer dat er geen omleiding voor alle gebruikers gebeurt.</span><span class="sxs-lookup"><span data-stu-id="b0ab3-257">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="b0ab3-258">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="b0ab3-258">Learn more</span></span>

[<span data-ttu-id="b0ab3-259">Het plannen van uw portal launch roll-out plan in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b0ab3-259">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)

[<span data-ttu-id="b0ab3-260">Uw communicatiesite plannen</span><span class="sxs-lookup"><span data-stu-id="b0ab3-260">Plan your communication site</span></span>](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
