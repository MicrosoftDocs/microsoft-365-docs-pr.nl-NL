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
ms.openlocfilehash: d992d98b916f5b59b67706b310edefdb37f157b4
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057474"
---
# <a name="investigate-entities-on-devices-using-live-response"></a><span data-ttu-id="5f06d-104">Entiteiten op apparaten onderzoeken met livereactie</span><span class="sxs-lookup"><span data-stu-id="5f06d-104">Investigate entities on devices using live response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5f06d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="5f06d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5f06d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="5f06d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="5f06d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f06d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="5f06d-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="5f06d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5f06d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="5f06d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="5f06d-110">Live response geeft beveiligingsbewerkingen teams direct toegang tot een apparaat (ook wel een computer genoemd) met behulp van een externe shell-verbinding.</span><span class="sxs-lookup"><span data-stu-id="5f06d-110">Live response gives security operations teams instantaneous access to a device (also referred to as a machine) using a remote shell connection.</span></span> <span data-ttu-id="5f06d-111">Dit geeft u de macht om uitgebreid onderzoek te doen en direct actie te ondernemen om snel geïdentificeerde bedreigingen in realtime te bevatten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-111">This gives you the power to do in-depth investigative work and take immediate response actions to promptly contain identified threats—in real time.</span></span> 

<span data-ttu-id="5f06d-112">Live response is ontworpen om onderzoeken te verbeteren door uw beveiligingsteam in staat te stellen om gerechtelijke gegevens te verzamelen, scripts uit te voeren, verdachte entiteiten te verzenden voor analyse, bedreigingen te corrigeren en proactief te zoeken naar nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-112">Live response is designed to enhance investigations by enabling your security operations team to collect forensic data, run scripts, send suspicious entities for analysis, remediate threats, and proactively hunt for emerging threats.</span></span><br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4qLUW]

<span data-ttu-id="5f06d-113">Met livereactie kunnen analisten alle volgende taken uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="5f06d-113">With live response, analysts can do all of the following tasks:</span></span>
- <span data-ttu-id="5f06d-114">Voer eenvoudige en geavanceerde opdrachten uit om onderzoek te doen op een apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-114">Run basic and advanced commands to do investigative work on a device.</span></span>
- <span data-ttu-id="5f06d-115">Download bestanden zoals malwarevoorbeelden en resultaten van PowerShell-scripts.</span><span class="sxs-lookup"><span data-stu-id="5f06d-115">Download files such as malware samples and outcomes of PowerShell scripts.</span></span>
- <span data-ttu-id="5f06d-116">Bestanden op de achtergrond downloaden (nieuw!).</span><span class="sxs-lookup"><span data-stu-id="5f06d-116">Download files in the background (new!).</span></span>
- <span data-ttu-id="5f06d-117">Upload een PowerShell-script of uitvoerbaar naar de bibliotheek en voer het uit op een apparaat vanaf tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="5f06d-117">Upload a PowerShell script or executable to the library and run it on a device from a tenant level.</span></span>
- <span data-ttu-id="5f06d-118">Herstelacties uitvoeren of ongedaan maken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-118">Take or undo remediation actions.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5f06d-119">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="5f06d-119">Before you begin</span></span>

<span data-ttu-id="5f06d-120">Voordat u een sessie op een apparaat kunt starten, moet u aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="5f06d-120">Before you can initiate a session on a device, make sure you fulfill the following requirements:</span></span>

