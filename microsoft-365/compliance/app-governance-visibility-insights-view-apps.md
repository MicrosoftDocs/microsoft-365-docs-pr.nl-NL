---
title: Uw apps weergeven
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
description: Uw apps weergeven.
ms.openlocfilehash: 48a1a2140a3b59091796ca013a12eeefb8a284b9
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420064"
---
# <a name="view-your-apps"></a><span data-ttu-id="96bdb-103">Uw apps weergeven</span><span class="sxs-lookup"><span data-stu-id="96bdb-103">View your apps</span></span>

><span data-ttu-id="96bdb-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="96bdb-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="96bdb-105">Met Microsoft-app-beheer kunt u snel uitgebreide inzichten verkrijgen in de Microsoft 365-apps in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="96bdb-105">Microsoft app governance allows you to quickly gain deep insights into the Microsoft 365 apps in your tenant.</span></span> <span data-ttu-id="96bdb-106">U kunt bijvoorbeeld het volgende zien:</span><span class="sxs-lookup"><span data-stu-id="96bdb-106">For example, you can see:</span></span>

- <span data-ttu-id="96bdb-107">Een lijst met OAuth-apps in de tenant die gebruikmaken van de Microsoft Graph API, samen met relevante app-metagegevens en gebruiksgegevens.</span><span class="sxs-lookup"><span data-stu-id="96bdb-107">A list of OAuth-enabled apps in the tenant that use the Microsoft Graph API, together with relevant app metadata and usage data.</span></span>
- <span data-ttu-id="96bdb-108">App-details met diepere inzichten en informatie door een app in de lijst te selecteren.</span><span class="sxs-lookup"><span data-stu-id="96bdb-108">App details with deeper insights and information by selecting an app in the list.</span></span>

## <a name="getting-a-list-of-all-the-apps-in-your-tenant"></a><span data-ttu-id="96bdb-109">Een lijst met alle apps in uw tenant ophalen</span><span class="sxs-lookup"><span data-stu-id="96bdb-109">Getting a list of all the apps in your tenant</span></span>

<span data-ttu-id="96bdb-110">Voor een overzicht van apps in uw tenant gaat u naar **Microsoft 365-compliancecentrum > App-beveiliging en beheer > Apps**.</span><span class="sxs-lookup"><span data-stu-id="96bdb-110">For a summary of apps in your tenant, go to **Microsoft 365 Compliance Center > App protection & governance > Apps**.</span></span>

![De samenvattingspagina van de MAPG-app in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-apps.png)

