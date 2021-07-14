---
title: App-beleid maken
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: App-beleid maken.
ms.openlocfilehash: 17417d7fac80f2763edbbaa8dbb2c8be16e47371
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420218"
---
# <a name="create-app-policies"></a><span data-ttu-id="525db-103">App-beleid maken</span><span class="sxs-lookup"><span data-stu-id="525db-103">Create app policies</span></span>

><span data-ttu-id="525db-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="525db-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="525db-105">Naast een ingebouwde set mogelijkheden om afwijkend app-gedrag te detecteren en waarschuwingen te genereren, geeft app-beleid in Microsoft app-governance u de volgende mogelijkheden:</span><span class="sxs-lookup"><span data-stu-id="525db-105">Along with a built-in set of capabilities to detect anomalous app behavior and generate alerts, app policies in Microsoft app governance are a way for you to:</span></span>

- <span data-ttu-id="525db-106">Geef voorwaarden op waarmee app-governance u kan waarschuwen voor app-gedrag voor automatisch of handmatig herstel.</span><span class="sxs-lookup"><span data-stu-id="525db-106">Specify conditions by which app governance can alert you to app behavior for automatic or manual remediation.</span></span>
- <span data-ttu-id="525db-107">Beheer het beveiligings- en nalevingsbeleid voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="525db-107">Implement the app compliance policies for your organization.</span></span>

<span data-ttu-id="525db-108">U kunt app-beleid maken op basis van opgegeven sjablonen die kunnen worden aangepast of u kunt uw eigen aangepaste app-beleid maken.</span><span class="sxs-lookup"><span data-stu-id="525db-108">You can create app policies from provided templates that can be customized, or you can create your own custom app policy.</span></span>

<span data-ttu-id="525db-109">Als u een nieuw app-beleid wilt maken, gaat u naar **Microsoft 365-compliancecentrum > App-beveiliging & -governance > Overzichtspagina > Beleidsregels**:</span><span class="sxs-lookup"><span data-stu-id="525db-109">To create a new app policy, go to **Microsoft 365 Compliance Center > App protection & governance > Overview page > Policies**:</span></span>

- <span data-ttu-id="525db-110">Als u een nieuw app-beleid wilt maken met sjablonen die zijn ontworpen voor app-gebruik, selecteert u **Beleid maken** onder **Een app-gebruiksbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="525db-110">To create a new app policy with templates designed for app usage, select **Create policy** under **Create an app usage policy**.</span></span>
- <span data-ttu-id="525db-111">Als u een nieuw app-beleid wilt maken met sjablonen die zijn ontworpen voor app-machtigingen, selecteert u **Beleid maken** onder **Een machtigingsbeleid maken**.</span><span class="sxs-lookup"><span data-stu-id="525db-111">To create a new app policy with templates designed for app permissions, select **Create policy** under **Create a permissions policy**.</span></span>
- <span data-ttu-id="525db-112">Als u een nieuw app-beleid wilt maken voor app-certificering of voor een aangepast beleid, selecteert u **Nieuwe maken**.</span><span class="sxs-lookup"><span data-stu-id="525db-112">To create a new app policy for app certification or for a custom policy, select **Create new**.</span></span>

## <a name="app-policy-templates"></a><span data-ttu-id="525db-113">App-beleidssjablonen</span><span class="sxs-lookup"><span data-stu-id="525db-113">App policy templates</span></span>

<span data-ttu-id="525db-114">Als u een nieuw app-beleid wilt maken op basis van een app-beleidssjabloon, selecteert u op de pagina **Sjabloon voor app-beleid kiezen** een categorie app-sjabloon, selecteert u de naam van de sjabloon en selecteert u vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-114">To create a new app policy based on an app policy template, on the **Choose App policy template page**, select a category of app template, select the name of the template, and then select **Next**.</span></span>

<span data-ttu-id="525db-115">App-governance heeft drie categorieën app-beleidssjablonen.</span><span class="sxs-lookup"><span data-stu-id="525db-115">App governance has three categories of app policy templates.</span></span>

### <a name="app-users-and-data-access"></a><span data-ttu-id="525db-116">App-gebruikers en gegevenstoegang</span><span class="sxs-lookup"><span data-stu-id="525db-116">App users and data access</span></span>

