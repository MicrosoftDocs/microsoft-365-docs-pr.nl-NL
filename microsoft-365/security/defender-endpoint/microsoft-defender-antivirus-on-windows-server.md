---
title: Microsoft Defender Antivirus op Windows Server
description: Meer informatie over het inschakelen en configureren van Microsoft Defender Antivirus op Windows Server 2016 en Windows Server 2019.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 04/23/2021
ms.openlocfilehash: 175b06738b8c1508dab68c1e19648aa5385a7137
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269490"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="bdcf3-104">Microsoft Defender Antivirus op Windows Server</span><span class="sxs-lookup"><span data-stu-id="bdcf3-104">Microsoft Defender Antivirus on Windows Server</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bdcf3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-105">**Applies to:**</span></span>

- [<span data-ttu-id="bdcf3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="bdcf3-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="bdcf3-107">Microsoft Defender Antivirus is beschikbaar in de volgende versies/versies van Windows Server:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-107">Microsoft Defender Antivirus is available on the following editions/versions of Windows Server:</span></span>
- <span data-ttu-id="bdcf3-108">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="bdcf3-108">Windows Server 2019</span></span>
- <span data-ttu-id="bdcf3-109">Windows Server, versie 1803 of hoger</span><span class="sxs-lookup"><span data-stu-id="bdcf3-109">Windows Server, version  1803 or later</span></span>
- <span data-ttu-id="bdcf3-110">Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-110">Windows Server 2016.</span></span> 

<span data-ttu-id="bdcf3-111">In sommige gevallen wordt Microsoft Defender Antivirus ook wel *Endpoint Protection genoemd;* De protection engine is echter hetzelfde.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-111">In some instances, Microsoft Defender Antivirus is referred to as *Endpoint Protection*; however, the protection engine is the same.</span></span> <span data-ttu-id="bdcf3-112">Hoewel de functionaliteit, configuratie en beheer grotendeels hetzelfde zijn voor Microsoft Defender Antivirus in [Windows 10,](microsoft-defender-antivirus-in-windows-10.md)zijn er een paar belangrijke verschillen op Windows Server:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-112">Although the functionality, configuration, and management are largely the same for [Microsoft Defender Antivirus on Windows 10](microsoft-defender-antivirus-in-windows-10.md), there are a few key differences on Windows Server:</span></span>

- <span data-ttu-id="bdcf3-113">Op Windows Server worden [automatische uitsluitingen](configure-server-exclusions-microsoft-defender-antivirus.md) toegepast op basis van uw gedefinieerde serverrol.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-113">On Windows Server, [automatic exclusions](configure-server-exclusions-microsoft-defender-antivirus.md) are applied based on your defined Server Role.</span></span>
 
- <span data-ttu-id="bdcf3-114">Als u op Windows Server een niet-Microsoft-antivirus-/antimalware-oplossing gebruikt, gaat Microsoft Defender Antivirus niet automatisch in de passieve modus of in de uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-114">On Windows Server, if you are running a non-Microsoft antivirus/antimalware solution, Microsoft Defender Antivirus does not go into either passive mode or disabled mode automatically.</span></span> <span data-ttu-id="bdcf3-115">U kunt Microsoft Defender Antivirus echter handmatig instellen op passieve of uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-115">However, you can set Microsoft Defender Antivirus to passive or disabled mode manually.</span></span>

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="bdcf3-116">Microsoft Defender Antivirus instellen op Windows Server</span><span class="sxs-lookup"><span data-stu-id="bdcf3-116">Setting up Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="bdcf3-117">Het proces van het instellen en uitvoeren van Microsoft Defender Antivirus op een serverplatform bevat verschillende stappen:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-117">The process of setting up and running Microsoft Defender Antivirus on a server platform includes several steps:</span></span>

1. <span data-ttu-id="bdcf3-118">[Schakel de interface in.](#enable-the-user-interface-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-118">[Enable the interface](#enable-the-user-interface-on-windows-server).</span></span>
2. <span data-ttu-id="bdcf3-119">[Microsoft Defender Antivirus installeren.](#install-microsoft-defender-antivirus-on-windows-server)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-119">[Install Microsoft Defender Antivirus](#install-microsoft-defender-antivirus-on-windows-server).</span></span>
3. <span data-ttu-id="bdcf3-120">[Controleer of Microsoft Defender Antivirus wordt uitgevoerd.](#verify-microsoft-defender-antivirus-is-running)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-120">[Verify Microsoft Defender Antivirus is running](#verify-microsoft-defender-antivirus-is-running).</span></span>
4. <span data-ttu-id="bdcf3-121">[Werk uw antimalwarebeveiligingsinformatie bij.](#update-antimalware-security-intelligence)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-121">[Update your antimalware Security intelligence](#update-antimalware-security-intelligence).</span></span>
5. <span data-ttu-id="bdcf3-122">(Indien nodig) [Steekproeven indienen](#submit-samples).</span><span class="sxs-lookup"><span data-stu-id="bdcf3-122">(As needed) [Submit samples](#submit-samples).</span></span>
6. <span data-ttu-id="bdcf3-123">(Indien nodig) [Automatische uitsluitingen configureren.](#configure-automatic-exclusions)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-123">(As needed) [Configure automatic exclusions](#configure-automatic-exclusions).</span></span>
7. <span data-ttu-id="bdcf3-124">(Alleen indien nodig) [Stel Microsoft Defender Antivirus in op passieve modus.](#need-to-set-microsoft-defender-antivirus-to-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-124">(Only if necessary) [Set Microsoft Defender Antivirus to passive mode](#need-to-set-microsoft-defender-antivirus-to-passive-mode).</span></span>

## <a name="enable-the-user-interface-on-windows-server"></a><span data-ttu-id="bdcf3-125">De gebruikersinterface inschakelen op Windows Server</span><span class="sxs-lookup"><span data-stu-id="bdcf3-125">Enable the user interface on Windows Server</span></span>

<span data-ttu-id="bdcf3-126">Microsoft Defender Antivirus is standaard geïnstalleerd en werkt op Windows Server.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-126">By default, Microsoft Defender Antivirus is installed and functional on Windows Server.</span></span> <span data-ttu-id="bdcf3-127">Soms is de gebruikersinterface (GUI) standaard geïnstalleerd, maar is de GUI niet vereist.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-127">Sometimes, the user interface (GUI) is installed by default, but the GUI is not required.</span></span> <span data-ttu-id="bdcf3-128">U kunt PowerShell, Groepsbeleid of andere methoden gebruiken om Microsoft Defender Antivirus te beheren.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-128">You can use PowerShell, Group Policy, or other methods to manage Microsoft Defender Antivirus.</span></span> 

<span data-ttu-id="bdcf3-129">Als de GUI niet is geïnstalleerd op uw server en u deze wilt installeren, kunt u de **wizard** Rollen en functies toevoegen of PowerShell-cmdlets gebruiken.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-129">If the GUI is not installed on your server, and you want to install it, either the **Add Roles and Features** wizard or PowerShell cmdlets.</span></span>

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a><span data-ttu-id="bdcf3-130">De GUI in- of uit te zetten met de wizard Rollen en functies toevoegen</span><span class="sxs-lookup"><span data-stu-id="bdcf3-130">Turn on the GUI using the Add Roles and Features Wizard</span></span>

1. <span data-ttu-id="bdcf3-131">Zie [Rollen, rollenservices](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)en functies installeren met de wizard Rollen en functies toevoegen en gebruik de wizard Rollen **en functies toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-131">See [Install roles, role services, and features by using the add Roles and Features Wizard](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="bdcf3-132">Wanneer u bij de stap **Functies** van de wizard komt, selecteert u onder **Windows Defender-functies** de optie **GUI voor Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-132">When you get to the **Features** step of the wizard, under **Windows Defender Features**, select the **GUI for Windows Defender** option.</span></span>

   <span data-ttu-id="bdcf3-133">In Windows Server 2016 ziet de wizard Rollen **en** functies toevoegen er als volgende uit:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-133">In Windows Server 2016, the **Add Roles and Features Wizard** looks like this:</span></span>

   ![Rollen en functiewizard toevoegen met de optie GUI voor Windows Defender](images/server-add-gui.png)

   <span data-ttu-id="bdcf3-135">In Windows Server 2019 is de wizard Rollen **en functies** toevoegen vergelijkbaar.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-135">In Windows Server 2019, the **Add Roles and Feature Wizard** is similar.</span></span>

### <a name="turn-on-the-gui-using-powershell"></a><span data-ttu-id="bdcf3-136">De GUI in-en-uit met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdcf3-136">Turn on the GUI using PowerShell</span></span>

<span data-ttu-id="bdcf3-137">Met de volgende PowerShell-cmdlet wordt de interface ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-137">The following PowerShell cmdlet will enable the interface:</span></span> 

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a><span data-ttu-id="bdcf3-138">Microsoft Defender Antivirus installeren op Windows Server</span><span class="sxs-lookup"><span data-stu-id="bdcf3-138">Install Microsoft Defender Antivirus on Windows Server</span></span>

<span data-ttu-id="bdcf3-139">Als u Microsoft Defender Antivirus op Windows Server wilt installeren of opnieuw wilt installeren, kunt u dat doen met de wizard Rollen en functies toevoegen **of** PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-139">If you need to install or reinstall Microsoft Defender Antivirus on Windows Server, you can do that using either the **Add Roles and Features Wizard** or PowerShell.</span></span>

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="bdcf3-140">De wizard Rollen en functies toevoegen gebruiken om Microsoft Defender Antivirus te installeren</span><span class="sxs-lookup"><span data-stu-id="bdcf3-140">Use the Add Roles and Features Wizard to install Microsoft Defender Antivirus</span></span>

1. <span data-ttu-id="bdcf3-141">Raadpleeg dit [artikel en](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)gebruik de wizard Rollen en **functies toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-141">Refer to [this article](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard), and use the **Add Roles and Features Wizard**.</span></span>

2. <span data-ttu-id="bdcf3-142">Wanneer u bij de stap **Functies** van de wizard komt, selecteert u de optie Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-142">When you get to the **Features** step of the wizard, select the Microsoft Defender Antivirus option.</span></span> <span data-ttu-id="bdcf3-143">Selecteer ook de **optie GUI voor Windows Defender.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-143">Also select the **GUI for Windows Defender** option.</span></span>

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a><span data-ttu-id="bdcf3-144">PowerShell gebruiken om Microsoft Defender Antivirus te installeren</span><span class="sxs-lookup"><span data-stu-id="bdcf3-144">Use PowerShell to install Microsoft Defender Antivirus</span></span>

<span data-ttu-id="bdcf3-145">Voer de volgende cmdlet uit als u PowerShell wilt gebruiken om Microsoft Defender Antivirus te installeren:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-145">To use PowerShell to install Microsoft Defender Antivirus, run the following cmdlet:</span></span>

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="bdcf3-146">Gebeurtenisberichten voor de antimalware-engine die is inbegrepen bij Microsoft Defender Antivirus vindt u in [Microsoft Defender AV Events.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-146">Event messages for the antimalware engine included with Microsoft Defender Antivirus can be found in [Microsoft Defender AV Events](troubleshoot-microsoft-defender-antivirus.md).</span></span>


## <a name="verify-microsoft-defender-antivirus-is-running"></a><span data-ttu-id="bdcf3-147">Controleren of Microsoft Defender Antivirus wordt uitgevoerd</span><span class="sxs-lookup"><span data-stu-id="bdcf3-147">Verify Microsoft Defender Antivirus is running</span></span>

<span data-ttu-id="bdcf3-148">Nadat Microsoft Defender Antivirus is geïnstalleerd, moet u controleren of het programma wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-148">Once Microsoft Defender Antivirus is installed, your next step is to verify that it's running.</span></span> <span data-ttu-id="bdcf3-149">Voer op uw Windows Server-eindpunt de volgende PowerShell-cmdlet uit:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-149">On your Windows Server endpoint, run the following PowerShell cmdlet:</span></span>

```PowerShell
Get-Service -Name windefend
```

<span data-ttu-id="bdcf3-150">Voer de volgende PowerShell-cmdlet uit om te controleren of firewallbeveiliging is ingeschakeld:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-150">To verify that firewall protection is turned on, run the following PowerShell cmdlet:</span></span>

```PowerShell 
Get-Service -Name mpssvc
```

<span data-ttu-id="bdcf3-151">Als alternatief voor PowerShell kunt u opdrachtprompt gebruiken om te controleren of Microsoft Defender Antivirus wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-151">As an alternative to PowerShell, you can use Command Prompt to verify that Microsoft Defender Antivirus is running.</span></span> <span data-ttu-id="bdcf3-152">Voer de volgende opdracht uit vanuit een opdrachtprompt:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-152">To do that, run the following command from a command prompt:</span></span> 

```console
sc query Windefend
```

<span data-ttu-id="bdcf3-153">De `sc query` opdracht retourneert informatie over de Microsoft Defender Antivirus-service.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-153">The `sc query` command returns information about the Microsoft Defender Antivirus service.</span></span> <span data-ttu-id="bdcf3-154">Wanneer Microsoft Defender Antivirus wordt uitgevoerd, wordt de `STATE` waarde `RUNNING` weergegeven.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-154">When Microsoft Defender Antivirus is running, the `STATE` value displays `RUNNING`.</span></span>

## <a name="update-antimalware-security-intelligence"></a><span data-ttu-id="bdcf3-155">Antimalware-beveiligingsinformatie bijwerken</span><span class="sxs-lookup"><span data-stu-id="bdcf3-155">Update antimalware Security intelligence</span></span> 

<span data-ttu-id="bdcf3-156">Als u bijgewerkte beveiligingsinformatie voor antimalware wilt downloaden, moet de Windows Update-service zijn uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-156">To get updated antimalware security intelligence, you must have the Windows Update service running.</span></span> <span data-ttu-id="bdcf3-157">Als u een updatebeheerservice gebruikt, zoals Windows Server Update Services (WSUS), moet u ervoor zorgen dat updates voor Microsoft Defender Antivirus Security Intelligence worden goedgekeurd voor de computers die u beheert.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-157">If you use an update management service, like Windows Server Update Services (WSUS), make sure that updates for Microsoft Defender Antivirus Security intelligence are approved for the computers you manage.</span></span>

<span data-ttu-id="bdcf3-158">Standaard worden updates niet automatisch gedownload en geïnstalleerd op Windows Server 2019 of Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-158">By default, Windows Update does not download and install updates automatically on Windows Server 2019 or Windows Server 2016.</span></span> <span data-ttu-id="bdcf3-159">U kunt deze configuratie wijzigen met behulp van een van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-159">You can change this configuration by using one of the following methods:</span></span>


|<span data-ttu-id="bdcf3-160">Methode</span><span class="sxs-lookup"><span data-stu-id="bdcf3-160">Method</span></span>  |<span data-ttu-id="bdcf3-161">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bdcf3-161">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bdcf3-162">**Windows Update** in configuratiescherm</span><span class="sxs-lookup"><span data-stu-id="bdcf3-162">**Windows Update** in Control Panel</span></span>     |<span data-ttu-id="bdcf3-163">- **Als u updates installeert,** worden alle updates automatisch geïnstalleerd, inclusief beveiligingsinformatie-updates van Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-163">- **Install updates automatically** results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="bdcf3-164">- **Updates downloaden, maar laat me kiezen of** ik ze wil installeren, kan Windows Defender automatisch beveiligingsinformatie-updates downloaden en installeren, maar andere updates worden niet automatisch geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-164">- **Download updates but let me choose whether to install them** allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>       |
|<span data-ttu-id="bdcf3-165">**Groepsbeleid**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-165">**Group Policy**</span></span>     | <span data-ttu-id="bdcf3-166">U kunt Windows Update instellen en beheren met behulp van de instellingen die beschikbaar zijn in groepsbeleid, in het volgende pad: **Beheersjablonen\Windows-onderdelen\Windows Update\Automatische updates configureren**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-166">You can set up and manage Windows Update by using the settings available in Group Policy, in the following path: **Administrative Templates\Windows Components\Windows Update\Configure Automatic Updates**</span></span>         |
|<span data-ttu-id="bdcf3-167">De **AUOptions-registersleutel**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-167">The **AUOptions** registry key</span></span>     |<span data-ttu-id="bdcf3-168">Met de volgende twee waarden kan Windows Update updates voor beveiligingsinformatie automatisch downloaden en installeren:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-168">The following two values allow Windows Update to automatically download and install Security intelligence updates:</span></span> <br/><span data-ttu-id="bdcf3-169">- **4**  -  **Updates automatisch installeren.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-169">- **4** - **Install updates automatically**.</span></span> <span data-ttu-id="bdcf3-170">Met deze waarde worden alle updates automatisch geïnstalleerd, inclusief beveiligingsinformatie-updates van Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-170">This value results in all updates being automatically installed, including Windows Defender Security intelligence updates.</span></span> <br/><span data-ttu-id="bdcf3-171">- **3**  -  **Download updates, maar laat me kiezen of ik ze wil installeren.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-171">- **3** - **Download updates but let me choose whether to install them**.</span></span>  <span data-ttu-id="bdcf3-172">Met deze waarde kan Windows Defender updates voor beveiligingsinformatie automatisch downloaden en installeren, maar andere updates worden niet automatisch geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-172">This value allows Windows Defender to download and install Security intelligence updates automatically, but other updates are not automatically installed.</span></span>         |

<span data-ttu-id="bdcf3-173">Om ervoor te zorgen dat de beveiliging tegen malware wordt gehandhaafd, raden we u aan de volgende services in te stellen:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-173">To ensure that protection from malware is maintained, we recommend that you enable the following services:</span></span>

- <span data-ttu-id="bdcf3-174">Windows Error Reporting-service</span><span class="sxs-lookup"><span data-stu-id="bdcf3-174">Windows Error Reporting service</span></span>

- <span data-ttu-id="bdcf3-175">Windows Update-service</span><span class="sxs-lookup"><span data-stu-id="bdcf3-175">Windows Update service</span></span>

<span data-ttu-id="bdcf3-176">De volgende tabel bevat de services voor Microsoft Defender Antivirus en de afhankelijke services.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-176">The following table lists the services for Microsoft Defender Antivirus and the dependent services.</span></span>

|<span data-ttu-id="bdcf3-177">Servicenaam</span><span class="sxs-lookup"><span data-stu-id="bdcf3-177">Service Name</span></span>|<span data-ttu-id="bdcf3-178">Bestandslocatie</span><span class="sxs-lookup"><span data-stu-id="bdcf3-178">File Location</span></span>|<span data-ttu-id="bdcf3-179">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="bdcf3-179">Description</span></span>|
|--------|---------|--------|
|<span data-ttu-id="bdcf3-180">Windows Defender Service (WinDefend)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-180">Windows Defender Service (WinDefend)</span></span>|`C:\Program Files\Windows Defender\MsMpEng.exe`|<span data-ttu-id="bdcf3-181">Dit is de belangrijkste Microsoft Defender Antivirus-service die altijd moet worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-181">This is the main Microsoft Defender Antivirus service that needs to be running at all times.</span></span>|
|<span data-ttu-id="bdcf3-182">Windows Error Reporting Service (Wersvc)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-182">Windows Error Reporting Service (Wersvc)</span></span>|`C:\WINDOWS\System32\svchost.exe -k WerSvcGroup`|<span data-ttu-id="bdcf3-183">Deze service stuurt foutrapporten terug naar Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-183">This service sends error reports back to Microsoft.</span></span>|
|<span data-ttu-id="bdcf3-184">Windows Defender Firewall (MpsSvc)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-184">Windows Defender Firewall (MpsSvc)</span></span>|`C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork`|<span data-ttu-id="bdcf3-185">Het is raadzaam om de Windows Defender Firewall-service ingeschakeld te laten.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-185">We recommend leaving the Windows Defender Firewall service enabled.</span></span>|
|<span data-ttu-id="bdcf3-186">Windows Update (Wuauserv)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-186">Windows Update (Wuauserv)</span></span>|`C:\WINDOWS\system32\svchost.exe -k netsvcs`|<span data-ttu-id="bdcf3-187">Windows Update is nodig om beveiligingsintelligentie-updates en antimalware-engine-updates te krijgen</span><span class="sxs-lookup"><span data-stu-id="bdcf3-187">Windows Update is needed to get Security intelligence updates and antimalware engine updates</span></span>|

## <a name="submit-samples"></a><span data-ttu-id="bdcf3-188">Voorbeelden verzenden</span><span class="sxs-lookup"><span data-stu-id="bdcf3-188">Submit samples</span></span>

<span data-ttu-id="bdcf3-189">Met voorbeeldinzending kan Microsoft voorbeelden van mogelijk schadelijke software verzamelen.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-189">Sample submission allows Microsoft to collect samples of potentially malicious software.</span></span> <span data-ttu-id="bdcf3-190">Microsoft-onderzoekers gebruiken deze voorbeelden om verdachte activiteiten te analyseren en bijgewerkte antimalwarebeveiligingsinformatie te produceren om de beveiliging voortdurend en up-to-date te houden.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-190">To help provide continued and up-to-date protection, Microsoft researchers use these samples to analyze suspicious activities and produce updated antimalware Security intelligence.</span></span> <span data-ttu-id="bdcf3-191">We verzamelen uitvoerbare programmabestanden, zoals .exe bestanden en .dll bestanden.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-191">We collect program executable files, such as .exe files and .dll files.</span></span> <span data-ttu-id="bdcf3-192">We verzamelen geen bestanden die persoonlijke gegevens bevatten, zoals Microsoft Word-documenten en PDF-bestanden.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-192">We do not collect files that contain personal data, like Microsoft Word documents and PDF files.</span></span>

### <a name="submit-a-file"></a><span data-ttu-id="bdcf3-193">Een bestand verzenden</span><span class="sxs-lookup"><span data-stu-id="bdcf3-193">Submit a file</span></span>

1. <span data-ttu-id="bdcf3-194">Bekijk de [inzendingshandleiding.](/windows/security/threat-protection/intelligence/submission-guide)</span><span class="sxs-lookup"><span data-stu-id="bdcf3-194">Review the [submission guide](/windows/security/threat-protection/intelligence/submission-guide).</span></span>

2. <span data-ttu-id="bdcf3-195">Ga naar [de voorbeeldportal](https://www.microsoft.com/wdsi/filesubmission)voor inzending en verzend uw bestand.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-195">Visit the [sample submission portal](https://www.microsoft.com/wdsi/filesubmission), and submit your file.</span></span>


### <a name="enable-automatic-sample-submission"></a><span data-ttu-id="bdcf3-196">Automatische voorbeeldinzending inschakelen</span><span class="sxs-lookup"><span data-stu-id="bdcf3-196">Enable automatic sample submission</span></span>

<span data-ttu-id="bdcf3-197">Als u automatische voorbeeldinzending wilt inschakelen, start u een Windows PowerShell-console als beheerder en stelt u de **waardegegevens van SubmitSamplesConsent** in op een van de volgende instellingen:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-197">To enable automatic sample submission, start a Windows PowerShell console as an administrator, and set the **SubmitSamplesConsent** value data according to one of the following settings:</span></span>

|<span data-ttu-id="bdcf3-198">Instelling</span><span class="sxs-lookup"><span data-stu-id="bdcf3-198">Setting</span></span>  |<span data-ttu-id="bdcf3-199">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="bdcf3-199">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="bdcf3-200">**0**  -  **Altijd vragen**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-200">**0** - **Always prompt**</span></span>     |<span data-ttu-id="bdcf3-201">De Microsoft Defender Antivirus-service vraagt u om te bevestigen dat u alle vereiste bestanden hebt ingediend.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-201">The Microsoft Defender Antivirus service prompts you to confirm submission of all required files.</span></span> <span data-ttu-id="bdcf3-202">Dit is de standaardinstelling voor Microsoft Defender Antivirus, maar wordt niet aanbevolen voor installaties op Windows Server 2016 of 2019 zonder gui.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-202">This is the default setting for Microsoft Defender Antivirus, but is not recommended for installations on Windows Server 2016 or 2019 without a GUI.</span></span>         |
|<span data-ttu-id="bdcf3-203">**1**   -  **Veilige steekproeven automatisch verzenden**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-203">**1**  - **Send safe samples automatically**</span></span>     |<span data-ttu-id="bdcf3-204">De Microsoft Defender Antivirus-service verzendt alle bestanden die zijn gemarkeerd als 'veilig' en vraagt om de rest van de bestanden.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-204">The Microsoft Defender Antivirus service sends all files marked as "safe" and prompts for the remainder of the files.</span></span>         |
|<span data-ttu-id="bdcf3-205">**2**  -  **Nooit verzenden**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-205">**2** - **Never send**</span></span>      |<span data-ttu-id="bdcf3-206">De Microsoft Defender Antivirus-service wordt niet gevraagd en verzendt geen bestanden.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-206">The Microsoft Defender Antivirus service does not prompt and does not send any files.</span></span>         |
|<span data-ttu-id="bdcf3-207">**3**  -  **Alle voorbeelden automatisch verzenden**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-207">**3** - **Send all samples automatically**</span></span>     |<span data-ttu-id="bdcf3-208">De Microsoft Defender Antivirus-service verzendt alle bestanden zonder een bevestigingsprompt.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-208">The Microsoft Defender Antivirus service sends all files without a prompt for confirmation.</span></span>         |

## <a name="configure-automatic-exclusions"></a><span data-ttu-id="bdcf3-209">Automatische uitsluitingen configureren</span><span class="sxs-lookup"><span data-stu-id="bdcf3-209">Configure automatic exclusions</span></span>

<span data-ttu-id="bdcf3-210">Om de beveiliging en prestaties te waarborgen, worden bepaalde uitsluitingen automatisch toegevoegd op basis van de rollen en functies die u installeert bij het gebruik van Microsoft Defender Antivirus op Windows Server 2016 of 2019.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-210">To help ensure security and performance, certain exclusions are automatically added based on the roles and features you install when using Microsoft Defender Antivirus on Windows Server 2016 or 2019.</span></span>

<span data-ttu-id="bdcf3-211">Zie [Uitsluitingen configureren in Microsoft Defender Antivirus op Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="bdcf3-211">See [Configure exclusions in Microsoft Defender Antivirus on Windows Server](configure-server-exclusions-microsoft-defender-antivirus.md).</span></span> 

## <a name="need-to-set-microsoft-defender-antivirus-to-passive-mode"></a><span data-ttu-id="bdcf3-212">Wilt u Microsoft Defender Antivirus instellen op passieve modus?</span><span class="sxs-lookup"><span data-stu-id="bdcf3-212">Need to set Microsoft Defender Antivirus to passive mode?</span></span>

<span data-ttu-id="bdcf3-213">Als u een niet-Microsoft-antivirusproduct gebruikt als uw primaire antivirusoplossing op Windows Server, moet u Microsoft Defender Antivirus instellen op passieve modus of uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-213">If you are using a non-Microsoft antivirus product as your primary antivirus solution on Windows Server, you must set Microsoft Defender Antivirus to passive mode or disabled mode.</span></span>

- <span data-ttu-id="bdcf3-214">Op Windows Server, versie 1803 of hoger of Windows Server 2019, kunt u Microsoft Defender Antivirus instellen op passieve modus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-214">On Windows Server, version 1803 or newer, or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode.</span></span>  

- <span data-ttu-id="bdcf3-215">In Windows Server 2016 wordt Microsoft Defender Antivirus niet ondersteund naast een niet-Microsoft antivirus/antimalware-product.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-215">On Windows Server 2016, Microsoft Defender Antivirus is not supported alongside a non-Microsoft antivirus/antimalware product.</span></span> <span data-ttu-id="bdcf3-216">In deze gevallen moet u Microsoft Defender Antivirus instellen op uitgeschakelde modus.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-216">In these cases, you must set Microsoft Defender Antivirus to disabled mode.</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-powershell"></a><span data-ttu-id="bdcf3-217">Microsoft Defender Antivirus instellen op passieve modus met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdcf3-217">Set Microsoft Defender Antivirus to passive mode using PowerShell</span></span>

<span data-ttu-id="bdcf3-218">Als u Windows Server, versie 1803 of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus met behulp van de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-218">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by using the following PowerShell cmdlet:</span></span>

`CMDLET NEEDED`

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-group-policy"></a><span data-ttu-id="bdcf3-219">Microsoft Defender Antivirus instellen op passieve modus met groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="bdcf3-219">Set Microsoft Defender Antivirus to passive mode using Group Policy</span></span>

<span data-ttu-id="bdcf3-220">PROCEDURE VEREIST</span><span class="sxs-lookup"><span data-stu-id="bdcf3-220">PROCEDURE NEEDED</span></span>

### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a><span data-ttu-id="bdcf3-221">Microsoft Defender Antivirus instellen op passieve modus met een registersleutel</span><span class="sxs-lookup"><span data-stu-id="bdcf3-221">Set Microsoft Defender Antivirus to passive mode using a registry key</span></span>

<span data-ttu-id="bdcf3-222">Als u Windows Server, versie 1803 of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus door de volgende registersleutel in te stellen:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-222">If you are using Windows Server, version 1803 or Windows Server 2019, you can set Microsoft Defender Antivirus to passive mode by setting the following registry key:</span></span>
- <span data-ttu-id="bdcf3-223">Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span><span class="sxs-lookup"><span data-stu-id="bdcf3-223">Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`</span></span>
- <span data-ttu-id="bdcf3-224">Naam: `ForceDefenderPassiveMode`</span><span class="sxs-lookup"><span data-stu-id="bdcf3-224">Name: `ForceDefenderPassiveMode`</span></span>
- <span data-ttu-id="bdcf3-225">Typ: `REG_DWORD`</span><span class="sxs-lookup"><span data-stu-id="bdcf3-225">Type: `REG_DWORD`</span></span>
- <span data-ttu-id="bdcf3-226">Waarde: `1`</span><span class="sxs-lookup"><span data-stu-id="bdcf3-226">Value: `1`</span></span>

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a><span data-ttu-id="bdcf3-227">Microsoft Defender Antivirus uitschakelen met de wizard Rollen en functies verwijderen</span><span class="sxs-lookup"><span data-stu-id="bdcf3-227">Disable Microsoft Defender Antivirus using the Remove Roles and Features wizard</span></span>

1. <span data-ttu-id="bdcf3-228">Zie [Rollen, rollen, rollenservices](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)of functies installeren of verwijderen en gebruik de wizard Rollen **en functies verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-228">See [Install or Uninstall Roles, Role Services, or Features](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard), and use the **Remove Roles and Features Wizard**.</span></span> 

2. <span data-ttu-id="bdcf3-229">Wanneer u bij de stap **Functies** van de wizard bent, kunt u de **optie Windows Defender-functies** uit.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-229">When you get to the **Features** step of the wizard, clear the **Windows Defender Features** option.</span></span> 

    <span data-ttu-id="bdcf3-230">Als u **Windows Defender zelf** verwijdert onder de sectie Windows **Defender-functies,** wordt u gevraagd de interfaceoptie GUI voor **Windows Defender te verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="bdcf3-230">If you clear **Windows Defender** by itself under the **Windows Defender Features** section, you will be prompted to remove the interface option **GUI for Windows Defender**.</span></span> 
    
    <span data-ttu-id="bdcf3-231">Microsoft Defender Antivirus wordt nog steeds normaal uitgevoerd zonder de gebruikersinterface, maar de gebruikersinterface kan niet worden ingeschakeld als u de belangrijkste **Windows Defender-functie** uit schakelt.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-231">Microsoft Defender Antivirus will still run normally without the user interface, but the user interface cannot be enabled if you disable the core **Windows Defender** feature.</span></span>

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a><span data-ttu-id="bdcf3-232">De gebruikersinterface van Microsoft Defender Antivirus uitschakelen met PowerShell</span><span class="sxs-lookup"><span data-stu-id="bdcf3-232">Turn off the Microsoft Defender Antivirus user interface using PowerShell</span></span>

<span data-ttu-id="bdcf3-233">Als u de Antivirus-GUI van Microsoft Defender wilt uitschakelen, gebruikt u de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-233">To turn off the Microsoft Defender Antivirus GUI, use the following PowerShell cmdlet:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2016"></a><span data-ttu-id="bdcf3-234">Gebruikt u Windows Server 2016?</span><span class="sxs-lookup"><span data-stu-id="bdcf3-234">Are you using Windows Server 2016?</span></span>

<span data-ttu-id="bdcf3-235">Als u Windows Server 2016 en een antimalware/antivirusproduct van derden gebruikt dat niet wordt aangeboden of ontwikkeld door Microsoft, moet u Microsoft Defender Antivirus uitschakelen/verwijderen.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-235">If you are using Windows Server 2016 and a third-party antimalware/antivirus product that is not offered or developed by Microsoft, you'll need to disable/uninstall Microsoft Defender Antivirus.</span></span> 

> [!NOTE]
> <span data-ttu-id="bdcf3-236">U kunt de Windows Security-app niet verwijderen, maar u kunt de interface wel uitschakelen met deze instructies.</span><span class="sxs-lookup"><span data-stu-id="bdcf3-236">You can't uninstall the Windows Security app, but you can disable the interface with these instructions.</span></span>

<span data-ttu-id="bdcf3-237">Met de volgende PowerShell-cmdlet verwijdert u Microsoft Defender Antivirus op Windows Server 2016:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-237">The following PowerShell cmdlet uninstalls Microsoft Defender Antivirus on Windows Server 2016:</span></span>

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender
```

<span data-ttu-id="bdcf3-238">Als u Microsoft Defender Antivirus wilt uitschakelen op Windows Server 2016, gebruikt u de volgende PowerShell-cmdlet:</span><span class="sxs-lookup"><span data-stu-id="bdcf3-238">To disable Microsoft Defender Antivirus on Windows Server 2016, use the following PowerShell cmdlet:</span></span>

```PowerShell
Set-MpPreference -DisableRealtimeMonitoring $true
```

## <a name="see-also"></a><span data-ttu-id="bdcf3-239">Zie ook</span><span class="sxs-lookup"><span data-stu-id="bdcf3-239">See also</span></span>

- [<span data-ttu-id="bdcf3-240">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="bdcf3-240">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="bdcf3-241">Microsoft Defender Antiviruscompatibiliteit</span><span class="sxs-lookup"><span data-stu-id="bdcf3-241">Microsoft Defender Antivirus compatibility</span></span>](microsoft-defender-antivirus-compatibility.md)
