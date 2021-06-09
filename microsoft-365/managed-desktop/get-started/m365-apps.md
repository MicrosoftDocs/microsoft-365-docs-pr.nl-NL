---
title: Microsoft 365-apps voor ondernemingen
description: Hoe implementeert u Microsoft 365-apps, hoe ze worden bijgewerkt en hoe instellingen worden beheerd
keywords: wijzigingsgeschiedenis
ms.service: m365-md
ms.sitesec: library
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.topic: article
ms.localizationpriority: normal
ms.openlocfilehash: f8dd666c41863192d866693c6860a64064f846e6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904850"
---
# <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="cd5b0-104">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-104">Microsoft 365 Apps for enterprise</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="cd5b0-105">Eerste implementatie</span><span class="sxs-lookup"><span data-stu-id="cd5b0-105">Initial deployment</span></span>

<span data-ttu-id="cd5b0-106">Microsoft Managed Desktop zorgt ervoor dat Microsoft 365-apps voor ondernemingen (64-bits) worden geïnstalleerd als onderdeel van de afbeelding op alle [programmaapparaten.](../service-description/device-list.md)</span><span class="sxs-lookup"><span data-stu-id="cd5b0-106">Microsoft Managed Desktop ensures that Microsoft 365 Apps for enterprise (64-bit) are installed as a part of the image on all [program devices](../service-description/device-list.md).</span></span> <span data-ttu-id="cd5b0-107">Alle volgende toepassingen moeten aanwezig zijn op het apparaat wanneer deze worden geleverd:</span><span class="sxs-lookup"><span data-stu-id="cd5b0-107">All of the following applications should be present on the device when it's delivered:</span></span>

- <span data-ttu-id="cd5b0-108">Word</span><span class="sxs-lookup"><span data-stu-id="cd5b0-108">Word</span></span>
- <span data-ttu-id="cd5b0-109">Excel</span><span class="sxs-lookup"><span data-stu-id="cd5b0-109">Excel</span></span>
- <span data-ttu-id="cd5b0-110">PowerPoint</span><span class="sxs-lookup"><span data-stu-id="cd5b0-110">PowerPoint</span></span>
- <span data-ttu-id="cd5b0-111">Outlook</span><span class="sxs-lookup"><span data-stu-id="cd5b0-111">Outlook</span></span>
- <span data-ttu-id="cd5b0-112">Publisher</span><span class="sxs-lookup"><span data-stu-id="cd5b0-112">Publisher</span></span>
- <span data-ttu-id="cd5b0-113">Toegang</span><span class="sxs-lookup"><span data-stu-id="cd5b0-113">Access</span></span>
- <span data-ttu-id="cd5b0-114">Skype voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="cd5b0-114">Skype for Business</span></span>
- <span data-ttu-id="cd5b0-115">OneNote</span><span class="sxs-lookup"><span data-stu-id="cd5b0-115">OneNote</span></span>

<span data-ttu-id="cd5b0-116">Deze benadering minimaliseert de netwerkeffecten en zorgt ervoor dat gebruikers productief kunnen zijn zodra ze hun apparaat ontvangen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-116">This approach minimizes network impact and ensures that users can be productive as soon as they receive their device.</span></span> <span data-ttu-id="cd5b0-117">Vervolgens implementeren we meer beleidsregels voor beheerde apparaten om de toepassingen in te stellen voor gebruik.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-117">We then deploy more policies to managed devices to set up the applications for use.</span></span>

> [!NOTE]
> <span data-ttu-id="cd5b0-118">Microsoft Teams wordt afzonderlijk van de Microsoft 365-apps voor ondernemingen geïmplementeerd en wordt niet opgenomen in de basisafbeelding.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-118">Microsoft Teams is deployed separately from Microsoft 365 Apps for enterprise and is not included in the base image.</span></span> 

### <a name="available-deployment-to-users"></a><span data-ttu-id="cd5b0-119">Beschikbare implementatie voor gebruikers</span><span class="sxs-lookup"><span data-stu-id="cd5b0-119">Available deployment to users</span></span>