<span data-ttu-id="525db-117">App-governance bevat deze sjablonen om waarschuwingen voor app-gebruik te genereren.</span><span class="sxs-lookup"><span data-stu-id="525db-117">App governance includes these templates to generate alerts for app usage.</span></span>

| <span data-ttu-id="525db-118">Sjabloonnaam</span><span class="sxs-lookup"><span data-stu-id="525db-118">Template name</span></span> | <span data-ttu-id="525db-119">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="525db-119">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="525db-120">Nieuwe app met veel gegevenstoegang</span><span class="sxs-lookup"><span data-stu-id="525db-120">New app with a high volume of data access</span></span> | <span data-ttu-id="525db-121">Markeert alle recent geregistreerde apps met toegang tot grote hoeveelheden gegevens om ervoor te zorgen dat die gegevenspatronen worden verwacht.</span><span class="sxs-lookup"><span data-stu-id="525db-121">Highlights any recently registered apps with high volume data access to ensure those data patterns are expected.</span></span> <br><br> <span data-ttu-id="525db-122">Dit beleid markeert standaard alle apps die in de afgelopen zeven dagen zijn geregistreerd en die gedurende die periode meer dan 1 GB aan gegevenstoegang hebben gehad.</span><span class="sxs-lookup"><span data-stu-id="525db-122">By default, this policy will flag all apps that have been registered in the last 7 days and that have had more than 1 GB in data access over that period.</span></span> <span data-ttu-id="525db-123">Dit beleid kan worden aangepast met meer voorwaarden en acties.</span><span class="sxs-lookup"><span data-stu-id="525db-123">This policy can be customized with more conditions and actions.</span></span> |
|||

### <a name="app-permissions"></a><span data-ttu-id="525db-124">App-machtigingen</span><span class="sxs-lookup"><span data-stu-id="525db-124">App Permissions</span></span>

<span data-ttu-id="525db-125">App-beheer bevat deze sjablonen voor het genereren van waarschuwingen voor app-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="525db-125">App governance includes these templates to generate alerts for app permissions.</span></span>

| <span data-ttu-id="525db-126">Sjabloonnaam</span><span class="sxs-lookup"><span data-stu-id="525db-126">Template name</span></span> | <span data-ttu-id="525db-127">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="525db-127">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="525db-128">Apps met te veel machtigingen</span><span class="sxs-lookup"><span data-stu-id="525db-128">Overprivileged apps</span></span> | <span data-ttu-id="525db-129">Markeert alle apps met meer verleende machtigingen dan die door die apps worden gebruikt om mogelijkheden voor mogelijke vermindering van machtigingen te identificeren.</span><span class="sxs-lookup"><span data-stu-id="525db-129">Highlights any apps with more granted permissions than are being used by those apps to identify opportunities for potential permission reduction.</span></span> <br><br> <span data-ttu-id="525db-130">Dit beleid markeert standaard alle apps die zijn gemarkeerd als Overprivileged als ze 90 dagen niet worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="525db-130">By default, this policy will flag all apps that are marked as Overprivileged if not used for 90 days.</span></span> <span data-ttu-id="525db-131">Dit tijdsperiodefilter kan worden aangepast met meer voorwaarden en acties.</span><span class="sxs-lookup"><span data-stu-id="525db-131">This time period filter can be customized with more conditions and actions.</span></span> |
| <span data-ttu-id="525db-132">Nieuwe app met machtigingen met hoge bevoegdheden</span><span class="sxs-lookup"><span data-stu-id="525db-132">New app with high-privilege permissions</span></span> | <span data-ttu-id="525db-133">Markeert alle nieuwe apps met machtigingen met hoge bevoegdheden om potentiële apps met een grote footprint te identificeren die mogelijk nader moeten worden onderzocht.</span><span class="sxs-lookup"><span data-stu-id="525db-133">Highlights all new apps with high privilege permissions to identify potential high-footprint apps that may need further investigation.</span></span> <br><br> <span data-ttu-id="525db-134">Dit beleid markeert standaard alle apps die in de afgelopen zeven dagen zijn geregistreerd en die hoge machtigingen hebben.</span><span class="sxs-lookup"><span data-stu-id="525db-134">By default, this policy will flag all apps registered within the last 7 days that have high-scoped permissions.</span></span> |
|||

