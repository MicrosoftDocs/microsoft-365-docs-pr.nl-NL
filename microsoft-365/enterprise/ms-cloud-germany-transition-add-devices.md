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
ms.openlocfilehash: 21188372f03af394fe1c0e227c1adeabbad02a85
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928154"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="36a85-103">Aanvullende apparaatgegevens voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="36a85-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="36a85-104">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="36a85-104">Frequently asked questions</span></span>

<span data-ttu-id="36a85-105">**Hoe weet ik of mijn organisatie is beïnvloed?**</span><span class="sxs-lookup"><span data-stu-id="36a85-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="36a85-106">Beheerders moeten controleren of ze geregistreerde apparaten `https://portal.microsoftazure.de` hebben.</span><span class="sxs-lookup"><span data-stu-id="36a85-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="36a85-107">Als uw organisatie geregistreerde apparaten heeft, is dit van invloed op u.</span><span class="sxs-lookup"><span data-stu-id="36a85-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="36a85-108">**Wat zijn de gevolgen voor mijn gebruikers?**</span><span class="sxs-lookup"><span data-stu-id="36a85-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="36a85-109">Gebruikers vanaf een geregistreerd apparaat kunnen zich niet meer aanmelden nadat uw migratie de [Azure AD-migratiefase](ms-cloud-germany-transition.md#how-is-the-migration-organized) definitief heeft bereikt.</span><span class="sxs-lookup"><span data-stu-id="36a85-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="36a85-110">Zorg ervoor dat al uw apparaten zijn geregistreerd bij het wereldwijde eindpunt voordat uw organisatie is losgekoppeld van Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="36a85-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="36a85-111">**Wanneer registreren mijn gebruikers hun apparaten opnieuw?**</span><span class="sxs-lookup"><span data-stu-id="36a85-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="36a85-112">Het is essentieel voor uw succes dat u uw apparaten alleen uitschrijft en opnieuw registreert tijdens de migratiefase Scheiden van [Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="36a85-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="36a85-113">**Hoe herstel ik de status van mijn apparaat na de migratie?**</span><span class="sxs-lookup"><span data-stu-id="36a85-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="36a85-114">Voor hybride Azure AD-apparaten en Windows-apparaten die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via op afstand geactiveerde werkstromen die de registratie van de oude apparaatstatussen ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="36a85-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="36a85-115">Voor alle andere apparaten, waaronder persoonlijke apparaten Windows die zijn geregistreerd in Azure AD, moet de eindgebruiker deze stappen handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="36a85-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="36a85-116">Voor apparaten die zijn verbonden met Azure AD, moeten gebruikers een lokaal beheerdersaccount hebben om de registratie uit te schrijven en vervolgens hun apparaten opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="36a85-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="36a85-117">Microsoft publiceert instructies voor het herstellen van de apparaattoestand.</span><span class="sxs-lookup"><span data-stu-id="36a85-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="36a85-118">**Hoe weet ik dat al mijn apparaten zijn geregistreerd in de openbare cloud?**</span><span class="sxs-lookup"><span data-stu-id="36a85-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="36a85-119">Als u wilt controleren of uw apparaten zijn geregistreerd in de openbare cloud, moet u de lijst met apparaten exporteren en downloaden van de Azure AD-portal naar een Excel spreadsheet.</span><span class="sxs-lookup"><span data-stu-id="36a85-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="36a85-120">Filter vervolgens de apparaten die zijn geregistreerd (met behulp van de kolom _registeredTime)_ na de migratiefase Scheiden [van Microsoft Cloud Deutschland.](ms-cloud-germany-transition.md#how-is-the-migration-organized)</span><span class="sxs-lookup"><span data-stu-id="36a85-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="36a85-121">Apparaatregistratie wordt gedeactiveerd na de migratie van de tenant en kan niet worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="36a85-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="36a85-122">Als Intune niet wordt gebruikt, meld u dan aan bij uw abonnement en voer deze opdracht uit om de optie opnieuw te activeren:</span><span class="sxs-lookup"><span data-stu-id="36a85-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="hybrid-azure-ad-join"></a><span data-ttu-id="36a85-123">Hybride Azure AD-join</span><span class="sxs-lookup"><span data-stu-id="36a85-123">Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="36a85-124">Windows down-level</span><span class="sxs-lookup"><span data-stu-id="36a85-124">Windows down-level</span></span>

<span data-ttu-id="36a85-125">_Windows_ apparaten op downniveau zijn Windows-apparaten die momenteel eerdere versies van Windows uitvoeren (zoals Windows 8.1 of Windows 7), of die eerder dan 2019 en 2016 Windows Server-versies uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="36a85-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="36a85-126">Als dergelijke apparaten eerder zijn geregistreerd, moet u de registratie van deze apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="36a85-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="36a85-127">Gebruik de volgende opdracht op het apparaat om te bepalen Windows een apparaat met een lager niveau eerder is verbonden met Azure AD:</span><span class="sxs-lookup"><span data-stu-id="36a85-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="36a85-128">Als het apparaat eerder is verbonden met Azure AD en als het apparaat netwerkconnectiviteit heeft met globale Azure AD-eindpunten, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="36a85-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device Details                                                       |
+----------------------------------------------------------------------+
         DeviceId : AEE2B956-DA62-48D0-BB47-046DD992A110
       Thumbprint : 00fdfa2de5c32feae57489873a13aa6a3ff7433b
             User : user1@<tenantname>.de
Private key state : Okay
     Device state : Unknown
```

<span data-ttu-id="36a85-129">De betreffende apparaten hebben de 'Apparaattoestand' met de waarde 'Onbekend'.</span><span class="sxs-lookup"><span data-stu-id="36a85-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="36a85-130">Als de uitvoer 'Apparaat niet is samengevoegd' is of waarvan de waarde 'Apparaatstaat' 'Ok' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="36a85-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="36a85-131">Alleen voor apparaten waaruit blijkt dat het apparaat is verbonden (op basis van apparaatId, duimafdruk, en dergelijke) en waarvan de waarde 'Apparaatstaat' onbekend is, moeten beheerders de volgende opdracht uitvoeren in de context van een domeingebruiker die zich aanmeldt op een dergelijk apparaat op een lager niveau:</span><span class="sxs-lookup"><span data-stu-id="36a85-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="36a85-132">De vorige opdracht hoeft slechts één keer te worden uitgevoerd per domeingebruiker die zich aanmeldt op het Windows apparaat op downniveau.</span><span class="sxs-lookup"><span data-stu-id="36a85-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="36a85-133">Deze opdracht moet worden uitgevoerd in de context van de domeingebruiker die zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="36a85-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="36a85-134">Er moet voldoende aandacht aan worden gegeven om deze opdracht niet uit te voeren wanneer de gebruiker zich vervolgens aan meldt.</span><span class="sxs-lookup"><span data-stu-id="36a85-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="36a85-135">Wanneer de vorige opdracht wordt uitgevoerd, wordt de samengevoegde status van de lokale hybride Azure AD-computer geweken voor de gebruiker die zich heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="36a85-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="36a85-136">En als de computer nog steeds is geconfigureerd voor hybride Azure AD-join in de tenant, wordt geprobeerd deel te nemen wanneer de gebruiker zich opnieuw meldt.</span><span class="sxs-lookup"><span data-stu-id="36a85-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="36a85-137">Windows Huidige</span><span class="sxs-lookup"><span data-stu-id="36a85-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="36a85-138">Unjoin</span><span class="sxs-lookup"><span data-stu-id="36a85-138">Unjoin</span></span>

<span data-ttu-id="36a85-139">Voer de volgende opdracht uit op het apparaat om te bepalen Windows 10 het apparaat eerder is verbonden met Azure AD:</span><span class="sxs-lookup"><span data-stu-id="36a85-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="36a85-140">Als het apparaat hybride Azure AD-lid is, ziet de beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="36a85-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="36a85-141">Als de uitvoer 'AzureAdJoined: Nee' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="36a85-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="36a85-142">Voer als beheerder alleen de volgende opdracht uit als beheerder om de samengevoegde status van het apparaat te verwijderen voor apparaten die aantonen dat het apparaat is verbonden met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36a85-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="36a85-143">De vorige opdracht hoeft slechts eenmaal in een administratieve context op het Windows worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="36a85-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="36a85-144">Hybride AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="36a85-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="36a85-145">Het apparaat wordt automatisch zonder tussenkomst van de gebruiker of beheerder aan Azure AD verbonden, zolang het apparaat netwerkconnectiviteit heeft met globale Azure AD-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="36a85-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="azure-ad-join"></a><span data-ttu-id="36a85-146">Azure AD Join</span><span class="sxs-lookup"><span data-stu-id="36a85-146">Azure AD Join</span></span>

<span data-ttu-id="36a85-147">**BELANGRIJK:** De Intune-service principal wordt ingeschakeld na de migratie van commerce, wat de activering van Azure AD Device Registration impliceert.</span><span class="sxs-lookup"><span data-stu-id="36a85-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="36a85-148">Als u Azure AD Device Registration vóór de migratie hebt geblokkeerd, moet u de Intune-service principal met PowerShell uitschakelen om Azure AD Device Registration weer uit te schakelen met de Azure AD-portal.</span><span class="sxs-lookup"><span data-stu-id="36a85-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="36a85-149">U kunt de Intune-service principal uitschakelen met deze opdracht in Azure Active Directory PowerShell voor Graph module.</span><span class="sxs-lookup"><span data-stu-id="36a85-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="36a85-150">Unjoin</span><span class="sxs-lookup"><span data-stu-id="36a85-150">Unjoin</span></span>

<span data-ttu-id="36a85-151">Als u wilt bepalen of het Windows 10 eerder is verbonden met Azure AD, kan de gebruiker of beheerder de volgende opdracht uitvoeren op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="36a85-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="36a85-152">Als het apparaat is verbonden met Azure AD, ziet de gebruiker of beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="36a85-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="36a85-153">Als de uitvoer 'AzureAdJoined: NO' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="36a85-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="36a85-154">Gebruiker: Als het apparaat is verbonden met Azure AD, kan een gebruiker de toegang tot het apparaat ontvoegen via de instellingen.</span><span class="sxs-lookup"><span data-stu-id="36a85-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="36a85-155">Controleer of er een lokaal beheerdersaccount op het apparaat is voordat u het apparaat losvoegt vanuit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36a85-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="36a85-156">Het lokale beheerdersaccount is vereist om u weer aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="36a85-157">Beheerder: Als de beheerder van de organisatie de apparaten van de gebruikers wil ontvoegen die zijn verbonden met Azure AD, kunnen ze dit doen door de volgende opdracht uit te voeren op elk van de apparaten met behulp van een mechanisme zoals Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="36a85-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="36a85-158">De beheerder moet controleren of er een lokaal beheerdersaccount op het apparaat is voordat het apparaat wordt ontvoegd vanuit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="36a85-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="36a85-159">Het lokale beheerdersaccount is nodig om u weer aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="36a85-160">De vorige opdracht hoeft slechts eenmaal in een administratieve context op het Windows worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="36a85-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="36a85-161">Azure AD Join/Re-Registration</span><span class="sxs-lookup"><span data-stu-id="36a85-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="36a85-162">De gebruiker kan het apparaat koppelen aan Azure AD via Windows instellingen: **Instellingen > Accounts > Access Work or School > Verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="36a85-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="azure-ad-registered-company-owned"></a><span data-ttu-id="36a85-163">Azure AD Registered (eigendom van het bedrijf)</span><span class="sxs-lookup"><span data-stu-id="36a85-163">Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="36a85-164">Als u wilt bepalen of Windows 10 Azure AD-geregistreerd is, voer u de volgende opdracht uit op het apparaat:</span><span class="sxs-lookup"><span data-stu-id="36a85-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="36a85-165">Als het apparaat Azure AD Registered is, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="36a85-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="36a85-166">Het bestaande door Azure AD geregistreerde account op het apparaat verwijderen:</span><span class="sxs-lookup"><span data-stu-id="36a85-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="36a85-167">Als u het door Azure AD geregistreerde account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpprogramma dat u hier kunt [downloaden:CleanupWPJ.zip. ](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip)</span><span class="sxs-lookup"><span data-stu-id="36a85-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="36a85-168">Haal het ZIP-bestand op en voer **WPJCleanup.cmd uit.**</span><span class="sxs-lookup"><span data-stu-id="36a85-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="36a85-169">Met dit hulpprogramma wordt de juiste uitvoerbare start gemaakt op basis van de versie van Windows op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="36a85-170">Met een mechanisme zoals Groepsbeleid kan de beheerder de opdracht uitvoeren op het apparaat in de context van elke gebruiker die is aangemeld op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="36a85-171">Als u de aanwijzingen van Web Account Manager wilt uitschakelen om het apparaat in Azure AD te registreren, voegt u deze registerwaarde toe:</span><span class="sxs-lookup"><span data-stu-id="36a85-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="36a85-172">Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="36a85-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="36a85-173">Type: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="36a85-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="36a85-174">Naam: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="36a85-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="36a85-175">Waardegegevens: 1</span><span class="sxs-lookup"><span data-stu-id="36a85-175">Value data: 1</span></span>

<span data-ttu-id="36a85-176">De aanwezigheid van deze registerwaarde moet de join van de werkplek blokkeren en voorkomen dat gebruikers aanwijzingen zien om deel te nemen aan het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="36a85-177">Android</span><span class="sxs-lookup"><span data-stu-id="36a85-177">Android</span></span>

<span data-ttu-id="36a85-178">Voor Android moeten gebruikers de registratie van hun apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="36a85-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="36a85-179">Dit kan via de Microsoft Authenticator app of de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="36a85-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="36a85-180">Vanuit de Microsoft Authenticator app kunnen gebruikers naar Instellingen > **Apparaatregistratie** gaan.</span><span class="sxs-lookup"><span data-stu-id="36a85-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="36a85-181">Van hieruit kunnen gebruikers hun registratie ongedaan maken en hun apparaat opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="36a85-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="36a85-182">Vanuit de Bedrijfsportal kunnen gebruikers naar het **tabblad** Apparaten gaan en het apparaat verwijderen.</span><span class="sxs-lookup"><span data-stu-id="36a85-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="36a85-183">Daarna kunt u het apparaat opnieuw registreren met behulp van Bedrijfsportal.</span><span class="sxs-lookup"><span data-stu-id="36a85-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="36a85-184">Gebruikers kunnen zich ook afmelden en opnieuw registreren door het account te verwijderen van de pagina accountinstellingen en vervolgens het werkaccount opnieuw toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="36a85-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="36a85-185">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren met de Microsoft Authenticator app:</span><span class="sxs-lookup"><span data-stu-id="36a85-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="36a85-186">Open de Microsoft Authenticator app en ga naar **Instellingen.**</span><span class="sxs-lookup"><span data-stu-id="36a85-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="36a85-187">Selecteer **Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="36a85-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="36a85-188">De registratie van het apparaat ongedaan maken door **Afmelden te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="36a85-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="36a85-189">Voor **apparaatregistratie,** moet u het apparaat opnieuw registreren door uw e-mailadres te typen en vervolgens **Registreren te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="36a85-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="36a85-190">Een Android-apparaat op de pagina Android-Instellingen opnieuw registreren:</span><span class="sxs-lookup"><span data-stu-id="36a85-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="36a85-191">Open **Apparaat Instellingen** en ga naar **Accounts.**</span><span class="sxs-lookup"><span data-stu-id="36a85-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="36a85-192">Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **Account verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="36a85-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="36a85-193">Nadat het account is verwijderd, selecteert u op de **pagina Accounts** de optie Account toevoegen **> werkaccount.**</span><span class="sxs-lookup"><span data-stu-id="36a85-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="36a85-194">Voor **Workplace Join** typt u uw e-mailadres en **selecteert** u Deelnemen om de registratie van het apparaat te voltooien.</span><span class="sxs-lookup"><span data-stu-id="36a85-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="36a85-195">U kunt de registratie van het apparaat op Android ongedaan maken en opnieuw registreren Bedrijfsportal:</span><span class="sxs-lookup"><span data-stu-id="36a85-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="36a85-196">Start Bedrijfsportal en ga naar **het tabblad** Apparaten.</span><span class="sxs-lookup"><span data-stu-id="36a85-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="36a85-197">Selecteer het apparaat om de apparaatdetails te bekijken.</span><span class="sxs-lookup"><span data-stu-id="36a85-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="36a85-198">Selecteer apparaat verwijderen in het menu drie puntjes (drie puntjes) en voltooi de verwijdering door dit te bevestigen in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="36a85-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="36a85-199">U moet nu zijn afgemeld bij de Bedrijfsportal app.</span><span class="sxs-lookup"><span data-stu-id="36a85-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="36a85-200">Selecteer **Aanmelden om** het apparaat opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="36a85-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="36a85-201">Bekijk de informatie over Azure Active Directory (Azure AD) in Aanvullende Azure AD-informatie voor de migratie van [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over acties die nodig zijn tijdens de migratiefase van deze werkbelasting of de gevolgen voor beheer of gebruik.</span><span class="sxs-lookup"><span data-stu-id="36a85-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="36a85-202">iOS</span><span class="sxs-lookup"><span data-stu-id="36a85-202">iOS</span></span>

<span data-ttu-id="36a85-203">Op iOS-apparaten moet een gebruiker accounts in de cache handmatig verwijderen uit de Microsoft Authenticator, het apparaat uitschrijven en zich afmelden bij native apps op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="36a85-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="36a85-204">Stap 1: Als u aanwezig bent, verwijdert u het account uit de Microsoft Authenticator app</span><span class="sxs-lookup"><span data-stu-id="36a85-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="36a85-205">Tik op het account in de Microsoft Authenticator app.</span><span class="sxs-lookup"><span data-stu-id="36a85-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="36a85-206">Tik op **Instellingen** in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="36a85-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="36a85-207">Als u het pictogram  Instellingen niet ziet, gebruikt u mogelijk niet de nieuwste versie van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="36a85-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="36a85-208">Tik op **de knop Account** verwijderen.</span><span class="sxs-lookup"><span data-stu-id="36a85-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="36a85-209">Tik **op Alle apps op dit apparaat.**</span><span class="sxs-lookup"><span data-stu-id="36a85-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="36a85-210">Stap 2: Het apparaat uit de app Microsoft Authenticator verwijderen</span><span class="sxs-lookup"><span data-stu-id="36a85-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="36a85-211">Tik op het menupictogram in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="36a85-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="36a85-212">Tik **Instellingen** en vervolgens **op Apparaatregistratie.**</span><span class="sxs-lookup"><span data-stu-id="36a85-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="36a85-213">Als uw account wordt weergegeven, tikt u **op Apparaat afmelden** en **doorgaan** in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="36a85-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="36a85-214">Daarna ziet u geen account meer.</span><span class="sxs-lookup"><span data-stu-id="36a85-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="36a85-215">Stap 3: Meld u indien nodig af bij afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="36a85-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="36a85-216">Gebruikers kunnen naar afzonderlijke apps gaan, zoals Outlook, Teams en OneDrive en accounts uit die apps verwijderen.</span><span class="sxs-lookup"><span data-stu-id="36a85-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="36a85-217">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="36a85-217">More information</span></span>

<span data-ttu-id="36a85-218">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="36a85-218">Getting started:</span></span>

- [<span data-ttu-id="36a85-219">Migratie van Microsoft Cloud Deutschland naar Office 365 services in de nieuwe Duitse datacenterregio's</span><span class="sxs-lookup"><span data-stu-id="36a85-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="36a85-220">Microsoft Cloud Deutschland-migratiehulp</span><span class="sxs-lookup"><span data-stu-id="36a85-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="36a85-221">Opt-in voor migratie</span><span class="sxs-lookup"><span data-stu-id="36a85-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="36a85-222">Klantervaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="36a85-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="36a85-223">Door de overgang lopen:</span><span class="sxs-lookup"><span data-stu-id="36a85-223">Moving through the transition:</span></span>

- [<span data-ttu-id="36a85-224">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="36a85-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="36a85-225">Extra pre-work</span><span class="sxs-lookup"><span data-stu-id="36a85-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="36a85-226">Aanvullende informatie voor [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [apparaten,](ms-cloud-germany-transition-add-devices.md) [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="36a85-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="36a85-227">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="36a85-227">Cloud apps:</span></span>

- [<span data-ttu-id="36a85-228">Dynamics 365-migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="36a85-228">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="36a85-229">Power BI migratieprogrammagegevens</span><span class="sxs-lookup"><span data-stu-id="36a85-229">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="36a85-230">Aan de slag met uw Microsoft Teams upgrade</span><span class="sxs-lookup"><span data-stu-id="36a85-230">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)