<span data-ttu-id="cd5b0-120">Als een gebruiker om Microsoft 365-apps reden geen toegang heeft tot het apparaat, kunt u een pakket gebruiken om het apparaat terug te geven naar de verwachte status.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-120">If a user does not have Microsoft 365 Apps on their device for any reason, you can use a package to return the device to its expected state.</span></span> <span data-ttu-id="cd5b0-121">Voeg de gebruiker toe aan de **groep Modern Workplace-Office-Office365_Install** en de apps zijn beschikbaar in de Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-121">Add the user to the **Modern Workplace-Office-Office365_Install** group and the apps will become available to them in the Company Portal.</span></span>

### <a name="microsoft-365-apps-for-enterprise-32-bit"></a><span data-ttu-id="cd5b0-122">Microsoft 365-apps voor ondernemingen (32-bits)</span><span class="sxs-lookup"><span data-stu-id="cd5b0-122">Microsoft 365 Apps for enterprise (32-bit)</span></span>

<span data-ttu-id="cd5b0-123">Microsoft Managed Desktop biedt geen ondersteuning voor de implementatie van de 32-bits versie van M365-apps voor ondernemingen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-123">Microsoft Managed Desktop doesn't support the deployment of the 32-bit version of M365 Apps for enterprise.</span></span>

## <a name="updates-to-microsoft-365-apps"></a><span data-ttu-id="cd5b0-124">Updates voor Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="cd5b0-124">Updates to Microsoft 365 Apps</span></span>