### <a name="app-certification"></a><span data-ttu-id="525db-135">App-certificering</span><span class="sxs-lookup"><span data-stu-id="525db-135">App certification</span></span>

<span data-ttu-id="525db-136">App-governance bevat deze sjablonen voor het genereren van waarschuwingen voor app-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="525db-136">App governance includes these templates to generate alerts for app certification.</span></span>

| <span data-ttu-id="525db-137">Sjabloonnaam</span><span class="sxs-lookup"><span data-stu-id="525db-137">Template name</span></span> | <span data-ttu-id="525db-138">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="525db-138">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="525db-139">Nieuwe niet-gecertificeerde app</span><span class="sxs-lookup"><span data-stu-id="525db-139">New uncertified app</span></span> | <span data-ttu-id="525db-140">Dit beleid markeert nieuwe apps die het app-certificeringsproces niet hebben doorlopen om ervoor te zorgen dat ze worden verwacht in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="525db-140">Highlights new apps that haven't been through the app certification process to ensure that they are expected in the tenant.</span></span> <br><br> <span data-ttu-id="525db-141">Standaard worden in dit beleid alle apps gemarkeerd die in de afgelopen zeven dagen zijn geregistreerd en die niet zijn gecertificeerd.</span><span class="sxs-lookup"><span data-stu-id="525db-141">By default, this policy will flag all apps that were registered in the last 7 days and are uncertified.</span></span> |
|||

## <a name="custom-app-policies"></a><span data-ttu-id="525db-142">Aangepast app-beleid</span><span class="sxs-lookup"><span data-stu-id="525db-142">Custom app policies</span></span>

<span data-ttu-id="525db-143">Gebruik een aangepast app-beleid wanneer u iets moet doen dat nog niet door een van de ingebouwde sjablonen is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="525db-143">Use a custom app policy when you need to do something not already done by one of the built-in templates.</span></span>

<span data-ttu-id="525db-144">Als u een nieuw aangepast app-beleid wilt maken, selecteert u eerst **Nieuwe maken** op de pagina **Beleidsregels**.</span><span class="sxs-lookup"><span data-stu-id="525db-144">To create a new custom app policy, first select **Create new** on the **Policies** page.</span></span> <span data-ttu-id="525db-145">Selecteer op de **pagina Sjabloon voor app-beleid kiezen** de categorie **Aangepast**, de sjabloon **Aangepast beleid** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-145">On the **Choose App policy template page**, select the **Custom** category, the **Custom policy** template, and then select **Next**.</span></span>

<span data-ttu-id="525db-146">Vul op de pagina **Naam en beschrijving** de volgende velden in:</span><span class="sxs-lookup"><span data-stu-id="525db-146">On the **Name and description** page, configure the following:</span></span>

- <span data-ttu-id="525db-147">Beleidsnaam</span><span class="sxs-lookup"><span data-stu-id="525db-147">Policy Name</span></span>

- <span data-ttu-id="525db-148">Beleidsbeschrijving</span><span class="sxs-lookup"><span data-stu-id="525db-148">Policy Description</span></span>

- <span data-ttu-id="525db-149">Selecteer de ernst van het beleid, waarmee de ernst wordt ingesteld van waarschuwingen die door dit beleid worden gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="525db-149">Select the policy severity, which sets the severity of alerts generated by this policy.</span></span>

  - <span data-ttu-id="525db-150">Hoog</span><span class="sxs-lookup"><span data-stu-id="525db-150">High</span></span>
  - <span data-ttu-id="525db-151">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="525db-151">Medium</span></span>
  - <span data-ttu-id="525db-152">Laag</span><span class="sxs-lookup"><span data-stu-id="525db-152">Low</span></span>

<span data-ttu-id="525db-153">Selecteer op de pagina **Beleidsinstellingen en -voorwaarden kiezen** voor **Kies op welke apps dit beleid van toepassing is**:</span><span class="sxs-lookup"><span data-stu-id="525db-153">On the **Choose Policy settings and conditions** page, for **Choose which apps this policy is applicable for**, select:</span></span>