- <span data-ttu-id="5f06d-121">**Controleer of u een ondersteunde versie van Windows gebruikt.**</span><span class="sxs-lookup"><span data-stu-id="5f06d-121">**Verify that you're running a supported version of Windows**.</span></span> <br/>
<span data-ttu-id="5f06d-122">Apparaten moeten een van de volgende versies van Windows uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5f06d-122">Devices must be running one of the following versions of Windows</span></span>

  - <span data-ttu-id="5f06d-123">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="5f06d-123">**Windows 10**</span></span>
    - <span data-ttu-id="5f06d-124">[Versie 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) of hoger</span><span class="sxs-lookup"><span data-stu-id="5f06d-124">[Version 1909](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1909) or later</span></span>  
    - <span data-ttu-id="5f06d-125">[Versie 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span><span class="sxs-lookup"><span data-stu-id="5f06d-125">[Version 1903](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1903) with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)</span></span>
    - <span data-ttu-id="5f06d-126">[Versie 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) [met KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span><span class="sxs-lookup"><span data-stu-id="5f06d-126">[Version 1809 (RS 5)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1809) with [with KB4537818](https://support.microsoft.com/help/4537818/windows-10-update-kb4537818)</span></span>
    - <span data-ttu-id="5f06d-127">[Versie 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) met [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span><span class="sxs-lookup"><span data-stu-id="5f06d-127">[Version 1803 (RS 4)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803) with [KB4537795](https://support.microsoft.com/help/4537795/windows-10-update-kb4537795)</span></span>
    - <span data-ttu-id="5f06d-128">[Versie 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) met [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span><span class="sxs-lookup"><span data-stu-id="5f06d-128">[Version 1709 (RS 3)](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) with [KB4537816](https://support.microsoft.com/help/4537816/windows-10-update-kb4537816)</span></span>
  
  - <span data-ttu-id="5f06d-129">**Windows Server 2019 - Alleen van toepassing op openbare preview**</span><span class="sxs-lookup"><span data-stu-id="5f06d-129">**Windows Server 2019 - Only applicable for Public preview**</span></span>
    - <span data-ttu-id="5f06d-130">Versie 1903 of (met [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span><span class="sxs-lookup"><span data-stu-id="5f06d-130">Version 1903 or (with [KB4515384](https://support.microsoft.com/en-us/help/4515384/windows-10-update-kb4515384)) later</span></span> 
    - <span data-ttu-id="5f06d-131">Versie 1809 (met [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span><span class="sxs-lookup"><span data-stu-id="5f06d-131">Version 1809 (with [KB4537818](https://support.microsoft.com/en-us/help/4537818/windows-10-update-kb4537818))</span></span>

- <span data-ttu-id="5f06d-132">**Schakel livereactie in vanaf de pagina met geavanceerde instellingen.**</span><span class="sxs-lookup"><span data-stu-id="5f06d-132">**Enable live response from the advanced settings page**.</span></span><br>
<span data-ttu-id="5f06d-133">U moet de mogelijkheid voor livereactie inschakelen op de [pagina Instellingen voor geavanceerde](advanced-features.md) functies.</span><span class="sxs-lookup"><span data-stu-id="5f06d-133">You'll need to enable the live response capability in the [Advanced features settings](advanced-features.md) page.</span></span>

    >[!NOTE]
    ><span data-ttu-id="5f06d-134">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-134">Only users with manage security or global admin roles can edit these settings.</span></span>

- <span data-ttu-id="5f06d-135">**Schakel livereactie voor servers in vanaf de pagina met geavanceerde instellingen** (aanbevolen).</span><span class="sxs-lookup"><span data-stu-id="5f06d-135">**Enable live response for servers from the advanced settings page** (recommended).</span></span><br>

    >[!NOTE]
    ><span data-ttu-id="5f06d-136">Alleen gebruikers met beveiligings- of globale beheerdersrollen kunnen deze instellingen bewerken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-136">Only users with manage security or global admin roles can edit these settings.</span></span>
    
- <span data-ttu-id="5f06d-137">**Controleer of aan het apparaat een automatiseringssaneringsniveau is toegewezen.**</span><span class="sxs-lookup"><span data-stu-id="5f06d-137">**Ensure that the device has an Automation Remediation level assigned to it**.</span></span><br>
<span data-ttu-id="5f06d-138">U moet ten minste het minimale herstelniveau voor een bepaalde apparaatgroep inschakelen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-138">You'll need to enable, at least, the minimum Remediation Level for a given Device Group.</span></span> <span data-ttu-id="5f06d-139">Anders kunt u geen livereactiesessie voor een lid van die groep opzetten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-139">Otherwise you won't be able to establish a Live Response session to a member of that group.</span></span>

    <span data-ttu-id="5f06d-140">U krijgt de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="5f06d-140">You'll receive the following error:</span></span>

    ![Afbeelding van foutbericht](images/live-response-error.png)

- <span data-ttu-id="5f06d-142">**Live response unsigned script execution (optioneel)** inschakelen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-142">**Enable live response unsigned script execution** (optional).</span></span> <br>

    >[!WARNING]
    ><span data-ttu-id="5f06d-143">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-143">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>
 
  <span data-ttu-id="5f06d-144">Het uitvoeren van niet-ondertekende scripts wordt afgeraden, omdat dit uw blootstelling aan bedreigingen kan vergroten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-144">Running unsigned scripts is not recommended as it can increase your exposure to threats.</span></span> <span data-ttu-id="5f06d-145">Als u deze echter moet gebruiken, moet u de instelling inschakelen op de pagina Geavanceerde [functiesinstellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-145">If you must use them however, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>
    
- <span data-ttu-id="5f06d-146">**Controleer of u de juiste machtigingen hebt.**</span><span class="sxs-lookup"><span data-stu-id="5f06d-146">**Ensure that you have the appropriate permissions**.</span></span><br>
    <span data-ttu-id="5f06d-147">Alleen gebruikers die zijn ingericht met de juiste machtigingen, kunnen een sessie starten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-147">Only users who have been provisioned with the appropriate permissions can initiate a session.</span></span> <span data-ttu-id="5f06d-148">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-148">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

    > [!IMPORTANT]
    > <span data-ttu-id="5f06d-149">De optie om een bestand te uploaden naar de bibliotheek is alleen beschikbaar voor personen met de juiste RBAC-machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-149">The option to upload a file to the library is only available to those with the appropriate RBAC permissions.</span></span> <span data-ttu-id="5f06d-150">De knop is grijs voor gebruikers met alleen gedelegeerde machtigingen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-150">The button is greyed out for users with only delegated permissions.</span></span>

    <span data-ttu-id="5f06d-151">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-151">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="5f06d-152">Gebruikersmachtigingen worden bepaald door de aangepaste rol van RBAC.</span><span class="sxs-lookup"><span data-stu-id="5f06d-152">Users permissions are controlled by RBAC custom role.</span></span> 

## <a name="live-response-dashboard-overview"></a><span data-ttu-id="5f06d-153">Overzicht van livereactiedashboard</span><span class="sxs-lookup"><span data-stu-id="5f06d-153">Live response dashboard overview</span></span>
<span data-ttu-id="5f06d-154">Wanneer u een livereactiesessie start op een apparaat, wordt er een dashboard geopend.</span><span class="sxs-lookup"><span data-stu-id="5f06d-154">When you initiate a live response session on a device, a dashboard opens.</span></span> <span data-ttu-id="5f06d-155">Het dashboard bevat informatie over de sessie, zoals de volgende:</span><span class="sxs-lookup"><span data-stu-id="5f06d-155">The dashboard provides information about the session such as the following:</span></span> 

- <span data-ttu-id="5f06d-156">Wie heeft de sessie gemaakt</span><span class="sxs-lookup"><span data-stu-id="5f06d-156">Who created the session</span></span>
- <span data-ttu-id="5f06d-157">Wanneer de sessie is gestart</span><span class="sxs-lookup"><span data-stu-id="5f06d-157">When the session started</span></span>
- <span data-ttu-id="5f06d-158">De duur van de sessie</span><span class="sxs-lookup"><span data-stu-id="5f06d-158">The duration of the session</span></span>

<span data-ttu-id="5f06d-159">Het dashboard biedt u ook toegang tot:</span><span class="sxs-lookup"><span data-stu-id="5f06d-159">The dashboard also gives you access to:</span></span>
- <span data-ttu-id="5f06d-160">Sessie verbreken</span><span class="sxs-lookup"><span data-stu-id="5f06d-160">Disconnect session</span></span>
- <span data-ttu-id="5f06d-161">Bestanden uploaden naar de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="5f06d-161">Upload files to the library</span></span> 
- <span data-ttu-id="5f06d-162">Opdrachtconsole</span><span class="sxs-lookup"><span data-stu-id="5f06d-162">Command console</span></span>
- <span data-ttu-id="5f06d-163">Opdrachtlogboek</span><span class="sxs-lookup"><span data-stu-id="5f06d-163">Command log</span></span>


## <a name="initiate-a-live-response-session-on-a-device"></a><span data-ttu-id="5f06d-164">Een livereactiesessie starten op een apparaat</span><span class="sxs-lookup"><span data-stu-id="5f06d-164">Initiate a live response session on a device</span></span> 

1. <span data-ttu-id="5f06d-165">Meld u aan bij het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="5f06d-165">Sign in to Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="5f06d-166">Ga naar de pagina apparatenlijst en selecteer een apparaat dat u wilt onderzoeken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-166">Navigate to the devices list page and select a device to investigate.</span></span> <span data-ttu-id="5f06d-167">De pagina Apparaten wordt geopend.</span><span class="sxs-lookup"><span data-stu-id="5f06d-167">The devices page opens.</span></span>

3. <span data-ttu-id="5f06d-168">Start de livereactiesessie door **Livereactiesessie starten te selecteren.**</span><span class="sxs-lookup"><span data-stu-id="5f06d-168">Launch the live response session by selecting **Initiate live response session**.</span></span> <span data-ttu-id="5f06d-169">Er wordt een opdrachtconsole weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5f06d-169">A command console is displayed.</span></span> <span data-ttu-id="5f06d-170">Wacht totdat de sessie verbinding maakt met het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-170">Wait while the session connects to the device.</span></span>

4. <span data-ttu-id="5f06d-171">Gebruik de ingebouwde opdrachten om onderzoekswerk te doen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-171">Use the built-in commands to do investigative work.</span></span> <span data-ttu-id="5f06d-172">Zie [Live-antwoordopdrachten voor meer informatie.](#live-response-commands)</span><span class="sxs-lookup"><span data-stu-id="5f06d-172">For more information, see [Live response commands](#live-response-commands).</span></span>

5. <span data-ttu-id="5f06d-173">Nadat u het onderzoek hebt afgerond, **selecteert** u Sessie verbreken en selecteert u **Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="5f06d-173">After completing your investigation, select **Disconnect session**, then select **Confirm**.</span></span>

## <a name="live-response-commands"></a><span data-ttu-id="5f06d-174">Opdrachten voor livereacties</span><span class="sxs-lookup"><span data-stu-id="5f06d-174">Live response commands</span></span>

<span data-ttu-id="5f06d-175">Afhankelijk van de rol die aan u is verleend, kunt u eenvoudige of geavanceerde opdrachten voor livereacties uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-175">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="5f06d-176">Gebruikersmachtigingen worden beheerd door aangepaste rollen van RBAC.</span><span class="sxs-lookup"><span data-stu-id="5f06d-176">User permissions are controlled by RBAC custom roles.</span></span> <span data-ttu-id="5f06d-177">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-177">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 


>[!NOTE]
><span data-ttu-id="5f06d-178">Live response is een interactieve shell in de cloud, dus specifieke opdrachtervaring kan variëren in reactietijd, afhankelijk van de netwerkkwaliteit en de systeembelasting tussen de eindgebruiker en het doelapparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-178">Live response is a cloud-based interactive shell, as such, specific command experience may vary in response time depending on network quality and system load between the end user and the target device.</span></span>

### <a name="basic-commands"></a><span data-ttu-id="5f06d-179">Basisopdrachten</span><span class="sxs-lookup"><span data-stu-id="5f06d-179">Basic commands</span></span>

<span data-ttu-id="5f06d-180">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om basisopdrachten **voor** livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-180">The following commands are available for user roles that are granted the ability to run **basic** live response commands.</span></span> <span data-ttu-id="5f06d-181">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-181">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="5f06d-182">Opdracht</span><span class="sxs-lookup"><span data-stu-id="5f06d-182">Command</span></span> | <span data-ttu-id="5f06d-183">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5f06d-183">Description</span></span> |
|---|---|--- |
|`cd` | <span data-ttu-id="5f06d-184">Wijzigt de huidige adreslijst.</span><span class="sxs-lookup"><span data-stu-id="5f06d-184">Changes the current directory.</span></span> | 
|`cls` | <span data-ttu-id="5f06d-185">Het scherm van de console wordt gewed.</span><span class="sxs-lookup"><span data-stu-id="5f06d-185">Clears the console screen.</span></span>  |
|`connect` | <span data-ttu-id="5f06d-186">Start een livereactiesessie op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-186">Initiates a live response session to the device.</span></span> |
|`connections` | <span data-ttu-id="5f06d-187">Toont alle actieve verbindingen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-187">Shows all the active connections.</span></span> |
|`dir` | <span data-ttu-id="5f06d-188">Toont een lijst met bestanden en subdirectorieën in een adreslijst.</span><span class="sxs-lookup"><span data-stu-id="5f06d-188">Shows a list of files and subdirectories in a directory.</span></span> |
|`download <file_path> &` | <span data-ttu-id="5f06d-189">Hiermee downloadt u een bestand op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="5f06d-189">Downloads a file in the background.</span></span> |
<span data-ttu-id="5f06d-190">stuurprogramma's</span><span class="sxs-lookup"><span data-stu-id="5f06d-190">drivers</span></span> |  <span data-ttu-id="5f06d-191">Toont alle stuurprogramma's die op het apparaat zijn geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="5f06d-191">Shows all drivers installed on the device.</span></span> |
|`fg <command ID>` | <span data-ttu-id="5f06d-192">Retourneert een bestand dat is gedownload naar de voorgrond.</span><span class="sxs-lookup"><span data-stu-id="5f06d-192">Returns a file download to the foreground.</span></span> |
|`fileinfo` | <span data-ttu-id="5f06d-193">Informatie over een bestand.</span><span class="sxs-lookup"><span data-stu-id="5f06d-193">Get information about a file.</span></span> |
|`findfile` | <span data-ttu-id="5f06d-194">Zoekt bestanden op een bepaalde naam op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-194">Locates files by a given name on the device.</span></span> |
|`help` | <span data-ttu-id="5f06d-195">Biedt help-informatie voor opdrachten voor livereacties.</span><span class="sxs-lookup"><span data-stu-id="5f06d-195">Provides help information for live response commands.</span></span> |
|`persistence` | <span data-ttu-id="5f06d-196">Toont alle bekende persistentiemethoden op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-196">Shows all known persistence methods on the device.</span></span> |
|`processes` | <span data-ttu-id="5f06d-197">Toont alle processen die op het apparaat worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="5f06d-197">Shows all processes running on the device.</span></span> |
|`registry` | <span data-ttu-id="5f06d-198">Geeft registerwaarden weer.</span><span class="sxs-lookup"><span data-stu-id="5f06d-198">Shows registry values.</span></span> |
|`scheduledtasks` | <span data-ttu-id="5f06d-199">Toont alle geplande taken op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-199">Shows all scheduled tasks on the device.</span></span> |
|`services` | <span data-ttu-id="5f06d-200">Toont alle services op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-200">Shows all services on the device.</span></span> |
|`trace` | <span data-ttu-id="5f06d-201">Hiermee stelt u de logboekregistratiemodus van de terminal in op foutopsporing.</span><span class="sxs-lookup"><span data-stu-id="5f06d-201">Sets the terminal's logging mode to debug.</span></span> |

### <a name="advanced-commands"></a><span data-ttu-id="5f06d-202">Geavanceerde opdrachten</span><span class="sxs-lookup"><span data-stu-id="5f06d-202">Advanced commands</span></span>
<span data-ttu-id="5f06d-203">De volgende opdrachten zijn beschikbaar voor gebruikersrollen die de mogelijkheid krijgen om geavanceerde **opdrachten** voor livereacties uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-203">The following commands are available for user roles that are granted the ability to run **advanced** live response commands.</span></span> <span data-ttu-id="5f06d-204">Zie Rollen maken en beheren voor meer informatie over [roltoewijzingen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-204">For more information on role assignments, see [Create and manage roles](user-roles.md).</span></span> 

| <span data-ttu-id="5f06d-205">Opdracht</span><span class="sxs-lookup"><span data-stu-id="5f06d-205">Command</span></span> | <span data-ttu-id="5f06d-206">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="5f06d-206">Description</span></span> |
|---|---|
| `analyze` | <span data-ttu-id="5f06d-207">Analyseert de entiteit met verschillende belastende motoren om tot een uitspraak te komen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-207">Analyses the entity with various incrimination engines to reach a verdict.</span></span> |
| `getfile` | <span data-ttu-id="5f06d-208">Haalt een bestand op van het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-208">Gets a file from the device.</span></span> <br> <span data-ttu-id="5f06d-209">OPMERKING: Deze opdracht heeft een vereiste opdracht.</span><span class="sxs-lookup"><span data-stu-id="5f06d-209">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="5f06d-210">U kunt de opdracht in combinatie met de opdracht gebruiken `-auto` om de vereiste opdracht automatisch uit te `getfile` voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-210">You can use the `-auto` command in conjunction with `getfile` to automatically run the prerequisite command.</span></span> |
| `run` | <span data-ttu-id="5f06d-211">Voert een PowerShell-script uit vanuit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-211">Runs a PowerShell script from the library on the device.</span></span> |
| `library` | <span data-ttu-id="5f06d-212">Hiermee worden bestanden vermeld die zijn geüpload naar de live antwoordbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="5f06d-212">Lists files that were uploaded to the live response library.</span></span> |
| `putfile` | <span data-ttu-id="5f06d-213">Zet een bestand uit de bibliotheek op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-213">Puts a file from the library to the device.</span></span> <span data-ttu-id="5f06d-214">Bestanden worden opgeslagen in een werkmap en worden verwijderd wanneer het apparaat standaard opnieuw wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="5f06d-214">Files are saved in a working folder and are deleted when the device restarts by default.</span></span> |
| `remediate` | <span data-ttu-id="5f06d-215">Herstelt een entiteit op het apparaat.</span><span class="sxs-lookup"><span data-stu-id="5f06d-215">Remediates an entity on the device.</span></span> <span data-ttu-id="5f06d-216">De herstelactie is afhankelijk van het entiteitstype:</span><span class="sxs-lookup"><span data-stu-id="5f06d-216">The remediation action will vary depending on the entity type:</span></span><br><span data-ttu-id="5f06d-217">- Bestand: verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-217">- File: delete</span></span><br><span data-ttu-id="5f06d-218">- Proces: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-218">- Process: stop, delete image file</span></span><br><span data-ttu-id="5f06d-219">- Service: stoppen, afbeeldingsbestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-219">- Service: stop, delete image file</span></span><br><span data-ttu-id="5f06d-220">- Registerinvoer: verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-220">- Registry entry: delete</span></span><br><span data-ttu-id="5f06d-221">- Geplande taak: verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-221">- Scheduled task: remove</span></span><br><span data-ttu-id="5f06d-222">- Mapitem opstarten: bestand verwijderen</span><span class="sxs-lookup"><span data-stu-id="5f06d-222">- Startup folder item: delete file</span></span> <br> <span data-ttu-id="5f06d-223">OPMERKING: Deze opdracht heeft een vereiste opdracht.</span><span class="sxs-lookup"><span data-stu-id="5f06d-223">NOTE: This command has a prerequisite command.</span></span> <span data-ttu-id="5f06d-224">U kunt de opdracht in combinatie met de opdracht gebruiken `-auto` om de vereiste opdracht automatisch uit te `remediate` voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-224">You can use the `-auto` command in conjunction with `remediate` to automatically run the prerequisite command.</span></span> 
|`undo` | <span data-ttu-id="5f06d-225">Herstelt een entiteit die is hersteld.</span><span class="sxs-lookup"><span data-stu-id="5f06d-225">Restores an entity that was remediated.</span></span> |


## <a name="use-live-response-commands"></a><span data-ttu-id="5f06d-226">Opdrachten voor livereacties gebruiken</span><span class="sxs-lookup"><span data-stu-id="5f06d-226">Use live response commands</span></span>

<span data-ttu-id="5f06d-227">De opdrachten die u in de console kunt gebruiken, volgen dezelfde principes als [Windows-opdrachten.](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c)</span><span class="sxs-lookup"><span data-stu-id="5f06d-227">The commands that you can use in the console follow similar principles as [Windows Commands](https://docs.microsoft.com/windows-server/administration/windows-commands/windows-commands#BKMK_c).</span></span>

<span data-ttu-id="5f06d-228">De geavanceerde opdrachten bieden een krachtigere reeks acties waarmee u krachtigere acties kunt uitvoeren, zoals het downloaden en uploaden van een bestand, het uitvoeren van scripts op het apparaat en het uitvoeren van herstelacties voor een entiteit.</span><span class="sxs-lookup"><span data-stu-id="5f06d-228">The advanced commands offer a more robust set of actions that allow you to take more powerful actions such as download and upload a file, run scripts on the device, and take remediation actions on an entity.</span></span>

### <a name="get-a-file-from-the-device"></a><span data-ttu-id="5f06d-229">Een bestand van het apparaat downloaden</span><span class="sxs-lookup"><span data-stu-id="5f06d-229">Get a file from the device</span></span>

<span data-ttu-id="5f06d-230">Voor scenario's wanneer u een bestand wilt downloaden van een apparaat dat u onderzoekt, kunt u de opdracht `getfile` gebruiken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-230">For scenarios when you'd like get a file from a device you're investigating, you can use the `getfile` command.</span></span> <span data-ttu-id="5f06d-231">Hiermee kunt u het bestand opslaan vanaf het apparaat voor verder onderzoek.</span><span class="sxs-lookup"><span data-stu-id="5f06d-231">This allows you to save the file from the device for further investigation.</span></span>

>[!NOTE]
><span data-ttu-id="5f06d-232">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="5f06d-232">The following file size limits apply:</span></span>
>- <span data-ttu-id="5f06d-233">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="5f06d-233">`getfile` limit: 3 GB</span></span>
>- <span data-ttu-id="5f06d-234">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="5f06d-234">`fileinfo` limit: 10 GB</span></span>
>- <span data-ttu-id="5f06d-235">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="5f06d-235">`library` limit: 250 MB</span></span>

### <a name="download-a-file-in-the-background"></a><span data-ttu-id="5f06d-236">Een bestand op de achtergrond downloaden</span><span class="sxs-lookup"><span data-stu-id="5f06d-236">Download a file in the background</span></span>

<span data-ttu-id="5f06d-237">Als u wilt dat uw beveiligingsteam een beïnvloed apparaat kan blijven onderzoeken, kunnen bestanden nu op de achtergrond worden gedownload.</span><span class="sxs-lookup"><span data-stu-id="5f06d-237">To enable your security operations team to continue investigating an impacted device, files can now be downloaded in the background.</span></span>

- <span data-ttu-id="5f06d-238">Als u een bestand op de achtergrond wilt downloaden, typt u in de opdrachtconsole voor `download <file_path> &` livereactie.</span><span class="sxs-lookup"><span data-stu-id="5f06d-238">To download a file in the background, in the live response command console, type `download <file_path> &`.</span></span>
- <span data-ttu-id="5f06d-239">Als u wacht totdat een bestand wordt gedownload, kunt u het naar de achtergrond verplaatsen met Ctrl+ Z.</span><span class="sxs-lookup"><span data-stu-id="5f06d-239">If you are waiting for a file to be downloaded, you can move it to the background by using Ctrl + Z.</span></span>
- <span data-ttu-id="5f06d-240">Als u een bestand wilt downloaden naar de voorgrond, typt u in de opdrachtconsole voor `fg <command_id>` livereactie.</span><span class="sxs-lookup"><span data-stu-id="5f06d-240">To bring a file download to the foreground, in the live response command console, type `fg <command_id>`.</span></span>

<span data-ttu-id="5f06d-241">Dit zijn enkele voorbeelden:</span><span class="sxs-lookup"><span data-stu-id="5f06d-241">Here are some examples:</span></span>


|<span data-ttu-id="5f06d-242">Opdracht</span><span class="sxs-lookup"><span data-stu-id="5f06d-242">Command</span></span>  |<span data-ttu-id="5f06d-243">Wat het doet</span><span class="sxs-lookup"><span data-stu-id="5f06d-243">What it does</span></span>  |
|---------|---------|
|`Download "C:\windows\some_file.exe" &`     |<span data-ttu-id="5f06d-244">Start het downloaden van een bestand met *some_file.exe* op de achtergrond.</span><span class="sxs-lookup"><span data-stu-id="5f06d-244">Starts downloading a file named *some_file.exe* in the background.</span></span>         |
|`fg 1234`     |<span data-ttu-id="5f06d-245">Retourneert een download met *opdracht-id 1234* op de voorgrond.</span><span class="sxs-lookup"><span data-stu-id="5f06d-245">Returns a download with command ID *1234* to the foreground.</span></span>         |


### <a name="put-a-file-in-the-library"></a><span data-ttu-id="5f06d-246">Een bestand in de bibliotheek zetten</span><span class="sxs-lookup"><span data-stu-id="5f06d-246">Put a file in the library</span></span>

<span data-ttu-id="5f06d-247">Live response heeft een bibliotheek waarin u bestanden kunt plaatsen.</span><span class="sxs-lookup"><span data-stu-id="5f06d-247">Live response has a library where you can put files into.</span></span> <span data-ttu-id="5f06d-248">In de bibliotheek worden bestanden (zoals scripts) opgeslagen die kunnen worden uitgevoerd in een livereactiesessie op tenantniveau.</span><span class="sxs-lookup"><span data-stu-id="5f06d-248">The library stores files (such as scripts) that can be run in a live response session at the tenant level.</span></span>

<span data-ttu-id="5f06d-249">Met livereactie kunnen PowerShell-scripts worden uitgevoerd, maar u moet de bestanden eerst in de bibliotheek zetten voordat u ze kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-249">Live response allows PowerShell scripts to run, however you must first put the files into the library before you can run them.</span></span> 

<span data-ttu-id="5f06d-250">U kunt een verzameling PowerShell-scripts hebben die kunnen worden uitgevoerd op apparaten met wie u livereactiesessies start.</span><span class="sxs-lookup"><span data-stu-id="5f06d-250">You can have a collection of PowerShell scripts that can run on devices that you initiate live response sessions with.</span></span> 

#### <a name="to-upload-a-file-in-the-library"></a><span data-ttu-id="5f06d-251">Een bestand uploaden in de bibliotheek</span><span class="sxs-lookup"><span data-stu-id="5f06d-251">To upload a file in the library</span></span>

1. <span data-ttu-id="5f06d-252">Klik **op Bestand uploaden naar bibliotheek**.</span><span class="sxs-lookup"><span data-stu-id="5f06d-252">Click **Upload file to library**.</span></span> 

2. <span data-ttu-id="5f06d-253">Klik **op Bladeren** en selecteer het bestand.</span><span class="sxs-lookup"><span data-stu-id="5f06d-253">Click **Browse** and select the file.</span></span>

3. <span data-ttu-id="5f06d-254">Geef een korte beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="5f06d-254">Provide a brief description.</span></span>

4. <span data-ttu-id="5f06d-255">Geef op of u een bestand met dezelfde naam wilt overschrijven.</span><span class="sxs-lookup"><span data-stu-id="5f06d-255">Specify if you'd like to overwrite a file with the same name.</span></span>

5. <span data-ttu-id="5f06d-256">Als u wilt weten welke parameters nodig zijn voor het script, schakelt u het selectievakje scriptparameters in.</span><span class="sxs-lookup"><span data-stu-id="5f06d-256">If you'd like to be,  know what parameters are needed for the script, select the script parameters check box.</span></span> <span data-ttu-id="5f06d-257">Voer in het tekstveld een voorbeeld en een beschrijving in.</span><span class="sxs-lookup"><span data-stu-id="5f06d-257">In the text field, enter an example and a description.</span></span>

6. <span data-ttu-id="5f06d-258">Klik **op Bevestigen**.</span><span class="sxs-lookup"><span data-stu-id="5f06d-258">Click **Confirm**.</span></span> 

7. <span data-ttu-id="5f06d-259">(Optioneel) Voer de opdracht uit om te controleren of het bestand naar de bibliotheek is `library` geüpload.</span><span class="sxs-lookup"><span data-stu-id="5f06d-259">(Optional) To verify that the file was uploaded to the library, run the `library` command.</span></span>


### <a name="cancel-a-command"></a><span data-ttu-id="5f06d-260">Een opdracht annuleren</span><span class="sxs-lookup"><span data-stu-id="5f06d-260">Cancel a command</span></span>
<span data-ttu-id="5f06d-261">Op elk gewenst moment tijdens een sessie kunt u een opdracht annuleren door op Ctrl + C te drukken.</span><span class="sxs-lookup"><span data-stu-id="5f06d-261">Anytime during a session, you can cancel a command by pressing CTRL + C.</span></span>  

>[!WARNING]
><span data-ttu-id="5f06d-262">Als u deze snelkoppeling gebruikt, stopt u de opdracht niet aan de agentzijde.</span><span class="sxs-lookup"><span data-stu-id="5f06d-262">Using this shortcut will not stop the command in the agent side.</span></span> <span data-ttu-id="5f06d-263">De opdracht in de portal wordt alleen geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="5f06d-263">It will only cancel the command in the portal.</span></span> <span data-ttu-id="5f06d-264">Het wijzigen van bewerkingen zoals 'herstel' kan dus doorgaan, terwijl de opdracht wordt geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="5f06d-264">So, changing operations such as "remediate" may continue, while the command is canceled.</span></span> 

### <a name="automatically-run-prerequisite-commands"></a><span data-ttu-id="5f06d-265">Vereiste opdrachten automatisch uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5f06d-265">Automatically run prerequisite commands</span></span>

<span data-ttu-id="5f06d-266">Sommige opdrachten hebben vereiste opdrachten om uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-266">Some commands have prerequisite commands to run.</span></span> <span data-ttu-id="5f06d-267">Als u de vereiste opdracht niet uit te voeren, krijgt u een foutmelding.</span><span class="sxs-lookup"><span data-stu-id="5f06d-267">If you don't run the prerequisite command, you'll get an error.</span></span> <span data-ttu-id="5f06d-268">Als u bijvoorbeeld de `download` opdracht zonder uit te `fileinfo` voeren, wordt een fout weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5f06d-268">For example, running the `download` command without `fileinfo` will return an error.</span></span>

<span data-ttu-id="5f06d-269">U kunt de automatische vlag gebruiken om automatisch vereiste opdrachten uit te voeren, bijvoorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5f06d-269">You can use the auto flag to automatically run prerequisite commands, for example:</span></span>

```console
getfile c:\Users\user\Desktop\work.txt -auto
```

## <a name="run-a-powershell-script"></a><span data-ttu-id="5f06d-270">Een PowerShell-script uitvoeren</span><span class="sxs-lookup"><span data-stu-id="5f06d-270">Run a PowerShell script</span></span> 

<span data-ttu-id="5f06d-271">Voordat u een PowerShell-script kunt uitvoeren, moet u het eerst uploaden naar de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="5f06d-271">Before you can run a PowerShell script, you must first upload it to the library.</span></span> 

<span data-ttu-id="5f06d-272">Nadat u het script naar de bibliotheek hebt geüpload, gebruikt u de `run` opdracht om het script uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="5f06d-272">After uploading the script to the library, use the `run` command to run the script.</span></span>

<span data-ttu-id="5f06d-273">Als u van plan bent een niet-ondertekend script te gebruiken in de sessie, moet u de instelling inschakelen op de pagina Geavanceerde [functies instellingen.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="5f06d-273">If you plan to use an unsigned script in the session, you'll need to enable the setting in the [Advanced features settings](advanced-features.md) page.</span></span>

>[!WARNING]
><span data-ttu-id="5f06d-274">Als u het gebruik van niet-ondertekende scripts toestaat, kunt u uw blootstelling aan bedreigingen vergroten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-274">Allowing the use of unsigned scripts may increase your exposure to threats.</span></span>

## <a name="apply-command-parameters"></a><span data-ttu-id="5f06d-275">Opdrachtparameters toepassen</span><span class="sxs-lookup"><span data-stu-id="5f06d-275">Apply command parameters</span></span>

- <span data-ttu-id="5f06d-276">Bekijk de help van de console voor meer informatie over opdrachtparameters.</span><span class="sxs-lookup"><span data-stu-id="5f06d-276">View the console help to learn about command parameters.</span></span> <span data-ttu-id="5f06d-277">Voer het volgende uit als u meer wilt weten over een afzonderlijke opdracht:</span><span class="sxs-lookup"><span data-stu-id="5f06d-277">To learn about an individual command, run:</span></span>
 
    `help <command name>`

- <span data-ttu-id="5f06d-278">Bij het toepassen van parameters op opdrachten, moet u er rekening mee houden dat parameters worden verwerkt op basis van een vaste volgorde:</span><span class="sxs-lookup"><span data-stu-id="5f06d-278">When applying parameters to commands, note that parameters are handled based on a fixed order:</span></span>
 
    `<command name> param1 param2` 

- <span data-ttu-id="5f06d-279">Wanneer u parameters opgeeft buiten de vaste volgorde, geeft u de naam van de parameter op met een afbreekstreester voordat u de waarde opgeeft:</span><span class="sxs-lookup"><span data-stu-id="5f06d-279">When specifying parameters outside of the fixed order, specify the name of the parameter with a hyphen before providing the value:</span></span>
 
    `<command name> -param2_name param2`

- <span data-ttu-id="5f06d-280">Wanneer u opdrachten gebruikt met vereiste opdrachten, kunt u vlaggen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="5f06d-280">When using commands that have prerequisite commands, you can use flags:</span></span>

    <span data-ttu-id="5f06d-281">`<command name> -type file -id <file path> - auto` of `remediate file <file path> - auto` .</span><span class="sxs-lookup"><span data-stu-id="5f06d-281">`<command name> -type file -id <file path> - auto` or `remediate file <file path> - auto`.</span></span>

## <a name="supported-output-types"></a><span data-ttu-id="5f06d-282">Ondersteunde uitvoertypen</span><span class="sxs-lookup"><span data-stu-id="5f06d-282">Supported output types</span></span>

<span data-ttu-id="5f06d-283">Livereactie ondersteunt uitvoertypen voor tabel- en JSON-indeling.</span><span class="sxs-lookup"><span data-stu-id="5f06d-283">Live response supports table and JSON format output types.</span></span> <span data-ttu-id="5f06d-284">Voor elke opdracht is er een standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="5f06d-284">For each command, there's a default output behavior.</span></span> <span data-ttu-id="5f06d-285">U kunt de uitvoer in de gewenste uitvoerindeling wijzigen met de volgende opdrachten:</span><span class="sxs-lookup"><span data-stu-id="5f06d-285">You can modify the output in your preferred output format using the following commands:</span></span>

- `-output json`
- `-output table`

>[!NOTE]
><span data-ttu-id="5f06d-286">Er worden minder velden weergegeven in tabelindeling vanwege de beperkte ruimte.</span><span class="sxs-lookup"><span data-stu-id="5f06d-286">Fewer fields are shown in table format due to the limited space.</span></span> <span data-ttu-id="5f06d-287">Als u meer details in de uitvoer wilt zien, kunt u de opdracht JSON-uitvoer gebruiken, zodat er meer details worden weergegeven.</span><span class="sxs-lookup"><span data-stu-id="5f06d-287">To see more details in the output, you can use the JSON output command so that more details are shown.</span></span>

## <a name="supported-output-pipes"></a><span data-ttu-id="5f06d-288">Ondersteunde uitvoerpijpen</span><span class="sxs-lookup"><span data-stu-id="5f06d-288">Supported output pipes</span></span>

<span data-ttu-id="5f06d-289">Live response ondersteunt uitvoerpijpleidingen naar CLI en bestand.</span><span class="sxs-lookup"><span data-stu-id="5f06d-289">Live response supports output piping to CLI and file.</span></span> <span data-ttu-id="5f06d-290">CLI is het standaarduitvoergedrag.</span><span class="sxs-lookup"><span data-stu-id="5f06d-290">CLI is the default output behavior.</span></span> <span data-ttu-id="5f06d-291">U kunt de uitvoer naar een bestand uitvoeren met de volgende opdracht: [opdracht] > [bestandsnaam].txt.</span><span class="sxs-lookup"><span data-stu-id="5f06d-291">You can pipe the output to a file using the following command: [command] > [filename].txt.</span></span>  

<span data-ttu-id="5f06d-292">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="5f06d-292">Example:</span></span>

```console
processes > output.txt
```

## <a name="view-the-command-log"></a><span data-ttu-id="5f06d-293">Het opdrachtlogboek weergeven</span><span class="sxs-lookup"><span data-stu-id="5f06d-293">View the command log</span></span>

<span data-ttu-id="5f06d-294">Selecteer het **tabblad Opdrachtlogboek** om de opdrachten weer te geven die tijdens een sessie op het apparaat zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5f06d-294">Select the **Command log** tab to see the commands used on the device during a session.</span></span> <span data-ttu-id="5f06d-295">Elke opdracht wordt bijgespoord met volledige details, zoals:</span><span class="sxs-lookup"><span data-stu-id="5f06d-295">Each command is tracked with full details such as:</span></span>
- <span data-ttu-id="5f06d-296">ID</span><span class="sxs-lookup"><span data-stu-id="5f06d-296">ID</span></span>
- <span data-ttu-id="5f06d-297">Opdrachtregel</span><span class="sxs-lookup"><span data-stu-id="5f06d-297">Command line</span></span>
- <span data-ttu-id="5f06d-298">Duur</span><span class="sxs-lookup"><span data-stu-id="5f06d-298">Duration</span></span>
- <span data-ttu-id="5f06d-299">Status- en invoer- of uitvoerzijdebalk</span><span class="sxs-lookup"><span data-stu-id="5f06d-299">Status and input or output side bar</span></span>

## <a name="limitations"></a><span data-ttu-id="5f06d-300">Beperkingen</span><span class="sxs-lookup"><span data-stu-id="5f06d-300">Limitations</span></span>

- <span data-ttu-id="5f06d-301">Livereactiesessies zijn beperkt tot 10 livereactiesessies tegelijk.</span><span class="sxs-lookup"><span data-stu-id="5f06d-301">Live response sessions are limited to 10 live response sessions at a time.</span></span>
- <span data-ttu-id="5f06d-302">Grootschalige opdrachtuitvoering wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="5f06d-302">Large-scale command execution is not supported.</span></span>
- <span data-ttu-id="5f06d-303">De inactieve time-outwaarde voor livereactiesessie is 5 minuten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-303">Live response session inactive timeout value is 5 minutes.</span></span> 
- <span data-ttu-id="5f06d-304">Een gebruiker kan slechts één sessie tegelijk starten.</span><span class="sxs-lookup"><span data-stu-id="5f06d-304">A user can only initiate one session at a time.</span></span>
- <span data-ttu-id="5f06d-305">Een apparaat kan slechts in één sessie tegelijk worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="5f06d-305">A device can only be in one session at a time.</span></span>
- <span data-ttu-id="5f06d-306">De volgende limieten voor bestandsgrootte zijn van toepassing:</span><span class="sxs-lookup"><span data-stu-id="5f06d-306">The following file size limits apply:</span></span>
   - <span data-ttu-id="5f06d-307">`getfile` limiet: 3 GB</span><span class="sxs-lookup"><span data-stu-id="5f06d-307">`getfile` limit: 3 GB</span></span>
   - <span data-ttu-id="5f06d-308">`fileinfo` limiet: 10 GB</span><span class="sxs-lookup"><span data-stu-id="5f06d-308">`fileinfo` limit: 10 GB</span></span>
   - <span data-ttu-id="5f06d-309">`library` limiet: 250 MB</span><span class="sxs-lookup"><span data-stu-id="5f06d-309">`library` limit: 250 MB</span></span>

## <a name="related-article"></a><span data-ttu-id="5f06d-310">Gerelateerd artikel</span><span class="sxs-lookup"><span data-stu-id="5f06d-310">Related article</span></span>
- [<span data-ttu-id="5f06d-311">Voorbeelden van livereactieopdracht</span><span class="sxs-lookup"><span data-stu-id="5f06d-311">Live response command examples</span></span>](live-response-command-examples.md)
