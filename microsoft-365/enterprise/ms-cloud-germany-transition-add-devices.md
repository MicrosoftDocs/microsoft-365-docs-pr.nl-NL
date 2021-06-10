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
ms.openlocfilehash: 27426a26befab85bf62a0a143861e447dd722724
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861300"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="ff457-103">Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="ff457-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="ff457-104">Verbonden en geregistreerde Azure AD-apparaten die zijn verbonden met Microsoft Cloud Deutschland, moeten worden gemigreerd na fase 9 en vóór fase 10.</span><span class="sxs-lookup"><span data-stu-id="ff457-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="ff457-105">De migratie van een apparaat is afhankelijk van het type apparaten, het besturingssysteem en de AAD-relatie.</span><span class="sxs-lookup"><span data-stu-id="ff457-105">The migration of a device depends on the devices type, operating system and AAD relation.</span></span> 

## <a name="frequently-asked-questions"></a><span data-ttu-id="ff457-106">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="ff457-106">Frequently asked questions</span></span>

<span data-ttu-id="ff457-107">**Hoe weet ik of mijn organisatie is beïnvloed?**</span><span class="sxs-lookup"><span data-stu-id="ff457-107">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="ff457-108">Beheerders moeten controleren of ze geregistreerde of `https://portal.microsoftazure.de` Azure AD-apparaten hebben.</span><span class="sxs-lookup"><span data-stu-id="ff457-108">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered or Azure AD joined devices.</span></span> <span data-ttu-id="ff457-109">Als uw organisatie geregistreerde apparaten heeft, is dit van invloed op u.</span><span class="sxs-lookup"><span data-stu-id="ff457-109">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="ff457-110">**Wat zijn de gevolgen voor mijn gebruikers?**</span><span class="sxs-lookup"><span data-stu-id="ff457-110">**What is the impact on my users?**</span></span>

<span data-ttu-id="ff457-111">Gebruikers van een geregistreerd apparaat kunnen zich niet meer aanmelden nadat [migratiefase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) is voltooid en de eindpunten voor Microsoft Cloud Deutschland zijn uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff457-111">Users from a registered device will no longer be able to sign in after [migration phase 10](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed and the endpoints for Microsoft Cloud Deutschland have been disabled.</span></span>  

<span data-ttu-id="ff457-112">Zorg ervoor dat al uw apparaten zijn geregistreerd bij het wereldwijde eindpunt voordat uw organisatie is losgekoppeld van Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="ff457-112">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="ff457-113">**Wanneer registreren mijn gebruikers hun apparaten opnieuw?**</span><span class="sxs-lookup"><span data-stu-id="ff457-113">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="ff457-114">Het is essentieel voor uw succes dat u uw apparaten alleen uitschrijft en opnieuw registreert nadat [fase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) is voltooid.</span><span class="sxs-lookup"><span data-stu-id="ff457-114">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="ff457-115">U moet de herregistratie voltooien voordat fase 10 wordt gestart, anders hebt u geen toegang meer tot uw apparaat.</span><span class="sxs-lookup"><span data-stu-id="ff457-115">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="ff457-116">**Hoe herstel ik de status van mijn apparaat na de migratie?**</span><span class="sxs-lookup"><span data-stu-id="ff457-116">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="ff457-117">Voor bedrijfsapparaten Windows die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via op afstand geactiveerde werkstromen die de registratie van de oude apparaatstatussen ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="ff457-117">For company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="ff457-118">Voor alle andere apparaten, waaronder persoonlijke apparaten Windows die zijn geregistreerd in Azure AD, moet de eindgebruiker deze stappen handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="ff457-118">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="ff457-119">Voor apparaten die zijn verbonden met Azure AD, moeten gebruikers een lokaal beheerdersaccount hebben om de registratie uit te schrijven en vervolgens hun apparaten opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="ff457-119">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="ff457-120">Raadpleeg hieronder gedetailleerde instructies voor het herstellen van apparaatstaten.</span><span class="sxs-lookup"><span data-stu-id="ff457-120">Please refer to detailed instructions for how to successfully restore device states below.</span></span> 
 
