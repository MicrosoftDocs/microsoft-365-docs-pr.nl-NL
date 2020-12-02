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
ms.openlocfilehash: da05a3c2eb6a8d579c53d403a1ef575c389eda12
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551951"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="a6646-103">Aanvullende informatie over apparaten voor de migratie van Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="a6646-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a6646-104">Veelgestelde vragen</span><span class="sxs-lookup"><span data-stu-id="a6646-104">Frequently asked questions</span></span>

<span data-ttu-id="a6646-105">**Hoe weet ik of mijn organisatie van invloed is?**</span><span class="sxs-lookup"><span data-stu-id="a6646-105">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="a6646-106">Beheerders moeten `https://portal.microsoftazure.de` nagaan of ze geregistreerde apparaten hebben.</span><span class="sxs-lookup"><span data-stu-id="a6646-106">Administrators should check `https://portal.microsoftazure.de` to determine if they have any registered devices.</span></span> <span data-ttu-id="a6646-107">Als uw organisatie geregistreerde apparaten heeft, hebt u last van.</span><span class="sxs-lookup"><span data-stu-id="a6646-107">If your organization has registered devices, you're affected.</span></span>

<span data-ttu-id="a6646-108">**Wat is de gevolgen voor mijn gebruikers?**</span><span class="sxs-lookup"><span data-stu-id="a6646-108">**What is the impact on my users?**</span></span>