- <span data-ttu-id="525db-154">Alle apps</span><span class="sxs-lookup"><span data-stu-id="525db-154">All Apps</span></span>
- <span data-ttu-id="525db-155">Specifieke apps kiezen</span><span class="sxs-lookup"><span data-stu-id="525db-155">Choose specific apps</span></span>

  <span data-ttu-id="525db-156">In een deelvenster kunt u een of meer apps selecteren.</span><span class="sxs-lookup"><span data-stu-id="525db-156">A pane allows you to select one or more apps.</span></span>
  <span data-ttu-id="525db-157">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="525db-157">Select **Add**.</span></span>

<span data-ttu-id="525db-158">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-158">Select **Next**.</span></span>

<span data-ttu-id="525db-159">Selecteer op de pagina **Beleidsinstellingen en -voorwaarden kiezen** de optie **Nieuwe voorwaarden instellen voor** en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-159">On the **Choose Policy settings and conditions** page, select **Set new conditions for policy**, and then select **Next**.</span></span>

<span data-ttu-id="525db-160">In het deelvenster **Regel maken** kunt u voorwaarden voor een nieuwe regel selecteren.</span><span class="sxs-lookup"><span data-stu-id="525db-160">The **Create rule** pane allows you to select conditions for a new rule.</span></span> <span data-ttu-id="525db-161">Selecteer **Voorwaarde toevoegen**, selecteer in de lijst met voorwaarden en geef vervolgens de waarde van de voorwaarde op.</span><span class="sxs-lookup"><span data-stu-id="525db-161">Select **Add condition** and select from the list of conditions, and then specify the value of the condition.</span></span> <span data-ttu-id="525db-162">U kunt meerdere voorwaarden toevoegen.</span><span class="sxs-lookup"><span data-stu-id="525db-162">You can add multiple conditions.</span></span>

<span data-ttu-id="525db-163">Hier zijn de beschikbare voorwaarden voor een aangepast app-beleid.</span><span class="sxs-lookup"><span data-stu-id="525db-163">Here are the available conditions for a custom app policy.</span></span>