<span data-ttu-id="cd5b0-125">Microsoft 365-apps zijn ingesteld op bijwerken op [het Monthly Enterprise-kanaal](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span><span class="sxs-lookup"><span data-stu-id="cd5b0-125">Microsoft 365 Apps are set to update on the [Monthly Enterprise Channel](/deployoffice/overview-update-channels#monthly-enterprise-channel-overview).</span></span> <span data-ttu-id="cd5b0-126">Deze oefening biedt uw gebruikers elke Office nieuwe functies, maar ze ontvangen slechts één update per maand volgens een voorspelbaar releaseschema.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-126">This practice provides your users with new Office features each month, but they'll receive just one update per month on a predictable release schedule.</span></span> <span data-ttu-id="cd5b0-127">Updates worden uitgebracht op de tweede dinsdag van de maand. Deze updates kunnen functie-, beveiligings- en kwaliteitsupdates bevatten.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-127">Updates are released on the second Tuesday of the month; these updates can include feature, security, and quality updates.</span></span> <span data-ttu-id="cd5b0-128">Deze updates worden automatisch uitgevoerd en worden rechtstreeks uit de Office CDN voor dat specifieke kanaal gehaald.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-128">These updates occur automatically and are pulled directly from the Office CDN for that specific channel.</span></span>

<span data-ttu-id="cd5b0-129">Microsoft Managed Desktop elke release om mogelijke problemen in uw omgeving te identificeren.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-129">Microsoft Managed Desktop staggers each release to identify any potential issues in your environment.</span></span> <span data-ttu-id="cd5b0-130">We voltooien de implementatie 28 dagen na de release van de Microsoft 365 App-productgroep.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-130">We complete the rollout 28 days after the release from the Microsoft 365 App product group.</span></span> <span data-ttu-id="cd5b0-131">Microsoft Managed Desktop geplande updatereleases voor verschillende groepen, zodat er tijd beschikbaar is voor validatie en testen als volgt:</span><span class="sxs-lookup"><span data-stu-id="cd5b0-131">Microsoft Managed Desktop schedules update releases to different groups to allow time for validation and testing as follows:</span></span> 

- <span data-ttu-id="cd5b0-132">Test: nul dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-132">Test: zero days</span></span>
- <span data-ttu-id="cd5b0-133">Ten eerste: nul dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-133">First: zero days</span></span>
- <span data-ttu-id="cd5b0-134">Snel: 3 dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-134">Fast: 3 days</span></span>
- <span data-ttu-id="cd5b0-135">Breed: 7 dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-135">Broad: 7 days</span></span>

<span data-ttu-id="cd5b0-136">Microsoft Managed Desktop stelt een updatedeadline van [zeven dagen in](/deployoffice/configure-update-settings-microsoft-365-apps) voor apparaten.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-136">Microsoft Managed Desktop sets a seven-day [update deadline](/deployoffice/configure-update-settings-microsoft-365-apps) for devices.</span></span> <span data-ttu-id="cd5b0-137">Zodra de update beschikbaar is, moet deze binnen zeven dagen zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-137">Once the update is available, it must be installed within seven days.</span></span> <span data-ttu-id="cd5b0-138">Gebruikers krijgen [een](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) melding dat updates vereist zijn op verschillende locaties: de toepassing, in het systeemvak 12 uur vóór de deadline, en ze ontvangen een waarschuwing van 15 minuten vóór de deadline.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-138">Users are [notified](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) that updates are required in several locations: the application, in the system tray 12 hours prior to the deadline, and they receive a 15-minute warning prior to the deadline.</span></span> <span data-ttu-id="cd5b0-139">Alle Microsoft 365-apps moeten worden gesloten om de update te voltooien.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-139">All Microsoft 365 Apps must be closed for the update to complete.</span></span>

### <a name="pausing-or-rolling-back-an-update"></a><span data-ttu-id="cd5b0-140">Een update onderbreken of terugrollen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-140">Pausing or rolling back an update</span></span>

<span data-ttu-id="cd5b0-141">Als u de app-update om Microsoft 365 reden wilt onderbreken of terugdraaien, dient u een ondersteuningsaanvraag voor beheerders in [via](../working-with-managed-desktop/admin-support.md) de Microsoft Managed Desktop portal.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-141">If you need to pause or roll back Microsoft 365 App update for any reason, file an [admin support request](../working-with-managed-desktop/admin-support.md) through the Microsoft Managed Desktop portal.</span></span>

<span data-ttu-id="cd5b0-142">Tijdens een release worden Microsoft Managed Desktop de foutpercentages van alle Microsoft 365-apps.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-142">During a release, Microsoft Managed Desktop monitors the error rates of all Microsoft 365 Apps.</span></span> <span data-ttu-id="cd5b0-143">Als we een aanzienlijk kwaliteitsverschil zien tussen de nieuwe release en de voorganger, kunnen we contact met u opnemen via de Microsoft Managed Desktop Admin portal.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-143">If we note a significant difference in quality between the new release and its predecessor, we might contact you through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="cd5b0-144">Afhankelijk van de ernst wordt u gevraagd of u de release wilt onderbreken of dat we actie hebben ondernomen om een probleem te beperken.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-144">Depending on the severity, we will either ask if you want to pause the release or inform you that we have taken action to mitigate an issue.</span></span> 

### <a name="delivery-optimization"></a><span data-ttu-id="cd5b0-145">Leveringsoptimalisatie</span><span class="sxs-lookup"><span data-stu-id="cd5b0-145">Delivery optimization</span></span>

<span data-ttu-id="cd5b0-146">Delivery Optimization is een peer-to-peer distributietechnologie die beschikbaar is in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-146">Delivery Optimization is a peer-to-peer distribution technology available in Windows 10.</span></span> <span data-ttu-id="cd5b0-147">Hiermee kunnen apparaten inhoud delen, zoals updates, die de apparaten via internet van Microsoft hebben gedownload.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-147">It allows devices to share content, such as updates, that the devices have downloaded from Microsoft over the internet.</span></span> <span data-ttu-id="cd5b0-148">Als u de update gebruikt, kunt u de netwerkbandbreedte verminderen omdat een apparaat delen van de update van een ander apparaat op het lokale netwerk kan downloaden in plaats van de update volledig van Microsoft te moeten downloaden.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-148">Using it can help reduce network bandwidth because a device can get portions of the update from another device on its local network instead of having to download the update completely from Microsoft.</span></span>

<span data-ttu-id="cd5b0-149">[Leveringsoptimalisatie](/deployoffice/delivery-optimization) is standaard ingeschakeld op apparaten met de Windows 10 Enterprise of Windows 10 Education versies.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-149">[Delivery Optimization](/deployoffice/delivery-optimization) is enabled by default on devices running the Windows 10 Enterprise or Windows 10 Education editions.</span></span> 

## <a name="settings-managed-by-microsoft-managed-desktop"></a><span data-ttu-id="cd5b0-150">Instellingen beheerd door Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="cd5b0-150">Settings managed by Microsoft Managed Desktop</span></span>

<span data-ttu-id="cd5b0-151">Microsoft beheert sommige instellingen als onderdeel van de service.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-151">Microsoft manages some settings as a part of the service.</span></span> <span data-ttu-id="cd5b0-152">Microsoft Managed Desktop beheert geen basislijn voor Office beveiliging, maar u kunt er zelf een instellen door de richtlijnen te volgen in de sectie Instellingen u [beheert.](#settings-you-manage)</span><span class="sxs-lookup"><span data-stu-id="cd5b0-152">Microsoft Managed Desktop doesn't manage an Office Security baseline but you can set one yourself by following the guidance in the [Settings you manage](#settings-you-manage) section.</span></span>

### <a name="update-settings"></a><span data-ttu-id="cd5b0-153">Update-instellingen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-153">Update settings</span></span>

<span data-ttu-id="cd5b0-154">Microsoft Managed Desktop alle [update-instellingen voor](/deployoffice/configure-update-settings-microsoft-365-apps) beheerde apparaten behouden en u moet deze instellingen wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-154">Microsoft Managed Desktop maintains all [update settings](/deployoffice/configure-update-settings-microsoft-365-apps) for managed devices and you should modify these settings.</span></span>

### <a name="set-updates-to-occur-automatically"></a><span data-ttu-id="cd5b0-155">Updates automatisch instellen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-155">Set updates to occur automatically</span></span>

<span data-ttu-id="cd5b0-156">**Standaardwaarde**: Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="cd5b0-156">**Default value**: Enabled</span></span>

<span data-ttu-id="cd5b0-157">Dit beleid is geconfigureerd om ervoor te zorgen dat Office apparaten up-to-date kunnen blijven vanuit de cloud.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-157">This policy is configured in order to ensure that all Office devices can be kept up to date from the cloud.</span></span> 

### <a name="set-a-deadline-when-updates-have-to-be-applied"></a><span data-ttu-id="cd5b0-158">Een deadline instellen wanneer updates moeten worden toegepast</span><span class="sxs-lookup"><span data-stu-id="cd5b0-158">Set a deadline when updates have to be applied</span></span>

<span data-ttu-id="cd5b0-159">**Standaardwaarde**: 7 dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-159">**Default value**: 7 days</span></span>

<span data-ttu-id="cd5b0-160">Het **UpdateDeadline-beleid** wordt gebruikt om de respijtperiode te configureren die gebruikers hebben voordat een update wordt afgedwongen op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-160">The **UpdateDeadline** policy is used to configure the grace period which users have before an update is enforced on the device.</span></span> <span data-ttu-id="cd5b0-161">Dit deadlinebeleid activeert ook [meldingen aan](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) de gebruiker om hem of haar te informeren over de wijzigingen die op het apparaat zijn vereist.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-161">This deadline policy also triggers [notifications](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) to the user to inform them of the changes required on their device.</span></span>  

### <a name="defer-updates-on-a-device-for-a-period"></a><span data-ttu-id="cd5b0-162">Updates op een apparaat een bepaalde periode uitstellen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-162">Defer updates on a device for a period</span></span>

<span data-ttu-id="cd5b0-163">Dit beleid is anders geconfigureerd voor elke updatebeheerapparaatgroep en is vereist om Microsoft Managed Desktop de updatedoelen te kunnen bereiken:</span><span class="sxs-lookup"><span data-stu-id="cd5b0-163">This policy is configured differently for each update management device group and is required for Microsoft Managed Desktop to meet its update targets:</span></span>  

- <span data-ttu-id="cd5b0-164">Test: nul dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-164">Test: zero days</span></span>
- <span data-ttu-id="cd5b0-165">Ten eerste: nul dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-165">First: zero days</span></span>
- <span data-ttu-id="cd5b0-166">Snel 7 dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-166">Fast 7 days</span></span>
- <span data-ttu-id="cd5b0-167">Breed: 21 dagen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-167">Broad: 21 days</span></span>

### <a name="update-notifications-settings"></a><span data-ttu-id="cd5b0-168">Instellingen voor meldingen bijwerken</span><span class="sxs-lookup"><span data-stu-id="cd5b0-168">Update notifications settings</span></span>

<span data-ttu-id="cd5b0-169">**Standaardwaarde:** Onwaar</span><span class="sxs-lookup"><span data-stu-id="cd5b0-169">**Default value**: False</span></span>

<span data-ttu-id="cd5b0-170">De instelling Updatemeldingen verbergen is  ingesteld op Onwaar op Microsoft Managed Desktop apparaten om [](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) gebruikers de beste update-ervaring te bieden door hen te informeren wanneer updates vereist zijn.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-170">The "hide update notifications" setting is set to **False** on Microsoft Managed Desktop devices to provide the best update experience for users by [notifying](/deployoffice/end-user-update-notifications-microsoft-365-apps#notifications-your-users-see-when-you-set-an-update-deadline-for-microsoft-365-apps) them when updates are required.</span></span>

### <a name="specify-a-location-to-look-for-updates"></a><span data-ttu-id="cd5b0-171">Een locatie opgeven om te zoeken naar updates</span><span class="sxs-lookup"><span data-stu-id="cd5b0-171">Specify a location to look for updates</span></span>

<span data-ttu-id="cd5b0-172">**Standaardwaarde:** Monthly Enterprise-kanaal</span><span class="sxs-lookup"><span data-stu-id="cd5b0-172">**Default value**: Monthly Enterprise Channel</span></span>

<span data-ttu-id="cd5b0-173">Een combinatie van het **UpdatePath-** en **UpdateChannel-beleid** wordt zo nodig gebruikt om de updateplanning te bereiken.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-173">A combination of the **UpdatePath** and **UpdateChannel** policies is used as needed to achieve the update schedule.</span></span> <span data-ttu-id="cd5b0-174">Dit beleid is ingesteld om ervoor te zorgen dat Office apparaten rechtstreeks updates ontvangen van de CDN voor het Monthly Enterprise-kanaal.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-174">These policies are set to ensure that all Office devices receive updates directly from the CDN for the Monthly Enterprise Channel.</span></span>

### <a name="specify-the-target-version-of-microsoft-365-apps"></a><span data-ttu-id="cd5b0-175">Geef de doelversie van Microsoft 365-apps</span><span class="sxs-lookup"><span data-stu-id="cd5b0-175">Specify the Target Version of Microsoft 365 Apps</span></span>

<span data-ttu-id="cd5b0-176">Het beleid doelversie wordt soms gebruikt door Microsoft Managed Desktop om een specifieke versie van de Office.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-176">The Target Version policy is sometimes used by Microsoft Managed Desktop in order to roll back or pin a specific version of Office.</span></span> 


### <a name="hide-the-option-to-enable-or-disable-office-automatic-updates"></a><span data-ttu-id="cd5b0-177">De optie voor het in- of uitschakelen van automatische Office verbergen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-177">Hide the option to enable or disable Office automatic updates</span></span>

<span data-ttu-id="cd5b0-178">**Standaardwaarde**: Ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="cd5b0-178">**Default value**: Enabled</span></span>

<span data-ttu-id="cd5b0-179">Deze instelling is vereist om Microsoft Managed Desktop te voldoen aan de updatedoelen voor Microsoft 365 toepassingen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-179">This setting is required for Microsoft Managed Desktop to meet its update targets for Microsoft 365 Applications.</span></span> 

### <a name="first-run-settings"></a><span data-ttu-id="cd5b0-180">Instellingen voor het eerst uitvoeren</span><span class="sxs-lookup"><span data-stu-id="cd5b0-180">First run settings</span></span> 

<span data-ttu-id="cd5b0-181">Er zijn verschillende instellingen die van invloed zijn op het gedrag dat de eerste keer Office wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-181">There are several settings that affect the behavior the first time Office is run.</span></span>

### <a name="accept-the-license-terms-on-behalf-of-the-end-user"></a><span data-ttu-id="cd5b0-182">De licentievoorwaarden namens de eindgebruiker accepteren</span><span class="sxs-lookup"><span data-stu-id="cd5b0-182">Accept the license terms on behalf of the end user</span></span>

<span data-ttu-id="cd5b0-183">**Standaardwaarde**: Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="cd5b0-183">**Default value**: Disabled</span></span>

<span data-ttu-id="cd5b0-184">De eerste keer dat een gebruiker een Microsoft 365 app opent, wordt hij of zij gevraagd de licentievoorwaarden te accepteren.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-184">The first time a user opens a Microsoft 365 App, they are prompted to accept the license terms.</span></span> <span data-ttu-id="cd5b0-185">Als u de licentievoorwaarden namens uw gebruikers wilt accepteren, moet u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team waarin u wordt gevraagd deze instelling in te stellen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-185">If you want to accept the license terms on behalf of your users, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

### <a name="suppress-outlook-mobile-check-box"></a><span data-ttu-id="cd5b0-186">Selectievakje Outlook mobiel onderdrukken</span><span class="sxs-lookup"><span data-stu-id="cd5b0-186">Suppress Outlook mobile check box</span></span>

<span data-ttu-id="cd5b0-187">**Standaardwaarde**: Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="cd5b0-187">**Default value**: Disabled</span></span>

<span data-ttu-id="cd5b0-188">De eerste keer dat een gebruiker een Outlook wordt hem of haar gevraagd om een Outlook installeren.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-188">The first time a user opens Outlook they are prompted to install Outlook Mobile.</span></span> <span data-ttu-id="cd5b0-189">Als u niet wilt dat uw gebruikers dit selectievakje zien, kunt u een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team met de vraag of deze instelling is ingeschakeld voor uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-189">If you don’t want your users to see that check box, file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled for your devices.</span></span> 

## <a name="other-settings"></a><span data-ttu-id="cd5b0-190">Andere instellingen</span><span class="sxs-lookup"><span data-stu-id="cd5b0-190">Other settings</span></span>

<span data-ttu-id="cd5b0-191">Er zijn andere Microsoft 365 app-instellingen die Microsoft Managed Desktop u desgewenst namens u kunt configureren.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-191">There are other Microsoft 365 App settings which Microsoft Managed Desktop can optionally configure on your behalf.</span></span> 

### <a name="disable-personal-onedrive"></a><span data-ttu-id="cd5b0-192">Persoonlijke OneDrive</span><span class="sxs-lookup"><span data-stu-id="cd5b0-192">Disable Personal OneDrive</span></span>

<span data-ttu-id="cd5b0-193">**Standaardwaarde**: Uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="cd5b0-193">**Default value**: Disabled</span></span>

<span data-ttu-id="cd5b0-194">Sommige organisaties maken zich zorgen over gebruikers die toegang hebben tot zowel zakelijke als persoonlijke bestanden op hun apparaten.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-194">Some organizations are concerned about users having access to both corporate and personal files on their devices.</span></span> <span data-ttu-id="cd5b0-195">U kunt een serviceaanvraag indienen bij het Microsoft Managed Desktop Operations-team waarin wordt gevraagd of deze instelling moet worden ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-195">You can file a service request with the Microsoft Managed Desktop Operations team asking for this setting to be enabled.</span></span> 

## <a name="settings-you-manage"></a><span data-ttu-id="cd5b0-196">Instellingen beheren</span><span class="sxs-lookup"><span data-stu-id="cd5b0-196">Settings you manage</span></span>

<span data-ttu-id="cd5b0-197">Er zijn veel andere beleidsregels Microsoft Managed Desktop nog niet als onderdeel van onze service is ingesteld.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-197">There are many other policies which Microsoft Managed Desktop does not yet set as a part of our service.</span></span> <span data-ttu-id="cd5b0-198">U kunt dit beleid configureren met Microsoft Intune, die gebruikmaakt van Office cloudbeleidsservice. [](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied)</span><span class="sxs-lookup"><span data-stu-id="cd5b0-198">You can configure these policies by using Microsoft Intune, which uses the [Office Cloud Policy](/DeployOffice/overview-office-cloud-policy-service#how-the-policy-configuration-is-applied) service.</span></span> <span data-ttu-id="cd5b0-199">Als u dit beleid wilt instellen, volgt u de volgende stappen:</span><span class="sxs-lookup"><span data-stu-id="cd5b0-199">To set these policies, follow these steps:</span></span>

1.  <span data-ttu-id="cd5b0-200">Meld u aan bij het Microsoft Endpoint Manager beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-200">Sign in to the Microsoft Endpoint Manager admin center.</span></span>
2.  <span data-ttu-id="cd5b0-201">Selecteer **Apps > beleid voor Office apps > Maken**</span><span class="sxs-lookup"><span data-stu-id="cd5b0-201">Select **Apps > Policies for Office apps > Create**</span></span>
3.  <span data-ttu-id="cd5b0-202">Ga als **volgt te werk** op de pagina Beleidsconfiguratie maken:</span><span class="sxs-lookup"><span data-stu-id="cd5b0-202">On the **Create policy** configuration page, do the following:</span></span>
    - <span data-ttu-id="cd5b0-203">Voer een naam in.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-203">Enter a name.</span></span>
    - <span data-ttu-id="cd5b0-204">Geef een beschrijving op (optioneel).</span><span class="sxs-lookup"><span data-stu-id="cd5b0-204">Provide a description (optional).</span></span>
    - <span data-ttu-id="cd5b0-205">Kies **in opdrachten** of dit beleid van toepassing is op alle gebruikers van Microsoft 365-apps voor ondernemingen of alleen op gebruikers die anoniem documenten openen met webversie van Office.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-205">In **assignments**, choose whether this policy applies to all users of Microsoft 365 Apps for enterprise, or just to users who anonymously access documents using Office for the web.</span></span>
    - <span data-ttu-id="cd5b0-206">Selecteer de op AAD gebaseerde beveiligingsgroep die is toegewezen aan de beleidsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-206">Select the AAD-based security group that is assigned to the policy configuration.</span></span> <span data-ttu-id="cd5b0-207">Elke beleidsconfiguratie kan slechts aan één groep worden toegewezen en aan elke groep kan slechts één beleidsconfiguratie worden toegewezen.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-207">Each policy configuration can only be assigned to one group, and each group can only be assigned one policy configuration.</span></span>
    - <span data-ttu-id="cd5b0-208">Configureer de beleidsinstellingen die moeten worden opgenomen in de beleidsconfiguratie.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-208">Configure the policy settings to be included in the policy configuration.</span></span> <span data-ttu-id="cd5b0-209">U kunt zoeken op de naam van de beleidsinstelling om de beleidsinstelling te zoeken die u wilt configureren.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-209">You can search on the policy setting name to find the policy setting that you want to configure.</span></span> <span data-ttu-id="cd5b0-210">U kunt ook filteren op de toepassing, op de vraag of het beleid een aanbevolen beveiligingslijn is en of het beleid is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-210">You can also filter on the application, on whether the policy is a recommended security baseline, and on whether the policy has been configured.</span></span> <span data-ttu-id="cd5b0-211">De platformkolom geeft aan of het beleid wordt toegepast op Microsoft 365-apps voor ondernemingen voor Windows apparaten, webversie van Office of alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="cd5b0-211">The platform column indicates whether the policy is applied to Microsoft 365 Apps for enterprise for Windows devices, Office for the web, or all.</span></span>
4.  <span data-ttu-id="cd5b0-212">Nadat u de selecties hebt gemaakt, kiest u **Maken.**</span><span class="sxs-lookup"><span data-stu-id="cd5b0-212">After you have made your selections, choose **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="cd5b0-213">Office Configuratiebeleid biedt alleen ondersteuning voor implementatie op basis van gebruikers</span><span class="sxs-lookup"><span data-stu-id="cd5b0-213">Office Configuration Policies only support user-based deployment</span></span>