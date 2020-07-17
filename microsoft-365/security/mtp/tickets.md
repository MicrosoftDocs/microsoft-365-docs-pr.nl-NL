---
title: Integreer ServiceNow-tickets in het Microsoft 365-beveiligingscentrum en het compliancecenter
description: Meer informatie over het maken en bijhouden van tickets in ServiceNow vanuit het Microsoft 365-beveiligingscentrum en het compliancecenter.
keywords: beveiliging, Microsoft 365, M365, compliance, compliance center, security center, ServiceNow, tickets, taken, SNOW, verbinding
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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086665"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a><span data-ttu-id="e516d-104">Integreer ServiceNow-tickets in het Microsoft 365-beveiligingscentrum en het compliancecenter</span><span class="sxs-lookup"><span data-stu-id="e516d-104">Integrate ServiceNow tickets into the Microsoft 365 security center and compliance center</span></span>

[!include[Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e516d-105">ServiceNow is een populair cloud computing-platform dat bedrijven helpt bij het beheren van digitale workflows voor bedrijfsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="e516d-105">ServiceNow is a popular cloud computing platform that helps companies manage digital workflows for enterprise operations.</span></span> <span data-ttu-id="e516d-106">Hun Now-platform heeft IT-workflows, workflows voor werknemers en workflows voor klanten.</span><span class="sxs-lookup"><span data-stu-id="e516d-106">Their Now platform has IT workflows, employee workflows, and customer workflows.</span></span> [<span data-ttu-id="e516d-107">Meer informatie over ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e516d-107">Learn more about ServiceNow</span></span>](https://www.servicenow.com/)

<span data-ttu-id="e516d-108">Microsoft werkt samen met ServiceNow om het voor IT-beheerders gemakkelijker te maken om hun tickets en taken op beide platforms te beheren.</span><span class="sxs-lookup"><span data-stu-id="e516d-108">Microsoft has partnered with ServiceNow to make it easier for IT admins to manage their tickets and tasks in both platforms.</span></span> <span data-ttu-id="e516d-109">[Microsoft 365 security center](overview-security-center.md) en het [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) worden uitgebreid met de mogelijkheid om native tickets te maken en bij te houden in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e516d-109">[Microsoft 365 security center](overview-security-center.md) and the [Microsoft 365 compliance center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) are being enhanced with the ability to natively create and track tickets in ServiceNow.</span></span>

- [<span data-ttu-id="e516d-110">**ServiceNow-tickets beheren in het beveiligingscentrum**</span><span class="sxs-lookup"><span data-stu-id="e516d-110">**Manage ServiceNow tickets in the security center**</span></span>](tickets-security-center.md)
- <span data-ttu-id="e516d-111">**ServiceNow-tickets beheren in het compliance center** (binnenkort beschikbaar)</span><span class="sxs-lookup"><span data-stu-id="e516d-111">**Manage ServiceNow tickets in the compliance center** (coming soon)</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e516d-112">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e516d-112">Prerequisites</span></span>

<span data-ttu-id="e516d-113">Heb toegang tot het Microsoft 365-beveiligingscentrum of compliance center en een ServiceNow-exemplaar met:</span><span class="sxs-lookup"><span data-stu-id="e516d-113">Have access to the Microsoft 365 security center or compliance center and a ServiceNow instance with:</span></span>  

* <span data-ttu-id="e516d-114">Kingston of hogere versie</span><span class="sxs-lookup"><span data-stu-id="e516d-114">Kingston or higher version</span></span>
* <span data-ttu-id="e516d-115">Beheerders-HI-referenties hebben</span><span class="sxs-lookup"><span data-stu-id="e516d-115">Have admin HI credentials</span></span>
* <span data-ttu-id="e516d-116">Beheerdersbevoegdheden hebben op de instantie van uw doelleverancier</span><span class="sxs-lookup"><span data-stu-id="e516d-116">Have admin privileges on your target vendor instance</span></span>

<span data-ttu-id="e516d-117">ServiceNow raadt gebruikers aan de standaardinstellingen in uw ServiceNow-exemplaar te behouden.</span><span class="sxs-lookup"><span data-stu-id="e516d-117">ServiceNow recommends that users keep default settings in your ServiceNow instance.</span></span> <span data-ttu-id="e516d-118">Het hebben van aanpassingen kan fouten veroorzaken bij het invullen van de installatiechecklist en integratie met het Microsoft 365-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="e516d-118">Having customizations could cause errors when completing the installation checklist and integration with the Microsoft 365 security center.</span></span>

## <a name="data-exchange"></a><span data-ttu-id="e516d-119">Gegevensuitwisseling</span><span class="sxs-lookup"><span data-stu-id="e516d-119">Data exchange</span></span>

<span data-ttu-id="e516d-120">Wanneer u het Microsoft 365-beveiligingscentrum of het compliancecenter verbindt met ServiceNow, ontvangt Microsoft de volgende aanvullende gegevens:</span><span class="sxs-lookup"><span data-stu-id="e516d-120">When you connect the Microsoft 365 security center or compliance center to ServiceNow, Microsoft receives the following additional data:</span></span>

* <span data-ttu-id="e516d-121">Naam serviceNow-instantie</span><span class="sxs-lookup"><span data-stu-id="e516d-121">ServiceNow instance name</span></span>
* <span data-ttu-id="e516d-122">ServiceNow-client-id</span><span class="sxs-lookup"><span data-stu-id="e516d-122">ServiceNow client ID</span></span>
* <span data-ttu-id="e516d-123">ServiceNow-clientgeheim</span><span class="sxs-lookup"><span data-stu-id="e516d-123">ServiceNow client secret</span></span>
* <span data-ttu-id="e516d-124">ServiceNow-toegang & tokens vernieuwen</span><span class="sxs-lookup"><span data-stu-id="e516d-124">ServiceNow access & refresh tokens</span></span>

<span data-ttu-id="e516d-125">Wanneer u een ServiceNow-ticket maakt vanuit het Microsoft 365-beveiligingscentrum of compliance center, worden de volgende gegevens naar ServiceNow verzonden:</span><span class="sxs-lookup"><span data-stu-id="e516d-125">When you create a ServiceNow ticket from the Microsoft 365 security center or compliance center, the following data is sent to ServiceNow:</span></span>

* <span data-ttu-id="e516d-126">Gebruikersnaam waarmee het ticket wordt gestart</span><span class="sxs-lookup"><span data-stu-id="e516d-126">User ID that initiates the ticket creation</span></span>
* <span data-ttu-id="e516d-127">Taaknaam</span><span class="sxs-lookup"><span data-stu-id="e516d-127">Task name</span></span>
* <span data-ttu-id="e516d-128">Taakbeschrijving</span><span class="sxs-lookup"><span data-stu-id="e516d-128">Task description</span></span>
* <span data-ttu-id="e516d-129">Priority</span><span class="sxs-lookup"><span data-stu-id="e516d-129">Priority</span></span>
* <span data-ttu-id="e516d-130">Vervaldatum</span><span class="sxs-lookup"><span data-stu-id="e516d-130">Due date</span></span>
* <span data-ttu-id="e516d-131">Aanbevelingsbron (Aanbeveling van de gebruiker of Aanbeveling van Microsoft)</span><span class="sxs-lookup"><span data-stu-id="e516d-131">Recommendation source (User recommendation or Microsoft recommendation)</span></span>
* <span data-ttu-id="e516d-132">Aanbevelingscategorie (Apparaten, Gegevens, Apps, Identiteit, Infrastructuur)</span><span class="sxs-lookup"><span data-stu-id="e516d-132">Recommendation category (Devices, Data, Apps, Identity, Infrastructure)</span></span>

## <a name="connect-to-servicenow"></a><span data-ttu-id="e516d-133">Verbinding maken met ServiceNow</span><span class="sxs-lookup"><span data-stu-id="e516d-133">Connect to ServiceNow</span></span>

<span data-ttu-id="e516d-134">Ga naar [ServiceNow-tickets maken en bijhouden in het Microsoft 365-beveiligingscentrum](tickets-security-center.md) voor meer informatie over hoe u verbinding maken met ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e516d-134">Go to [Create and track ServiceNow tickets in the Microsoft 365 security center](tickets-security-center.md) to learn how to connect to ServiceNow.</span></span> <span data-ttu-id="e516d-135">Verbinding maken vanuit het Microsoft 365 compliance center is binnenkort beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="e516d-135">Connecting from the Microsoft 365 compliance center is coming soon.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e516d-136">Problemen oplossen</span><span class="sxs-lookup"><span data-stu-id="e516d-136">Troubleshooting</span></span>

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a><span data-ttu-id="e516d-137">U ontvangt een foutmelding in de eerste stap van de installatiechecklist (OAuth creation)</span><span class="sxs-lookup"><span data-stu-id="e516d-137">You receive an error in the first step of the installation checklist (OAuth creation)</span></span>

<span data-ttu-id="e516d-138">**Foutbericht**: Lees de bewerking tegen 'oauth_entity' van scope 'x_mioms_m365ticket' is geweigerd vanwege het toegangsbeleid voor de verschillende scopes van de tabel</span><span class="sxs-lookup"><span data-stu-id="e516d-138">**Error Message**: Read operation against 'oauth_entity' from scope 'x_mioms_m365ticket' has been refused due to the table's cross-scope access policy</span></span>

<span data-ttu-id="e516d-139">De app gaat ervan uit dat elke beheerder op de ServiceNow-instantie OAuth-entiteiten kan maken en lezen.</span><span class="sxs-lookup"><span data-stu-id="e516d-139">The app assumes any admin on the ServiceNow instance can create and read OAuth entities.</span></span> <span data-ttu-id="e516d-140">Deze fout kan worden veroorzaakt door een aanpassing in uw exemplaar van ServiceNow, die beperkt wie OAuth-entiteiten kan maken/lezen.</span><span class="sxs-lookup"><span data-stu-id="e516d-140">This error could be caused due to a customization on your instance of ServiceNow, which restricts who can create/read OAuth entities.</span></span>

<span data-ttu-id="e516d-141">**ServiceNow raadt gebruikers aan de standaardfunctionaliteit te behouden.**</span><span class="sxs-lookup"><span data-stu-id="e516d-141">**ServiceNow recommends that users keep default functionality.**</span></span>

<span data-ttu-id="e516d-142">Stel de tabelconfiguraties 'toepassingsregisters' in op standaard:</span><span class="sxs-lookup"><span data-stu-id="e516d-142">Set the "application registries" table configurations to default:</span></span>

* <span data-ttu-id="e516d-143">Label = Toepassingsregisters</span><span class="sxs-lookup"><span data-stu-id="e516d-143">Label = Application Registeries</span></span>
* <span data-ttu-id="e516d-144">Naam = oauth_entity</span><span class="sxs-lookup"><span data-stu-id="e516d-144">Name = oauth_entity</span></span>
* <span data-ttu-id="e516d-145">Toegankelijk vanaf = Alle toepassingsscopes</span><span class="sxs-lookup"><span data-stu-id="e516d-145">Accessible from = All application scopes</span></span>
* <span data-ttu-id="e516d-146">Kan lezen = selectievakje ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e516d-146">Can read = check box selected</span></span>

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e516d-147">De OAuth-entiteit valideren die is gemaakt voor Microsoft 365 Security & Compliance-connector</span><span class="sxs-lookup"><span data-stu-id="e516d-147">How to validate the OAuth entity created for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="e516d-148">Ga naar de tabel toepassingsregisters **(Menu > System OAuth > Application Registry)** in ServiceNow en zoek de OAuth-entiteit die door u is gemaakt, met de naam die u hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e516d-148">Go to application registries table (**Menu > System OAuth > Application Registry**) in ServiceNow and find the OAuth entity created by you, with the name that you assigned it.</span></span>

### <a name="logging-in-as-the-integration-user"></a><span data-ttu-id="e516d-149">Inloggen als integratiegebruiker</span><span class="sxs-lookup"><span data-stu-id="e516d-149">Logging in as the integration user</span></span>

<span data-ttu-id="e516d-150">Voordat u de verbinding tussen Microsoft 365-beveiligingscentrum en ServiceNow autoriseert, moet u de aanmelding en het wachtwoord van de integratiegebruiker gebruiken die u in de installatiestappen hebt gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e516d-150">Before you authorize the connection between Microsoft 365 security center and ServiceNow, make sure you use the integration user login and password you created in the installation steps.</span></span> <span data-ttu-id="e516d-151">Gebruik uw persoonlijke referenties niet.</span><span class="sxs-lookup"><span data-stu-id="e516d-151">Do not use your personal credentials.</span></span>

1. <span data-ttu-id="e516d-152">Ga naar de autorisatiepagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e516d-152">Go the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="e516d-153">Als u bent aangemeld met uw persoonlijke referenties, selecteert u de koppeling **Niet u** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="e516d-153">If you are signed in with your personal credentials, select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="e516d-154">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt vanuit de installatiechecklist.</span><span class="sxs-lookup"><span data-stu-id="e516d-154">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="e516d-155">Selecteer **Toestaan** op de ServiceNow-pagina waarin wordt gevraagd of de Security + Compliance Connector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="e516d-155">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="e516d-156">Ga verder met de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="e516d-156">Proceed with the setup steps.</span></span>

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a><span data-ttu-id="e516d-157">De integratiegebruiker valideren die is gemaakt met de installatiechecklist voor Microsoft 365 Security & Compliance-connector</span><span class="sxs-lookup"><span data-stu-id="e516d-157">How to validate the Integration User created with the installation checklist for Microsoft 365 Security & Compliance connector</span></span>

<span data-ttu-id="e516d-158">Ga naar Gebruikerstabel **(menu > gebruikersbeheer > gebruikers)** in ServiceNow en zoek de integratiegebruiker die door u is gemaakt, met de naam die u hebt toegewezen.</span><span class="sxs-lookup"><span data-stu-id="e516d-158">Go to Users Table **(Menu > User Administration > Users**) in ServiceNow and find the Integration user created by you, with the name that you assigned it.</span></span>

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a><span data-ttu-id="e516d-159">Uw bedrijf heeft één aanmelding ingeschakeld waardoor u geen verbinding maken met ServiceNow via het Microsoft 365-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="e516d-159">Your company has single sign-on enabled which prevents you from connecting to ServiceNow through the Microsoft 365 security center</span></span>

<span data-ttu-id="e516d-160">Als uw bedrijf eenmalige aanmelding heeft ingeschakeld en u een fout ontvangt of als u niet inlogt, volgt u een van de twee oplossingen.</span><span class="sxs-lookup"><span data-stu-id="e516d-160">If your company has enabled single sign-on and you receive an error or login is unsuccessful, follow one of the two solutions.</span></span>

#### <a name="log-into-servicenow-as-the-integration-user"></a><span data-ttu-id="e516d-161">Log in bij ServiceNow als integratiegebruiker</span><span class="sxs-lookup"><span data-stu-id="e516d-161">Log into ServiceNow as the integration user</span></span>

1. <span data-ttu-id="e516d-162">Navigeer terug naar de autorisatiepagina in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e516d-162">Navigate back to the authorization page in ServiceNow.</span></span>
2. <span data-ttu-id="e516d-163">Selecteer de koppeling **Niet u** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="e516d-163">Select the **Not You** link in the upper right-hand corner.</span></span>
3. <span data-ttu-id="e516d-164">Meld u aan bij ServiceNow als de integratiegebruiker die u eerder hebt gemaakt vanuit de installatiechecklist.</span><span class="sxs-lookup"><span data-stu-id="e516d-164">Log in to ServiceNow as the integration user you created previously from the installation checklist.</span></span>  
4. <span data-ttu-id="e516d-165">Selecteer **Toestaan** op de ServiceNow-pagina waarin wordt gevraagd of de Security + Compliance Connector verbinding kan maken met uw ServiceNow-account.</span><span class="sxs-lookup"><span data-stu-id="e516d-165">Select **Allow** in the ServiceNow page that asks whether the Security + Compliance Connector can connect to your ServiceNow account.</span></span>
5. <span data-ttu-id="e516d-166">Ga verder met de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="e516d-166">Proceed with the setup steps.</span></span>

#### <a name="create-a-security-admin-user"></a><span data-ttu-id="e516d-167">Een beveiligingsbeheerder maken</span><span class="sxs-lookup"><span data-stu-id="e516d-167">Create a security admin user</span></span>

1. <span data-ttu-id="e516d-168">Maak een gebruiker met beveiligingsbeheerbevoegdheden in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e516d-168">Create a user with security admin privileges in Azure Active Directory.</span></span> <span data-ttu-id="e516d-169">De gebruiker moet dezelfde naam en e-mailadres hebben als de integratiegebruiker die u hebt gemaakt vanuit de installatiechecklist.</span><span class="sxs-lookup"><span data-stu-id="e516d-169">The user needs to have the same name and email address as the integration user you created from the Installation Checklist.</span></span> <span data-ttu-id="e516d-170">U de rol van de beveiligingsbeheerder verwijderen zodra de aanmelding en verbinding is voltooid.</span><span class="sxs-lookup"><span data-stu-id="e516d-170">You can remove the security admin role once login and connection has been completed.</span></span>
2. <span data-ttu-id="e516d-171">Meld u als gebruiker aan bij het Microsoft 365-beveiligingscentrum en volg de installatiestappen.</span><span class="sxs-lookup"><span data-stu-id="e516d-171">Log in to the Microsoft 365 security center as this user and follow the setup steps.</span></span>

### <a name="ip-filtering"></a><span data-ttu-id="e516d-172">IP-filtering</span><span class="sxs-lookup"><span data-stu-id="e516d-172">IP filtering</span></span>

<span data-ttu-id="e516d-173">Als u IP-filtering hebt ingeschakeld, moet u mogelijk expliciet IP-adressen toestaan.</span><span class="sxs-lookup"><span data-stu-id="e516d-173">If you have enabled IP filtering, you may need to explicitly allow IP addresses.</span></span> <span data-ttu-id="e516d-174">Zie [IP-adrestoegangsbeheer](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) voor informatie over het toestaan van IP-bereiken in ServiceNow.</span><span class="sxs-lookup"><span data-stu-id="e516d-174">See [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) for information on how to allow IP ranges in ServiceNow.</span></span> <span data-ttu-id="e516d-175">Zie [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span><span class="sxs-lookup"><span data-stu-id="e516d-175">See [Azure IP Ranges and Service Tags - Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) for a list of IP addresses to allow.</span></span>

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a><span data-ttu-id="e516d-176">De installatie is voltooid, maar zie geen tickets en kan niet delen</span><span class="sxs-lookup"><span data-stu-id="e516d-176">Installation is complete but don't see tickets and can't share</span></span>

<span data-ttu-id="e516d-177">Als de installatie- en installatiestappen zijn voltooid, maar u de ServiceNow-kaarten niet op de startpagina ziet en niet delen met ServiceNow vanuit Microsoft Secure Score, controleert u de status van de inrichtingspagina op https://security.microsoft.com/ticketProvisioning .</span><span class="sxs-lookup"><span data-stu-id="e516d-177">If the installation and setup steps have been completed, but you don't see the ServiceNow cards on the home page and can't share to ServiceNow from Microsoft Secure Score, check the status of the provisioning page at https://security.microsoft.com/ticketProvisioning.</span></span> <span data-ttu-id="e516d-178">Selecteer **Autoriseren** en ga terug naar de startpagina.</span><span class="sxs-lookup"><span data-stu-id="e516d-178">Select **Authorize** and return to the home page.</span></span> <span data-ttu-id="e516d-179">De kaarten moeten verschijnen.</span><span class="sxs-lookup"><span data-stu-id="e516d-179">The cards should appear.</span></span>

## <a name="resources"></a><span data-ttu-id="e516d-180">Resources</span><span class="sxs-lookup"><span data-stu-id="e516d-180">Resources</span></span>

- [<span data-ttu-id="e516d-181">ServiceNow-tickets beheren in het beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="e516d-181">Manage ServiceNow tickets in the security center</span></span>](tickets-security-center.md)