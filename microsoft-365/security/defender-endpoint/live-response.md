---
title: Entiteiten onderzoeken op apparaten met livereactie in Microsoft Defender ATP
description: Toegang tot een apparaat met een beveiligde externe shell-verbinding om onderzoek te doen en direct actie te ondernemen op een apparaat in realtime.
keywords: remote, shell, connection, live, response, real-time, command, script, remediate, hunt, export, log, drop, download, file,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 235df8c84077311444c597b120a19477cfd0986a
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760414"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="577bd-104">Entiteiten op apparaten onderzoeken met livereactie</span><span class="sxs-lookup"><span data-stu-id="577bd-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="577bd-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="577bd-105">**Applies to:**</span></span>
- [<span data-ttu-id="577bd-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="577bd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="577bd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="577bd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="577bd-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="577bd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="577bd-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="577bd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="577bd-110">Live response geeft beveiligingsbewerkingen teams direct toegang tot een apparaat (ook wel een computer genoemd) met behulp van een externe shell-verbinding.</span><span class="sxs-lookup"><span data-stu-id="577bd-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="577bd-111">Dit geeft u de macht om uitgebreid onderzoek te doen en direct actie te ondernemen om snel geïdentificeerde bedreigingen in realtime te bevatten.</span><span class="sxs-lookup"><span data-stu-id="577bd-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="577bd-112">Live response is ontworpen om onderzoeken te verbeteren door uw beveiligingsteam in staat te stellen om gerechtelijke gegevens te verzamelen, scripts uit te voeren, verdachte entiteiten te verzenden voor analyse, bedreigingen te corrigeren en proactief te zoeken naar nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="577bd-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="577bd-113">Met livereactie kunnen analisten alle volgende taken uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="577bd-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="577bd-114">Voer eenvoudige en geavanceerde opdrachten uit om onderzoek te doen op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="577bd-115">Download bestanden zoals malwarevoorbeelden en resultaten van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="577bd-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="577bd-116">Bestanden op de achtergrond downloaden (nieuw!).</span><span class="sxs-lookup"><span data-stu-id="577bd-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="577bd-117">Upload een PowerShell-script of uitvoerbaar naar de bibliotheek en voer het uit op een apparaat vanaf tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="577bd-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="577bd-118">Herstelacties uitvoeren of ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="577bd-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="577bd-119">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="577bd-119">Before you begin</span></span>

<span data-ttu-id="577bd-120">Voordat u een sessie op een apparaat kunt starten, moet u aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="577bd-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="577bd-121">**Controleer of u een ondersteunde versie van Windows gebruikt.**</span><span class="sxs-lookup"><span data-stu-id="577bd-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="577bd-122">Apparaten moeten een van de volgende versies van Windows uitvoeren</span><span class="sxs-lookup"><span data-stu-id="577bd-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="577bd-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="577bd-123">**Windows 10**</span></span>
    - <span data-ttu-id="577bd-124">[Versie 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) of hoger</span><span class="sxs-lookup"><span data-stu-id="577bd-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="577bd-125">[Versie 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="577bd-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="577bd-126">[Versie 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) [met KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="577bd-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="577bd-127">[Versie 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) met [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="577bd-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="577bd-128">[Versie 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) met [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="577bd-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="577bd-129">**Windows Server 2019 - Alleen van toepassing op openbare preview**</span><span class="sxs-lookup"><span data-stu-id="577bd-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="577bd-130">Versie 1903 of (met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span><span class="sxs-lookup"><span data-stu-id="577bd-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="577bd-131">Versie 1809 (met [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="577bd-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="577bd-132">**Schakel livereactie in vanaf de pagina met geavanceerde instellingen.**</span><span class="sxs-lookup"><span data-stu-id="577bd-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="577bd-133">U moet de mogelijkheid voor livereactie inschakelen op de [pagina Instellingen voor geavanceerde](advanced-features.md) functies.</span><span class="sxs-lookup"><span data-stu-id="577bd-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="577bd-134">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="577bd-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="577bd-135">**Schakel livereactie voor servers in vanaf de pagina met geavanceerde instellingen** (aanbevolen).</span><span class="sxs-lookup"><span data-stu-id="577bd-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="577bd-136">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="577bd-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="577bd-137">**Controleer of aan het apparaat een automatiseringssaneringsniveau is toegewezen.**</span><span class="sxs-lookup"><span data-stu-id="577bd-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="577bd-138">U moet ten minste het minimale herstelniveau voor een bepaalde apparaatgroep inschakelen.</span><span class="sxs-lookup"><span data-stu-id="577bd-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="577bd-139">Anders kunt u geen livereactiesessie voor een lid van die groep opzetten.</span><span class="sxs-lookup"><span data-stu-id="577bd-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="577bd-140">U krijgt de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="577bd-140">You'll receive the following error:</span></span>

    ![Afbeelding van foutbericht](images/live-response-error.png)

- <span data-ttu-id="577bd-142">**Live response unsigned script execution (optioneel)** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="577bd-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="577bd-143">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="577bd-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="577bd-144">Het uitvoeren van niet-ondertekende scripts wordt afgeraden, omdat dit uw blootstelling aan bedreigingen kan vergroten.</span><span class="sxs-lookup"><span data-stu-id="577bd-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="577bd-145">Als u deze echter moet gebruiken, moet u de instelling inschakelen op de pagina Geavanceerde [functiesinstellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="577bd-146">**Controleer of u de juiste machtigingen hebt.**</span><span class="sxs-lookup"><span data-stu-id="577bd-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="577bd-147">Alleen gebruikers die zijn ingericht met de juiste machtigingen, kunnen een sessie starten.</span><span class="sxs-lookup"><span data-stu-id="577bd-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="577bd-148">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="577bd-149">De optie om een bestand te uploaden naar de bibliotheek is alleen beschikbaar voor personen met de juiste RBAC-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="577bd-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="577bd-150">De knop is grijs voor gebruikers met alleen gedelegeerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="577bd-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="577bd-151">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="577bd-152">Gebruikersmachtigingen worden bepaald door de aangepaste rol van RBAC.</span><span class="sxs-lookup"><span data-stu-id="577bd-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="577bd-153">Overzicht van livereactiedashboard</span><span class="sxs-lookup"><span data-stu-id="577bd-153">Live response dashboard overview</span></span>
<span data-ttu-id="577bd-154">Wanneer u een livereactiesessie start op een apparaat, wordt er een dashboard geopend.</span><span class="sxs-lookup"><span data-stu-id="577bd-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="577bd-155">Het dashboard bevat informatie over de sessie, zoals de volgende:</span><span class="sxs-lookup"><span data-stu-id="577bd-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="577bd-156">Wie heeft de sessie gemaakt</span><span class="sxs-lookup"><span data-stu-id="577bd-156">Who created the session</span></span>
- <span data-ttu-id="577bd-157">Wanneer de sessie is gestart</span><span class="sxs-lookup"><span data-stu-id="577bd-157">When the session started</span></span>
- <span data-ttu-id="577bd-158">De duur van de sessie</span><span class="sxs-lookup"><span data-stu-id="577bd-158">The duration of the session</span></span>

<span data-ttu-id="577bd-159">Het dashboard biedt u ook toegang tot:</span><span class="sxs-lookup"><span data-stu-id="577bd-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="577bd-160">Sessie verbreken</span><span class="sxs-lookup"><span data-stu-id="577bd-160">Disconnect session</span></span>
- <span data-ttu-id="577bd-161">Bestanden uploaden naar de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="577bd-161">Upload files to the library</span></span> 
- <span data-ttu-id="577bd-162">Opdrachtconsole</span><span class="sxs-lookup"><span data-stu-id="577bd-162">Command console</span></span>
- <span data-ttu-id="577bd-163">Opdrachtlogboek</span><span class="sxs-lookup"><span data-stu-id="577bd-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="577bd-164">Een livereactiesessie starten op een apparaat</span><span class="sxs-lookup"><span data-stu-id="577bd-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="577bd-165">Meld u aan bij het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="577bd-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="577bd-166">Ga naar de pagina apparatenlijst en selecteer een apparaat dat u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="577bd-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="577bd-167">De pagina Apparaten wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="577bd-167">The devices page opens.</span></span>

3. <span data-ttu-id="577bd-168">Start de livereactiesessie door **Livereactiesessie starten te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="577bd-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="577bd-169">Er wordt een opdrachtconsole weergegeven.</span><span class="sxs-lookup"><span data-stu-id="577bd-169">A command console is displayed.</span></span> <span data-ttu-id="577bd-170">Wacht totdat de sessie verbinding maakt met het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="577bd-171">Gebruik de ingebouwde opdrachten om onderzoekswerk te doen.</span><span class="sxs-lookup"><span data-stu-id="577bd-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="577bd-172">Zie [Live-antwoordopdrachten voor meer informatie.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="577bd-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="577bd-173">Nadat u het onderzoek hebt afgerond, **selecteert** u Sessie verbreken en selecteert u **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="577bd-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="577bd-174">Opdrachten voor livereacties</span><span class="sxs-lookup"><span data-stu-id="577bd-174">Live response commands</span></span>

<span data-ttu-id="577bd-175">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="577bd-176">Gebruikersmachtigingen worden beheerd door aangepaste rollen van RBAC.</span><span class="sxs-lookup"><span data-stu-id="577bd-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="577bd-177">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="577bd-178">Live response is een interactieve shell in de cloud, dus specifieke opdrachtervaring kan variëren in reactietijd, afhankelijk van de netwerkkwaliteit en de systeembelasting tussen de eindgebruiker en het doelapparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="577bd-179">Basisopdrachten</span><span class="sxs-lookup"><span data-stu-id="577bd-179">Basic commands</span></span>

<span data-ttu-id="577bd-180">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om basisopdrachten **voor** livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="577bd-181">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="577bd-182">Opdracht</span><span class="sxs-lookup"><span data-stu-id="577bd-182">Command</span></span> | <span data-ttu-id="577bd-183">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="577bd-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="577bd-184">Wijzigt de huidige adreslijst.</span><span class="sxs-lookup"><span data-stu-id="577bd-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="577bd-185">Het scherm van de console wordt gewed.</span><span class="sxs-lookup"><span data-stu-id="577bd-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="577bd-186">Start een livereactiesessie op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="577bd-187">Toont alle actieve verbindingen.</span><span class="sxs-lookup"><span data-stu-id="577bd-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="577bd-188">Toont een lijst met bestanden en subdirectorieën in een adreslijst.</span><span class="sxs-lookup"><span data-stu-id="577bd-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="577bd-189">Hiermee downloadt u een bestand op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="577bd-189">Downloads a file in the background.</span></span> |
|`drivers` |  <span data-ttu-id="577bd-190">Toont alle stuurprogramma's die op het apparaat zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="577bd-190">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="577bd-191">Plaats de opgegeven taak op de voorgrond op de voorgrond, zodat deze de huidige taak is.</span><span class="sxs-lookup"><span data-stu-id="577bd-191">Place the specified job in the foreground in the foreground, making it the current job.</span></span> <br> <span data-ttu-id="577bd-192">OPMERKING: fg gebruikt een 'opdracht-id' die beschikbaar is vanuit taken, niet uit een PID</span><span class="sxs-lookup"><span data-stu-id="577bd-192">NOTE: fg takes a “command ID” available from jobs, not a PID</span></span> |
|`fileinfo` | <span data-ttu-id="577bd-193">Informatie over een bestand.</span><span class="sxs-lookup"><span data-stu-id="577bd-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="577bd-194">Zoekt bestanden op een bepaalde naam op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-194">Locates files by a given name on the device.</span></span> |
|`getfile <file_path>` | <span data-ttu-id="577bd-195">Hiermee wordt een bestand gedownload.</span><span class="sxs-lookup"><span data-stu-id="577bd-195">Downloads a file.</span></span> |
|`help` | <span data-ttu-id="577bd-196">Biedt help-informatie voor opdrachten voor livereacties.</span><span class="sxs-lookup"><span data-stu-id="577bd-196">Provides help information for live response commands.</span></span> |
|`jobs` | <span data-ttu-id="577bd-197">Toont momenteel lopende taken, hun id en status.</span><span class="sxs-lookup"><span data-stu-id="577bd-197">Shows currently running jobs, their ID and status.</span></span> |
|`persistence` | <span data-ttu-id="577bd-198">Toont alle bekende persistentiemethoden op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-198">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="577bd-199">Toont alle processen die op het apparaat worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="577bd-199">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="577bd-200">Geeft registerwaarden weer.</span><span class="sxs-lookup"><span data-stu-id="577bd-200">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="577bd-201">Toont alle geplande taken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-201">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="577bd-202">Toont alle services op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-202">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="577bd-203">Hiermee stelt u de logboekregistratiemodus van de terminal in op foutopsporing.</span><span class="sxs-lookup"><span data-stu-id="577bd-203">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="577bd-204">Geavanceerde opdrachten</span><span class="sxs-lookup"><span data-stu-id="577bd-204">Advanced commands</span></span>
<span data-ttu-id="577bd-205">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om geavanceerde **opdrachten** voor livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-205">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="577bd-206">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-206">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="577bd-207">Opdracht</span><span class="sxs-lookup"><span data-stu-id="577bd-207">Command</span></span> | <span data-ttu-id="577bd-208">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="577bd-208">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="577bd-209">Analyseert de entiteit met verschillende belastende motoren om tot een uitspraak te komen.</span><span class="sxs-lookup"><span data-stu-id="577bd-209">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `run` | <span data-ttu-id="577bd-210">Voert een PowerShell-script uit vanuit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-210">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="577bd-211">Hiermee worden bestanden vermeld die zijn geüpload naar de live antwoordbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="577bd-211">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="577bd-212">Zet een bestand uit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-212">Puts a file from the library to the device.</span></span> <span data-ttu-id="577bd-213">Bestanden worden opgeslagen in een werkmap en worden verwijderd wanneer het apparaat standaard opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="577bd-213">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="577bd-214">Herstelt een entiteit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="577bd-214">Remediates an entity on the device.</span></span> <span data-ttu-id="577bd-215">De herstelactie is afhankelijk van het entiteitstype:</span><span class="sxs-lookup"><span data-stu-id="577bd-215">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="577bd-216">- Bestand: verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-216">- File: delete</span></span><br><span data-ttu-id="577bd-217">- Proces: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-217">- Process: stop, delete image file</span></span><br><span data-ttu-id="577bd-218">- Service: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-218">- Service: stop, delete image file</span></span><br><span data-ttu-id="577bd-219">- Registerinvoer: verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-219">- Registry entry: delete</span></span><br><span data-ttu-id="577bd-220">- Geplande taak: verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-220">- Scheduled task: remove</span></span><br><span data-ttu-id="577bd-221">- Mapitem opstarten: bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="577bd-221">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="577bd-222">OPMERKING: Deze opdracht heeft een vereiste opdracht.</span><span class="sxs-lookup"><span data-stu-id="577bd-222">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="577bd-223">U kunt de opdracht in combinatie met de opdracht gebruiken `-auto` om de vereiste opdracht automatisch uit te `remediate` voeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-223">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="577bd-224">Herstelt een entiteit die is hersteld.</span><span class="sxs-lookup"><span data-stu-id="577bd-224">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="577bd-225">Opdrachten voor livereacties gebruiken</span><span class="sxs-lookup"><span data-stu-id="577bd-225">Use live response commands</span></span>

<span data-ttu-id="577bd-226">De opdrachten die u in de console kunt gebruiken, volgen dezelfde principes als [Windows-opdrachten.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="577bd-226">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="577bd-227">De geavanceerde opdrachten bieden een krachtigere reeks acties waarmee u krachtigere acties kunt uitvoeren, zoals het downloaden en uploaden van een bestand, het uitvoeren van scripts op het apparaat en het uitvoeren van herstelacties voor een entiteit.</span><span class="sxs-lookup"><span data-stu-id="577bd-227">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="577bd-228">Een bestand van het apparaat downloaden</span><span class="sxs-lookup"><span data-stu-id="577bd-228">Get a file from the device</span></span>

<span data-ttu-id="577bd-229">Voor scenario's wanneer u een bestand wilt downloaden van een apparaat dat u onderzoekt, kunt u de opdracht `getfile` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="577bd-229">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="577bd-230">Hiermee kunt u het bestand opslaan vanaf het apparaat voor verder onderzoek.</span><span class="sxs-lookup"><span data-stu-id="577bd-230">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="577bd-231">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="577bd-231">The following file size limits apply:</span></span>
>- <span data-ttu-id="577bd-232">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="577bd-232">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="577bd-233">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="577bd-233">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="577bd-234">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="577bd-234">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="577bd-235">Een bestand op de achtergrond downloaden</span><span class="sxs-lookup"><span data-stu-id="577bd-235">Download a file in the background</span></span>

<span data-ttu-id="577bd-236">Als u wilt dat uw beveiligingsteam een beïnvloed apparaat kan blijven onderzoeken, kunnen bestanden nu op de achtergrond worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="577bd-236">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="577bd-237">Als u een bestand op de achtergrond wilt downloaden, typt u in de opdrachtconsole voor `download <file_path> &` livereactie.</span><span class="sxs-lookup"><span data-stu-id="577bd-237">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="577bd-238">Als u wacht totdat een bestand wordt gedownload, kunt u het naar de achtergrond verplaatsen met Ctrl+ Z.</span><span class="sxs-lookup"><span data-stu-id="577bd-238">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="577bd-239">Als u een bestand wilt downloaden naar de voorgrond, typt u in de opdrachtconsole voor `fg <command_id>` livereactie.</span><span class="sxs-lookup"><span data-stu-id="577bd-239">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="577bd-240">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="577bd-240">Here are some examples:</span></span>


|<span data-ttu-id="577bd-241">Opdracht</span><span class="sxs-lookup"><span data-stu-id="577bd-241">Command</span></span>  |<span data-ttu-id="577bd-242">Wat het doet</span><span class="sxs-lookup"><span data-stu-id="577bd-242">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="577bd-243">Start het downloaden van een bestand met *some_file.exe* op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="577bd-243">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="577bd-244">Retourneert een download met *opdracht-id 1234* op de voorgrond.</span><span class="sxs-lookup"><span data-stu-id="577bd-244">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="577bd-245">Een bestand in de bibliotheek zetten</span><span class="sxs-lookup"><span data-stu-id="577bd-245">Put a file in the library</span></span>

<span data-ttu-id="577bd-246">Live response heeft een bibliotheek waarin u bestanden kunt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="577bd-246">Live response has a library where you can put files into.</span></span> <span data-ttu-id="577bd-247">In de bibliotheek worden bestanden (zoals scripts) opgeslagen die kunnen worden uitgevoerd in een livereactiesessie op tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="577bd-247">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="577bd-248">Met livereactie kunnen PowerShell-scripts worden uitgevoerd, maar u moet de bestanden eerst in de bibliotheek zetten voordat u ze kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-248">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="577bd-249">U kunt een verzameling PowerShell-scripts hebben die kunnen worden uitgevoerd op apparaten met wie u livereactiesessies start.</span><span class="sxs-lookup"><span data-stu-id="577bd-249">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="577bd-250">Een bestand uploaden in de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="577bd-250">To upload a file in the library</span></span>

1. <span data-ttu-id="577bd-251">Klik **op Bestand uploaden naar bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="577bd-251">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="577bd-252">Klik **op Bladeren** en selecteer het bestand.</span><span class="sxs-lookup"><span data-stu-id="577bd-252">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="577bd-253">Geef een korte beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="577bd-253">Provide a brief description.</span></span>

4. <span data-ttu-id="577bd-254">Geef op of u een bestand met dezelfde naam wilt overschrijven.</span><span class="sxs-lookup"><span data-stu-id="577bd-254">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="577bd-255">Als u wilt weten welke parameters nodig zijn voor het script, schakelt u het selectievakje scriptparameters in.</span><span class="sxs-lookup"><span data-stu-id="577bd-255">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="577bd-256">Voer in het tekstveld een voorbeeld en een beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="577bd-256">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="577bd-257">Klik **op Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="577bd-257">Click **Confirm**.</span></span> 

7. <span data-ttu-id="577bd-258">(Optioneel) Voer de opdracht uit om te controleren of het bestand naar de bibliotheek is `library` geüpload.</span><span class="sxs-lookup"><span data-stu-id="577bd-258">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="577bd-259">Een opdracht annuleren</span><span class="sxs-lookup"><span data-stu-id="577bd-259">Cancel a command</span></span>
<span data-ttu-id="577bd-260">Op elk gewenst moment tijdens een sessie kunt u een opdracht annuleren door op Ctrl + C te drukken.</span><span class="sxs-lookup"><span data-stu-id="577bd-260">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="577bd-261">Als u deze snelkoppeling gebruikt, stopt u de opdracht niet aan de agentzijde.</span><span class="sxs-lookup"><span data-stu-id="577bd-261">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="577bd-262">De opdracht in de portal wordt alleen geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="577bd-262">It will only cancel the command in the portal.</span></span> <span data-ttu-id="577bd-263">Het wijzigen van bewerkingen zoals 'herstel' kan dus doorgaan, terwijl de opdracht wordt geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="577bd-263">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="577bd-264">Vereiste opdrachten automatisch uitvoeren</span><span class="sxs-lookup"><span data-stu-id="577bd-264">Automatically run prerequisite commands</span></span>

<span data-ttu-id="577bd-265">Sommige opdrachten hebben vereiste opdrachten om uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-265">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="577bd-266">Als u de vereiste opdracht niet uit te voeren, krijgt u een foutmelding.</span><span class="sxs-lookup"><span data-stu-id="577bd-266">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="577bd-267">Als u bijvoorbeeld de `download` opdracht zonder uit te `fileinfo` voeren, wordt een fout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="577bd-267">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="577bd-268">U kunt de automatische vlag gebruiken om automatisch vereiste opdrachten uit te voeren, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="577bd-268">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="577bd-269">Een PowerShell-script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="577bd-269">Run a PowerShell script</span></span> 

<span data-ttu-id="577bd-270">Voordat u een PowerShell-script kunt uitvoeren, moet u het eerst uploaden naar de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="577bd-270">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="577bd-271">Nadat u het script naar de bibliotheek hebt geüpload, gebruikt u de `run` opdracht om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="577bd-271">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="577bd-272">Als u van plan bent een niet-ondertekend script te gebruiken in de sessie, moet u de instelling inschakelen op de pagina Geavanceerde [functies instellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="577bd-272">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="577bd-273">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="577bd-273">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="577bd-274">Opdrachtparameters toepassen</span><span class="sxs-lookup"><span data-stu-id="577bd-274">Apply command parameters</span></span>

- <span data-ttu-id="577bd-275">Bekijk de help van de console voor meer informatie over opdrachtparameters.</span><span class="sxs-lookup"><span data-stu-id="577bd-275">View the console help to learn about command parameters.</span></span> <span data-ttu-id="577bd-276">Voer het volgende uit als u meer wilt weten over een afzonderlijke opdracht:</span><span class="sxs-lookup"><span data-stu-id="577bd-276">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="577bd-277">Bij het toepassen van parameters op opdrachten, moet u er rekening mee houden dat parameters worden verwerkt op basis van een vaste volgorde:</span><span class="sxs-lookup"><span data-stu-id="577bd-277">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="577bd-278">Wanneer u parameters opgeeft buiten de vaste volgorde, geeft u de naam van de parameter op met een afbreekstreester voordat u de waarde opgeeft:</span><span class="sxs-lookup"><span data-stu-id="577bd-278">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="577bd-279">Wanneer u opdrachten gebruikt met vereiste opdrachten, kunt u vlaggen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="577bd-279">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="577bd-280">`<command name> -type file -id <file path> - auto` of `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="577bd-280">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="577bd-281">Ondersteunde uitvoertypen</span><span class="sxs-lookup"><span data-stu-id="577bd-281">Supported output types</span></span>

<span data-ttu-id="577bd-282">Livereactie ondersteunt uitvoertypen voor tabel- en JSON-indeling.</span><span class="sxs-lookup"><span data-stu-id="577bd-282">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="577bd-283">Voor elke opdracht is er een standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="577bd-283">For each command, there's a default output behavior.</span></span> <span data-ttu-id="577bd-284">U kunt de uitvoer in de gewenste uitvoerindeling wijzigen met de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="577bd-284">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="577bd-285">Er worden minder velden weergegeven in tabelindeling vanwege de beperkte ruimte.</span><span class="sxs-lookup"><span data-stu-id="577bd-285">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="577bd-286">Als u meer details in de uitvoer wilt zien, kunt u de opdracht JSON-uitvoer gebruiken, zodat er meer details worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="577bd-286">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="577bd-287">Ondersteunde uitvoerpijpen</span><span class="sxs-lookup"><span data-stu-id="577bd-287">Supported output pipes</span></span>

<span data-ttu-id="577bd-288">Live response ondersteunt uitvoerpijpleidingen naar CLI en bestand.</span><span class="sxs-lookup"><span data-stu-id="577bd-288">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="577bd-289">CLI is het standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="577bd-289">CLI is the default output behavior.</span></span> <span data-ttu-id="577bd-290">U kunt de uitvoer naar een bestand uitvoeren met de volgende opdracht: [opdracht] > [bestandsnaam].txt.</span><span class="sxs-lookup"><span data-stu-id="577bd-290">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="577bd-291">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="577bd-291">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="577bd-292">Het opdrachtlogboek weergeven</span><span class="sxs-lookup"><span data-stu-id="577bd-292">View the command log</span></span>

<span data-ttu-id="577bd-293">Selecteer het **tabblad Opdrachtlogboek** om de opdrachten weer te geven die tijdens een sessie op het apparaat zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="577bd-293">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="577bd-294">Elke opdracht wordt bijgespoord met volledige details, zoals:</span><span class="sxs-lookup"><span data-stu-id="577bd-294">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="577bd-295">ID</span><span class="sxs-lookup"><span data-stu-id="577bd-295">ID</span></span>
- <span data-ttu-id="577bd-296">Opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="577bd-296">Command line</span></span>
- <span data-ttu-id="577bd-297">Duur</span><span class="sxs-lookup"><span data-stu-id="577bd-297">Duration</span></span>
- <span data-ttu-id="577bd-298">Status- en invoer- of uitvoerzijdebalk</span><span class="sxs-lookup"><span data-stu-id="577bd-298">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="577bd-299">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="577bd-299">Limitations</span></span>

- <span data-ttu-id="577bd-300">Livereactiesessies zijn beperkt tot 25 livereactiesessies tegelijk.</span><span class="sxs-lookup"><span data-stu-id="577bd-300">Live response sessions are limited to 25 live response sessions at a time.</span></span>
- <span data-ttu-id="577bd-301">De inactieve time-outwaarde voor livereactiesessie is 30 minuten.</span><span class="sxs-lookup"><span data-stu-id="577bd-301">Live response session inactive timeout value is 30 minutes.</span></span> 
- <span data-ttu-id="577bd-302">Een gebruiker kan maximaal tien gelijktijdige sessies starten.</span><span class="sxs-lookup"><span data-stu-id="577bd-302">A user can initiate up to 10 concurrent sessions.</span></span>
- <span data-ttu-id="577bd-303">Een apparaat kan slechts in één sessie tegelijk worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="577bd-303">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="577bd-304">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="577bd-304">The following file size limits apply:</span></span>
   - <span data-ttu-id="577bd-305">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="577bd-305">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="577bd-306">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="577bd-306">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="577bd-307">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="577bd-307">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="577bd-308">Gerelateerd artikel</span><span class="sxs-lookup"><span data-stu-id="577bd-308">Related article</span></span>
- [<span data-ttu-id="577bd-309">Voorbeelden van opdrachten voor Live-reacties</span><span class="sxs-lookup"><span data-stu-id="577bd-309">Live response command examples</span></span>](live-response-command-examples.md)
