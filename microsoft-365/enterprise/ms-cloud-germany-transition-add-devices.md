---
title: Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Overzicht: Aanvullende apparaatinformatie over services wanneer u van Microsoft Cloud Germany (Microsoft Cloud Deutschland) naar Office 365 services in de nieuwe Duitse datacenterregio gaat.'
ms.openlocfilehash: 1eb7b18360cefeeb2d5770c3d77e564d5a757a5e
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453565"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="7db10-103">Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="7db10-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="7db10-104">Verbonden en geregistreerde Azure AD-apparaten die zijn verbonden met Microsoft Cloud Deutschland, moeten worden gemigreerd na fase 9 en vóór fase 10.</span><span class="sxs-lookup"><span data-stu-id="7db10-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="7db10-105">De migratie van een apparaat is afhankelijk van het type apparaat, het besturingssysteem en de Azure AD-relatie.</span><span class="sxs-lookup"><span data-stu-id="7db10-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span>

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="7db10-106">Azure AD Joined Windows 10 apparaten</span><span class="sxs-lookup"><span data-stu-id="7db10-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="7db10-107">Als een Windows 10 Azure AD is gekoppeld, moet de verbinding met Azure AD zijn verbroken en opnieuw worden verbonden.</span><span class="sxs-lookup"><span data-stu-id="7db10-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span>