>[!Note]
> <span data-ttu-id="96bdb-112">Uw aanmeldingsaccount moet een van [deze rollen](app-governance-get-started.md#administrator-roles) hebben om app-beheergegevens weer te geven.</span><span class="sxs-lookup"><span data-stu-id="96bdb-112">Your sign-in account must have one of [these roles](app-governance-get-started.md#administrator-roles) to view any app governance data.</span></span>
>

<span data-ttu-id="96bdb-113">U ziet een lijst met apps en deze informatie:</span><span class="sxs-lookup"><span data-stu-id="96bdb-113">You will see a list of apps and this information:</span></span>

- <span data-ttu-id="96bdb-114">App-naam</span><span class="sxs-lookup"><span data-stu-id="96bdb-114">App Name</span></span>
- <span data-ttu-id="96bdb-115">Publisher</span><span class="sxs-lookup"><span data-stu-id="96bdb-115">Publisher</span></span>
- <span data-ttu-id="96bdb-116">App-certificering</span><span class="sxs-lookup"><span data-stu-id="96bdb-116">App certification</span></span>

  <span data-ttu-id="96bdb-117">Geeft aan of de app compatibel is met Microsoft-technologieën, voldoet aan de aanbevolen procedures voor cloud-app-beveiliging en wordt ondersteund door Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96bdb-117">Indicates whether the app is compatible with Microsoft technologies, compliant with cloud app security best practices, and supported by Microsoft.</span></span>

- <span data-ttu-id="96bdb-118">Laatst gewijzigd</span><span class="sxs-lookup"><span data-stu-id="96bdb-118">Last modified</span></span>

  <span data-ttu-id="96bdb-119">Geeft de datum weer waarop app-beheer in de client is geïnstalleerd als die datum recenter is dan de datum waarop de app voor het laatst is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="96bdb-119">Shows the date app governance was installed in client if that date is more recent than the date the app was last modified.</span></span>

- <span data-ttu-id="96bdb-120">Installatiedatum</span><span class="sxs-lookup"><span data-stu-id="96bdb-120">Date installed</span></span>
- <span data-ttu-id="96bdb-121">Bevoegdhedenniveau</span><span class="sxs-lookup"><span data-stu-id="96bdb-121">Privilege level</span></span>
- <span data-ttu-id="96bdb-122">Aantal gebruikers</span><span class="sxs-lookup"><span data-stu-id="96bdb-122">Number of users</span></span>
- <span data-ttu-id="96bdb-123">Toegang tot gegevens</span><span class="sxs-lookup"><span data-stu-id="96bdb-123">Data access</span></span>

  <span data-ttu-id="96bdb-124">De som van de gegevensupload en -download in uw tenant van deze app tijdens de laatste dag, samen met de verandering ten opzichte van de dag ervoor.</span><span class="sxs-lookup"><span data-stu-id="96bdb-124">The sum of the app’s data upload and download in the tenant over the last day, along with the change over the prior day.</span></span>

<span data-ttu-id="96bdb-125">App-beheer sorteert de lijst met apps standaard op **app-naam**.</span><span class="sxs-lookup"><span data-stu-id="96bdb-125">App governance sorts the app list by **App name** by default.</span></span> <span data-ttu-id="96bdb-126">Selecteer de kenmerknaam om de lijst op een ander app-kenmerk te sorteren.</span><span class="sxs-lookup"><span data-stu-id="96bdb-126">To sort the list by another app attribute, select the attribute name.</span></span>

<span data-ttu-id="96bdb-127">U kunt ook **Zoeken** selecteren om op naam naar een app te zoeken.</span><span class="sxs-lookup"><span data-stu-id="96bdb-127">You can also select **Search** to search for an app by name.</span></span>

## <a name="getting-detailed-information-on-an-app"></a><span data-ttu-id="96bdb-128">Gedetailleerde informatie over een app ophalen</span><span class="sxs-lookup"><span data-stu-id="96bdb-128">Getting detailed information on an app</span></span>

<span data-ttu-id="96bdb-129">Ga voor gedetailleerde informatie over een specifieke app in uw tenant naar de pagina \*\*Microsoft 365-compliancecentrum > App-beheer > Apps-pagina > \*app-naam\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="96bdb-129">For detailed information on a specific app in your tenant, go to \*\*Microsoft 365 Compliance Center > App governance > Apps page > \*app name\*\*\*.</span></span>

![Het detailvenster voor app-beheer in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-apps-app.png)

<span data-ttu-id="96bdb-131">Het detailvenster van de app bevat aanvullende informatie op deze tabbladen:</span><span class="sxs-lookup"><span data-stu-id="96bdb-131">The app details pane provides additional information on these tabs:</span></span>

| <span data-ttu-id="96bdb-132">Tabbladnaam</span><span class="sxs-lookup"><span data-stu-id="96bdb-132">Tab name</span></span> | <span data-ttu-id="96bdb-133">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="96bdb-133">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="96bdb-134">Details</span><span class="sxs-lookup"><span data-stu-id="96bdb-134">Details</span></span> | <span data-ttu-id="96bdb-135">Bekijk aanvullende gegevens over de app, zoals de datum waarop de eerste toestemming is verleend en de app-id.</span><span class="sxs-lookup"><span data-stu-id="96bdb-135">See additional data on the app such as the date first consented and the App ID.</span></span> <span data-ttu-id="96bdb-136">Als u de eigenschappen van de app wilt zien zoals geregistreerd in Azure AD, selecteert u **App weergeven in Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="96bdb-136">To see the properties of the app as registered in Azure AD, select **View app in Azure AD**.</span></span> |
| <span data-ttu-id="96bdb-137">Gebruik</span><span class="sxs-lookup"><span data-stu-id="96bdb-137">Usage</span></span> | <span data-ttu-id="96bdb-138">Bekijk de gegevens waartoe de app toegang heeft in de tenant, plot het gegevensgebruik en toon het gebruik door de top \<x>-gebruikers en gebruikers met [prioriteitsaccounts](/microsoft-365/admin/setup/priority-accounts).</span><span class="sxs-lookup"><span data-stu-id="96bdb-138">See the data accessed by the app in the tenant, plot the data usage, and show usage by the top \<x> users and users with [priority accounts](/microsoft-365/admin/setup/priority-accounts).</span></span> |
| <span data-ttu-id="96bdb-139">Gebruikers</span><span class="sxs-lookup"><span data-stu-id="96bdb-139">Users</span></span> | <span data-ttu-id="96bdb-140">Bekijk een lijst met gebruikers die de app gebruiken, of ze een prioriteitsaccount zijn en de hoeveelheid gegevens die is gedownload en geüpload.</span><span class="sxs-lookup"><span data-stu-id="96bdb-140">See a list of users who are using the app, whether they are a priority account, and the amount of data downloaded and uploaded.</span></span> |
| <span data-ttu-id="96bdb-141">Machtigingen</span><span class="sxs-lookup"><span data-stu-id="96bdb-141">Permissions</span></span> | <span data-ttu-id="96bdb-142">Bekijk een samenvatting van de machtigingen die zijn verleend aan en gebruikt door de app en de lijst met specifieke machtigingen.</span><span class="sxs-lookup"><span data-stu-id="96bdb-142">See a summary of the permissions granted to and used by the app and the list of specific permissions.</span></span> <span data-ttu-id="96bdb-143">Zie de verwijzing naar [Microsoft Graph-machtigingen](/graph/permissions-reference) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="96bdb-143">See the [Microsoft Graph permissions reference](/graph/permissions-reference) for more information.</span></span> |
|||

<span data-ttu-id="96bdb-144">Voor een ingeschakelde app is er ook een besturingselement **App uitschakelen** om het gebruik van de geselecteerde app uit te schakelen en een besturingselement **App inschakelen** om het gebruik van de uitgeschakelde app in te schakelen.</span><span class="sxs-lookup"><span data-stu-id="96bdb-144">For an enabled app, there is also a **Disable app** control to disable the use of the selected app and an **Enable app** control to enable the use of the disabled app.</span></span> <span data-ttu-id="96bdb-145">Deze acties vereisen deze [beheerdersrollen](app-governance-get-started.md#administrator-roles):</span><span class="sxs-lookup"><span data-stu-id="96bdb-145">These actions require these [administrator roles](app-governance-get-started.md#administrator-roles):</span></span>

- <span data-ttu-id="96bdb-146">Beheerder voor naleving</span><span class="sxs-lookup"><span data-stu-id="96bdb-146">Compliance Administrator</span></span>
- <span data-ttu-id="96bdb-147">Globale beheerder</span><span class="sxs-lookup"><span data-stu-id="96bdb-147">Global Administrator</span></span>
- <span data-ttu-id="96bdb-148">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="96bdb-148">Security Administrator</span></span>
- <span data-ttu-id="96bdb-149">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="96bdb-149">Security Operator</span></span>

## <a name="next-step"></a><span data-ttu-id="96bdb-150">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="96bdb-150">Next step</span></span>

<span data-ttu-id="96bdb-151">[Bepaal uw algehele app-compliancehouding](app-governance-visibility-insights-compliance-posture.md).</span><span class="sxs-lookup"><span data-stu-id="96bdb-151">[Determine your overall app compliance posture](app-governance-visibility-insights-compliance-posture.md).</span></span>
