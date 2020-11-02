---
title: ServiceNow tickets integreren in Microsoft 365 Beveiligingscentrum en compliance Center
description: Informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365 Beveiligingscentrum en compliance Center.
keywords: beveiliging, Microsoft 365, M365, compliance, compliance Center, Beveiligingscentrum, ServiceNow, tickets, taken, sneeuw, verbinding
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769651"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="2d75d-104">ServiceNow tickets integreren in Microsoft 365 Beveiligingscentrum en compliance Center</span><span class="sxs-lookup"><span data-stu-id="2d75d-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
><span data-ttu-id="2d75d-105">**De voorbeeldperiode voor de ServiceNow-connector eindigt**</span><span class="sxs-lookup"><span data-stu-id="2d75d-105">**The preview period for the ServiceNow connector is ending**</span></span><br>
><span data-ttu-id="2d75d-106">Deze functie is niet meer beschikbaar voor het einde van november 2020.</span><span class="sxs-lookup"><span data-stu-id="2d75d-106">This capability will no longer available by the end of November 2020.</span></span> <span data-ttu-id="2d75d-107">Bedankt voor uw feedback en voortdurende ondersteuning terwijl we volgende stappen bepalen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-107">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="2d75d-108">ServiceNow is een populaire Cloud computing platform waarmee bedrijven digitale werkstromen voor bedrijfsactiviteiten kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="2d75d-108">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="2d75d-109">Hun platform bevat IT-werkstromen, werkstromen voor werknemers en workflows van klanten.</span><span class="sxs-lookup"><span data-stu-id="2d75d-109">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="2d75d-110">Meer informatie over ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2d75d-110">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="2d75d-111">Microsoft heeft een samenwerkingsverband gemaakt met ServiceNow, zodat IT-beheerders hun tickets en taken op beide platforms kunnen beheren.</span><span class="sxs-lookup"><span data-stu-id="2d75d-111">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="2d75d-112">[Microsoft 365-Beveiligingscentrum](overview-security-center.md) en het [Microsoft 365 compliance-centrum](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) worden uitgebreid met de mogelijkheid om in ServiceNow in te stellen en tickets te volgen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-112">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="2d75d-113">**ServiceNow tickets beheren in het Beveiligingscentrum**</span><span class="sxs-lookup"><span data-stu-id="2d75d-113">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="2d75d-114">**ServiceNow tickets beheren in het compliance Center** (binnenkort beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="2d75d-114">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d75d-115">Vereisten</span><span class="sxs-lookup"><span data-stu-id="2d75d-115">Prerequisites</span></span>

<span data-ttu-id="2d75d-116">Toegang hebben tot het Microsoft 365-Beveiligingscentrum of het compliance Center en een ServiceNow-exemplaar met:</span><span class="sxs-lookup"><span data-stu-id="2d75d-116">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="2d75d-117">Kingston of hogere versie</span><span class="sxs-lookup"><span data-stu-id="2d75d-117">Kingston or higher version</span></span>
* <span data-ttu-id="2d75d-118">Beheerders HI-referenties hebben</span><span class="sxs-lookup"><span data-stu-id="2d75d-118">Have admin HI credentials</span></span>
* <span data-ttu-id="2d75d-119">Beheerdersrechten hebben voor de instantie van uw doel leverancier</span><span class="sxs-lookup"><span data-stu-id="2d75d-119">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="2d75d-120">U wordt aangeraden gebruikers standaardinstellingen te behouden in uw ServiceNow-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="2d75d-120">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="2d75d-121">Het kan zijn dat bij het voltooien van de installatie checklist en integratie met het Microsoft 365-Beveiligingscentrum fouten zijn opgetreden bij het voltooien</span><span class="sxs-lookup"><span data-stu-id="2d75d-121">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="2d75d-122">Gegevensuitwisseling</span><span class="sxs-lookup"><span data-stu-id="2d75d-122">Data exchange</span></span>

