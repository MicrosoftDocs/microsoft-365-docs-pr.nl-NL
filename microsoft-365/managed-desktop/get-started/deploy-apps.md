---
title: Apps implementeren op apparaten
description: Informatie voor het toevoegen en implementeren van apps op Microsoft Managed Desktop-apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie, apps, line-of-business-apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922024"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="72f85-104">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="72f85-104">Deploy apps to devices</span></span>
<span data-ttu-id="72f85-105">Onderdeel van onboarding bij Microsoft Managed Desktop is het toevoegen en implementeren van apps op de apparaten van uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="72f85-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="72f85-106">Wanneer u de Microsoft Managed Desktop-portal gebruikt, kunt u uw apps toevoegen en implementeren.</span><span class="sxs-lookup"><span data-stu-id="72f85-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="72f85-107">Het totale proces ziet er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="72f85-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="72f85-108">[Apps toevoegen aan Microsoft Managed Desktop Portal:](#1) dit kunnen bestaande LOB-apps (Line-of-Business) zijn of apps uit de Microsoft Store voor Bedrijven die u hebt gesynchroniseerd met Intune.</span><span class="sxs-lookup"><span data-stu-id="72f85-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="72f85-109">[Ad-groepen (Azure Active Directory) maken voor](#2) app-toewijzing: u gebruikt deze groepen om app-toewijzing te beheren.</span><span class="sxs-lookup"><span data-stu-id="72f85-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="72f85-110">Apps toewijzen aan uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="72f85-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="72f85-111">Stap 1: Apps toevoegen aan Microsoft Managed Desktop Portal</span><span class="sxs-lookup"><span data-stu-id="72f85-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="72f85-112">U kunt [Win32- of Windows MSI-apps](#lob-apps)of Microsoft Store voor Bedrijven-apps toevoegen aan Microsoft Managed Desktop en deze vervolgens implementeren op Microsoft Managed Desktop-apparaten. [](#msfb-apps)</span><span class="sxs-lookup"><span data-stu-id="72f85-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="72f85-113">Win32- of Windows MSI-apps naar Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="72f85-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="72f85-114">U kunt uw LOB-apps (Line-of-Business) toevoegen aan de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="72f85-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="72f85-115">Zie [Microsoft Managed Desktop-appvereisten](../service-description/mmd-app-requirements.md)voor informatie over vereisten voor apps die zijn geïnstalleerd op Microsoft Managed Desktop-apparaten.</span><span class="sxs-lookup"><span data-stu-id="72f85-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="72f85-116">In deze procedure selecteert u welk type app u wilt toevoegen en configureert en uploadt u de app-bron.</span><span class="sxs-lookup"><span data-stu-id="72f85-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="72f85-117">**Uw LOB-app of Windows-app toevoegen aan microsoft managed desktopportal**</span><span class="sxs-lookup"><span data-stu-id="72f85-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="72f85-118">U kunt zich aanmelden bij de Microsoft Managed Desktop Portal of u aanmelden bij Intune en vervolgens zoeken naar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="72f85-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="72f85-119">We laten zien dat u zich aanmeldt bij de Microsoft Managed Desktop-portal.</span><span class="sxs-lookup"><span data-stu-id="72f85-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="72f85-120">Meld u aan bij [de Microsoft Managed Desktop Admin Portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="72f85-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="72f85-121">Selecteer **onder Inventaris** de optie **Apps.**</span><span class="sxs-lookup"><span data-stu-id="72f85-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="72f85-122">Selecteer toevoegen in de werkbelasting **apps.**</span><span class="sxs-lookup"><span data-stu-id="72f85-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="72f85-123">Selecteer **in App toevoegen** de optie **Line-of-Business-app of Windows-app** **(Win32)**.</span><span class="sxs-lookup"><span data-stu-id="72f85-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="72f85-124">Als u **line-of-business-app** hebt geselecteerd, zie [Een Windows-line-of-business-app](/intune/lob-apps-windows) toevoegen aan Microsoft Intune voor instructies over het toevoegen en configureren van line-of-business-apps.</span><span class="sxs-lookup"><span data-stu-id="72f85-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="72f85-125">Als u **Windows-app (Win32)** hebt geselecteerd, zie [Win32-appbeheer](/intune/apps-win32-app-management) voor instructies over het toevoegen en configureren van Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="72f85-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="72f85-126">Microsoft Store voor Bedrijven-apps</span><span class="sxs-lookup"><span data-stu-id="72f85-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="72f85-127">Als u zich nog niet hebt aangemeld bij de Microsoft Store voor Bedrijven, kunt u zich registreren wanneer u naar apps winkelt.</span><span class="sxs-lookup"><span data-stu-id="72f85-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="72f85-128">Nadat u uw apps hebt, kunt u deze synchroniseren met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="72f85-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="72f85-129">**Apps kopen in de Microsoft Store voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="72f85-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="72f85-130">Meld u aan [bij de Microsoft Store voor Bedrijven met](https://businessstore.microsoft.com) uw Microsoft Store voor Bedrijven-account.</span><span class="sxs-lookup"><span data-stu-id="72f85-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="72f85-131">Selecteer **Winkelen voor mijn groep.**</span><span class="sxs-lookup"><span data-stu-id="72f85-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="72f85-132">Gebruik Zoeken om te zoeken naar de beste app en selecteer de app.</span><span class="sxs-lookup"><span data-stu-id="72f85-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="72f85-133">Selecteer in de **productdetails De app downloaden.**</span><span class="sxs-lookup"><span data-stu-id="72f85-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="72f85-134">Microsoft Store voegt de app toe aan **Uw producten** voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="72f85-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="72f85-135">**Een synchronisatie forceer tussen Intune en Microsoft Store voor Bedrijven**</span><span class="sxs-lookup"><span data-stu-id="72f85-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="72f85-136">Meld u aan bij [het Microsoft Endpoint Manager-beheercentrum.](https://go.microsoft.com/fwlink/?linkid=2109431)</span><span class="sxs-lookup"><span data-stu-id="72f85-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="72f85-137">Selecteer **Tenantbeheer**  >  **connectors en tokens** Microsoft Store voor  >  **Bedrijven**.</span><span class="sxs-lookup"><span data-stu-id="72f85-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="72f85-138">Selecteer **Synchroniseren** om de apps die u hebt gekocht in de Microsoft Store in Intune te krijgen.</span><span class="sxs-lookup"><span data-stu-id="72f85-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="72f85-139">**Controleren of een synchronisatie tussen Intune en Microsoft Store voor Bedrijven actief is**</span><span class="sxs-lookup"><span data-stu-id="72f85-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="72f85-140">Meld u aan [bij de Microsoft Store voor Bedrijven met](https://businessstore.microsoft.com) uw Microsoft Store voor Bedrijven-account.</span><span class="sxs-lookup"><span data-stu-id="72f85-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="72f85-141">Selecteer **Beheren.**</span><span class="sxs-lookup"><span data-stu-id="72f85-141">Select **Manage**.</span></span>
3. <span data-ttu-id="72f85-142">Selecteer **Instellingen** en selecteer vervolgens **Distribueren.**</span><span class="sxs-lookup"><span data-stu-id="72f85-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="72f85-143">Controleer **onder Beheerhulpmiddelen** of Intune wordt vermeld en of de status **Actief** is.</span><span class="sxs-lookup"><span data-stu-id="72f85-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="72f85-144">Stap 2: Azure AD-groepen maken</span><span class="sxs-lookup"><span data-stu-id="72f85-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="72f85-145">Maak drie Azure AD-groepen voor elke app.</span><span class="sxs-lookup"><span data-stu-id="72f85-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="72f85-146">In deze tabel worden de groepen beschreven die u nodig hebt (Beschikbaar, Vereist en Verwijderen).</span><span class="sxs-lookup"><span data-stu-id="72f85-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="72f85-147">App-toewijzingstype</span><span class="sxs-lookup"><span data-stu-id="72f85-147">App assignment type</span></span> |    <span data-ttu-id="72f85-148">Groepsgebruik</span><span class="sxs-lookup"><span data-stu-id="72f85-148">Group use</span></span>    | <span data-ttu-id="72f85-149">Voorbeeld Azure AD-naam</span><span class="sxs-lookup"><span data-stu-id="72f85-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="72f85-150">Beschikbaar</span><span class="sxs-lookup"><span data-stu-id="72f85-150">Available</span></span> |  <span data-ttu-id="72f85-151">De app is beschikbaar via de bedrijfsportal-app of -website.</span><span class="sxs-lookup"><span data-stu-id="72f85-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="72f85-152">MMD – *naam van app* – Beschikbaar</span><span class="sxs-lookup"><span data-stu-id="72f85-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="72f85-153">Vereist</span><span class="sxs-lookup"><span data-stu-id="72f85-153">Required</span></span> |  <span data-ttu-id="72f85-154">De app is geïnstalleerd op apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="72f85-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="72f85-155">MMD – *naam van app* – Vereist</span><span class="sxs-lookup"><span data-stu-id="72f85-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="72f85-156">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="72f85-156">Uninstall</span></span> |  <span data-ttu-id="72f85-157">De app wordt verwijderd van apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="72f85-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="72f85-158">MMD – *naam van app* – Verwijderen</span><span class="sxs-lookup"><span data-stu-id="72f85-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="72f85-159">Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te maken, de app te installeren of de app te verwijderen van hun Microsoft Managed Desktop-apparaat.</span><span class="sxs-lookup"><span data-stu-id="72f85-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="72f85-160">Stap 3: Apps toewijzen aan uw gebruikers</span><span class="sxs-lookup"><span data-stu-id="72f85-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="72f85-161">**De app toewijzen aan uw gebruikers**</span><span class="sxs-lookup"><span data-stu-id="72f85-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="72f85-162">Meld u aan bij [de Microsoft Managed Desktop Admin Portal](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="72f85-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="72f85-163">Selecteer apps in het deelvenster Beheerd **bureaublad.**</span><span class="sxs-lookup"><span data-stu-id="72f85-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="72f85-164">Selecteer in de werkbelasting Apps de app aan wie u gebruikers wilt toewijzen en selecteer **Gebruikersgroepen toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="72f85-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="72f85-165">Selecteer voor de specifieke app een toewijzingstype (Beschikbaar, Vereist, Verwijderen) en wijs de juiste groep toe.</span><span class="sxs-lookup"><span data-stu-id="72f85-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="72f85-166">Selecteer OK in het deelvenster Apps **toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="72f85-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="72f85-167">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="72f85-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="72f85-168">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="72f85-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="72f85-169">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="72f85-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="72f85-170">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="72f85-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="72f85-171">Intune Company Portal implementeren</span><span class="sxs-lookup"><span data-stu-id="72f85-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="72f85-172">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="72f85-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="72f85-173">Apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="72f85-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="72f85-174">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="72f85-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="72f85-175">Apps implementeren (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="72f85-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->