<span data-ttu-id="a6646-109">Gebruikers van een geregistreerd apparaat kunnen zich niet meer aanmelden nadat de migratie is voltooid met de [Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) -migratie fase.</span><span class="sxs-lookup"><span data-stu-id="a6646-109">Users from a registered device will no longer be able to sign in after your migration enters the [Finalize Azure AD](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>  

<span data-ttu-id="a6646-110">Zorg ervoor dat al uw apparaten geregistreerd zijn met het wereldwijde eindpunt voordat uw organisatie wordt losgekoppeld van Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="a6646-110">Ensure that all of your devices are registered with the worldwide endpoint before your organization is disconnected from Microsoft Cloud Deutschland.</span></span>
  
<span data-ttu-id="a6646-111">**Wanneer worden mijn gebruikers hun apparaten opnieuw registreren?**</span><span class="sxs-lookup"><span data-stu-id="a6646-111">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="a6646-112">Het is belangrijk dat u het niet meer registreert en uw apparaten opnieuw registreert onder de migratie fase [van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) .</span><span class="sxs-lookup"><span data-stu-id="a6646-112">It's critical to your success that you only unregister and re-register your devices during the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="a6646-113">**Hoe kan ik de status van mijn apparaat na migratie herstellen?**</span><span class="sxs-lookup"><span data-stu-id="a6646-113">**How do I restore my device state after migration?**</span></span>

<span data-ttu-id="a6646-114">Voor hybride Azure AD-en bedrijfsgeschikte Windows-apparaten die zijn geregistreerd bij Azure AD, kunnen beheerders de migratie van deze apparaten beheren via externe, geactiveerde werkstromen waarmee de registratie van de oude status van het oude apparaat wordt opgeheven.</span><span class="sxs-lookup"><span data-stu-id="a6646-114">For hybrid Azure AD–joined and company-owned Windows devices that are registered with Azure AD, administrators will be able to manage the migration of these devices through remotely triggered workflows that will unregister the old device states.</span></span>
  
<span data-ttu-id="a6646-115">Voor alle andere apparaten, waaronder persoonlijke Windows-apparaten die in azure AD zijn geregistreerd, moet de eindgebruiker deze stappen handmatig uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a6646-115">For all other devices, including personal Windows devices that are registered in Azure AD, the end user must perform these steps manually.</span></span> <span data-ttu-id="a6646-116">Voor Azure AD – gekoppelde apparaten moet de gebruiker een lokaal beheerdersaccount hebben om de registratie te deactiveren en de apparaten vervolgens opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="a6646-116">For Azure AD–joined devices, users need to have a local administrator account to unregister and then re-register their devices.</span></span>

<span data-ttu-id="a6646-117">In Microsoft wordt de instructies gepubliceerd voor het herstellen van de status van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-117">Microsoft will publish instructions for how to successfully restore device state.</span></span> 
 
<span data-ttu-id="a6646-118">**Hoe weet ik of al mijn apparaten geregistreerd zijn in de openbare Cloud?**</span><span class="sxs-lookup"><span data-stu-id="a6646-118">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="a6646-119">Als u wilt controleren of de apparaten in de openbare Cloud zijn geregistreerd, moet u de lijst met apparaten in de Azure AD-Portal exporteren naar een Excel-spreadsheet en deze downloaden.</span><span class="sxs-lookup"><span data-stu-id="a6646-119">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="a6646-120">Vervolgens kunt u de geregistreerde apparaten filteren (met behulp van de kolom _registeredTime_ ), na de [afzonderlijke migratie van Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migratie fase.</span><span class="sxs-lookup"><span data-stu-id="a6646-120">Then, filter the devices that are registered (by using the _registeredTime_ column) after the [Separate from Microsoft Cloud Deutschland](ms-cloud-germany-transition.md#how-is-the-migration-organized) migration phase.</span></span>

<span data-ttu-id="a6646-121">Apparaatregistratie wordt gedeactiveerd na migratie van de Tenant en kan niet worden ingeschakeld of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a6646-121">Device registration is deactivated after migration of the tenant and cannot be enabled or disabled.</span></span> <span data-ttu-id="a6646-122">Als intune niet wordt gebruikt, meldt u zich aan bij uw abonnement en voert u deze opdracht uit om de optie weer te activeren:</span><span class="sxs-lookup"><span data-stu-id="a6646-122">If Intune is not used, sign in to your subscription and run this command to re-activate the option:</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="windows-hybrid-azure-ad-join"></a><span data-ttu-id="a6646-123">Windows Hybrid Azure AD join</span><span class="sxs-lookup"><span data-stu-id="a6646-123">Windows Hybrid Azure AD join</span></span>

### <a name="windows-down-level"></a><span data-ttu-id="a6646-124">Windows-downlevel</span><span class="sxs-lookup"><span data-stu-id="a6646-124">Windows down-level</span></span>

<span data-ttu-id="a6646-125">_Windows-apparaten op een lager niveau_ zijn Windows-apparaten die op dit moment eerdere versies van Windows gebruiken (zoals Windows 8,1 of Windows 7) of die Windows Server-versies ouder dan 2019 en 2016 uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="a6646-125">_Windows down-level devices_ are Windows devices that currently run earlier versions of Windows (such as Windows 8.1 or Windows 7), or that run Windows Server versions earlier than 2019 and 2016.</span></span> <span data-ttu-id="a6646-126">Als deze apparatuur eerder geregistreerd is, moet u de registratie van deze apparaten ongedaan maken en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="a6646-126">If such devices were registered before, you'll need to unregister and re-register those devices.</span></span> 

<span data-ttu-id="a6646-127">Gebruik de volgende opdracht op het apparaat om te bepalen of een apparaat op het Windows-apparaat eerder lid is van Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a6646-127">To determine whether a Windows down-level device was previously joined to Azure AD, use following command on the device:</span></span>

```console
%programfiles%\Microsoft Workplace Join\autoworkplace /status
```

<span data-ttu-id="a6646-128">Als het apparaat eerder is verbonden met Azure AD en als het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="a6646-128">If the device was previously joined to Azure AD, and if the device has network connectivity to global Azure AD endpoints, you would see the following output:</span></span>

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

<span data-ttu-id="a6646-129">De beïnvloede apparaten hebben de ' apparaat State ' met de waarde ' onbekend '.</span><span class="sxs-lookup"><span data-stu-id="a6646-129">The affected devices will have the "Device state" with value of "Unknown".</span></span> <span data-ttu-id="a6646-130">Als de uitvoer de waarde ' apparaat niet meeneemt ' of waarvan de waarde ' apparaat State ' ' ' u ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="a6646-130">If the output is "Device not joined" or whose "Device state" value is "Okay", ignore the following guidance.</span></span>

<span data-ttu-id="a6646-131">Alleen voor apparaten die aangeven dat het apparaat is verbonden (op basis van deviceId, vingerafdruk, enzovoort) en waarvan de waarde ' apparaat State ' ' onbekend ' is, moeten beheerders de volgende opdracht uitvoeren in de context van een domeingebruiker die zich aanmeldt op een dergelijk apparaat met een lager niveau:</span><span class="sxs-lookup"><span data-stu-id="a6646-131">Only for devices that show that the device is joined (by virtue of deviceId, thumbprint, and so on) and whose "Device state" value is "Unknown", admins should run the following command in the context of a domain user signing in on such a down-level device:</span></span>

```console
"%programfiles%\Microsoft Workplace Join\autoworkplace /leave"
```

<span data-ttu-id="a6646-132">De bovenstaande opdracht hoeft slechts één keer per domeingebruiker te worden uitgevoerd op het Windows-apparaat op het niveau van het laagste niveau.</span><span class="sxs-lookup"><span data-stu-id="a6646-132">The preceding command only needs to be run once per domain user signing in on the Windows down-level device.</span></span> <span data-ttu-id="a6646-133">Deze opdracht moet worden uitgevoerd in de context van de domeingebruiker die zich aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="a6646-133">This command should be run in the context of the domain user signing in.</span></span> 

<span data-ttu-id="a6646-134">U dient deze opdracht niet uit te voeren wanneer de gebruiker zich daarna aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="a6646-134">Sufficient care must be taken to not run this command when the user subsequently signs in.</span></span> <span data-ttu-id="a6646-135">Wanneer de vorige opdracht wordt uitgevoerd, wordt de gekoppelde status gewist van de lokale hybride Azure AD-computer die is gekoppeld aan de gebruiker die zich heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="a6646-135">When the preceding command runs, it will clear the joined state of the local hybrid Azure AD–joined computer for the user who signed in.</span></span> <span data-ttu-id="a6646-136">En als de computer nog steeds is geconfigureerd voor hybride Azure AD – deelnemen aan de Tenant, wordt geprobeerd deel te nemen wanneer de gebruiker zich opnieuw aanmeldt.</span><span class="sxs-lookup"><span data-stu-id="a6646-136">And, if the computer is still configured to be hybrid Azure AD–joined in the tenant, it will attempt to join when the user signs in again.</span></span>

### <a name="windows-current"></a><span data-ttu-id="a6646-137">Windows-actueel</span><span class="sxs-lookup"><span data-stu-id="a6646-137">Windows Current</span></span>

#### <a name="unjoin"></a><span data-ttu-id="a6646-138">Ontkoppelen</span><span class="sxs-lookup"><span data-stu-id="a6646-138">Unjoin</span></span>

<span data-ttu-id="a6646-139">Voer de volgende opdracht uit op het apparaat om te controleren of het Windows 10-apparaat eerder lid is van Azure AD:</span><span class="sxs-lookup"><span data-stu-id="a6646-139">To determine whether the Windows 10 device was previously joined to Azure AD, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="a6646-140">Als het apparaat hybride Azure AD bevat, ziet de beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="a6646-140">If the device is hybrid Azure AD–joined, the admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : YES
```

<span data-ttu-id="a6646-141">Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="a6646-141">If the output is "AzureAdJoined : No", ignore the following guidance.</span></span>

<span data-ttu-id="a6646-142">Voor apparaten die aangeven dat het apparaat is verbonden met Azure AD, voert u de volgende opdracht uit als beheerder om de gekoppelde status van het apparaat te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a6646-142">Only for devices that show that the device is joined to Azure AD, run the following command as an admin to remove the joined state of the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="a6646-143">De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-143">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span>

#### <a name="hybrid-ad-joinre-registration"></a><span data-ttu-id="a6646-144">Hybrid AD Join\Re-Registration</span><span class="sxs-lookup"><span data-stu-id="a6646-144">Hybrid AD Join\Re-Registration</span></span>

<span data-ttu-id="a6646-145">Het apparaat maakt automatisch deel uit van Azure AD zonder dat de gebruiker of de beheerder van de beheerder zijn, zolang het apparaat netwerkverbinding heeft met globale Azure AD-eindpunten.</span><span class="sxs-lookup"><span data-stu-id="a6646-145">The device is automatically joined to Azure AD without user or admin intervention as long as the device has network connectivity to global Azure AD endpoints.</span></span> 


## <a name="windows-azure-ad-join"></a><span data-ttu-id="a6646-146">Deelnemen aan Windows Azure AD</span><span class="sxs-lookup"><span data-stu-id="a6646-146">Windows Azure AD Join</span></span>

### <a name="unjoin"></a><span data-ttu-id="a6646-147">Ontkoppelen</span><span class="sxs-lookup"><span data-stu-id="a6646-147">Unjoin</span></span>

<span data-ttu-id="a6646-148">Als u wilt controleren of het Windows 10-apparaat eerder is verbonden met Azure AD, kunt u de volgende opdracht op het apparaat uitvoeren met de gebruiker of beheerder:</span><span class="sxs-lookup"><span data-stu-id="a6646-148">To determine whether the Windows 10 device was previously joined to Azure AD, the user or admin can run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="a6646-149">Als het apparaat is verbonden met Azure AD, ziet de gebruiker of beheerder de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="a6646-149">If the device is joined to Azure AD, the user or admin would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| Device State                                                         |
+----------------------------------------------------------------------+
 
             AzureAdJoined : YES
          EnterpriseJoined : NO
              DomainJoined : NO
```

<span data-ttu-id="a6646-150">Als de uitvoer ' AzureAdJoined: Nee ' is, negeert u de volgende richtlijnen.</span><span class="sxs-lookup"><span data-stu-id="a6646-150">If the output is "AzureAdJoined : NO", ignore the following guidance.</span></span>

<span data-ttu-id="a6646-151">Gebruiker: als het apparaat Azure Active Directory is, kan een gebruiker het apparaat loskoppelen van de instellingen.</span><span class="sxs-lookup"><span data-stu-id="a6646-151">User: If the device is Azure AD joined, a user can unjoin the device from the settings.</span></span> <span data-ttu-id="a6646-152">Controleer of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding maakt met het apparaat via Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a6646-152">Verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="a6646-153">U moet het lokale beheerdersaccount opnieuw aanmelden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-153">The local administrator account is required to sign back into the device.</span></span>

<span data-ttu-id="a6646-154">Beheerder: als de beheerder van de organisatie wil deelnemen aan de apparaten van de gebruikers die lid zijn van Azure AD – u kunt dat doen door de volgende opdracht uit te voeren op alle apparaten met behulp van een mechanisme, zoals Groepsbeleid.</span><span class="sxs-lookup"><span data-stu-id="a6646-154">Admin: If the organization's admin wants to unjoin the users' devices that are Azure AD–joined, they can do so by running the following command on each of the devices by using a mechanism such as Group Policy.</span></span> <span data-ttu-id="a6646-155">De beheerder moet controleren of er een lokaal beheerdersaccount op het apparaat staat voordat u de verbinding met het apparaat via Azure AD verzorgt.</span><span class="sxs-lookup"><span data-stu-id="a6646-155">The admin must verify that there is a local administrator account on the device before unjoining the device from Azure AD.</span></span> <span data-ttu-id="a6646-156">Het lokale beheerdersaccount is nodig om u weer aan te melden bij het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-156">The local administrator account is needed to sign back into the device.</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /leave
```

<span data-ttu-id="a6646-157">De bovenstaande opdracht hoeft slechts eenmaal te worden uitgevoerd in een beheer context op het Windows-apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-157">The preceding command only needs to be run once in an administrative context on the Windows device.</span></span> 

### <a name="azure-ad-joinre-registration"></a><span data-ttu-id="a6646-158">Azure AD deelnemen/opnieuw registreren</span><span class="sxs-lookup"><span data-stu-id="a6646-158">Azure AD Join/Re-Registration</span></span>

<span data-ttu-id="a6646-159">De gebruiker kan deelnemen aan Azure AD via Windows-instellingen: **instellingen > Accounts > toegang tot werk of School > verbinding maken**.</span><span class="sxs-lookup"><span data-stu-id="a6646-159">The user can join the device to Azure AD from Windows settings: **Settings > Accounts > Access Work Or School > Connect**.</span></span>
 

## <a name="windows-azure-ad-registered-company-owned"></a><span data-ttu-id="a6646-160">Geregistreerde Windows Azure AD (bedrijfseigenaar)</span><span class="sxs-lookup"><span data-stu-id="a6646-160">Windows Azure AD Registered (Company owned)</span></span>

<span data-ttu-id="a6646-161">Voer de volgende opdracht uit op het apparaat om te controleren of het apparaat met Windows 10 Azure AD is geregistreerd:</span><span class="sxs-lookup"><span data-stu-id="a6646-161">To determine whether the Windows 10 device is Azure AD–registered, run the following command on the device:</span></span>

```console
%SystemRoot%\system32\dsregcmd.exe /status
```

<span data-ttu-id="a6646-162">Als Azure AD is geregistreerd, ziet u de volgende uitvoer:</span><span class="sxs-lookup"><span data-stu-id="a6646-162">If the device is Azure AD Registered, you would see the following output:</span></span>

```console
+----------------------------------------------------------------------+
| User State                                                           |
+----------------------------------------------------------------------+
           WorkplaceJoined : YES
          WamDefaultSet : NO
          WamDefaultAuthority : organizations
```

<span data-ttu-id="a6646-163">U kunt als volgt het bestaande in azure AD geregistreerde account van het apparaat verwijderen:</span><span class="sxs-lookup"><span data-stu-id="a6646-163">To remove the existing Azure AD-registered account on the device:</span></span>

- <span data-ttu-id="a6646-164">Als u het door u geregistreerde Azure AD-account op het apparaat wilt verwijderen, gebruikt u CleanupWPJ, een hulpmiddel dat u kunt downloaden: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span><span class="sxs-lookup"><span data-stu-id="a6646-164">To remove the Azure AD–registered account on the device, use CleanupWPJ, a tool that you can download from here: [CleanupWPJ.zip](https://download.microsoft.com/download/8/e/f/8ef13ae0-6aa8-48a2-8697-5b1711134730/WPJCleanUp.zip).</span></span>

- <span data-ttu-id="a6646-165">Uitpak het ZIP-bestand en voer **WPJCleanup. cmd** uit.</span><span class="sxs-lookup"><span data-stu-id="a6646-165">Extract the ZIP file and run **WPJCleanup.cmd**.</span></span> <span data-ttu-id="a6646-166">Met dit hulpprogramma wordt het juiste uitvoerbare bestand geopend op basis van de versie van Windows op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-166">This tool will launch the right executable based on the version of Windows on the device.</span></span>

- <span data-ttu-id="a6646-167">Met behulp van een mechanisme, zoals Groepsbeleid, kan de beheerder de opdracht op het apparaat uitvoeren in de context van elke gebruiker die zich op het apparaat heeft aangemeld.</span><span class="sxs-lookup"><span data-stu-id="a6646-167">By using a mechanism like Group Policy, the admin can run the command on the device in the context of any user who is signed in on the device.</span></span>

<span data-ttu-id="a6646-168">Als u wilt dat webaccount manager vraagt om het apparaat te registreren in azure AD, voegt u deze registerwaarde toe:</span><span class="sxs-lookup"><span data-stu-id="a6646-168">To disable Web Account Manager prompts to register the device in Azure AD, add this registry value:</span></span> 

- <span data-ttu-id="a6646-169">Locatie: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="a6646-169">Location: HKLM\SOFTWARE\Policies\Microsoft\Windows\WorkplaceJoin</span></span>
- <span data-ttu-id="a6646-170">Type: DWORD (32 bits)</span><span class="sxs-lookup"><span data-stu-id="a6646-170">Type: DWORD (32 bit)</span></span>
- <span data-ttu-id="a6646-171">Naam: BlockAADWorkplaceJoin</span><span class="sxs-lookup"><span data-stu-id="a6646-171">Name: BlockAADWorkplaceJoin</span></span>
- <span data-ttu-id="a6646-172">Waardegegevens: 1</span><span class="sxs-lookup"><span data-stu-id="a6646-172">Value data: 1</span></span>

<span data-ttu-id="a6646-173">De aanwezigheid van deze registerwaarde moet de verbinding voor werkplek blokkeren en voorkomen dat gebruikers prompts zien om lid te worden van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-173">The presence of this registry value should block workplace join and prevent users from seeing prompts to join the device.</span></span>

## <a name="android"></a><span data-ttu-id="a6646-174">Android</span><span class="sxs-lookup"><span data-stu-id="a6646-174">Android</span></span>

<span data-ttu-id="a6646-175">Voor Android moeten gebruikers hun apparaten registreren en opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="a6646-175">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="a6646-176">U kunt dit doen via de Microsoft Authenticator-app of de bedrijfsportal-app.</span><span class="sxs-lookup"><span data-stu-id="a6646-176">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span> 

- <span data-ttu-id="a6646-177">Via de Microsoft Authenticator-app kunnen gebruikers naar **instellingen > apparaatregistratie** gaan.</span><span class="sxs-lookup"><span data-stu-id="a6646-177">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="a6646-178">Van de gebruikers kunnen zich registreren en het apparaat opnieuw registreren.</span><span class="sxs-lookup"><span data-stu-id="a6646-178">From there users can unregister and re-register their device.</span></span>
 
- <span data-ttu-id="a6646-179">Vanuit de bedrijfs portal kunnen gebruikers naar het tabblad **apparaten** gaan en het apparaat verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a6646-179">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="a6646-180">Registreer vervolgens het apparaat opnieuw via de bedrijfs portal.</span><span class="sxs-lookup"><span data-stu-id="a6646-180">After that, re-enroll the device by using Company Portal.</span></span>
 
- <span data-ttu-id="a6646-181">Gebruikers kunnen zich ook registreren en opnieuw registreren door het account uit de pagina Accountinstellingen te verwijderen en vervolgens de werkaccount opnieuw toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="a6646-181">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="a6646-182">Met de Microsoft Authenticator-app kunt u de registratie en het apparaat opnieuw registreren voor Android met behulp van de Microsoft Authenticator-app:</span><span class="sxs-lookup"><span data-stu-id="a6646-182">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1.  <span data-ttu-id="a6646-183">Open de Microsoft Authenticator-app en ga naar **instellingen**.</span><span class="sxs-lookup"><span data-stu-id="a6646-183">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2.  <span data-ttu-id="a6646-184">Selecteer **apparaatregistratie**.</span><span class="sxs-lookup"><span data-stu-id="a6646-184">Select **Device registration**.</span></span>
3.  <span data-ttu-id="a6646-185">Hef de registratie van het apparaat op door **register** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a6646-185">Unregister the device by selecting **Unregister**.</span></span>
4.  <span data-ttu-id="a6646-186">Voor apparaatregistratie meldt u het apparaat **opnieuw aan door** uw e-mailadres te typen en vervolgens **registreren** te selecteren.</span><span class="sxs-lookup"><span data-stu-id="a6646-186">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="a6646-187">De registratie van een Android-apparaat opheffen en opnieuw registreren met de pagina Android-instellingen:</span><span class="sxs-lookup"><span data-stu-id="a6646-187">To unregister and re-register an Android device with the Android Settings page:</span></span>

1.  <span data-ttu-id="a6646-188">Open **device settings** en ga naar **accounts**.</span><span class="sxs-lookup"><span data-stu-id="a6646-188">Open **Device Settings** and go to **Accounts**.</span></span>
2.  <span data-ttu-id="a6646-189">Selecteer het werkaccount dat u opnieuw wilt registreren en selecteer **account verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="a6646-189">Select the work account that you want to re-register and select **Remove account**.</span></span>
3.  <span data-ttu-id="a6646-190">Nadat het account is verwijderd, selecteert u op de pagina **accounts** de optie **account toevoegen > werkaccount**.</span><span class="sxs-lookup"><span data-stu-id="a6646-190">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4.  <span data-ttu-id="a6646-191">Voor **Workplace join** typt u uw e-mailadres en selecteert u **deelnemen** om het registreren van het apparaat te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a6646-191">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="a6646-192">Als u het apparaat wilt registreren en opnieuw wilt registreren voor Android vanuit de bedrijfs portal, doet u het volgende:</span><span class="sxs-lookup"><span data-stu-id="a6646-192">To unregister and re-register the device on Android from Company Portal:</span></span>

1.  <span data-ttu-id="a6646-193">Start Company Portal en ga naar het tabblad **apparaten** .</span><span class="sxs-lookup"><span data-stu-id="a6646-193">Launch Company Portal and go to **Devices** tab.</span></span>
2.  <span data-ttu-id="a6646-194">Selecteer het apparaat om de details van het apparaat te zien.</span><span class="sxs-lookup"><span data-stu-id="a6646-194">Select the device to see the device details.</span></span>
3.  <span data-ttu-id="a6646-195">Selecteer in het menu weglatingstekens (drie puntjes) de optie **apparaat verwijderen** en voltooi de verwijdering door het dialoogvenster te bevestigen.</span><span class="sxs-lookup"><span data-stu-id="a6646-195">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4.  <span data-ttu-id="a6646-196">U dient nu af te melden bij de bedrijfs portal-app.</span><span class="sxs-lookup"><span data-stu-id="a6646-196">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="a6646-197">Selecteer **Aanmelden** om het apparaat opnieuw te registreren.</span><span class="sxs-lookup"><span data-stu-id="a6646-197">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="a6646-198">Zie de informatie over Azure Active Directory in [aanvullende algemene informatie over de migratie van Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory)voor meer informatie over de acties die moeten worden uitgevoerd tijdens de migratie fase van deze werkbelasting of van invloed zijn op beheer of gebruik.</span><span class="sxs-lookup"><span data-stu-id="a6646-198">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory in [Additional general information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-add-general.md#azure-active-directory).</span></span>

## <a name="ios"></a><span data-ttu-id="a6646-199">Apparaten</span><span class="sxs-lookup"><span data-stu-id="a6646-199">iOS</span></span>

<span data-ttu-id="a6646-200">Op iOS-apparaten moet een gebruiker alle in de cache opgeslagen accounts handmatig verwijderen van de Microsoft Authenticator, de registratie van het apparaat opheffen en u afmelden bij een willekeurige app op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="a6646-200">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="a6646-201">Stap 1: indien aanwezig, verwijdert u het account uit de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="a6646-201">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="a6646-202">Tik op het account in de Microsoft Authenticator-app.</span><span class="sxs-lookup"><span data-stu-id="a6646-202">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="a6646-203">Tik in de rechterbovenhoek op het pictogram **instellingen** .</span><span class="sxs-lookup"><span data-stu-id="a6646-203">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="a6646-204">Als u het pictogram **instellingen** niet ziet, gebruikt u mogelijk niet de meest recente versie van Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="a6646-204">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="a6646-205">Tik op de knop **account verwijderen** .</span><span class="sxs-lookup"><span data-stu-id="a6646-205">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="a6646-206">Tik **op alle apps op dit apparaat**.</span><span class="sxs-lookup"><span data-stu-id="a6646-206">Tap **All apps on this device**.</span></span>
 
### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="a6646-207">Stap 2: het apparaat uit de Microsoft Authenticator-app verwijderen</span><span class="sxs-lookup"><span data-stu-id="a6646-207">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="a6646-208">Tik op het menupictogram in de rechterbovenhoek.</span><span class="sxs-lookup"><span data-stu-id="a6646-208">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="a6646-209">Tik op **instellingen** en vervolgens op **apparaatregistratie**.</span><span class="sxs-lookup"><span data-stu-id="a6646-209">Tap **Settings** and then **Device Registration**.</span></span>
4. <span data-ttu-id="a6646-210">Als uw account wordt weergegeven, tikt u op **apparaat registreren** en **gaat u door** in het dialoogvenster.</span><span class="sxs-lookup"><span data-stu-id="a6646-210">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="a6646-211">U ziet geen account meer.</span><span class="sxs-lookup"><span data-stu-id="a6646-211">You should see no account after that.</span></span>
 
### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="a6646-212">Stap 3: zo nodig afmelden bij afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="a6646-212">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="a6646-213">Gebruikers kunnen naar afzonderlijke apps, zoals Outlook, teams en OneDrive, gaan en accounts van die apps verwijderen.</span><span class="sxs-lookup"><span data-stu-id="a6646-213">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="more-information"></a><span data-ttu-id="a6646-214">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="a6646-214">More information</span></span>

<span data-ttu-id="a6646-215">Aan de slag:</span><span class="sxs-lookup"><span data-stu-id="a6646-215">Getting started:</span></span>

- [<span data-ttu-id="a6646-216">Migratie van Microsoft Cloud Deutschland naar Office 365-Services in de nieuwe Duitse datacenter gebieden</span><span class="sxs-lookup"><span data-stu-id="a6646-216">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="a6646-217">Migratie ondersteuning voor Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="a6646-217">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="a6646-218">Hoe kan ik me aanmelden voor migratie?</span><span class="sxs-lookup"><span data-stu-id="a6646-218">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="a6646-219">Gebruikerservaring tijdens de migratie</span><span class="sxs-lookup"><span data-stu-id="a6646-219">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="a6646-220">Door de overgang navigeren:</span><span class="sxs-lookup"><span data-stu-id="a6646-220">Moving through the transition:</span></span>

- [<span data-ttu-id="a6646-221">Acties en effecten bij migratie fasen</span><span class="sxs-lookup"><span data-stu-id="a6646-221">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="a6646-222">Extra vooraf werken</span><span class="sxs-lookup"><span data-stu-id="a6646-222">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="a6646-223">Aanvullende informatie over [Services](ms-cloud-germany-transition-add-general.md), [apparaten](ms-cloud-germany-transition-add-devices.md), [ervaringen](ms-cloud-germany-transition-add-experience.md)en [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="a6646-223">Additional information for [services](ms-cloud-germany-transition-add-general.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="a6646-224">Cloud-apps:</span><span class="sxs-lookup"><span data-stu-id="a6646-224">Cloud apps:</span></span>

- [<span data-ttu-id="a6646-225">Dynamics 365-migratieprogramma gegevens</span><span class="sxs-lookup"><span data-stu-id="a6646-225">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="a6646-226">Informatie over migratieprogramma's voor Power BI</span><span class="sxs-lookup"><span data-stu-id="a6646-226">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="a6646-227">Aan de slag met uw upgrade naar Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a6646-227">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
