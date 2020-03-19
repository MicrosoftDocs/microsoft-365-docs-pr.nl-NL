---
title: Apps implementeren op apparaten
description: Informatie voor het toevoegen en implementeren van apps op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a064a41fc7ab69e31d49553f600dfd6bb91ef7b0
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2019
ms.locfileid: "42812417"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="53abf-104">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="53abf-104">Deploy apps to devices</span></span>
<span data-ttu-id="53abf-105">Een deel van onboarding naar Microsoft Managed Desktop omvat het toevoegen en implementeren van apps op de apparaten van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="53abf-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="53abf-106">Zodra u de Microsoft Managed Desktop-portal gebruikt, u uw apps toevoegen en implementeren.</span><span class="sxs-lookup"><span data-stu-id="53abf-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="53abf-107">Het totale proces ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="53abf-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="53abf-108">[Apps toevoegen aan Microsoft Managed Desktop-portal](#1) - Dit kunnen bestaande LOB-apps (Line-of-Business) zijn of apps uit De Microsoft Store voor Bedrijven die u hebt gesynchroniseerd met Intune.</span><span class="sxs-lookup"><span data-stu-id="53abf-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="53abf-109">[Azure Active Directory -groepen (AD) maken voor app-toewijzing](#2) - U gebruikt deze groepen om app-toewijzing te beheren.</span><span class="sxs-lookup"><span data-stu-id="53abf-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="53abf-110">Apps toewijzen aan uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="53abf-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="53abf-111">Stap 1: Apps toevoegen aan Microsoft Managed Desktop-portal</span><span class="sxs-lookup"><span data-stu-id="53abf-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="53abf-112">U [Win32- of Windows MSI-apps](#lob-apps)of [Microsoft Store for Business-apps](#msfb-apps) toevoegen aan Microsoft Managed Desktop en deze vervolgens implementeren op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="53abf-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="53abf-113">Win32- of Windows MSI-apps naar Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="53abf-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="53abf-114">U uw LOB-apps (line-of-business) toevoegen aan microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="53abf-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="53abf-115">Zie [Microsoft Managed Desktop-app-vereisten](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)voor informatie over vereisten voor apps die zijn geïnstalleerd op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="53abf-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="53abf-116">In deze procedure selecteert u welk type app u wilt toevoegen en configureert en uploadt u de app-bron.</span><span class="sxs-lookup"><span data-stu-id="53abf-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="53abf-117">**Uw LOB-app of Windows-app toevoegen aan Microsoft Managed Desktop-portal**</span><span class="sxs-lookup"><span data-stu-id="53abf-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="53abf-118">U zich aanmelden bij microsoft Managed Desktop-portal of u aanmelden bij Intune en vervolgens zoeken naar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="53abf-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="53abf-119">We tonen aanmelden bij Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="53abf-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="53abf-120">Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="53abf-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="53abf-121">Selecteer **Onder Inventaris**de optie **Apps**.</span><span class="sxs-lookup"><span data-stu-id="53abf-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="53abf-122">Selecteer in de werkbelasting Apps de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="53abf-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="53abf-123">Selecteer in **App toevoegen**de optie **Line-of-business-app** of **Windows-app (Win32).**</span><span class="sxs-lookup"><span data-stu-id="53abf-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="53abf-124">Als u **de line-of-business-app hebt**geselecteerd, raadpleegt u Een [Windows-line-of-business-app toevoegen aan Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) voor instructies over het toevoegen en configureren van bedrijfsapps.</span><span class="sxs-lookup"><span data-stu-id="53abf-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="53abf-125">Als u **De Windows-app (Win32) hebt**geselecteerd, raadpleegt u [Win32-appbeheer](https://docs.microsoft.com/intune/apps-win32-app-management) voor instructies over het toevoegen en configureren van Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="53abf-125">If you selected **Windows app (Win32)**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="53abf-126">Microsoft Store voor Bedrijven-apps</span><span class="sxs-lookup"><span data-stu-id="53abf-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="53abf-127">Als u zich nog niet hebt aangemeld bij Microsoft Store for Business, u zich aanmelden wanneer u apps koopt.</span><span class="sxs-lookup"><span data-stu-id="53abf-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="53abf-128">Nadat u uw apps hebt, u ze synchroniseren met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="53abf-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="53abf-129">**Apps kopen in de Microsoft Store voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="53abf-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="53abf-130">Meld u aan bij [Microsoft Store for Business](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="53abf-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="53abf-131">Selecteer **Winkelen voor mijn groep**.</span><span class="sxs-lookup"><span data-stu-id="53abf-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="53abf-132">Gebruik Zoeken om de gewenste app te vinden en selecteer de app.</span><span class="sxs-lookup"><span data-stu-id="53abf-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="53abf-133">Selecteer de app **downloaden**in de productdetails.</span><span class="sxs-lookup"><span data-stu-id="53abf-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="53abf-134">Microsoft Store voegt de app toe aan **producten & services** voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="53abf-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="53abf-135">**Synchronisatie tussen Intune en Microsoft Store voor Bedrijven forceren**</span><span class="sxs-lookup"><span data-stu-id="53abf-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="53abf-136">Meld u aan bij [Azure Portal](https://portal.azure.com/) als Intune-beheerder of globale beheerder voor uw tenant</span><span class="sxs-lookup"><span data-stu-id="53abf-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="53abf-137">Selecteer **Alle services > Intune**.</span><span class="sxs-lookup"><span data-stu-id="53abf-137">Select **All services > Intune**.</span></span> <span data-ttu-id="53abf-138">Intune bevindt zich in de sectie Monitoring + Management.</span><span class="sxs-lookup"><span data-stu-id="53abf-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="53abf-139">Selecteer in het deelvenster Intune **client-apps**en selecteer **Vervolgens Microsoft Store voor Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="53abf-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="53abf-140">Selecteer **Inschakelen** om uw Microsoft Store for Business-apps te synchroniseren met Intune.</span><span class="sxs-lookup"><span data-stu-id="53abf-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="53abf-141">Als u dit nog niet hebt gedaan, meldt u zich aan en koppelt u uw Microsoft Store for Business-account aan Intune</span><span class="sxs-lookup"><span data-stu-id="53abf-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="53abf-142">Selecteer de taal waarin apps in de Microsoft Store voor Bedrijven worden weergegeven in uw Intune-console</span><span class="sxs-lookup"><span data-stu-id="53abf-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="53abf-143">Selecteer **Synchroniseren** om uw Microsoft Store for Business-apps te synchroniseren met Intune.</span><span class="sxs-lookup"><span data-stu-id="53abf-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="53abf-144">Controleer of de synchronisatie tussen Microsoft Store for Business en Intune actief is (volgende stap).</span><span class="sxs-lookup"><span data-stu-id="53abf-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="53abf-145">**Controleren of een synchronisatie tussen Intune en Microsoft Store voor Bedrijven actief is**</span><span class="sxs-lookup"><span data-stu-id="53abf-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="53abf-146">Meld u aan bij [Microsoft Store for Business](https://businessstore.microsoft.com) met uw Microsoft Store voor Bedrijven-beheerdersaccount.</span><span class="sxs-lookup"><span data-stu-id="53abf-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="53abf-147">Selecteer **Beheren**.</span><span class="sxs-lookup"><span data-stu-id="53abf-147">Select **Manage**.</span></span>
3. <span data-ttu-id="53abf-148">Selecteer **Instellingen** en selecteer **Vervolgens Distribueren**.</span><span class="sxs-lookup"><span data-stu-id="53abf-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="53abf-149">Controleer **onder Beheergereedschappen**of Intune wordt vermeld en of de status **Actief**is .</span><span class="sxs-lookup"><span data-stu-id="53abf-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="53abf-150">Stap 2: Azure AD-groepen maken</span><span class="sxs-lookup"><span data-stu-id="53abf-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="53abf-151">Maak drie Azure AD-groepen voor elke app.</span><span class="sxs-lookup"><span data-stu-id="53abf-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="53abf-152">In deze tabel worden de groepen beschreven die u nodig hebt (Beschikbaar, Vereist en Verwijderen).</span><span class="sxs-lookup"><span data-stu-id="53abf-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="53abf-153">Type app-toewijzing</span><span class="sxs-lookup"><span data-stu-id="53abf-153">App assignment type</span></span> |   <span data-ttu-id="53abf-154">Groepsgebruik</span><span class="sxs-lookup"><span data-stu-id="53abf-154">Group use</span></span>   | <span data-ttu-id="53abf-155">Voorbeeld azure AD-naam</span><span class="sxs-lookup"><span data-stu-id="53abf-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="53abf-156">Beschikbaar</span><span class="sxs-lookup"><span data-stu-id="53abf-156">Available</span></span> |  <span data-ttu-id="53abf-157">De app is beschikbaar via de bedrijfsportal-app of -website.</span><span class="sxs-lookup"><span data-stu-id="53abf-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="53abf-158">MMD – *app-naam* – Beschikbaar</span><span class="sxs-lookup"><span data-stu-id="53abf-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="53abf-159">Vereist</span><span class="sxs-lookup"><span data-stu-id="53abf-159">Required</span></span> |  <span data-ttu-id="53abf-160">De app is geïnstalleerd op apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="53abf-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="53abf-161">MMD – *app-naam* – Vereist</span><span class="sxs-lookup"><span data-stu-id="53abf-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="53abf-162">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="53abf-162">Uninstall</span></span> |  <span data-ttu-id="53abf-163">De app wordt verwijderd van apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="53abf-163">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="53abf-164">MMD – *app-naam* – Verwijderen</span><span class="sxs-lookup"><span data-stu-id="53abf-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="53abf-165">Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te stellen, de app te installeren of de app te verwijderen van hun Microsoft Managed Desktop-apparaat.</span><span class="sxs-lookup"><span data-stu-id="53abf-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="53abf-166">Stap 3: Apps toewijzen aan uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="53abf-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="53abf-167">**De app toewijzen aan uw gebruikers**</span><span class="sxs-lookup"><span data-stu-id="53abf-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="53abf-168">Meld u aan bij [microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="53abf-168">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="53abf-169">Selecteer **Apps**in het deelvenster Beheerd bureaublad .</span><span class="sxs-lookup"><span data-stu-id="53abf-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="53abf-170">Selecteer in de werkbelasting Apps de app waaraan u gebruikers wilt toewijzen en selecteer **Gebruikersgroepen toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="53abf-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="53abf-171">Selecteer voor de specifieke app een toewijzingstype (Beschikbaar, Vereist, Verwijderen) en wijs de juiste groep toe.</span><span class="sxs-lookup"><span data-stu-id="53abf-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="53abf-172">Selecteer **OK**in het deelvenster Apps toewijzen .</span><span class="sxs-lookup"><span data-stu-id="53abf-172">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="53abf-173">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="53abf-173">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="53abf-174">Beheerderscontactpersonen toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="53abf-174">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="53abf-175">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="53abf-175">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="53abf-176">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="53abf-176">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="53abf-177">Intune-bedrijfsportal implementeren</span><span class="sxs-lookup"><span data-stu-id="53abf-177">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="53abf-178">Roaming voor ondernemingsstatus inschakelen</span><span class="sxs-lookup"><span data-stu-id="53abf-178">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="53abf-179">Apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="53abf-179">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="53abf-180">Uw gebruikers klaar maken om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="53abf-180">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="53abf-181">Apps implementeren (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="53abf-181">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