<span data-ttu-id="7db10-108">[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7db10-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="7db10-109">Als de gebruiker een beheerder is op het Windows 10 apparaat, kan de gebruiker de registratie van het apparaat uit Azure AD ongedaan maken en in drie stappen opnieuw deelnemen.</span><span class="sxs-lookup"><span data-stu-id="7db10-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="7db10-110">Stap 1: bepalen of het apparaat is verbonden met Azure-id</span><span class="sxs-lookup"><span data-stu-id="7db10-110">Step 1: Determine if the device is Azure ID joined</span></span>

1. <span data-ttu-id="7db10-111">Meld u aan met uw werkaccount.</span><span class="sxs-lookup"><span data-stu-id="7db10-111">Sign in with your work account.</span></span>
2. <span data-ttu-id="7db10-112">Ga naar **Instellingen**  >  **Accounts**  >  **Access Work Or School**.</span><span class="sxs-lookup"><span data-stu-id="7db10-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="7db10-113">Zoek naar een account in de lijst met **verbonden met [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="7db10-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span>
4. <span data-ttu-id="7db10-114">Als er een verbonden account bestaat, gaat u verder met stap 2.</span><span class="sxs-lookup"><span data-stu-id="7db10-114">If a connected account exists, proceed with Step 2.</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="7db10-115">Stap 2: Het apparaat loskoppelen van Azure AD</span><span class="sxs-lookup"><span data-stu-id="7db10-115">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="7db10-116">Klik **op Loskoppelen** op het verbonden werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="7db10-116">Click **Disconnect** on the connected work or School Account.</span></span>
2. <span data-ttu-id="7db10-117">Bevestig de verbinding tweemaal.</span><span class="sxs-lookup"><span data-stu-id="7db10-117">Confirm the disconnect twice.</span></span>
3. <span data-ttu-id="7db10-118">Voer een gebruikersnaam en wachtwoord van een lokale beheerder in.</span><span class="sxs-lookup"><span data-stu-id="7db10-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="7db10-119">Het apparaat is losgekoppeld.</span><span class="sxs-lookup"><span data-stu-id="7db10-119">The device is disconnected.</span></span>
4. <span data-ttu-id="7db10-120">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="7db10-120">Restart the device.</span></span>

### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="7db10-121">Stap 3: Deelnemen aan het apparaat aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="7db10-121">Step 3: Join the device to Azure AD</span></span>

1. <span data-ttu-id="7db10-122">Meld u aan met de referenties van de lokale beheerder.</span><span class="sxs-lookup"><span data-stu-id="7db10-122">Sign in with the credentials of the local administrator.</span></span>
2. <span data-ttu-id="7db10-123">Ga naar **Instellingen**  >  **Accounts**  >  **Access Work Or School**.</span><span class="sxs-lookup"><span data-stu-id="7db10-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="7db10-124">Klik op **Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="7db10-124">Click **Connect**.</span></span>
4. <span data-ttu-id="7db10-125">**BELANGRIJK:** Klik op **Deelnemen aan Azure AD.**</span><span class="sxs-lookup"><span data-stu-id="7db10-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5. <span data-ttu-id="7db10-126">Voer het e-mailadres en wachtwoord van uw werkaccount in.</span><span class="sxs-lookup"><span data-stu-id="7db10-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="7db10-127">Het apparaat is verbonden.</span><span class="sxs-lookup"><span data-stu-id="7db10-127">The device is connected.</span></span>
6. <span data-ttu-id="7db10-128">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="7db10-128">Restart the device.</span></span>
7. <span data-ttu-id="7db10-129">Meld u aan met het e-mailadres en wachtwoord van uw werkaccount.</span><span class="sxs-lookup"><span data-stu-id="7db10-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="7db10-130">Als de gebruiker geen beheerder van het apparaat is, kan een globale beheerder van Azure AD het lokale beheerdersaccount op het apparaat maken na dit configuratiepad en het apparaat ontvoegen:</span><span class="sxs-lookup"><span data-stu-id="7db10-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="7db10-131">*Instellingen > Accounts > Andere accounts > referenties onbekend > Gebruiker toevoegen zonder Microsoft-account*</span><span class="sxs-lookup"><span data-stu-id="7db10-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="7db10-132">Als u opnieuw wilt deelnemen, kunnen de referenties van een werkaccount van uw organisatie in deze stap worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7db10-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span>

<span data-ttu-id="7db10-133">Houd er rekening mee dat het werkaccount dat wordt gebruikt om deel te nemen aan het apparaat automatisch wordt gepromoveerd als beheerder van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="7db10-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="7db10-134">Elk ander werkaccount van de organisatie kan zich aanmelden bij het apparaat, maar heeft geen beheerdersbevoegdheden.</span><span class="sxs-lookup"><span data-stu-id="7db10-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="7db10-135">Azure AD-geregistreerde (werkplek-verbonden) Windows 10 apparaten</span><span class="sxs-lookup"><span data-stu-id="7db10-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>

<span data-ttu-id="7db10-136">Als een Windows 10 Azure AD is geregistreerd, moet dit worden losgekoppeld van de Azure AD en opnieuw worden verbonden.</span><span class="sxs-lookup"><span data-stu-id="7db10-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="7db10-137">[![Azure AD Device Re-Registration Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="7db10-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="7db10-138">Stap 1: bepalen of het apparaat is geregistreerd als Azure-id</span><span class="sxs-lookup"><span data-stu-id="7db10-138">Step 1: Determine if the device is Azure ID registered</span></span>

1. <span data-ttu-id="7db10-139">Meld u aan met uw gebruiker.</span><span class="sxs-lookup"><span data-stu-id="7db10-139">Sign in with your user.</span></span>
2. <span data-ttu-id="7db10-140">Ga naar **Instellingen**  >  **Accounts**  >  **Access Work Or School**.</span><span class="sxs-lookup"><span data-stu-id="7db10-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="7db10-141">Ontdek uw werkaccount in de lijst en controleer of het is **verbonden met [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="7db10-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="7db10-142">Als uw werkaccount in de lijst staat, maar niet is verbonden met een Azure AD, gaat u verder met stap 2.</span><span class="sxs-lookup"><span data-stu-id="7db10-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="7db10-143">Anders is uw apparaat een apparaat dat deel uit maakt van Azure AD en moet u verwijzen naar [Azure AD Joined Windows 10 apparaten.](#azure-ad-joined-windows-10-devices)</span><span class="sxs-lookup"><span data-stu-id="7db10-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="7db10-144">Stap 2: Het apparaat loskoppelen van Azure AD</span><span class="sxs-lookup"><span data-stu-id="7db10-144">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="7db10-145">Klik op uw werkaccount.</span><span class="sxs-lookup"><span data-stu-id="7db10-145">Click on your work account.</span></span> <span data-ttu-id="7db10-146">De knoppen *Info* en *Loskoppelen worden* weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7db10-146">The buttons *Info* and *Disconnect* appear.</span></span>
2. <span data-ttu-id="7db10-147">Klik **op Loskoppelen.**</span><span class="sxs-lookup"><span data-stu-id="7db10-147">Click **Disconnect**.</span></span>
3. <span data-ttu-id="7db10-148">Bevestig accountverwijdering van het apparaat door op Ja **te klikken.**</span><span class="sxs-lookup"><span data-stu-id="7db10-148">Confirm account removal from the device by clicking **Yes**.</span></span>

### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="7db10-149">Stap 3: Verbinding maken naar Azure AD</span><span class="sxs-lookup"><span data-stu-id="7db10-149">Step 3: Connect the device to Azure AD</span></span>

1. <span data-ttu-id="7db10-150">Klik op **Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="7db10-150">Click **Connect**.</span></span>
2. <span data-ttu-id="7db10-151">Voer het e-mailadres van uw werkaccount in en klik op **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="7db10-151">Enter the email address of your work account and click **Next**.</span></span>
3. <span data-ttu-id="7db10-152">Voer het wachtwoord van uw werkaccount in en klik **op Aanmelden.**</span><span class="sxs-lookup"><span data-stu-id="7db10-152">Enter the password of your work account and click **Sign in**.</span></span>
4. <span data-ttu-id="7db10-153">Bevestig door op Klaar **te klikken.**</span><span class="sxs-lookup"><span data-stu-id="7db10-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="7db10-154">Uw werkaccount wordt opnieuw weergegeven.</span><span class="sxs-lookup"><span data-stu-id="7db10-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="7db10-155">Android</span><span class="sxs-lookup"><span data-stu-id="7db10-155">Android</span></span>

<span data-ttu-id="7db10-156">Voor Android moeten gebruikers de registratie van hun apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="7db10-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="7db10-157">Dit kan via de Microsoft Authenticator app of de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="7db10-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span>

- <span data-ttu-id="7db10-158">Vanuit de Microsoft Authenticator app kunnen gebruikers naar Instellingen > **Apparaatregistratie** gaan.</span><span class="sxs-lookup"><span data-stu-id="7db10-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="7db10-159">Van hieruit kunnen gebruikers hun registratie ongedaan maken en hun apparaat opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="7db10-159">From there users can unregister and re-register their device.</span></span>

- <span data-ttu-id="7db10-160">Vanuit de Bedrijfsportal kunnen gebruikers naar het **tabblad** Apparaten gaan en het apparaat verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7db10-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="7db10-161">Daarna kunt u het apparaat opnieuw registreren met behulp van Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="7db10-161">After that, re-enroll the device by using Company Portal.</span></span>

- <span data-ttu-id="7db10-162">Gebruikers kunnen zich ook afmelden en opnieuw registreren door het account te verwijderen van de pagina accountinstellingen en vervolgens het werkaccount opnieuw toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="7db10-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="7db10-163">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren met de Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="7db10-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1. <span data-ttu-id="7db10-164">Open de Microsoft Authenticator app en ga naar **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="7db10-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2. <span data-ttu-id="7db10-165">Selecteer **Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="7db10-165">Select **Device registration**.</span></span>
3. <span data-ttu-id="7db10-166">De registratie van het apparaat ongedaan maken door **Afmelden te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="7db10-166">Unregister the device by selecting **Unregister**.</span></span>
4. <span data-ttu-id="7db10-167">Voor **apparaatregistratie,** moet u het apparaat opnieuw registreren door uw e-mailadres te typen en vervolgens **Registreren te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="7db10-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="7db10-168">Een Android-apparaat op de pagina Android-Instellingen opnieuw registreren:</span><span class="sxs-lookup"><span data-stu-id="7db10-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1. <span data-ttu-id="7db10-169">Open **Apparaat Instellingen** en ga naar **Accounts.**</span><span class="sxs-lookup"><span data-stu-id="7db10-169">Open **Device Settings** and go to **Accounts**.</span></span>
2. <span data-ttu-id="7db10-170">Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **Account verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="7db10-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3. <span data-ttu-id="7db10-171">Nadat het account is verwijderd, selecteert u op de **pagina Accounts** de optie Account toevoegen **> werkaccount.**</span><span class="sxs-lookup"><span data-stu-id="7db10-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4. <span data-ttu-id="7db10-172">Voor **Workplace Join** typt u uw e-mailadres en **selecteert** u Deelnemen om de registratie van het apparaat te voltooien.</span><span class="sxs-lookup"><span data-stu-id="7db10-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="7db10-173">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren Bedrijfsportal:</span><span class="sxs-lookup"><span data-stu-id="7db10-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1. <span data-ttu-id="7db10-174">Start Bedrijfsportal en ga naar **het tabblad** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="7db10-174">Launch Company Portal and go to **Devices** tab.</span></span>
2. <span data-ttu-id="7db10-175">Selecteer het apparaat om de apparaatdetails te bekijken.</span><span class="sxs-lookup"><span data-stu-id="7db10-175">Select the device to see the device details.</span></span>
3. <span data-ttu-id="7db10-176">Selecteer apparaat verwijderen in het menu drie puntjes (drie puntjes) en voltooi de verwijdering door dit te bevestigen in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="7db10-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4. <span data-ttu-id="7db10-177">U moet nu zijn afgemeld bij de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="7db10-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="7db10-178">Selecteer **Aanmelden om** het apparaat opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="7db10-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="7db10-179">Bekijk de informatie over Azure Active Directory (Azure AD) in Aanvullende Azure AD-informatie voor de migratie van [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over acties die nodig zijn tijdens de migratiefase van deze werkbelasting of de gevolgen voor beheer of gebruik.</span><span class="sxs-lookup"><span data-stu-id="7db10-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="7db10-180">iOS</span><span class="sxs-lookup"><span data-stu-id="7db10-180">iOS</span></span>

<span data-ttu-id="7db10-181">Op iOS-apparaten moet een gebruiker accounts in de cache handmatig verwijderen uit de Microsoft Authenticator, het apparaat uitschrijven en zich afmelden bij native apps op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="7db10-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="7db10-182">Stap 1: Als u aanwezig bent, verwijdert u het account uit de Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="7db10-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="7db10-183">Tik op het account in de Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="7db10-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="7db10-184">Tik op **Instellingen** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="7db10-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="7db10-185">Als u het pictogram  Instellingen niet ziet, gebruikt u mogelijk niet de nieuwste versie van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="7db10-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="7db10-186">Tik op **de knop Account** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7db10-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="7db10-187">Tik **op Alle apps op dit apparaat.**</span><span class="sxs-lookup"><span data-stu-id="7db10-187">Tap **All apps on this device**.</span></span>

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="7db10-188">Stap 2: Het apparaat uit de app Microsoft Authenticator verwijderen</span><span class="sxs-lookup"><span data-stu-id="7db10-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="7db10-189">Tik op het menupictogram in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="7db10-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="7db10-190">Tik **Instellingen** en vervolgens **op Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="7db10-190">Tap **Settings** and then **Device Registration**.</span></span>
3. <span data-ttu-id="7db10-191">Als uw account wordt weergegeven, tikt u **op Apparaat afmelden** en **doorgaan** in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="7db10-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="7db10-192">Daarna ziet u geen account meer.</span><span class="sxs-lookup"><span data-stu-id="7db10-192">You should see no account after that.</span></span>

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="7db10-193">Stap 3: Meld u indien nodig af bij afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="7db10-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="7db10-194">Gebruikers kunnen naar afzonderlijke apps gaan, zoals Outlook, Teams en OneDrive en accounts uit die apps verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7db10-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="7db10-195">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="7db10-195">Frequently asked questions</span></span>

<span data-ttu-id="7db10-196">**Hoe weet ik of mijn organisatie is beïnvloed?**</span><span class="sxs-lookup"><span data-stu-id="7db10-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="7db10-197">Beheerders moeten controleren of ze azure AD-geregistreerde of `https://portal.microsoftazure.de` Azure AD-apparaten hebben.</span><span class="sxs-lookup"><span data-stu-id="7db10-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="7db10-198">Als uw organisatie azure AD-geregistreerde of Azure AD-apparaten heeft, moet uw organisatie de instructies op deze pagina volgen.</span><span class="sxs-lookup"><span data-stu-id="7db10-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="7db10-199">**Wanneer registreren mijn gebruikers hun apparaten opnieuw?**</span><span class="sxs-lookup"><span data-stu-id="7db10-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="7db10-200">Het is essentieel voor uw succes dat u uw apparaten alleen uitschrijft en opnieuw registreert nadat [fase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="7db10-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="7db10-201">U moet de herregistratie voltooien voordat fase 10 wordt gestart, anders hebt u geen toegang meer tot uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="7db10-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="7db10-202">**Hoe weet ik dat al mijn apparaten zijn geregistreerd in de openbare cloud?**</span><span class="sxs-lookup"><span data-stu-id="7db10-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="7db10-203">Als u wilt controleren of uw apparaten zijn geregistreerd in de openbare cloud, moet u de lijst met apparaten exporteren en downloaden van de Azure AD-portal naar een Excel spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="7db10-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="7db10-204">Filter vervolgens de apparaten die zijn geregistreerd (met behulp van de kolom _registeredTime)_ na de datum waarop uw organisatie fase 9 van het [migratieproces heeft doorlopen.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="7db10-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

<span data-ttu-id="7db10-205">**Moet ik nog steeds de DNS-naam toevoegen zoals aangegeven in [DNS-records voor Microsoft maken](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)met Windows dns?**</span><span class="sxs-lookup"><span data-stu-id="7db10-205">**Do I still need to add the DNS name as stated in [Create DNS records for Microsoft using Windows-based DNS](/microsoft-365/admin/dns/create-dns-records-using-windows-based-dns?view=o365-worldwide#add-two-cname-records-for-mobile-device-management-mdm-for-microsoft)?**</span></span>

<span data-ttu-id="7db10-206">Deze DNS-vermelding is niet meer nodig voor het opnieuw registreren van uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="7db10-206">This DNS entry is no longer needed for re-registering your device.</span></span> 

## <a name="additional-considerations"></a><span data-ttu-id="7db10-207">Aanvullende overwegingen</span><span class="sxs-lookup"><span data-stu-id="7db10-207">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7db10-208">De Intune-service principal wordt ingeschakeld na [fase 3 van](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)het migratieproces, wat de activering van Azure AD Device Registration impliceert.</span><span class="sxs-lookup"><span data-stu-id="7db10-208">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="7db10-209">Als u Azure AD Device Registration vóór de migratie hebt geblokkeerd, moet u de Intune-service principal met PowerShell uitschakelen om Azure AD Device Registration weer uit te schakelen met de Azure AD-portal.</span><span class="sxs-lookup"><span data-stu-id="7db10-209">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="7db10-210">U kunt de Intune-service principal uitschakelen met deze opdracht in Azure Active Directory PowerShell voor Graph module.</span><span class="sxs-lookup"><span data-stu-id="7db10-210">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="7db10-211">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="7db10-211">More information</span></span>

<span data-ttu-id="7db10-212">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="7db10-212">Getting started:</span></span>

- [<span data-ttu-id="7db10-213">Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's</span><span class="sxs-lookup"><span data-stu-id="7db10-213">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="7db10-214">Microsoft Cloud Deutschland-migratiehulp</span><span class="sxs-lookup"><span data-stu-id="7db10-214">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="7db10-215">Opt-in voor migratie</span><span class="sxs-lookup"><span data-stu-id="7db10-215">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="7db10-216">Klantervaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="7db10-216">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="7db10-217">Door de overgang lopen:</span><span class="sxs-lookup"><span data-stu-id="7db10-217">Moving through the transition:</span></span>

- [<span data-ttu-id="7db10-218">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="7db10-218">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="7db10-219">Extra pre-work</span><span class="sxs-lookup"><span data-stu-id="7db10-219">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="7db10-220">Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="7db10-220">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="7db10-221">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="7db10-221">Cloud apps:</span></span>

- [<span data-ttu-id="7db10-222">Dynamics 365-migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="7db10-222">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="7db10-223">Power BI migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="7db10-223">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="7db10-224">Aan de slag met uw Microsoft Teams upgrade</span><span class="sxs-lookup"><span data-stu-id="7db10-224">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