<span data-ttu-id="ff457-121">**Hoe weet ik dat al mijn apparaten zijn geregistreerd in de openbare cloud?**</span><span class="sxs-lookup"><span data-stu-id="ff457-121">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="ff457-122">Als u wilt controleren of uw apparaten zijn geregistreerd in de openbare cloud, moet u de lijst met apparaten exporteren en downloaden van de Azure AD-portal naar een Excel spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="ff457-122">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="ff457-123">Filter vervolgens de apparaten die zijn geregistreerd (met behulp van de kolom _registeredTime)_ na de migratiefase Scheiden [van Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="ff457-123">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="ff457-124">Aanvullende overwegingen</span><span class="sxs-lookup"><span data-stu-id="ff457-124">Additional considerations</span></span>
<span data-ttu-id="ff457-125">Apparaatregistratie wordt gedeactiveerd na de migratie van de tenant en kan niet worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ff457-125">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> 

<span data-ttu-id="ff457-126">Als Intune niet wordt gebruikt, meld u dan aan bij uw abonnement en voer deze opdracht uit om de optie opnieuw te activeren:</span><span class="sxs-lookup"><span data-stu-id="ff457-126">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```
<span data-ttu-id="ff457-127">**BELANGRIJK:** De Intune-service principal wordt ingeschakeld na de migratie van commerce, wat de activering van Azure AD Device Registration impliceert.</span><span class="sxs-lookup"><span data-stu-id="ff457-127">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="ff457-128">Als u Azure AD Device Registration vóór de migratie hebt geblokkeerd, moet u de Intune-service principal met PowerShell uitschakelen om Azure AD Device Registration weer uit te schakelen met de Azure AD-portal.</span><span class="sxs-lookup"><span data-stu-id="ff457-128">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="ff457-129">U kunt de Intune-service principal uitschakelen met deze opdracht in Azure Active Directory PowerShell voor Graph module.</span><span class="sxs-lookup"><span data-stu-id="ff457-129">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```


## <a name="azure-ad-join"></a><span data-ttu-id="ff457-130">Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="ff457-130">Azure AD Join</span></span>
<span data-ttu-id="ff457-131">Dit geldt voor Windows 10 apparaten.</span><span class="sxs-lookup"><span data-stu-id="ff457-131">This applies to Windows 10 devices.</span></span> 

<span data-ttu-id="ff457-132">Als een apparaat is gekoppeld aan Azure AD, moet de verbinding met Azure AD zijn verbroken en opnieuw worden verbonden.</span><span class="sxs-lookup"><span data-stu-id="ff457-132">If a device is Azure AD joined, it must be disconnected from Azure AD and be connected again.</span></span> 

<span data-ttu-id="ff457-133">[![Azure AD Device Re-Join Flow ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png)](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ff457-133">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="ff457-134">Als de gebruiker een beheerder is op het Windows 10 apparaat, kan de gebruiker de registratie van het apparaat uit Azure AD ongedaan maken en opnieuw deelnemen.</span><span class="sxs-lookup"><span data-stu-id="ff457-134">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again.</span></span> <span data-ttu-id="ff457-135">Als hij geen beheerdersbevoegdheden heeft, heeft de gebruiker referenties nodig van een lokaal beheerdersaccount op deze computer.</span><span class="sxs-lookup"><span data-stu-id="ff457-135">If he has no administrator privileges, the user needs credentials of a local administrator account on this machine.</span></span> 


<span data-ttu-id="ff457-136">Een beheerder kan een lokaal beheerdersaccount op het apparaat maken op basis van dit configuratiepad:</span><span class="sxs-lookup"><span data-stu-id="ff457-136">An Administrator can create an local administrator account on the device following this configuration path:</span></span>

<span data-ttu-id="ff457-137">*Instellingen > Accounts > Andere accounts > referenties onbekend > Gebruiker toevoegen zonder Microsoft-account*</span><span class="sxs-lookup"><span data-stu-id="ff457-137">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="ff457-138">Stap 1: bepalen of het apparaat is verbonden met Azure-id</span><span class="sxs-lookup"><span data-stu-id="ff457-138">Step 1: Determine if the device is Azure ID joined</span></span>
1.  <span data-ttu-id="ff457-139">Meld u aan met e-mail en wachtwoord van gebruikers.</span><span class="sxs-lookup"><span data-stu-id="ff457-139">Sign In with users E-mail and password.</span></span>
2.  <span data-ttu-id="ff457-140">Ga naar Instellingen > accounts > Toegang tot werk of school.</span><span class="sxs-lookup"><span data-stu-id="ff457-140">Go to Settings > Accounts > Access Work Or School.</span></span> 
3.  <span data-ttu-id="ff457-141">Zoek een gebruiker in de lijst met **verbonden met ... 's Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="ff457-141">Look for a user in the list with **connected to … ‘s Azure AD**.</span></span> 
4.  <span data-ttu-id="ff457-142">Als er een verbonden gebruiker bestaat, gaat u verder met stap 2.</span><span class="sxs-lookup"><span data-stu-id="ff457-142">If a connected user exists, proceed with Step 2.</span></span> <span data-ttu-id="ff457-143">Zo niet, dan is er geen verdere actie vereist.</span><span class="sxs-lookup"><span data-stu-id="ff457-143">If not, no further action is required.</span></span>
### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="ff457-144">Stap 2: Het apparaat loskoppelen van Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff457-144">Step 2: Disconnect the device from Azure AD</span></span>
1.  <span data-ttu-id="ff457-145">Tik **op Loskoppelen** op het verbonden werk- of schoolaccount.</span><span class="sxs-lookup"><span data-stu-id="ff457-145">Tap **Disconnect** on the connected work or School Account.</span></span> 
2.  <span data-ttu-id="ff457-146">Bevestig de verbinding tweemaal.</span><span class="sxs-lookup"><span data-stu-id="ff457-146">Confirm the disconnect twice.</span></span> 
3.  <span data-ttu-id="ff457-147">Voer de gebruikersnaam en het wachtwoord van de lokale beheerder in.</span><span class="sxs-lookup"><span data-stu-id="ff457-147">Enter the local administrator username and password.</span></span> <span data-ttu-id="ff457-148">Het apparaat is losgekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ff457-148">The device is disconnected.</span></span>
4.  <span data-ttu-id="ff457-149">Start het apparaat opnieuw op.</span><span class="sxs-lookup"><span data-stu-id="ff457-149">Restart the device.</span></span>
### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="ff457-150">Stap 3: Deelnemen aan het apparaat aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="ff457-150">Step 3: Join the device to Azure AD</span></span>
1.  <span data-ttu-id="ff457-151">de gebruiker zich aanmeld met de referenties van de lokale beheerder</span><span class="sxs-lookup"><span data-stu-id="ff457-151">the user signs in with the credentials of the local administrator</span></span>
2.  <span data-ttu-id="ff457-152">Ga naar **Instellingen** accounts **en** vervolgens Toegang tot werk **of school**</span><span class="sxs-lookup"><span data-stu-id="ff457-152">Go to **Settings** then **Accounts** then **Access Work Or School**</span></span>
3.  <span data-ttu-id="ff457-153">Tik **Verbinding maken**</span><span class="sxs-lookup"><span data-stu-id="ff457-153">Tap **Connect**</span></span>
4.  <span data-ttu-id="ff457-154">**BELANGRIJK:** Tik op **Deelnemen aan Azure AD**</span><span class="sxs-lookup"><span data-stu-id="ff457-154">**IMPORTANT**: Tap **Join to Azure AD**</span></span>
5.  <span data-ttu-id="ff457-155">Voer het e-mailadres en wachtwoord van de gebruiker in.</span><span class="sxs-lookup"><span data-stu-id="ff457-155">Enter the e-mail address and password of the user.</span></span> <span data-ttu-id="ff457-156">Het apparaat is verbonden</span><span class="sxs-lookup"><span data-stu-id="ff457-156">The device is connected</span></span>
6.  <span data-ttu-id="ff457-157">Het apparaat opnieuw starten</span><span class="sxs-lookup"><span data-stu-id="ff457-157">Restart the device</span></span> 
7.  <span data-ttu-id="ff457-158">ondertekenen met uw e-mailadres en wachtwoord</span><span class="sxs-lookup"><span data-stu-id="ff457-158">sign with your e-mail address and password</span></span>

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="ff457-159">Azure AD Registered (eigendom van het bedrijf)</span><span class="sxs-lookup"><span data-stu-id="ff457-159">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="ff457-160">Als u wilt bepalen of Windows 10 Azure AD-geregistreerd is, voer u de volgende opdracht uit op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="ff457-160">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="ff457-161">Als het apparaat Azure AD Registered is, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="ff457-161">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="ff457-162">Het bestaande door Azure AD geregistreerde account op het apparaat verwijderen:</span><span class="sxs-lookup"><span data-stu-id="ff457-162">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="ff457-163">Als u het door Azure AD geregistreerde account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpprogramma dat u hier kunt [downloaden:CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="ff457-163">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="ff457-164">Haal het ZIP-bestand op en voer **WPJCleanup.cmd uit.**</span><span class="sxs-lookup"><span data-stu-id="ff457-164">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="ff457-165">Met dit hulpprogramma wordt de juiste uitvoerbare start gemaakt op basis van de versie van Windows op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ff457-165">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="ff457-166">Met een mechanisme zoals Groepsbeleid kan de beheerder de opdracht uitvoeren op het apparaat in de context van elke gebruiker die is aangemeld op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ff457-166">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="ff457-167">Als u de aanwijzingen van Web Account Manager wilt uitschakelen om het apparaat in Azure AD te registreren, voegt u deze registerwaarde toe:</span><span class="sxs-lookup"><span data-stu-id="ff457-167">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="ff457-168">Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="ff457-168">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="ff457-169">Type: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="ff457-169">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="ff457-170">Naam: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="ff457-170">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="ff457-171">Waardegegevens: 1</span><span class="sxs-lookup"><span data-stu-id="ff457-171">Value data: 1</span></span>

<span data-ttu-id="ff457-172">De aanwezigheid van deze registerwaarde moet de join van de werkplek blokkeren en voorkomen dat gebruikers aanwijzingen zien om deel te nemen aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ff457-172">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="ff457-173">Android</span><span class="sxs-lookup"><span data-stu-id="ff457-173">Android</span></span>

<span data-ttu-id="ff457-174">Voor Android moeten gebruikers de registratie van hun apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="ff457-174">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="ff457-175">Dit kan via de Microsoft Authenticator app of de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="ff457-175">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="ff457-176">Vanuit de Microsoft Authenticator app kunnen gebruikers naar Instellingen > **Apparaatregistratie** gaan.</span><span class="sxs-lookup"><span data-stu-id="ff457-176">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="ff457-177">Van hieruit kunnen gebruikers hun registratie ongedaan maken en hun apparaat opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="ff457-177">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="ff457-178">Vanuit de Bedrijfsportal kunnen gebruikers naar het **tabblad** Apparaten gaan en het apparaat verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ff457-178">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="ff457-179">Daarna kunt u het apparaat opnieuw registreren met behulp van Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="ff457-179">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="ff457-180">Gebruikers kunnen zich ook afmelden en opnieuw registreren door het account te verwijderen van de pagina accountinstellingen en vervolgens het werkaccount opnieuw toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="ff457-180">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="ff457-181">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren met de Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="ff457-181">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="ff457-182">Open de Microsoft Authenticator app en ga naar **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="ff457-182">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="ff457-183">Selecteer **Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="ff457-183">Select **Device registration**.</span></span>
3.  <span data-ttu-id="ff457-184">De registratie van het apparaat ongedaan maken door **Afmelden te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="ff457-184">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="ff457-185">Voor **apparaatregistratie,** moet u het apparaat opnieuw registreren door uw e-mailadres te typen en vervolgens **Registreren te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="ff457-185">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="ff457-186">Een Android-apparaat op de pagina Android-Instellingen opnieuw registreren:</span><span class="sxs-lookup"><span data-stu-id="ff457-186">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="ff457-187">Open **Apparaat Instellingen** en ga naar **Accounts.**</span><span class="sxs-lookup"><span data-stu-id="ff457-187">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="ff457-188">Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **Account verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ff457-188">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="ff457-189">Nadat het account is verwijderd, selecteert u op de **pagina Accounts** de optie Account toevoegen **> werkaccount.**</span><span class="sxs-lookup"><span data-stu-id="ff457-189">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="ff457-190">Voor **Workplace Join** typt u uw e-mailadres en **selecteert** u Deelnemen om de registratie van het apparaat te voltooien.</span><span class="sxs-lookup"><span data-stu-id="ff457-190">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="ff457-191">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren Bedrijfsportal:</span><span class="sxs-lookup"><span data-stu-id="ff457-191">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="ff457-192">Start Bedrijfsportal en ga naar **het tabblad** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="ff457-192">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="ff457-193">Selecteer het apparaat om de apparaatdetails te bekijken.</span><span class="sxs-lookup"><span data-stu-id="ff457-193">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="ff457-194">Selecteer apparaat verwijderen in het menu drie puntjes (drie puntjes) en voltooi de verwijdering door dit te bevestigen in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="ff457-194">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="ff457-195">U moet nu zijn afgemeld bij de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="ff457-195">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="ff457-196">Selecteer **Aanmelden om** het apparaat opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="ff457-196">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="ff457-197">Bekijk de informatie over Azure Active Directory (Azure AD) in Aanvullende Azure AD-informatie voor de migratie van [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over acties die nodig zijn tijdens de migratiefase van deze werkbelasting of de gevolgen voor beheer of gebruik.</span><span class="sxs-lookup"><span data-stu-id="ff457-197">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="ff457-198">iOS</span><span class="sxs-lookup"><span data-stu-id="ff457-198">iOS</span></span>

<span data-ttu-id="ff457-199">Op iOS-apparaten moet een gebruiker accounts in de cache handmatig verwijderen uit de Microsoft Authenticator, het apparaat uitschrijven en zich afmelden bij native apps op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="ff457-199">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="ff457-200">Stap 1: Als u aanwezig bent, verwijdert u het account uit de Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="ff457-200">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="ff457-201">Tik op het account in de Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="ff457-201">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="ff457-202">Tik op **Instellingen** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="ff457-202">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="ff457-203">Als u het pictogram  Instellingen niet ziet, gebruikt u mogelijk niet de nieuwste versie van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="ff457-203">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="ff457-204">Tik op **de knop Account** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ff457-204">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="ff457-205">Tik **op Alle apps op dit apparaat.**</span><span class="sxs-lookup"><span data-stu-id="ff457-205">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="ff457-206">Stap 2: Het apparaat uit de app Microsoft Authenticator verwijderen</span><span class="sxs-lookup"><span data-stu-id="ff457-206">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="ff457-207">Tik op het menupictogram in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="ff457-207">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="ff457-208">Tik **Instellingen** en vervolgens **op Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="ff457-208">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="ff457-209">Als uw account wordt weergegeven, tikt u **op Apparaat afmelden** en **doorgaan** in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="ff457-209">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="ff457-210">Daarna ziet u geen account meer.</span><span class="sxs-lookup"><span data-stu-id="ff457-210">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="ff457-211">Stap 3: Meld u indien nodig af bij afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="ff457-211">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="ff457-212">Gebruikers kunnen naar afzonderlijke apps gaan, zoals Outlook, Teams en OneDrive en accounts uit die apps verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ff457-212">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="ff457-213">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="ff457-213">More information</span></span>

<span data-ttu-id="ff457-214">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="ff457-214">Getting started:</span></span>

- [<span data-ttu-id="ff457-215">Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's</span><span class="sxs-lookup"><span data-stu-id="ff457-215">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="ff457-216">Microsoft Cloud Deutschland-migratiehulp</span><span class="sxs-lookup"><span data-stu-id="ff457-216">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="ff457-217">Opt-in voor migratie</span><span class="sxs-lookup"><span data-stu-id="ff457-217">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="ff457-218">Klantervaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="ff457-218">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="ff457-219">Door de overgang lopen:</span><span class="sxs-lookup"><span data-stu-id="ff457-219">Moving through the transition:</span></span>

- [<span data-ttu-id="ff457-220">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="ff457-220">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="ff457-221">Extra pre-work</span><span class="sxs-lookup"><span data-stu-id="ff457-221">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="ff457-222">Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="ff457-222">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="ff457-223">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="ff457-223">Cloud apps:</span></span>

- [<span data-ttu-id="ff457-224">Dynamics 365-migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="ff457-224">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="ff457-225">Power BI migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="ff457-225">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="ff457-226">Aan de slag met uw Microsoft Teams upgrade</span><span class="sxs-lookup"><span data-stu-id="ff457-226">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)