<span data-ttu-id="2d75d-123">Wanneer u het Microsoft 365 Beveiligingscentrum of compliance Center verbindt met ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:</span><span class="sxs-lookup"><span data-stu-id="2d75d-123">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="2d75d-124">Naam van ServiceNow-exemplaar</span><span class="sxs-lookup"><span data-stu-id="2d75d-124">ServiceNow instance name</span></span>
* <span data-ttu-id="2d75d-125">ServiceNow client-ID</span><span class="sxs-lookup"><span data-stu-id="2d75d-125">ServiceNow client ID</span></span>
* <span data-ttu-id="2d75d-126">ServiceNow client Secret</span><span class="sxs-lookup"><span data-stu-id="2d75d-126">ServiceNow client secret</span></span>
* <span data-ttu-id="2d75d-127">ServiceNow Access-& vernieuwingstokens</span><span class="sxs-lookup"><span data-stu-id="2d75d-127">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="2d75d-128">Wanneer u een ServiceNow-ticket maakt via het Microsoft 365-Beveiligingscentrum of nalevings centrum, worden de volgende gegevens naar ServiceNow verzonden:</span><span class="sxs-lookup"><span data-stu-id="2d75d-128">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="2d75d-129">Gebruikers-ID waarmee het maken van tickets wordt gestart</span><span class="sxs-lookup"><span data-stu-id="2d75d-129">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="2d75d-130">Taaknaam</span><span class="sxs-lookup"><span data-stu-id="2d75d-130">Task name</span></span>
* <span data-ttu-id="2d75d-131">Taakbeschrijving</span><span class="sxs-lookup"><span data-stu-id="2d75d-131">Task description</span></span>
* <span data-ttu-id="2d75d-132">Priority</span><span class="sxs-lookup"><span data-stu-id="2d75d-132">Priority</span></span>
* <span data-ttu-id="2d75d-133">Vervaldatum</span><span class="sxs-lookup"><span data-stu-id="2d75d-133">Due date</span></span>
* <span data-ttu-id="2d75d-134">Bron voor aanbevelingen (gebruikers aanbevelingen of Microsoft aanbevelingen)</span><span class="sxs-lookup"><span data-stu-id="2d75d-134">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="2d75d-135">Aanbevelings categorie (apparaten, gegevens, apps, identiteit, infrastructuur)</span><span class="sxs-lookup"><span data-stu-id="2d75d-135">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="2d75d-136">Verbinding maken met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="2d75d-136">Connect to ServiceNow</span></span>

<span data-ttu-id="2d75d-137">Ga naar [ServiceNow tickets maken en bijhouden in het Microsoft 365-Beveiligingscentrum](tickets-security-center.md) voor informatie over hoe u verbinding maakt met ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2d75d-137">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="2d75d-138">Verbinding maken via het nalevings centrum voor Microsoft 365 is binnenkort beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="2d75d-138">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="2d75d-139">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="2d75d-139">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="2d75d-140">U ontvangt een foutbericht in de eerste stap van de installatie Controlelijst (OAuth-maken)</span><span class="sxs-lookup"><span data-stu-id="2d75d-140">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="2d75d-141">**Foutbericht** : leesbewerking voor ' oauth_entity ' van de scope ' x_mioms_m365ticket ' is geweigerd vanwege het toegangsbeleid voor meerdere regels via meerdere bereiken</span><span class="sxs-lookup"><span data-stu-id="2d75d-141">**Error Message** : Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused because of the table's cross-scope access policy</span></span>

<span data-ttu-id="2d75d-142">De app ervan uitgaat dat de beheerder van het ServiceNow-exemplaar OAuth-entiteiten kan maken en lezen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-142">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="2d75d-143">Deze fout kan worden veroorzaakt door aanpassingen in uw exemplaar van ServiceNow die beperkingen opleggen voor het maken of lezen van OAuth-entiteiten.</span><span class="sxs-lookup"><span data-stu-id="2d75d-143">This error could be caused by a customization in your instance of ServiceNow that restricts who can create or read OAuth entities.</span></span>

<span data-ttu-id="2d75d-144">**ServiceNow adviseert dat gebruikers standaardfunctionaliteit behouden.**</span><span class="sxs-lookup"><span data-stu-id="2d75d-144">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="2d75d-145">De tabel configuraties van Application registers instellen op standaard:</span><span class="sxs-lookup"><span data-stu-id="2d75d-145">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="2d75d-146">Label = Application registraties</span><span class="sxs-lookup"><span data-stu-id="2d75d-146">Label = Application Registeries</span></span>
* <span data-ttu-id="2d75d-147">Naam = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="2d75d-147">Name = oauth_entity</span></span>
* <span data-ttu-id="2d75d-148">Toegankelijk van = alle toepassings bereiken</span><span class="sxs-lookup"><span data-stu-id="2d75d-148">Accessible from = All application scopes</span></span>
* <span data-ttu-id="2d75d-149">Vak kan lezen = selectievakje is geselecteerd</span><span class="sxs-lookup"><span data-stu-id="2d75d-149">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2d75d-150">De OAuth-entiteit die is gemaakt voor Microsoft 365-beveiliging valideren & compliance connector</span><span class="sxs-lookup"><span data-stu-id="2d75d-150">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2d75d-151">Ga naar de tabel toepassingen registers ( **Menu > systeem > voor toepassing toepassing** ) in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2d75d-151">Go to application registries table ( **Menu > System OAuth > Application Registry** ) in ServiceNow.</span></span> <span data-ttu-id="2d75d-152">Zoek de OAuth-entiteit die u hebt gemaakt, met de naam die u eraan hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-152">Find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="signing-in-as-the-integration-user"></a><span data-ttu-id="2d75d-153">Aanmelden als de integratiegebruiker</span><span class="sxs-lookup"><span data-stu-id="2d75d-153">Signing in as the integration user</span></span>

<span data-ttu-id="2d75d-154">Voordat u de verbinding tussen Microsoft 365 Beveiligingscentrum en ServiceNow machtigt, moet u ervoor zorgen dat u de gebruikers van de gebruikersaanmelding gebruikt en het wachtwoord dat u hebt gemaakt tijdens de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-154">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user sign in and password you created in the installation steps.</span></span> <span data-ttu-id="2d75d-155">Gebruik geen persoonlijke gegevens.</span><span class="sxs-lookup"><span data-stu-id="2d75d-155">Don't use your personal credentials.</span></span>