|<span data-ttu-id="525db-164">Voorwaarde</span><span class="sxs-lookup"><span data-stu-id="525db-164">Condition</span></span> | <span data-ttu-id="525db-165">Geaccepteerde voorwaarden</span><span class="sxs-lookup"><span data-stu-id="525db-165">Condition values accepted</span></span> | <span data-ttu-id="525db-166">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="525db-166">More information</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="525db-167">Leeftijd van app-registratie</span><span class="sxs-lookup"><span data-stu-id="525db-167">App registration age</span></span> | <span data-ttu-id="525db-168">Binnen de afgelopen X dagen</span><span class="sxs-lookup"><span data-stu-id="525db-168">Within last X days</span></span> |  |
| <span data-ttu-id="525db-169">App-certificering</span><span class="sxs-lookup"><span data-stu-id="525db-169">App certification</span></span> | <span data-ttu-id="525db-170">Basisnaleving, MCAS-naleving of n.v.t.</span><span class="sxs-lookup"><span data-stu-id="525db-170">Basic compliance, MCAS Compliance, or N/A</span></span> | [<span data-ttu-id="525db-171">Microsoft 365-certificering</span><span class="sxs-lookup"><span data-stu-id="525db-171">Microsoft 365 Certification</span></span>](https://docs.microsoft.com/microsoft-365-app-certification/docs/enterprise-app-certification-guide) |
| <span data-ttu-id="525db-172">Verificatie van uitgever</span><span class="sxs-lookup"><span data-stu-id="525db-172">Publisher verification</span></span> | <span data-ttu-id="525db-173">Ja of nee</span><span class="sxs-lookup"><span data-stu-id="525db-173">Yes or No</span></span> | [<span data-ttu-id="525db-174">Verificatie van uitgever</span><span class="sxs-lookup"><span data-stu-id="525db-174">Publisher Verification</span></span>](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) |
| <span data-ttu-id="525db-175">Toepassingsmachtiging</span><span class="sxs-lookup"><span data-stu-id="525db-175">Application Permission</span></span> | <span data-ttu-id="525db-176">Selecteer een of meer API-machtigingen in de lijst</span><span class="sxs-lookup"><span data-stu-id="525db-176">Select one or more API permission from list</span></span> | [<span data-ttu-id="525db-177">naslaginformatie over Microsoft Graph machtigingen</span><span class="sxs-lookup"><span data-stu-id="525db-177">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="525db-178">Gedelegeerde machtiging</span><span class="sxs-lookup"><span data-stu-id="525db-178">Delegated Permission</span></span> | <span data-ttu-id="525db-179">Selecteer een of meer API-machtigingen in de lijst</span><span class="sxs-lookup"><span data-stu-id="525db-179">Select one or more API permission from list</span></span> | [<span data-ttu-id="525db-180">naslaginformatie over Microsoft Graph machtigingen</span><span class="sxs-lookup"><span data-stu-id="525db-180">Microsoft Graph permissions reference</span></span>](https://docs.microsoft.com/graph/permissions-reference) |
| <span data-ttu-id="525db-181">Hoge bevoegdheid</span><span class="sxs-lookup"><span data-stu-id="525db-181">High privilege</span></span> | <span data-ttu-id="525db-182">Ja of nee</span><span class="sxs-lookup"><span data-stu-id="525db-182">Yes or No</span></span> | <span data-ttu-id="525db-183">Dit is een interne aanduiding op basis van dezelfde logica die door MCAS wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="525db-183">This is an internal designation based on the same logic used by MCAS.</span></span> |
| <span data-ttu-id="525db-184">App met te veel machtigingen</span><span class="sxs-lookup"><span data-stu-id="525db-184">Overprivileged app</span></span> | <span data-ttu-id="525db-185">Ja of nee</span><span class="sxs-lookup"><span data-stu-id="525db-185">Yes or No</span></span> | <span data-ttu-id="525db-186">Apps met meer machtigingen dan door die apps worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="525db-186">Apps with more granted permissions than are being used by those apps.</span></span> |
| <span data-ttu-id="525db-187">Toegang tot app-gegevens</span><span class="sxs-lookup"><span data-stu-id="525db-187">App data access</span></span> | <span data-ttu-id="525db-188">Meer dan X GB gegevenstoegang per uur</span><span class="sxs-lookup"><span data-stu-id="525db-188">Greater than X GB data access per hour</span></span> |  |
| <span data-ttu-id="525db-189">Trend voor toegang tot app-gegevens</span><span class="sxs-lookup"><span data-stu-id="525db-189">App data access trend</span></span> | <span data-ttu-id="525db-190">X% toename van het gegevensgebruik in de afgelopen zeven dagen</span><span class="sxs-lookup"><span data-stu-id="525db-190">X% increase in data usage in last 7 days</span></span> |  |
| <span data-ttu-id="525db-191">Toegang tot app-API</span><span class="sxs-lookup"><span data-stu-id="525db-191">App API Access</span></span> | <span data-ttu-id="525db-192">Groter dan X API-aanroepen per uur</span><span class="sxs-lookup"><span data-stu-id="525db-192">Greater than X API calls per hour</span></span> |  |
| <span data-ttu-id="525db-193">Trend van API-toegang voor app</span><span class="sxs-lookup"><span data-stu-id="525db-193">App API Access trend</span></span> | <span data-ttu-id="525db-194">X% toename in API-aanroepen in de afgelopen zeven dagen</span><span class="sxs-lookup"><span data-stu-id="525db-194">X% increase in API Calls in last 7 days</span></span>     |  |
| <span data-ttu-id="525db-195">Gebruikers die toestemming hebben verleend</span><span class="sxs-lookup"><span data-stu-id="525db-195">Users consented</span></span> | <span data-ttu-id="525db-196">(Groter dan of Kleiner dan) X gebruikers die toestemming hebben verleend</span><span class="sxs-lookup"><span data-stu-id="525db-196">(Greater than or Less than) X consented users</span></span> |  |
| <span data-ttu-id="525db-197">Gebruiker met prioriteit heeft toestemming verleend</span><span class="sxs-lookup"><span data-stu-id="525db-197">Priority user consented</span></span> | <span data-ttu-id="525db-198">Ja of nee</span><span class="sxs-lookup"><span data-stu-id="525db-198">Yes or No</span></span> | <span data-ttu-id="525db-199">Een gebruiker met een [prioriteitsaccount](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="525db-199">A user with a [priority account](https://docs.microsoft.com/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="525db-200">App-toestemming gegeven door</span><span class="sxs-lookup"><span data-stu-id="525db-200">App consented by</span></span> | <span data-ttu-id="525db-201">Gebruiker(s) selecteren in lijst</span><span class="sxs-lookup"><span data-stu-id="525db-201">Select user(s) from list</span></span> |  |
| <span data-ttu-id="525db-202">De rol van de gebruiker die toestemming geeft</span><span class="sxs-lookup"><span data-stu-id="525db-202">Consenting user’s role</span></span> | <span data-ttu-id="525db-203">Selecteer een of meer opties: Teams-beheerder, adreslijstlezer, beveiligingslezer, nalevingsbeheerder, beveiligingsbeheerder, helpdeskbeheerder, SharePoint-beheerder, Exchange-beheerder, globale lezer, globale beheerder, beheerder van nalevingsgegevens, gebruikersbeheerder, serviceondersteuningsbeheerder</span><span class="sxs-lookup"><span data-stu-id="525db-203">Select one or more: Teams Administrator, Directory Readers, Security Reader, Compliance Administrator, Security Administrator, Helpdesk Administrator, SharePoint Administrator, Exchange Administrator, Global Reader, Global Administrator, Compliance Data Administrator, User Administrator, Service Support Administrator</span></span> | <span data-ttu-id="525db-204">Meerdere selecties toegestaan.</span><span class="sxs-lookup"><span data-stu-id="525db-204">Multiple selections allowed.</span></span> <br><br> <span data-ttu-id="525db-205">Elke Azure AD-rol met toegewezen lid moet beschikbaar worden gemaakt in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="525db-205">Any Azure AD role with assigned member should be made available in this list.</span></span> |
| <span data-ttu-id="525db-206">Werkbelasting geopend</span><span class="sxs-lookup"><span data-stu-id="525db-206">Workload accessed</span></span> | <span data-ttu-id="525db-207">OneDrive en/of SharePoint en/of Exchange</span><span class="sxs-lookup"><span data-stu-id="525db-207">OneDrive and/or SharePoint and/or Exchange</span></span> | <span data-ttu-id="525db-208">Meerdere selecties toegestaan.</span><span class="sxs-lookup"><span data-stu-id="525db-208">Multiple selections allowed.</span></span> |
| <span data-ttu-id="525db-209">Foutpercentage</span><span class="sxs-lookup"><span data-stu-id="525db-209">Error rate</span></span> | <span data-ttu-id="525db-210">Foutpercentage is in de afgelopen zeven dagen groter dan X%, waarbij X een door de beheerder gedefinieerde waarde is</span><span class="sxs-lookup"><span data-stu-id="525db-210">Error rate is greater than X% in the last 7 days, where X is an admin-defined value</span></span> |  |
||||

<!--
NOTE TO WRITER: Replace X in the above table with correct values.
-->

<span data-ttu-id="525db-211">Aan alle opgegeven voorwaarden moet worden voldaan om dit app-beleid van toepassing te laten zijn.</span><span class="sxs-lookup"><span data-stu-id="525db-211">All of the specified conditions must be met for this app policy to apply.</span></span>

<span data-ttu-id="525db-212">Wanneer u klaar bent met het opgeven van de voorwaarden, selecteert u **Opslaan** en selecteert u vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-212">When you are done specifying the conditions, select **Save**, and then select **Next**.</span></span>

<span data-ttu-id="525db-213">Selecteer op de pagina **Beleidsacties definiëren** de optie **App uitschakelen** als u wilt dat app-governance de app uitschakelt wanneer een waarschuwing op basis van dit beleid wordt gegenereerd, en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="525db-213">On the **Define Policy Actions** page, select **Disable app** if you want app governance to disable the app when an alert based on this policy is generated, and then select **Next**.</span></span>

<span data-ttu-id="525db-214">Selecteer op de pagina **Beleidsstatus definiëren** een van de volgende opties:</span><span class="sxs-lookup"><span data-stu-id="525db-214">On the **Define Policy Status** page, select one of these options:</span></span>

- <span data-ttu-id="525db-215">**Auditmodus**: beleidsregels worden geëvalueerd, maar geconfigureerde acties worden niet uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="525db-215">**Audit mode**: Policies are evaluated but configured actions will not occur.</span></span> <span data-ttu-id="525db-216">De beleidsregels voor de auditmodus worden weergegeven met de status **Audit** in de lijst met beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="525db-216">Audit mode policies appear with the status of **Audit** in the list of policies.</span></span>
- <span data-ttu-id="525db-217">**Actief**: beleidsregels worden geëvalueerd en geconfigureerde acties worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="525db-217">**Active**: Policies are evaluated and configured actions will occur.</span></span>
- <span data-ttu-id="525db-218">**Inactief**: beleidsregels worden niet geëvalueerd en geconfigureerde acties worden niet uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="525db-218">**Inactive**: Policies are not evaluated and configured actions will not occur.</span></span>

<!--
## Configure a user-based policy

## Create an app metadata-based policy

Publish metadata-based policies

## Configure access permissions
-->

## <a name="test-and-monitor-your-new-app-policy"></a><span data-ttu-id="525db-219">Uw nieuwe app-beleid testen en bewaken</span><span class="sxs-lookup"><span data-stu-id="525db-219">Test and monitor your new app policy</span></span>

<span data-ttu-id="525db-220">Nu uw app-beleid is gemaakt, moet u het controleren op de pagina **Beleid** om ervoor te zorgen dat het een verwacht aantal actieve waarschuwingen en het totale aantal waarschuwingen registreert tijdens het testen.</span><span class="sxs-lookup"><span data-stu-id="525db-220">Now that your app policy is created, you should monitor it on the **Policies** page to ensure it is registering an expected number of active alerts and total alerts during testing.</span></span> 

![De overzichtspagina van MAPG-beleidsregels in het Microsoft 365-compliancecentrum met een gemarkeerd beleid](..\media\manage-app-protection-governance\mapg-cc-policies-policy.png)

<span data-ttu-id="525db-222">Als het aantal waarschuwingen een onverwacht lage waarde heeft, bewerkt u de instellingen van het app-beleid om ervoor te zorgen dat u deze correct hebt geconfigureerd voordat u de status instelt.</span><span class="sxs-lookup"><span data-stu-id="525db-222">If the number of alerts is an unexpectedly low value, edit the settings of the app policy to ensure you've configured it correctly before setting its status.</span></span>

<span data-ttu-id="525db-223">Hier is een voorbeeld van een proces om een nieuw beleid te maken, het te testen en vervolgens te activeren:</span><span class="sxs-lookup"><span data-stu-id="525db-223">Here is an example of a process for creating a new policy, testing it, and then making it active:</span></span>

1. <span data-ttu-id="525db-224">Maak het nieuwe beleid met de ernst, apps, voorwaarden en acties ingesteld op beginwaarden en de status ingesteld op **Auditmodus**.</span><span class="sxs-lookup"><span data-stu-id="525db-224">Create the new policy with severity, apps, conditions, and actions set to initial values and the status set to **Audit mode**.</span></span>
2. <span data-ttu-id="525db-225">Controleer op verwacht gedrag, zoals gegenereerde waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="525db-225">Check for expected behavior, such as alerts generated.</span></span>
3. <span data-ttu-id="525db-226">Als het gedrag niet wordt verwacht, bewerkt u indien nodig de beleidsapps, voorwaarden en actie-instellingen en gaat u terug naar stap 2.</span><span class="sxs-lookup"><span data-stu-id="525db-226">If the behavior is not expected, edit the policy apps, conditions, and action settings as needed and go back to step 2.</span></span>
4. <span data-ttu-id="525db-227">Als het gedrag wordt verwacht, bewerkt u het beleid en wijzigt u de status ervan in **Actief**.</span><span class="sxs-lookup"><span data-stu-id="525db-227">If the behavior is expected, edit the policy and change its status to **Active**.</span></span>

![De werkstroom voor het maken van app-beleid](../media/manage-app-protection-governance/mapg-create-new-policy-process.png)

## <a name="next-step"></a><span data-ttu-id="525db-229">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="525db-229">Next step</span></span>

[<span data-ttu-id="525db-230">Uw app-beleid beheren.</span><span class="sxs-lookup"><span data-stu-id="525db-230">Manage your app policies.</span></span>](app-governance-app-policies-manage.md)
