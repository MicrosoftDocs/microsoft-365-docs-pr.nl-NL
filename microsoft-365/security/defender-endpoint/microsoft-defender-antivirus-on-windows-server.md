---
title: Microsoft Defender Antivirus op Windows Server
description: Meer informatie over het inschakelen en configureren Microsoft Defender Antivirus op Windows Server 2016 en Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: fde1e20eedc50b37fca17dc9dc17dc1c9f1373fa
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246438"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="971a1-104">Microsoft Defender Antivirus op Windows Server</span><span class="sxs-lookup"><span data-stu-id="971a1-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="971a1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="971a1-105">**Applies to:**</span></span>

- [<span data-ttu-id="971a1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="971a1-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="971a1-107">Microsoft Defender Antivirus is beschikbaar in de volgende versies/versies van Windows Server:</span><span class="sxs-lookup"><span data-stu-id="971a1-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="971a1-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="971a1-108">Windows Server 2019</span></span>
- <span data-ttu-id="971a1-109">Windows Server, versie 1803 of hoger</span><span class="sxs-lookup"><span data-stu-id="971a1-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="971a1-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="971a1-110">Windows Server 2016.</span></span> 

<span data-ttu-id="971a1-111">In sommige gevallen wordt Microsoft Defender Antivirus aangeduid als *Endpoint Protection;* De protection engine is echter hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="971a1-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="971a1-112">Hoewel de functionaliteit, configuratie en beheer grotendeels hetzelfde zijn voor Microsoft Defender Antivirus op [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)zijn er een paar belangrijke verschillen op Windows Server:</span><span class="sxs-lookup"><span data-stu-id="971a1-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="971a1-113">Op Windows Server worden [automatische uitsluitingen](configure-server-exclusions-microsoft-defender-antivirus.md) toegepast op basis van uw gedefinieerde serverrol.</span><span class="sxs-lookup"><span data-stu-id="971a1-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="971a1-114">Als Windows server een niet-Microsoft antivirus-/antimalware-oplossing gebruikt, wordt Microsoft Defender Antivirus niet automatisch in de passieve modus of uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="971a1-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="971a1-115">U kunt de Microsoft Defender Antivirus echter handmatig instellen op passieve of uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="971a1-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="971a1-116">Het instellen Microsoft Defender Antivirus op Windows Server</span><span class="sxs-lookup"><span data-stu-id="971a1-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="971a1-117">Het proces van het instellen en uitvoeren van Microsoft Defender Antivirus op een serverplatform bevat verschillende stappen:</span><span class="sxs-lookup"><span data-stu-id="971a1-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="971a1-118">[Schakel de interface in.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="971a1-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="971a1-119">[Installeer Microsoft Defender Antivirus.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="971a1-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="971a1-120">[Controleer Microsoft Defender Antivirus wordt uitgevoerd.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="971a1-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="971a1-121">[Werk uw antimalwarebeveiligingsinformatie bij.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="971a1-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="971a1-122">(Indien nodig) [Steekproeven indienen](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="971a1-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="971a1-123">(Indien nodig) [Automatische uitsluitingen configureren.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="971a1-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="971a1-124">(Alleen indien nodig) [Stel Microsoft Defender Antivirus in op passieve modus.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="971a1-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="971a1-125">De gebruikersinterface op Windows server inschakelen</span><span class="sxs-lookup"><span data-stu-id="971a1-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="971a1-126">Standaard is Microsoft Defender Antivirus geïnstalleerd en functioneel op Windows Server.</span><span class="sxs-lookup"><span data-stu-id="971a1-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="971a1-127">Soms is de gebruikersinterface (GUI) standaard geïnstalleerd, maar is de GUI niet vereist.</span><span class="sxs-lookup"><span data-stu-id="971a1-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="971a1-128">U kunt PowerShell, Groepsbeleid of andere methoden gebruiken om de Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="971a1-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="971a1-129">Als de GUI niet is geïnstalleerd op uw server en u deze wilt installeren, kunt u de **wizard** Rollen en functies toevoegen of PowerShell-cmdlets gebruiken.</span><span class="sxs-lookup"><span data-stu-id="971a1-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="971a1-130">De GUI in- of uit te zetten met de wizard Rollen en functies toevoegen</span><span class="sxs-lookup"><span data-stu-id="971a1-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="971a1-131">Zie [Rollen, rollenservices](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)en functies installeren met de wizard Rollen en functies toevoegen en gebruik de wizard Rollen **en functies toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="971a1-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="971a1-132">Wanneer u bij de stap **Functies** van de wizard bent, **selecteert** u onder Windows Defender functies de gui voor **Windows Defender** optie.</span><span class="sxs-lookup"><span data-stu-id="971a1-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="971a1-133">In Windows Server 2016 ziet de wizard **Rollen en functies** toevoegen er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="971a1-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Rollen en functiewizard toevoegen met de optie GUI voor Windows Defender](images/server-add-gui.png)

   <span data-ttu-id="971a1-135">In Windows Server 2019 is de wizard Rollen **en functies** toevoegen vergelijkbaar.</span><span class="sxs-lookup"><span data-stu-id="971a1-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="971a1-136">De GUI in-en-uit met PowerShell</span><span class="sxs-lookup"><span data-stu-id="971a1-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="971a1-137">Met de volgende PowerShell-cmdlet wordt de interface ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="971a1-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="971a1-138">Installatie Microsoft Defender Antivirus op Windows Server</span><span class="sxs-lookup"><span data-stu-id="971a1-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="971a1-139">Als u een Microsoft Defender Antivirus server wilt installeren Windows opnieuw installeren, kunt u dit  doen met de wizard Rollen en functies toevoegen of PowerShell.</span><span class="sxs-lookup"><span data-stu-id="971a1-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="971a1-140">Gebruik de wizard Rollen en functies toevoegen om de Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="971a1-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="971a1-141">Raadpleeg dit [artikel en](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)gebruik de wizard Rollen en **functies toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="971a1-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="971a1-142">Wanneer u bij de stap **Functies** van de wizard bent, selecteert u de Microsoft Defender Antivirus optie.</span><span class="sxs-lookup"><span data-stu-id="971a1-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="971a1-143">Selecteer ook de **gui voor Windows Defender** optie.</span><span class="sxs-lookup"><span data-stu-id="971a1-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="971a1-144">PowerShell gebruiken om een Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="971a1-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="971a1-145">Als u PowerShell wilt gebruiken om Microsoft Defender Antivirus te installeren, voer u de volgende cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="971a1-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="971a1-146">Gebeurtenisberichten voor de antimalware-engine die bij Microsoft Defender Antivirus zijn te vinden in [Microsoft Defender AV Events.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="971a1-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="971a1-147">Controleren Microsoft Defender Antivirus wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="971a1-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="971a1-148">Nadat Microsoft Defender Antivirus is geïnstalleerd, is de volgende stap om te controleren of deze wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="971a1-149">Voer op Windows Server-eindpunt de volgende PowerShell-cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="971a1-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="971a1-150">Voer de volgende PowerShell-cmdlet uit om te controleren of firewallbeveiliging is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="971a1-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="971a1-151">Als alternatief voor PowerShell kunt u opdrachtprompt gebruiken om te controleren of Microsoft Defender Antivirus wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="971a1-152">Voer de volgende opdracht uit vanuit een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="971a1-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="971a1-153">De `sc query` opdracht retourneert informatie over de Microsoft Defender Antivirus service.</span><span class="sxs-lookup"><span data-stu-id="971a1-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="971a1-154">Wanneer Microsoft Defender Antivirus wordt uitgevoerd, wordt `STATE` de waarde `RUNNING` weergegeven.</span><span class="sxs-lookup"><span data-stu-id="971a1-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="971a1-155">Antimalware-beveiligingsinformatie bijwerken</span><span class="sxs-lookup"><span data-stu-id="971a1-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="971a1-156">Als u bijgewerkte antimalwarebeveiligingsinformatie wilt downloaden, moet de Windows Update-service hebben uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="971a1-157">Als u een updatebeheerservice gebruikt, zoals Windows Server Update Services (WSUS), moet u ervoor zorgen dat updates voor Microsoft Defender Antivirus Beveiligingsinformatie worden goedgekeurd voor de computers die u beheert.</span><span class="sxs-lookup"><span data-stu-id="971a1-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="971a1-158">Standaard worden Windows Updates niet automatisch gedownload en geïnstalleerd op Windows Server 2019 of Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="971a1-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="971a1-159">U kunt deze configuratie wijzigen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="971a1-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="971a1-160">Methode</span><span class="sxs-lookup"><span data-stu-id="971a1-160">Method</span></span>  |<span data-ttu-id="971a1-161">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="971a1-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="971a1-162">**Windows Bijwerken** in configuratiescherm</span><span class="sxs-lookup"><span data-stu-id="971a1-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="971a1-163">- **Als u updates installeert,** worden alle updates automatisch geïnstalleerd, Windows Defender beveiligingsinformatieupdates.</span><span class="sxs-lookup"><span data-stu-id="971a1-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="971a1-164">- **Updates downloaden, maar laat me kiezen** of u ze wilt installeren, Windows Defender beveiligingsinformatieupdates automatisch kunnen downloaden en installeren, maar andere updates worden niet automatisch geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="971a1-165">**Groepsbeleid**</span><span class="sxs-lookup"><span data-stu-id="971a1-165">**Group Policy**</span></span>     | <span data-ttu-id="971a1-166">U kunt Windows Bijwerken instellen en beheren met behulp van de instellingen die beschikbaar zijn in groepsbeleid, in het volgende pad: **Beheersjablonen\Windows Onderdelen\Windows Bijwerken\Automatische updates configureren**</span><span class="sxs-lookup"><span data-stu-id="971a1-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="971a1-167">De **AUOptions-registersleutel**</span><span class="sxs-lookup"><span data-stu-id="971a1-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="971a1-168">Met de volgende twee waarden Windows Update automatisch beveiligingsinformatieupdates downloaden en installeren:</span><span class="sxs-lookup"><span data-stu-id="971a1-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="971a1-169">- **4**  -  **Updates automatisch installeren.**</span><span class="sxs-lookup"><span data-stu-id="971a1-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="971a1-170">Deze waarde resulteert in het automatisch installeren van alle updates, Windows Defender beveiligingsinformatieupdates.</span><span class="sxs-lookup"><span data-stu-id="971a1-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="971a1-171">- **3**  -  **Download updates, maar laat me kiezen of ik ze wil installeren.**</span><span class="sxs-lookup"><span data-stu-id="971a1-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="971a1-172">Met deze waarde Windows Defender automatisch beveiligingsinformatie-updates downloaden en installeren, maar andere updates worden niet automatisch geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="971a1-173">Om ervoor te zorgen dat de beveiliging tegen malware wordt gehandhaafd, raden we u aan de volgende services in te stellen:</span><span class="sxs-lookup"><span data-stu-id="971a1-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="971a1-174">Windows Foutrapportage service</span><span class="sxs-lookup"><span data-stu-id="971a1-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="971a1-175">Windows Updateservice</span><span class="sxs-lookup"><span data-stu-id="971a1-175">Windows Update service</span></span>

<span data-ttu-id="971a1-176">De volgende tabel bevat de services voor Microsoft Defender Antivirus en de afhankelijke services.</span><span class="sxs-lookup"><span data-stu-id="971a1-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="971a1-177">Servicenaam</span><span class="sxs-lookup"><span data-stu-id="971a1-177">Service Name</span></span>|<span data-ttu-id="971a1-178">Bestandslocatie</span><span class="sxs-lookup"><span data-stu-id="971a1-178">File Location</span></span>|<span data-ttu-id="971a1-179">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="971a1-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="971a1-180">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="971a1-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="971a1-181">Dit is de belangrijkste Microsoft Defender Antivirus service die altijd moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="971a1-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="971a1-182">Windows Foutrapportage Service (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="971a1-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="971a1-183">Deze service stuurt foutrapporten terug naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="971a1-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="971a1-184">Windows Defender Firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="971a1-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="971a1-185">Het is raadzaam om de Windows Defender Firewall service ingeschakeld te laten.</span><span class="sxs-lookup"><span data-stu-id="971a1-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="971a1-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="971a1-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="971a1-187">Windows Update is nodig om beveiligingsinformatie-updates en antimalware-engine-updates te krijgen</span><span class="sxs-lookup"><span data-stu-id="971a1-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="971a1-188">Voorbeelden verzenden</span><span class="sxs-lookup"><span data-stu-id="971a1-188">Submit samples</span></span>

<span data-ttu-id="971a1-189">Met voorbeeldinzending kan Microsoft voorbeelden van mogelijk schadelijke software verzamelen.</span><span class="sxs-lookup"><span data-stu-id="971a1-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="971a1-190">Microsoft-onderzoekers gebruiken deze voorbeelden om verdachte activiteiten te analyseren en bijgewerkte antimalwarebeveiligingsinformatie te produceren om de beveiliging voortdurend en up-to-date te houden.</span><span class="sxs-lookup"><span data-stu-id="971a1-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="971a1-191">We verzamelen uitvoerbare programmabestanden, zoals .exe bestanden en .dll bestanden.</span><span class="sxs-lookup"><span data-stu-id="971a1-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="971a1-192">We verzamelen geen bestanden die persoonlijke gegevens bevatten, zoals Microsoft Word en PDF-bestanden.</span><span class="sxs-lookup"><span data-stu-id="971a1-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="971a1-193">Een bestand verzenden</span><span class="sxs-lookup"><span data-stu-id="971a1-193">Submit a file</span></span>

1. <span data-ttu-id="971a1-194">Bekijk de [inzendingshandleiding.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="971a1-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="971a1-195">Ga naar [de voorbeeldportal](https://www.microsoft.com/wdsi/filesubmission)voor inzending en verzend uw bestand.</span><span class="sxs-lookup"><span data-stu-id="971a1-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="971a1-196">Automatische voorbeeldinzending inschakelen</span><span class="sxs-lookup"><span data-stu-id="971a1-196">Enable automatic sample submission</span></span>

<span data-ttu-id="971a1-197">Als u automatische voorbeeldinzending wilt inschakelen, start u een Windows PowerShell-console als beheerder en stelt u de **waardegegevens van SubmitSamplesConsent** in op een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="971a1-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="971a1-198">Instelling</span><span class="sxs-lookup"><span data-stu-id="971a1-198">Setting</span></span>  |<span data-ttu-id="971a1-199">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="971a1-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="971a1-200">**0**  -  **Altijd vragen**</span><span class="sxs-lookup"><span data-stu-id="971a1-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="971a1-201">De Microsoft Defender Antivirus service vraagt u om te bevestigen dat u alle vereiste bestanden hebt ingediend.</span><span class="sxs-lookup"><span data-stu-id="971a1-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="971a1-202">Dit is de standaardinstelling voor Microsoft Defender Antivirus, maar wordt niet aanbevolen voor installaties op Windows Server 2016 of 2019 zonder gui.</span><span class="sxs-lookup"><span data-stu-id="971a1-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="971a1-203">**1**   -  **Veilige steekproeven automatisch verzenden**</span><span class="sxs-lookup"><span data-stu-id="971a1-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="971a1-204">De Microsoft Defender Antivirus-service verzendt alle bestanden die zijn gemarkeerd als 'veilig' en vraagt om de rest van de bestanden.</span><span class="sxs-lookup"><span data-stu-id="971a1-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="971a1-205">**2**  -  **Nooit verzenden**</span><span class="sxs-lookup"><span data-stu-id="971a1-205">**2** - **Never send**</span></span>      |<span data-ttu-id="971a1-206">De Microsoft Defender Antivirus service wordt niet gevraagd en verzendt geen bestanden.</span><span class="sxs-lookup"><span data-stu-id="971a1-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="971a1-207">**3**  -  **Alle voorbeelden automatisch verzenden**</span><span class="sxs-lookup"><span data-stu-id="971a1-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="971a1-208">De Microsoft Defender Antivirus-service verzendt alle bestanden zonder een prompt voor bevestiging.</span><span class="sxs-lookup"><span data-stu-id="971a1-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="971a1-209">Automatische uitsluitingen configureren</span><span class="sxs-lookup"><span data-stu-id="971a1-209">Configure automatic exclusions</span></span>

<span data-ttu-id="971a1-210">Om de beveiliging en prestaties te waarborgen, worden bepaalde uitsluitingen automatisch toegevoegd op basis van de rollen en functies die u installeert bij het gebruik van Microsoft Defender Antivirus op Windows Server 2016 of 2019.</span><span class="sxs-lookup"><span data-stu-id="971a1-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="971a1-211">Zie [Uitsluitingen configureren in Microsoft Defender Antivirus op Windows Server.](configure-server-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="971a1-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="971a1-212">Wilt u de Microsoft Defender Antivirus passieve modus instellen?</span><span class="sxs-lookup"><span data-stu-id="971a1-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="971a1-213">Als u een niet-Microsoft-antivirusproduct gebruikt als uw primaire antivirusoplossing op Windows Server, moet u de Microsoft Defender Antivirus passieve modus of uitgeschakelde modus instellen.</span><span class="sxs-lookup"><span data-stu-id="971a1-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="971a1-214">Op Windows Server, versie 1803 of hoger of Windows Server 2019 kunt u de Microsoft Defender Antivirus passieve modus instellen.</span><span class="sxs-lookup"><span data-stu-id="971a1-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="971a1-215">Op Windows Server 2016 wordt Microsoft Defender Antivirus niet ondersteund naast een niet-Microsoft-antivirus-/antimalwareproduct.</span><span class="sxs-lookup"><span data-stu-id="971a1-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="971a1-216">In deze gevallen moet u de modus Microsoft Defender Antivirus uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="971a1-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="971a1-217">Instellen Microsoft Defender Antivirus passieve modus met PowerShell</span><span class="sxs-lookup"><span data-stu-id="971a1-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="971a1-218">Als u Windows Server, versie 1803 of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus met de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="971a1-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="971a1-219">De Microsoft Defender Antivirus op passieve modus instellen met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="971a1-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="971a1-220">PROCEDURE VEREIST</span><span class="sxs-lookup"><span data-stu-id="971a1-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="971a1-221">De Microsoft Defender Antivirus de passieve modus instellen met een registersleutel</span><span class="sxs-lookup"><span data-stu-id="971a1-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="971a1-222">Als u Windows Server, versie 1803 of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus door de volgende registersleutel in te stellen:</span><span class="sxs-lookup"><span data-stu-id="971a1-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="971a1-223">Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="971a1-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="971a1-224">Naam: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="971a1-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="971a1-225">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="971a1-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="971a1-226">Waarde: `1`</span><span class="sxs-lookup"><span data-stu-id="971a1-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="971a1-227">De Microsoft Defender Antivirus met de wizard Rollen en functies verwijderen uitschakelen</span><span class="sxs-lookup"><span data-stu-id="971a1-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="971a1-228">Zie [Rollen, rollen, rollenservices](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)of functies installeren of verwijderen en gebruik de wizard Rollen **en functies verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="971a1-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="971a1-229">Wanneer u bij de stap **Functies** van de wizard bent, kunt u de optie **Windows Defender functies.**</span><span class="sxs-lookup"><span data-stu-id="971a1-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="971a1-230">Als u **Windows Defender** onder de sectie **Windows Defender-functies** uitwijst, wordt u gevraagd om de interfaceoptie **GUI** voor Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="971a1-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="971a1-231">Microsoft Defender Antivirus wordt nog steeds normaal uitgevoerd zonder **de gebruikersinterface,** maar de gebruikersinterface kan niet worden ingeschakeld als u de kernfunctie Windows Defender uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="971a1-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="971a1-232">De gebruikersinterface Microsoft Defender Antivirus uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="971a1-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="971a1-233">Als u de Microsoft Defender Antivirus gui wilt uitschakelen, gebruikt u de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="971a1-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="971a1-234">Gebruikt u Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="971a1-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="971a1-235">Als u Windows Server 2016 en een antimalware/antivirusproduct van derden gebruikt dat niet wordt aangeboden of ontwikkeld door Microsoft, moet u de Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="971a1-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="971a1-236">U kunt de app Windows-beveiliging verwijderen, maar u kunt de interface uitschakelen met deze instructies.</span><span class="sxs-lookup"><span data-stu-id="971a1-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="971a1-237">De volgende PowerShell-cmdlet verwijdert Microsoft Defender Antivirus op Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="971a1-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="971a1-238">Als u Microsoft Defender Antivirus op Windows Server 2016 wilt uitschakelen, gebruikt u de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="971a1-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="971a1-239">Zie ook</span><span class="sxs-lookup"><span data-stu-id="971a1-239">See also</span></span>

- [<span data-ttu-id="971a1-240">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="971a1-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="971a1-241">Microsoft Defender Antivirus compatibiliteit</span><span class="sxs-lookup"><span data-stu-id="971a1-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
