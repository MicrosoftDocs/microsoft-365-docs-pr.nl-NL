---
title: Aanvullende informatie over apparaten voor de migratie van Microsoft Cloud Deutschland
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
description: 'Overzicht: aanvullende informatie over apparaten voor services wanneer u overstapt van Microsoft Cloud Duitsland (Microsoft Cloud Deutschland) naar Office 365-Services in het nieuwe Duitse datacenter-gebied.'
ms.openlocfilehash: 1bbb4bf39db61a93844c21cd6062a70699b5d6d7
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688651"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="3bda8-103">Aanvullende informatie over apparaten voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="3bda8-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="3bda8-104">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="3bda8-104">Frequently asked questions</span></span>

<span data-ttu-id="3bda8-105">**Hoe weet ik of mijn organisatie van invloed is?**</span><span class="sxs-lookup"><span data-stu-id="3bda8-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="3bda8-106">Beheerders moeten `https://portal.microsoftazure.de` nagaan of ze geregistreerde apparaten hebben.</span><span class="sxs-lookup"><span data-stu-id="3bda8-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="3bda8-107">Als uw organisatie geregistreerde apparaten heeft, hebt u last van.</span><span class="sxs-lookup"><span data-stu-id="3bda8-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="3bda8-108">**Wat is de gevolgen voor mijn gebruikers?**</span><span class="sxs-lookup"><span data-stu-id="3bda8-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="3bda8-109">Gebruikers van een geregistreerd apparaat kunnen zich niet meer aanmelden nadat de migratie is voltooid met de [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) -migratie fase.</span><span class="sxs-lookup"><span data-stu-id="3bda8-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="3bda8-110">Zorg ervoor dat al uw apparaten geregistreerd zijn met het wereldwijde eindpunt voordat uw organisatie wordt losgekoppeld van Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="3bda8-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="3bda8-111">**Wanneer worden mijn gebruikers hun apparaten opnieuw registreren?**</span><span class="sxs-lookup"><span data-stu-id="3bda8-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="3bda8-112">Het is belangrijk dat u het niet meer registreert en uw apparaten opnieuw registreert onder de migratie fase [van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="3bda8-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="3bda8-113">**Hoe kan ik de status van mijn apparaat na migratie herstellen?**</span><span class="sxs-lookup"><span data-stu-id="3bda8-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="3bda8-114">Voor hybride Azure AD-en bedrijfsgeschikte Windows-apparaten die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via externe, geactiveerde werkstromen waarmee de registratie van de oude status van het oude apparaat wordt opgeheven.</span><span class="sxs-lookup"><span data-stu-id="3bda8-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="3bda8-115">Voor alle andere apparaten, waaronder persoonlijke Windows-apparaten die in azure AD zijn geregistreerd, moet de eindgebruiker deze stappen handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="3bda8-116">Voor Azure AD – gekoppelde apparaten moet de gebruiker een lokaal beheerdersaccount hebben om de registratie te deactiveren en de apparaten vervolgens opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="3bda8-117">In Microsoft wordt de instructies gepubliceerd voor het herstellen van de status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="3bda8-118">**Hoe weet ik of al mijn apparaten geregistreerd zijn in de openbare Cloud?**</span><span class="sxs-lookup"><span data-stu-id="3bda8-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="3bda8-119">Als u wilt controleren of de apparaten in de openbare Cloud zijn geregistreerd, moet u de lijst met apparaten in de Azure AD-Portal exporteren naar een Excel-spreadsheet en deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="3bda8-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="3bda8-120">Vervolgens kunt u de geregistreerde apparaten filteren (met behulp van de kolom _registeredTime_ ), na de [afzonderlijke migratie van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migratie fase.</span><span class="sxs-lookup"><span data-stu-id="3bda8-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="3bda8-121">Apparaatregistratie wordt gedeactiveerd na migratie van de Tenant en kan niet worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="3bda8-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="3bda8-122">Als intune niet wordt gebruikt, meldt u zich aan bij uw abonnement en voert u deze opdracht uit om de optie weer te activeren:</span><span class="sxs-lookup"><span data-stu-id="3bda8-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="3bda8-123">Windows Hybrid Azure AD join</span><span class="sxs-lookup"><span data-stu-id="3bda8-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="3bda8-124">Windows-downlevel</span><span class="sxs-lookup"><span data-stu-id="3bda8-124">Windows down-level</span></span>

<span data-ttu-id="3bda8-125">_Windows-apparaten op een lager niveau_ zijn Windows-apparaten die op dit moment eerdere versies van Windows gebruiken (zoals Windows 8,1 of Windows 7) of die Windows Server-versies ouder dan 2019 en 2016 uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="3bda8-126">Als deze apparatuur eerder geregistreerd is, moet u de registratie van deze apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="3bda8-127">Gebruik de volgende opdracht op het apparaat om te bepalen of een apparaat op het Windows-apparaat eerder lid is van Azure AD:</span><span class="sxs-lookup"><span data-stu-id="3bda8-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="3bda8-128">Als het apparaat eerder is verbonden met Azure AD en als het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="3bda8-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="3bda8-129">De beïnvloede apparaten hebben de ' apparaat State ' met de waarde ' onbekend '.</span><span class="sxs-lookup"><span data-stu-id="3bda8-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="3bda8-130">Als de uitvoer de waarde ' apparaat niet meeneemt ' of waarvan de waarde ' apparaat State ' ' ' u ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="3bda8-131">Alleen voor apparaten die aangeven dat het apparaat is verbonden (op basis van deviceId, vingerafdruk, enzovoort) en waarvan de waarde ' apparaat State ' ' onbekend ' is, moeten beheerders de volgende opdracht uitvoeren in de context van een domeingebruiker die zich aanmeldt op een dergelijk apparaat met een lager niveau:</span><span class="sxs-lookup"><span data-stu-id="3bda8-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="3bda8-132">De bovenstaande opdracht hoeft slechts één keer per domeingebruiker te worden uitgevoerd op het Windows-apparaat op het niveau van het laagste niveau.</span><span class="sxs-lookup"><span data-stu-id="3bda8-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="3bda8-133">Deze opdracht moet worden uitgevoerd in de context van de domeingebruiker die zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="3bda8-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="3bda8-134">U dient deze opdracht niet uit te voeren wanneer de gebruiker zich daarna aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="3bda8-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="3bda8-135">Wanneer de vorige opdracht wordt uitgevoerd, wordt de gekoppelde status gewist van de lokale hybride Azure AD-computer die is gekoppeld aan de gebruiker die zich heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="3bda8-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="3bda8-136">En als de computer nog steeds is geconfigureerd voor hybride Azure AD – deelnemen aan de Tenant, wordt geprobeerd deel te nemen wanneer de gebruiker zich opnieuw aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="3bda8-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="3bda8-137">Windows-actueel</span><span class="sxs-lookup"><span data-stu-id="3bda8-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="3bda8-138">Ontkoppelen</span><span class="sxs-lookup"><span data-stu-id="3bda8-138">Unjoin</span></span>

<span data-ttu-id="3bda8-139">Voer de volgende opdracht uit op het apparaat om te controleren of het Windows 10-apparaat eerder lid is van Azure AD:</span><span class="sxs-lookup"><span data-stu-id="3bda8-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3bda8-140">Als het apparaat hybride Azure AD bevat, ziet de beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="3bda8-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="3bda8-141">Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="3bda8-142">Voor apparaten die aangeven dat het apparaat is verbonden met Azure AD, voert u de volgende opdracht uit als beheerder om de gekoppelde status van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="3bda8-143">De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="3bda8-144">Hybrid AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="3bda8-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="3bda8-145">Het apparaat maakt automatisch deel uit van Azure AD zonder dat de gebruiker of de beheerder van de beheerder zijn, zolang het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="3bda8-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="3bda8-146">Deelnemen aan Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="3bda8-146">Windows Azure AD Join</span></span>

<span data-ttu-id="3bda8-147">**Belangrijk:** De intune service-principal wordt ingeschakeld na commerce Migration, wat impliceert het activeren van Azure AD-apparaatregistratie.</span><span class="sxs-lookup"><span data-stu-id="3bda8-147">**IMPORTANT:** The Intune service principal will be enabled after commerce migration, which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="3bda8-148">Als u ervoor hebt gezorgd dat u de registratie van Azure AD-apparaat voorafgaand aan de migratie hebt geblokkeerd, moet u de intune-Service-Principal uitschakelen met PowerShell om Azure AD-apparaatregistratie opnieuw te uitschakelen met de Azure AD-Portal</span><span class="sxs-lookup"><span data-stu-id="3bda8-148">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="3bda8-149">U kunt tijdens de module Azure Active Directory PowerShell voor Graph de intune-Service-Principal uitschakelen met deze opdracht.</span><span class="sxs-lookup"><span data-stu-id="3bda8-149">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

### <a name="unjoin"></a><span data-ttu-id="3bda8-150">Ontkoppelen</span><span class="sxs-lookup"><span data-stu-id="3bda8-150">Unjoin</span></span>

<span data-ttu-id="3bda8-151">Als u wilt controleren of het Windows 10-apparaat eerder is verbonden met Azure AD, kunt u de volgende opdracht op het apparaat uitvoeren met de gebruiker of beheerder:</span><span class="sxs-lookup"><span data-stu-id="3bda8-151">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3bda8-152">Als het apparaat is verbonden met Azure AD, ziet de gebruiker of beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="3bda8-152">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="3bda8-153">Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-153">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="3bda8-154">Gebruiker: als het apparaat Azure Active Directory is, kan een gebruiker het apparaat loskoppelen van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-154">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="3bda8-155">Controleer of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding maakt met het apparaat via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3bda8-155">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="3bda8-156">U moet het lokale beheerdersaccount opnieuw aanmelden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-156">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="3bda8-157">Beheerder: als de beheerder van de organisatie wil deelnemen aan de apparaten van de gebruikers die lid zijn van Azure AD – u kunt dat doen door de volgende opdracht uit te voeren op alle apparaten met behulp van een mechanisme, zoals Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="3bda8-157">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="3bda8-158">De beheerder moet controleren of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding met het apparaat via Azure AD verzorgt.</span><span class="sxs-lookup"><span data-stu-id="3bda8-158">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="3bda8-159">Het lokale beheerdersaccount is nodig om u weer aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-159">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="3bda8-160">De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-160">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="3bda8-161">Azure AD deelnemen/opnieuw registreren</span><span class="sxs-lookup"><span data-stu-id="3bda8-161">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="3bda8-162">De gebruiker kan deelnemen aan Azure AD via Windows-instellingen: **instellingen > Accounts > toegang tot werk of School > verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-162">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="3bda8-163">Geregistreerde Windows Azure AD (bedrijfseigenaar)</span><span class="sxs-lookup"><span data-stu-id="3bda8-163">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="3bda8-164">Voer de volgende opdracht uit op het apparaat om te controleren of het apparaat met Windows 10 Azure AD is geregistreerd:</span><span class="sxs-lookup"><span data-stu-id="3bda8-164">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="3bda8-165">Als Azure AD is geregistreerd, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="3bda8-165">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="3bda8-166">U kunt als volgt het bestaande in azure AD geregistreerde account van het apparaat verwijderen:</span><span class="sxs-lookup"><span data-stu-id="3bda8-166">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="3bda8-167">Als u het door u geregistreerde Azure AD-account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpmiddel dat u kunt downloaden: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="3bda8-167">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="3bda8-168">Uitpak het ZIP-bestand en voer **WPJCleanup. cmd** uit.</span><span class="sxs-lookup"><span data-stu-id="3bda8-168">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="3bda8-169">Met dit hulpprogramma wordt het juiste uitvoerbare bestand geopend op basis van de versie van Windows op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-169">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="3bda8-170">Met behulp van een mechanisme, zoals Groepsbeleid, kan de beheerder de opdracht op het apparaat uitvoeren in de context van elke gebruiker die zich op het apparaat heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="3bda8-170">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="3bda8-171">Als u wilt dat webaccount manager vraagt om het apparaat te registreren in azure AD, voegt u deze registerwaarde toe:</span><span class="sxs-lookup"><span data-stu-id="3bda8-171">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="3bda8-172">Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="3bda8-172">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="3bda8-173">Type: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="3bda8-173">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="3bda8-174">Naam: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="3bda8-174">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="3bda8-175">Waardegegevens: 1</span><span class="sxs-lookup"><span data-stu-id="3bda8-175">Value data: 1</span></span>

<span data-ttu-id="3bda8-176">De aanwezigheid van deze registerwaarde moet de verbinding voor werkplek blokkeren en voorkomen dat gebruikers prompts zien om lid te worden van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-176">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="3bda8-177">Android</span><span class="sxs-lookup"><span data-stu-id="3bda8-177">Android</span></span>

<span data-ttu-id="3bda8-178">Voor Android moeten gebruikers hun apparaten registreren en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-178">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="3bda8-179">U kunt dit doen via de Microsoft Authenticator-app of de bedrijfsportal-app.</span><span class="sxs-lookup"><span data-stu-id="3bda8-179">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="3bda8-180">Via de Microsoft Authenticator-app kunnen gebruikers naar **instellingen > apparaatregistratie** gaan.</span><span class="sxs-lookup"><span data-stu-id="3bda8-180">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="3bda8-181">Van de gebruikers kunnen zich registreren en het apparaat opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-181">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="3bda8-182">Vanuit de bedrijfs portal kunnen gebruikers naar het tabblad **apparaten** gaan en het apparaat verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-182">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="3bda8-183">Registreer vervolgens het apparaat opnieuw via de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="3bda8-183">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="3bda8-184">Gebruikers kunnen zich ook registreren en opnieuw registreren door het account uit de pagina Accountinstellingen te verwijderen en vervolgens de werkaccount opnieuw toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-184">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="3bda8-185">Met de Microsoft Authenticator-app kunt u de registratie en het apparaat opnieuw registreren voor Android met behulp van de Microsoft Authenticator-app:</span><span class="sxs-lookup"><span data-stu-id="3bda8-185">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="3bda8-186">Open de Microsoft Authenticator-app en ga naar **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-186">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="3bda8-187">Selecteer **apparaatregistratie**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-187">Select **Device registration**.</span></span>
3.  <span data-ttu-id="3bda8-188">Hef de registratie van het apparaat op door **register** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-188">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="3bda8-189">Voor apparaatregistratie meldt u het apparaat **opnieuw aan door** uw e-mailadres te typen en vervolgens **registreren** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-189">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="3bda8-190">De registratie van een Android-apparaat opheffen en opnieuw registreren met de pagina Android-instellingen:</span><span class="sxs-lookup"><span data-stu-id="3bda8-190">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="3bda8-191">Open **device settings** en ga naar **accounts**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-191">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="3bda8-192">Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **account verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-192">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="3bda8-193">Nadat het account is verwijderd, selecteert u op de pagina **accounts** de optie **account toevoegen > werkaccount**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-193">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="3bda8-194">Voor **Workplace join** typt u uw e-mailadres en selecteert u **deelnemen** om het registreren van het apparaat te voltooien.</span><span class="sxs-lookup"><span data-stu-id="3bda8-194">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="3bda8-195">Als u het apparaat wilt registreren en opnieuw wilt registreren voor Android vanuit de bedrijfs portal, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="3bda8-195">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="3bda8-196">Start Company Portal en ga naar het tabblad **apparaten** .</span><span class="sxs-lookup"><span data-stu-id="3bda8-196">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="3bda8-197">Selecteer het apparaat om de details van het apparaat te zien.</span><span class="sxs-lookup"><span data-stu-id="3bda8-197">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="3bda8-198">Selecteer in het menu weglatingstekens (drie puntjes) de optie **apparaat verwijderen** en voltooi de verwijdering door het dialoogvenster te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-198">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="3bda8-199">U dient nu af te melden bij de bedrijfs portal-app.</span><span class="sxs-lookup"><span data-stu-id="3bda8-199">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="3bda8-200">Selecteer **Aanmelden** om het apparaat opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-200">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="3bda8-201">Zie de informatie over Azure Active Directory (Azure AD) in [extra Azure AD-informatie voor de migratie van Microsoft Cloud-Deutschland](ms-cloud-germany-transition-azure-ad.md)voor meer informatie over de acties die moeten worden uitgevoerd tijdens de migratie fase van deze werkbelasting of van invloed zijn op beheer of gebruik.</span><span class="sxs-lookup"><span data-stu-id="3bda8-201">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="3bda8-202">Apparaten</span><span class="sxs-lookup"><span data-stu-id="3bda8-202">iOS</span></span>

<span data-ttu-id="3bda8-203">Op iOS-apparaten moet een gebruiker alle in de cache opgeslagen accounts handmatig verwijderen van de Microsoft Authenticator, de registratie van het apparaat opheffen en u afmelden bij een willekeurige app op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="3bda8-203">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="3bda8-204">Stap 1: indien aanwezig, verwijdert u het account uit de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="3bda8-204">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="3bda8-205">Tik op het account in de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="3bda8-205">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="3bda8-206">Tik in de rechterbovenhoek op het pictogram **instellingen** .</span><span class="sxs-lookup"><span data-stu-id="3bda8-206">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="3bda8-207">Als u het pictogram **instellingen** niet ziet, gebruikt u mogelijk niet de meest recente versie van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="3bda8-207">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="3bda8-208">Tik op de knop **account verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="3bda8-208">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="3bda8-209">Tik **op alle apps op dit apparaat**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-209">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="3bda8-210">Stap 2: het apparaat uit de Microsoft Authenticator-app verwijderen</span><span class="sxs-lookup"><span data-stu-id="3bda8-210">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="3bda8-211">Tik op het menupictogram in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="3bda8-211">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="3bda8-212">Tik op **instellingen** en vervolgens op **apparaatregistratie**.</span><span class="sxs-lookup"><span data-stu-id="3bda8-212">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="3bda8-213">Als uw account wordt weergegeven, tikt u op **apparaat registreren** en **gaat u door** in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="3bda8-213">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="3bda8-214">U ziet geen account meer.</span><span class="sxs-lookup"><span data-stu-id="3bda8-214">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="3bda8-215">Stap 3: zo nodig afmelden bij afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="3bda8-215">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="3bda8-216">Gebruikers kunnen naar afzonderlijke apps, zoals Outlook, teams en OneDrive, gaan en accounts van die apps verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3bda8-216">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="3bda8-217">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="3bda8-217">More information</span></span>

<span data-ttu-id="3bda8-218">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="3bda8-218">Getting started:</span></span>

- [<span data-ttu-id="3bda8-219">Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden</span><span class="sxs-lookup"><span data-stu-id="3bda8-219">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="3bda8-220">Migratie ondersteuning voor Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="3bda8-220">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="3bda8-221">Hoe kan ik me aanmelden voor migratie?</span><span class="sxs-lookup"><span data-stu-id="3bda8-221">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="3bda8-222">Gebruikerservaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="3bda8-222">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="3bda8-223">Door de overgang navigeren:</span><span class="sxs-lookup"><span data-stu-id="3bda8-223">Moving through the transition:</span></span>

- [<span data-ttu-id="3bda8-224">Acties en effecten voor de migratiefasen</span><span class="sxs-lookup"><span data-stu-id="3bda8-224">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="3bda8-225">Extra vooraf werken</span><span class="sxs-lookup"><span data-stu-id="3bda8-225">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="3bda8-226">Aanvullende informatie over [Azure AD](ms-cloud-germany-transition-azure-ad.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="3bda8-226">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="3bda8-227">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="3bda8-227">Cloud apps:</span></span>

- [<span data-ttu-id="3bda8-228">Dynamics 365-migratieprogramma gegevens</span><span class="sxs-lookup"><span data-stu-id="3bda8-228">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="3bda8-229">Informatie over migratieprogramma's voor Power BI</span><span class="sxs-lookup"><span data-stu-id="3bda8-229">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="3bda8-230">Aan de slag met uw upgrade naar Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="3bda8-230">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