1. <span data-ttu-id="2d75d-156">Ga naar de autorisatie pagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2d75d-156">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2d75d-157">Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **niet** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="2d75d-157">If you're signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2d75d-158">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt in de installatie controlelijst.</span><span class="sxs-lookup"><span data-stu-id="2d75d-158">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2d75d-159">Selecteer **toestaan** op de ServiceNow-pagina om te vragen of de Security + compliance connector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="2d75d-159">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2d75d-160">Ga verder met de instellingsstappen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-160">Continue with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="2d75d-161">De berekeningswijze valideren die is gemaakt met de installatie controlelijst voor Microsoft 365 Security & compliance connector</span><span class="sxs-lookup"><span data-stu-id="2d75d-161">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="2d75d-162">Ga naar de tabel gebruikers **(Menu > Gebruikersbeheer > gebruikers** ) in ServiceNow en zoek de integratie-gebruiker die door u is gemaakt, met de naam die u eraan hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-162">Go to Users Table **(Menu > User Administration > Users** ) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="2d75d-163">Voor uw bedrijf is eenmalige aanmelding ingeschakeld waarmee u geen verbinding kunt maken met ServiceNow via het Microsoft 365-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="2d75d-163">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="2d75d-164">Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een foutmelding krijgt of als het niet lukt om u aan te melden, voert u een van de twee oplossingen uit.</span><span class="sxs-lookup"><span data-stu-id="2d75d-164">If your company has enabled single sign-on and you receive an error or sign in is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a><span data-ttu-id="2d75d-165">Meld u aan bij ServiceNow als de gebruikers van de integratie</span><span class="sxs-lookup"><span data-stu-id="2d75d-165">Sign in to ServiceNow as the integration user</span></span>

1. <span data-ttu-id="2d75d-166">Ga terug naar de autorisatie pagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2d75d-166">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="2d75d-167">Selecteer de koppeling **niet die u** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="2d75d-167">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="2d75d-168">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt in de installatie controlelijst.</span><span class="sxs-lookup"><span data-stu-id="2d75d-168">Sign in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="2d75d-169">Selecteer **toestaan** op de ServiceNow-pagina om te vragen of de Security + compliance connector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="2d75d-169">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="2d75d-170">Ga verder met de instellingsstappen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-170">Continue with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="2d75d-171">Een gebruiker met een beveiligingsbeheerder maken</span><span class="sxs-lookup"><span data-stu-id="2d75d-171">Create a security admin user</span></span>

1. <span data-ttu-id="2d75d-172">Maak een gebruiker met bevoegdheden voor beveiligingsbeheerders in azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d75d-172">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="2d75d-173">De gebruiker moet dezelfde naam en hetzelfde e-mailadres hebben als de integratiegebruiker die u hebt gemaakt vanuit de installatie controlelijst.</span><span class="sxs-lookup"><span data-stu-id="2d75d-173">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="2d75d-174">U kunt de functie beveiligingsbeheerder verwijderen zodra de aanmelding en de verbinding zijn voltooid.</span><span class="sxs-lookup"><span data-stu-id="2d75d-174">You can remove the security admin role once sign-in and connection has been completed.</span></span>
2. <span data-ttu-id="2d75d-175">Meld u aan bij het Microsoft 365-Beveiligingscentrum als deze gebruiker en volg de instellingsstappen.</span><span class="sxs-lookup"><span data-stu-id="2d75d-175">Sign in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="2d75d-176">IP-filters</span><span class="sxs-lookup"><span data-stu-id="2d75d-176">IP filtering</span></span>

<span data-ttu-id="2d75d-177">Als u IP-filtering hebt ingeschakeld, moet u mogelijk IP-adressen expliciet toestaan.</span><span class="sxs-lookup"><span data-stu-id="2d75d-177">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="2d75d-178">Zie [toegangsbeheer voor IP-adressen](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="2d75d-178">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="2d75d-179">Zie [Azure IP-bereiken en service Tags-openbare Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) voor een lijst met IP-adressen die u wilt toestaan.</span><span class="sxs-lookup"><span data-stu-id="2d75d-179">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="2d75d-180">De installatie is voltooid, maar u ziet geen tickets en kan niet delen</span><span class="sxs-lookup"><span data-stu-id="2d75d-180">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="2d75d-181">Als u klaar bent met de installatie-en configuratiestappen, maar de ServiceNow-kaarten op de startpagina niet worden weergegeven en u deze niet kunt delen met ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtings pagina op https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="2d75d-181">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="2d75d-182">Selecteer **geautoriseerd** en ga terug naar de startpagina.</span><span class="sxs-lookup"><span data-stu-id="2d75d-182">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="2d75d-183">De kaarten worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="2d75d-183">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="2d75d-184">Resources</span><span class="sxs-lookup"><span data-stu-id="2d75d-184">Resources</span></span>

- [<span data-ttu-id="2d75d-185">ServiceNow tickets beheren in het Beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="2d75d-185">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)
