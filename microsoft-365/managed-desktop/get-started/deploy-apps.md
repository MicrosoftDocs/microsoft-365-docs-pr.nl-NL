---
title: Apps implementeren op apparaten
description: Informatie over het toevoegen en implementeren van apps aan Microsoft beheerde bureaublad apparaten.
keywords: Microsoft Managed Desktop, Microsoft 365, service, Documentatie, apps, line-of-Business-Apps, LOB-apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769104"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="6395c-104">Apps implementeren op apparaten</span><span class="sxs-lookup"><span data-stu-id="6395c-104">Deploy apps to devices</span></span>
<span data-ttu-id="6395c-105">Een onderdeel van onboarding voor Microsoft Managed Desktop bevat het toevoegen en implementeren van apps aan de apparaten van uw gebruikers.</span><span class="sxs-lookup"><span data-stu-id="6395c-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="6395c-106">Wanneer u de Microsoft beheerde bureaublad Portal gebruikt, kunt u uw apps toevoegen en implementeren.</span><span class="sxs-lookup"><span data-stu-id="6395c-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="6395c-107">Het algehele proces ziet er als volgt uit:</span><span class="sxs-lookup"><span data-stu-id="6395c-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="6395c-108">[Apps toevoegen aan de beheerde bureaublad portal van Microsoft](#1) : dit kan bestaan uit bestaande LOB-apps (line-of-Business), of apps uit Microsoft Store voor bedrijven die u met intune hebt gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="6395c-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="6395c-109">[Azure Active Directory (AD) groepen maken voor app-toewijzing](#2) : u gebruikt deze groepen om de app-toewijzing te beheren.</span><span class="sxs-lookup"><span data-stu-id="6395c-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="6395c-110">Apps aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="6395c-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="6395c-111">Stap 1: apps toevoegen aan de beheerde bureaublad portal van Microsoft</span><span class="sxs-lookup"><span data-stu-id="6395c-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="6395c-112">U kunt [Win32-of Windows MSI-](#lob-apps)apps of [Microsoft Store for Business-Apps](#msfb-apps) toevoegen aan het Microsoft-beheer bureaublad en ze vervolgens implementeren op Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="6395c-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="6395c-113">Win32-of Windows MSI-apps op basis van de Microsoft beheerde bureaubladversie</span><span class="sxs-lookup"><span data-stu-id="6395c-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="6395c-114">U kunt uw LOB-apps (line-of-Business) toevoegen aan de beheerde bureaublad portal van Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6395c-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="6395c-115">Zie vereisten voor de [beheerde bureaublad-app](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)voor meer informatie over de vereisten voor apps die zijn geïnstalleerd op Microsoft beheerde bureaublad apparaten.</span><span class="sxs-lookup"><span data-stu-id="6395c-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="6395c-116">Bij deze procedure selecteert u het type app dat u wilt toevoegen en vervolgens configureert en uploadt u de app-bron.</span><span class="sxs-lookup"><span data-stu-id="6395c-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="6395c-117">**Uw LOB-app of Windows-app toevoegen aan de beheerde bureaublad portal van Microsoft**</span><span class="sxs-lookup"><span data-stu-id="6395c-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="6395c-118">U kunt zich aanmelden bij Microsoft beheerde bureaublad Portal, of u kunt zich aanmelden bij intune en vervolgens zoeken naar Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6395c-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="6395c-119">We tonen het aanmelden bij Microsoft beheerde bureaublad Portal.</span><span class="sxs-lookup"><span data-stu-id="6395c-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="6395c-120">Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="6395c-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="6395c-121">Selecteer onder **voorraad** **apps** .</span><span class="sxs-lookup"><span data-stu-id="6395c-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="6395c-122">Selecteer **toevoegen** in de apps-werkbelasting.</span><span class="sxs-lookup"><span data-stu-id="6395c-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="6395c-123">Selecteer in **app toevoegen** de optie **line-of-Business** of **Windows-app (Win32)** .</span><span class="sxs-lookup"><span data-stu-id="6395c-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="6395c-124">Als u een **line-of-Business-app** hebt geselecteerd, raadpleegt u [een Windows line-of-Business-app toevoegen aan Microsoft intune](https://docs.microsoft.com/intune/lob-apps-windows) voor instructies over het toevoegen en configureren van line-of-Business-Apps.</span><span class="sxs-lookup"><span data-stu-id="6395c-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="6395c-125">Als u **Windows-app (Win32)** hebt geselecteerd, raadpleegt u [Win32 app Management](https://docs.microsoft.com/intune/apps-win32-app-management) for instructies over het toevoegen en configureren van Windows-apps.</span><span class="sxs-lookup"><span data-stu-id="6395c-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="6395c-126">Apps voor Microsoft Store voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="6395c-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="6395c-127">Als u zich nog niet hebt aangemeld bij Microsoft Store voor bedrijven, kunt u zich registreren wanneer u voor apps moet winkelen.</span><span class="sxs-lookup"><span data-stu-id="6395c-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="6395c-128">Wanneer u uw apps hebt, kunt u deze synchroniseren met Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="6395c-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="6395c-129">**Apps kopen in de Microsoft Store voor bedrijven**</span><span class="sxs-lookup"><span data-stu-id="6395c-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="6395c-130">Meld u aan bij [Microsoft Store voor bedrijven](https://businessstore.microsoft.com) met uw beheerdersaccount voor Microsoft Store voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="6395c-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="6395c-131">Selecteer **winkel voor mijn groep** .</span><span class="sxs-lookup"><span data-stu-id="6395c-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="6395c-132">Gebruik de zoekfunctie om de gewenste app te vinden en selecteer de app.</span><span class="sxs-lookup"><span data-stu-id="6395c-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="6395c-133">Selecteer op de productgegevens **de optie Get the app** .</span><span class="sxs-lookup"><span data-stu-id="6395c-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="6395c-134">Microsoft Store voegt de app toe aan **uw producten** voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6395c-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="6395c-135">**Een synchronisatie tussen intune en Microsoft Store voor bedrijven afdwingen**</span><span class="sxs-lookup"><span data-stu-id="6395c-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="6395c-136">Meld u aan bij het [Beheercentrum van Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).</span><span class="sxs-lookup"><span data-stu-id="6395c-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="6395c-137">Selecteer **Tenant beheer**  >  **connectors en tokens**  >  **Microsoft Store voor bedrijven** .</span><span class="sxs-lookup"><span data-stu-id="6395c-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="6395c-138">Selecteer **synchroniseren** om de apps die u in de Microsoft Store hebt gekocht, op te downloaden in intune.</span><span class="sxs-lookup"><span data-stu-id="6395c-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="6395c-139">**Controleren of een synchronisatie tussen intune en Microsoft Store voor bedrijven actief is**</span><span class="sxs-lookup"><span data-stu-id="6395c-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="6395c-140">Meld u aan bij [Microsoft Store voor bedrijven](https://businessstore.microsoft.com) met uw beheerdersaccount voor Microsoft Store voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="6395c-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="6395c-141">Selecteer **beheren** .</span><span class="sxs-lookup"><span data-stu-id="6395c-141">Select **Manage** .</span></span>
3. <span data-ttu-id="6395c-142">Selecteer **instellingen** en selecteer **verdelen** .</span><span class="sxs-lookup"><span data-stu-id="6395c-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="6395c-143">Controleer onder **beheerprogramma's** of intune wordt weergegeven en of de status **actief** is.</span><span class="sxs-lookup"><span data-stu-id="6395c-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="6395c-144">Stap 2: Azure AD-groepen maken</span><span class="sxs-lookup"><span data-stu-id="6395c-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="6395c-145">Maak drie Azure AD-groepen voor elke app.</span><span class="sxs-lookup"><span data-stu-id="6395c-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="6395c-146">In deze tabel vindt u een overzicht van de groepen die u nodig hebt (beschikbaar, vereist en verwijderen).</span><span class="sxs-lookup"><span data-stu-id="6395c-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="6395c-147">Type app-toewijzing</span><span class="sxs-lookup"><span data-stu-id="6395c-147">App assignment type</span></span> |    <span data-ttu-id="6395c-148">Groepsgebruik</span><span class="sxs-lookup"><span data-stu-id="6395c-148">Group use</span></span>    | <span data-ttu-id="6395c-149">Voorbeeld van Azure AD naam</span><span class="sxs-lookup"><span data-stu-id="6395c-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="6395c-150">Beschikbaar</span><span class="sxs-lookup"><span data-stu-id="6395c-150">Available</span></span> |  <span data-ttu-id="6395c-151">De app is beschikbaar in de bedrijfs portal-app of-website.</span><span class="sxs-lookup"><span data-stu-id="6395c-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="6395c-152">MMD – *app-naam* – beschikbaar</span><span class="sxs-lookup"><span data-stu-id="6395c-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="6395c-153">Vereist</span><span class="sxs-lookup"><span data-stu-id="6395c-153">Required</span></span> |  <span data-ttu-id="6395c-154">De app is geïnstalleerd op apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="6395c-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="6395c-155">MMD – *app-naam* – vereist</span><span class="sxs-lookup"><span data-stu-id="6395c-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="6395c-156">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="6395c-156">Uninstall</span></span> |  <span data-ttu-id="6395c-157">De app wordt verwijderd van apparaten in de geselecteerde groepen.</span><span class="sxs-lookup"><span data-stu-id="6395c-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="6395c-158">MMD – *app-naam* – verwijderen</span><span class="sxs-lookup"><span data-stu-id="6395c-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="6395c-159">Voeg uw gebruikers toe aan deze groepen om de app beschikbaar te maken, de app te installeren of de app te verwijderen van het Microsoft-beheerapparaat.</span><span class="sxs-lookup"><span data-stu-id="6395c-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="6395c-160">Stap 3: apps aan uw gebruikers toewijzen</span><span class="sxs-lookup"><span data-stu-id="6395c-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="6395c-161">**De app toewijzen aan uw gebruikers**</span><span class="sxs-lookup"><span data-stu-id="6395c-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="6395c-162">Meld u aan bij de [Portal van Microsoft beheerde bureaubladbeheer](https://aka.ms/mmdportal).</span><span class="sxs-lookup"><span data-stu-id="6395c-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="6395c-163">Selecteer **apps** in het deelvenster beheerde bureaubladversie.</span><span class="sxs-lookup"><span data-stu-id="6395c-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="6395c-164">Selecteer in de apps op de app waaraan u gebruikers wilt toewijzen en selecteer **gebruikersgroepen toewijzen** .</span><span class="sxs-lookup"><span data-stu-id="6395c-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="6395c-165">Selecteer voor de specifieke app een type toewijzing (beschikbaar, vereist, verwijderen) en wijs de juiste groep toe.</span><span class="sxs-lookup"><span data-stu-id="6395c-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="6395c-166">Selecteer in het deelvenster apps toewijzen de optie **OK** .</span><span class="sxs-lookup"><span data-stu-id="6395c-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="6395c-167">Stappen om aan de slag te gaan met Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="6395c-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="6395c-168">Contactpersonen voor beheer toevoegen en verifiëren in de beheerportal</span><span class="sxs-lookup"><span data-stu-id="6395c-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="6395c-169">Voorwaardelijke toegang aanpassen</span><span class="sxs-lookup"><span data-stu-id="6395c-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="6395c-170">Licenties toewijzen</span><span class="sxs-lookup"><span data-stu-id="6395c-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="6395c-171">Intune Company Portal implementeren</span><span class="sxs-lookup"><span data-stu-id="6395c-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="6395c-172">Enterprise State Roaming inschakelen</span><span class="sxs-lookup"><span data-stu-id="6395c-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="6395c-173">Apparaten instellen</span><span class="sxs-lookup"><span data-stu-id="6395c-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="6395c-174">Uw gebruikers voorbereiden om apparaten te gebruiken</span><span class="sxs-lookup"><span data-stu-id="6395c-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="6395c-175">Apps implementeren (dit onderwerp)</span><span class="sxs-lookup"><span data-stu-id="6395c-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
